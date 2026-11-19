---
layout: default
title: "Horizon Summary: 2026-11-19 (ZH)"
date: 2026-11-19
lang: zh
---

> 从 43 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [谷歌发布 Gemini 4 Neon，主打编程与科研工作流](#item-tech-news-1) ⭐️ 9.0/10
2. [Wiz 报告 Nginx HTTP/2 未认证 RCE 漏洞](#item-tech-news-2) ⭐️ 8.0/10
3. [Xint 披露 5 个 nginx 漏洞链，可提权至主机 root](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9 退出法国，DNS 不应成为反盗版执法点](#item-tech-news-4) ⭐️ 7.0/10
5. [微软 Ignite 2026 发布七款新 AI 模型](#item-tech-news-5) ⭐️ 7.0/10
6. [Google DeepMind 发布 Genie 4 世界模型](#item-tech-news-6) ⭐️ 7.0/10
7. [从 4004 到 486：x86 CPU 的历史回顾](#item-tech-news-7) ⭐️ 7.0/10
8. [Show HN：拆解旅行者 1 号到单个存储芯片的交互网站](#item-tech-news-8) ⭐️ 7.0/10
9. [curl 维护者质疑 AI 生成的 Rust 重写能否持续跟进修复](#item-tech-news-9) ⭐️ 7.0/10
10. [微信小微测试扩至 3000 万日活，采用 WeLM 模型](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [美联储纪要：多数官员预计需进一步加息，并警惕 AI 相关通胀风险](#item-finance-news-1) ⭐️ 8.0/10
2. [腾讯 2026 年三季度营收 2073 亿元，资本开支 814 亿元](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [谷歌发布 Gemini 4 Neon，主打编程与科研工作流](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 9.0/10

谷歌发布 Gemini 4 Neon，将其定位为面向复杂软件工程、知识工作和科研工作流的快速端到端模型，现已向开发者、企业以及 Google AI Pro/Ultra 订阅用户开放。该模型支持 100 万 token 上下文，API 价格为每百万输入 token 3 美元（缓存输入 0.15 美元），每百万输出 token 15 美元。谷歌公布的评测显示，它在 Artificial Analysis 编程智能体指数以 58.6 分居首、智能指数 xhigh 档以 61 分列总榜第三，Terminal-Bench 4.1 得分 65.2%，默认 high 档单任务成本较 Carbon 低 32%。

hackernews · yigitdemirag · 11月18日 21:34 · [社区讨论](https://news.ycombinator.com/item?id=50552424)

**「背景」** Gemini 4 Neon 是 Google Gemini 4 模型家族中的新成员，与已出现的 Carbon 等型号并列；在社区讨论中，Carbon 被描述为更偏向“长时程”任务。Google 用不同代号区分模型定位，而 Neon 这次主打复杂软件工程、知识工作与科研工作流的端到端执行，因此其命名和适用场景成为理解此次发布的重要背景。

**「影响」** 需要长上下文的编程智能体团队可直接用 100 万 token 上下文处理跨文件任务，但成本测算应区分缓存与未缓存输入；谷歌所称较 Carbon 低 32% 的单任务成本仅针对默认 high 档，不能外推到所有调用。

**「社区讨论」** 评论区最集中的抱怨是谷歌、Anthropic 和 OpenAI 的型号命名越来越难映射到具体使用场景；也有评论者指出，Neon 在总体智能评分上高于 Carbon，但 Carbon 仍被定位为长程模型，并在 CritPt 等研究级推理评测中得分更高。另有用户报告 OpenRouter 上 Neon 约为 127 token/s、快于 Carbon 的约 46 token/s，并对旗舰型号的服务速度感到意外。

**标签**: `#Gemini`, `#Google AI`, `#LLM release`, `#model naming`, `#AI industry`

---

<a id="item-tech-news-2"></a>
### [Wiz 报告 Nginx HTTP/2 未认证 RCE 漏洞](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

Wiz 报告 Nginx HTTP/2 存在未认证远程代码执行漏洞，涉及 CVE-2026-123633 和 CVE-2026-123007。当前条目未提供受影响版本、修复版本或复现细节。有评论称修复已先进入开源仓库，并认为实际利用需要 128Gb 的 HTTP/2 流量和特定 CPU 指令，因此风险主要集中在显式启用 HTTP/2 的部署。

hackernews · speedping · 11月18日 15:19 · [社区讨论](https://news.ycombinator.com/item?id=50547374)

**「背景」** 这两枚漏洞（CVE-2026-123633 与 CVE-2026-123007）出在 nginx 自身而非站点应用代码中；Wiz 称二者均评为 Critical，CVSS 4.0 评分为 9.2。Xint 的披露显示，CVE-2026-123007 影响 nginx 1.9.5 至 1.31.8 的所有官方版本，且截至 2026 年 11 月 10 日 master 分支仍含脆弱代码。暴露点在 nginx 的 HTTP/2 处理路径上，因此即使网站或 API 的应用代码本身安全，也不能消除服务器软件层面的风险。

**「影响与处置」** 对启用 HTTP/2 的 Nginx 运维者，在受影响版本和补丁信息明确前，可评估临时禁用 HTTP/2 作为缓解措施；评论指出该功能默认关闭，并引用 W3Techs 数据称约 12% 的服务器启用，暴露面因此集中在主动开启该协议的部署。

**「社区讨论」** 评论区的核心分歧在风险定级：一方批评修复提交提前一周出现在开源仓库却未发布临时公告，认为熟练攻击者可监控此类提交；另一方强调利用需要极高流量和特定 CPU 指令，且 HTTP/2 并非默认开启，称其实际风险有限。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root: New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>

</ul>
</details>

**标签**: `#nginx`, `#http/2`, `#security vulnerability`, `#remote code execution`, `#CVE`

---

<a id="item-tech-news-3"></a>
### [Xint 披露 5 个 nginx 漏洞链，可提权至主机 root](https://nginx2root.com/) ⭐️ 8.0/10

据 Telegram 帖子，Xint 公开了 NGINX2Root：5 个 nginx 漏洞与 1 个 Linux 内核缺陷可串联，从 nginx 访客权限提升到主机 root。其中 CVE-2026-123007 被描述为 HTTP/2 流控内存破坏，未认证即可在 worker 进程中执行命令。nginx 1.30.7 与 1.31.9 于 11 月 18 日修复 10 个 CVE；Rapid7 已发布 PoC，目前暂无在野利用报告。无法升级的运维者被建议关闭对外 HTTP/2。上述说法来自单一 Telegram 摘要，尚缺独立技术验证。

telegram · zaihuapd · 11月18日 16:21

**「背景」** 该漏洞链的核心 CVE-2026-123007 位于 nginx 的 HTTP/2 流控处理路径，属于内存破坏问题。相关缺陷代码自 2015 年 9 月 22 日发布的 nginx 1.9.5 起就存在，影响 1.9.5 至 1.31.8 的官方发布版本；截至 2026 年 11 月 10 日，开发分支仍含有该缺陷。

**「影响与处置」** 仍对外提供 HTTP/2 且无法升级到 nginx 1.30.7 或 1.31.9 的站点，需要把关闭对外 HTTP/2 作为缓解措施，但这会切断 HTTP/2 客户端流量；Rapid7 的 PoC 也使未修补实例面临更高的被验证和利用风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root : New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html">10-Year-Old NGINX HTTP/2 Flaw Lets Unauthenticated Attackers...</a></li>

</ul>
</details>

**标签**: `#nginx`, `#HTTP/2`, `#privilege escalation`, `#vulnerability disclosure`, `#CVE`

---

<a id="item-tech-news-4"></a>
### [Quad9 退出法国，DNS 不应成为反盗版执法点](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

技术评论文章《DNS resolvers are the wrong place to fight piracy》以 Quad9 退出法国为案例，论证用 DNS 解析器执行反盗版封锁既过度，也不符合互联网基础设施的职责。文章的核心判断是，DNS 层拦截会把内容执法的压力转嫁给解析服务，并带来言论审查和隐私风险。需要区分的是，这属于评论分析，现有材料并未提供法国法院命令的具体范围、生效时间或受影响用户规模。

hackernews · ritzaco · 11月18日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50545958)

**「背景」** DNS 解析器负责把域名转换为 IP 地址；一旦公共解析器按法院命令封禁域名，所有使用该解析器的用户都会受到影响。法国法院此前应 beIN Sports 请求，要求非营利解析器 Quad9 封锁被指控传播未经授权体育直播的域名；Quad9 随后选择于 2026 年 11 月 24 日停止为法国用户服务，而不是执行该封锁。

**「影响」** 对法国用户而言，Quad9 退出直接意味着少了一个公共 DNS 解析器选项；对依赖公共解析服务的组织，文章提示的风险是，若域名封锁成为常规执法手段，基础设施服务商将被迫承担内容审查职责并扩大屏蔽范围。

**「社区讨论」** HN 评论中，有人主张若不直接起诉盗版者，所谓反盗版措施只会变成压制言论的后门；也有人认为应靠更好的正版体验竞争，并质疑在商业 AI 使用版权内容未被追究的情况下，为何只针对个人。另有评论追问，问题到底出在法院越权解释，还是法国立法本身设定了过宽的封锁义务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad9 Is Leaving France: Why DNS Resolvers Are the Wrong ...</a></li>
<li><a href="https://cyberinsider.com/quad9-to-leave-france/">Quad9 to leave France after court orders piracy-related DNS ...</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet censorship`, `#piracy`, `#Quad9`, `#internet policy`

---

<a id="item-tech-news-5"></a>
### [微软 Ignite 2026 发布七款新 AI 模型](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

微软在 Ignite 2026 上宣布推出七款新 AI 模型，统一以可扩展的性价比为定位。现有材料未披露这些模型的具体名称、基准成绩、定价或可用时间，因此无法确认它们是否已经面向开发者开放，也无法核实其性能主张。

hackernews · gmays · 11月18日 16:08 · [社区讨论](https://news.ycombinator.com/item?id=50548021)

**「背景」** 微软此次在 Ignite 上主推的是面向具体任务的专用模型，包括代码、安全漏洞发现和图像生成，并以“比竞争对手更低的成本”作为核心卖点。按微软自己的说法，MAI Code 2 的代码质量达到 GPT-6.1 Sol 的 98%、价格约为后者的 40%，相对 Opus 5.5 则是 96% 的性能、5% 的价格。这些倍数均为厂商自述的对比，目前尚无独立复现或第三方基准验证。

**「对开发者的影响」** GitHub Copilot 中新增了 MAI Code 2 和 Code 2 Flash 这两个编码模型选项，主打更低的成本；微软称，在四项编码基准上，MAI Code 2 平均达到 GPT-6.1 Sol 的 98% 性能，成本为后者的 40%，并达到 Claude Opus 5.5 的 96% 性能，成本为后者的 5%。这些数据来自微软自报的基准和定价比较，团队在切换前应按自己的仓库和任务复测，并留意成本计算方式在脚注中的限制。

**「社区讨论」** 有评论者表示已在实际工作中测试 MAI Code 2，认为其表现不错，并将其与 Opus 或 Sol 相提并论；这属于个人使用体验。另有评论主张微软应开放部分模型权重以争取市场份额，也有人批评 Ignite 主题演讲缺乏技术深度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world class models at scalable... | Microsoft AI</a></li>
<li><a href="https://forklog.com/en/microsoft-unveils-ai-models-for-coding-and-cybersecurity/">Microsoft unveils AI models for coding and cybersecurity | ForkLog</a></li>
<li><a href="https://finance.yahoo.com/markets/article/microsoft-ignite-focuses-on-ai-models-for-specific-tasks-lowering-costs-for-enterprise-203433266.html">Microsoft &#x27;s AI pitch at Ignite : Cheaper models as business &#x27;token...</a></li>
<li><a href="https://felloai.com/mai-code-2/">MAI Code 2: Price, Benchmarks and Copilot Plans</a></li>
<li><a href="https://www.datastudios.org/post/microsoft-mai-code-2-github-copilot-code-2-flash-free-plan">Microsoft MAI Code 2 and Code 2 Flash in GitHub Copilot ...</a></li>

</ul>
</details>

**标签**: `#microsoft`, `#ai-models`, `#price-performance`, `#model-release`, `#coding-assistants`

---

<a id="item-tech-news-6"></a>
### [Google DeepMind 发布 Genie 4 世界模型](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind 宣布 Genie 4 已可用，称其为世界模型系统的新版本，但现有材料没有提供能力、基准测试或技术架构的具体信息。评论者引述的页面称该版本面向“符合条件的 Google AI Ultra 订阅者”；一名英国用户报告其工作区账号无法开通 Ultra，非工作区账号页面仍显示 Ultra 对应 Genie 3，因此实际地区与套餐可用范围尚不明确。

hackernews · leumon · 11月18日 18:49 · [社区讨论](https://news.ycombinator.com/item?id=50550415)

**「背景」** Genie 是 Google DeepMind 的交互式世界模型产品线，它生成的是可探索、可实时交互的场景，而非一段固定视频。DeepMind 将 Genie 4 描述为迄今最具交互性的版本，并称其新增原生实时音频生成；但公开材料未披露技术规格、基准测试结果或公开 API/定价信息。

**「对开发者与研究者的实际影响」** 根据 DeepMind 的模型卡，Genie 4 是首个能同时生成音乐、环境音与交互对话等多模态音频的世界生成系统，并接入了 Gemini 系列能力（如 Gemini Omni 用于锚定模拟）；官方还明确其生成的世界可用于训练 SIMA 这类智能体。这意味着构建交互场景或智能体训练环境时，需要把音频条件与画面生成一并纳入设计。可用性方面，有评论者引述公告称该功能面向「符合条件的 Google AI Ultra 订阅者」，并报告 Workspace 账号无法开通 Ultra、英国区账号的 Ultra 权益仍显示 Genie 3，因此打算使用的人应先确认自己账号类型与所在地区是否符合资格。

**「社区讨论」** 评论中最具体的讨论集中在付费与地区可用性：一名用户称工作区账号无法开通 AI Ultra，而普通账号页面仍把 Ultra 与 Genie 3 关联，因而无法确认 Genie 4 是否已在英国开放。另有评论者质疑这类世界模型的盈利路径，并有人认为“世界”应能在 360° 旋转时保持环境细节一致。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://worldattention.com/stories/google-deepmind-genie-4-world-model-research-preview-release-92e860e9a7">Google DeepMind Releases Genie 4 World Model... — WorldAttention</a></li>
<li><a href="https://kie.ai/blog/genie-4-world-model-architecture-capabilities">Genie 4 Deep Dive: What Actually Shipped</a></li>
<li><a href="https://deepmind.google/models/genie/">Genie 4 — Google DeepMind</a></li>
<li><a href="https://deepmind.google/models/genie/">Genie 4 — Google DeepMind</a></li>
<li><a href="https://deepmind.google/models/model-cards/genie-4/">Genie 4 - Model Card — Google DeepMind</a></li>

</ul>
</details>

**标签**: `#world models`, `#Google DeepMind`, `#generative AI`, `#AI research`, `#product availability`

---

<a id="item-tech-news-7"></a>
### [从 4004 到 486：x86 CPU 的历史回顾](https://pikuma.com/blog/history-of-x86-4004-to-486) ⭐️ 7.0/10

一篇技术回顾文章梳理了英特尔从 4004 到 486 的 CPU 演进，覆盖早期 x86 架构的形成过程。Hacker News 的评论者围绕小端序起源、8085 总线复用、8008 指令集设计归属以及 4004 与 8008 的关系提出了具体修正。该文属于历史分析，而非新产品发布或新事件；讨论还延伸到现代 PC 为何仍要兼容 1978 年芯片启动方式这一兼容性问题。

hackernews · ibobev · 11月18日 14:47 · [社区讨论](https://news.ycombinator.com/item?id=50546967)

**「背景」** 这篇回顾把 x86 的早期源流放到 Intel 4004 上：4004 的架构为后续 Intel 处理器奠定了基础，之后又出现了改进型号 4040，以及 8 位的 8008 和 8080。8008 于 1972 年 4 月推出，能寻址 16 KB 内存；其架构由 Computer Terminal Corporation 设计，由 Intel 实现并制造。这些早期芯片是理解后来从 8086 到 486 的演进的必要背景。

**「社区讨论」** 评论者给出了若干技术修正：小端序最初是为了 2200 的数据访问速度而非算术，8085 的地址/数据总线复用也见于 8008 和 8080，且 8008 指令集并非完全由英特尔设计，但经 Stan Mazor 等工程师增改；还有人强调 4004 与 8008 除人员重叠外并无直接关系。另有评论质疑英特尔和 AMD 为何仍让现代 PC 兼容 1978 年芯片的启动方式，并认为改变这一点主要会影响 BIOS 编写者。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Intel_4004">Intel 4004 - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Intel_8008">Intel 8008 - Wikipedia</a></li>

</ul>
</details>

**标签**: `#x86`, `#computer-history`, `#cpu-architecture`, `#intel`, `#hardware`

---

<a id="item-tech-news-8"></a>
### [Show HN：拆解旅行者 1 号到单个存储芯片的交互网站](https://rshekhar.com/voyager/) ⭐️ 7.0/10

开发者 raj-shekhar 在 Show HN 发布交互网站 rshekhar.com/voyager/，用户可在线查看两艘旅行者号的位置，并逐层拆解旅行者 1 号。网站能打开核电池（RTG）查看 24 个钚球，进入数据计算机直至单个存储芯片，查看 Golden Record 封套上的播放说明，以及“通过无线电修复旅行者 1 号”的故事。作者还提供了 4 分钟影片，并在评论中给出 RTG、存储芯片、单比特存储单元和 Golden Record 封套的直接链接。作者在帖中称旅行者 1 号当天达到距地球一光日，但这一说法未在给出的材料中独立核实。

hackernews · raj-shekhar · 11月18日 16:18 · [社区讨论](https://news.ycombinator.com/item?id=50548161)

**「背景」** 旅行者 1 号于 1977 年发射，是美国宇航局（NASA）迄今飞得最远的人造物体，也是第一个进入星际空间的人造探测器。据 2026 年 11 月的报道，它正逼近距地球一光日的距离，即无线电信号单程需要约 24 小时才能抵达；这一距离尺度正是该互动站点以“一光日”为切入点展开拆解的现实背景。

**「影响」** 对于计算机体系结构或航天硬件爱好者，这个站点把 RTG、数据计算机和单比特存储单元放在同一条可点击的浏览路径中，适合作为讲解航天器硬件的入口；若要引用具体结构或参数，仍需另行核对权威资料，因为帖中未说明资料来源与审校过程。

**「社区讨论」** 评论者称赞拆解展示，同时有人追问 CMOS 存储芯片为何会持续读错值，希望追到栅极、走线和封装互连的物理失效机制；另有人询问项目是否主要由 AI 生成、是否对照权威资料核对。还有评论者分享了自己制作的 Golden Record 致敬页面和原始音频解码器。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://science.nasa.gov/mission/voyager/voyager-1/">Voyager 1 : The Farthest Spacecraft — NASA Science</a></li>
<li><a href="https://www.downtoearth.org.in/science-technology/endless-voyage-nasas-voyager-1-nears-one-light-day-distance-from-earth-pushes-limits-of-endurance">NASA&#x27;s Voyager 1 Nears One - Light - Day Milestone, Defying Limits of...</a></li>
<li><a href="https://phys.org/news/2026-11-nasa-voyager-day-interstellar-space.html">NASA&#x27;s Voyager 1 closes in on a light - day in interstellar space for...</a></li>

</ul>
</details>

**标签**: `#interactive-visualization`, `#computer-hardware`, `#spacecraft`, `#embedded-systems`, `#education`

---

<a id="item-tech-news-9"></a>
### [curl 维护者质疑 AI 生成的 Rust 重写能否持续跟进修复](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) ⭐️ 7.0/10

curl 维护者 Daniel Stenberg 在 11 月 17 日的博文中称，在 AI 代理把 18.5 万行 C 代码转换为 34 万行 Rust 代码的约三周多时间里，实际的 curl 项目合并了 300 多个提交、修复了 200 多个缺陷，并修补了若干安全漏洞。他据此反问，这些生成的 Rust 重写版本能否跟上 curl 后续的修复节奏。上述行数、提交数和修复数均来自 Stenberg 的自述，未提供独立验证。

rss · Simon Willison · 11月18日 15:58

**「背景」** curl 是长期以 C 维护、被广泛嵌入各类软件的开源数据传输工具和库，其上游变更既包含功能修复，也包含安全漏洞修复。对这类项目做 Rust 重写，实质上会生成一个需要持续吸收上游提交和漏洞补丁的独立代码库；Daniel Stenberg 的对比正是围绕这一维护负担展开。

**「影响」** 对考虑采用这些 AI 生成 Rust 重写版本的开发者来说，它们不包含同期 curl 已修复的 200 多个缺陷和若干安全漏洞；若要采用，需要评估与上游持续同步及补丁维护的成本。

**标签**: `#AI coding agents`, `#curl`, `#Rust`, `#open source maintenance`, `#security`

---

<a id="item-tech-news-10"></a>
### [微信小微测试扩至 3000 万日活，采用 WeLM 模型](https://mp.weixin.qq.com/s/r3NthxJZQJgztyLADwNV4A) ⭐️ 7.0/10

腾讯在 2026 年第三季度财报中称，微信小微的测试范围已扩大，日活跃用户达到 3000 万，并逐步接入微信聊天、朋友圈、公众号和视频号等场景。小微使用针对成本效率优化的定制 WeLM 模型，腾讯称其推理成本较低且持续下降，未来部分推理任务预计会放到用户设备端运行。

telegram · zaihuapd · 11月18日 11:35

**「背景」** 微信小微是内嵌在微信内的 AI 助手，可从聊天、朋友圈、公众号和视频号等入口直接调用，因此其日活跃规模会直接推高服务端推理成本。腾讯为该助手定制 WeLM 模型时把成本效率作为主要优化目标，而计划将部分推理迁移到用户设备端，正是降低单次调用成本、缓解服务端算力压力的常见路径。

**「影响」** 测试扩大后，更多微信用户可在上述入口直接使用小微；但腾讯未披露具体开放条件、测试地区及端侧推理时间表，实际可用范围仍取决于测试推进。

**标签**: `#WeChat`, `#Tencent`, `#AI assistant`, `#WeLM`, `#on-device AI`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美联储纪要：多数官员预计需进一步加息，并警惕 AI 相关通胀风险](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

美联储 10 月会议纪要显示，几乎所有与会者认为需要进一步加息才能使通胀及时回到 2%目标，并警告 AI 相关需求是“实质性通胀风险”来源、其复杂融资结构可能放大损失。会议以 10 比 2 决定将联邦基金利率目标区间维持在 3.75%-4%，两位反对者主张立即加息 25 个基点。

rss · CNBC Finance · 11月18日 19:41

**「背景」** 会议以来公布的数据显示，10 月 CPI 环比上涨 0.4%、核心 CPI 上涨 0.3%，均比预期高 0.1 个百分点，通胀仍远高于 2%目标。

**「市场反应」** 市场已完全计入 12 月 8-9 日会议加息 25 个基点，利率期货交易员还认为 2027 年再加息两次的可能性较大。

**标签**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#artificial intelligence`, `#financial stability`

---

<a id="item-finance-news-2"></a>
### [腾讯 2026 年三季度营收 2073 亿元，资本开支 814 亿元](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

腾讯公布 2026 年第三季度财报，营收 2073 亿元、同比增长 8%，低于市场预期；归母净利润 636 亿元、同比增长 0.8%；当季资本开支 814.33 亿元，远超市场预估的 554 亿元，自由现金流为负 691 亿元。腾讯还称，WorkBuddy 日均 Token 用量超过 100 万亿，为国内大语言模型 AI 产品最高。

telegram · zaihuapd · 11月18日 09:20

**「背景」** 腾讯在财报中将单季自由现金流为负归因于：当季经营活动产生的现金净额仅 26 亿元，却要支付 651 亿元资本开支、媒体开支等款项；而 WorkBuddy 是腾讯云代码助手推出的 AI Agent 办公工具，可自主规划并交付多模态复杂任务。

**「影响」** 对投资者而言，资本开支远超预期并伴随单季自由现金流为负，意味着可用于回购、分红或再投资的现金减少，利润率也受到挤压（彭博）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611183934001422.html">腾 讯 控股 第 三 季 度 营 收 2073 亿 元 同比增长8% _ 东方 财 富网</a></li>
<li><a href="https://www.workbuddy.cn/">WorkBuddy - AI Agent 办公新范式</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-18/tencent-s-sales-miss-estimates-in-setback-for-founder-s-ai-push">Tencent ’s Profit Squeeze Exposes China’s AI Spending... - Bloomberg</a></li>

</ul>
</details>

**标签**: `#Tencent`, `#earnings`, `#AI capex`, `#free cash flow`, `#token usage`

---