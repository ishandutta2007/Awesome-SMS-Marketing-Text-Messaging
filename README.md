# Awesome-SMS-Marketing-Text-Messaging

## Top SMS Marketing & Text Messaging Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Bulk Campaigns, OTP Delivery & Self-Hosted Messaging Infrastructure*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **SMS Marketing & Text Messaging**. These tools enable businesses to send promotional campaigns, transactional notifications, and two-way conversations at scale—turning text messaging from a manual process into an automated, measurable revenue channel.



**Examples** include HubSpot SMS Marketing, Klaviyo SMS, Attentive, Postscript, SimpleTexting, EZ Texting, SlickText, Twilio, TextMagic, and Podium (the category leaders).



**Open-source emphasis**: SMS Marketing & Text Messaging is a domain where open-source tooling is **surprisingly capable at the infrastructure and delivery layers but almost non-existent as a complete marketing platform**. **Chorus** (cntm-labs) is the strongest open-source CPaaS—a Rust-based platform with waterfall routing (email first, SMS fallback for 60-80% cost savings), multi-provider failover across Telnyx/Twilio/Plivo, template engine, webhooks, SDKs in six languages, and MIT licensing for self-hosting . **MessageLane** provides a consent-aware SMS campaign service with contact imports, rate-limited sends, delivery records, and MCP tools—but explicitly does not provide carrier delivery; you connect your own gateway . **vsms** offers a Cameroon-first A2P SMS gateway with schema-driven Rust services, OIDC security, multi-provider HTTP/SMPP delivery, and PostgreSQL workers . **termux-bulk-sms** is a niche but functional tool for sending personalized SMS from an Android phone via Termux, with CSV imports, campaign management, and a local web UI . The critical gap: **no open-source project replicates the marketing automation depth** of Klaviyo SMS (AI Customer Agent, product recommendations, Shopify integration) or Attentive (two-tap opt-in, product affinity segments, journey analytics) . Open-source covers the pipes, not the marketing brain.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-products)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[HubSpot SMS Marketing](https://www.hubspot.com/)**  

  SMS capabilities within HubSpot's Marketing Hub; send promotional texts tied to CRM contact records and workflows, with opt-in management and attribution to deals.



- **[Klaviyo SMS](https://www.klaviyo.com/)**  

  SMS marketing within Klaviyo's data platform; features **Customer Agent** (AI assistant that responds to inbound SMS 24/7, recommends products, and resolves FAQs with cost guardrails), deep Shopify integration, segmentation, and flows . Requires an active SMS plan; SHAFT brands cannot activate Customer Agent.



- **[Attentive](https://www.attentive.com/)**  

  Enterprise SMS marketing platform; Q3 2026 release adds **Product Affinity Segments** (dynamic audiences based on browsing interests), **two-tap™ opt-in** (pre-filled text message reduces invalid numbers), subscriber list uploads, channel ROAS reporting, and journey analytics with exit-rule visibility . Billini case study: 19.4% reduction in invalid records and 67% higher SMS sign-up rate in A/B test .



- **[Postscript](https://postscript.io/)**  

  SMS marketing for Shopify brands; Q1 2026 adds advanced discounting (stackable offers, Buy X Get Y), RCS support (calendar events, video, webviews), landing pages with scratch-off gamification, and UTM tracking for popups . Professional plan at $500/month drops per-message rate from $0.009 to $0.007—pays for itself at 250,000 messages .



- **[SimpleTexting](https://simpletexting.com/)**  

  SMS marketing and two-way messaging for businesses; mass SMS/MMS campaigns, drip automations, text-to-join keywords, and a mobile app for managing conversations .



- **[EZ Texting](https://www.eztexting.com/)**  

  SMS marketing platform with bulk sending, autoresponders, and integrations; positioned for small to mid-sized businesses.



- **[SlickText](https://www.slicktext.com/)**  

  SMS marketing with segmentation, automation, and a mobile app; focused on ease of use for growing businesses.



- **[Twilio](https://www.twilio.com/)**  

  The **developer API infrastructure** for SMS; Programmable Messaging REST API and SDKs for Python, Node.js, PHP, C#, Java, Go, and Ruby . Not a marketing platform—you build campaigns and automation on top of Twilio's delivery network.



- **[TextMagic](https://www.textmagic.com/)**  

  Business texting platform with an **MCP Connector** (September 2026) enabling Claude, ChatGPT, or any MCP-compatible AI to send SMS, schedule recurring sends, check replies, and manage contacts via natural language with OAuth and explicit send confirmation .



- **[Podium](https://www.podium.com/)**  

  Local business communications platform; inbox consolidating texts, reviews, social messages, and calls; bulk messaging with 98% open rate; payments via text; review invitations . Positioned for small local businesses rather than ecommerce DTC.



## Open-Source GitHub Projects



### CPaaS & Delivery Infrastructure



- **[Chorus (cntm-labs)](https://github.com/cntm-labs/chorus)**  

  The most complete open-source **Communications Platform as a Service** available (Rust/Axum, MIT) . Features: **waterfall routing** (email first via Resend free tier, SMS fallback only when needed—saving 60-80% cost), **multi-provider failover** across Telnyx, Twilio, Plivo (SMS) and Resend, AWS SES, Mailgun, SMTP (email), template engine with OTP generation, **batch send**, webhooks with HMAC-SHA256 signatures, **SDKs in Rust, TypeScript, Java, Go, Python, C**, Stripe billing integration, Prometheus metrics, and test mode (`ch_test_` keys). **Self-hosted is free with no billing**. **The strongest open-source foundation for OTP and notification delivery**—but it is infrastructure, not a marketing campaign platform with segmentation or journeys.



- **[MessageLane (talocode)](https://pypi.org/project/talocode-messagelane/)**  

  Open-source **SMS campaign service** for consent-aware contact imports, rate-limited sends, delivery records, CLI, HTTP API, and **MCP tools** (Python SDK) . **Critical design**: MessageLane explicitly **does not provide carrier delivery**—you connect an approved gateway (Twilio, etc.) and are responsible for consent, sender-ID approval, and DND compliance. Features: contact import with consent flag, campaign creation and dry-run, delivery reports. **Best for teams wanting campaign operations portability** while keeping delivery gateway separate—but it is not a turnkey marketing platform.



- **[vsms (vaam-apps)](https://github.com/vaam-apps/vsms)**  

  Cameroon-first **A2P SMS gateway** for OTPs and notifications (Rust) . Features: schema-driven Rust services, OIDC security, **multi-provider HTTP/SMPP delivery** (Orange Cameroon, MTN adapters), DLRs, signed webhooks, fault-tolerant PostgreSQL workers, GSM 03.38 vs UCS-2 encoding analysis, E.164 parsing, and fault-injecting fakes for testing. **Region-specific**—best for organizations operating in Cameroon or wanting a reference architecture for A2P gateway design.



### Android-Based Bulk SMS



- **[termux-bulk-sms (Logicbloke)](https://pypi.org/project/termux-bulk-sms/)**  

  Open-source **personalized bulk SMS from an Android phone** via Termux:API (Python, stdlib only) . Features: paste CSV, write message with `[name]` placeholders, set delay, press start; **campaigns** (Fixed or Ongoing), duplicate/blocklist prevention, remote lookup to skip known numbers, local web UI with password, configurable send windows (08:00–21:00 default), SIM slot for dual-SIM, and max consecutive failure auto-pause. **Niche**—for small-scale, phone-based sending without carrier APIs; not suitable for enterprise volume or compliance-heavy campaigns.



### Additional Strong Open-Source Options



- **No open-source equivalent to Klaviyo SMS or Attentive exists** — The AI Customer Agent (inbound SMS answering, product recommendations, cost guardrails) , two-tap™ opt-in , and product affinity segments  are commercial differentiators with no open-source replication. Chorus and MessageLane cover delivery and campaign operations, but not the marketing intelligence layer.

- **No open-source platform handles carrier compliance (10DLC, toll-free verification, opt-out keywords) as a managed service** — these remain operational responsibilities that commercial platforms absorb.



**Frameworks for building custom systems**: For **OTP and notification delivery with cost optimization**, Chorus provides the most complete open-source CPaaS with waterfall routing and multi-provider failover . For **campaign operations with gateway portability**, MessageLane separates consent-aware campaign management from delivery . For **Android-based small-scale sending**, termux-bulk-sms . For **marketing automation depth** (segmentation, AI responses, product recommendations), no open-source option exists—organizations requiring that should evaluate Klaviyo SMS, Attentive, or Postscript.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- SMS marketing platforms handling phone numbers and consent data must comply with applicable regulations (TCPA in the US, GDPR in the EU, CASL in Canada, and local anti-spam laws); **express opt-in consent, clear opt-out mechanisms (STOP keywords), and sender identification are legally required** in most jurisdictions.

- **Open-source SMS is mature at the delivery and CPaaS layer but absent at the marketing automation layer**—Chorus provides production-grade multi-provider delivery , and MessageLane provides consent-aware campaign operations . However, **no open-source project replicates the AI Customer Agent, two-tap™ opt-in, or product affinity segments** of Klaviyo SMS or Attentive . Organizations requiring marketing automation depth should evaluate commercial platforms.

- Verify license terms for commercial use; Chorus uses MIT , and MessageLane is MIT .



---



**Made for marketing teams, developers building messaging infrastructure, and businesses choosing their SMS platform.**  

Let's make SMS marketing more open at the delivery layer, but with clear eyes about the marketing automation and carrier compliance gaps that commercial platforms still fill.
