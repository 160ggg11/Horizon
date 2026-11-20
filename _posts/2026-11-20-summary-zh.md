---
layout: default
title: "Horizon Summary: 2026-11-20 (ZH)"
date: 2026-11-20
lang: zh
---

> 从 33 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [PostgreSQL 19 发布：用 WAIT FOR LSN 保证备库读一致性](#item-tech-news-1) ⭐️ 9.0/10
2. [Anthropic 登陆纳斯达克，估值与 AI 前景接受公开市场检验](#item-tech-news-2) ⭐️ 8.0/10
3. [英国法庭迫使政府承认苹果加密命令](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenJDK 被报 java4shell 漏洞，Oracle 接管 PR](#item-tech-news-4) ⭐️ 8.0/10
5. [Gemini 在 Mac 上可代用户操作并随时暂停](#item-tech-news-5) ⭐️ 8.0/10
6. [PHP 流包装器大写 S 致 TLS 静默失效](#item-tech-news-6) ⭐️ 8.0/10
7. [OpenSSL EVP\_EncodeBlock\(\) 缓冲区溢出问题标注 CVSS 9.8](#item-tech-news-7) ⭐️ 7.0/10
8. [Anthropic 称 Claude 解决两个黑洞物理开放问题](#item-tech-news-8) ⭐️ 7.0/10
9. [美众院文件显示近半年批准近 88 万颗 AI 芯片对华出口](#item-tech-news-9) ⭐️ 7.0/10
10. [Meta AI 助手 Muse 被指串号泄露私密数据](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [据报 Anthropic 纳斯达克上市首日开盘涨 34%，市值约 1.5 万亿美元](#item-finance-news-1) ⭐️ 9.0/10
2. [Anthropic 上市后 AI 投资疑虑拖累亚洲股市](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [PostgreSQL 19 发布：用 WAIT FOR LSN 保证备库读一致性](https://www.postgresql.org/docs/release/19.0/) ⭐️ 9.0/10

PostgreSQL 19 已发布，发布时间比通常的 9 月惯例晚约两个月；来源称主要原因是团队需要处理大量由 AI 报告的漏洞问题。该版本为把读请求发送到备库的应用新增 \`WAIT FOR LSN\`：应用可先记录主库当前的 WAL 插入 LSN，再让备库等待回放到该 LSN 后执行查询，从而读到刚刚在主库写入的数据。等待可附带可选超时，例如 \`WAIT FOR LSN &\#x27;0/0306EE20&\#x27; WITH \(TIMEOUT &\#x27;0.1s&\#x27;\)\`；如果备库未在时限内追上，则会报错。

hackernews · linzhangrun · 11月20日 03:45 · [社区讨论](https://news.ycombinator.com/item?id=50569890)

**「背景」** PostgreSQL 通常每年 9 月发布新大版本，此次发布时间比惯例晚约两个月。在流复制中，备库回放 WAL 可能落后于主库，因此刚写入后立刻从备库读取可能得到旧数据；MediaWiki 曾针对 MySQL 复制手工实现过基于日志位点的同类等待机制。

**「影响」** 对把读流量放到备库的开发者来说，现在可以由应用按请求控制读一致性：保存主库 LSN，在备库执行 \`WAIT FOR LSN\` 后再查询。使用超时选项时，应用需要处理等待失败的错误，而不应假定备库一定已经追上。

**「社区讨论」** 有评论者称这是自己见过 bug 最少的 Postgres \`.0\` 版本，但表示过去通常等到 \`.1\` 或 \`.2\` 才升级，并犹豫这次是否还应继续等待；这属于个人经验判断，并非项目方的稳定性声明。

**标签**: `#PostgreSQL`, `#databases`, `#open source`, `#software release`, `#SQL`

---

<a id="item-tech-news-2"></a>
### [Anthropic 登陆纳斯达克，估值与 AI 前景接受公开市场检验](https://www.reuters.com/business/finance/anthropics-historic-debut-put-ais-promise-peril-wall-st-test-2026-11-19/) ⭐️ 8.0/10

据路透社 2026 年 11 月 19 日报道，Anthropic 在纳斯达克完成上市，报道将其定位为对 AI 行业“承诺与风险”的一次华尔街检验。所给材料仅有标题与评论，未披露发行价、募资规模、股票代码或首日收盘价，因此具体交易数据无法核实。评论区有人称其市值自首笔交易后持续走低、降至约 1.26 万亿美元，并称数周前市场期望还在 2 万亿美元以上；这些数字来自 Hacker News 评论，未经独立确认。另有评论引用 Yahoo Finance 的说法称，Anthropic 上市后的首个半小时是 2008 年以来大型 IPO 最差的开局。

hackernews · wslh · 11月19日 17:02 · [社区讨论](https://news.ycombinator.com/item?id=50562754)

**「背景」** Anthropic 是 Claude 系列大模型的开发商，此前长期作为非上市公司运营，其估值主要在私募市场形成，因此这次登陆纳斯达克是其首次进入公开市场定价。在此之前，史上最大规模 IPO 的纪录由 SpaceX 保持——该公司在今年 6 月上市时募资约 750 亿美元；Anthropic 以每股 83 美元定价、募资 81.3 亿美元，刷新了这一纪录。

**「影响」** 这次上市为 AI 实验室的估值提供了公开市场参照：有评论者据此推断，若 Anthropic 市值确实落到约 1.26 万亿美元、低于 OpenAI 在私募市场寻求的估值水平，那么 OpenAI 以更高估值融资、并用股权激励留住员工的难度会随之上升。该推论建立在评论者引用的未核实数字之上，属于对后续影响的判断，而非已发生的结果。

**「社区讨论」** 讨论集中在职业前景与估值两方面：有自称软件工程师的用户认为“SWE 的好日子基本结束”，一位从业 50 年的程序员回忆早年赴新加坡学习 C 语言的经历，称这或许是这种谋生方式的黄昏，但对如何建议新人表示难以给出明确路径。另一位评论者则认为该估值“相当疯狂”、难以维持，并把 Anthropic 的首日表现与 OpenAI 的私募估值联系起来解读；以上均为个人观点，不构成对估值或就业趋势的证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.euronews.com/2026/11/19/anthropic-shares-open-34-above-ipo-price-in-nasdaq-debut-after-record-listing">Anthropic shares open 34% above IPO price in Nasdaq debut</a></li>
<li><a href="https://www.aljazeera.com/economy/2026/11/19/anthropic-raises-81-3bn-in-biggest-ipo-of-all-time">Anthropic raises $81.3bn in biggest IPO of all time | Al Jazeera</a></li>
<li><a href="https://admiralmarkets.com/analytics/traders-blog/anthropic-stock-ant-first-day-trading">Anthropic Stock (ANT): First Day of Trading After $83 IPO</a></li>

</ul>
</details>

**标签**: `#AI industry`, `#Anthropic`, `#IPO`, `#software engineering careers`, `#AI valuations`

---

<a id="item-tech-news-3"></a>
### [英国法庭迫使政府承认苹果加密命令](https://macanorak.com/uk-government-forced-to-admit-it-issued-apple-a-secret-encryption-order/) ⭐️ 8.0/10

英国调查权力法庭（IPT）裁定苹果胜诉，内政部不能再保密其向苹果发出的技术能力通知（TCN），案件大部分将公开审理。内政部随后确认曾发出该通知，称目的仅为将罪犯绳之以法；法庭认定其国家安全理由“不切实际”。通知的具体内容目前仍然保密，外界尚无法核实它要求苹果对 iPhone 加密数据提供何种访问能力。

hackernews · Terretta · 11月19日 16:21 · [社区讨论](https://news.ycombinator.com/item?id=50562113)

**「背景」** 技术能力通知（TCN）是英国政府可发出的保密命令，用于要求企业提供特定的技术协助；本案中它被用于要求苹果开放 iPhone 加密数据访问。英国调查权力法庭负责审理此类命令的合法性，而此前命令的存在与内容都处于保密状态；现在法庭裁定内政部不能再保密，案件大部分将公开审理，但通知内容仍未解密。

**「影响」** 这一裁决使英国政府更难用保密程序阻止外界审视针对平台商的 TCN；但对依赖 iPhone 加密的英国用户和组织而言，目前只能确认存在过一项秘密访问要求，通知内容未公开，仍无法判断哪些数据或功能实际受影响。

**「社区讨论」** 评论中，natch 认为苹果的安全承诺已从“任何人（包括苹果）都无法访问”退到“苹果无法访问”，并称设备上的密钥可能只是保护另一把数据密钥的 KEK；fweimer 给出判决链接，指出媒体是通过保密安全简报而非泄密得知 TCN，且通知内容仍保密。另有评论者质疑英国为何在西方国家标准下仍如此公开强硬地推进大规模监控，也有人追问此案与当年苹果对抗 FBI 的争议相比为何重要。

**标签**: `#encryption`, `#privacy`, `#uk-government`, `#apple`, `#surveillance`

---

<a id="item-tech-news-4"></a>
### [OpenJDK 被报 java4shell 漏洞，Oracle 接管 PR](https://github.com/openjdk/jdk/pull/32781) ⭐️ 8.0/10

一个被社区称为 java4shell 的 OpenJDK 漏洞报告正在 PR \#32781 中讨论；据 PR 作者称，Oracle 已接管该变更，但公开材料尚未确认受影响版本、严重级别或利用条件。该作者在关联的 Adoptium 问题中表示，Oracle 于 10 月 1 日要求其在获得批准前不要推进 PR，10 月 28 日又称变更已由 Oracle 接管、无需其继续操作。

hackernews · notmine1337 · 11月19日 11:47 · [社区讨论](https://news.ycombinator.com/item?id=50558906)

**「背景」** Java4Shell 对应 CVE-2026-114938，是 OpenJDK Base64 解码器中的一处堆溢出，影响 Java 17.0.6 及之后在特定 x86-64 系统上运行的版本；据安全厂商博客，Oracle 与 OpenJDK 漏洞组已于 2026 年 11 月 17 日发布修复版本，并提供在无法立即升级时关闭相关优化作为临时缓解。按社区评论提供的线索，该缺陷最初以 SIGSEGV 形式在 6 月被上报，9 月被定位到 Base64 相关代码，随后才有本 PR 的讨论；评论者还称 Oracle 曾要求 PR 作者在获得批准前暂停推进，并于 10 月底接管该改动。

**「升级与缓解」** 运行 Java 17.0.6 及以上版本、且部署在受影响 x86-64 平台上的用户，应升级到各厂商已发布的修复版本（Oracle 与 OpenJDK 漏洞组于 2026 年 11 月 17 日发布修复）。若无法立即升级，可临时关闭相关优化作为缓解，但暴露与否还取决于是否满足特定使用条件，因此需要先按厂商公告核对自身环境。

**「社区讨论」** 评论区的争论集中在披露先后与独立性：一位评论者称自己在正式披露前用离线运行的模糊测试工具独立发现并拼出完整 RCE 链，因而怀疑该问题可能已进入模型训练数据；另一位评论者则追问协助研究者的 LLM 是否只是读到了早先的漏洞报告。也有评论指出更早的 SIGSEGV 报告可追溯到 6 月、9 月已缩小到 Base64 相关代码，但这些都属评论者说法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.dynatrace.com/news/blog/java4shell-cve-2026-114938-which-java-runtimes-are-affected-and-how-to-fix-them/">Java4Shell (CVE-2026-114938): Affected Java Versions &amp; fixes</a></li>
<li><a href="https://pentest-tools.com/blog/java4shell-cve-2026-114938">Java4Shell (CVE-2026-114938): affected versions and fixes</a></li>
<li><a href="https://cybersecuritynews.com/java4shell/">Critical Java4Shell Flaw Lets Hackers Execute Code Without ...</a></li>
<li><a href="https://pentest-tools.com/blog/java4shell-cve-2026-114938">Java4Shell (CVE-2026-114938): affected versions and fixes</a></li>
<li><a href="https://cycode.com/blog/java4shell-cve-2026-114938/">Java4Shell (CVE-2026-114938): Affected Versions, How to Check ...</a></li>
<li><a href="https://www.dynatrace.com/news/blog/java4shell-cve-2026-114938-which-java-runtimes-are-affected-and-how-to-fix-them/">Java4Shell (CVE-2026-114938): Affected Java Versions &amp; fixes</a></li>

</ul>
</details>

**标签**: `#Java`, `#OpenJDK`, `#security vulnerability`, `#RCE`, `#responsible disclosure`

---

<a id="item-tech-news-5"></a>
### [Gemini 在 Mac 上可代用户操作并随时暂停](https://www.bloomberg.com/news/articles/2026-11-19/google-s-gemini-can-now-control-mac-devices-on-users-behalf) ⭐️ 8.0/10

Google Gemini 新增“电脑操作”功能，可在 Mac 上代替用户点击、输入、浏览菜单和填写表单。该功能面向美国地区使用 Mac 版 Gemini、并订阅 Google AI Plus、Pro 或 Ultra 的用户开放。用户可让 Gemini 在独立后台窗口运行，同时继续使用主屏幕和光标；还可限制其可访问的应用、实时查看操作、随时暂停，并在关键操作前进行审批。目前提供的说明未包含技术细节或独立评测结果。

telegram · zaihuapd · 11月20日 02:51

**「背景」** 桌面自动化代理的关键，是让模型直接读取屏幕并模拟点击、输入、浏览菜单等图形界面操作，而不是只通过应用接口执行任务；这也使权限边界和人工监督成为能否实际使用的核心问题。Gemini 此次把这类能力放入独立后台窗口，并配套应用访问限制、实时查看、暂停和关键操作前审批，正是围绕这一前提设计控制机制。

**标签**: `#AI agents`, `#Google Gemini`, `#desktop automation`, `#macOS`, `#human-in-the-loop`

---

<a id="item-tech-news-6"></a>
### [PHP 流包装器大写 S 致 TLS 静默失效](https://x.com/ljachowicz/status/2123477025268924514) ⭐️ 8.0/10

PHP 的 HTTP/FTP 流包装器在识别 URL scheme 时忽略大小写，但只有第五个字符为小写“s”时才启用 TLS；因此“HTTPS://”“httpS://”“FTPS://”会被当作明文 HTTP/FTP 发出。转发的安全帖称，这会使 Basic 认证、令牌、Cookie、POST 请求体和 FTP 登录信息以明文传输，经第三方重定向到此类地址时同样受影响，并给出 CVE-2026-128064（GHSA-f6gg-rchx-xw8j）、CVSS 4.0 评分 8.2。修复版本为 PHP 8.2.36、8.3.37、8.4.28、8.5.13 和 8.6.0；8.1 及更早版本已 EOL，不会获得修复，需自行将 URL scheme 统一转为小写。

telegram · zaihuapd · 11月20日 03:04

**「背景」** PHP 的 HTTP/FTP 流包装器在识别 URL scheme 时不区分大小写，但只有在固定位置出现小写“s”时才启用 TLS；因此 HTTPS://、httpS:// 和 FTPS:// 会被当作明文 HTTP/FTP 处理，而不是建立加密连接。问题出在包装器的 scheme 解析逻辑，受影响的也包括被第三方重定向到这类地址的请求。

**「影响」** 仍在使用 PHP 8.1 及更早版本的组织无法通过升级修补，必须在应用层把 scheme 规范化为小写，否则包含凭据的请求可能被静默以明文发送；可升级者应尽快安装上述补丁版本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://everycve.com/CVE-2026-128064">CVE - 2026 - 128064 : Mixed-case HTTPS and FTPS URLs can expose...</a></li>

</ul>
</details>

**标签**: `#PHP`, `#security vulnerability`, `#TLS`, `#CVE`, `#open source`

---

<a id="item-tech-news-7"></a>
### [OpenSSL EVP\_EncodeBlock\(\) 缓冲区溢出问题标注 CVSS 9.8](https://github.com/openssl/openssl/pull/33652) ⭐️ 7.0/10

OpenSSL 的 base64 编码函数 EVP\_EncodeBlock\(\) 被报告存在缓冲区溢出，编号为 CVE-2026-121481，条目标注的 CVSS 评分为 9.8。现有材料没有说明受影响版本范围、修复是否发布或官方利用条件；有评论者根据快速阅读称，输入超过约 1.5GB 时该函数会出错，并指出调用方需自行计算输出缓冲区大小、函数又不接收输出长度，因而无法校验。对使用该函数处理大块数据的应用，实际风险取决于不可信输入能否到达该调用点，而不能仅由评分判断。

hackernews · JacobHenner · 11月20日 02:01 · [社区讨论](https://news.ycombinator.com/item?id=50569226)

**「背景」** EVP\_EncodeBlock\(\) 是 OpenSSL 的 base64 编码接口：调用方需要按编码后约 4/3 的扩张自行计算输出缓冲区大小，却不把输出缓冲区长度传给函数，因此实现无法在写入前校验容量。根据漏洞库信息，CVE-2026-121481 影响 OpenSSL 4.1.0（4.1.1 修复）以及 4.0.0 至 4.0.3（4.0.4 修复），触发条件是输入过长，导致其编码后大小无法用 int 表示。

**「影响：超大输入与绑定层暴露」** 影响主要落在把 EVP\_EncodeBlock\(\) 直接暴露给超大外部输入的应用和语言绑定上：有评论分析指出，输入超过约 1.5 GB 才会触发问题，因此带长度上限的协议通常不受影响；但 HsOpenSSL 等绑定会直接调用该函数，相关封装也需要审计。运维和开发者应在确认所用 OpenSSL 版本已包含该 PR 的修复前，限制单次编码的输入大小，并检查是否存在一次性读入不受信大对象的调用路径。

**「社区讨论」** 评论者对 CVSS 9.8 是否合理存在分歧：userbinator 认为评分被夸大，实际可利用性取决于不可信输入能否到达 EVP\_EncodeBlock\(\)，并非所有使用场景都会受影响；amluto 则把问题部分归因于 API 设计，称调用方必须自行计算输出缓冲区长度，而函数拿不到该长度、无法校验。另有评论者追问是否存在可演示的利用，讨论中没有给出明确结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cve.now/CVE-2026-121481">CVE-2026-121481: OpenSSL overflow in EVP_EncodeBlock ()</a></li>
<li><a href="https://hackage.haskell.org/package/HsOpenSSL-0.11.4/docs/src/OpenSSL-EVP-Base64.html">OpenSSL / EVP / Base 64 .hs</a></li>

</ul>
</details>

**标签**: `#OpenSSL`, `#CVE-2026-121481`, `#buffer overflow`, `#security vulnerability`, `#base64 encoding`

---

<a id="item-tech-news-8"></a>
### [Anthropic 称 Claude 解决两个黑洞物理开放问题](https://www.anthropic.com/research/claude-black-hole-physics) ⭐️ 7.0/10

Anthropic 在一篇 AI 辅助科学发现研究帖中声称，Claude 解决了黑洞物理中的两个开放问题；现有信息主要来自厂商声明和社区转述，尚无独立验证或同行评审结论。Hacker News 评论者认为，第一项结果更像一项复杂且易出错的计算，第二项结果则更有分量：Claude 给出了与给定中心电荷相容的黑洞质量上限，并据此排除质量超过该上限的量子引力理论。上述技术细节来自评论者对论文的解读，而非已确认的独立测量。

hackernews · cybermango · 11月19日 17:30 · [社区讨论](https://news.ycombinator.com/item?id=50563148)

**「背景：模 bootstrap 与黑洞质量上限」** 在二维共形场论中，模不变性与幺正性会对能谱施加自洽约束，物理学家据此通过“bootstrap”方法推导出形如 M₁ ≤ c/Λ 的不等式，其中 M₁ 是最轻态（黑洞）的质量上限，Λ 与中心荷 c 相关：上限越低，意味着 Λ 越大。这类界限不依赖显式构造，只要求理论本身自洽，因此常被用来判断某个理论能否作为量子引力理论成立。Anthropic 的研究帖称，相关结果此前只覆盖这一方法中最简单、忽略黑洞自旋的版本。

**「对科研读者的实际影响」** 对关注 AI 用于科学的研究者来说，这条公告目前仍只是厂商声明而非可独立复核的结论：评论中的物理学家指出，理论物理领域的“开放问题”数量近乎无限且分量差别极大，而他自己尚未细读论文、结果也不在其直接研究范围内，因此读者不宜据此判断 Claude 已具备可验证的科研能力。另一条评论指出，Hexagon 条目和 PDF 除 Claude/Anthropic 外没有任何署名，这意味着任何想引用或跟进这项工作的人，都需要先自行核对作者身份与人类贡献的具体归属。

**「社区讨论」** 一位自称物理学家的评论者提醒，理论物理中的“开放问题”数量极多、重要性差异很大，解决其中一个并不必然意味着整个领域会跟进；另一位评论者则指出，相关论文和 Hexagon 条目除 Claude/Anthropic 外几乎没有其他署名。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/research/claude-black-hole-physics">Claude Fable 5.2 solves two open problems in the physics of black ...</a></li>

</ul>
</details>

**标签**: `#AI for science`, `#physics`, `#Claude`, `#LLM reasoning`, `#research claims`

---

<a id="item-tech-news-9"></a>
### [美众院文件显示近半年批准近 88 万颗 AI 芯片对华出口](https://foreignaffairs.house.gov/news/press-releases/chairman-brian-mast-exercises-legislative-authority-to-publicly-release-ai-chip-license-information-for-china) ⭐️ 7.0/10

美国众议院外交事务委员会公布的文件显示，2025 年 12 月至 2026 年 5 月，美国批准英伟达和 AMD 向中国出口 879,868 颗 AI 芯片，涉及 H200 和 MI325X，企业申请总量为 344.4 万颗。获批对象包括腾讯、字节跳动（各 15 万颗），阿里巴巴、快手、滴滴（各 7.5 万颗），以及米哈游、百度、京东等。文件还显示，阿里、腾讯、百度、比亚迪被列入美方所谓中国军方关联企业名单，引发国会对出口审查的质疑；截至 5 月 11 日，21 份批准许可均显示尚未发货，因此获批数量不等于实际交付。

telegram · zaihuapd · 11月20日 04:25

**「背景」** 美国对华出口先进 AI 芯片长期受许可证管理，英伟达、AMD 等企业向中国客户销售特定型号需获得美方批准。此次众议院外交事务委员会公开的许可信息，把 2025 年 12 月至 2026 年 5 月的审批规模，以及获批企业中涉及所谓中国军方关联名单的情况，置于国会审查焦点。

**「影响」** 对相关中国买家而言，获批许可尚未转化为实际供货：截至 5 月 11 日，文件所列 21 份批准许可均未发货，实际可获得的芯片仍取决于后续出货和合规审查。国会围绕军方关联名单的质疑，也可能使相关企业的出口许可面临更严格审视。

**标签**: `#AI chips`, `#export controls`, `#US-China tech`, `#NVIDIA/AMD`, `#semiconductor policy`

---

<a id="item-tech-news-10"></a>
### [Meta AI 助手 Muse 被指串号泄露私密数据](https://techcrunch.com/2026/11/19/metas-ai-agent-muse-is-mixing-up-conversations-and-exposing-private-data-report-says/) ⭐️ 7.0/10

据路透社援引 Meta 内部帖子报道，Meta 的 AI 助手 Muse 会在不同账户之间串对话，导致员工看到不属于自己的私密信息。报道举例称，一名员工在天气对话中看到插入的 Capital One 余额 2722.58 美元和 Charles Schwab 余额 5899.57 美元；另一名员工称，Muse 在其个人手机上提醒她回复姐姐在 Signal 上的消息，而她并未授权它访问其他应用。这些说法来自内部帖子，尚未看到 Meta 的公开说明或独立验证，具体影响范围和原因仍不明确。

telegram · zaihuapd · 11月20日 05:10

**「背景」** Muse 是 Meta 主推的 AI 助手，Meta 曾宣称它“从底层为隐私和安全而设计”；但 Ars Technica 2026 年 9 月报道称，这个权限极高的助手存在严重的 0-day 漏洞。此次员工反映的跨账户串话，进一步引发了对 Muse 在拥有广泛账户与应用访问权限时如何隔离用户数据的担忧。

**「影响与注意事项」** 报道中的案例把风险集中在账户间对话隔离和跨应用授权上：员工未授权的 Signal 消息和他人银行余额出现在自己的会话里，表明用户授权设置未必能阻止数据串入。在 Meta 说明原因并完成修复前，受影响用户应把 Muse 会话视为可能被其他账户看到，并避免在其中处理金融信息或私人消息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arstechnica.com/security/2026/09/muse-metas-extraordinarily-privileged-ai-assistant-has-a-serious-0-day/">Muse , Meta &#x27;s extraordinarily privileged AI assistant ... - Ars Technica</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#privacy`, `#Meta`, `#data leakage`, `#trust and safety`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [据报 Anthropic 纳斯达克上市首日开盘涨 34%，市值约 1.5 万亿美元](https://www.cls.cn/detail/2539480) ⭐️ 9.0/10

据财联社报道，Anthropic 于 11 月 19 日登陆纳斯达克，发行价 83 美元/股，开盘报 111.5 美元，较发行价上涨 34%，按开盘价计算市值约 1.5 万亿美元。本次 IPO 发行总额约 813.4 亿美元，另同步私募配售 260 亿美元，合计约 1073.4 亿美元。

telegram · zaihuapd · 11月19日 16:56

**「背景」** 据雅虎财经报道，Anthropic 的发行价高于此前每股 70 至 78 美元的预期区间；按计入期权等股份的完全稀释口径，估值约 1.5 万亿美元，仅按已发行股份计算约 1.1 万亿美元，并超过 SpaceX 成为史上最大规模 IPO。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/ai/articles/anthropic-announces-price-83-per-234507433.html?fr=sycsrp_catchall">Anthropic announces price of $83 per share for IPO Anthropic valued at $1.5 trillion as IPO raises record $81 ... Anthropic hits Nasdaq exchanges at $111, 33% above IPO price Anthropic begins trading on Nasdaq, tops SpaceX for biggest ... Anthropic to begin trading after pricing its stock at $83 per ...</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#IPO`, `#Nasdaq`, `#AI financing`, `#private placement`

---

<a id="item-finance-news-2"></a>
### [Anthropic 上市后 AI 投资疑虑拖累亚洲股市](https://www.bloomberg.com/news/articles/2026-11-19/stock-market-today-dow-s-p-live-updates) ⭐️ 7.0/10

Anthropic IPO 后，其股价盘后跌逾 5%、跌破 92 美元，市场对 AI 巨额投入能否带来相应回报的疑虑升温，亚洲股市普遍下跌。MSCI 亚太指数跌 1.7%，连续第七个交易日走低；东京电子和 SK 海力士分别跌 7.19% 和 6%。

telegram · zaihuapd · 11月20日 01:58

**「背景」** Anthropic 于 11 月 19 日在纳斯达克上市，以每股 83 美元募资 813 亿美元、创史上最大 IPO 纪录，开盘报 111.50 美元，估值一度接近 2 万亿美元，此次上市被视作检验 AI 高估值的关键测试。

**「影响」** 日本和韩国半导体股及软银等 AI 相关投资者直接承压；软银已向 OpenAI 累计投资 646 亿美元，其股价本月下跌 31%。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.aljazeera.com/economy/2026/11/19/anthropic-raises-81-3bn-in-biggest-ipo-of-all-time">Anthropic raises $81.3bn in biggest IPO of all time | Al Jazeera</a></li>
<li><a href="https://www.euronews.com/2026/11/19/anthropic-shares-open-34-above-ipo-price-in-nasdaq-debut-after-record-listing">Anthropic shares open 34% above IPO price in Nasdaq... | Euronews</a></li>

</ul>
</details>

**标签**: `#Asian markets`, `#AI investment`, `#semiconductors`, `#Anthropic IPO`, `#market selloff`

---