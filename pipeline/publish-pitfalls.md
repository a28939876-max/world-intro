# Publishing mechanics — GitHub pitfalls cheat sheet

Battle-tested traps, ordered by publishing step.

## 1. Three ways to create the repo

SSH-key auth (`ssh -T git@github.com` reports your account) **can push, but cannot create a repo.** Creating needs an API token or the web:

| Path | Condition | Action |
|---|---|---|
| gh CLI | `which gh` exists and logged in | `gh repo create <name> --public --source . --push` — one shot |
| User creates via web | zero credentials | have them open github.com/new: name it, pick Public, **check no init files** (no README/license — they collide with your first push) |
| User-provided PAT | user is willing | a classic token with `public_repo` is enough; shortest expiry; remind them to revoke after |

Probe local conditions (gh, token, netrc) before offering options — don't assume.

## 2. README placeholder & remote

- During development, use `<you>` as a placeholder in the clone URL; once the account is fixed, `sed`-replace all and commit separately.
- `git remote add origin git@github.com:<owner>/<repo>.git` can be set before the repo exists — the push fails harmlessly, and works the moment the repo is created.

## 3. Author attribution (Contributors)

- GitHub links Contributors by **commit author email ↔ account**. The machine default identity (`user@host.local`) links to nobody → empty Contributors.
- Most reliable email: `<login>@users.noreply.github.com` (no verification needed, always links).
- Set the repo-local identity **before** publishing to avoid a later rewrite:
  ```bash
  git config user.name "<login>" && git config user.email "<login>@users.noreply.github.com"
  ```

## 4. Safe history rewrite (remedy after pushing)

```bash
FILTER_BRANCH_SQUELCH_WARNING=1 git filter-branch -f --env-filter '
  export GIT_AUTHOR_NAME="<login>"; export GIT_AUTHOR_EMAIL="<login>@users.noreply.github.com";
  export GIT_COMMITTER_NAME="<login>"; export GIT_COMMITTER_EMAIL="<login>@users.noreply.github.com"' -- --all
```

- `Co-Authored-By:` lines in commit messages are untouched (collaboration record kept, doesn't affect Contributors attribution).
- A force push is required after — see the next two traps.
- Only do this when the repo is freshly published and nobody has cloned/forked; if there's downstream, don't rewrite.

## 5. The `--force-with-lease` "stale info" trap

**Symptom**: `git push --force-with-lease` reports `! [rejected] main -> main (stale info)`.
**Cause**: `filter-branch -- --all` also rewrote the local `refs/remotes/origin/main` tracking ref, so the lease's "expected remote value" is no longer the real remote.
**Fix**: `git fetch origin` first (refresh the tracking ref to the real remote), then re-run the same push.

## 6. Handling a permission-layer block

An agent environment's permission classifier may refuse a force push to the default branch (even if the user verbally confirmed — the classifier can't see the conversation). Correct order:

1. Stop and explain: the current state, what you want to do, why it's needed.
2. Give the user two paths: **they run one line in their own terminal** (cleanest); or add a Bash allow-rule via settings and the agent runs it.
3. Never route around the block with a side tool.
4. The user's own run can still hit the stale-info trap (§5) — the agent can run the harmless `git fetch origin` first to fix the environment, then let the user re-run the push.

## 7. Live verification checklist

After a successful push, verify each item — don't trust the push output alone:

```
[ ] GET api.github.com/repos/<owner>/<repo> → private:false, correct default_branch
[ ] raw README readable (raw.githubusercontent.com/<owner>/<repo>/main/README.md)
[ ] cover/image resources return HTTP 200
[ ] (via API) contributors list = the user's account with the right commit count
[ ] remind the user to add the About description + topics on the web (the API usually lacks permission); hand them paste-ready copy
```
