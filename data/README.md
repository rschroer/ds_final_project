# Notes for Microsoft Defender Kaggle Project dataset.

## Getting and extracting

This dataset is big and I had some challenges in it and with it. It is too big for excel, too big for the OSX GUI unzip and it takea abuout a minute to load into pandas.

To help the other members, I've documented some of the commands to get this up and running on OSX.

1. Unpack it in the command line
`unzip -a microsoft-malware-prediction.zip`

1. Change file priviledges to read write (everyone)
`chmod 666 train.csv`

1. Count the number of lines
`wc -l train.csv`

Soo, yes, we have 8.9 million rows.

## Some Definitions of some features

__EngineVersion__
This is the core detection engine of the Defender. Think of this like "What can this thing to do detect malware?" Can it check the hash of a running process againstk known bad, check registry for run keys, or call batman?

__AvSigVersion__
This is the content that tells the engine if something is bad or not. This list of process hashes are bad, these registry keys are bad, or batman says these are malware. 

__AppVersion__
This is the app itself and may not be related to any engine or av. It includes UX components and integration features.

__PuaMode__
Think of PUA Mode as an additional module in Windows Defender that blocks browser toolbars, adware, and other "Potentially Unwanted Applications."

[Microsoft Documentation for PUA Mode](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus)

__UacLuaenable__
User Account Control (UAC) is part of that process where a confirmation box pops up whenever you request to do something that requires elevated priviledges. The file virtualization part of UAC is also referred to as LUA (LUAFV.SYS)

[Microsoft Documentation for UAC](https://docs.microsoft.com/en-us/windows/win32/uxguide/winenv-uac)

__HasTpm__
Windows Trusted Platform Module (TPM) verifies the integrity of OS files.

[Microsoft Documentation for TPM](https://docs.microsoft.com/en-us/windows/security/information-protection/tpm/how-windows-uses-the-tpm)

__Firewall__
This is specifially Windows host based firewall. This does not know if there are any network based firewalls in line. A firewall should block any network traffic that is not specifically allowed.


__SMode__
Windows 10 in S Mode is a more limited, locked-down Windows operating system. In S Mode, you can only install apps from the Store, and you can only browse the web with Microsoft Edge.

__SmartScreen__
SmartScreen is a module for only internet explorer and only for Browser security.

[Microsoft Documentation for smartscreen](https://support.microsoft.com/en-us/help/17443/windows-internet-explorer-smartscreen-filter-faq)