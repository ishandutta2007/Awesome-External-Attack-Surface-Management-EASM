# Awesome-External-Attack-Surface-Management-EASM

# Awesome External Attack Surface Management (EASM)

> A curated list of top External Attack Surface Management (EASM) platforms — both SaaS/Hosted commercial solutions and open-source alternatives for self-hosted attack surface discovery and exposure management.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [CrowdStrike Falcon Attack Surface Management](#crowdstrike-falcon-attack-surface-management)
  - [Cortex Xpanse](#cortex-xpanse)
  - [Censys](#censys)
  - [Microsoft Defender EASM](#microsoft-defender-easm)
  - [Rapid7 Surface Command](#rapid7-surface-command)
  - [Recorded Future Attack Surface Intelligence](#recorded-future-attack-surface-intelligence)
  - [NetSPI EASM](#netspi-easm)
  - [CyCognito](#cycognito)
  - [ProjectDiscovery Cloud](#projectdiscovery-cloud)
  - [Mandiant Advantage ASM](#mandiant-advantage-asm)
- [Open-Source Software](#-open-source-software)
  - [IVRE](#ivre)
  - [OWASP Amass](#owasp-amass)
  - [reNgine](#rengine)
  - [Osmedeus](#osmedeus)
  - [Xingrin](#xingrin)
  - [LunaFox](#lunafox)
  - [OpenEASD](#openeasd)
  - [Open-ASM](#open-asm)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted External Attack Surface Management platforms. These are not open-source but are included as reference points for feature comparison.

### CrowdStrike Falcon Attack Surface Management
**Type:** AI-native external exposure discovery  
Part of CrowdStrike Falcon Exposure Management, Falcon Surface (and broader ASM capabilities) discovers internet-facing assets and maps attack paths using AI-powered correlation. Leverages the Falcon platform's single agent and threat intelligence to prioritize exposures based on exploitability and adversary activity. Users report discovering shadow IT and forgotten VMs previously missing from asset inventories. Real-time monitoring continuously alerts on new exposures. Integration with Falcon Fusion SOAR enables automated remediation workflows [citation:16][citation:27].  
**Best for:** Organizations already invested in the CrowdStrike Falcon platform seeking integrated external and internal exposure visibility.

### Cortex Xpanse
**Type:** Active internet-wide scanning ASM  
Palo Alto Networks' EASM solution continuously scans the entire IPv4 address space (4.3 billion addresses) multiple times daily, plus 500 billion ports, to identify an organization's internet-facing assets and exposures [citation:1][citation:17]. The July 2026 release (v2.14) added on-demand attack surface rescanning from AST alerts, bulk business unit asset mapping, and frontier AI-informed detection coverage [citation:2]. Available as a standalone cloud service or as a module within Cortex XSIAM (standalone has a smaller feature set). Deep integration with Cortex XSOAR for remediation workflows [citation:28].  
**Best for:** Enterprises already in the Palo Alto Cortex ecosystem that need internet-scale discovery and are comfortable with platform dependency.

### Censys
**Type:** Internet intelligence + AI-driven scanning  
Censys maps internet infrastructure with predictive AI scanning that learns deployment patterns, continuously monitoring IPs, hosts, services, and websites across the whole internet. Features a natural language Query Assistant supporting multiple languages and a Model Context Protocol (MCP) server for AI agent integration. SOC 2 Type II certified. Suited for teams that hunt threat infrastructure as well as inventory their own exposure, and for organizations building AI-assisted security workflows [citation:1].  
**Best for:** Security teams wanting internet-wide visibility with AI agent integration and threat hunting capabilities.

### Microsoft Defender EASM
**Type:** Cloud-native EASM within Microsoft Security  
Deploys as an Azure resource with no agents or network changes required. Uses Microsoft's proprietary recursive discovery from seed domains, IP blocks, and ASNs to map unknown internet-facing infrastructure. Inventories domains, hosts, web pages, IP blocks, IPs, ASNs, SSL certificates, and WHOIS contacts. Integrates with Microsoft Security Exposure Management and Defender for Cloud for attack path analysis. Copilot in Azure enables natural language to inventory queries [citation:1][citation:18][citation:29].  
**Best for:** Organizations heavily invested in Azure and the Microsoft security ecosystem wanting EASM with native integration.

### Rapid7 Surface Command
**Type:** Dynamic EASM with CTEM alignment  
Surface Command replaces static seed lists with dynamic discovery that continuously ingests known domain and IP information from DNS records, network services, and asset repositories. Announced in late 2025 and generally available January 2026. Aligns with the full CTEM (Continuous Threat Exposure Management) lifecycle: discovery, prioritization, validation, and mobilization. Integrates with Rapid7's broader Command Platform for unified exposure management [citation:3][citation:10].  
**Best for:** Organizations pursuing a CTEM strategy with continuous, automated seed refresh and unified exposure data.

### Recorded Future Attack Surface Intelligence
**Type:** Intelligence-driven EASM  
Leverages 10+ years of current and historical DNS, WHOIS, and SSL/TLS certificate data to discover forgotten assets, shadow IT, subsidiaries, and third-party infrastructure. Prioritizes exposures based on exploitability and active threat activity using Recorded Future's threat intelligence. Customers report 29% increase in visibility and 51% reduction in vulnerable attack surface (Fortune 500, 6 months). Integrates with Splunk, Palo Alto XSOAR, Tines, and ServiceNow [citation:4].  
**Best for:** Organizations wanting threat-intelligence-driven prioritization and a focus on attacker-targeted exposures.

### NetSPI EASM
**Type:** Human-led, AI-accelerated attack surface management  
Combines automated discovery (weekly external asset scans, dark web monitoring, domain monitoring) with human-led penetration testing expertise. The AI-powered Continuous Pentesting service (launched May 2026) validates real risk through ongoing testing that simulates attacker behavior. Includes MCP integrations for automated risk-based workflows. Discovers IPs, DNS domains, open ports, ASNs, networks, and cloud misconfigurations (AWS, Azure) [citation:5][citation:12].  
**Best for:** Organizations wanting validated, exploitability-tested findings rather than automated-only discovery.

### CyCognito
**Type:** Active-testing EASM  
Differentiates from pure discovery products by running dynamic application security testing (DAST) against web applications across the entire external surface. Uses attacker-like reconnaissance to map business structure and find assets across subsidiaries and acquisitions. Multi-pass, multi-engine testing architecture. Contextualizes and classifies assets, then prioritizes based on exploit intelligence and attack path visualization. Scanning cadence configurable from daily to monthly [citation:1].  
**Best for:** Teams whose priority question after discovery is whether an exposure is exploitable right now.

### ProjectDiscovery Cloud
**Type:** Community-driven security scanning platform  
Built by the team behind Nuclei, subfinder, httpx, and 20+ open-source security tools. The Free tier connects Nuclei scans to the cloud platform for viewing findings (up to 1K/month), vulnerability retesting, and sharing. Pay-as-you-go starts at $200/seat/month with weekly usage allowances. Enterprise adds on-prem/VPC deployment, SSO/SAML, BYOK, and dedicated support. The underlying tools are the most-used offensive security stack on the internet [citation:6][citation:13].  
**Best for:** Security engineers and bug bounty hunters already using ProjectDiscovery's open-source tools.

### Mandiant Advantage ASM
**Type:** Threat-intelligence-backed ASM  
Scans corporate assets and cloud resources daily, identifying application and service technologies. Assesses exposure risks, assigns severity, and creates incidents within Cortex XSOAR. Integrates with Splunk for threat intelligence correlation. Combines comprehensive visibility of the extended enterprise with Mandiant's industry-leading threat research and incident response expertise [citation:7][citation:14].  
**Best for:** Organizations wanting ASM tightly coupled with threat intelligence and incident response capabilities.

---

## 🟩 Open-Source Software

Self-hosted, community-driven EASM tools. All listed projects offer source code you can deploy on your own infrastructure.

### IVRE
**Stack:** Python | **License:** Open Source (per GitHub)  
A network recon framework for building your own self-hosted, fully-controlled alternative to Shodan, ZoomEye, Censys, and GreyNoise. Supports passive DNS, custom EASM tooling, and network intelligence collection from your own sensors. Uses Nmap, Masscan, Zeek, p0f, and ProjectDiscovery tools. 4,000+ GitHub stars with active maintenance [citation:19].  
**Best for:** Teams wanting to build a fully controlled internet scanning and intelligence platform without relying on third-party data.

### OWASP Amass
**Stack:** Go | **License:** Apache 2.0  
The OWASP Amass Project performs network mapping of attack surfaces and external asset discovery using open-source information gathering and active reconnaissance techniques. Aggregates data from 50+ APIs (Shodan, VirusTotal, SecurityTrails, etc.), certificate transparency logs, DNS brute forcing, routing data, web scraping, and web archives. Used by Accenture's adversary simulation team and Visma's red team for infrastructure enumeration. Installable via Homebrew, Docker, or Go [citation:20].  
**Best for:** Penetration testers and red teams needing comprehensive, API-rich subdomain and asset enumeration.

### reNgine
**Stack:** Python | **License:** Open Source (per GitHub)  
An automated reconnaissance framework for web applications with a focus on highly configurable streamlined recon processes via Engines. Features recon data correlation and organization, continuous monitoring, database-backed results, and an intuitive User Interface. Makes it easy for penetration testers to gather reconnaissance with minimal configuration [citation:26].  
**Best for:** Penetration testers wanting a visual, database-backed recon workflow.

### Osmedeus
**Stack:** Go | **License:** MIT  
An offensive security reconnaissance framework that automates the workflow of reconnaissance and vulnerability scanning. 6,000+ GitHub stars. Provides a comprehensive, automated approach to attack surface mapping and asset discovery for security assessments [citation:26].  
**Best for:** Security teams wanting an automated, end-to-end recon and scanning workflow.

### Xingrin
**Stack:** TypeScript | **License:** Open Source (per GitHub)  
An open-source attack surface management and authorized security automation platform for asset discovery, service probing, scan orchestration, and security result management. 671+ GitHub stars, updated September 2026 [citation:25][citation:30].  
**Best for:** Teams wanting a modern, TypeScript-based ASM platform with scan orchestration.

### LunaFox
**Stack:** (Check repository) | **License:** Open Source (per GitHub)  
An open-source, self-hosted attack surface management platform with distributed agents for asset discovery, scan orchestration, and vulnerability management. Updated recently with 53+ stars [citation:30].  
**Best for:** Teams needing distributed scanning across multiple network locations.

### OpenEASD
**Stack:** (Check repository) | **License:** Open Source (per GitHub)  
A self-hosted external attack surface scanner that shows what attackers see: subdomains, takeovers, open ports, CVEs ranked by EPSS/KEV, and TLS/SSH findings. Detection-only with a clear focus on external visibility [citation:25][citation:30].  
**Best for:** Teams wanting a focused, detection-only external scanner with EPSS/KEV prioritization.

### Open-ASM
**Stack:** (Check repository) | **License:** Open Source (per GitHub)  
An open-source Attack Surface Management platform for discovering assets, identifying exposure, and owning your security data. 259+ stars, updated October 2026 [citation:30].  
**Best for:** Organizations wanting a self-hosted ASM foundation they can extend and customize.

---

## 📊 Comparison at a Glance

| Software | License | Type | Internet-Wide Scan | Active Testing | Best For |
|----------|---------|------|-------------------|----------------|----------|
| **Falcon ASM** | Proprietary | AI-native EASM | ❌ | Limited | CrowdStrike ecosystem |
| **Cortex Xpanse** | Proprietary | Active ASM | ✅ (IPv4-wide) | ❌ | Palo Alto ecosystem, scale |
| **Censys** | Proprietary | Internet intelligence | ✅ | Limited | AI agent integration |
| **Defender EASM** | Proprietary | Cloud EASM | ❌ (seed-based) | Limited | Microsoft/Azure estates |
| **Rapid7 Surface** | Proprietary | Dynamic EASM | ✅ (IPv4) | ❌ | CTEM alignment |
| **Recorded Future** | Proprietary | Intelligence EASM | ❌ | ❌ | Threat-intel prioritization |
| **NetSPI EASM** | Proprietary | Human-led ASM | ❌ | ✅ (pentesting) | Validated findings |
| **CyCognito** | Proprietary | Active-testing EASM | ❌ | ✅ (DAST) | Exploitability validation |
| **ProjectDiscovery** | Proprietary | Community-driven | ❌ | Via Nuclei | Existing OSS users |
| **Mandiant ASM** | Proprietary | Intel-backed ASM | ❌ | ❌ | Threat intel + IR |
| **IVRE** | Open Source | Recon framework | ✅ (self-built) | Via tools | Full control / self-hosted |
| **OWASP Amass** | Apache 2.0 | Asset discovery | ❌ | ❌ | Pen testers / red teams |
| **reNgine** | Open Source | Recon framework | ❌ | Via engines | Visual recon workflow |
| **Osmedeus** | MIT | Recon automation | ❌ | ✅ (automated) | Automated offensive recon |
| **Xingrin** | Open Source | ASM platform | ❌ | Via orchestration | TypeScript-based ASM |
| **OpenEASD** | Open Source | External scanner | ❌ | ❌ (detection) | EPSS/KEV prioritization |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source External Attack Surface Management tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
