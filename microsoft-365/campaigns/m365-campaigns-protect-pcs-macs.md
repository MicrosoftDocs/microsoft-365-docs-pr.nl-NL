---
title: Niet-beheerde Windows 10 pc's en Macs beveiligen
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Bescherm onmanaged of bring-your-own devices (BYOD) met Microsoft 365.
ms.openlocfilehash: 430f5446f86c26cb1f0fd1c7f34613cddec473b2
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398251"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Niet-beheerde Windows 10 pc's en Macs beveiligen

U kunt Windows 10 pc's en Macs beheren door ze in te schrijven in Microsoft Intune, zodat u ervoor kunt zorgen dat ze gezond en veilig zijn voordat u toegang krijgt tot gegevens in uw omgeving. Veel campagnes en kleine bedrijven bevatten echter medewerkers die hun eigen apparaten (BYOD) meenemen, die niet door de organisatie worden beheerd. Voor deze niet-bemande pc's en Macs gebruikt u dit artikel om ervoor te zorgen dat minimale beveiligingsmogelijkheden zijn geconfigureerd.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Een computer met een mac Windows 10 of een Mac beveiligen

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Als uw Windows 10 pc of Mac niet wordt beheerd door uw organisatie, moet u deze beveiligingsmogelijkheden configureren.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Apparaatversleuteling in- en uit-**<p>

Apparaatversleuteling is beschikbaar op een groot aantal Windows apparaten en helpt uw gegevens te beschermen door deze te versleutelen. Als u apparaatversleuteling in bedrijf neemt, hebben alleen geautoriseerde personen toegang tot uw apparaat en gegevens. Zie [Apparaatversleuteling in- en](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) uit te zetten voor instructies.

 Als apparaatversleuteling niet beschikbaar is op uw apparaat, kunt u in plaats daarvan standaardversleuteling [BitLocker in.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) (BitLocker is niet beschikbaar op Windows 10 Home editie.) 

**Uw apparaat beveiligen met Windows-beveiliging**<p>
Als u Windows 10 hebt, krijgt u de nieuwste antivirusbeveiliging met Windows-beveiliging. Wanneer u de Windows 10 voor het eerst start, is Windows-beveiliging actief bezig met het beschermen van uw pc door te scannen op malware (schadelijke software), virussen en beveiligingsrisico's. Windows-beveiliging realtime beveiliging gebruikt om alles wat u downloadt of op uw pc uit te voeren, te scannen.

Windows Updates voor downloads voor Windows-beveiliging automatisch bijwerken om uw pc veilig te houden en te beschermen tegen bedreigingen.

Als u een eerdere versie van Windows en Microsoft Security Essentials gebruikt, is het een goed idee om naar een andere Windows-beveiliging. Zie Voor meer informatie help [mijn apparaat te beveiligen met Windows-beveiliging.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**De firewall Windows in-**<p>
U moet altijd Windows Firewall uitvoeren, zelfs als u een andere firewall hebt ingeschakeld. Als u Windows firewall uitschakelen, is uw apparaat (en uw netwerk, als u er een hebt) kwetsbaarder voor onbevoegde toegang. Zie [Firewall Windows in- of uitschakelen voor](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) instructies.

## <a name="mac"></a>[Mac](#tab/Mac)

**FileVault gebruiken om uw Mac-schijf te versleutelen**<p>
Schijfversleuteling beschermt gegevens wanneer apparaten verloren gaan of worden gestolen. FileVault-versleuteling op volledige schijf helpt voorkomen dat onbevoegden toegang hebben tot de gegevens op de opstartschijf. Zie [FileVault gebruiken om de opstartschijf](https://support.apple.com/HT204837) op uw Mac te versleutelen voor instructies.

**Uw Mac beschermen tegen malware**<p>
Microsoft raadt u aan betrouwbare antivirussoftware op uw Mac te installeren en te gebruiken. Zie het volgende artikel voor een lijst met opties: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

U kunt ook het risico op malware beperken door software alleen te gebruiken uit betrouwbare bronnen. Met de instellingen in & privacyvoorkeuren kunt u opgeven welke softwarebronnen op uw Mac zijn geïnstalleerd. Zie uw Mac beschermen [tegen malware voor meer informatie.](https://support.apple.com/kb/PH25087)

**Firewallbeveiliging in- en uit-**<p>
Gebruik firewallinstellingen om uw Mac te beschermen tegen ongewenste contactpersonen die door andere computers worden gestart wanneer u verbinding hebt met internet of een netwerk. Zonder deze beveiliging is uw Mac mogelijk kwetsbaarder voor onbevoegde toegang. Zie [de toepassingsfirewall voor](https://support.apple.com/HT201642) instructies.
