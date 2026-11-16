# Vultr reviews: why G2 shows 4.3/5 while Trustpilot fills with 1-star warnings, what the $300 credit really requires, and which plan fits (full price table)

Vultr's compute reviews well. Its account system reviews badly. G2 has the platform at **4.3 out of 5 across 288 reviews**, and the praise is specific: instances deploy in under two minutes, the Terraform provider holds up, a 72-core box with 512GB of RAM is a few clicks away. Trustpilot is a wall of one-star posts about suspended accounts, deposits that never come back, and tickets that sat unanswered for days.

Both describe the same company. What separates the two experiences has little to do with hardware and a lot to do with whether the customer ever needed a human. Buy a small VM, break it yourself, rebuild it, and Vultr is one of the cheapest competent options available. Get flagged by the fraud system on a Saturday, or deposit four figures for GPU capacity, and the experience drops off a cliff.

The **$300 credit** that probably brought you here is real — it sits on Vultr's own coupon page under the code `FLY300VULTR`. Getting that credit to actually pay for something involves a card-linking charge, a deposit and product gating that most review roundups skip. That's the middle of this article.

## Which Vultr plan should you start on?

Most people reading Vultr reviews are pricing one small server: a blog, a staging environment, a Docker host, a self-hosted automation tool, maybe a VPN endpoint. For that, the entry Cloud Compute tiers are plenty, and paying more buys capacity you won't use.

