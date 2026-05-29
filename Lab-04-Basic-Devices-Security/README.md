\# Lab 04 - Basic Device Security



\## Objective

Configure basic security settings on Cisco routers and switches.



\## Topology

!\[Lab Topology\\](topology.png)



\## Commands Used

Router(config)# hostname R1

Switch(config)# hostname SW1

R1(config)# enable password CCNA

R1(config)# service password-encryption

R1(config)# enable secret Cisco

R1# show running-config

R1# copy running-config startup-config

\## What I Did

1\. Changed hostnames to R1 and SW1

2\. Configured unencrypted enable password CCNA

3\. Tested password from user EXEC mode

4\. Enabled password encryption

5\. Configured encrypted enable secret Cisco

6\. Compared encryption types in running-config



\## Key Findings

\- enable password encryption type: 7 (weak, reversible)

\- enable secret encryption type: 5 (MD5, more secure)

\- When both configured, enable secret takes priority



\\## Status

Completed



\## Notes

Part of Jeremy's IT Lab CCNA course

