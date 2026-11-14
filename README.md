# Security Onion SOC Lab: Network Monitoring and Threat Investigation

**Personal SOC home lab | Portfolio documentation**

An isolated lab project documenting network monitoring, intrusion-detection review, alert triage, and investigation workflows using Security Onion, Suricata, Zeek, and Elastic/Kibana.

> **Reconstruction and evidence note:** The original virtual-machine files, raw logs, packet captures, and configuration exports are no longer available. This repository reconstructs the project documentation from the author's published portfolio case file and CV. It does not claim to contain original runtime artifacts or to be independently reproducible from the files in this repository. The observations and metrics below are reported from the published portfolio material. Any future rebuilt lab, screenshots, logs, or demonstrations must be clearly labelled as a reproduction rather than original evidence.

## Project overview

The project used a dedicated virtual network to keep simulated testing traffic separate from the host environment. Kali Linux was used for controlled security testing, while Security Onion provided the monitoring and detection platform. The documented virtual-machine roles were Security Onion, Kali Linux, Ubuntu Server, and Windows. DVWA (Damn Vulnerable Web Application) was used as a vulnerable web-application target; the surviving project information does not establish whether it was hosted on a separate VM or on one of the existing target systems.

The published portfolio case file reports:

- **951 total hits observed**
- **2 detection engines**
- **4 attack categories**
- **4 virtual-machine roles**

These are portfolio-reported observations, not fresh measurements reproduced from raw telemetry in this repository.

## Objectives

- Review network activity and security telemetry in an isolated lab.
- Generate controlled reconnaissance, authentication brute-force, and web-application test traffic.
- Review Suricata alerts and correlate relevant activity with Zeek connection metadata.
- Use Elastic/Kibana dashboards and searches to examine event patterns and timelines.
- Investigate repeated SSH authentication failures and document the assessment and recommended response.
- Distinguish controlled test activity and benign background traffic from events requiring further investigation.

## Environment and tools

| Component | Documented role |
|---|---|
| Security Onion | Central network monitoring and security analysis platform |
| Suricata | Network intrusion-detection alerts |
| Zeek | Network connection and protocol metadata |
| Elastic Stack / Kibana | Event search, analysis, and visualization |
| Kali Linux | Controlled offensive testing / traffic generation |
| Ubuntu Server | Monitored Linux host role |
| Windows | Monitored endpoint role |
| DVWA | Deliberately vulnerable web application used for web-security testing; hosting arrangement is unconfirmed |

## Conceptual lab layout

The diagram below describes the documented functional roles, not a recovered network diagram or a verified physical topology.

```text
                   Isolated virtual lab network
                              |
          +-------------------+-------------------+
          |                   |                   |
   +-------------+     +---------------+    +------------------+
   | Kali Linux  | --> | Security      |    | Monitored targets|
   | Test source |     | Onion         |    | Ubuntu Server    |
   +-------------+     | - Suricata    |    | Windows          |
                       | - Zeek         |    | DVWA web target* |
                       | - Elastic/     |    +------------------+
                       |   Kibana       |
                       +---------------+

   *DVWA was documented as a target; its hosting arrangement is
    not established by the surviving project records.
```

## Documented testing and investigation areas

1. Network reconnaissance using Nmap.
2. SSH authentication brute-force simulation.
3. Web-application testing against DVWA.
4. Review of Suricata alerts and related Zeek connection metadata.
5. Investigation of repeated SSH authentication failures.

See [`attack-scenarios/`](attack-scenarios/) for scenario summaries and [`investigations/`](investigations/) for the documented SSH case study.

## Investigation workflow

1. Identify an alert or unusual activity pattern.
2. Establish the relevant time window and affected systems.
3. Review the detection details, including signature, source/destination information, port, and protocol where available.
4. Correlate with Zeek connection metadata to add network context.
5. Determine whether the activity matches a controlled lab test, benign activity, or an event requiring escalation.
6. Record supporting observations, uncertainty, and recommended containment or follow-up actions.

This is a summary of the workflow described in the portfolio and CV, not a claim that original logs are included here.

## Evidence and provenance

The portfolio case file contains supporting screenshots and project context:

- [Security Onion lab case file](https://naphtali-portfolio.netlify.app/security-onion-lab)
- [Hunt / alert evidence image](https://naphtali-portfolio.netlify.app/images/onion-hunt.png)
- [Dashboard evidence image](https://naphtali-portfolio.netlify.app/images/onion-dashboards.png)
- [Alert breakdown evidence image](https://naphtali-portfolio.netlify.app/images/onion-breakdown.png)

The images are linked from the portfolio site; they are not repackaged as original raw telemetry in this repository. See [`evidence/README.md`](evidence/README.md) and [`sources/README.md`](sources/README.md).

## Limitations

- Original VM images, raw logs, PCAPs, and configuration exports are unavailable.
- Exact IP addresses, timestamps, full alert records, and complete packet-level evidence cannot be reconstructed reliably from the surviving summary material.
- The precise DVWA hosting arrangement is unconfirmed.
- The architecture diagram is conceptual and should not be interpreted as a recovered network topology.
- This repository is documentation of a completed personal lab, not a deployable lab bundle or a production SOC implementation.

## Suggested future improvements

If the lab is rebuilt, add clearly labelled reproduction evidence such as sanitized alert exports, sample PCAPs, Zeek logs, screenshots, a network diagram with verified addressing, and step-by-step setup notes. Do not present newly generated artifacts as evidence from the original lab.

## Repository structure

```text
security-onion-soc-lab/
├── README.md
├── docs/
│   ├── lab-architecture.md
│   ├── environment-setup.md
│   ├── detection-workflow.md
│   └── investigation-methodology.md
├── investigations/
│   └── ssh-brute-force-investigation.md
├── attack-scenarios/
│   ├── reconnaissance.md
│   ├── brute-force.md
│   └── web-attacks.md
├── evidence/
│   └── README.md
├── sources/
│   └── README.md
└── .gitignore
```
