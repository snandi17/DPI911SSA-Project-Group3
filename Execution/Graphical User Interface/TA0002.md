# Technique Description

## T1061 - Graphical User Interface 
## [Description from ATT&CK](https://attack.mitre.org/techniques/T1061/)
<blockquote>
The Graphical User Interfaces (GUI) is a common way to interact with an operating system. Adversaries may use a system's GUI during an operation, commonly through a remote interactive session such as Remote Desktop Protocol, instead of through a Command-Line Interface, to search for information and execute files via mouse double-click events, the Windows Run command [1], or other potentially difficult to monitor interactions.
</blockquote>

# Assumption
This technique is difficult to monitor for through the various tools available to us. The monitoring tools have no way to tell if a remote desktop session is malicious. Again looking for indicators of compromise on user accounts, endpoints and also unusual user behavior (odd login times) are ways of identifying if an adversary is using this technique.  

# Execution

# Detection

## Visibility

## Splunk Filter
