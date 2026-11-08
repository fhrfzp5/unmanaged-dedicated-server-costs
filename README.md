# Unmanaged dedicated server hosting: what you actually take on, what the second invoice costs, and when managed is the cheaper call

Unmanaged dedicated hosting is cheaper per month, and that is the only simple part of the deal. The saving holds if someone on your side can patch a kernel, read a firewall log, and notice a failing disk before your users do. Everything above the bare metal — the operating system, the control panel, the mail stack, the backups — lands on your desk, and several of those pieces carry their own price tag.

SpinServers sells exactly this kind of server: bare metal from **$79/mo**, month to month, no setup fee, no management. Below is how the work splits, what the $79 actually includes, and which add-ons turn a cheap server into an expensive one.

> **Quick pick:** if you already run servers and want raw hardware with 10 Gbps networking, start with the **$79 Xeon E3-1280 v5** (4 cores / 8 threads, 32 GB ECC RAM, 1 TB NVMe, 30 TB transfer). If you are moving a client portfolio or a store where an hour of downtime costs sales, buy managed hosting instead, or budget for a contractor, because nothing on the SpinServers lineup is managed.
>
> 👉 [See the current SpinServers plan list and prices](https://bit.ly/Spinservers)

## The published plans, and who each one fits

SpinServers runs two locations, Dallas and San Jose, and prices the same hardware differently in each. The tiers below are the vendor's published list, recorded on 21 September 2026.

| Plan | CPU / RAM / Storage | Network & transfer | Price | Order |
| --- | --- | --- | --- | --- |
| Intel Xeon E3-1280 v5 | 4 cores / 8 threads @ 3.7 GHz turbo, 32 GB DDR4 ECC, 1 TB M.2 NVMe | 10 Gbps port, 30 TB/mo, 1 IPv4 | **$79/mo** | [Check this plan](https://bit.ly/Spinservers) |
| Starter Package | 32 GB RAM, 1 TB NVMe, full root | 10 Gbps, 10 TB/mo | **$99/mo** | [Check this plan](https://bit.ly/Spinservers) |
| Growth Package | 256 GB RAM, 2 × 1.6 TB SSD, full root | 10 Gbps, 20 TB/mo | **$149/mo** | [Check this plan](https://bit.ly/Spinservers) |
| High Performance Package | 768 GB RAM, 8 × 2 TB SSD, full root | 10 Gbps, 40 TB/mo | **$679/mo** | [Check this plan](https://bit.ly/Spinservers) |

No setup fee on any tier, and billing is month to month rather than annual.

Three things the table hides. The Starter, Growth and High Performance tiers are published without CPU details, so ask for the processor before you compare them against the Xeon E3 entry, which is the only one with a full spec sheet. Inventory rotates: at the time of the price check the Dallas page also listed a dual Xeon Platinum 8173M (56 cores / 112 threads, 512 GB RAM, 4 × 1.92 TB SSD, 2 × 10 Gbps LACP) with no public price, and San Jose listed a 32-core / 64-thread machine with 512 GB RAM and 2 × 3.84 TB SSD. And San Jose generally costs more than Dallas for equivalent hardware, which is the usual trade for West Coast and Asia-Pacific latency.

One published review of the lineup points out where the pricing comes from: SpinServers is vertically integrated with a large used-enterprise-hardware trader, which is how Dell, HP, Quanta and Supermicro machines reach these monthly numbers.

## What "unmanaged" leaves on your desk

Both managed and unmanaged give you a whole physical machine, and both can hand you full root. The split is about who does the daily work on top of that root access.

| Task | Managed | Unmanaged (SpinServers) |
| --- | --- | --- |
| Patching and OS updates | Provider | You |
| Uptime and performance monitoring | Provider | You |
| Firewall configuration | Provider, usually with your input | You |
| Skill level needed | Low to moderate | High |
| Time commitment | Low | Ongoing |
| Control | Full root, guided by support | Full root, entirely self-directed |
| Monthly cost | Higher | Lower |
| Typical buyer | Team without a server admin | Developers and agencies with existing ops |

A first-time unmanaged customer gets the keys to the server and builds from an empty machine. Nothing arrives pre-tuned for your workload, which is the point for a team with a deployment pipeline and a liability for everyone else.

## Where support actually stops

"Unmanaged means no support" is wrong, and it is the sentence that causes the most expensive misunderstandings. The boundary sits in three layers.

**Hardware, network and the data center are the provider's problem.** Failed disks, dead power supplies, switch ports, upstream routing: you open a ticket and they fix it. SpinServers gives IPMI/iKVM console access, so you can reinstall or debug even if you have bricked the OS. Hostkey, which also sells only unmanaged servers, keeps a fleet of substitution machines and replaces failed components as part of the rental. KnownHost advertises DDoS protection and a 99.99% SLA on its unmanaged plans.

**The operating system and everything above it is yours.** Updates, kernel tuning, firewall rules, malware scanning, intrusion detection, backups, the web stack. A hardware fault is their ticket; a broken application config is yours.

**Management can usually be bought separately.** Hostkey states it plainly for its own lineup: all servers are unmanaged, and administration services are available for a fee. Ask SpinServers the same question before you order if you want a retainer rather than a DIY setup.

Worth knowing: "managed" has no industry-wide definition. One large host's own blog describes its managed tier as proactively handling patching, monitoring and backups, then says a few paragraphs later that day-to-day administration stays with the customer. Get the inclusion list in writing, from any provider.

## The second invoice: what is not in the $79

A dedicated server quote covers hardware, power, port and a transfer allowance. It rarely covers the software you need to actually run websites, and the extras add up faster than the base price suggests.

**Control panels and commercial licences.** cPanel, WHM, LiteSpeed, DirectAdmin and server-side security suites are licensed per account or per domain and billed monthly. As a benchmark, one established host published these add-on prices in 2023: LiteSpeed Site Owner Plus for 5 domains at $16/mo, Web Host Essential unlimited at $32/mo, Imunify360 from $11/mo for one user to $41/mo unlimited, and MailChannels outbound email from $15/mo for 5,000 messages to $90/mo for 50,000. Those are another company's 2023 numbers, not SpinServers pricing, but they show the order of magnitude: a panel plus a security suite plus a mail relay can add $50–$100 a month on top of the server.

**Backup storage.** Backups are your responsibility on an unmanaged box, and the disk to hold them is often not included. At KnownHost, managed plans ship with a secondary 1 TB drive for local backups by default; unmanaged plans do not.

**IP addresses.** SpinServers includes one IPv4 address plus an IPv6 /64 allocation. If you host mail, run separate SSL properties or manage sites for several clients, one address runs out quickly. Conventions vary: KnownHost hands out a /29 with every dedicated server, which is 5 usable addresses, and sells additional addresses in blocks of 8. Ask what extra IPv4 costs before you design around it.

**Outbound traffic.** Every tier above carries a monthly allowance: 10 TB on Starter, 30 TB on the Xeon E3, 40 TB on the High Performance plan. What happens past the cap is a billing question, and it differs by provider. Hostkey, for example, keeps inbound traffic free under fair use and meters outbound according to the chosen plan. Get the overage rate in writing.

**Software licensed per physical machine.** If you own per-socket or per-core licences, a dedicated box lets you reuse them, which is one of the strongest arguments for bare metal. Note the cloud caveat: AWS states that its Dedicated Instances cannot support per-machine licensing because of the architecture, and that workload needs Dedicated Hosts or bare metal instead.

👉 [See what SpinServers includes at the base price, tier by tier](https://bit.ly/Spinservers)

## What SpinServers bundles, and what it does not

Included across the lineup, per the vendor's own specification sheets and published review material: 10 Gbps networking (several configurations list two 10 Gbps ports with LACP), IPMI/iKVM console access, DDoS-protected multihomed network on the provider's own ASN, a free virtual private cloud for Layer 2 private networking between your servers, automatic installs of Linux, Windows or ESXi, and 24/7 support through email, phone, tickets and live chat. Provisioning on in-stock hardware is quoted at around 30 minutes, and facilities are advertised as SOC 2, HIPAA and PCI compliant Tier III data centers.

Not included: any management or administration, managed PCI compliance work or vulnerability scanning as a service, and per the same review material, month-to-month service generally carries no refund policy. If a refund window or an uptime SLA number matters to your contract, settle both before paying, because neither is something you can retrofit after a bad month.

The compliance point deserves emphasis. Renting space in a compliant building does not make your workload compliant. If PCI or HIPAA paperwork is the reason you are moving, you are buying infrastructure and doing the audit work yourself, or hiring someone to do it.

## Who should not buy unmanaged

**E-commerce with no technical staff.** Uptime, checkout security and page speed convert directly into revenue, and the margin for error is thinner when downtime means lost orders. Managed hosting costs more per month and less per incident.

**Agencies with a lean team and many client sites.** You inherit every client's plugin conflict and every 2 a.m. page. Unless you already run a DevOps process, an unmanaged box converts client work into server work.

**Anyone whose compliance requirement includes a managed service.** If the auditor expects a provider to own scanning, file integrity monitoring and audit logs, a self-managed server moves that obligation to you, not away from you.

**Anyone who cannot answer "who patches this on a Sunday?"** That is the whole test. If no name comes to mind, the $79 server is the expensive option.

## VPS first, or straight to bare metal?

A VPS is a virtualized slice of a shared node. Your CPU and RAM may be guaranteed, but you still have neighbours. A dedicated server is the whole physical machine, and nobody else's traffic spike touches it. If your current problem is a noisy neighbour or a resource ceiling, a larger VPS solves it for less money and scales faster. Move to bare metal when you need the full machine's resources, per-machine software licensing, or hardware-level control.

## FAQ

**Can I move to a managed setup later?** Usually yes, and it depends on the provider. Confirm the migration steps and the expected downtime before you commit, and confirm whether migration assistance is included or billed as an extra. Providers differ on this.

**Who fixes hardware when it fails?** The provider. Disks, PSUs, RAM and network gear are covered; the operating system and applications are not. Keep your own backups regardless, and ask how fast replacement parts are dispatched.

**Can I install a custom ISO or a non-standard OS?** On most unmanaged providers, yes. Hostkey, for instance, offers an ISO library in its control panel and lets you mount your own image through IPMI. SpinServers provides IPMI/iKVM access and automated Linux, Windows and ESXi installs, which covers the same ground for standard stacks.

**Do I have to buy cPanel?** No. It is optional and separately licensed, and plenty of unmanaged servers run a bare LEMP stack with no panel at all. Only pay for it if you or your clients actually need the interface.

**Is there a trial or refund?** Some providers offer a paid trial month with unused funds returned to account credit. For SpinServers, month-to-month service is generally reported as non-refundable, so treat the first invoice as committed spend and confirm the cancellation terms in writing.

## How to decide

- **One or two high-traffic sites, and you already run servers** → the $79 Xeon E3-1280 v5 with 32 GB RAM and 30 TB transfer is the sensible entry point. Spend the difference on a panel licence and a backup target.
- **Heavy virtualisation or a multi-tenant stack** → the Growth tier at $149/mo with 256 GB RAM and 2 × 1.6 TB SSD gives you room for several VMs; the High Performance tier at $679/mo only makes sense if you genuinely need 768 GB RAM and 8 × 2 TB SSD.
- **Client sites, a store, or nobody on call** → buy managed, or price a contractor into the budget before you order.
- **A short project such as a migration stress test or a render batch** → month-to-month billing is the minimum commitment here, so a month is what you pay. Hourly billing exists at some providers if you need days rather than weeks.

Four things to confirm before you pay: how many IPv4 addresses you get and what extras cost, the outbound overage rate past your transfer allowance, whether migration help is included, and the cancellation and refund terms. Then pick the tier that matches your RAM and disk, not the one with the biggest number in the marketing copy.

👉 [Start with the $79 Xeon E3 plan at SpinServers](https://bit.ly/Spinservers)
