# DMIT VPS plans: which LAX, HKG or TYO tier fits, what year two costs, and the IP rules that decide it (full price tables)

DMIT sells KVM VPS in Los Angeles, Hong Kong and Tokyo across three network tiers, and the cheapest way in is the **LAX Tier 1 WEE at $36.90/year** for 1 vCPU, 1GB RAM, 20GB SSD and 1TB of monthly traffic. If your users are in mainland China, the entry point is **$88.88/year**, and at that price you get to choose between two plans that cost the same but are not the same: LAX Eyeball TINY (1500GB, 2Gbps port) or LAX Premium TINY (1000GB, 1Gbps, CN2 GIA routing). If latency is the entire reason you're here, **Hong Kong Premium starts at $39.90/month**, with roughly 20–50ms to mainland cities.

Everything below is the price table for every tier currently listed, plus the parts that decide whether the cheap plan was actually cheap: renewal math, how IP replacement works on each series, how traffic is counted, and what the refund window really covers.

> **Quick picks**
> - Cheapest usable box, no China routing: LAX T1 WEE, $36.90/yr
> - China-optimized on a budget: LAX EB TINY, $88.88/yr, 1500GB, 2Gbps
> - Strictest routing: LAX Pro TINY at $88.88/yr, or HKG Pro from $39.90/mo
> - Want to test first: LAX T1 STARTER at $12.90/mo, refundable inside 3 days
>
> 👉 [See the current DMIT plan list and cart prices](https://www.dmit.io/aff.php?aff=9081)

## The three network tiers, and what you're actually paying for

Premium (Pro) is the China Telecom CN2 GIA product. It combines DMIT's own backbone and Tier 1 transit with China Telecom CN2 GIA (AS4809), dedicated peering with China Unicom (AS9929) and China Mobile International (AS58807). DMIT's own network page quotes about **15ms from Hong Kong to Shenzhen and 28ms from Tokyo to Shanghai, with peak packet loss under 0.1%**. Those are vendor measurements, so treat them as a ceiling on what to expect rather than an independent benchmark.

Eyeball (EB) rides CMIN2 and related China-optimized routes. It sits below Pro on routing strictness and above it on traffic allowance and port speed at the same price. Tier 1 (T1) is plain international transit, aggregated up to 7.6Tbps across Cogent, NTT, GTT, Arelion, Lumen, Tata and exchanges including Equinix IX, BBIX and JPIX. No mainland-specific routing at all.

Hardware comes in three generations. AN5 is AMD EPYC 9005 (Zen 5) with DDR5 and PCIe 5.0 NVMe and carries a premium. AN4 is EPYC 9004 and is the volume platform. AS3 is EPYC 7003 and is the budget tier, still being rolled out on LAX; DMIT's own notice warns of reduced disk performance during that transition.

**A word on the numbers.** DMIT's storefront renders prices dynamically and the figures below come from third-party plan trackers, the most complete of which was compiled in April 2026. A few tiers are listed inconsistently between trackers. Treat every figure as indicative and let the cart settle it at checkout.

## LAX Premium (AN4, CN2 GIA)

| Plan | vCPU / RAM / SSD | Traffic / Port | Price | Order |
| --- | --- | --- | --- | --- |
| TINY | 1C / 2GB / 20GB | 1000GB / 1Gbps | $88.88/yr | [ View TINY](https://www.dmit.io/aff.php?aff=9081) |
| Pocket | 2C / 2GB / 40GB | 1500GB / 4Gbps | $159.98/yr | [ View Pocket](https://www.dmit.io/aff.php?aff=9081) |
| STARTER | 2C / 2GB / 80GB | 3000GB / 10Gbps | $29.90/mo | [ View STARTER](https://www.dmit.io/aff.php?aff=9081) |
| MINI | 4C / 4GB / 80GB | 5000GB / 10Gbps | $58.88/mo | [ View MINI](https://www.dmit.io/aff.php?aff=9081) |
| MICRO | 4C / 4GB / 160GB | 7000GB / 10Gbps | $74.99/mo | [ View MICRO](https://www.dmit.io/aff.php?aff=9081) |
| MEDIUM | 6C / 8GB / 160GB | 15000GB / 10Gbps | $168.88/mo | [ View MEDIUM](https://www.dmit.io/aff.php?aff=9081) |
| LARGE | 8C / 16GB / 320GB | 25000GB / 10Gbps | $338.88/mo | [ View LARGE](https://www.dmit.io/aff.php?aff=9081) |
| GIANT | 12C / 24GB / 640GB | 50000GB / 10Gbps | $619.99/mo | [ View GIANT](https://www.dmit.io/aff.php?aff=9081) |

## LAX Premium on the newer AN5 platform (EPYC 9005)

| Plan | vCPU / RAM / SSD | Traffic / Port | Price | Order |
| --- | --- | --- | --- | --- |
| TINY | 1C / 2GB / 20GB | 1000GB / 1Gbps | $119.99/yr | [ View AN5 TINY](https://www.dmit.io/aff.php?aff=9081) |
| Pocket | 2C / 2GB / 40GB | 1500GB / 4Gbps | $203.90/yr | [ View AN5 Pocket](https://www.dmit.io/aff.php?aff=9081) |
| STARTER | 2C / 2GB / 80GB | 3000GB / 10Gbps | $38.90/mo | [ View AN5 STARTER](https://www.dmit.io/aff.php?aff=9081) |
| MINI | 4C / 4GB / 80GB | 5000GB / 10Gbps | $76.90/mo | [ View AN5 MINI](https://www.dmit.io/aff.php?aff=9081) |
| MICRO | 4C / 4GB / 160GB | 7000GB / 10Gbps | $99.90/mo | [ View AN5 MICRO](https://www.dmit.io/aff.php?aff=9081) |
| MEDIUM | 6C / 8GB / 160GB | 15000GB / 10Gbps | $219.90/mo | [ View AN5 MEDIUM](https://www.dmit.io/aff.php?aff=9081) |
| GIANT | 12C / 24GB / 640GB | 50000GB / 10Gbps | $839.90/mo | [ View AN5 GIANT](https://www.dmit.io/aff.php?aff=9081) |

AN5 runs roughly a third more than the AN4 equivalent on the same traffic and port. One tracker lists lower AN5 figures ($34.90 / $62.90 / $87.90 for STARTER / MINI / MICRO), so the honest summary is that AN5 costs meaningfully more than AN4 and you should price it in the cart before assuming a number.

## LAX Eyeball (AN4, CMIN2)

| Plan | vCPU / RAM / SSD | Traffic / Port | Price | Order |
| --- | --- | --- | --- | --- |
| TINY | 1C / 2GB / 20GB | 1500GB / 2Gbps | $88.88/yr | [ View EB TINY](https://www.dmit.io/aff.php?aff=9081) |
| Pocket | 2C / 2GB / 40GB | 3000GB / 4Gbps | $159.98/yr | [ View EB Pocket](https://www.dmit.io/aff.php?aff=9081) |
| STARTER | 2C / 2GB / 80GB | 5000GB / 10Gbps | $29.90/mo | [ View EB STARTER](https://www.dmit.io/aff.php?aff=9081) |
| MINI | 4C / 4GB / 80GB | 10000GB / 10Gbps | $58.88/mo | [ View EB MINI](https://www.dmit.io/aff.php?aff=9081) |
| MICRO | 4C / 4GB / 160GB | 14000GB / 10Gbps | $74.99/mo | [ View EB MICRO](https://www.dmit.io/aff.php?aff=9081) |
| MEDIUM | 6C / 8GB / 160GB | 30000GB / 10Gbps | $168.88/mo | [ View EB MEDIUM](https://www.dmit.io/aff.php?aff=9081) |
| LARGE | 8C / 16GB / 320GB | 50000GB / 10Gbps | $338.88/mo | [ View EB LARGE](https://www.dmit.io/aff.php?aff=9081) |
| GIANT | 12C / 24GB / 640GB | 100000GB / 10Gbps | $619.99/mo | [ View EB GIANT](https://www.dmit.io/aff.php?aff=9081) |

## LAX Tier 1

| Plan | vCPU / RAM / SSD | Traffic | Price | Order |
| --- | --- | --- | --- | --- |
| WEE | 1C / 1GB / 20GB | 1000GB | $36.90/yr | [ View T1 WEE](https://www.dmit.io/aff.php?aff=9081) |
| TINY | 1C / 1GB / 20GB | 2000GB | $6.90/mo | [ View T1 TINY](https://www.dmit.io/aff.php?aff=9081) |
| STARTER | 2C / 2GB / 40GB | 4000GB | $12.90/mo | [ View T1 STARTER](https://www.dmit.io/aff.php?aff=9081) |
| MINI | 2C / 4GB / 80GB | 8000GB | $21.90/mo | [ View T1 MINI](https://www.dmit.io/aff.php?aff=9081) |
| MICRO | 4C / 4GB / 120GB | 16000GB | $32.90/mo | [ View T1 MICRO](https://www.dmit.io/aff.php?aff=9081) |

Tracker listings disagree on the exact vCPU and disk on the T1 STARTER and MINI tiers. The prices are consistent everywhere; the configurations are not, so verify the spec block on the cart page.

## Hong Kong Premium

| Plan | vCPU / RAM / SSD | Traffic | Price | Order |
| --- | --- | --- | --- | --- |
| TINY | 1C / 1GB / 20GB | 500GB | $39.90/mo | [ View HKG Pro TINY](https://www.dmit.io/aff.php?aff=9081) |
| STARTER | 1C / 2GB / 40GB | 1000GB | $79.90/mo | [ View HKG Pro STARTER](https://www.dmit.io/aff.php?aff=9081) |
| MINI | 2C / 2GB / 60GB | 1200GB | $119.90/mo | [ View HKG Pro MINI](https://www.dmit.io/aff.php?aff=9081) |
| MICRO | 4C / 4GB / 80GB | 1600GB | $159.90/mo | [ View HKG Pro MICRO](https://www.dmit.io/aff.php?aff=9081) |

Hong Kong traffic is counted bidirectionally, and the allowance is thin by design: this line exists to be close to Shenzhen, not to move terabytes. One listing shows 800GB on STARTER where another shows 1TB.

## Hong Kong Eyeball

| Plan | vCPU / RAM / SSD | Traffic / Port | Price | Order |
| --- | --- | --- | --- | --- |
| STARTERv2 | 1C / 2GB / 40GB | 2000GB / 2Gbps | $59.90/mo | [ View HKG EB STARTERv2](https://www.dmit.io/aff.php?aff=9081) |
| MINIv2 | 2C / 2GB / 60GB | 3000GB / 2Gbps | $89.90/mo | [ View HKG EB MINIv2](https://www.dmit.io/aff.php?aff=9081) |
| MICROv2 | 4C / 4GB / 80GB | 4000GB / 4Gbps | $129.90/mo | [ View HKG EB MICROv2](https://www.dmit.io/aff.php?aff=9081) |

## Tokyo Premium

| Plan | vCPU / RAM / SSD | Traffic | Monthly | Annual | Order |
| --- | --- | --- | --- | --- | --- |
| TINY | 1C / 1GB / 20GB | 500GB | $21.90 | $262 | [ View TYO Pro TINY](https://www.dmit.io/aff.php?aff=9081) |
| STARTER | 1C / 2GB / 40GB | 1000GB | $39.90 | $478 | [ View TYO Pro STARTER](https://www.dmit.io/aff.php?aff=9081) |
| MINI | 2C / 2GB / 60GB | 2000GB | $79.90 | $958 | [ View TYO Pro MINI](https://www.dmit.io/aff.php?aff=9081) |
| MICRO | 4C / 4GB / 80GB | 4000GB | $159.90 | $1918 | [ View TYO Pro MICRO](https://www.dmit.io/aff.php?aff=9081) |
| MEDIUM | 4C / 8GB / 160GB | 5000GB | $259.90 | $3118 | [ View TYO Pro MEDIUM](https://www.dmit.io/aff.php?aff=9081) |
| LARGE | 8C / 16GB / 320GB | 8000GB | $429.90 | $5158 | [ View TYO Pro LARGE](https://www.dmit.io/aff.php?aff=9081) |
| GIANT | 8C / 24GB / 640GB | 15000GB | $799.90 | $9598 | [ View TYO Pro GIANT](https://www.dmit.io/aff.php?aff=9081) |

## Tokyo Eyeball

| Plan | vCPU / RAM / SSD | Traffic / Port | Monthly | Annual | Order |
| --- | --- | --- | --- | --- | --- |
| TINY | 1C / 1GB / 20GB | 1000GB / 1Gbps | $25.90 | $310 | [ View TYO EB TINY](https://www.dmit.io/aff.php?aff=9081) |
| STARTER | 1C / 2GB / 40GB | 2000GB / 2Gbps | $55.90 | $670 | [ View TYO EB STARTER](https://www.dmit.io/aff.php?aff=9081) |
| MINI | 2C / 2GB / 60GB | 3000GB / 2Gbps | $85.90 | $1030 | [ View TYO EB MINI](https://www.dmit.io/aff.php?aff=9081) |
| MICRO | 4C / 4GB / 80GB | 4000GB / 4Gbps | $119.90 | $1438 | [ View TYO EB MICRO](https://www.dmit.io/aff.php?aff=9081) |
| MEDIUM | 4C / 8GB / 160GB | 6000GB / 4Gbps | $179.90 | $2158 | [ View TYO EB MEDIUM](https://www.dmit.io/aff.php?aff=9081) |
| LARGE | 8C / 16GB / 320GB | 12000GB / 4Gbps | $369.90 | $4438 | [ View TYO EB LARGE](https://www.dmit.io/aff.php?aff=9081) |
| GIANT | 8C / 24GB / 640GB | 24000GB / 4Gbps | $749.90 | $8998 | [ View TYO EB GIANT](https://www.dmit.io/aff.php?aff=9081) |

## Tokyo Tier 1

| Plan | vCPU / RAM / SSD | Traffic / Port | Price | Order |
| --- | --- | --- | --- | --- |
| WEE | 1C / 1GB / 20GB | 1000GB / 4Gbps | $36.90/yr | [ View TYO T1 WEE](https://www.dmit.io/aff.php?aff=9081) |
| TINY | 1C / 1GB / 20GB | 2000GB / 4Gbps | $6.90/mo or $76.90/yr | [ View TYO T1 TINY](https://www.dmit.io/aff.php?aff=9081) |
| STARTER | 1C / 2GB / 40GB | 4000GB / 10Gbps | $12.90/mo or $154.80/yr | [ View TYO T1 STARTER](https://www.dmit.io/aff.php?aff=9081) |
| MINI | 2C / 2GB / 60GB | 8000GB / 10Gbps | $21.90/mo or $262.80/yr | [ View TYO T1 MINI](https://www.dmit.io/aff.php?aff=9081) |

## Three pairs where the same money buys different things

**LAX EB TINY vs LAX Pro TINY, both $88.88/year.** Identical CPU, RAM and disk. The Pro plan gives you CN2 GIA and 1000GB on a 1Gbps port. The EB plan gives you CMIN2 and 1500GB on a 2Gbps port. If you're serving a blog or an API to mixed Chinese ISPs and you aren't chasing the strictest telecom path, EB is the better buy at the same price. Take Pro when China Telecom users dominate your traffic and evening jitter has already cost you customers elsewhere.

**Tokyo EB MICRO at $119.90/mo vs Tokyo Pro MICRO at $159.90/mo.** Same 4C/4GB/80GB, same 4000GB of traffic. EB throws in a 4Gbps port; Pro stays at 1Gbps and charges $40/month more for three-network CN2 GIA. That's $480 a year for routing. Worth it if you've measured the difference on your own traffic, wasteful if you haven't.

**LAX T1 STARTER at $12.90/mo vs LAX Pro STARTER at $29.90/mo.** Roughly double, and what the extra $17 buys is the routing and the 10Gbps port. If your audience is in Europe or the US, that $17 is a donation.

## What the second year costs

Annual billing is not uniformly a discount. On Tokyo Tier 1 TINY, paying $76.90 up front against $6.90/month works out to about $6.41/month, so you save roughly 7%. On Tokyo Premium TINY, $262/year against $21.90/month is $21.83/month, which is a rounding error. LAX Premium TINY is only sold annually at $88.88, so the monthly comparison doesn't exist there.

The bigger lever is recurring coupons. A 20% recurring code on an $88.88 annual plan drops it to about $71.10, and that price holds on every renewal for as long as you keep the plan, not just the first invoice. Most recurring codes only activate on quarterly or annual terms, monthly orders usually don't qualify, one code per order, and they're issued to new customers. Reusing a code tied to another account can get the order suspended. Some promotions also pay back a percentage as account credit starting around day 27 of the billing cycle, and that credit is balance, not cash. Refund the order and you lose the promotional pricing with it.

👉 [Check which term length unlocks the current discount](https://www.dmit.io/aff.php?aff=9081)

## The fine print that decides whether it was a good deal

**Refunds.** Within 3 days and under 30GB of traffic used, you get a full refund minus the payment gateway fee. Between day 3 and day 30 it's prorated, and DMIT takes the lower of two figures: the value of your remaining traffic, or the value of your remaining service time. Renewal orders, orders paid from account balance, balance top-ups, a product line you've already refunded three times, and IPs that have been DDoSed are all excluded. So is a "region unreachable" claim filed after you've pushed more than 3GB.

**IP replacement works differently per series, and this is the most common surprise.** On Premium and Eyeball, the first IP is guaranteed globally reachable barring force majeure. Without the IP Care+ add-on you can swap it free every 15 days; with it, every 7 days. Paying $5 gets you an immediate replacement. On Tier 1 there is no reachability guarantee at all, including for China and Russia. You either buy the IP Guarantee+ add-on or pay $5 per change with a 7-day cooldown. If your use case makes a blocked IP likely, budget for that add-on before you compare the T1 price against anything else.

**Traffic is counted in both directions on standard packages.** Uploads eat the quota alongside downloads. A 1000GB allowance on a file host or a backup target is 500GB of usable outbound, not 1000.

**Tier 1 overage throttles instead of suspending.** Blow through the quota and the port drops to 50–100Mbps until the monthly reset, so the box stays reachable over SSH rather than going dark. Most standard packages also let you pay for an early quota reset.

**It's unmanaged.** Ticket response is guaranteed within 72 hours, not 72 minutes. Root password login is disabled by default and you're expected to use SSH keys, which you can change later from the console if you need to. Accounts can't be transferred.

👉 [Start with a plan small enough to test inside the 3-day window](https://www.dmit.io/aff.php?aff=9081)

## Coupon codes: what's circulating and how to check it

Third-party trackers list recurring codes such as `LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF` for LAX Eyeball on quarterly or annual terms, `202510_HKG_TYO_PRO_20OFF_RECURRING` for Hong Kong and Tokyo Premium, `202510_HKG_TYO_T1_30OFF_RECURRING` for Hong Kong and Tokyo Tier 1 (excluding WEE), and `2025-TYO-T1-HI-GSL-NON-MONTHLY-30OFF` for Tokyo Tier 1. These were compiled during 2025–2026 promotional cycles and there is no guarantee any of them still validates today.

The only reliable procedure is to paste the code into the Promotion Code field on the checkout page and hit Validate Code before you pay. If it returns an error, the campaign is over and you buy at list price. Codes don't stack, so pick the single best one for the plan in your cart.

👉 [Paste and validate your code on the DMIT order page](https://www.dmit.io/aff.php?aff=9081)

## Who shouldn't buy this

If none of your users are in mainland China, skip Premium entirely. Tier 1 at $12.90/month in LAX, HKG or TYO gives you solid APAC transit at a fraction of the price, and a generic budget provider will often beat even that on raw specs. Paying three to six times more for CN2 GIA routing you don't use is the most expensive mistake in this product line.

If you're not comfortable with a Linux shell and SSH keys, this is unmanaged infrastructure with a 72-hour ticket SLA. Nobody is going to install your stack for you.

## FAQ

**Can I pay with Alipay or WeChat Pay?** Yes, both are supported alongside PayPal and cards. There's also a Chinese-language interface and Chinese support staff.

**Do coupons work on monthly billing?** Most don't. Recurring discounts generally require quarterly or annual terms, which is one reason the annual price is worth comparing even when the monthly discount looks trivial.

**What happens if my IP gets blocked?** On Premium and Eyeball, request a replacement; free every 15 days normally, every 7 days with IP Care+, or $5 for immediate. On Tier 1, expect $5 per change with a 7-day cooldown unless you bought IP Guarantee+.

**How strict is the 3-day refund?** Both conditions apply: within 3 days of purchase and under 30GB of traffic consumed. Past that you're in prorated territory, and past 30 days there's nothing.

**Is Tier 1 the same server as Premium with worse routing?** Same platform family, different network treatment and different IP guarantees. The hardware tier (AN5 / AN4 / AS3) is a separate axis from the network tier (Pro / EB / T1), and the cart shows both.

**Is "no overselling" something I can verify?** It's a claim the vendor and its users repeat, not a published metric. Judge it by your own latency and packet loss after deployment rather than by the phrase.

## Before you click order

Pick by audience, not by spec sheet. Mainland China users where telecom quality matters: LAX Pro or HKG Pro. Mainland users where budget and traffic volume matter more: LAX or HKG Eyeball, and Tokyo Eyeball above MICRO if you need a fast port. Nobody in China: Tier 1, cheapest tier that fits the RAM.

Then do two things. Validate your coupon on the checkout page before paying, because a dead code silently costs you the entire discount. And once the box is up, run mtr from two or three real user locations within the first 72 hours. If the routing doesn't hold up on your traffic, the refund window is still open and the decision is reversible.

👉 [Compare the LAX, HKG and TYO carts side by side](https://www.dmit.io/aff.php?aff=9081)
