# Part 1: Lab Design and Architecture

## Objective

The first phase of this project involved designing the architecture for an isolated Active Directory security monitoring lab.

The environment contains a Windows Server domain controller, a Windows target machine, a Splunk server and a Kali Linux testing machine. These systems will communicate through a private VMware network.

## Architecture Diagram

![Active Directory lab architecture](../active-directory-lab-diagram.png)

## Lab Components

| System | Operating System | Planned IP Address | Purpose |
|---|---|---:|---|
| Splunk Server | Ubuntu Server | 192.168.10.10 | Collects and analyses security events |
| Domain Controller | Windows Server 2022 | 192.168.10.7 | Provides Active Directory and domain services |
| Windows Target | Windows 10 | DHCP | Domain-joined endpoint used for monitoring and testing |
| Attacker Machine | Kali Linux | 192.168.10.250 | Generates authorised security-testing activity |

## Network Configuration

The lab is designed to use the private `192.168.10.0/24` network.

VMware VMnet2 will be used to place the virtual machines on the same virtual network. Static IP addresses will be assigned to the Splunk server, domain controller and Kali Linux machine. The Windows target machine will initially obtain its address through DHCP.

## Planned Data Flow

1. Sysmon records detailed activity on the Windows systems.
2. Splunk Universal Forwarder collects Windows and Sysmon events.
3. The events are sent to the Splunk server.
4. Splunk indexes the events and makes them searchable.
5. Kali Linux and Atomic Red Team generate authorised test activity.
6. The resulting events are investigated in Splunk.

## Security Considerations

All security testing will be performed against systems inside the virtual lab. Private IP addresses are used, and no external systems will be targeted.

## Outcome

The lab architecture and IP-addressing plan were successfully designed. The next phase involves configuring the required virtual machines and network settings.
