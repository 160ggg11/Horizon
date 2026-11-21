---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 41 items, 17 important content pieces were selected

---

**Technology News**
1. [Terry Tao on unforced Navier–Stokes singularities and the Generalized Riemann Hypothesis](#item-tech-news-1) ⭐️ 9.0/10
2. [Alpöge Claims Generalized Riemann Hypothesis Proof With Lean Formalization](#item-tech-news-2) ⭐️ 8.0/10
3. [GitHub repo claims Navier–Stokes blow-up, without a published proof](#item-tech-news-3) ⭐️ 8.0/10
4. [KVM Flaw CVE-2026-99312 Exposes AMD Host Memory to Guests](#item-tech-news-4) ⭐️ 8.0/10
5. [TSMC Halts 16nm-and-Below Orders From Chinese Firms Under US Rules](#item-tech-news-5) ⭐️ 8.0/10
6. [Zhejiang University reports real-device QRAM prototype on superconducting chip](#item-tech-news-6) ⭐️ 8.0/10
7. [Thinking Machines releases Inkling 2 Mini, a local-first looped transformer](#item-tech-news-7) ⭐️ 7.0/10
8. [Aaronson post on LLMs, theorem proving, and Riemann Hypothesis debated](#item-tech-news-8) ⭐️ 7.0/10
9. [Nasdaq Erases 2026 Gains as AI Selloff Weighs on Anthropic IPO](#item-tech-news-9) ⭐️ 7.0/10
10. [Ravi Vakil announces proposed proof of Generalized Riemann Hypothesis](#item-tech-news-10) ⭐️ 7.0/10
11. [OpenAI claims anti-distillation defenses cut reasoning extraction to 0.2%](#item-tech-news-11) ⭐️ 7.0/10
12. [Trump Threatens Large Taxes on US AI Data Centers Built Abroad](#item-tech-news-12) ⭐️ 7.0/10
13. [Microsoft previews RDMA over USB4 for pooling PCs to run local AI](#item-tech-news-13) ⭐️ 7.0/10
14. [OpenRouter warns MiniMax prompts may be exposed to third parties](#item-tech-news-14) ⭐️ 7.0/10

**Technology Blog**
1. [Why Output Caching Barely Helps LLM Agent Costs](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Fed Officials Speak More as Warsh Withholds Rate Guidance](#item-finance-news-1) ⭐️ 7.0/10
2. [Net U.S. Equity Issuance Reaches 3.1% of Market Value, Acadian Says](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Terry Tao on unforced Navier–Stokes singularities and the Generalized Riemann Hypothesis](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 9.0/10

Terry Tao has published a blog post titled &quot;Unforced Euler Singularity, Unforced Navier-Stokes Singularity, and the Generalized Riemann Hypothesis,&quot; which by its title addresses unforced singularity formation in the Euler and Navier–Stokes equations together with the Generalized Riemann Hypothesis. No body text of the post was available in the supplied material, so the specific claims, constructions, or conditions it sets out cannot be verified or summarized here. The accompanying Hacker News discussion centered not on the mathematical arguments but on Lean formalization and on how much trust to place in very large machine-checked proofs.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Background」** Terry Tao&\#x27;s post concerns two longstanding open problems: whether the Navier–Stokes equations can develop finite-time singularities from smooth initial data, and the Generalized Riemann Hypothesis, which extends the Riemann Hypothesis to a broader class of L-functions. The discussion also centers on Lean, a proof assistant that machine-checks formal proofs against a small kernel. Tao&\#x27;s blog listing separately advertises MathHelm, a venue for discussing AI-generated papers, and a related Hacker News listing points to a GitHub paper on finite-time blow-up for Navier–Stokes.

**「Verification burden shifts to statement fidelity」** For mathematicians and formal-verification engineers, the practical consequence is that trust shifts from reading a proof to auditing its formal statement: a passing Lean build certifies only the encoded theorem, so independent kernel checks and statement-fidelity review become the operative safeguards as proofs reach the scale cited in the thread \(15 million lines\). Commenters report that two independent kernels accepted one such result, which addresses kernel bugs but not whether the formal statement matches the claimed theorem; announcements of AI-generated Lean proofs for Navier–Stokes and the Riemann Hypothesis make that distinction routine rather than hypothetical.

**「Community discussion」** One commenter linked a Lean Zulip discussion and argued that because two independent kernels accept the result under discussion, kernel-bug exploitation is unlikely; others were less settled, with swingboy asking how, in a body of roughly 15 million lines of Lean, anyone can tell that a passing build proves the intended statement rather than something trivial that merely type-checks. Several commenters described the moment in emotional terms, reporting excitement mixed with career anxiety rather than offering technical assessments.

<details><summary>References</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Euler singularity, unforced Navier - Stokes singularity , and...</a></li>
<li><a href="https://news.ycombinator.com/news">Hacker News</a></li>
<li><a href="https://openai.com/index/navier-stokes-solution/">On the Navier–Stokes Millennium Prize Problem | OpenAI</a></li>
<li><a href="https://timesof.ai/2026/11/anthropic-mathematician-alpoge-riemann-hypothesis-proof-claude-lean-checks-pass">Riemann Hypothesis Proof Claimed With Claude | Times of AI</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#formal verification`, `#Lean`, `#Navier-Stokes`, `#Riemann Hypothesis`

---

<a id="item-tech-news-2"></a>
### [Alpöge Claims Generalized Riemann Hypothesis Proof With Lean Formalization](https://alpo.ge/remark.pdf) ⭐️ 8.0/10

Levent Alpöge has posted a PDF claiming that, working with Claude, he discovered a proof of the Riemann Hypothesis that extends to the Generalized Riemann Hypothesis and formalized the arguments in Lean without assumptions; he also says he expects the Extended Riemann Hypothesis with more time. The supplied item provides no independent verification or peer review and is labeled an unverified claim. A commenter reports that the Lean proof archive is about 1.3 GB and roughly 15 million lines, indicating the artifact&\#x27;s scale but not its correctness.

hackernews · iamronaldo · Nov 20, 14:16 · [Discussion](https://news.ycombinator.com/item?id=50574968)

**「Background」** The Riemann Hypothesis is an 1859 conjecture about the zeros of the Riemann zeta function, and the Generalized Riemann Hypothesis extends the claim to a much broader family of objects; Scientific American describes the generalization as a &quot;gargantuan expansion&quot; on Riemann&\#x27;s original guess. The claim rests on a Lean formalization, and Lean checks that a proof follows from its stated assumptions, but as mathematician Dr. Maynard told the New York Times, &quot;you have to be a little bit careful about making sure that a Lean verification is proving the thing that you want it to be proving.&quot; Neither the argument nor its formal statement has been independently confirmed.

**「Impact」** Mathematicians and formal-verification practitioners should treat the theorem as unverified until the Lean development is independently checked; the reported 1.3 GB size makes that audit a substantial task, and the PDF&\#x27;s assertion of a proof without assumptions is not itself confirmation.

**「Community discussion」** Commenters focused on the proof&\#x27;s reported scale and on the pace of AI-driven mathematical discovery, with reactions ranging from excitement to concern about the speed of such results and calls for a pause. The supplied comments do not include an independent verification of the Lean formalization.

<details><summary>References</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>
<li><a href="https://www.nacionale.com/en/articles/has-riemann-hypothesis-been-proved-levent-alpoge-claude-anthropic-claim-lean">Riemann hypothesis proof claimed with Claude , unverified</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis With...</a></li>

</ul>
</details>

**Tags**: `#Riemann Hypothesis`, `#Lean`, `#formal verification`, `#mathematics`, `#unverified claim`

---

<a id="item-tech-news-3"></a>
### [GitHub repo claims Navier–Stokes blow-up, without a published proof](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

A Hacker News submission points to a GitHub repository attributed to Tristan Buckmaster that claims a finite-time blow-up result for the Navier–Stokes equations. The supplied material contains no abstract, preprint, proof sketch, or peer review, and no statement of the dimension, function space, or boundary conditions involved, so the claim cannot be assessed from the evidence given. Commenters describe the work as targeting the unforced version of the problem, in contrast to a separate claimed result they attribute to OpenAI that reportedly relies on a deliberately constructed external force. The existence and correctness of the result therefore remain unverified.

hackernews · trotro · Nov 20, 15:34 · [Discussion](https://news.ycombinator.com/item?id=50576232)

**「Background」** The Navier–Stokes existence and smoothness problem is one of the Clay Mathematics Institute&\#x27;s Millennium Prize problems: it asks whether smooth, compactly supported initial data in three dimensions always produce smooth solutions for all time, or whether solutions can instead blow up in finite time. The linked repository accompanies a paper by L. Alpöge and T. Buckmaster and contains a 79-page PDF plus a Lean 4 package formalizing the paper&\#x27;s statements and proofs \(tool-2-1\); the paper&\#x27;s abstract claims unforced blow-up for compactly supported data on R^3 and periodic data on T^3, resting on an approximate self-similar profile checked by interval arithmetic \(tool-2-2\).

**「Impact」** For readers trying to judge the claim, the operative question is verification: a finite-time blow-up proof would need a complete argument plus an explicit statement of the setting \(for example dimension, incompressibility, and the function class in which the solution is constructed\) before anyone can compare it with prior partial results or with the reportedly forced counterexample. Commenters also asked whether a numerical simulation could reproduce the blow-up in real time to build intuition, but nothing in the supplied material indicates such a demonstration exists.

**「Community Discussion」** Commenters framed the repository as the unforced counterpart to a reported OpenAI result, with one arguing the unforced case is &quot;more realistic&quot; because the other depends on a carefully designed external force. Others focused on priority and speculation about AI-lab involvement, and one characterized the day as unusually significant for mathematics by citing a separate claimed generalized Riemann Hypothesis result; these are commenter opinions and rumors, not confirmed facts.

<details><summary>References</summary>
<ul>
<li><a href="https://hotrepo.ai/tristanbuckmaster/navier-stokes">tristanbuckmaster/navier-stokes: Lean 4 formalization of a ...</a></li>
<li><a href="https://aixiv.online/abs/2611.02204">[2611.02204] Finite-time blow-up for the Navier–Stokes ...</a></li>

</ul>
</details>

**Tags**: `#Navier-Stokes equations`, `#mathematical research`, `#fluid dynamics`, `#research breakthrough`, `#Hacker News`

---

<a id="item-tech-news-4"></a>
### [KVM Flaw CVE-2026-99312 Exposes AMD Host Memory to Guests](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

A Linux KVM vulnerability, CVE-2026-99312, reportedly lets a guest virtual machine read host memory on AMD hosts when nested virtualization is enabled. Researchers demonstrated the flaw on DigitalOcean by reading about 127 GB of host memory from inside a VM. Upstream fixes shipped on November 18 in stable kernel 7.3.5 and other stable releases, but Debian and Ubuntu distribution kernels remained unpatched, according to the secondary summary. Operators can disable nested virtualization as a mitigation until patched kernels are available.

telegram · zaihuapd · Nov 20, 14:23

**「Background」** The flaw is a use-after-free in Linux KVM&\#x27;s AMD nested-virtualization code: when KVM emulates an INIT processor reset with paging disabled, it fails to clear the nested page table \(NPT\) pointer. The stale NPT page can then be freed and reallocated, allowing a guest to forge page-table entries and reach host memory, according to Red Hat&\#x27;s CVE entry.

**「Impact」** Cloud providers and operators running AMD hosts with nested virtualization should apply a kernel containing the upstream fix or disable nested virtualization; guests on unpatched Debian or Ubuntu kernels remain exposed.

<details><summary>References</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99312">CVE-2026-99312 - Red Hat Customer Portal</a></li>

</ul>
</details>

**Tags**: `#KVM`, `#Linux kernel`, `#CVE`, `#virtualization security`, `#AMD`

---

<a id="item-tech-news-5"></a>
### [TSMC Halts 16nm-and-Below Orders From Chinese Firms Under US Rules](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

TSMC has reportedly notified customers that it is suspending advanced-process orders — 16nm and below — from Chinese companies, because tightened US semiconductor export rules bar shipments without a prior US export license or exemption. Previously TSMC could itself assess whether a customer&\#x27;s design met exemption criteria; under the new requirement customers must apply in advance, and the US approved list includes Apple, AMD and Nvidia but no Chinese companies. Chinese firms are consequently limited to older nodes such as 28nm and 40nm and lose access to the high-bandwidth memory used in AI data centers. The account comes from a brief secondary summary attributing the report to AppleInsider, and TSMC has only said it will comply with the new rules, so the suspension should be treated as reported rather than confirmed in detail.

telegram · zaihuapd · Nov 21, 02:01

**「Background」** 16nm and below are advanced logic process nodes, and HBM is high-bandwidth memory used in AI data-center systems. The report says the tightened US rules change how exemptions work: TSMC previously could assess customer designs itself, but customers must now apply in advance, and the report names Apple, AMD and Nvidia on the US approved list but no Chinese company.

**「Impact」** Chinese chip designers that rely on TSMC&\#x27;s 16nm-and-below processes must now obtain a US export license or exemption before placing orders, rather than relying on TSMC&\#x27;s own design review. Those without approval will need to retarget products to older 28nm or 40nm nodes or qualify another foundry, a particular constraint for AI data-center chips that require advanced nodes and HBM.

**Tags**: `#TSMC`, `#US export controls`, `#semiconductors`, `#China`, `#AI chips`

---

<a id="item-tech-news-6"></a>
### [Zhejiang University reports real-device QRAM prototype on superconducting chip](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

Researchers at Zhejiang University report that they have run a quantum random-access memory \(QRAM\) prototype on their own superconducting chip, “Tianmu-2,” and say it is the first real-device implementation of the architecture. The team says the results were published in Nature Physics. The chip ran 4-bit and 8-bit data-retrieval prototypes with 80.9% and 60.4% accuracy, respectively; the team also reports that circuit depth fell by more than 30% versus an unoptimized design and that local noise resilience was verified for the first time. The team plans to scale up the QRAM work, but the 8-bit accuracy is low and scalability has not been demonstrated.

telegram · zaihuapd · Nov 21, 08:31

**「What QRAM requires」** QRAM is a proposed quantum memory that lets an algorithm query many stored entries at once by addressing them in superposition, a capability underlying several data-intensive quantum algorithms. Building it physically is hard because straightforward designs require deep circuits and are highly sensitive to noise, making any real-device demonstration a test of whether the architecture can be made practical.

**「Impact」** The 60.4% eight-bit retrieval accuracy leaves the prototype short of the reliability needed for practical quantum algorithms, so the immediate result is a research baseline: follow-up experiments must raise fidelity and demonstrate scaling before QRAM’s claimed memory advantage can be tested in real workloads.

**Tags**: `#quantum computing`, `#QRAM`, `#superconducting qubits`, `#hardware`, `#research`

---

<a id="item-tech-news-7"></a>
### [Thinking Machines releases Inkling 2 Mini, a local-first looped transformer](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 7.0/10

Thinking Machines released Inkling 2 Mini, a small, local-first language model that uses a looped transformer architecture instead of a standard feed-forward stack. A commenter quoted a Reddit note saying the model was trained end-to-end in nvfp4, and other commenters reported running it through llama.cpp with Vulkan at about 27 tokens/s on a Ryzen 395 and about 10 tokens/s on a 32GB M1 Pro MacBook. Those throughput figures and comparisons to Qwen3.8-27B are user reports, not independently verified benchmarks; the linked article body was not available. Commenters also said the model is open weights and aimed at local deployment.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「Background」** Thinking Machines describes Inkling 2 Mini as a looped transformer: the model runs its middle layers three times for every token, a design the company says lets it apply more reasoning and reach answers with fewer tokens, especially on reasoning-heavy tasks such as agentic coding.

**「Local deployment caveats」** Running Inkling 2 Mini locally currently depends on unmerged llama.cpp pull requests \(32694, 32657, 32429, 32704\); one commenter reported that adding a small patch to src/llama-graph.cpp on top of those gave roughly a 30% speed boost. Reported throughput in the comments was about 27 tokens/s decode on a Ryzen 395 via llama.cpp&\#x27;s Vulkan backend and about 10 tokens/s on a 32GB M1 Pro at q4 while other applications were running, so users on comparable hardware should expect interactive but not fast generation. The team&\#x27;s end-to-end nvfp4 training, per its Reddit note quoted in the thread, was aimed at making the model more amenable to local use, though the commenter&\#x27;s excerpt leaves the qualification about that training incomplete.

**「Community discussion」** Commenters were impressed by the benchmark claims—one called the results &quot;bonkers good if these benchmarks hold up&quot;—and several focused on the unusual looped architecture, with one predicting most open models would adopt it and another raising safety and interpretability questions. The most practical thread was hands-on deployment: users shared llama.cpp Vulkan throughput numbers, unmerged PR references, and a small patch claimed to give about a 30% speed boost.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>

</ul>
</details>

**Tags**: `#LLM`, `#local inference`, `#model release`, `#llama.cpp`, `#transformer architecture`

---

<a id="item-tech-news-8"></a>
### [Aaronson post on LLMs, theorem proving, and Riemann Hypothesis debated](https://scottaaronson.blog/?p=10344) ⭐️ 7.0/10

A Hacker News submission links to a Scott Aaronson blog post headlined &quot;The stochastic parrots have apparently proved the Riemann Hypothesis,&quot; framing LLMs and mathematical theorem proving. The supplied item does not include the post text, so no actual result, method, Lean formalization, or claim of a proof can be verified; nothing in the supplied material supports reading the headline as a literal Riemann Hypothesis proof. Discussion instead centers on the idea of combining Lean with a stochastic predictor as a brute-force theorem solver.

hackernews · stratos123 · Nov 20, 20:03 · [Discussion](https://news.ycombinator.com/item?id=50581084)

**「Context: what the claim involves」** The Riemann Hypothesis, posed in 1859, asserts that every non-trivial zero of the Riemann zeta function has real part 1/2; the Generalized Riemann Hypothesis the post&\#x27;s title alludes to extends the claim to a wider family of L-functions, and neither has been proved. Lean is an interactive theorem prover built on dependent type theory, so a proof encoded in it can in principle be checked mechanically line by line rather than accepted on an author&\#x27;s authority. According to a summary of the post, Levent Alpöge reported that Anthropic models produced a 17.4-million-line Lean proof of the Generalized Riemann Hypothesis, and Aaronson&\#x27;s stated position is that the result needs scrutiny even though he saw no sign the AI had exploited known weaknesses in Lean.

**「What Lean actually guarantees」** For developers and mathematicians working in Lean, the practical consequence is that an LLM-generated proof is only as trustworthy as the kernel check that follows it: Lean accepts a proof term only if it type-checks against the stated theorem, so verification remains the gate rather than generation. Commenters characterize the pattern as &quot;Lean + Stochastic predictor = Brute-force theorem solver,&quot; and Anthropic&\#x27;s write-up on formalizing Fermat&\#x27;s Last Theorem likewise treats checking a proof like checking a computation as the novel contribution — implying the bottleneck sits in formalizing statements correctly, not in search over goals.

**「Community discussion」** Commenters frame the technical idea as &quot;Lean + stochastic predictor = brute-force theorem solver&quot; and compare its spirit to AlphaGo, while another asks whether anyone can comprehend Lean in its entirety. These are opinions about the framing, not verified results from the linked post.

<details><summary>References</summary>
<ul>
<li><a href="https://scottaaronson.blog/?p=10344">Shtetl-Optimized » Blog Archive » The stochastic parrots have ...</a></li>
<li><a href="https://hn.today/s/the-stochastic-parrots-have-apparently-proved-the-riemann-hypothesis">The stochastic parrots have apparently proved the Riemann ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Lean_%28proof_assistant%29">Lean (proof assistant) - Wikipedia</a></li>
<li><a href="https://www.anthropic.com/research/formalizing-fermats-last-theorem">Formalizing Fermat&#x27;s Last Theorem \ Anthropic</a></li>

</ul>
</details>

**Tags**: `#LLMs`, `#formal verification`, `#Lean`, `#automated theorem proving`, `#AI criticism`

---

<a id="item-tech-news-9"></a>
### [Nasdaq Erases 2026 Gains as AI Selloff Weighs on Anthropic IPO](https://www.theguardian.com/business/2026/nov/20/global-stock-markets-slump-anthropic-ipo-ai-sell-off) ⭐️ 7.0/10

The Nasdaq erased all of its 2026 gains on Nov. 20 as an AI-led selloff weighed on Anthropic&\#x27;s second day of public trading, according to The Guardian. The report treats the drop as a broad market move rather than an Anthropic-specific technical disclosure, and the supplied item provides no closing levels, valuation, or deal size.

hackernews · cdrnsf · Nov 20, 13:29 · [Discussion](https://news.ycombinator.com/item?id=50574383)

**「Context」** Anthropic&\#x27;s Nasdaq debut, under the ticker ANT, was described as the largest IPO on record, and the stock had gained on its first day before giving back most of that advance. The offering was being watched as a test of public-market appetite for AI companies after a period in which AI-linked shares had driven major indexes higher.

**「Impact」** Anthropic&\#x27;s IPO is thus trading into a falling AI market, making the aftermarket—not a stable offer price—the immediate reference for investors and for the company&\#x27;s public valuation. The item does not supply the closing price, amount raised, or valuation.

**「Community Discussion」** Commenters debated whether AI automation can shrink measured GDP by collapsing prices in high-wage industries, while one said Anthropic had flirted with its IPO price and was down 21% since trading began, blaming lofty valuations and IPO allocants reluctant to book deeper losses. Others criticized the concentration of AI gains among a small group and remarked on the unusual mix of events; these are opinions, not facts established by the report.

<details><summary>References</summary>
<ul>
<li><a href="https://247wallst.com/investing/2026/11/20/anthropic-sinks-14-on-day-two-as-ai-sell-off-spreads-coreweave-falls-6-amazon-slips-2/">Anthropic Sinks 14% on Day Two as AI Sell-Off Spreads ...</a></li>
<li><a href="https://www.cnn.com/2026/11/20/investing/us-stocks-anthropic-ai">Nasdaq wipes out gains for the year as Anthropic IPO fails to ...</a></li>

</ul>
</details>

**Tags**: `#AI industry`, `#stock market`, `#Anthropic`, `#IPO`, `#AI economics`

---

<a id="item-tech-news-10"></a>
### [Ravi Vakil announces proposed proof of Generalized Riemann Hypothesis](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 7.0/10

Ravi Vakil announced in a November 20 post that Alessandro Masullo has a proposed proof of the Generalized Riemann Hypothesis, and that Brian Conrad has been examining it closely for months and has given extensive feedback that is being incorporated. Vakil said the work is &quot;so far looking good&quot; and is &quot;all human, with no AI.&quot; The original plan was to bring Masullo to Stanford for a year to polish the writing and circulate the proof widely before announcing it, but Vakil said it now seems best to release the current draft. The announcement provides no technical details, manuscript, or independent verification.

rss · Simon Willison · Nov 20, 19:21

**「Background」** The Generalized Riemann Hypothesis extends the Riemann Hypothesis from the zeta function to a broader class of L-functions, so a proof would settle many number-theory results that currently depend on it. The announcement came amid competing claims: Scientific American reported that Vakil, the American Mathematical Society president, posted the human claim, while the New York Times reported that Conrad—Masullo&\#x27;s doctoral adviser—called Masullo&\#x27;s approach different from the one used by Dr. Alpoge and Claude and credible without major gaps.

**「Impact」** Number theorists who rely on results stated conditionally on GRH — such as the nonexistence of Siegel zeros, which GRH would imply — have no basis yet to treat those results as unconditional: Vakil&\#x27;s note announces a draft that &quot;is so far looking good,&quot; not a refereed or independently verified proof. The concrete step for readers is to wait for the draft itself and for scrutiny beyond the feedback Vakil describes before citing it as established.

<details><summary>References</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/dueling-claims-of-riemann-hypothesis-proofs-emerge/">Dueling claims of Riemann hypothesis proofs ... | Scientific American</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis With...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Riemann_hypothesis">Riemann hypothesis - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#number theory`, `#research`, `#GRH`, `#proof`

---

<a id="item-tech-news-11"></a>
### [OpenAI claims anti-distillation defenses cut reasoning extraction to 0.2%](https://openai.com/index/combatting-adversarial-distillation/) ⭐️ 7.0/10

OpenAI says it has strengthened protections around reasoning-model chains of thought, claiming that in red-team testing the success rate for extracting reasoning from historical requests fell from 54.0% to 0.2%, according to a November 20 post. The company attributes the improvement to defenses applied to its GPT-6.2 Astra and Sol models. OpenAI also says it takes enforcement action against thousands to tens of thousands of distillation accounts each week, and that it has reported suspected distillation by DeepSeek to Congress. The figures are vendor-reported, and the aggregated post does not describe the testing methodology, so the reduction has not been independently verified.

telegram · zaihuapd · Nov 21, 01:30

**「Background: adversarial distillation」** Adversarial distillation is the term OpenAI uses for unauthorized collection of a model&\#x27;s outputs or internal reasoning in order to transfer its capabilities into another model, which is the practice the new defenses target. OpenAI describes its countermeasures as layered, combining model training, safeguards, detection, and enforcement against accounts rather than relying on a single filter. The source item also notes that OpenAI has previously reported suspected distillation by DeepSeek to Congress.

**「Impact」** Developers and API customers whose pipelines depend on capturing or training on model reasoning traces should expect account-level enforcement, not just technical blocks, since OpenAI says it acts weekly against thousands to tens of thousands of distillation accounts. Because the extraction-resistance numbers come only from OpenAI&\#x27;s own red team, outside teams cannot yet judge how well the defenses hold against their own extraction methods.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/combatting-adversarial-distillation/">Combatting adversarial distillation - OpenAI</a></li>
<li><a href="https://xenospectrum.com/en/openai-gpt-distillation-defense-metrics/">OpenAI Cuts Success Rate of Reasoning-Extraction Attacks From ...</a></li>

</ul>
</details>

**Tags**: `#AI model security`, `#adversarial distillation`, `#OpenAI`, `#reasoning models`, `#model IP`

---

<a id="item-tech-news-12"></a>
### [Trump Threatens Large Taxes on US AI Data Centers Built Abroad](https://apnews.com/article/trump-artificial-intelligence-data-centers-f1ac03b73d13445400eeed8631d9d879) ⭐️ 7.0/10

Trump said at a White House press conference on Nov. 20 that he plans to impose &quot;large taxes&quot; on US technology companies that build AI data centers abroad. He said he had not yet told officials inside the government about the plan, which is intended to keep data centers in the United States and preserve an AI competitive edge over China. No tax rate, legislation, enforcement mechanism, or timeline was reported, so the proposal remains an announced intention rather than a finalized policy. Trump also urged communities to accept data centers and negotiate payments from developers, as local opposition has grown over electricity demand and noise.

telegram · zaihuapd · Nov 21, 03:26

**「Background」** Data-center siting in the US has become contentious, with the source reporting opposition in communities concerned about electricity demand and noise. That local resistance is the backdrop for Trump&\#x27;s suggestion that communities negotiate payments from developers rather than block projects.

**「Planning uncertainty」** US tech companies considering AI data-center projects abroad cannot yet quantify the threatened cost: the announcement supplied no tax rate, effective date, or enforcement mechanism, so the added tax exposure cannot be reliably modeled. Companies that keep or move projects to the US instead face Trump&\#x27;s separate push for developers to negotiate payments with host communities, adding a local-approval condition to domestic siting.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ibtimes.com/trump-tax-ai-data-centers-overseas-3810039">Trump Threatens &#x27;Tremendous Tax&#x27; On US Tech Firms Building AI ...</a></li>

</ul>
</details>

**Tags**: `#AI data centers`, `#US tech policy`, `#AI infrastructure`, `#geopolitics`, `#taxation`

---

<a id="item-tech-news-13"></a>
### [Microsoft previews RDMA over USB4 for pooling PCs to run local AI](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

Microsoft released a developer preview of RDMA over USB4 for Windows that lets multiple USB4-connected PCs share memory and GPU compute to run a single local AI model, without a dedicated NIC or switch. In a demo, three AMD Ryzen AI Max+ 395 systems ran Qwen3-235B-A22B at 4-bit quantization at roughly 18.5 tokens per second. The preview is being distributed through Windows Insider. The report comes from a secondary outlet and describes a developer preview rather than a generally available feature, and no supported hardware list or scaling data beyond the three-machine demo was given.

telegram · zaihuapd · Nov 21, 06:13

**「Background」** RDMA, or remote direct memory access, lets one machine read and write another&\#x27;s memory directly, reducing CPU overhead, and it has traditionally depended on specialized networking hardware. Microsoft&\#x27;s USB blog describes this developer preview as bringing that capability over USB4, the consumer high-speed connection, so connected Windows PCs can pool memory and GPU compute without dedicated RDMA hardware. Coverage of the preview also notes that Microsoft demonstrated it across PCs from both AMD and Intel.

**「Impact」** Because the capability arrives as a Windows Insider developer preview, testing it requires machines on that channel plus USB4 connections between them; the reported ~18.5 tokens/s for the three-machine Qwen3-235B-A22B setup is the only published performance figure, so behavior with different cluster sizes, models, or mixed hardware remains unstated.

<details><summary>References</summary>
<ul>
<li><a href="https://techcommunity.microsoft.com/blog/microsoftusbblog/introducing-rdma-over-usb4%C2%AE-on-windows-run-larger-local-ai-models-across-pcs/4574602">Introducing RDMA over USB4® on Windows: run larger local AI ...</a></li>
<li><a href="https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model">Microsoft brings RDMA over USB4 to Windows, allowing multiple ...</a></li>

</ul>
</details>

**Tags**: `#Windows`, `#RDMA`, `#USB4`, `#local AI inference`, `#distributed computing`

---

<a id="item-tech-news-14"></a>
### [OpenRouter warns MiniMax prompts may be exposed to third parties](https://news.ycombinator.com/item?id=50585962) ⭐️ 7.0/10

OpenRouter has warned that prompts sent to MiniMax models through its service may have been read by third parties, according to a Telegram summary of an email notice that OpenRouter had not published on its site. Security researchers who sent prompts containing test URLs between July and October 2026 found those URLs were accessed 40 to 130 hours later. OpenRouter attributed the problem to MiniMax and forwarding providers AtlasCloud, Novita, and StreamLake, removed the “zero data retention” labels from the affected endpoints, and advised users with sensitive credentials to rotate API keys and passwords.

telegram · zaihuapd · Nov 21, 06:53

**「How OpenRouter labels retention」** OpenRouter routes model requests to a network of third-party providers and publishes provider-level data-retention categories, including zero retention and limited retention \(tool-1-1\). A zero-retention label therefore describes the endpoint&\#x27;s stated handling of prompts, which is why it can be removed when an intermediary&\#x27;s handling is called into question.

**「Impact」** Developers who sent credentials, customer data, or proprietary code in prompts to these MiniMax endpoints should treat that data as potentially exposed and rotate any affected API keys and passwords; removing the zero-data-retention label also means those routes no longer carry that assurance.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/providers">Browse the network of model providers available on OpenRouter .</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#data privacy`, `#OpenRouter`, `#MiniMax`, `#API security`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why Output Caching Barely Helps LLM Agent Costs](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** LLM inference already relies on caching inputs, especially the KV cache, to avoid recomputing conversation history. But agents also visibly repeat themselves—restating code snippets, quoting evidence documents, or reproducing sample outputs—and output tokens are much more expensive to generate than input tokens are to ingest, making output caching seem attractive.

**「Solution」** Sean Goedecke argues that caching outputs would require the model to reference earlier conversation segments instead of regenerating them, perhaps through prompting or fine-tuning, with the harness expanding those references transparently. The problem is that this optimizes only visible output. Based on his own agent histories, he estimates that visible output is about 6% of output tokens, while reasoning accounts for 50% and tool calls 44%. Under Amdahl&\#x27;s law, even saving two-thirds of visible tokens would reduce total output tokens by only about 4%. He is only moderately confident that frontier models rarely repeat themselves internally, and he flags possible repetition between reasoning and tool calls as an open question. To reduce the other 94%, the lever is model and harness intelligence: a model that costs five times more per token but needs six times fewer tokens can be cheaper overall.

**「Takeaway」** Output caching targets a small, visible slice of agent token use, so it is unlikely to produce meaningful savings. The author&\#x27;s larger point is that agent inference cost is dominated by invisible reasoning and tool calls, making model intelligence and token efficiency the more important economic lever.

**Tags**: `#LLM inference`, `#output caching`, `#token economics`, `#AI agents`, `#Amdahl&\#x27;s law`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed Officials Speak More as Warsh Withholds Rate Guidance](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Federal Reserve officials are publicly voicing support for rate increases while Chair Kevin Warsh declines to signal where policy is headed, and a Bank of America analysis found more Fed commentary in the past two weeks than in any comparable stretch since the start of 2025. Traders priced a 100% probability of at least a quarter-point hike at the December meeting, according to CME Group&\#x27;s FedWatch.

rss · CNBC Finance · Nov 20, 21:10

**「Background」** Warsh became Fed chair in 2026 and has rejected forward guidance—public hints about future policy—since his first meeting, when the Fed held rates steady with inflation above its 2% target.

**「Impact」** Bank of America economist Aditya Bhave said the public back-and-forth is producing &quot;undue rates volatility in already turbulent times,&quot; which complicates planning for rate-sensitive borrowers and investors.

<details><summary>References</summary>
<ul>
<li><a href="https://www.businessinsider.com/kevin-warsh-first-fomc-fed-meeting-interest-rates-2026-6">Fed Holds Rates Steady As Warsh Signals a Break... - Business Insider</a></li>
<li><a href="https://www.foxbusiness.com/economy/what-warshs-jackson-hole-speech-signals-about-where-interest-rates-headed">Kevin Warsh outlines hawkish PCE inflation stance at... | Fox Business</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#Kevin Warsh`

---

<a id="item-finance-news-2"></a>
### [Net U.S. Equity Issuance Reaches 3.1% of Market Value, Acadian Says](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

U.S. companies have shifted from repurchasing shares to issuing equity, with net new share issuance equal to 3.1% of total market capitalization as of late last week, according to an Acadian Asset Management analysis.

rss · CNBC Finance · Nov 20, 14:15

**「Background」** Before 2026, U.S. companies were net repurchasers of shares—buybacks that shrank the supply available to trade and helped support prices—but Acadian says that era has ended and firms are now net issuers.

**「Impact」** That added supply can weigh on U.S. equity prices by giving investors more shares to absorb and by diluting per-share earnings, a potential headwind for the bull market, according to the analysis.

<details><summary>References</summary>
<ul>
<li><a href="https://www.acadian-asset.com/investment-insights/owenomics/the-smart-money-is-selling-equity">The smart money is selling equity | Acadian Asset Management</a></li>

</ul>
</details>

**Tags**: `#equity issuance`, `#stock buybacks`, `#AI capex`, `#IPO market`, `#market liquidity`

---