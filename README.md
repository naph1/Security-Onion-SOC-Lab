# \# 🛡️ Enterprise Security Operations \& Threat Hunting Lab: Security Onion

# \*\*Personal SOC Home Lab | 2026\*\*

# 

# An isolated, documented Security Operations Center (SOC) lab built to evaluate network telemetry, intrusion detection, alert triage, and incident investigation workflows. Powered by \*\*Security Onion\*\*, \*\*Suricata\*\*, \*\*Zeek\*\*, and the \*\*Elastic Stack\*\*.

# 

# > \*\*Reconstruction Note:\*\* The original virtual-machine files and raw logs are no longer available. This repository reconstructs project documentation from telemetry and case-file evidence published on the author's portfolio website and CV. It does not claim to contain original VM images, packet captures, raw event records, or reproducible configuration exports. Any future recreated demonstrations should be labelled as reproductions.

# 

# \---

# 

# \## 🏗️ Project Overview

# 

# The lab leveraged a dedicated virtual network architecture to segregate simulated threat traffic from host systems. \*\*Kali Linux\*\* acted as the controlled offensive testing framework, while \*\*Security Onion\*\* performed centralized network monitoring and threat detection. Target assets included \*\*Ubuntu Server\*\*, \*\*Windows endpoints\*\*, and a \*\*DVWA\*\* (Damn Vulnerable Web Application) target.

# 

# The published portfolio case file records \*\*951 total hits observed\*\*, \*\*two detection engines\*\*, \*\*four attack categories\*\*, and \*\*four VM roles\*\*. These metrics reflect documented portfolio evidence and are presented as observed lab telemetry rather than independently regenerated runtime results.

# 

# \---

# 

# \## 🎯 Objectives

# 

# \* Monitor and inspect packet-level network activity within an isolated laboratory environment.

# \* Generate controlled reconnaissance, authentication brute-force, and web-application attack vectors.

# \* Review \*\*Suricata\*\* intrusion detection signatures and correlate them with \*\*Zeek\*\* connection metadata.

# \* Utilize \*\*Elastic/Kibana\*\* dashboards and visualizers to dissect event distributions and attack timelines.

# \* Investigate structured SSH authentication failures, compile empirical evidence, and document containment recommendations.

# \* Practice precise methodologies for distinguishing benign background traffic from actionable security anomalies.

# 

# \---

# 

# \## 🛠️ Environment and Tooling Stack

# 

# | Component | Role Documented in the Project |

# | :--- | :--- |

# | \*\*Security Onion\*\* | Unified network monitoring, threat hunting, and detection platform |

# | \*\*Suricata\*\* | Open-source network intrusion detection and alert generation engine |

# | \*\*Zeek\*\* | High-performance network analysis and protocol metadata framework |

# | \*\*Elastic Stack / Kibana\*\* | Centralized event logging, indexing, search, and data visualization |

# | \*\*Kali Linux\*\* | Controlled offensive testing and threat emulation machine |

# | \*\*Ubuntu Server\*\* | Monitored Linux host target |

# | \*\*Windows\*\* | Monitored enterprise endpoint target |

# | \*\*DVWA\*\* | Deliberately vulnerable web application target for HTTP-based exploits |

# 

# \---

# 

# \## 📐 Lab Topology \& Architecture

# 

# The project environment organizes four core virtual machine roles across an isolated virtual network, separating the attack simulation layer, the monitoring core, and the target systems:

# 

# ```text

# &#x20;                    Isolated Virtual Network

# &#x20;                               |

# &#x20;      +------------------------+------------------------+

# &#x20;      |                        |                        |

# ┌──────────────┐        ┌────────────────┐        ┌───────────────────────

# │ Attack Sim   │        │ Monitoring Core│        │ Monitored Target      │

# │ Layer        │        │                │        │ Systems               │

# │              │        │ Security Onion │        │ • Ubuntu Server       │

# │ • Kali Linux │───────>│ • Suricata     │───────>│ • Windows Endpoint    │

# │   (Offensive │        │ • Zeek         │        │ • DVWA Target         │

# │    Testing)  │        │ • Elastic Stack│        │                       │

# └──────────────┘        └────────────────┘        └───────────────────────

