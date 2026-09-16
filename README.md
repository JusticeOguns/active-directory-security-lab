# Active Directory Security Monitoring Lab

## Overview

This repository documents my completion of the MyDFIR Active Directory Project 1.0.

The project involves building an Active Directory home lab using Windows Server, a Windows target machine, Splunk, Sysmon, Kali Linux and Atomic Red Team.

The goal is to collect Windows security events, generate authorised test activity and investigate the resulting logs using Splunk.

## Project Status

✅ Completed

## Lab Architecture

The diagram below shows the planned architecture of the Active Directory security monitoring lab. All virtual machines are connected through the private `192.168.10.0/24` network.

![Active Directory lab architecture](active-directory-lab-diagram.png)

## Project Documentation

- [Part 1: Lab Design and Architecture](docs/01-lab-design.md)
- 
### Lab Systems

| System | Hostname | IP Address | Purpose |
|---|---|---:|---|
| Ubuntu Server | Splunk Server | 192.168.10.10 | Receives, indexes and displays security events |
| Windows Server 2022 | ADDC01 | 192.168.10.7 | Domain controller for `mydfir.local` |
| Windows 10 | TARGET-PC | 192.168.10.100 | Domain-joined endpoint monitored using Sysmon and Splunk Universal Forwarder |
| Kali Linux | kali | 192.168.10.250 | Authorised security-testing machine |
