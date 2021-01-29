---
title: Onopgeslagen Windows 10-pc's en Macs beveiligen
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Bebeveiligen onmanaged of breng uw eigen apparaten (BYOD) aan met Microsoft 365.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044382"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Niet-bemande Windows 10-pc's en Macs beveiligen

U kunt Windows 10-pc's en Macs beheren door ze te registreren in Microsoft Intune, zodat u er zeker van kunt zijn dat ze gezond en veilig zijn voordat u toegang krijgt tot gegevens in uw omgeving. Veel campagnes en kleine bedrijven omvatten echter medewerkers die hun eigen apparaten (BYOD) brengen, die niet worden beheerd door de organisatie. Gebruik dit artikel voor deze onveilige pc's en Macs om ervoor te zorgen dat minimale beveiligingsmogelijkheden zijn geconfigureerd.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Een computer met Windows 10 of een Mac beveiligen

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Als uw Windows 10-pc of Mac niet wordt beheerd door uw organisatie, moet u deze beveiligingsmogelijkheden configureren.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Apparaatversleuteling inversleutelen**<p>

Apparaatversleuteling is beschikbaar op een groot aantal Windows-apparaten en helpt uw gegevens te beschermen door ze te versleutelen. Als u apparaatversleuteling in bedrijf neemt, hebben alleen geautoriseerde personen toegang tot uw apparaat en gegevens. Zie [Apparaatversleuteling in turn on](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.

 Als apparaatversleuteling niet beschikbaar is op uw apparaat, kunt u in plaats daarvan de [standaard-BitLocker-versleuteling](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) in te stellen. (BitLocker is niet beschikbaar in de Windows 10 Home-editie.) 

**Bescherm uw apparaat met Windows-beveiliging**<p>
Als u Windows 10 hebt, krijgt u de nieuwste antivirusbeveiliging met Windows-beveiliging. Wanneer u Windows 10 voor de eerste keer start, is Windows-beveiliging aan en wordt uw pc actief beschermd door te scannen op malware (kwaadaardige software), virussen en beveiligingsrisico's. Windows-beveiliging maakt gebruik van realtime-beveiliging om alles te scannen wat u downloadt of op uw pc gebruikt.

Windows Update downloadt updates voor Windows-beveiliging automatisch om uw pc te beschermen tegen bedreigingen.

Als u een eerdere versie van Windows hebt en Microsoft Security Essentials gebruikt, is het een goed idee om over te gaan op Windows-beveiliging. Zie 'Mijn apparaat beschermen [met Windows-beveiliging' voor meer informatie.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Windows Firewall in te zetten**<p>
U moet Windows Firewall altijd gebruiken, zelfs als u een andere firewall hebt ingeschakeld. Als u Windows Firewall uit schakelen, wordt uw apparaat (en netwerk, indien van gebruik) kwetsbaarder voor toegang door onbevoegden. Zie [Windows Firewall in- of uitschakelen](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) voor instructies

## <a name="mac"></a>[Mac](#tab/Mac)

**FileVault gebruiken om uw Mac-schijf te versleutelen**<p>
Met schijfversleuteling beschermt u uw gegevens bij verlies of diefstal van een apparaat. Met de volledige schijfversleuteling van FileVault voorkomt u dat onbevoegden toegang krijgen tot de gegevens op de opstartschijf. Zie [FileVault gebruiken om de opstartschijf op](https://support.apple.com/HT204837) uw Mac te versleutelen voor instructies.

**Bescherm uw Mac tegen malware**<p>
Microsoft raadt u aan betrouwbare antivirussoftware op uw Mac te installeren en te gebruiken. Zie het volgende artikel voor een lijst met opties: [Beste Mac-antivirussoftware 2019. ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)

U kunt het risico van malware ook verminderen door alleen software uit betrouwbare bronnen te gebruiken. Met de instellingen in & privacyvoorkeuren kunt u de bronnen opgeven van software die op uw Mac is geïnstalleerd. Zie uw [Mac beveiligen tegen malware voor meer informatie.](https://support.apple.com/kb/PH25087)

**Firewallbeveiliging in bedrijf**<p>
Gebruik firewallinstellingen om uw Mac te beschermen tegen ongewenst contact met andere computers wanneer u verbinding hebt met internet of een netwerk. Zonder deze beveiliging is uw Mac mogelijk kwetsbaarder voor onbevoegde toegang. Zie [de firewall van de toepassing](https://support.apple.com/HT201642) voor instructies.
