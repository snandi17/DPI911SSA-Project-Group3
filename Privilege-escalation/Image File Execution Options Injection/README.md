# Technique Description

## T1183 - Image File Execution Options Injection 
## [Description from ATT&CK](https://attack.mitre.org/techniques/T1183/)
<blockquote>
Image File Execution Options (IFEO) enable a developer to attach a debugger to an application. When a process is created, a debugger present in an application’s IFEO will be prepended to the application’s name, effectively launching the new process under the debugger (e.g., "C:\dbg\ntsd.exe -g notepad.exe"). [1]
\
IFEOs can be set directly via the Registry or in Global Flags via the GFlags tool. [2] IFEOs are represented as Debugger values in the Registry under HKLM\SOFTWARE{\Wow6432Node}\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\ where is the binary on which the debugger is attached. [1]
</blockquote>

# Assumption

# Execution

# Detection

## Visibility

## Splunk Filter
