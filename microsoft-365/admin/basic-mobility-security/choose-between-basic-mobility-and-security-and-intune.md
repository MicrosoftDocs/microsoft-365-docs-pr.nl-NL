---
title: Kiezen tussen basis mobiliteit en beveiliging en intune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Basis mobiliteit en beveiliging maken deel uit van de Microsoft 365-abonnementen.
ms.openlocfilehash: cfd1a68c313d1a1335490e2b8d6938de192fe3f3
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877090"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Kiezen tussen basis mobiliteit en beveiliging of intune

[Microsoft intune](https://docs.microsoft.com/mem/intune/) is een standalone product dat is inbegrepen bij bepaalde microsoft 365-abonnementen, terwijl basis en beveiliging deel uitmaakt van de microsoft 365-abonnementen. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Beschikbaarheid van basis mobiliteit en beveiliging en intune
 
Zowel eenvoudige mobiliteit als beveiliging en intune zijn opgenomen in diverse plannen, zoals in de volgende tabel wordt beschreven.

| Plannen | Basic Mobility en Security | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365-apps|Ja|Nee|
|Microsoft 365 Business Basic|Ja|Nee|
|Microsoft 365 Business Standard|Ja|Nee|
|Office 365 E1 |Ja|Nee|
|Office 365 E3 |Ja|Nee|
|Office 365 E5 |Ja|Nee|
|Microsoft 365 Business Premium |Ja|Ja|
|Microsoft 365 Firstline Workers 3 |Ja|Ja|
|Microsoft 365 Enterprise E3 |Ja|Ja|
|Microsoft 365 Enterprise E5 |Ja|Ja|
|Microsoft 365 education a1 |Ja|Ja|
|Microsoft 365 education a3 |Ja|Ja|
|Microsoft 365 education A5 |Ja|Ja|
|Microsoft Intune |Nee|Ja|
|Enterprise Mobility-& Security E3 |Nee|Ja|
|Enterprise Mobility-& Security E5 |Nee|Ja|

>[!NOTE]
>U kunt geen eenvoudige mobiliteit en beveiliging gebruiken als u al Microsoft intune gebruikt.

 Zie [beschrijvingen van Microsoft 365 en Office 365 platform service](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)voor meer informatie. 

## <a name="differences-in-capabilities"></a>Verschillen in mogelijkheden

Microsoft intune en ingebouwde basis mobiliteit en beveiliging bieden u de mogelijkheid om mobiele apparaten te beheren in uw organisatie, maar er zijn belangrijke verschillen in de mogelijkheid, zoals in de volgende tabel wordt beschreven.

>[!NOTE]
>U kunt gebruikers en hun mobiele apparaten beheren met zowel intune als basis mobiliteit en beveiliging in dezelfde Microsoft 365 Business Standard-organisatie *door eerst basis mobiliteit en beveiliging in te stellen en vervolgens Microsoft intune toe te voegen*. Hiermee kunt u eenvoudige mobiliteit en beveiliging kiezen, of de functie meer-rijke intune-oplossingen. Wijs een intune-licentie toe als u de intune-functies wilt inschakelen.

| Functiegebied | Kenmerken van functies | Basic Mobility en Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Apparaattypen|Het beheren van diverse varianten van OS en belangrijkste beheermodus. |Windows<br/>Apparaten<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>Apparaten<br/>Android<br/>Android Samsung KNOX<br/>Mac OS, iPad OS|
|Apparaatcompatibiliteit|Stel beveiligingsbeleid in en beheer dit, zoals pincode vergrendeling op apparaatniveau en detectie van jailbreak. |Beperkingen voor Android 9 en latere apparaten. [Details](capabilities.md)weergeven. |Ja|
|Voorwaardelijke toegang op basis van apparaatcompatibiliteit |Voorkomen dat niet-compatibele apparaten toegang hebben tot zakelijke e-mail en-gegevens vanuit de Cloud. |Niet ondersteund in Windows 10.<br/>Beperkt tot het beheren van de toegang tot Exchange Online, SharePoint Online en Outlook. |Ja |
|Apparaatconfiguratie  |Instellingen configureren voor apparaten (bijvoorbeeld de camera uitschakelen)|Beperkte set instellingen.|Ja|
|Apparaatcompatibiliteit  |Stel beveiligingsbeleid in en beheer dit, zoals pincode vergrendeling op apparaatniveau en detectie van jailbreak. |Beperkingen voor Android 9 en latere apparaten. [Details](capabilities.md)weergeven. |Ja|
|E-mail profielen  |Het inrichten van een systeemeigen e-mail profiel op het apparaat. |Ja|Ja|
|WiFi-profielen |Het inrichten van een systeemeigen WiFi-profiel op het apparaat. |Nee|Ja|
|VPN-profielen |Het inrichten van een systeemeigen VPN-profiel op het apparaat. |Nee|Ja|
|Basisbeperkingen voor mobiliteit en beveiligingstoepassingen  |Implementeer uw interne line-of-Business-Apps en van apps winkels voor gebruikers. |Nee|Ja|
|Mobiele toepassing beschermen  |Zorg ervoor dat uw gebruikers veilig toegang krijgen tot bedrijfsgegevens met behulp van de Office Mobile-en line-of-Business-Apps waarover ze weten en wat de beveiliging van gegevens kan helpen voor het beperken van acties zoals kopiëren, knippen, plakken en opslaan als voor alleen de apps die zijn erkend voor bedrijfsgegevens. Werkt zelfs als de apparatuur niet is geregistreerd voor basis mobiliteit en beveiliging. Zie app-gegevens beschermen met behulp van MAM-beleidsregels. |Nee|Ja|
|Beheerde browser  |Veiliger browsen op het web met behulp van de Edge-app. |Nee|Ja|
|Ongeproefde aanraak Programma's voor aanmelding |Registreer grote nummers van bedrijfseigendoms apparaten, terwijl gebruikersinstellingen eenvoudiger worden. |Nee|Ja|
|||

Naast de functies die in de bovenstaande tabel worden vermeld, zijn basis mobiliteit en beveiliging en intune ook een reeks externe acties opgenomen waarmee opdrachten naar apparaten via internet worden verzonden. U kunt bijvoorbeeld Office-gegevens verwijderen van het apparaat van een werknemer, terwijl u persoonlijke gegevens op hun plaats laat staan (buiten gebruik stellen), Office-apps verwijderen van het apparaat van een werknemer (wissen) of een apparaat opnieuw instellen op de fabrieksinstellingen (volledig wissen). 

Basisacties voor mobiliteit en beveiliging zijn onder meer buiten gebruik stellen, wissen en volledig wissen. Zie [mogelijkheden van eenvoudige mobiliteit en beveiliging](capabilities.md)voor meer informatie over basisacties voor mobiliteit en beveiliging.

Met intune hebt u de volgende set acties:

-   Auto Pilot opnieuw instellen (alleen Windows)
-  [BitLocker-sneltoets draaien](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Alleen Windows)
-  [Het apparaat wissen, buiten gebruik stellen of handmatig opnieuw registreren](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Activeer-Loc uitschakelen](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (alleen iOS)
-  [Fresh Start](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Alleen Windows)
- [Volledige scan](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Alleen Windows 10)
- [Apparaat zoeken](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (alleen iOS)
- [Verloren modus](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (alleen iOS): [snelle scan](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(alleen Windows 10)
- [Extern beheer voor Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Extern vergrendelen](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Naam van apparaat wijzigen](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Wachtwoordcode opnieuw instellen](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (alleen Windows)
-  Windows Defender-beveiligingsinformatie bijwerken (alleen Windows)
-  Windows 10 pincode opnieuw instellen (alleen Windows)
-  [Aangepaste meldingen verzenden](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Apparaat synchroniseren](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Zie [Microsoft intune-documentatie](https://docs.microsoft.com/mem/intune/)voor meer informatie over intune-acties.