> **Quick pick:** Cloud Compute Regular at **$3.50/month** — 1 vCPU, 0.5 GB RAM, 10 GB storage, 0.5 TB bandwidth, IPv4 included. Drop to **$2.50/month** if the workload is IPv6-only and disposable. Move up to **$6/month High Frequency** (1 vCPU, 1 GB RAM, 32 GB NVMe) when a CMS or a small game server needs NVMe and faster cores.
> 👉 [Start on the $3.50 Cloud Compute plan](https://www.vultr.com/pricing/?ref=9738262-9J)

A G2 reviewer describes the same calculus from the other end: "I can spin up really small servers that could cost as low as $5 a month or even $2.5 for tiny servers… I can test it and then destroy the server after that." If your pattern is create, test, destroy, the cheapest tier is the correct tier.

## Vultr plans and prices: the full lineup

Vultr prices every family by the hour and caps the monthly bill at the plan rate, so a server you destroy after 40 hours costs roughly 40 hours' worth. Prices below are the entry configuration in each family; every family scales up to much larger shapes on the pricing page.

| Plan family | Entry configuration | Price | Billing | Link |
| --- | --- | --- | --- | --- |
| Cloud Compute – Regular (IPv6-only) | 1 vCPU, 0.5 GB RAM, 10 GB storage, 0.5 TB transfer | $2.50/mo | Hourly, monthly cap | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Cloud Compute – Regular (IPv4) | Same as above, IPv4 included | $3.50/mo | Hourly, monthly cap | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Cloud Compute – High Performance | 1 vCPU, 1 GB RAM, 25 GB NVMe, 2 TB transfer | $6.00/mo | Hourly, monthly cap | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Cloud Compute – High Frequency | 1 vCPU, 1 GB RAM, 32 GB NVMe, 1 TB transfer | $6.00/mo | Hourly, monthly cap | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Optimized – CPU Optimized | 1 vCPU, 2 GB RAM, 25 GB NVMe, 4 TB transfer | $28.00/mo | Hourly, monthly cap | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Optimized – General Purpose | 1 vCPU, 4 GB RAM, 30 GB NVMe, 4 TB transfer | $30.00/mo | Hourly, monthly cap | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Optimized – Memory Optimized | 1 vCPU, 8 GB RAM, 50 GB NVMe, 5 TB transfer | $40.00/mo | Hourly, monthly cap | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Optimized – Storage Optimized | 1 vCPU, 8 GB RAM, 150 GB NVMe, 4 TB transfer | $75.00/mo | Hourly, monthly cap | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Bare Metal (CPU) | 4 cores / 8 threads, 32 GB RAM, 480 GB SSD, 5 TB transfer | $120.00/mo | Monthly | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Bare Metal (GPU, L40S) | 8× NVIDIA L40S 48 GB, 2 TB RAM | ~$0.848 per GPU-hour | Hourly | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Cloud GPU (H100) | 8× NVIDIA H100, 2 TB RAM, 32 TB NVMe | $13,432/mo | 36-month reserved, prepaid | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Block Storage | 10 GB minimum, $0.10/GB beyond | from $1.00/mo | Monthly | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Object Storage | S3-compatible, base quota plus $0.018/GB overage | from $18.00/mo | Monthly | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Managed Database | Single-node starter (MySQL, PostgreSQL, Redis) | from $15.00/mo | Monthly | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Kubernetes Engine (VKE) | Control plane options differ between standard and HA tiers; worker nodes billed separately | Varies by tier | Monthly | [ Pricing](https://www.vultr.com/pricing/?ref=9738262-9J) |

Two things about that table matter more than the rows.

**The H100 number is not a flexible price.** It's a 36-month, fully prepaid reserved contract. Shorter commitments cost more per hour, and on-demand GPU capacity shows up when it shows up. Anyone budgeting $13,432 as a monthly line item without reading the contract terms is going to have a bad quarter.

**GPU billing uses a 730-hour month, not the 672-hour cap applied to standard compute.** An H100 box left running all month bills about 58 more hours than a CPU instance would. On a $13,432 plan that's not a rounding error.

### What the plan price leaves out

Bandwidth overage runs **$0.01/GB** and is the most common source of surprise charges. Snapshots cost **$0.05/GB/month and keep billing after you destroy the source instance** — a detail that catches people who snapshot, tear down, and assume the bill followed. DDoS protection is opt-in at **$10/month per IP**, not something switched on for you.

Storage is billed independently of compute. Stop the VM, keep paying for the disk.

👉 [Compare the $6 High Frequency and $3.50 Regular plans side by side](https://www.vultr.com/pricing/?ref=9738262-9J)

## What reviewers consistently praise

**Deployment speed and console design.** The line that shows up in review after review is some version of "it just works in a couple of minutes." One G2 user put numbers on it: spinning up either a 72-core/512GB machine or a 512MB one takes under two minutes, and "the initial setup was very easy too." A TrustRadius reviewer who migrated off Azure said the difference was setting up an environment "in a couple minutes, not a whole day of research."

**API and infrastructure-as-code.** "We use the Vultr Terraform provider to automate our entire stack, and it works flawlessly," one G2 reviewer wrote. TrustRadius reviewers describe the API as "easy to use and well-documented" for spawning and destroying nodes on demand. For teams that never open the web console, this is the feature that decides the purchase.

**Image library and IP reputation.** Ubuntu LTS, LAMP stacks, OpenVPN and a long list of other images can be selected at creation, which skips the clean install. Multiple long-term TrustRadius users specifically call out clean IP reputation as the reason they host email on Vultr — a rarity among budget providers.

Cost is the fourth recurring theme, with a caveat on the numbers. Vultr's marketing claims customers save "up to 90%" versus hyperscalers. A G2 reviewer reports roughly **40% monthly savings** against their previous hyperscaler setup. TrustRadius's US page states that **59% of its 31 US reviewers** report significant savings versus alternatives. Treat 90% as a ceiling from a sales page and 40% as a figure from someone who actually moved a workload.

## What reviewers consistently complain about

**Support, when the problem is account-level.** Vultr offers email and help-desk tickets plus a knowledge base. No phone, no live chat, standard business hours. For routine tickets this is fine — TrustRadius reviewers call the support "top tier," "responsive and helpful," and one eight-year customer says "their support is always there." The failure mode is specific: risk, verification, suspension, refunds. One G2 reviewer describes being flagged for credit verification during a weekend hackathon, which locked API key configuration and even the Load Balancer UI, with no path to resolution until business hours resumed. A Trustpilot reviewer reports more than eight hours of silence broken only by template replies telling them not to submit duplicate tickets. Another names an agent who spent days requesting information already supplied.

Rated honestly: routine tickets get answered, account actions get stuck in a queue, and the queue doesn't run on weekends.

**Scaling down is harder than scaling up.** TrustRadius's US review page lists "difficulty in easily downscaling deployed machines" as a named drawback. Upgrading from the admin console is straightforward; going back down is not. If you over-provision for a launch and expect to shrink afterwards, plan for a rebuild instead of a resize.

**Missing pieces that show up mid-project.** No webhooks — integrations have to poll, which one TrustRadius reviewer sums up as "we rely a lot on polling, which sucks." No VPN or WAF product of its own. No regions in the Middle East or Africa, and no SIP trunk support, which rules out running a communications platform on it. One Trustpilot user reports being throttled to 200–250 Mbps down after requesting a BGP session, with upload left at roughly 1 Gbps.

**Self-managed means nobody is watching your firewall.** This is the complaint that matters most and gets discussed least. From a G2 reviewer: "Unlike managed providers, Vultr won't warn you if your firewall is misconfigured or if your OS is out of date. If you get hacked due to a simple oversight, the solution is often just to null-route your IP (take you offline) until you fix it yourself."

Read that twice if you're a small team with no sysadmin. The failure mode isn't a slow ticket. It's your IP being pulled offline while you work out what happened.

## The $300 credit: the real path from signup to a running instance

Vultr's coupon page currently lists four new-customer offers:

- `VULTRMATCH` — Vultr matches your first deposit dollar for dollar, up to $100
- `FLY300VULTR` — $300 in free credit
- `250VULTRFLY` — $250 in free credit
- `FLYTWOHUNDRED` — $200 in free credit

The terms are identical across all four: promotional credit applies to select products only, cannot be combined with other offers, new customers only, restrictions and terms apply. There's also a separate free-tier programme you apply for rather than enrol in automatically.

What the coupon page doesn't tell you is what users report about getting the credit to work.

**A card-linking charge, then a deposit.** Multiple independent Trustpilot complaints describe the same sequence: a **$5 card-linking deposit** at registration, then a **$50 deposit** before instance creation unlocks. One reviewer who deposited $5 expecting GPU access found out about the $50 requirement afterwards and called it a bait-and-switch. A Reddit thread on the same subject frames the $50 as a legitimacy check: the $300 is trial credit for the month, and the deposit verifies you're a real customer.

**GPU access can require a 60-day wait.** One Trustpilot reviewer deposited **$1,000** intending to rent GPUs and was told to wait 60 days, with spending restricted to a handful of $5/month nodes in the meantime. Their money sat in the account, unusable, until they negotiated the restriction down. Reddit commenters give the other side of it: trial credit isn't meant to fund GPU rentals, because people would mine crypto with it.

**Bare metal can sit behind a 30-day probation.** A reviewer trying to provision the `vbm-8c-64gb-amd` bare-metal configuration, roughly **$400/month**, reports it being gated behind a 30-day probationary period plus a requirement to spend an extra **$250 within 30 days** on services they didn't need, purely to "earn" the right to rent the hardware.

**Suspension takes the credit with it.** When an account gets suspended, users report the $300 credit is removed along with access. One wrote: "The $300 credit, which was supposed to be usable during the trial period, was also removed from our account."

**Account Credit is not refundable, according to users.** A G2 reviewer describes Vultr as generally not refunding "Account Credit," calling the policy "a bit anti-consumer." Another reports a $100 deposit, a completed installation, a suspended account, and no balance returned. To be clear: these are customer accounts of what happened to them, not quoted policy text. Vultr's published promo terms say only that restrictions apply.

**The credit is time-limited.** It functions as a trial balance rather than permanent funds. Don't model it as a year of free hosting; model it as a month of testing that ends whether or not you've finished evaluating.

The practical takeaway for anyone planning to use the credit: **don't fund the account before you know which product tier you're cleared for.** Verify identity at signup, ask support in writing whether your intended product is available to a new account, and only then deposit. Starting on a $3.50 or $6 instance for a week costs almost nothing and tells you more about the platform than a support thread will.

👉 [Claim the current new-customer credit and check the terms](https://www.vultr.com/coupons?ref=9738262-9J)

## Who should use Vultr, and who should not

The official footprint is genuinely broad: **32 data centres across six continents, 1.5 million+ customers in 185 countries, 45 million+ instances deployed**. But a large network doesn't tell you whether it fits your situation.

**Good fit:**
- Developers and small teams who are comfortable on the command line and want a cheap, fast VM in a specific region
- Anyone automating infrastructure through Terraform or the API
- Self-hosters running Docker workloads, n8n, WordPress, small game servers, MQTT brokers for IoT projects
- Teams that need a hot backup or disaster-recovery copy in the same region as their main cloud
- AI and HPC teams that can commit to reserved GPU contracts and plan around capacity

**Poor fit:**
- Businesses with no dedicated sysadmin running critical workloads, because nothing catches a misconfigured firewall for you
- Anyone who needs phone or live-chat support during an incident, or works weekends
- Teams provisioning GPUs or bare metal on a deadline who can't absorb a 30- to 60-day gate
- Architectures that depend on turn-key services — batch processing, message buses, advanced security and monitoring. A TrustRadius reviewer puts it plainly: Vultr "may not be well suited for architectures that require more turn-key services"
- Anyone whose workload requires a Middle East or Africa region

## Vultr vs DigitalOcean, AWS and Azure

Reviewers mention four competitors by name when explaining why they moved, and the reasoning is consistent enough to be useful.

**Against AWS:** cost, mostly. "If for instance we wanted to get similar quality in AWS we would be paying a lot more," one TrustRadius reviewer wrote. Teams that don't need the wider AWS service catalogue come out ahead on Vultr.

**Against Azure:** setup speed. One team migrated their app off Azure because "doing anything took ages" and rebuilt the environment on Vultr in minutes.

**Against DigitalOcean:** close enough that reviewers argue about it. One TrustRadius review is titled "competitive and better than digital ocean." The pattern in the comments is that Vultr edges ahead on price-to-performance and GPU breadth, while DigitalOcean's advantage is a deeper library of tutorials and a more mature ecosystem.

**Against Hostinger:** Hostinger appears once, in a US TrustRadius review, purely as an alternative considered. No comparative detail was given, so there's nothing reliable to say about that pairing.

Vultr's own positioning against all of them is that it avoids hyperscaler complexity while undercutting hyperscaler pricing. Whether that's a benefit depends entirely on whether you want a smaller, simpler service catalogue or need the breadth.

## Before you sign up: five things to confirm

1. **Pick the region before the plan.** With 32 locations, latency differences will matter more to your users than the difference between a $3.50 and a $6 instance.
2. **Check that your product tier is open to new accounts.** GPU and bare-metal provisioning are the two areas where users report gating. Ask before you deposit.
3. **Set billing alerts on day one.** Bandwidth overage at $0.01/GB and snapshots at $0.05/GB/month accumulate quietly.
4. **Decide how you'll handle a security incident.** If the answer is "call support," this isn't the provider for that workload.
5. **Read the promo terms for the code you're using.** The four offers can't be combined, and the free-tier programme is a separate application.

## The bottom line

Start on the **$3.50/month Cloud Compute Regular** instance with IPv4, or the **$6/month High Frequency** plan if you want NVMe under a CMS. Run something real on it for a week. If your workload is self-managed by design and you never need a human, Vultr's price-to-performance holds up against everything reviewers compare it to, and the GPU catalogue goes places the budget providers don't.

If your business stops when a ticket goes unanswered until Monday, budget for that risk before you budget for the server.

Either way, don't let the $300 credit drive the decision. It's a month of testing with conditions attached, not a discount on a year of hosting.

👉 [Open a Vultr account and pick your plan](https://bit.ly/VuLtr)
