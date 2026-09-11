# Wazuh Installation and Lab Setup

## 1. Project Overview

This project implements a small cybersecurity monitoring lab using Wazuh.

The objective is to deploy a centralized security monitoring platform capable of collecting and analyzing security events from a Windows endpoint.

The laboratory consists of:

* Ubuntu Server — Wazuh server
* Physical Windows laptop — monitored endpoint
* Kali Linux — controlled security testing machine

## 2. Lab Architecture

The architecture follows this data flow:

```text
Kali Linux
    |
    | Controlled security testing
    v
Windows Laptop
    |
    | Wazuh Agent
    v
Ubuntu Server
    |
    +-- Wazuh Manager
    +-- Wazuh Indexer
    +-- Wazuh Dashboard
```

The Windows laptop runs the Wazuh agent, which collects security-related telemetry and sends it to the Wazuh server.

The Ubuntu server hosts the main Wazuh components used for event processing, indexing and visualization.

Kali Linux is used as a controlled testing machine inside the laboratory.

## 3. Wazuh Server

The Wazuh server was deployed on Ubuntu Server.

The deployment uses the Wazuh all-in-one architecture, where the main components are installed on the same Ubuntu server.

The main components are:

### Wazuh Manager

Responsible for receiving and analyzing security events from monitored endpoints.

### Wazuh Indexer

Responsible for storing and indexing security events so that they can be searched and analyzed.

### Wazuh Dashboard

Provides the web interface used to visualize agents, events, rules and security alerts.

## 4. Windows Endpoint

The physical Windows laptop was configured with the Wazuh Agent.

The agent is registered with the Wazuh server and appears in the dashboard as:

`windows_victin`

The agent allows Windows security events and other supported telemetry to be forwarded to the Wazuh infrastructure.

## 5. Connectivity

The laboratory machines were configured so that the Kali testing environment, Windows endpoint and Ubuntu Wazuh server could communicate over the laboratory network.

Connectivity was verified before performing the security tests.

## 6. Verification

The Wazuh Manager and Wazuh Indexer were verified to be running on Ubuntu.

The Windows Wazuh Agent was also verified to be running and connected to the Wazuh server.

Security events generated on the Windows endpoint were successfully visible in the Wazuh Dashboard.

## 7. Result

The final laboratory provides a functional centralized security monitoring environment capable of receiving and analyzing Windows endpoint events through Wazuh.
