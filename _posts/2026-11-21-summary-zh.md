---
layout: default
title: "Horizon Summary: 2026-11-21 (ZH)"
date: 2026-11-21
lang: zh
---

> 从 41 条内容中筛选出 17 条重要资讯。

---

**科技新闻**
1. [陶哲轩讨论无外力 Navier–Stokes 奇点与广义黎曼猜想](#item-tech-news-1) ⭐️ 9.0/10
2. [Levent Alpöge 声称证明广义黎曼猜想并提供 Lean 形式化](#item-tech-news-2) ⭐️ 8.0/10
3. [GitHub 仓库声称给出 Navier–Stokes 有限时间爆破解](#item-tech-news-3) ⭐️ 8.0/10
4. [KVM 漏洞 CVE-2026-99312 可泄露 AMD 宿主内存](#item-tech-news-4) ⭐️ 8.0/10
5. [台积电暂停中国公司 16nm 及以下订单](#item-tech-news-5) ⭐️ 8.0/10
6. [浙江大学首次真机实现 QRAM](#item-tech-news-6) ⭐️ 8.0/10
7. [Thinking Machines 推出 Inkling 2 Mini 本地小模型](#item-tech-news-7) ⭐️ 7.0/10
8. [Aaronson 博客讨论 LLM 与 Lean 定理证明](#item-tech-news-8) ⭐️ 7.0/10
9. [AI 抛售抹去纳斯达克 2026 年涨幅，Anthropic 上市次日承压](#item-tech-news-9) ⭐️ 7.0/10
10. [Vakil 宣布 Masullo 提出广义黎曼猜想证明草案](#item-tech-news-10) ⭐️ 7.0/10
11. [OpenAI 称 GPT-6.2 推理链提取成功率降至 0.2%](#item-tech-news-11) ⭐️ 7.0/10
12. [特朗普拟对海外建 AI 数据中心的美企征巨额税](#item-tech-news-12) ⭐️ 7.0/10
13. [微软发布 Windows USB4 RDMA 开发者预览](#item-tech-news-13) ⭐️ 7.0/10
14. [OpenRouter 警告 MiniMax 模型提示词可能遭第三方读取](#item-tech-news-14) ⭐️ 7.0/10

**科技博客**
1. [为什么缓存 LLM 输出难以省钱](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [沃什回避前瞻指引，美联储官员却更频繁发声](#item-finance-news-1) ⭐️ 7.0/10
2. [美国企业转为净发行股票，净发行量达总市值 3.1%](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [陶哲轩讨论无外力 Navier–Stokes 奇点与广义黎曼猜想](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 9.0/10

陶哲轩（Terry Tao）在博客中讨论无外力 Euler 奇点、无外力 Navier–Stokes 奇点以及广义黎曼猜想，Hacker News 的讨论随后集中在 Lean 形式化和超大型机器可检验证明的可信度上。现有材料没有给出证明的具体陈述、形式化代码规模或独立复现结果，因此对数学家和形式化验证研究者而言，这些主张能否被外部检查确认仍是关键。评论称有两个独立内核接受了相关证明，但这是社区转述，不能替代源文或独立验证。

hackernews · archon1410 · 11月20日 17:21 · [社区讨论](https://news.ycombinator.com/item?id=50578358)

**「背景」** 三维不可压纳维-斯托克斯方程（包括无外力情形）的光滑解是否会在有限时间内产生奇点，是克雷研究所的千禧年难题之一；广义黎曼猜想则把黎曼ζ函数的零点分布猜想推广到狄利克雷 L 函数。讨论中反复提到的 Lean 是交互式定理证明器，其证明最终由一个小型内核逐项检查，因此“构建通过”只表示证明项通过了该内核对所陈述定理的检查，并不自动说明定理陈述就是研究者想要证明的命题。

**「对研究者的实际影响」** 对关注这些结果的数学研究者和形式化验证社区而言，当前的实际门槛已从“是否给出了证明”转为“机器检查能否支撑到所声称的命题”：据 tool-2-3，MIT 的检查显示相关 Lean 代码能够编译并通过独立检查器；tool-2-1 显示 Navier–Stokes 的 AI 解法也附有 Lean 形式化证明。因此接下来的关键动作是核对 Lean 中写下的形式化陈述是否与所声称的定理一致，并在独立内核上复现构建；多个内核同时接受只能减少内核实现缺陷带来的风险，并不覆盖“形式化命题是否就是目标命题”这一问题。

**「社区讨论」** 最实质的争论是“内核通过”能证明到什么程度：chunky1994 提到两个独立内核接受结果，认为内核漏洞被利用的可能性较低；swingboy 则以约 1500 万行 Lean 代码为例反问，构建通过如何保证证明的是目标命题，而不是某个“1+1=2”式的小定理。另有 sega\_sai 等评论者表达了对 AI 研究能力与个人科研空间的焦虑，这属于个人感受，不是对结果的技术确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/navier-stokes-solution/">On the Navier–Stokes Millennium Prize Problem | OpenAI</a></li>
<li><a href="https://timesof.ai/2026/11/anthropic-mathematician-alpoge-riemann-hypothesis-proof-claude-lean-checks-pass">Riemann Hypothesis Proof Claimed With Claude | Times of AI</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#formal verification`, `#Lean`, `#Navier-Stokes`, `#Riemann Hypothesis`

---

<a id="item-tech-news-2"></a>
### [Levent Alpöge 声称证明广义黎曼猜想并提供 Lean 形式化](https://alpo.ge/remark.pdf) ⭐️ 8.0/10

Levent Alpöge 在 alpo.ge/remark.pdf 中声称，他与 Claude 合作发现了黎曼猜想的证明，该方法还可扩展到广义黎曼猜想，并称相关论证已在无额外假设下完成形式化。Hacker News 讨论称其 Lean 产物约 1.3GB、约 1500 万行代码，但目前没有独立验证或同行评审确认这一结果。

hackernews · iamronaldo · 11月20日 14:16 · [社区讨论](https://news.ycombinator.com/item?id=50574968)

**「背景」** 黎曼猜想是 1859 年提出的关于黎曼ζ函数零点分布的经典问题；广义黎曼猜想是对它的扩展。Lean 是交互式定理证明器，可机械检查形式化证明，但有数学家提醒，还需确认形式化陈述确实对应该证明的命题。

**「影响」** 在独立检查完成前，研究者和形式化验证社区只能将此视为待核验声明；据评论所述，核验需处理约 1.3GB、约 1500 万行的 Lean 产物，而编译通过不能替代对数学论证的独立审查。

**「社区讨论」** 评论中最具体的信息是证明产物的规模：约 1.3GB、约 1500 万行 Lean 代码；还有人贴出 Alpöge 2014 年称解决黎曼猜想是人生目标的采访。讨论中没有人提供独立验证，更多是对潜在影响和 AI 角色的感叹与推测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>
<li><a href="https://www.nacionale.com/en/articles/has-riemann-hypothesis-been-proved-levent-alpoge-claude-anthropic-claim-lean">Riemann hypothesis proof claimed with Claude , unverified</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis With...</a></li>

</ul>
</details>

**标签**: `#Riemann Hypothesis`, `#Lean`, `#formal verification`, `#mathematics`, `#unverified claim`

---

<a id="item-tech-news-3"></a>
### [GitHub 仓库声称给出 Navier–Stokes 有限时间爆破解](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

一篇提交到 Hacker News 的帖子链接到 GitHub 仓库 tristanbuckmaster/navier-stokes，声称给出了 Navier–Stokes 方程的有限时间爆破解。当前提供的条目没有摘要、论文正文或独立验证，因此这仍是一项待核实的研究声明，而不是已确认的数学结果。评论中有人把它与据称由 OpenAI 给出的“强制”版本区分开来，称该仓库处理的是无外力情形；这一对比同样来自评论，尚未在给定材料中得到确认。

hackernews · trotro · 11月20日 15:34 · [社区讨论](https://news.ycombinator.com/item?id=50576232)

**「背景」** 纳维–斯托克斯方程解的存在性与光滑性是千禧年大奖难题之一；该仓库被描述为 Alpöge 与 Buckmaster 论文的配套材料，包含 79 页论文 PDF 和 Lean 4 形式化，覆盖定理 1.1、定理 7.1、推论 7.2 及附录 B 的陈述与证明。论文摘要称，作者构造了 R^3 上紧支、T^3 上周期的光滑初值，使无外力纳维–斯托克斯解在有限时间爆破，并依赖由区间算术检验的近似自相似剖面证书。

**「影响」** 对研究 Navier–Stokes 方程的人而言，当前能采取的行动是核查仓库内容并等待独立验证；在验证出现前，不应把这项声明当作可引用的结论或据此修改数值方法。

**「社区讨论」** 评论者最实质的争论是这项声明与据称的 OpenAI 结果有何不同：tancop 认为此仓库针对无外力版本，因而比用“精心设计的外部力”破坏方程的例子更接近真实情形；xianshou 则把它放进同一天出现多项重大数学声明的叙事中。上述说法均为评论者主张，给定材料没有提供论文或验证来支持任何一方。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://hotrepo.ai/tristanbuckmaster/navier-stokes">tristanbuckmaster/navier-stokes: Lean 4 formalization of a ...</a></li>
<li><a href="https://aixiv.online/abs/2611.02204">[2611.02204] Finite-time blow-up for the Navier–Stokes ...</a></li>

</ul>
</details>

**标签**: `#Navier-Stokes equations`, `#mathematical research`, `#fluid dynamics`, `#research breakthrough`, `#Hacker News`

---

<a id="item-tech-news-4"></a>
### [KVM 漏洞 CVE-2026-99312 可泄露 AMD 宿主内存](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

Linux KVM 被曝出 CVE-2026-99312：在启用嵌套虚拟化的 AMD 主机上，虚拟机可以读取宿主内存，研究人员在 DigitalOcean 环境中从虚拟机内读取到约 127 GB 宿主内存。上游修复已于 11 月 18 日随稳定内核 7.3.5 等版本发布，但 Debian、Ubuntu 等发行版内核尚未修复。补丁到位前，受影响环境可以关闭嵌套虚拟化作为缓解措施；该消息来自二手摘要，具体受影响版本范围仍应以官方公告为准。

telegram · zaihuapd · 11月20日 14:23

**「背景：嵌套页表与 INIT 复位」** 嵌套虚拟化允许客户机内部再运行一层虚拟化管理程序，因此 KVM 需要借助嵌套页表（NPT）把客户机的物理地址映射到宿主机的物理地址。Red Hat 的漏洞说明指出，在模拟处理器 INIT 复位且分页处于关闭状态时，KVM 没有重置 NPT 指针，导致此前引用的页表页可能被释放并重新分配，客户机内的攻击者由此可以伪造页表项（tool-1-1）。这一缺陷路径也解释了该漏洞为何只出现在启用嵌套虚拟化的 AMD 主机上。

**「影响与应对」** 运行启用嵌套虚拟化的 AMD 主机的云平台和自建虚拟化集群，在发行版内核尚未修复期间仍暴露于宿主内存被虚拟机读取的风险；运维方需要核对内核版本并应用上游修复，或在补丁到位前关闭嵌套虚拟化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99312">CVE-2026-99312 - Red Hat Customer Portal</a></li>

</ul>
</details>

**标签**: `#KVM`, `#Linux kernel`, `#CVE`, `#virtualization security`, `#AMD`

---

<a id="item-tech-news-5"></a>
### [台积电暂停中国公司 16nm 及以下订单](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

据 AppleInsider 报道，台积电已通知客户暂停接受中国公司的 16nm 及以下先进制程订单。按收紧后的美国出口新规，除非事先取得美国许可或豁免，台积电不得供货；报道称，中国企业因此只能转向 28nm、40nm 等旧制程，也无法获得 AI 数据中心所需的高带宽内存（HBM）。此前台积电可自行评估客户设计是否符合豁免条件，现在客户须提前申请，而美国获批名单中有苹果、AMD、英伟达，尚无中国公司；台积电表示将遵守新规。该消息目前来自简短转述，尚无台积电或美方公告提供更多细节。

telegram · zaihuapd · 11月21日 02:01

**「背景」** 16nm 及以下属于此次美国新规覆盖的先进逻辑制程；28nm、40nm 等成熟制程不在同一限制范围内，相关订单可继续。此前台积电可自行评估客户设计是否符合豁免条件，新规要求客户提前申请美国出口许可或豁免，台积电才能供货。

**「影响」** 目前美国获批名单中没有中国公司，因此依赖台积电 16nm 及以下制程的中国芯片设计企业须改用 28nm、40nm 等旧节点，或逐单申请许可/豁免；这也会限制其 AI 数据中心芯片获取所需的高带宽内存，相关订单和替代工艺需重新评估。

**标签**: `#TSMC`, `#US export controls`, `#semiconductors`, `#China`, `#AI chips`

---

<a id="item-tech-news-6"></a>
### [浙江大学首次真机实现 QRAM](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

浙江大学团队报告在自主制备的超导量子芯片“天目 2 号”上首次于真机实现量子随机存储器（QRAM），并称成果已发表于《自然·物理》。原型可调取 4 位和 8 位数据，准确率分别为 80.9%和 60.4%，线路深度较未优化方案降低 30%以上，同时首次验证该架构具备局部抗噪特性。上述数据来自二手摘要，尚无论文链接或独立复现，8 位准确率偏低且规模化能力未验证；团队称下一步将推进 QRAM 的规模化研究。

telegram · zaihuapd · 11月21日 08:31

**「背景」** QRAM（量子随机存储器）旨在让量子计算机像访问内存一样按地址调取数据，并支持地址处于量子叠加态时完成访问，这是许多需要读取大量数据的量子算法的基础组件。其实现难点在于寻址和读出过程不能破坏量子态，因此此前长期缺少真机层面的验证。

**「影响」** 对量子算法实现而言，QRAM 若能扩展，可降低数据调取所需的线路深度；但当前 8 位仅 60.4%的准确率表明它仍处于原型验证阶段，距离作为可用的量子内存还有明显差距。

**标签**: `#quantum computing`, `#QRAM`, `#superconducting qubits`, `#hardware`, `#research`

---

<a id="item-tech-news-7"></a>
### [Thinking Machines 推出 Inkling 2 Mini 本地小模型](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 7.0/10

Thinking Machines 发布 Inkling 2 Mini，一款面向本地运行的小型语言模型，采用循环 Transformer 架构，发布后在 Hacker News 引发大量讨论。社区评论称其基准可接近更大的 Qwen 模型，并报告在 llama.cpp 的 Vulkan 后端上，Ryzen 395 解码约 27 tokens/s、M1 Pro 32GB 约 10 tokens/s。上述基准对比和速度均来自评论者，尚未独立验证；评论还提到本地部署需应用若干未合并的 llama.cpp PR 和一个可带来约 30% 加速的小补丁。

hackernews · jasondavies · 11月20日 20:12 · [社区讨论](https://news.ycombinator.com/item?id=50581260)

**「背景」** Inkling 2 Mini 属于 Thinking Machines 的 Inkling 2 系列，该系列上一款产品 Inkling 2 Small 于 2026 年 11 月 5 日发布，官方称其在指令遵循、审慎考虑改动以及无需提示即自行核验结果方面较初代 Inkling 有所改进。所谓“循环式 transformer”（looped transformer），是指同一组中间层在每个 token 上被重复执行；Inkling 2 Mini 的具体做法是让中间层运行三次，官方称这能使模型以更少的 token 完成推理，尤其适用于 agentic coding 这类依赖推理质量的任务。

**「本地部署的实际门槛」** 对打算本地运行的开发者来说，llama.cpp 路径目前仍不顺畅：有用户报告需叠加四个尚未合并的 PR（32694、32657、32429、32704），再加一段可带来约 30% 解码提速的源码补丁才够实用。现有使用者自测速度差异明显——Ryzen 395 上 Vulkan 后端约 27 tokens/s，M1 Pro 32GB 以 q4 量化运行约 10 tokens/s；这些数字以及该模型与 Qwen3.8-27B 的基准对比均为社区报告，尚未获得独立验证。

**「社区讨论」** 评论者对基准的可信度存在分歧：有人认为若结果在真实场景成立，循环架构的小模型会非常有竞争力，也有人强调这些对比尚未验证。另有评论赞赏用完整小游戏或应用来展示模型能力，认为这比单纯列分数更能说明问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-small/">Introducing Inkling 2 Small - Thinking Machines Lab</a></li>

</ul>
</details>

**标签**: `#LLM`, `#local inference`, `#model release`, `#llama.cpp`, `#transformer architecture`

---

<a id="item-tech-news-8"></a>
### [Aaronson 博客讨论 LLM 与 Lean 定理证明](https://scottaaronson.blog/?p=10344) ⭐️ 7.0/10

Hacker News 上出现一篇指向 Scott Aaronson 博客的提交，讨论大语言模型（“随机鹦鹉”）与数学定理证明，并牵涉 Lean 形式化验证和自动定理求解。由于提交未附文章正文，无法核实文中是否给出具体证明、实验结果或可复现的技术细节；标题所称“证明了黎曼猜想”应视为讽刺性说法，而不是已确认的成果。该提交获得 278 分和 248 条评论，讨论热度明显，但评论本身不能替代对原文的验证。

hackernews · stratos123 · 11月20日 20:03 · [社区讨论](https://news.ycombinator.com/item?id=50581084)

**「背景」** 黎曼猜想断言 ζ 函数的所有非平凡零点实部均为 1/2，是数学中最著名的未解问题之一；广义黎曼猜想则把这一断言推广到更广泛的一类 L 函数。Lean 是交互式定理证明器，其中的证明由机器逐行检查，因此“Lean 证明”在形式上可核验，但证明的规模以及它是否确实对应所声称的命题，仍是判断的关键。据 tool-1-2 转述，Levent Alpöge 称 Anthropic 的模型产出了一份 1740 万行的 Lean 证明来证明广义黎曼猜想，Scott Aaronson 则表示该结果仍需审视，但他没有看到 AI 利用 Lean 已知弱点的迹象。

**「社区讨论」** 评论者 esjeon 将相关思路概括为“Lean + 随机预测器 = 暴力定理求解器”，并认为 AlphaGo 在精神上类似；hoppp 则反问是否真有人能完整理解 Lean 的整个体系。另有评论把讨论引向“仍应修补漏洞”的一般原则，但这些都属于观点交流，未对原文的技术结论形成一致判断。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://scottaaronson.blog/?p=10344">Shtetl-Optimized » Blog Archive » The stochastic parrots have ...</a></li>
<li><a href="https://hn.today/s/the-stochastic-parrots-have-apparently-proved-the-riemann-hypothesis">The stochastic parrots have apparently proved the Riemann ...</a></li>

</ul>
</details>

**标签**: `#LLMs`, `#formal verification`, `#Lean`, `#automated theorem proving`, `#AI criticism`

---

<a id="item-tech-news-9"></a>
### [AI 抛售抹去纳斯达克 2026 年涨幅，Anthropic 上市次日承压](https://www.theguardian.com/business/2026/nov/20/global-stock-markets-slump-anthropic-ipo-ai-sell-off) ⭐️ 7.0/10

据《卫报》报道，一轮由 AI 板块主导的抛售使纳斯达克综合指数回吐了 2026 年的全部涨幅，并压在 Anthropic 上市后的第二个交易日上。报道将该轮回调与市场对 AI 相关估值的情绪变化联系在一起，但原文正文未提供，因此具体指数点位、跌幅以及 Anthropic 的发行价与成交价均无法从现有材料中确认。可确认的仅是标题层面的事实：纳斯达克年内涨幅已被完全抹去，且抛售恰逢 Anthropic 挂牌初期。

hackernews · cdrnsf · 11月20日 13:29 · [社区讨论](https://news.ycombinator.com/item?id=50574383)

**「背景」** Anthropic 本周进行的 IPO 被 247wallst 称为有记录以来规模最大的 IPO；其在上市首日上涨后，第二个交易日回吐了大部分首日涨幅。此前 AI 相关交易是推动纳斯达克 2026 年上涨的主要力量之一，而 11 月 20 日的科技股抛售使该指数年内涨幅全部消失。

**「社区讨论」** 有评论者从经济核算角度提出疑问：如果原本价值十亿美元、支付高薪的行业被廉价通用 AI 替代，其产出价值会先下降，这在 GDP 上究竟意味着什么。另一位评论者称 Anthropic 当日多次逼近发行价、自开始交易以来下跌 21%，并把支撑价格的因素归于获配 IPO 股份者不愿兑现亏损，同时提到市场预期美联储将进一步加息；这些均为其个人判断，未在报道中得到证实。也有评论者推测，此次下跌可能影响 OpenAI 的上市计划及其后续融资能力，这属于猜测而非已知事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.france24.com/en/business/20261120-anthropic-shares-slide-on-second-day-of-trading-as-ai-jitters-fuel-tech-sell-off">Anthropic shares slide on second day of trading as AI jitters ...</a></li>
<li><a href="https://247wallst.com/investing/2026/11/20/anthropic-sinks-14-on-day-two-as-ai-sell-off-spreads-coreweave-falls-6-amazon-slips-2/">Anthropic Sinks 14% on Day Two as AI Sell-Off Spreads ...</a></li>
<li><a href="https://www.cnn.com/2026/11/20/investing/us-stocks-anthropic-ai">Nasdaq wipes out gains for the year as Anthropic IPO fails to ...</a></li>

</ul>
</details>

**标签**: `#AI industry`, `#stock market`, `#Anthropic`, `#IPO`, `#AI economics`

---

<a id="item-tech-news-10"></a>
### [Vakil 宣布 Masullo 提出广义黎曼猜想证明草案](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 7.0/10

Ravi Vakil 在博客中宣布，Alessandro Masullo 已提出广义黎曼猜想（GRH）的证明草案；Brian Conrad 已密切审阅数月，并给出了正在纳入修改的广泛反馈，Vakil 称目前“看起来不错”。原计划是邀请 Masullo 到斯坦福一年打磨写作、再经足够多人审阅后公布，但现在决定先发布当前草案。Vakil 特别说明这项工作完全由人完成、没有使用 AI；公告未提供技术细节，因此这仍是尚待验证的草案，不能视为已确立的证明。

rss · Simon Willison · 11月20日 19:21

**「背景」** 广义黎曼猜想（GRH）是黎曼猜想向更广泛一类 L 函数（如狄利克雷 L 函数）的推广，自 19 世纪提出以来一直没有得到证明；如果它成立，就能推出大量关于素数分布的结果。据 Scientific American 与《纽约时报》报道，同期还出现了另一份黎曼猜想的证明主张，由 Alpoge 与 Anthropic 的 Claude 参与得出；Brian Conrad 表示，Masullo 采用的是与那份工作完全不同的路线。两份草案目前都尚未被数学界接受，这也解释了 Vakil 为何特意强调这项工作“全部由人完成、没有使用 AI”。

**「验证负担转移」** 由于这份证明是以“仓促发布”的草稿形式公开、尚未走完原定的充分传阅与润色流程，验证工作实际上落到了数论界身上：在独立审阅确认之前，依赖广义黎曼假设的条件性结论（例如 Dirichlet L 函数不存在 Siegel 零点）不能把该草稿当作已确立结果引用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/dueling-claims-of-riemann-hypothesis-proofs-emerge/">Dueling claims of Riemann hypothesis proofs ... | Scientific American</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis With...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Riemann_hypothesis">Riemann hypothesis - Wikipedia</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#number theory`, `#research`, `#GRH`, `#proof`

---

<a id="item-tech-news-11"></a>
### [OpenAI 称 GPT-6.2 推理链提取成功率降至 0.2%](https://openai.com/index/combatting-adversarial-distillation/) ⭐️ 7.0/10

OpenAI 于 11 月 20 日发文介绍针对“对抗性蒸馏”的防御措施，称 GPT-6.2 Astra 与 Sol 已加强对推理链的保护；在其红队测试中，提取历史请求推理内容的成功率从 54.0% 降至 0.2%。OpenAI 还称今年每周会对数千至数万个蒸馏账号采取执法行动，并曾就 DeepSeek 疑似蒸馏行为向国会汇报。上述数据与效果均为 OpenAI 的厂商说法，现有信息未披露红队测试方法或独立验证结果。

telegram · zaihuapd · 11月21日 01:30

**「背景」** 对抗性蒸馏是指未经授权收集模型的输出或内部推理，以把一种模型的能力迁移到另一种模型。OpenAI 将相关防御描述为模型训练、防护措施、检测与账号执法的多层组合，本次公告正是在这一框架下说明推理链保护和执法进展。

**「影响」** 对通过 API 批量采集推理链来构建训练数据的开发者而言，OpenAI 持续的账号执法意味着相关操作可能直接导致账号被处置；在依赖此类数据前，需要评估合规与账号风险。0.2% 是 OpenAI 红队测试中的提取成功率，并非第三方复现的普遍防护水平。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/combatting-adversarial-distillation/">Combatting adversarial distillation - OpenAI</a></li>
<li><a href="https://xenospectrum.com/en/openai-gpt-distillation-defense-metrics/">OpenAI Cuts Success Rate of Reasoning-Extraction Attacks From ...</a></li>

</ul>
</details>

**标签**: `#AI model security`, `#adversarial distillation`, `#OpenAI`, `#reasoning models`, `#model IP`

---

<a id="item-tech-news-12"></a>
### [特朗普拟对海外建 AI 数据中心的美企征巨额税](https://apnews.com/article/trump-artificial-intelligence-data-centers-f1ac03b73d13445400eeed8631d9d879) ⭐️ 7.0/10

特朗普于当地时间 11 月 20 日在白宫记者会上表示，计划对在海外建设 AI 数据中心的美国科技公司征收“巨额税款”，目标是把这些数据中心留在美国，并维持对中国的 AI 竞争优势。他称尚未向政府内部官员透露该计划，报道也未给出税率、适用范围或实施时间，因此这仍是拟议表态而非已落地政策。特朗普同时敦促美国各地接纳数据中心，建议社区与开发商谈判争取付款；当前全美多地因用电需求和噪音问题反对新建项目。

telegram · zaihuapd · 11月21日 03:26

**「背景」** AI 数据中心是高耗电设施，美国多地社区已因用电需求和噪音问题反对新建项目，使选址成为扩张的现实约束。路透社和 ABC7 的同期报道均把特朗普的表态称为“计划惩罚”而非已生效政策，且目前没有正式法案文本、税率或执行时间表，因此这项提议仍处于政策设想阶段。

**「企业面临的直接不确定性」** 由于白宫尚未给出税率、时间表或执行方式，正在规划海外 AI 数据中心容量的美国企业暂时无法量化这项潜在税负，也难以判断是否应调整选址。若因此改在美国境内建设，则需应对多地社区因用电需求和噪音而提出的反对；特朗普本人建议社区与开发商谈判，争取由开发商向社区付款。

<details><summary>参考链接</summary>
<ul>
<li>Trump says US to penalize firms building data centers abroad - Reuters</li>
<li>Trump says he plans to penalize US tech companies that build AI data centers in other countries - ABC7 News</li>
<li><a href="https://www.ibtimes.com/trump-tax-ai-data-centers-overseas-3810039">Trump Threatens &#x27;Tremendous Tax&#x27; On US Tech Firms Building AI ...</a></li>

</ul>
</details>

**标签**: `#AI data centers`, `#US tech policy`, `#AI infrastructure`, `#geopolitics`, `#taxation`

---

<a id="item-tech-news-13"></a>
### [微软发布 Windows USB4 RDMA 开发者预览](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

微软发布 Windows 的 RDMA over USB4 开发者预览，允许通过普通 USB4 连接的多台 PC 共享内存和 GPU 算力，共同运行同一个本地 AI 模型，无需专用网卡或交换机。演示使用三台 AMD Ryzen AI Max+ 395，以 4-bit 量化运行 Qwen3-235B-A22B，达到约 18.5 token/s。该功能将通过 Windows Insider 推送，目前仍是开发者预览，并非已广泛可用的正式功能。

telegram · zaihuapd · 11月21日 06:13

**「背景」** RDMA（远程直接内存访问）此前主要用于 InfiniBand、RoCE 等数据中心网络，需要专用网卡与交换机，才能让一台机器直接读写另一台机器的内存。微软此次把这项能力搬到消费级 USB4 接口上：据微软 USB 博客，该开发者预览让相连的 Windows PC 合并内存容量与 GPU 算力，运行单台机器放不下的模型；参与演示的机器通过 USB4 直连，无需专用 RDMA 硬件。

**「影响」** 对希望在本机运行超出单机显存容量模型的 Windows 开发者而言，这套预览把多机互联的硬件门槛降到普通 USB4 连接；但需要多台具备 USB4 的 PC 和通过 Windows Insider 获取预览版，且 18.5 token/s 只是三机演示结果，不能视为普遍性能保证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcommunity.microsoft.com/blog/microsoftusbblog/introducing-rdma-over-usb4%C2%AE-on-windows-run-larger-local-ai-models-across-pcs/4574602">Introducing RDMA over USB4® on Windows: run larger local AI ...</a></li>
<li><a href="https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model">Microsoft brings RDMA over USB4 to Windows, allowing multiple ...</a></li>
<li><a href="https://www.guru3d.com/story/microsoft-previews-usb4-links-that-let-windows-pcs-pool-memory-and-gpu-resources/">Microsoft previews USB4 links that let Windows PCs pool ...</a></li>

</ul>
</details>

**标签**: `#Windows`, `#RDMA`, `#USB4`, `#local AI inference`, `#distributed computing`

---

<a id="item-tech-news-14"></a>
### [OpenRouter 警告 MiniMax 模型提示词可能遭第三方读取](https://news.ycombinator.com/item?id=50585962) ⭐️ 7.0/10

OpenRouter 的邮件通知称，用户发往 MiniMax 模型的请求内容可能已被第三方读取。安全研究者在 2026 年 7 月至 10 月发送含测试 URL 的提示词，第三方在 40 至 130 小时后访问了这些 URL；OpenRouter 将问题指向 MiniMax 及其转发方 AtlasCloud、Novita、StreamLake。相关端点的“零数据保留”标签已被下架，OpenRouter 建议涉及敏感凭证的用户更换 API Key 和密码。OpenRouter 官网目前尚未公布相关消息，当前信息来自 Telegram 摘要而非公开公告。

telegram · zaihuapd · 11月21日 06:53

**「背景」** OpenRouter 在模型提供商目录中按数据保留策略区分端点，标出“零保留”“有限保留”和“保留提示词”等类别；开发者通常据此判断某条路由能否用于处理敏感数据。此次下架相关端点的“零数据保留”标签，等于移除了原先可供路由选择依据的保留承诺。

**「对开发者的影响」** 使用这些 MiniMax 托管端点的开发者不能再把“零数据保留”视为敏感数据的保障；若提示词中曾包含 API Key、密码或其他凭证，应按通知建议轮换，并在 OpenRouter 恢复或重新说明相关端点的数据保留政策前避免发送机密内容。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openrouter.ai/providers">Browse the network of model providers available on OpenRouter .</a></li>

</ul>
</details>

**标签**: `#AI security`, `#data privacy`, `#OpenRouter`, `#MiniMax`, `#API security`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [为什么缓存 LLM 输出难以省钱](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月21日 00:00

**「背景」** LLM 推理成本通常靠缓存输入（KV cache）来避免每次重算整段上下文，于是自然有人设想也缓存输出：agent 经常复述代码片段和证据文档，而输出 token 又明显比输入 token 昂贵。

**「方案」** 作者设想的做法是让模型用“src/script.py:12-15”这类引用代替复述，再由 harness 展开，或者微调模型去引用自身历史。但他认为这只能优化用户可见的输出；按其个人 agent 历史，可见输出仅约 6%，推理 token 约占 50%，工具调用约占 44%。这正撞上 Amdahl 定律：即使乐观地省掉可见输出的三分之二，总输出 token 也只减少约 4%。真正的大头是占 94% 的不可见输出，减少它更依赖模型智能——更强模型能用更少推理和工具调用得到答案，因此会出现单 token 贵 5 倍、总 token 少 6 倍、总体反而更便宜的情况。作者对自己的 token 比例、以及前沿模型链式思考不常复述这一点只有中等信心，并指出工具调用内部是否也存在重复仍待验证。

**「启示」** 作者的核心结论是，输出缓存瞄准的是很小的一块，agent 的成本优化应关注推理和工具调用等不可见 token，而非表面的复述。更广泛地说，更强的模型可能靠减少总 token 用量而非降低单价来省钱。

**标签**: `#LLM inference`, `#output caching`, `#token economics`, `#AI agents`, `#Amdahl&\#x27;s law`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [沃什回避前瞻指引，美联储官员却更频繁发声](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

美联储官员近日密集公开表态，多数认为应尽快加息，而主席凯文·沃什继续避免就利率路径提供前瞻指引；美国银行分析称，过去两周的“美联储讲话”数量为 2025 年初以来同期最多。据 CME Group 的 FedWatch 数据，市场交易员认为 12 月至少加息 25 个基点的概率为 100%，并预计之后可能进一步加息。

rss · CNBC Finance · 11月20日 21:10

**「背景」** 美联储公开市场委员会（FOMC）负责制定利率，而“前瞻性指引”指官员提前暗示未来利率路径；沃什在 2026 年 6 月接任主席后拒绝这种沟通方式，他在首次会议上维持利率不变，当时通胀已处于多年高位。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.businessinsider.com/kevin-warsh-first-fomc-fed-meeting-interest-rates-2026-6">Fed Holds Rates Steady As Warsh Signals a Break... - Business Insider</a></li>
<li><a href="https://www.cnbc.com/2026/07/18/warshgpt-federal-reserve-communications-task-force-warsh.html">&#x27;WarshGPT&#x27;: Wall Street adapts to new era of Federal Reserve ...</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#Kevin Warsh`

---

<a id="item-finance-news-2"></a>
### [美国企业转为净发行股票，净发行量达总市值 3.1%](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

据 Acadian Asset Management 的 Owen Lamont 在致投资者信中的分析，美国企业已从 2024 年的净回购转为净发行股票，截至上周晚些时候净新股发行量相当于总市值的 3.1%。这一转变增加了市场需消化的股票供给，与回购减少流通股、支撑股价和每股收益的旧趋势相反。

rss · CNBC Finance · 11月20日 14:15

**「背景」** 过去多年，美国企业一直是股票的净回购方：回购减少了流通股数量，在资金追逐更少股票的情况下托举股价，同时因分母变小而抬高每股收益。Acadian 的分析显示，这一格局在 2026 年发生逆转，截至 11 月 12 日净发行量已达总市值的 3.1%。

**「影响」** 对现有股东而言，净发行取代回购意味着流通股不再收缩，回购对股价和每股收益的支撑减弱，新增供给可能成为牛市的逆风。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.acadian-asset.com/investment-insights/owenomics/the-smart-money-is-selling-equity">The smart money is selling equity | Acadian Asset Management</a></li>

</ul>
</details>

**标签**: `#equity issuance`, `#stock buybacks`, `#AI capex`, `#IPO market`, `#market liquidity`

---