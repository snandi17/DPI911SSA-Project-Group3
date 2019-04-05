# Technique Description

## T1107 - File Deletion
## [Description from ATT&CK](https://attack.mitre.org/techniques/T1107/)
<blockquote>
Malware, tools, or other non-native files dropped or created on a system by an adversary may leave traces behind as to what was done within a network and how. Adversaries may remove these files over the course of an intrusion to keep their footprint low or remove them at the end as part of the post-intrusion cleanup process.

There are tools available from the host operating system to perform cleanup, but adversaries may use other tools as well. Examples include native cmd functions such as DEL, secure deletion tools such as Windows Sysinternals SDelete, or other third-party file deletion tools.
</blockquote>

# Assumption
The assumptions that we took was that the end point victim machine was already compromised, and that any files that were deleted was by the attacker as a means to evade our defenses.

# Execution
The Atomic-Red-Team T1089 module describes the test for this technique (https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1107/T1107.md)

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

<b>Filter 1 - Splunk filter to detect Antivirus being killed</b>
<p align="center">
  <img src="">
</p>

<b>Filter 2 - Splunk filter to detect Unloading Sysmon driver</b>
<p align="center">
  <img src="">
</p>
