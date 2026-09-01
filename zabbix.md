# Zabbix

## 📌 Overview

**Zabbix** is an **open-source enterprise IT infrastructure monitoring and observability platform**. It is used to monitor the availability, performance, health, and behavior of IT infrastructure.

Zabbix can monitor:

* 🖥️ Servers
* 🌐 Network devices
* ☁️ Cloud infrastructure
* 🗄️ Databases
* 📦 Applications
* 🖥️ Virtual machines
* 💾 Storage systems
* 🌍 Websites
* 🔌 IoT devices

> **In simple words:** Zabbix continuously monitors IT infrastructure and alerts administrators when something goes wrong.

---

## 📑 Table of Contents

* [What is Zabbix?](#what-is-zabbix)
* [Key Information](#key-information)
* [What Does Zabbix Monitor?](#what-does-zabbix-monitor)
* [Zabbix Architecture](#zabbix-architecture)
* [Major Components](#major-components)
* [Important Zabbix Concepts](#important-zabbix-concepts)
* [How Zabbix Works](#how-zabbix-works)
* [Monitoring Methods](#monitoring-methods)
* [Alerts and Notifications](#alerts-and-notifications)
* [Dashboards and Visualization](#dashboards-and-visualization)
* [Network Discovery](#network-discovery)
* [Zabbix API](#zabbix-api)
* [Zabbix in DevOps](#zabbix-in-devops)
* [Advantages](#advantages)
* [Challenges](#challenges)
* [Zabbix vs Dynatrace](#zabbix-vs-dynatrace)
* [Use Cases](#use-cases)
* [Important Terms](#important-terms)
* [Learning Path](#learning-path)
* [Useful Resources](#useful-resources)
* [Conclusion](#conclusion)

---

# What is Zabbix?

Zabbix is an **open-source monitoring solution** designed to collect, process, visualize, and analyze monitoring data from IT infrastructure.

It continuously collects metrics such as:

* CPU utilization
* Memory utilization
* Disk usage
* Network traffic
* System availability
* Application performance
* Interface status
* Temperature
* Processes and services

When a monitored value reaches a predefined condition, Zabbix can generate an event and notify the responsible team.

---

# Key Information

| Property                  | Details                                 |
| ------------------------- | --------------------------------------- |
| **Software**              | Zabbix                                  |
| **Category**              | IT Infrastructure Monitoring            |
| **Developer**             | Zabbix SIA                              |
| **Founder**               | Alexei Vladishev                        |
| **Initial Development**   | 2001                                    |
| **First Release**         | 2001                                    |
| **License**               | AGPLv3                                  |
| **Source Code**           | Open Source                             |
| **Monitoring Type**       | Infrastructure & Application Monitoring |
| **Current Stable Branch** | Zabbix 7.4                              |
| **Latest 7.4 Release**    | 7.4.14                                  |

---

# What Does Zabbix Monitor?

## 1. Servers

Zabbix can monitor Windows and Linux servers.

Typical metrics include:

* CPU usage
* RAM usage
* Disk usage
* Disk I/O
* Network traffic
* Running processes
* Services
* System uptime
* File systems

Example:

```text
Server
  |
  +-- CPU Usage
  +-- Memory Usage
  +-- Disk Usage
  +-- Network Traffic
  +-- Processes
  +-- Services
```

---

## 2. Network Devices

Zabbix can monitor network infrastructure such as:

* Routers
* Switches
* Firewalls
* Load balancers
* Printers
* UPS systems

It can monitor:

* Interface status
* Bandwidth
* Packet loss
* CPU
* Memory
* Temperature
* Interface errors

Zabbix provides strong **SNMP monitoring**, making it useful for network infrastructure.

---

## 3. Applications

Zabbix can monitor applications for:

* Availability
* Response time
* Performance
* Processes
* Application metrics
* Service status

---

## 4. Databases

Zabbix can monitor database availability and performance metrics using appropriate templates, agents, plugins, and monitoring methods.

---

## 5. Virtualization

Zabbix supports monitoring of virtualization environments, including **VMware** infrastructure.

---

## 6. Websites

Zabbix provides web monitoring capabilities for checking:

* Website availability
* Response time
* HTTP status
* Multi-step web scenarios

---

# Zabbix Architecture

A simplified Zabbix architecture is:

```text
                     +----------------------+
                     |     Zabbix Web UI    |
                     | Dashboards / Graphs  |
                     | Alerts / Reports     |
                     +----------+-----------+
                                |
                                v
                     +----------------------+
                     |    Zabbix Server     |
                     |                      |
                     | Data Collection      |
                     | Data Processing      |
                     | Trigger Evaluation   |
                     | Event Processing     |
                     | Alerting             |
                     +----------+-----------+
                                |
                                v
                     +----------------------+
                     |       Database       |
                     |                      |
                     | History              |
                     | Trends               |
                     | Configuration        |
                     | Events               |
                     +----------------------+
                                ^
                                |
              +-----------------+----------------+
              |                                  |
      +-------+--------+                 +-------+--------+
      |  Zabbix Agent  |                 |  Zabbix Proxy  |
      +-------+--------+                 +-------+--------+
              |                                  |
              v                                  v
        Servers / OS                     Remote Networks
```

---

# Major Components

## 1. Zabbix Server

The **Zabbix Server** is the central component of the monitoring system.

Responsibilities include:

* Receiving monitoring data
* Processing data
* Evaluating triggers
* Generating events
* Sending alerts
* Managing configuration
* Communicating with agents and proxies

---

## 2. Zabbix Agent

The **Zabbix Agent** is software installed on a monitored server.

It collects local information such as:

* CPU utilization
* Memory utilization
* Disk usage
* Network statistics
* Processes
* Services

Example:

```text
Linux Server
     |
     +-- Zabbix Agent
             |
             +-- CPU = 75%
             +-- RAM = 82%
             +-- Disk = 90%
                     |
                     v
               Zabbix Server
```

---

## 3. Zabbix Agent 2

**Zabbix Agent 2** is the newer generation of the Zabbix agent.

It is written in **Go** and uses a plugin-based architecture.

It provides additional flexibility for monitoring modern applications and infrastructure.

---

## 4. Zabbix Proxy

A **Zabbix Proxy** collects monitoring information from remote infrastructure and forwards it to the Zabbix Server.

Example:

```text
                    Zabbix Server
                          |
             +------------+------------+
             |            |            |
          Proxy A      Proxy B      Proxy C
             |            |            |
         Servers       Servers      Network
         Network       Network      Devices
```

A proxy is useful for:

* Remote locations
* Large environments
* Distributed infrastructure
* Reducing Zabbix Server workload
* Networks with unreliable connections

---

## 5. Zabbix Database

The database stores Zabbix configuration and monitoring information.

It can contain:

* Host configuration
* Items
* Triggers
* Events
* Problems
* Historical data
* Trends
* User configuration

---

## 6. Zabbix Web Interface

The Web UI provides access to:

* Dashboards
* Graphs
* Problems
* Hosts
* Configuration
* Monitoring data
* Reports
* Administration

---

# Important Zabbix Concepts

Understanding these concepts is essential for learning Zabbix.

## Host

A **Host** represents a device or system being monitored.

Examples:

```text
WEB-SERVER-01
DATABASE-SERVER-01
CORE-SWITCH-01
```

---

## Item

An **Item** defines what data Zabbix should collect.

Examples:

```text
CPU utilization
Memory utilization
Disk usage
Network traffic
```

---

## Trigger

A **Trigger** defines a condition that indicates a problem.

Example:

```text
CPU utilization > 90%
```

When the condition becomes true, Zabbix generates a problem/event.

---

## Event

An **Event** represents something that happened in the monitored environment.

Example:

```text
CPU utilization exceeded 90%
```

---

## Action

An **Action** specifies what Zabbix should do when an event occurs.

Example:

```text
Trigger
   |
   v
CPU > 90%
   |
   v
Problem
   |
   v
Action
   |
   +----> Send Email
   |
   +----> Send Notification
   |
   +----> Execute Command
```

---

## Template

A **Template** contains reusable monitoring configurations.

Templates can contain:

* Items
* Triggers
* Graphs
* Discovery rules
* Applications
* Macros

Instead of manually configuring every server, a template can be applied to multiple hosts.

```text
             Linux Template
                    |
        +-----------+-----------+
        |           |           |
        v           v           v
     Server 1    Server 2    Server 3
```

---

# How Zabbix Works

The basic Zabbix workflow is:

```text
Host
  |
  v
Item
  |
  v
Data Collection
  |
  v
Trigger
  |
  v
Event
  |
  v
Action
  |
  v
Alert / Notification
```

### Example

Suppose a server's disk usage reaches 90%.

```text
Disk Usage = 90%
       |
       v
Zabbix Item collects data
       |
       v
Trigger evaluates condition
       |
       v
Problem generated
       |
       v
Action executed
       |
       v
Administrator receives alert
```

---

# Monitoring Methods

Zabbix supports multiple monitoring technologies.

## Zabbix Agent

Used mainly for monitoring operating systems and servers.

---

## SNMP

**Simple Network Management Protocol (SNMP)** is widely used for monitoring network devices.

Common devices include:

* Cisco switches
* Cisco routers
* Juniper devices
* Firewalls
* Printers
* UPS systems

Zabbix supports:

* SNMP polling
* SNMP traps

---

## IPMI

**Intelligent Platform Management Interface (IPMI)** can be used for hardware-level monitoring.

---

## JMX

**Java Management Extensions (JMX)** can be used to monitor Java applications.

---

## VMware

Zabbix provides monitoring capabilities for VMware environments.

---

## HTTP/Web Monitoring

Zabbix can monitor web applications and websites.

---

## Custom Monitoring

Zabbix supports customized monitoring using various data collection methods, scripts, APIs, and integrations.

---

# Alerts and Notifications

One of Zabbix's most important features is alerting.

Example:

```text
CPU Usage > 90%
       |
       v
Trigger Activated
       |
       v
Problem Created
       |
       v
Action
       |
       +--------> Email
       |
       +--------> Notification
       |
       +--------> Automation
```

Alerts can be configured based on:

* Severity
* User
* Schedule
* Event
* Media type
* Escalation rules

---

# Dashboards and Visualization

Zabbix provides dashboards to visualize infrastructure health.

Dashboards can display:

* CPU utilization
* Memory usage
* Disk usage
* Network traffic
* Problems
* Availability
* Trends
* Performance metrics
* Network maps
* Reports

This helps administrators quickly understand the health of an IT environment.

---

# Network Discovery

Zabbix provides network discovery capabilities.

A network can contain:

```text
Network
   |
   +-- Router
   |
   +-- Switch
   |
   +-- Firewall
   |
   +-- Server
   |
   +-- Printer
```

Discovery can help automatically identify devices and interfaces.

This is particularly useful in large enterprise environments.

---

# Zabbix API

Zabbix provides an API for programmatic interaction with the monitoring platform.

The API can be used for:

* Creating hosts
* Updating configurations
* Retrieving monitoring data
* Managing users
* Automating configuration
* Integrating third-party applications

Example automation workflow:

```text
Python Script
     |
     v
Zabbix API
     |
     v
Create / Update Host
     |
     v
Apply Template
     |
     v
Start Monitoring
```

---

# Zabbix in DevOps

Monitoring is an important part of the DevOps lifecycle.

A typical DevOps environment can look like:

```text
Developer
    |
    v
Git Repository
    |
    v
CI/CD Pipeline
    |
    v
Application Deployment
    |
    v
Docker / Kubernetes / VM
    |
    v
Zabbix Monitoring
    |
    +----> Metrics
    |
    +----> Alerts
    |
    +----> Dashboards
    |
    v
DevOps Team
```

Zabbix can help DevOps teams detect:

* Application failures
* Server failures
* High CPU usage
* High memory usage
* Disk problems
* Network failures
* Service downtime
* Performance degradation

---

# Advantages

## 1. Open Source

Zabbix is open-source software distributed under the **AGPLv3 license**.

---

## 2. Cost Effective

The software itself does not require traditional proprietary monitoring licenses.

---

## 3. Highly Customizable

Administrators can create:

* Custom items
* Triggers
* Templates
* Dashboards
* Discovery rules
* Alerts

---

## 4. Strong Network Monitoring

Zabbix's SNMP capabilities make it particularly useful for monitoring network infrastructure.

---

## 5. Scalable

Zabbix is designed for environments ranging from small installations to large enterprise infrastructures.

---

## 6. Automation

Zabbix provides automation capabilities through:

* Actions
* API
* Discovery
* Autoregistration
* Templates

---

# Challenges

Although Zabbix is powerful, there are some challenges.

* Initial configuration can be complex
* Large installations require database planning
* Trigger expressions require learning
* Advanced monitoring requires knowledge of templates
* Large environments require careful architecture
* Custom dashboards may require additional configuration

> **Zabbix is relatively easy to start with, but advanced enterprise deployments require deeper technical knowledge.**

---

# Zabbix vs Dynatrace

| Feature                  | Zabbix                    | Dynatrace                |
| ------------------------ | ------------------------- | ------------------------ |
| Type                     | Infrastructure Monitoring | Full-Stack Observability |
| Open Source              | ✅ Yes                     | ❌ No                     |
| Traditional License Cost | Low/None for software     | Commercial               |
| Server Monitoring        | ⭐⭐⭐⭐⭐                     | ⭐⭐⭐⭐⭐                    |
| Network Monitoring       | ⭐⭐⭐⭐⭐                     | ⭐⭐⭐                      |
| SNMP                     | ⭐⭐⭐⭐⭐                     | ⭐⭐                       |
| Application Monitoring   | ⭐⭐⭐                       | ⭐⭐⭐⭐⭐                    |
| APM                      | Limited                   | ⭐⭐⭐⭐⭐                    |
| Customization            | ⭐⭐⭐⭐⭐                     | ⭐⭐⭐⭐                     |
| AI/Automation            | Good                      | Advanced                 |
| Best Use                 | Infrastructure & Network  | Full-Stack Observability |

### Simple Difference

**Zabbix:**

> Strong open-source infrastructure and network monitoring.

**Dynatrace:**

> Commercial full-stack observability and application performance monitoring.

---

# Use Cases

Zabbix can be used in:

* 🏦 Banking
* 🏢 Enterprise IT
* 🏫 Universities
* 🏭 Manufacturing
* 🏛️ Government organizations
* 📡 Telecom networks
* ☁️ Cloud environments
* 🖥️ Data centers
* 🌐 Network Operations Centers
* 🔧 Managed Service Providers

---

# Example Enterprise Environment

Consider an organization with:

```text
100 Linux Servers
50 Windows Servers
20 Cisco Switches
10 Routers
5 Firewalls
3 VMware Hosts
```

Zabbix can monitor the entire infrastructure.

```text
                    ZABBIX
                       |
        +--------------+--------------+
        |              |              |
     Servers        Network         VMware
        |              |              |
        +--------------+--------------+
                       |
                       v
                    Metrics
                       |
                       v
                    Triggers
                       |
                       v
                     Alerts
                       |
                       v
                  IT Engineers
```

For example, if a server's disk usage reaches 90%:

```text
Disk = 90%
   |
   v
Trigger Activated
   |
   v
Problem Created
   |
   v
Action Executed
   |
   v
Administrator Alerted
```

---

# Important Terms

| Term          | Meaning                                              |
| ------------- | ---------------------------------------------------- |
| **Host**      | Device/system being monitored                        |
| **Item**      | Metric collected from a host                         |
| **Trigger**   | Condition that identifies a problem                  |
| **Event**     | Something that happened in the monitored environment |
| **Action**    | Operation performed after an event                   |
| **Template**  | Reusable monitoring configuration                    |
| **Agent**     | Software installed on a monitored system             |
| **Agent 2**   | New-generation Zabbix monitoring agent               |
| **Proxy**     | Collects data from remote environments               |
| **SNMP**      | Protocol commonly used for network monitoring        |
| **Dashboard** | Visual monitoring interface                          |
| **Discovery** | Automatic discovery of infrastructure                |
| **API**       | Interface for programmatic automation                |

---

# Zabbix Learning Path

If you are learning Zabbix for **DevOps**, follow this sequence:

```text
1. What is Zabbix?
        |
        v
2. Zabbix Architecture
        |
        v
3. Zabbix Server
        |
        v
4. Zabbix Agent
        |
        v
5. Zabbix Agent 2
        |
        v
6. Zabbix Proxy
        |
        v
7. Hosts
        |
        v
8. Items
        |
        v
9. Triggers
        |
        v
10. Events
        |
        v
11. Actions
        |
        v
12. Templates
        |
        v
13. SNMP
        |
        v
14. Discovery
        |
        v
15. Dashboards
        |
        v
16. Alerts
        |
        v
17. API
        |
        v
18. Automation
```

---

# Useful Resources

### Official Website

https://www.zabbix.com/

### Documentation

https://www.zabbix.com/documentation/current/

### Downloads

https://www.zabbix.com/download

### GitHub

https://github.com/zabbix/zabbix

---

# Conclusion

**Zabbix is a powerful open-source monitoring and observability platform used to monitor IT infrastructure, networks, servers, applications, databases, virtual machines, websites, and other systems.**

Its basic monitoring workflow can be summarized as:

```text
Host
  ↓
Item
  ↓
Trigger
  ↓
Event
  ↓
Action
  ↓
Alert
```

The most important components are:

```text
Zabbix Server
Zabbix Agent
Zabbix Agent 2
Zabbix Proxy
Database
Web Interface
```

Zabbix is especially useful for **DevOps, System Administration, Network Administration, Infrastructure Monitoring, and NOC operations**.

> **Key Takeaway:** Zabbix continuously collects infrastructure metrics, evaluates conditions, visualizes system health, and automatically alerts teams when problems occur.
