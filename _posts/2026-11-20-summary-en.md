---
layout: default
title: "Horizon Summary: 2026-11-20 (EN)"
date: 2026-11-20
lang: en
---

> From 33 items, 12 important content pieces were selected

---

**Technology News**
1. [PostgreSQL 19 ships with WAIT FOR LSN for standby reads](#item-tech-news-1) ⭐️ 9.0/10
2. [Anthropic Begins Nasdaq Trading as Public Markets Test AI Valuations](#item-tech-news-2) ⭐️ 8.0/10
3. [UK tribunal forces disclosure of secret Apple encryption order](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenJDK &\#x27;java4shell&\#x27; PR Draws Oracle Takeover and Disclosure Questions](#item-tech-news-4) ⭐️ 8.0/10
5. [Gemini Can Now Operate Mac Apps for US Subscribers](#item-tech-news-5) ⭐️ 8.0/10
6. [PHP fixes mixed-case HTTPS URLs silently disabling TLS](#item-tech-news-6) ⭐️ 8.0/10
7. [OpenSSL reports EVP\_EncodeBlock\(\) buffer overflow, CVSS 9.8](#item-tech-news-7) ⭐️ 7.0/10
8. [Anthropic claims Claude solved two black-hole physics problems](#item-tech-news-8) ⭐️ 7.0/10
9. [U.S. Approved 879,868 AI Chip Exports to China in Six Months](#item-tech-news-9) ⭐️ 7.0/10
10. [Meta&\#x27;s Muse AI agent reportedly mixed conversations across accounts](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [Anthropic reportedly opens 34% above IPO price on Nasdaq](#item-finance-news-1) ⭐️ 9.0/10
2. [Asian stocks fall as AI investment doubts mount after Anthropic IPO](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [PostgreSQL 19 ships with WAIT FOR LSN for standby reads](https://www.postgresql.org/docs/release/19.0/) ⭐️ 9.0/10

PostgreSQL 19.0 has been released two months later than the usual September cadence, after the team addressed a wave of AI-reported vulnerability issues. The release adds WAIT FOR LSN, which lets a session on a standby wait until WAL replay reaches a supplied log sequence number before running a query, providing read-your-writes consistency for reads sent to replicas. Applications can store the value returned by pg\_current\_wal\_insert\_lsn\(\) and issue WAIT FOR LSN &\#x27;0/0306EE20&\#x27; WITH \(TIMEOUT &\#x27;0.1s&\#x27;\); the timeout is optional and produces an error if the standby has not caught up in time.

hackernews · linzhangrun · Nov 20, 03:45 · [Discussion](https://news.ycombinator.com/item?id=50569890)

**「Background」** Read-your-writes consistency is the guarantee that a client immediately sees data it just wrote, a problem when reads go to asynchronous standbys that may lag behind the primary. MediaWiki previously implemented a hand-rolled equivalent against MySQL replication by saving the primary binlog position and waiting for the replica to catch up; MySQL now exposes WAIT\_FOR\_EXECUTED\_GTID\_SET\(\) and SOURCE\_POS\_WAIT\(\).

**「Impact」** For teams that route reads to standbys, PostgreSQL 19 makes it possible to enforce read-your-writes per request by passing an LSN from the primary to the standby session; setting TIMEOUT turns prolonged replication lag into an error rather than waiting indefinitely.

**「Community discussion」** Hacker News commenter murkt called this “the most bug-free .0 release of Postgres” and said they normally wait for .1 or .2 before upgrading, asking whether that caution is still warranted.

**Tags**: `#PostgreSQL`, `#databases`, `#open source`, `#software release`, `#SQL`

---

<a id="item-tech-news-2"></a>
### [Anthropic Begins Nasdaq Trading as Public Markets Test AI Valuations](https://www.reuters.com/business/finance/anthropics-historic-debut-put-ais-promise-peril-wall-st-test-2026-11-19/) ⭐️ 8.0/10

Reuters reported on Nov. 19, 2026, that Anthropic made its Nasdaq debut, framing the listing as a Wall Street test of AI&\#x27;s promise and risks. The supplied item is headline-level and does not include the offer price, amount raised, valuation, or first-day trading results. It confirms the public listing but not how the shares performed or what terms investors received.

hackernews · wslh · Nov 19, 17:02 · [Discussion](https://news.ycombinator.com/item?id=50562754)

**「Background」** Anthropic is the San Francisco-based developer of the Claude models, and until this listing it had been privately held. Its $81.3 billion raise is the largest IPO on record, surpassing SpaceX&\#x27;s $75 billion market debut in June 2026, which had held the previous record.

**「Impact」** Public-market investors now have a direct, daily price for Anthropic that can be compared with the private valuations AI labs have used to raise capital. The supplied report does not include enough terms to judge whether the debut supported or undercut those private marks.

**「Community discussion」** Commenters split between valuation skepticism and career anxiety: one claimed the stock had fallen to a $1.26T valuation, below OpenAI&\#x27;s private mark, and another cited a Yahoo Finance headline calling it the worst start for a big IPO since 2008. A software engineer said the &quot;gravy train&quot; is over, while a 50-year programming veteran described the shift as the sunset of this way of making a living but said engineers who move up the food chain may still succeed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.euronews.com/2026/11/19/anthropic-shares-open-34-above-ipo-price-in-nasdaq-debut-after-record-listing">Anthropic shares open 34% above IPO price in Nasdaq debut</a></li>
<li><a href="https://www.aljazeera.com/economy/2026/11/19/anthropic-raises-81-3bn-in-biggest-ipo-of-all-time">Anthropic raises $81.3bn in biggest IPO of all time | Al Jazeera</a></li>

</ul>
</details>

**Tags**: `#AI industry`, `#Anthropic`, `#IPO`, `#software engineering careers`, `#AI valuations`

---

<a id="item-tech-news-3"></a>
### [UK tribunal forces disclosure of secret Apple encryption order](https://macanorak.com/uk-government-forced-to-admit-it-issued-apple-a-secret-encryption-order/) ⭐️ 8.0/10

A UK tribunal has forced the government to acknowledge a secret Technical Capability Notice issued to Apple demanding access to encrypted iPhone data, ruling that the Home Office can no longer keep the order confidential and that most of the case will be public. The Home Office confirmed the notice and said it was intended to help bring criminals to justice, while the tribunal judged its national security rationale &quot;impractical.&quot; The notice&\#x27;s technical contents remain secret for now, so the scope of what Apple was asked to do is not publicly established.

hackernews · Terretta · Nov 19, 16:21 · [Discussion](https://news.ycombinator.com/item?id=50562113)

**「What a technical capability notice is」** At issue is a technical capability notice \(TCN\), a secret UK instrument that can compel a communications provider to take technical steps—here, to give authorities access to encrypted iPhone data. Because TCNs are meant to operate confidentially, the tribunal first had to decide whether the government could keep even the order’s existence secret; it ruled that most of the case must be heard publicly, while the notice’s contents remain undisclosed.

**「Impact」** Because the notice&\#x27;s technical scope remains undisclosed, iPhone users and organizations relying on Apple&\#x27;s encryption guarantees still cannot verify whether those protections were affected; the public tribunal proceedings are the next point at which those details could emerge.

**「Community discussion」** Commenters questioned whether the disclosure is meaningful, with one saying the UK has long disregarded privacy and another asking why the order matters after earlier claims about Apple and the NSA. A technical argument held that Apple&\#x27;s wording has shifted from saying not even Apple can access user data to saying Apple cannot, raising doubts about whether device-held keys protect more than a key-encryption layer.

**Tags**: `#encryption`, `#privacy`, `#uk-government`, `#apple`, `#surveillance`

---

<a id="item-tech-news-4"></a>
### [OpenJDK &\#x27;java4shell&\#x27; PR Draws Oracle Takeover and Disclosure Questions](https://github.com/openjdk/jdk/pull/32781) ⭐️ 8.0/10

A reported OpenJDK vulnerability nicknamed “java4shell” is under discussion in a pull request, with Oracle reportedly taking over the change. According to comments, the PR author said in a linked Adoptium support issue that Oracle asked them not to proceed until approval and later that the work had been taken over by Oracle. The available material does not establish affected Java versions, severity, or exploit details.

hackernews · notmine1337 · Nov 19, 11:47 · [Discussion](https://news.ycombinator.com/item?id=50558906)

**「Background」** Java4Shell is tracked as CVE-2026-114938, a heap overflow in OpenJDK&\#x27;s Base64 decoder that external analyses say can crash the JVM, expose memory, or enable remote code execution. Oracle and the OpenJDK Vulnerability Group released fixes on November 17, 2026; coverage lists Java 17.0.6 and later on certain x86-64 systems as affected, with disabling the affected optimization as a temporary mitigation.

**「Remediation for affected Java builds」** External reports identify CVE-2026-114938 as a Base64-decoder flaw enabling remote code execution in Java 17, 21, 25, and 27, with Java 17.0.6+ on certain x86-64 systems specifically affected. Teams on those builds should apply the vendor fixes released on November 17, 2026, or, if they cannot upgrade immediately, disable the affected optimization as a temporary mitigation.

**「Community Discussion」** Commenters point to earlier reports in the linked Adoptium issue—a June SIGSEGV report and a September isolation to Base64—and to the PR author’s October statements about Oracle’s request to pause and later takeover. One commenter says they independently found and reported the issue to Oracle, while others speculate that an LLM-assisted rediscovery may have seen the earlier public report; no supplied evidence confirms that.

<details><summary>References</summary>
<ul>
<li><a href="https://www.dynatrace.com/news/blog/java4shell-cve-2026-114938-which-java-runtimes-are-affected-and-how-to-fix-them/">Java4Shell (CVE-2026-114938): Affected Java Versions &amp; fixes</a></li>
<li><a href="https://pentest-tools.com/blog/java4shell-cve-2026-114938">Java4Shell (CVE-2026-114938): affected versions and fixes</a></li>
<li><a href="https://cybersecuritynews.com/java4shell/">Critical Java4Shell Flaw Lets Hackers Execute Code Without ...</a></li>
<li><a href="https://cycode.com/blog/java4shell-cve-2026-114938/">Java4Shell (CVE-2026-114938): Affected Versions, How to Check ...</a></li>
<li><a href="https://www.dynatrace.com/news/blog/java4shell-cve-2026-114938-which-java-runtimes-are-affected-and-how-to-fix-them/">Java4Shell (CVE-2026-114938): Affected Java Versions &amp; fixes</a></li>

</ul>
</details>

**Tags**: `#Java`, `#OpenJDK`, `#security vulnerability`, `#RCE`, `#responsible disclosure`

---

<a id="item-tech-news-5"></a>
### [Gemini Can Now Operate Mac Apps for US Subscribers](https://www.bloomberg.com/news/articles/2026-11-19/google-s-gemini-can-now-control-mac-devices-on-users-behalf) ⭐️ 8.0/10

Google&\#x27;s Gemini can now perform desktop actions on Mac—clicking, typing, navigating menus, and filling forms—for US users with a Google AI Plus, Pro, or Ultra subscription who use the Mac app. The feature runs in a separate background window, lets users restrict which apps Gemini can access, supports real-time monitoring and pausing, and requires approval before key actions. The source provides no technical details or independent evaluation of reliability or security.

telegram · zaihuapd · Nov 20, 02:51

**「Background」** Desktop agents go beyond chat-based assistants by translating a goal into concrete interface actions—clicks, keystrokes, menu choices, and form entries—rather than only producing text. That makes oversight mechanisms such as app restrictions, live monitoring, pause controls, and approval before sensitive steps part of the feature’s basic design rather than an add-on.

**Tags**: `#AI agents`, `#Google Gemini`, `#desktop automation`, `#macOS`, `#human-in-the-loop`

---

<a id="item-tech-news-6"></a>
### [PHP fixes mixed-case HTTPS URLs silently disabling TLS](https://x.com/ljachowicz/status/2123477025268924514) ⭐️ 8.0/10

PHP&\#x27;s HTTP/FTP stream wrappers silently disable TLS for scheme spellings such as &\#x27;HTTPS://&\#x27;, &\#x27;httpS://&\#x27; and &\#x27;FTPS://&\#x27;, sending credentials, cookies, POST bodies and FTP logins in plaintext, including after third-party redirects. The flaw, tracked as CVE-2026-128064 \(GHSA-f6gg-rchx-xw8j\) with a CVSS 4.0 score of 8.2, is fixed in PHP 8.2.36, 8.3.37, 8.4.28, 8.5.13 and 8.6.0. PHP 8.1 and earlier are EOL and will not receive a fix; affected users can mitigate by normalizing URL schemes to lowercase.

telegram · zaihuapd · Nov 20, 03:04

**「Background」** PHP&\#x27;s HTTP and FTP stream wrappers are the built-in handlers that functions such as file\_get\_contents\(\) and fopen\(\) use when given a URL, so their parsing behavior affects ordinary application code and third-party libraries rather than only explicit socket calls. URL schemes are conventionally case-insensitive, but these wrappers recognized the scheme that way while enabling TLS only for a lowercase &quot;s&quot; at a fixed position.

**「Impact」** Applications that pass user-supplied or redirect-derived URLs to PHP&\#x27;s HTTP/FTP wrappers should upgrade to a fixed release or normalize the scheme to lowercase, because otherwise credentials and request bodies can be exposed to network observers.

<details><summary>References</summary>
<ul>
<li><a href="https://everycve.com/CVE-2026-128064">CVE - 2026 - 128064 : Mixed-case HTTPS and FTPS URLs can expose...</a></li>

</ul>
</details>

**Tags**: `#PHP`, `#security vulnerability`, `#TLS`, `#CVE`, `#open source`

---

<a id="item-tech-news-7"></a>
### [OpenSSL reports EVP\_EncodeBlock\(\) buffer overflow, CVSS 9.8](https://github.com/openssl/openssl/pull/33652) ⭐️ 7.0/10

A pull request in the OpenSSL repository discloses CVE-2026-121481, a buffer overflow in EVP\_EncodeBlock\(\), the API used for base64 encoding, and assigns it a CVSS score of 9.8. Commenters reading the change say the overflow occurs only when the input is larger than roughly 1.5 GB, because EVP\_EncodeBlock takes no output-buffer length argument and instead requires callers to compute the required size from a nontrivial formula, leaving the implementation unable to validate it. The item as supplied does not state which OpenSSL versions are affected, whether a fix has been released, or how untrusted input would reach the function.

hackernews · JacobHenner · Nov 20, 02:01 · [Discussion](https://news.ycombinator.com/item?id=50569226)

**「Background」** OpenSSL&\#x27;s EVP\_EncodeBlock\(\) is the library&\#x27;s base64 encoder, and base64 expands data by roughly one third, so callers must allocate an output buffer large enough for the encoded result. According to the CVE listing, CVE-2026-121481 is a heap buffer overflow in the function&\#x27;s output sizing that occurs when an input is long enough that its encoded size does not fit in an int; the same listing says OpenSSL 4.1.0 is affected and fixed in 4.1.1, while 4.0.0 through 4.0.3 are fixed in 4.0.4.

**「Who is actually exposed」** The exposed class is code that base64-encodes unbounded, attacker-supplied data in a single EVP\_EncodeBlock\(\) call: as commenters noted, the function accepts no output-buffer length, so the implementation cannot validate the write itself, and it malfunctions once input exceeds roughly 1.5 GB. Applications whose input arrives behind a length-bounded protocol field fall outside that path, so teams should first confirm whether untrusted input can reach a single-call encode, and otherwise cap the input size or move to the streaming EVP\_EncodeUpdate\(\) API. Language bindings that wrap the call directly — HsOpenSSL&\#x27;s encodeBase64, for example — inherit the same assumption that the caller has already sized the output buffer correctly.

**「Community discussion」** Commenters disputed the 9.8 rating: one argued the bug is nowhere near as serious as Heartbleed and that exploitability hinges on whether untrusted input can arrive at a length in the gigabyte range, while another said the real defect is the API design that forces callers to size the output buffer themselves. Others asked whether the flaw had been demonstrated with a working exploit; no one in the thread reported one.

<details><summary>References</summary>
<ul>
<li><a href="https://cve.now/CVE-2026-121481">CVE-2026-121481: OpenSSL overflow in EVP_EncodeBlock ()</a></li>
<li><a href="https://hackage.haskell.org/package/HsOpenSSL-0.11.4/docs/src/OpenSSL-EVP-Base64.html">OpenSSL / EVP / Base 64 .hs</a></li>

</ul>
</details>

**Tags**: `#OpenSSL`, `#CVE-2026-121481`, `#buffer overflow`, `#security vulnerability`, `#base64 encoding`

---

<a id="item-tech-news-8"></a>
### [Anthropic claims Claude solved two black-hole physics problems](https://www.anthropic.com/research/claude-black-hole-physics) ⭐️ 7.0/10

Anthropic’s research post claims that Claude solved two open problems in black-hole physics, a result that drew substantial Hacker News discussion. Commenters describe the first as a complex and error-prone calculation and the second—proving an upper limit on black-hole mass consistent with a given central charge—as the more notable claim. The supplied material contains no paper text or independent verification, so the results remain vendor claims rather than confirmed scientific findings.

hackernews · cybermango · Nov 19, 17:30 · [Discussion](https://news.ycombinator.com/item?id=50563148)

**「Background」** Anthropic&\#x27;s post frames the work around the “bootstrap” method, in which consistency conditions—rather than direct force laws—constrain which quantum-gravity theories can exist. Anthropic reports that Claude derived a ceiling on black-hole mass for a given central charge, written M₁ ≤ c/Λ; the calculation concerns the simplest, most-studied version of the method, which ignores black-hole spin.

**「Consistency check, pending verification」** For theorists working on holographic quantum gravity, the practical value of the second result is a consistency filter: as one commenter reads it, the paper establishes an upper bound on black-hole mass for a given central charge, so any candidate theory predicting a heavier black hole in that setting would be excluded. That consequence only holds if the derivation survives scrutiny, and the supplied material reports no independent verification of the proofs — a physicist cited in the discussion independently ran Claude on the same problem, but that is not the same as checking Anthropic&\#x27;s argument, so groups building on the bound would need to verify it first.

**「Community discussion」** Physicist commenter turzmo cautioned that theoretical physics contains a near-infinite number of “open problems” and that solving one does not mean physicists worldwide would treat it as a major result, while chunky1994 argued the second result is “much much cooler” than the first. steinwinde also noted that the PDF and related material give no attribution beyond Claude/Anthropic.

<details><summary>References</summary>
<ul>
<li><a href="https://www.anthropic.com/research/claude-black-hole-physics">Claude Fable 5.2 solves two open problems in the physics of black ...</a></li>
<li>Claude solves two open problems in the physics of black holes | Hacker News</li>

</ul>
</details>

**Tags**: `#AI for science`, `#physics`, `#Claude`, `#LLM reasoning`, `#research claims`

---

<a id="item-tech-news-9"></a>
### [U.S. Approved 879,868 AI Chip Exports to China in Six Months](https://foreignaffairs.house.gov/news/press-releases/chairman-brian-mast-exercises-legislative-authority-to-publicly-release-ai-chip-license-information-for-china) ⭐️ 7.0/10

Documents released by the U.S. House Foreign Affairs Committee show that from December 2025 through May 2026 the U.S. approved 879,868 Nvidia and AMD AI chips for export to China, including H200 and MI325X models, out of 3.444 million chips applied for. Approved recipients include Tencent and ByteDance at 150,000 chips each; Alibaba, Kuaishou and Didi at 75,000 each; and miHoYo, Baidu and JD, among others. The committee highlighted that Alibaba, Tencent, Baidu and BYD appear on a U.S. list of firms linked to China&\#x27;s military, and that 21 approved licenses showed no shipments as of May 11, so approvals do not equal deliveries.

telegram · zaihuapd · Nov 20, 04:25

**「Background」** U.S. export controls require chipmakers to obtain government licenses before shipping advanced AI accelerators to China, so disclosed approval totals reflect cleared applications rather than completed sales. A license can be granted while goods remain unshipped, meaning such figures do not by themselves measure actual exports.

**「Impact」** The release puts the names and approved quantities for Tencent, ByteDance, Alibaba and other Chinese buyers on the public record, exposing them to congressional scrutiny over military-linked designations even though the licenses had not shipped.

**Tags**: `#AI chips`, `#export controls`, `#US-China tech`, `#NVIDIA/AMD`, `#semiconductor policy`

---

<a id="item-tech-news-10"></a>
### [Meta&\#x27;s Muse AI agent reportedly mixed conversations across accounts](https://techcrunch.com/2026/11/19/metas-ai-agent-muse-is-mixing-up-conversations-and-exposing-private-data-report-says/) ⭐️ 7.0/10

Meta employees reported that the company&\#x27;s AI assistant Muse mixed conversations across accounts and exposed private data, including bank balances and Signal messages, according to Reuters&\#x27; account of internal Meta posts cited by TechCrunch. Employees described seeing parenting requests, career advice and orders they had not made, and one post showed Muse inserting Capital One and Charles Schwab balances—$2,722.58 and $5,899.57—into a weather chat. Another employee said Muse, running on her personal phone, prompted her to reply to her sister&\#x27;s Signal message even though she had not authorized access to other apps. The claims come from internal posts and were not independently verified in the supplied material.

telegram · zaihuapd · Nov 20, 05:10

**「Background」** Muse is Meta&\#x27;s AI assistant, which the company has promoted as &quot;built from the ground up for privacy and security.&quot; Ars Technica reported in September 2026 that the assistant, described as extraordinarily privileged, had a serious 0-day vulnerability, an earlier sign that its broad access carried security risk. The current report concerns a different failure mode: conversations and personal data surfacing in other people&\#x27;s accounts rather than an outside attacker exploiting a flaw.

**「Impact」** For affected users, the reported behavior undermines the expectation that an AI assistant stays within one account and accesses only apps a user has authorized: bank balances and Signal messages appeared in conversations they did not initiate. It also gives Meta a specific area to audit—cross-account conversation routing and the permissions Muse uses to read other apps—before employees or users trust it with connected personal data.

<details><summary>References</summary>
<ul>
<li><a href="https://arstechnica.com/security/2026/09/muse-metas-extraordinarily-privileged-ai-assistant-has-a-serious-0-day/">Muse , Meta &#x27;s extraordinarily privileged AI assistant ... - Ars Technica</a></li>

</ul>
</details>

**Tags**: `#AI agents`, `#privacy`, `#Meta`, `#data leakage`, `#trust and safety`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Anthropic reportedly opens 34% above IPO price on Nasdaq](https://www.cls.cn/detail/2539480) ⭐️ 9.0/10

Anthropic reportedly began trading on Nasdaq at $111.50 a share, 34% above its $83 initial public offering price, giving it a market value of about $1.5 trillion at that price. The IPO and a simultaneous $26 billion private placement with strategic investors including Google, Nvidia and Microsoft totaled about $107.3 billion, according to a CLS report relayed on Telegram.

telegram · zaihuapd · Nov 19, 16:56

**「Background」** Anthropic priced the shares at $83, above an earlier expected range of $70–$78; Yahoo Finance reported the offering surpassed SpaceX as the largest-ever public offering, and the $1.5 trillion figure is a fully diluted valuation that falls to about $1.1 trillion on a non-diluted basis.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/ai/articles/anthropic-announces-price-83-per-234507433.html?fr=sycsrp_catchall">Anthropic announces price of $83 per share for IPO Anthropic valued at $1.5 trillion as IPO raises record $81 ... Anthropic hits Nasdaq exchanges at $111, 33% above IPO price Anthropic begins trading on Nasdaq, tops SpaceX for biggest ... Anthropic to begin trading after pricing its stock at $83 per ...</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#IPO`, `#Nasdaq`, `#AI financing`, `#private placement`

---

<a id="item-finance-news-2"></a>
### [Asian stocks fall as AI investment doubts mount after Anthropic IPO](https://www.bloomberg.com/news/articles/2026-11-19/stock-market-today-dow-s-p-live-updates) ⭐️ 7.0/10

Asian stocks fell, with the MSCI Asia-Pacific index down 1.7% for a seventh straight session, as doubts over returns on AI spending intensified after Anthropic’s IPO; Anthropic shares fell more than 5% after hours to below $92.

telegram · zaihuapd · Nov 20, 01:58

**「Background」** The selloff followed Anthropic’s record Nasdaq debut on Nov 19, when the AI developer raised $81.3 billion and its shares opened at $111.50, 34% above the $83 IPO price.

**「Impact」** The selloff hit semiconductor and AI-linked shares: Tokyo Electron fell 7.19%, SK Hynix 6% and Samsung Electronics 4.7%, while SoftBank—which has invested $64.6 billion in OpenAI—has fallen 31% this month.

<details><summary>References</summary>
<ul>
<li><a href="https://www.euronews.com/2026/11/19/anthropic-shares-open-34-above-ipo-price-in-nasdaq-debut-after-record-listing">Anthropic shares open 34% above IPO price in Nasdaq... | Euronews</a></li>

</ul>
</details>

**Tags**: `#Asian markets`, `#AI investment`, `#semiconductors`, `#Anthropic IPO`, `#market selloff`

---