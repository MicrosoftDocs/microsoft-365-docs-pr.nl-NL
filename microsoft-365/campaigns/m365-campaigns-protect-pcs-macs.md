---
title: Onbeheerde Windows 10-pc's en Macs beveiligen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Bescherm tegen phishing en andere aanvallen met Microsoft 365 voor campagnes.
ms.openlocfilehash: 7cb09d0cadcc70b96c5f1404defa5d0387947ca8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809847"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Onbeheerde Windows 10-pc's en Macs beveiligen

U Windows 10-pc's en Macs beheren door ze in te schrijven in Microsoft Intune, zodat u ervoor zorgen dat ze gezond en veilig zijn voordat ze toegang krijgen tot gegevens in uw omgeving. Veel campagnes en kleine bedrijven omvatten echter medewerkers die hun eigen apparaten (byod) meebrengen, die niet door de organisatie worden beheerd. Gebruik dit artikel voor deze onbeheerde pc's en Macs om ervoor te zorgen dat minimale beveiligingsmogelijkheden zijn geconfigureerd. 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Een computer met Windows 10 of een Mac beveiligen

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Als uw Windows 10-pc of Mac niet wordt beheerd door uw organisatie, moet u deze beveiligingsmogelijkheden configureren.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)
**Apparaatversleuteling inschakelen**<p>

Apparaatversleuteling is beschikbaar op een breed scala aan Windows-apparaten en helpt uw gegevens te beschermen door deze te versleutelen. Als u apparaatversleuteling inschakelt, hebben alleen geautoriseerde personen toegang tot uw apparaat en gegevens. Zie [apparaatversleuteling inschakelen](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) voor instructies.

 Als apparaatversleuteling niet beschikbaar is op uw apparaat, u in plaats daarvan standaard [BitLocker-versleuteling](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) inschakelen. (BitLocker is niet beschikbaar op Windows 10 Home-editie.) 


**Bescherm uw apparaat met Windows-beveiliging**<p>
Als u Windows 10 hebt, krijgt u de nieuwste antivirusbeveiliging met Windows Security. Wanneer u Windows 10 voor de eerste keer opstart, is Windows Security ingeschakeld en helpt u actief om uw pc te beschermen door te scannen op malware (schadelijke software), virussen en beveiligingsbedreigingen. Windows Security maakt gebruik van realtime beveiliging om alles wat u downloadt of uitvoert op uw pc te scannen.

Windows Update downloadt automatisch updates voor Windows Security om uw pc veilig te houden en te beschermen tegen bedreigingen.

Als u een eerdere versie van Windows hebt en Microsoft Security Essentials gebruikt, is het een goed idee om over te stappen op Windows Security. Zie [mijn apparaat beveiligen met Windows Security voor](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)meer informatie.

**Windows Firewall inschakelen**<p>
U moet Windows Firewall altijd uitvoeren, zelfs als u een andere firewall hebt ingeschakeld. Het uitschakelen van Windows Firewall kan uw apparaat (en uw netwerk, als u er een hebt) kwetsbaarder maken voor ongeautoriseerde toegang. Zie [Windows Firewall in- of uitschakelen](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) voor instructies

## <a name="mac"></a>[Mac](#tab/Mac)
**FileVault gebruiken om uw Mac-schijf te versleutelen**<p>
Schijfversleuteling beschermt gegevens wanneer apparaten verloren gaan of worden gestolen. FileVault-versleuteling op volledige schijf helpt onbevoegde toegang tot de informatie op uw opstartschijf te voorkomen. Zie [FileVault gebruiken om de opstartschijf op je Mac te versleutelen](https://support.apple.com/HT204837) voor instructies.

**Bescherm uw mac tegen malware**<p>
Microsoft raadt u aan betrouwbare antivirussoftware op uw Mac te installeren en te gebruiken. Zie het volgende artikel voor een lijst met keuzes: [Beste Mac-antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

U ook het risico op malware verminderen door software alleen uit betrouwbare bronnen te gebruiken. Met de instellingen voor beveiliging & privacyvoorkeuren u de bronnen van software opgeven die op uw Mac zijn geïnstalleerd. Zie [uw Mac beschermen tegen malware](https://support.apple.com/kb/PH25087)voor meer informatie.

**Firewallbeveiliging inschakelen**<p>
Gebruik firewall-instellingen om uw Mac te beschermen tegen ongewenste contactpersonen die door andere computers worden geïnitieerd wanneer u verbinding hebt gemaakt met internet of een netwerk. Zonder deze bescherming is uw Mac mogelijk kwetsbaarder voor ongeautoriseerde toegang. Zie [meer over de toepassingsfirewall](https://support.apple.com/HT201642) voor instructies.
