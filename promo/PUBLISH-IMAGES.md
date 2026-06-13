<!-- 内部发布手册（不随推文发出）。文案见 launch-copy.md。 -->

# world-intro 各平台图片发布编排

卖点：你写了个好用的 skill 想开源，world-intro 帮你判断值不值得开，再通用化、验证、叙事、推广。钩子：它是用它自己开源出来的。

## 资产清单

| 文件 | 尺寸 / 比例 | 角色 | 适配平台 |
|---|---|---|---|
| `assets/cover.png` | 1200×630 · 1.91 | 主 banner（wordmark + 五动词） | 推特头图、微信头图、GitHub |
| `assets/input-output.png` | 1600×760 · 2.10 | 输入→输出讲解图（私有 skill → 开源项目） | 微信正文、推特第二张 |
| `promo/xhs/wi-1-cover.png` | 1080×1440 · 3:4 | 小红书封面（钩子：用它开源它自己） | 小红书 |
| `promo/xhs/wi-2-pain.png` | 1080×1440 · 3:4 | 小红书 P2（三个开源前的卡点） | 小红书 |
| `promo/xhs/wi-3-how.png` | 1080×1440 · 3:4 | 小红书 P3（六步流程 + 五动词） | 小红书 |
| `promo/xhs/wi-4-cta.png` | 1080×1440 · 3:4 | 小红书 P4（自我开源判决 + 仓库 + 标签） | 小红书 |

## 1) 小红书（4 张竖卡，按序）

1. `wi-1-cover.png` → 2. `wi-2-pain.png` → 3. `wi-3-how.png` → 4. `wi-4-cta.png`
正文用 [`launch-copy.md` 第三节](./launch-copy.md)；仓库链接放评论区第一条。

## 2) 微信公众号

- **头图**：`cover.png`（或 `input-output.png`，更讲清"它做什么"）。
- **正文插图**：开头讲卡点之后插 `input-output.png`（一图说清私有 skill → 开源项目）；正文用 launch-copy.md 第一节，可直接带可点链接。

## 3) 推特 / X

- 第一张（时间线 16:9 预览）：`cover.png`（1.91，接近 16:9，不被裁）。
- 第二张：`input-output.png`（点开看"输入→输出"全貌）。
- 英文帖投 HN/技术圈、中文帖各一版，文案见 launch-copy.md 第二节。

## 待补（可选）

- 英文版小红书/Twitter 卡（现卡片中文）：HTML 源在 `assets/*.html` 与 `promo/xhs/*.html`，改文案重渲即可。
- 发布前把 launch-copy.md 各平台正文过一遍 humanizer-zh + codex 反 slop 审核（门禁③）。

> 所有图的 HTML 源都在 `assets/` 和 `promo/xhs/`，改文案后用本机 Chrome `--headless=new --screenshot "file://…"` 重渲，无需起服务器。
