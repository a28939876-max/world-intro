<!-- 内部发布文案（不随推文发出）。卖点收窄=你写了个好用的 skill 想开源,但不知道值不值得开、会不会被官方碾压、推出去会不会石沉大海;world-intro 把这一条龙包了。钩子=它是用它自己开源出来的。发布前过一遍 humanizer-zh + codex 反slop 审核(门禁③)。 -->

# world-intro 发布文案

卖点一句话：**你写了个好用的 skill 想开源，world-intro 先帮你判断值不值得开，再帮你通用化、验证、写成让人想用的样子、推出去被看见。**
钩子：**这个工具是用它自己开源出来的。**

## 一、微信公众号

### 标题候选
- A：我写了个帮人开源工具的东西，然后用它把它自己开源了
- B：开源前最该问的不是"怎么发"，是"值不值得发"
- C：你的 skill 只在自己电脑上好用，推上 GitHub 就没人理

### 正文

我手上攒了不少自己写的小工具，自己用着顺手。每次想开源，卡的都不是写代码，是另外几件事：这东西到底值不值得开，会不会人家早做好了；我的脚本里全是自己的路径和密钥，怎么剥干净；真推上去，0 star 了又怎么办。

所以我把这套自己摸出来的流程做成了一个 skill，叫 world-intro。你跟它说一句"帮我把这个工具开源"，剩下它来。它先去搜一圈，告诉你这东西到底值不值得开——要是早有人做透了，就别硬发，去给那个项目补一刀更划算。值得开，它再把工具里只适合你电脑的那些路径、密钥改掉，让别人也能跑；拿真实数据跑一遍当例子；把 README 写成人话；最后连发布带各平台的文案配图，一并给你弄好。

做完我干了件有意思的事：拿 world-intro 开源 world-intro 自己。

它先给自己搜了一圈。最像的是个叫 open-source-hardening-skills 的项目，9 个星，但人家管的是把代码弄干净、加测试；我这套管的是该不该开、怎么改成别人能用的、怎么写得让人想点进来。两件事，不打架。它给的结论是：做这行的人不少，但没人做全，可以开，README 里把跟人家的分工写清楚就行。

接着改通用、写 README、配图、发布。你现在看到的这个仓库，它的判断、例子、README，都是它自己跑出来的。例子也不是编的，就是我之前用这套流程开源的两个真东西：一个查 skill 血统的 skill-lineage，一个"说句需求帮你把工具找齐"的 world-aid。

如果你也有个自己用着不错、一直没开源的工具，可以拿去试试。

🔗 github.com/a28939876-max/world-intro

---

## 二、推特 / X

### 英文帖（投 HN / 技术圈）

I kept building little tools I used daily but never open-sourced. The hard part was never the code. It was knowing whether it was even worth shipping, stripping my paths and keys out of it, and not landing on 0 stars.

So I turned that into a skill: world-intro. You say "open-source this tool" and it walks six gated steps — a real worth-it search first (ship / differentiate / don't and contribute upstream instead), generalize it out of your machine, prove it on real data that becomes the README cases, polish the README against anti-slop rules, publish, promote.

Then I pointed it at itself and open-sourced the pipeline with itself. Its own P0 verdict: the nearest tool (open-source-hardening-skills, 9★) hardens your code — tests, CI; this one handles whether to ship, how to generalize, and how to get seen. Different lanes, so: ship, name the difference.

The README, the verdict, the cases — all produced by running it on itself.
🔗 github.com/a28939876-max/world-intro

### 中文帖（配 cover 图）

我老写些自己用着顺手的小工具，但从不开源。难的从来不是代码，是三件事：值不值得开、怎么把我的路径和密钥剥干净、推出去会不会 0 star。

我把这套流程做成了一个 skill，world-intro。你说一句"帮我开源这个"，它会先帮你查有没有同类、值不值得开，再把只适合你电脑的部分改掉，拿真实数据跑个例子，把 README 和发布文案都整理出来。

然后我拿它把它自己开源了。它给自己的判断、例子、README，都是它自己跑出来的。
🔗 github.com/a28939876-max/world-intro

---

## 三、小红书

### 标题候选
- A：我写了个帮人开源的工具，然后用它把它自己开源了
- B：开源前先别急着发，先问值不值得发
- C：你电脑里那个好用的小工具，其实可以开源

### 正文

我电脑里攒了一堆自己写的小工具，用着都挺顺手，但从来没开源过。

每次想发都卡在同样几件事：这东西值不值得开，会不会别人早做好了；我脚本里全是自己的路径和密钥，得删干净；真发出去 0 star 了又图啥。

后来我把这套自己摸出来的流程做成了一个 skill，叫 world-intro。你跟它说一句"帮我把这个开源"，它先帮你搜一圈、看值不值得开，再把只属于我电脑的路径、配置这些去掉，拿真实数据跑一遍当例子，把 README 写成人话，发布，再配好各平台的文案和图。

最有意思的是，我拿它把它自己开源了。你现在能看到的这个仓库，开源判断、例子、README，全是它自己跑出来的。

有自己写的小工具一直没开源的，可以拿去试。

🔗 github.com/a28939876-max/world-intro

#开源项目 #AI工具 #程序员日常 #效率工具 #ClaudeCode
