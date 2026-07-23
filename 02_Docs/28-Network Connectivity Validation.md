# Day 28 – Network Connectivity Validation

## Overview

Before performing attack simulations and security monitoring, network connectivity between the lab systems was verified to ensure reliable communication across the internal environment.

This validation confirms that the attacker machine can successfully communicate with the target endpoint, providing a stable foundation for subsequent detection engineering and incident analysis.

---

## Objective

Validate network communication between the attack workstation and the Windows client before initiating attack simulations.

---

## Lab Systems

### Kali Linux

**Role:** Attack Workstation

**Network Adapters:**
- NAT
- Internal Network

---

### Windows 11 Enterprise

**Role:** Target Endpoint

**Network Adapter:**
- Internal Network

---

## Validation Activities

- Verified internal network configuration.
- Confirmed IP address assignment for both systems.
- Validated network reachability between the attacker and target machines.
- Enabled ICMP echo responses on the Windows endpoint to support connectivity testing.
- Confirmed successful communication across the internal network.

---

## Validation Result

Network connectivity was successfully established between Kali Linux and the Windows client.

The lab environment is fully operational and ready for attack simulation, log generation, and security monitoring within Splunk Enterprise.

---

## Outcome

The successful network validation confirms that the Enterprise SOC Lab environment is correctly configured to support controlled attack simulations and detection engineering activities in subsequent phases of the project.
