# Security Onion SOC Lab
### Network Security Monitoring, Detection Triage & SSH Brute-Force Investigation

A virtualized SOC lab documenting controlled security testing, network monitoring, alert triage, and investigation workflows using Security Onion, Suricata, Zeek, Elastic/Kibana, Kali Linux, Ubuntu Server, and Windows.

**Portfolio case file:** https://naphtali-portfolio.netlify.app/security-onion-lab  
**Repository:** https://github.com/naph1/Security-Onion-SOC-Lab

---

## Project overview

This project documents a four-VM lab environment used to explore how controlled network activity can be observed and investigated from a defensive monitoring platform.

The documented roles were:

| System | Lab role |
|---|---|
| Security Onion | Network security monitoring, alert review, hunting and investigation |
| Kali Linux | Controlled testing and traffic generation |
| Ubuntu Server | Monitored Linux server |
| Windows | Monitored Windows endpoint |

The documented testing included Nmap reconnaissance, controlled authentication/brute-force activity, and web-application testing involving DVWA. Security Onion's Suricata alerts were reviewed alongside Zeek connection metadata in Elastic/Kibana. A separate investigation write-up documents the analytical workflow used for an SSH brute-force alert.

> **Important provenance note:** This repository is a reconstructed documentation package based on the surviving project description, portfolio case file, and screenshots. The original virtual-machine files and raw runtime logs are unavailable. This repository therefore does **not** contain original VM images, original PCAPs, raw event records, or configuration exports. The documentation must not be treated as a forensic evidence archive or a reproducible copy of the original lab.

## What this project demonstrates

- Understanding of a small virtualized SOC monitoring environment.
- Use of Suricata alerts as detection leads.
- Use of Zeek connection metadata to add network context.
- Review and correlation of monitoring information in Elastic/Kibana.
- Triage-oriented analysis of SSH authentication brute-force activity.
- Controlled security testing with Nmap, authentication testing, and DVWA-related web activity.
- Clear documentation of evidence limitations and analytical confidence.

## Monitoring and analysis workflow

1. Generate controlled test traffic from the testing system.
2. Review the resulting network-security alerts and monitoring data in Security Onion.
3. Examine Suricata alert information.
4. Use Zeek connection metadata to add context to relevant network activity.
5. Review and correlate available information in Elastic/Kibana.
6. Document the investigation, observations, limitations, and recommended follow-up.

Suricata and Zeek serve complementary purposes: Suricata provides signature-based detection alerts, while Zeek provides structured network-activity metadata. Zeek should not be described as a second signature-based IDS engine.

## Reported portfolio metrics

The portfolio case file reports the following figures:

- **951 search hits** displayed in a Security Onion Hunt view.
- **Two network analysis components:** Suricata and Zeek.
- **Four attack categories** reported in the portfolio case file.

These are portfolio-reported figures, not counts independently recalculated from original telemetry. The individual labels for all four attack categories are not fully preserved in the available project material. The 951 figure should be read as the count displayed by the historical search view, not as a count of unique malicious events or confirmed incidents.

## Repository map

```text
Security-Onion-SOC-Lab/
├── README.md
├── .gitignore
├── .gitattributes
├── docs/
│   ├── lab-overview.md
│   ├── architecture-and-data-flow.md
│   └── testing-methodology.md
├── investigations/
│   └── ssh-brute-force-investigation.md
├── attack-scenarios/
│   ├── nmap-reconnaissance.md
│   ├── authentication-brute-force.md
│   └── dvwa-web-testing.md
├── evidence/
│   └── README.md
└── sources/
    └── README.md
```

## Evidence and reproducibility

The `evidence/README.md` file indexes the surviving portfolio screenshots and explains what they can and cannot establish. The screenshots are linked to the portfolio rather than copied into this archive because the original project artifacts were not available in the working materials used to prepare this package.

Do not infer missing IP addresses, hostnames, usernames, exact timestamps, commands, rule identifiers, event IDs, packet contents, or final attack outcomes. Where those details are not preserved, the reports explicitly say so.

## Safety and scope

The scenarios describe controlled testing in an isolated lab. They are documentation of previously performed learning activities, not instructions to target systems without authorization. Do not run scanning or authentication-testing commands against systems you do not own or have explicit permission to assess.

## Limitations

- Original VM images and snapshots are unavailable.
- Original PCAPs and raw event records are unavailable.
- Original Security Onion, Suricata, Zeek, Elastic, and Kibana configuration exports are unavailable.
- Exact network addressing, complete timestamps, individual alert identifiers, and all test parameters were not preserved in the available source material.
- The documentation is not a claim that the historical lab can be recreated exactly from this repository.

## Author

**Naphtali Peter**  
Cybersecurity | SOC Monitoring | Network Security

