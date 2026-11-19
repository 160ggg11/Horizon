---
layout: default
title: "Horizon Summary: 2026-11-19 (EN)"
date: 2026-11-19
lang: en
---

> From 43 items, 12 important content pieces were selected

---

**Technology News**
1. [Google releases Gemini 4 Neon with 1M-token context](#item-tech-news-1) ⭐️ 9.0/10
2. [Wiz reports unauthenticated RCE flaws in Nginx HTTP/2](#item-tech-news-2) ⭐️ 8.0/10
3. [Xint discloses nginx-to-root chain of five flaws](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9’s France exit shows DNS blocking is the wrong anti-piracy tool](#item-tech-news-4) ⭐️ 7.0/10
5. [Microsoft announces seven AI models pitched at scalable price-performance](#item-tech-news-5) ⭐️ 7.0/10
6. [Google DeepMind announces Genie 4 for eligible AI Ultra subscribers](#item-tech-news-6) ⭐️ 7.0/10
7. [pikuma.com Technical Retrospective: Intel x86 From 4004 to 486](#item-tech-news-7) ⭐️ 7.0/10
8. [Show HN: Interactive Voyager 1 model goes down to a single memory chip](#item-tech-news-8) ⭐️ 7.0/10
9. [curl Maintainer Says AI Rust Rewrites Lag 200+ Bugfixes](#item-tech-news-9) ⭐️ 7.0/10
10. [WeChat Xiaowei AI assistant test expands to 30 million daily users](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [Fed October minutes signal further rate hikes and AI inflation risk](#item-finance-news-1) ⭐️ 8.0/10
2. [Tencent Q3 2026: revenue misses estimates as capex jumps](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google releases Gemini 4 Neon with 1M-token context](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 9.0/10

Google has released Gemini 4 Neon, positioned for complex software engineering, knowledge work, and research workflows, and says it is available to developers, enterprises, and Google AI Pro/Ultra subscribers. Google lists pricing at $3 per million input tokens, $0.15 per million cached input tokens, and $15 per million output tokens, with a 1 million-token context window. Google-reported results put Neon first on Artificial Analysis&\#x27;s coding-agent index at 58.6, third on its intelligence index at 61 in the xhigh setting, and at 65.2% on Terminal-Bench 4.1; Google also claims a 32% lower per-task cost than Carbon in the default high setting.

hackernews · yigitdemirag · Nov 18, 21:34 · [Discussion](https://news.ycombinator.com/item?id=50552424)

**「Background」** Google places Gemini 4 Neon within its Gemini 4 lineup alongside Carbon, which the source uses as the cost baseline for Neon&\#x27;s default high setting. Google also cites Artificial Analysis&\#x27; coding-agent and intelligence indices as the external benchmarks for its performance claims.

**「Impact」** The practical opening is for teams that need long-context coding or research agents: Neon&\#x27;s 1M-token window and advertised lower per-task cost than Carbon give them a new option, while one commenter notes that Carbon remains positioned for long-horizon work and scores higher on CritPt research-reasoning evaluations. Teams should test Neon against their own research-heavy workloads rather than treating the overall index ranking as a drop-in replacement for Carbon.

**「Community Discussion」** Commenters focused heavily on naming confusion, with one saying it is hard to map names such as Neon, Carbon, Sol, Astra, and Opus to use cases, and another asking whether Google&\#x27;s naming scheme reveals model size class. A separate thread questioned benchmark-driven comparisons, with one user saying Gemini models still feel less capable than Opus 5.5 in general use despite benchmark results, while another user reported faster OpenRouter serving for Neon at 127 tokens per second versus Carbon at 46.

**Tags**: `#Gemini`, `#Google AI`, `#LLM release`, `#model naming`, `#AI industry`

---

<a id="item-tech-news-2"></a>
### [Wiz reports unauthenticated RCE flaws in Nginx HTTP/2](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

Wiz reports two Nginx HTTP/2 vulnerabilities, CVE-2026-123633 and CVE-2026-123007, that it describes as enabling unauthenticated remote code execution. The flaws affect Nginx deployments with HTTP/2 enabled, which is not the default configuration. The supplied source does not specify affected Nginx versions or a patched release, and commenters disputed how exploitable the bugs are in practice.

hackernews · speedping · Nov 18, 15:19 · [Discussion](https://news.ycombinator.com/item?id=50547374)

**「Background」** HTTP/2 is a multiplexed revision of HTTP, and these bugs sit in NGINX&\#x27;s own protocol handling rather than in the applications it serves, so a site can be exposed even when its application code is secure. Xint&\#x27;s analysis says every official NGINX release from 1.9.5 through 1.31.8 carries CVE-2026-123007 and that the vulnerable code was still in master as of November 10, 2026; Wiz rates both CVEs critical at CVSS 4.0 9.2.

**「Impact」** Operators who have enabled HTTP/2 should prioritize patching or disable HTTP/2 as a stopgap. Because the reported flaws are unauthenticated, exposed servers do not require stolen credentials for an attacker to attempt exploitation.

**「Community Discussion」** One commenter criticized the disclosure timeline, arguing that the fix had been visible in the open-source repository about a week before the advisory and that a temporary PSA to disable HTTP/2 would have been warranted. Others countered that HTTP/2 is not enabled by default and reaches only about 12% of servers, while another commenter claimed exploitation requires roughly 128GB of HTTP/2 traffic and specific CPU instructions and called it a non-issue.

<details><summary>References</summary>
<ul>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root: New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>

</ul>
</details>

**Tags**: `#nginx`, `#http/2`, `#security vulnerability`, `#remote code execution`, `#CVE`

---

<a id="item-tech-news-3"></a>
### [Xint discloses nginx-to-root chain of five flaws](https://nginx2root.com/) ⭐️ 8.0/10

Xint&\#x27;s NGINX2Root disclosure claims a chain of five nginx vulnerabilities plus a Linux kernel flaw can take an unauthenticated nginx visitor to host root; the Telegram post identifies CVE-2026-123007 as an HTTP/2 flow-control memory-corruption bug that allows command execution in a worker without authentication. It says nginx 1.30.7 and 1.31.9 fix 10 CVEs on November 18, that Rapid7 has published a proof-of-concept, and that no in-the-wild exploitation is known. These details come from a Telegram summary and have not been independently verified.

telegram · zaihuapd · Nov 18, 16:21

**「Background」** The HTTP/2 bug central to the chain, CVE-2026-123007, was present in every official nginx release from 1.9.5, shipped in September 2015, through 1.31.8, and Xint reported that the vulnerable code was still in the development branch as of November 10, 2026. The first fixed releases are 1.31.9 and 1.30.7.

**「Impact」** Operators are directed to nginx 1.30.7 or 1.31.9; the post says those who cannot upgrade should disable externally accessible HTTP/2, which can affect clients that depend on the protocol.

<details><summary>References</summary>
<ul>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root : New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html">10-Year-Old NGINX HTTP/2 Flaw Lets Unauthenticated Attackers...</a></li>

</ul>
</details>

**Tags**: `#nginx`, `#HTTP/2`, `#privilege escalation`, `#vulnerability disclosure`, `#CVE`

---

<a id="item-tech-news-4"></a>
### [Quad9’s France exit shows DNS blocking is the wrong anti-piracy tool](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

DNS resolver Quad9 has withdrawn from France over DNS blocking, and this analysis argues that using resolvers to enforce piracy law is overbroad and inappropriate. The piece treats the withdrawal as a case study, contending that DNS-level blocking turns resolver operators into enforcement and censorship choke points instead of targeting alleged infringers. It is an opinion/analysis with limited primary technical detail, so it does not establish the French order’s scope or its measurable effects.

hackernews · ritzaco · Nov 18, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50545958)

**「Background」** A DNS resolver translates domain names into IP addresses, and Quad9 is a nonprofit public resolver. In October 2026, reporting said a Paris court ordered Quad9 to block domains accused of distributing unauthorized sports broadcasts; Quad9 was set to stop serving French users on November 24 rather than comply, making it the second DNS resolver to leave France over such orders.

**「Impact」** The concrete consequence is that users in France who relied on Quad9 lose that resolver option, while other independent DNS operators face the same choice the article describes: comply with blocking mandates or exit the jurisdiction.

**「Community discussion」** Commenters were skeptical of DNS enforcement: one argued that any anti-piracy effort short of prosecuting pirates is a backdoor to suppressing speech, and another said the better remedy is making paid options easier than piracy, citing DRM-free movie downloads at $2–5. A third asked whether blame belongs with judges or lawmakers, framing the issue as either judicial incompetence or a defensible reading of a bad law, while another questioned pursuing individual pirates when commercial IP use by AI companies goes unprosecuted.

<details><summary>References</summary>
<ul>
<li><a href="https://torrentfreak.com/dns-resolver-quad9-will-leave-france-after-court-orders-piracy-blocking-penalty/">DNS Resolver Quad9 Will Leave France After Court Orders ...</a></li>
<li><a href="https://cyberinsider.com/quad9-to-leave-france/">Quad9 to leave France after court orders piracy-related DNS ...</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet censorship`, `#piracy`, `#Quad9`, `#internet policy`

---

<a id="item-tech-news-5"></a>
### [Microsoft announces seven AI models pitched at scalable price-performance](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

Microsoft announced seven new AI models under a scalable price-performance pitch. The available item does not provide model names beyond a commenter&\#x27;s reference to MAI Code 2, nor benchmark figures, pricing tiers, release dates, or compatibility details, so the announcement&\#x27;s performance and cost claims cannot be independently assessed. A commenter says MAI Code 2 has performed well in their usual work and that Microsoft positions it near Opus or Sol, but that is a single user report rather than a published benchmark.

hackernews · gmays · Nov 18, 16:08 · [Discussion](https://news.ycombinator.com/item?id=50548021)

**「Background」** Microsoft&\#x27;s price-performance claim is measured against established coding models: its own comparison puts MAI Code 2 at 98% of GPT-6.1 Sol&\#x27;s coding quality for about 40% of the price, and at 96% of Opus 5.5&\#x27;s performance for 5% of the price. The Ignite lineup also covers specialized models for vulnerability discovery and image generation, reflecting a task-specific rather than one-model-fits-all approach.

**「What it means for Copilot users」** Developers can already try the coding models from the announcement — MAI Code 2 and the smaller MAI Code 2 Flash — inside GitHub Copilot, including on its free plan, according to coverage of the launch. The headline figures \(98% of GPT-6.1 Sol&\#x27;s performance at 40% of the cost, 96% of Claude Opus 5.5&\#x27;s at 5% of the cost\) are Microsoft&\#x27;s own claims averaged over four coding benchmarks, and the announcement footnote qualifies the cost basis, so teams weighing a switch should benchmark on their own workloads rather than treat the ratios as independently measured.

**「Community Discussion」** Commenters split between a hands-on report that MAI Code 2 is “quite good” for ordinary work and skepticism about Microsoft&\#x27;s market position: one argued that the models need open-source or open-weight releases to gain share, comparing the alternative to Windows Phone. Others criticized the Ignite keynote as shallow and said they see no reason to adopt Microsoft&\#x27;s AI stack.

<details><summary>References</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world class models at scalable... | Microsoft AI</a></li>
<li><a href="https://forklog.com/en/microsoft-unveils-ai-models-for-coding-and-cybersecurity/">Microsoft unveils AI models for coding and cybersecurity | ForkLog</a></li>
<li><a href="https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/">MAI Code 2 and Code 2 Flash: Everyday coding at scalable ...</a></li>
<li><a href="https://felloai.com/mai-code-2/">MAI Code 2: Price, Benchmarks and Copilot Plans</a></li>
<li><a href="https://www.datastudios.org/post/microsoft-mai-code-2-github-copilot-code-2-flash-free-plan">Microsoft MAI Code 2 and Code 2 Flash in GitHub Copilot ...</a></li>

</ul>
</details>

**Tags**: `#microsoft`, `#ai-models`, `#price-performance`, `#model-release`, `#coding-assistants`

---

<a id="item-tech-news-6"></a>
### [Google DeepMind announces Genie 4 for eligible AI Ultra subscribers](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind announced Genie 4, a new version of its world-model system. The available material provides no benchmarks, model details, or precise rollout terms; the announcement lists access for eligible Google AI Ultra subscribers, and commenters report confusion over regional and workspace-account eligibility.

hackernews · leumon · Nov 18, 18:49 · [Discussion](https://news.ycombinator.com/item?id=50550415)

**「What Genie is」** Genie is Google DeepMind&\#x27;s family of generative world models: systems that use text and image prompts to produce photorealistic environments that users can explore and interact with in real time. DeepMind describes Genie 4 as its &quot;most interactive world model yet,&quot; continuing that prompt-to-interactive-world approach.

**「Access and audio changes for Genie users」** Access is the binding constraint: Genie 4 is offered to eligible Google AI Ultra subscribers, and one commenter reported that their Workspace account could not obtain Ultra while their consumer account still surfaced Genie 3, leaving UK availability unconfirmed — so teams planning to build on Genie 4 should confirm subscription tier and regional eligibility before committing. For those with access, Genie 4 generates audio such as music, ambient noise, and interactive dialogue simultaneously with the world, so agent-training pipelines built around silent world output, such as SIMA runs, must handle the added audio channel.

**「Community discussion」** Commenters focused on practical access, with one unable to determine whether UK availability or workspace-account restrictions explain why their account shows Genie 3 rather than Genie 4. Others debated whether the work is craft-driven rather than commercially viable, raised concerns about negative consequences, and treated 360-degree scene consistency as a key test of a world model.

<details><summary>References</summary>
<ul>
<li><a href="https://deepmind.google/models/genie/">Genie 4 — Google DeepMind</a></li>
<li><a href="https://deepmind.google/models/genie/">Genie 4 — Google DeepMind</a></li>
<li><a href="https://deepmind.google/models/model-cards/genie-4/">Genie 4 - Model Card — Google DeepMind</a></li>

</ul>
</details>

**Tags**: `#world models`, `#Google DeepMind`, `#generative AI`, `#AI research`, `#product availability`

---

<a id="item-tech-news-7"></a>
### [pikuma.com Technical Retrospective: Intel x86 From 4004 to 486](https://pikuma.com/blog/history-of-x86-4004-to-486) ⭐️ 7.0/10

pikuma.com published a technical retrospective tracing Intel&\#x27;s CPU evolution from the 4004 through the 486, aimed at systems and software engineers interested in early x86 architecture. The item is a historical analysis rather than a new product announcement or an independently measured benchmark. No primary article text was supplied with the item, so its specific technical claims could not be checked here.

hackernews · ibobev · Nov 18, 14:47 · [Discussion](https://news.ycombinator.com/item?id=50546967)

**「Background」** The 4004&\#x27;s architecture laid the foundation for later Intel processors, including the 4040 and the 8-bit 8008 and 8080. The 8008, introduced in April 1972, could address 16 KB of memory and was designed by Computer Terminal Corporation but implemented and manufactured by Intel.

**「Community Discussion」** Commenters supplied corrections and context: chimpontherun argues the original little-endian choice on the 2200 was driven by data-access speed rather than arithmetic, and that multiplexed address/data buses were not unique to the 8085; petercooper and kens dispute parts of the article&\#x27;s framing of the 8008&\#x27;s instruction set and its relationship to the 4004. Separately, skissane questions why Intel and AMD still make modern PCs start in a mode compatible with 1978-era chips, arguing that BIOS writers could adapt if the vendors changed the requirement.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Intel_4004">Intel 4004 - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Intel_8008">Intel 8008 - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#x86`, `#computer-history`, `#cpu-architecture`, `#intel`, `#hardware`

---

<a id="item-tech-news-8"></a>
### [Show HN: Interactive Voyager 1 model goes down to a single memory chip](https://rshekhar.com/voyager/) ⭐️ 7.0/10

Raj Shekhar has published an interactive site at rshekhar.com/voyager that lets visitors inspect Voyager 1, including its nuclear battery&\#x27;s 24 plutonium spheres, its data computer down to individual memory chips, and the Golden Record cover; it also shows where both Voyagers are now and which Earth dish is listening live. The site walks through how Voyager 1 was repaired by radio, and Shekhar posted it as Voyager 1 reached one light-day from Earth and made a four-minute film from the material. It is an educational visualization rather than a new mission result, and Shekhar supplied direct links for hard-to-find views such as a single bit of command-computer memory.

hackernews · raj-shekhar · Nov 18, 16:18 · [Discussion](https://news.ycombinator.com/item?id=50548161)

**「Why one light-day matters」** Voyager 1 is the first human-made object to reach interstellar space, and it is now roughly one light-day from Earth — about 173 astronomical units, the milestone this interactive breakdown is built around. At that range a radio command takes close to a day to arrive and its reply another day to come back, so the memory-chip repair the site documents under &quot;how Voyager 1 was fixed by radio&quot; had to be executed as a pre-planned sequence rather than live troubleshooting.

**「Impact」** For hardware and embedded-systems readers, the drill-down paths expose the spacecraft&\#x27;s computer organization at bay, memory-plane, and single-bit levels, so the design can be inspected directly rather than through a separate technical reference.

**「Community discussion」** Commenters praised the detail and shared related Golden Record projects, including a decoder for the record&\#x27;s raw audio; one commenter asked what physical failure mode made a CMOS memory IC consistently misread stored values, and another asked whether the site was AI-generated and checked against authoritative sources. Those questions were not answered in the supplied comments.

<details><summary>References</summary>
<ul>
<li><a href="https://science.nasa.gov/mission/voyager/voyager-1/">Voyager 1 : The Farthest Spacecraft — NASA Science</a></li>
<li><a href="https://phys.org/news/2026-11-nasa-voyager-day-interstellar-space.html">NASA&#x27;s Voyager 1 closes in on a light - day in interstellar space for...</a></li>

</ul>
</details>

**Tags**: `#interactive-visualization`, `#computer-hardware`, `#spacecraft`, `#embedded-systems`, `#education`

---

<a id="item-tech-news-9"></a>
### [curl Maintainer Says AI Rust Rewrites Lag 200+ Bugfixes](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) ⭐️ 7.0/10

curl maintainer Daniel Stenberg wrote that AI agents converted 185,000 lines of C code into 340,000 lines of Rust in a little over three weeks, while the actual curl project merged more than 300 commits during the same period, including over 200 bugfixes and several vulnerability fixes. He said none of the Rust rewrites contain those fixes and asked whether the generated clones can keep up as curl continues to change. Stenberg added that in another month the project would have made another 200 fixes and perhaps addressed more vulnerabilities.

rss · Simon Willison · Nov 18, 15:58

**「Background」** curl is a C codebase, and the Rust efforts Stenberg describes are separate AI-generated ports rather than changes merged into upstream curl. That distinction matters because upstream development continued in parallel: the comparison is between the maintained project and generated clones that must independently track later bug and security fixes.

**「Impact」** For developers considering a generated Rust port as a replacement, the comparison highlights a continuing maintenance gap: a one-time conversion does not include curl&\#x27;s 200+ bugfixes or vulnerability fixes, so adopters would need a way to track and apply upstream changes.

**Tags**: `#AI coding agents`, `#curl`, `#Rust`, `#open source maintenance`, `#security`

---

<a id="item-tech-news-10"></a>
### [WeChat Xiaowei AI assistant test expands to 30 million daily users](https://mp.weixin.qq.com/s/r3NthxJZQJgztyLADwNV4A) ⭐️ 7.0/10

Tencent said in its Q3 2026 earnings report that WeChat&\#x27;s Xiaowei AI assistant has expanded testing to 30 million daily active users and is being gradually integrated into WeChat chats, Moments, Official Accounts and Channels. The assistant uses a cost-optimized custom WeLM model, and Tencent claims its inference cost is low and continuing to fall. Tencent also expects some inference tasks to run on users&\#x27; devices in the future.

telegram · zaihuapd · Nov 18, 11:35

**「Context」** Tencent names WeLM as the base model for Xiaowei and says the version used here is customized for cost efficiency; the source does not disclose its parameter count or version. The 30 million figure is a daily-active-user count within an expanded test, so it does not establish that Xiaowei is generally available to all WeChat users.

**「Impact」** The 30 million figure describes an expanded test rather than a general release; Tencent did not disclose a full-rollout date, device requirements, or which tasks would run on-device. For users, Xiaowei is appearing across more WeChat surfaces during the test, but availability remains limited to the test scope.

**Tags**: `#WeChat`, `#Tencent`, `#AI assistant`, `#WeLM`, `#on-device AI`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed October minutes signal further rate hikes and AI inflation risk](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

Minutes from the Federal Reserve&\#x27;s October meeting showed almost all officials judged further rate increases would likely be appropriate to return inflation to 2%, while the FOMC voted 10-2 to hold its benchmark rate at 3.75%-4%. Officials also flagged AI-related demand and opaque financing as material inflation and financial-instability concerns.

rss · CNBC Finance · Nov 18, 19:41

**「Background」** Since the meeting, October CPI rose 0.4% overall and 0.3% excluding food and energy, each 0.1 percentage point above expectations and well above the Fed&\#x27;s 2% target.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#artificial intelligence`, `#financial stability`

---

<a id="item-finance-news-2"></a>
### [Tencent Q3 2026: revenue misses estimates as capex jumps](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

Tencent’s 2026 third-quarter revenue rose 8% year on year to 207.3 billion yuan, missing market expectations, while capital expenditure reached 81.433 billion yuan—well above the 55.4 billion yuan consensus estimate—and free cash flow was negative 69.1 billion yuan. The company also said its WorkBuddy product has the highest daily token usage among domestic large-language-model products, exceeding 100 trillion tokens a day, a company-disclosed milestone without an independent baseline.

telegram · zaihuapd · Nov 18, 09:20

**「Background」** WorkBuddy is an AI-agent office tool from Tencent Cloud’s code-assistant unit; tokens are the units of text that language models process, so daily token counts measure usage. Tencent’s filing attributed the quarter’s negative free cash flow to 65.1 billion yuan of capital-expenditure payments outweighing 2.6 billion yuan in net operating cash.

**「Who is affected」** The burden falls mainly on Tencent shareholders: Bloomberg reported that the company&\#x27;s AI spending has begun to stall profit growth, as margins are sacrificed to fund a buildout with no clear immediate returns.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611183934001422.html">腾 讯 控股 第 三 季 度 营 收 2073 亿 元 同比增长8% _ 东方 财 富网</a></li>
<li><a href="https://www.workbuddy.cn/">WorkBuddy - AI Agent 办公新范式</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-18/tencent-s-sales-miss-estimates-in-setback-for-founder-s-ai-push">Tencent ’s Profit Squeeze Exposes China’s AI Spending... - Bloomberg</a></li>

</ul>
</details>

**Tags**: `#Tencent`, `#earnings`, `#AI capex`, `#free cash flow`, `#token usage`

---