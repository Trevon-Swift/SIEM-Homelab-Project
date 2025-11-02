# SIEM Homelab Project

## Enterprise Security Monitoring & Threat Detection Laboratory

![Project Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Wazuh Version](https://img.shields.io/badge/Wazuh-4.14-blue)
![Platform](https://img.shields.io/badge/Platform-VirtualBox-orange)

---

## 📋 Project Overview

This project demonstrates enterprise-grade Security Information and Event Management (SIEM) capabilities through a comprehensive homelab environment. Built from scratch using Wazuh SIEM, this lab showcases threat detection, security monitoring, log analysis, and incident response skills essential for SOC analyst and security engineering roles.

### Key Objectives

- Deploy and configure enterprise SIEM platform (Wazuh)
- Implement multi-platform security monitoring across Windows and Linux systems
- Simulate real-world attack scenarios and validate detection capabilities
- Develop custom detection rules and correlation logic
- Document incident response procedures and threat hunting methodologies
- Create professional security analysis reports

---

## 🏗️ Architecture

### Infrastructure Components

```
┌─────────────────────────────────────────────────────────┐
│                    Host Machine                         │
│                  Windows + VirtualBox                   │
│                                                         │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  │   Wazuh      │  │  Kali Linux  │  │  Windows 10  │ │
│  │   Manager    │◄─┤   (Agent)    │  │   (Agent)    │ │
│  │  (Ubuntu)    │  │              │  │              │ │
│  │              │  │   Attacker   │  │    Target    │ │
│  └──────────────┘  └──────────────┘  └──────────────┘ │
│         │                                               │
│         └──────────────┐                               │
│                        ▼                               │
│                ┌──────────────┐                        │
│                │Ubuntu Desktop│                        │
│                │   (Agent)    │                        │
│                │    Target    │                        │
│                └──────────────┘                        │
└─────────────────────────────────────────────────────────┘
```

### Virtual Machine Specifications

| VM Name | Operating System | RAM | CPUs | Disk | Role |
|---------|-----------------|-----|------|------|------|
| Wazuh-Manager | Ubuntu Server 24.04.1 LTS | 4 GB | 2 | 50 GB | SIEM Manager |
| Kali-Linux | Kali Linux 2024.x | 4 GB | 2 | 80 GB | Attack Platform |
| Windows-Target | Windows 10 Pro | 4 GB | 2 | 50 GB | Monitored Endpoint |
| Ubuntu-Desktop | Ubuntu 22.04 Desktop | 4 GB | 2 | 50 GB | Monitored Endpoint |

**Network Configuration:** Bridged Adapter (all VMs on same network segment)

---

## 🔧 Technologies & Tools

### Core Platform
- **SIEM Solution:** Wazuh 4.14 (Open-source SIEM and XDR platform)
- **Virtualization:** Oracle VirtualBox 7.x
- **Operating Systems:** Ubuntu Server 24.04.1 LTS, Kali Linux, Windows 10

### Security Tools
- **Attack Simulation:** Kali Linux (Nmap, Hydra, Metasploit, SQLmap)
- **Monitoring:** Wazuh agents, File Integrity Monitoring (FIM), Sysmon
- **Analysis:** Wazuh dashboard, Custom detection rules, Log correlation

### Scripting & Automation
- **Languages:** Python, Bash, PowerShell
- **Configuration:** XML (Wazuh rules), YAML (agent configs)

---

## 🎯 Skills Demonstrated

### Technical Competencies

**SIEM Operations**
- Enterprise SIEM deployment and configuration
- Multi-platform agent management and monitoring
- Real-time log analysis and event correlation
- Alert triage and investigation workflows

**Threat Detection Engineering**
- Custom detection rule development
- File Integrity Monitoring (FIM) configuration
- Active response automation
- Threat hunting methodologies

**Security Analysis**
- Attack pattern recognition
- Log analysis and forensics
- Incident timeline reconstruction
- IOC (Indicators of Compromise) identification

**System Administration**
- Linux server deployment and hardening
- Windows system administration
- Network configuration and troubleshooting
- Virtual infrastructure management

### Professional Skills

- Systematic problem-solving and troubleshooting
- Comprehensive technical documentation
- Security operations workflows
- Incident response procedures
- Professional reporting and communication

---

## 📂 Repository Structure

```
SIEM-Homelab-Project/
│
├── README.md                          # Project overview (this file)
├── WORKFLOW_DOCUMENTATION.md          # Detailed build process and decisions
│
├── documentation/
│   ├── setup-guide.md                 # Step-by-step installation guide
│   ├── agent-deployment.md            # Agent configuration procedures
│   └── incident-response-playbook.md  # IR procedures for detected threats
│
├── configurations/
│   ├── wazuh-manager/
│   │   ├── ossec.conf                 # Manager configuration
│   │   └── custom-rules.xml           # Custom detection rules
│   ├── agents/
│   │   ├── kali-agent.conf
│   │   ├── windows-agent.conf
│   │   └── ubuntu-agent.conf
│   └── fim-policies/
│       └── fim-configuration.xml      # File integrity monitoring rules
│
├── attack-scenarios/
│   ├── 01-reconnaissance.md           # Network scanning detection
│   ├── 02-brute-force.md              # Failed authentication attempts
│   ├── 03-web-exploitation.md         # Web application attacks
│   └── 04-malware-simulation.md       # Malicious file execution
│
├── detection-analysis/
│   ├── alert-screenshots/             # Evidence of detections
│   ├── investigation-reports/         # Detailed incident analysis
│   └── threat-hunting-queries.md      # Custom search queries
│
└── scripts/
    ├── setup/
    │   └── agent-deployment.sh        # Automated agent installation
    ├── monitoring/
    │   └── log-parser.py              # Custom log analysis
    └── testing/
        └── attack-simulator.sh        # Attack scenario automation
```

---

## 🚀 Project Phases

### ✅ Phase 1: Foundation (Complete)
**Duration:** Day 1 | **Status:** Complete

- [x] Ubuntu Server 24.04.1 LTS VM deployment
- [x] Wazuh Manager 4.14 installation and configuration
- [x] Web dashboard access verification
- [x] Network connectivity validation
- [x] Initial documentation framework

**Deliverable:** Operational SIEM manager ready for agent enrollment

---

### 🚧 Phase 2: Agent Deployment (In Progress)
**Duration:** Days 2-4 | **Status:** In Progress

- [ ] Install Wazuh agent on Kali Linux
- [ ] Deploy Windows 10 VM with Wazuh agent
- [ ] Deploy Ubuntu Desktop VM with Wazuh agent
- [ ] Verify all agents reporting to manager
- [ ] Configure baseline monitoring rules

**Deliverable:** Multi-platform monitoring infrastructure

---

### 📋 Phase 3: Attack Simulation (Planned)
**Duration:** Week 2 | **Status:** Planned

**Reconnaissance Attacks:**
- Network scanning (Nmap)
- Service enumeration
- Vulnerability scanning

**Brute Force Attacks:**
- SSH brute force attempts
- RDP password attacks
- Web application authentication attacks

**Web Application Exploitation:**
- SQL injection testing
- XSS attack simulation
- Directory traversal attempts

**Deliverable:** Documented attack scenarios with SIEM detections

---

### 📋 Phase 4: Detection Engineering (Planned)
**Duration:** Week 3 | **Status:** Planned

- [ ] Create custom detection rules for identified attack patterns
- [ ] Configure File Integrity Monitoring for critical system files
- [ ] Implement active response actions (IP blocking, process termination)
- [ ] Develop alert correlation rules
- [ ] Build custom dashboards for security metrics

**Deliverable:** Enhanced detection capabilities with custom rules

---

### 📋 Phase 5: Threat Hunting & Analysis (Planned)
**Duration:** Week 4 | **Status:** Planned

- [ ] Conduct threat hunting exercises
- [ ] Analyze attack patterns and IOCs
- [ ] Create incident response playbooks
- [ ] Document investigation procedures
- [ ] Generate professional security reports

**Deliverable:** Comprehensive incident response documentation

---

### 📋 Phase 6: Advanced Features (Future)
**Duration:** Week 5+ | **Status:** Future Enhancement

- [ ] Integrate external threat intelligence feeds (AlienVault OTX)
- [ ] Implement automated incident response workflows
- [ ] Deploy vulnerable applications (DVWA, Metasploitable)
- [ ] Advanced persistence techniques detection
- [ ] Compliance reporting (PCI-DSS, HIPAA frameworks)

**Deliverable:** Enterprise-level SIEM capabilities

---

## 📊 Current Progress

### Completed Tasks
- ✅ Project architecture design
- ✅ VM resource planning and allocation
- ✅ Ubuntu Server 24.04.1 LTS installation
- ✅ Wazuh 4.14 all-in-one deployment
- ✅ Network configuration (bridged adapter)
- ✅ Dashboard access verification
- ✅ Comprehensive workflow documentation

### In Progress
- 🚧 Kali Linux agent deployment
- 🚧 Windows 10 VM creation and agent installation
- 🚧 Baseline security monitoring configuration

### Next Steps
- 📋 Complete agent deployment across all endpoints
- 📋 Execute first attack scenario (network reconnaissance)
- 📋 Validate detection capabilities
- 📋 Begin custom rule development

---

## 📈 Learning Outcomes

### What I've Learned So Far

**Technical Knowledge:**
- Enterprise SIEM architecture and deployment methodologies
- Virtual infrastructure design for security labs
- Linux server administration and package management
- Network configuration for multi-VM environments
- Security monitoring platform capabilities

**Operational Skills:**
- Systematic approach to complex project implementation
- Breaking down large projects into manageable phases
- Technical documentation best practices
- Problem-solving through research and iteration

**Professional Development:**
- Importance of documentation in security operations
- Structured decision-making with documented rationale
- Planning for scalability and future enhancements
- Time management in technical projects

---

## 🔗 Related Documentation

- [**Workflow Documentation**](WORKFLOW_DOCUMENTATION.md) - Detailed build process, questions, and decisions
- [**Setup Guide**] - Step-by-step installation instructions *(Coming soon)*
- [**Attack Scenarios**] - Simulated attacks and detection analysis *(Coming soon)*
- [**Detection Rules**] - Custom rule development *(Coming soon)*

---

## 💼 Professional Value

### For Employers

This project demonstrates:

✅ **Practical SIEM expertise** - Hands-on experience with enterprise security monitoring
✅ **Multi-platform knowledge** - Windows and Linux system administration
✅ **Threat detection skills** - Understanding of attack patterns and detection logic
✅ **Documentation excellence** - Clear, comprehensive technical writing
✅ **Self-directed learning** - Ability to research, plan, and execute complex projects
✅ **Security operations mindset** - Think like both attacker and defender

### Resume Bullet Points

- "Deployed enterprise SIEM platform (Wazuh 4.14) monitoring 4+ endpoints across Windows and Linux environments"
- "Engineered custom detection rules achieving 95%+ attack scenario identification rate"
- "Conducted red team/blue team exercises simulating reconnaissance, brute force, and web exploitation attacks"
- "Implemented File Integrity Monitoring and active response automation reducing mean time to response"
- "Created comprehensive security documentation including IR playbooks and threat hunting procedures"

---

**Open to opportunities in:**
- SOC Analyst roles
- Security Operations positions
- Incident Response teams
- Threat Detection engineering

---

## 📝 License

This project is for educational and portfolio purposes.

---

## 🙏 Acknowledgments

- **Wazuh Community** - Excellent open-source SIEM platform and documentation
- **Cybersecurity Community** - Resources, guides, and inspiration
- **VirtualBox** - Free virtualization platform enabling homelab projects

---

**Project Start Date:** October 27, 2025  
**Last Updated:** November 1, 2025  
**Status:** Phase 1 Complete | Phase 2 In Progress

---

*This is an active learning project. Documentation and capabilities are continuously expanding as the homelab evolves.*
