# Technique Description

## T1060 - Registry Run Keys / Startup Folder 
## [Description from ATT&CK](https://attack.mitre.org/techniques/T1060/)
<blockquote>
Adding an entry to the "run keys" in the Registry or startup folder will cause the program referenced to be executed when a user logs in. [1] These programs will be executed under the context of the user and will have the account's associated permissions level.

The following run keys are created by default on Windows systems: 
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
\
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce 
\
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run 
\
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\RunOnce
</blockquote>

# Assumption
The assumption here is that there should be no keys entered to any of the Run keys in the registry. 

# Execution
The execution method used is from Red-Atomics atomics T1060 https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1060/T1060.md

# Detection

## Visibility



## Splunk Filter
