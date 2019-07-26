# Notes for Microsoft Defender Kaggle Project dataset.

## Getting and extracting

This dataset is big and I had some challenges in it and with it. It is too big for excel, too big for the OSX GUI unzip and it takea abuout a minute to load into pandas.

To help the other members, I've documented some of the commands to get this up and running on OSX.

1. Unpack it in the command line
`unzip -a microsoft-malware-prediction.zip`

1. Change file priviledges to read write (everyone)
`chmod 666 train.csv`

1. Count the number of lines
`1wc -l train.csv`

Soo, yes, we have 8.9 million rows.

## Some Definitions of some features


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

This is specifially Windows host based firewall. This does not know if there are any network based firewalls in line.


__SMode__

Windows 10 in S Mode is a more limited, locked-down Windows operating system. In S Mode, you can only install apps from the Store, and you can only browse the web with Microsoft Edge.

__SmartScreen__

SmartScreen is a modeule for internet explorer that is like safe browsing for Chrome.

[Microsoft Documentation for smartscreen](https://support.microsoft.com/en-us/help/17443/windows-internet-explorer-smartscreen-filter-faq)