# Technique Description

## T1012 - Query Registry
## [Description from ATT&CK](https://attack.mitre.org/techniques/T1012/)
<blockquote>
Adversaries may interact with the Windows Registry to gather information about the system, configuration, and installed software.

The Registry contains a significant amount of information about the operating system, configuration, software, and security. Some of the information may help adversaries to further their operation within a network.
</blockquote>

# Assumption
The assumptions that we took was that the end point victim machine was already compromised, and that any queries that were made to registries were done by the attacker in an attempt to gather information. We also asume that regular users do not make queries to the registry from command line.

# Execution
The Atomic-Red-Team T1089 module describes the test for this technique (https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1012/T1012.md)

<b>Test 1 - Killing the AntiVirus process:</b>
<p align="center">
  <img src="">
</p>

<b>Test 2 - Unloading the Sysmon Driver:</b>
<p align="center">
  <img src="">
</p>

# Detection
Detection is done by monitoring processes and command line arguments. we look for the arguments like taskkill and fltmc.exe unload which could indicate tools are being disabled.

## Splunk Filter
The following splunk query will allow us to detect these techniques

<b>Filter 1 - Splunk filter to detect command line argument of Antivirus being killed</b>
<p align="center">
  <img src="">
</p>

<b>Filter 2 - Splunk filter to detect Process of Antivirus being killed</b>
<p align="center">
  <img src="">
</p>

<b>Filter 3 - Splunk filter to detect Unloading Sysmon driver</b>
<p align="center">
  <img src="">
</p>
