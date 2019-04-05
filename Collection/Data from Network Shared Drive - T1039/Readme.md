# Technique Description

## T1039 - Data from Network Shared Drive
## [Description from ATT&CK](https://attack.mitre.org/techniques/T1039/)
<blockquote>
Sensitive data can be collected from remote systems via shared network drives (host shared directory, network file server, etc.) that are accessible from the current system prior to Exfiltration.

Adversaries may search network shares on computers they have compromised to find files of interest. Interactive command shells may be in use, and common functionality within cmd may be used to gather information.
</blockquote>

# Assumption
The assumptions that we took was that the end point victim machine was already compromised, and that any security tools that were disabled was by the attacker as a means to evade our defenses.

# Execution
The Atomic-Red-Team T1089 module describes the test for this technique (https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1089/T1089.md)

<b>Test 1 - Killing the AntiVirus process:</b>
<p align="center">
  <img src="">
</p>

<b>Test 2 - Unloading the Sysmon Driver:</b>
<p align="center">
  <img src="">
</p>

# Detection
Detection is done by monitoring processes and command line arguments. we look for the arguments like taskkill and fltmc.exe unload whihc could indicate tools are being disabled.

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
