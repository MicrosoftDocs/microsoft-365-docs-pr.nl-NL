---
title: Kiezen tussen Basic Mobility en Security en Intune
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
description: Basic Mobility and Security maken deel uit van de Microsoft 365-abonnementen.
ms.openlocfilehash: ec3ffa8879bf14ab3116bbbbf5cf2a1a3fd7c6e6
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053799"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Kiezen tussen Basic Mobility en Security of Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) is een zelfstandig product dat deel uitmaakt van bepaalde Microsoft 365-abonnementen, terwijl Basic Mobility and Security deel uitmaakt van de Microsoft 365-abonnementen.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Beschikbaarheid van Basic Mobility and Security en Intune

Zowel Basic Mobility en Security als Intune zijn opgenomen in diverse abonnementen, zoals wordt beschreven in de volgende tabel.

| Plannen | Basic Mobility en Security | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365-apps|Ja|Nee|
|Microsoft 365 Business Basic|Ja|Nee|
|Microsoft 365 Business Standard|Ja|Nee|
|Office 365 E1 |Ja|Nee|
|Office 365 E3 |Ja|Nee|
|Office 365 E5 |Ja|Nee|
|Microsoft 365 Business Premium |Ja|Ja|
|Microsoft 365 Firstline 3 |Ja|Ja|
|Microsoft 365 Enterprise E3 |Ja|Ja|
|Microsoft 365 Enterprise E5 |Ja|Ja|
|Microsoft 365 Education A1 |Ja|Ja|
|Microsoft 365 Education A3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nee|Ja|
|Enterprise Mobility & Security E3 |Nee|Ja|
|Enterprise Mobility & Security E5 |Nee|Ja|

>[!NOTE]
>U kunt Basic Mobility and Security niet gaan gebruiken als u al Microsoft Intune gebruikt.

 Zie de servicebeschrijvingen [van de Microsoft 365- en Office 365-platformservice voor meer informatie.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Verschillen in mogelijkheden

Microsoft Intune en de ingebouwde Basic Mobility and Security bieden u beide de mogelijkheid om mobiele apparaten in uw organisatie te beheren, maar er zijn belangrijke verschillen in mogelijkheden, zoals wordt beschreven in de volgende tabel.

>[!NOTE]
>U kunt gebruikers en hun mobiele apparaten beheren met zowel Intune als Basic Mobility en Security in dezelfde Microsoft 365 Business Standard-organisatie door Eerst Basic Mobility en Security in te stellen en vervolgens *Microsoft Intune* toe te voegen. Hierdoor kunt u Basic Mobility and Security kiezen of de meer uitgebreide Intune-oplossing. Wijs een Intune-licentie toe om de Intune-functies in teschakelen.

| Functiegebied | Highlights van functies | Basic Mobility en Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Apparaattypen|Het beheren van verschillende besturingssysteemplatforms en belangrijke managementmodusvarianten. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Apparaat compliance|Beveiligingsbeleid instellen en beheren, zoals pincodevergrendeling en jailbreak-detectie op apparaatniveau. |Beperkingen voor Android 9 en latere apparaten. Meer [informatie.](capabilities.md) |Ja|
|Voorwaardelijke toegang op basis van apparaat compliance |Voorkomen dat niet-compatibele apparaten toegang krijgen tot zakelijke e-mail en gegevens vanuit de cloud. |Niet ondersteund in Windows 10.<br/>Beperkt tot het beheren van toegang tot Exchange Online, SharePoint Online en Outlook. |Ja |
|Apparaatconfiguratie  |Apparaatinstellingen configureren (bijvoorbeeld de camera uitschakelen)|Beperkte set instellingen.|Ja|
|Apparaat compliance  |Beveiligingsbeleid instellen en beheren, zoals pincodevergrendeling en jailbreak-detectie op apparaatniveau. |Beperkingen voor Android 9 en latere apparaten. Meer [informatie.](capabilities.md) |Ja|
|E-mailprofielen  |Een systeemeigen e-mailprofiel op het apparaat inrichten. |Ja|Ja|
|WiFi-profielen |Een systeemeigen Wifi-profiel op het apparaat inrichten. |Nee|Ja|
|VPN-profielen |Een eigen VPN-profiel inrichten op het apparaat. |Nee|Ja|
|Beheer van basis mobiliteits- en beveiligingstoepassing  |Implementeer uw interne Line-Of-Business-apps en van apps-stores naar gebruikers. |Nee|Ja|
|Mobiele toepassingsbeveiliging  |Stelt uw gebruikers in staat veilig toegang te krijgen tot bedrijfsgegevens met behulp van de Mobiele Office-apps en line-of-business-apps die ze kennen, terwijl ze tegelijkertijd de beveiliging van gegevens waarborgen door acties zoals kopiëren, knippen, plakken en opslaan als te beperken tot alleen die apps die zijn goedgekeurd voor bedrijfsgegevens. Dit werkt zelfs als de apparaten niet zijn geregistreerd voor Basic Mobility and Security. Zie App-gegevens beveiligen met MAM-beleid. |Nee|Ja|
|Beheerde browser  |Schakel veiliger surfen in met de Edge-app. |Nee|Ja|
|Autopilot-programma's voor nul-aanraakinschrijvingen) |Schrijf grote aantallen bedrijfsapparaten in en vereenvoudig het instellen van gebruikers. |Nee|Ja|
|||

Naast de functies die in de bovenstaande tabel staan vermeld, bevatten Basic Mobility en Security en Intune beide een reeks externe acties die opdrachten verzenden naar apparaten via internet. U kunt bijvoorbeeld Office-gegevens verwijderen van het apparaat van een werknemer terwijl u persoonlijke gegevens op zijn plaats laat (niet meer gebruiken), Office-apps verwijderen van het apparaat van een werknemer (wissen) of de fabrieksinstellingen van een apparaat herstellen (volledig wissen). 

Externe acties voor Basis mobiliteit en beveiliging omvatten retire, wissen en volledig wissen. Zie de mogelijkheden van Basis mobiliteit en beveiliging voor meer informatie over acties voor basis mobiliteit [en beveiliging.](capabilities.md)

Met Intune hebt u de volgende acties:

-   Autopilot opnieuw instellen (alleen voor Windows)
-  [Bitlocker-toets draaien](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Alleen Windows)
-  [Het apparaat wissen, ingetrokken of handmatig in te trekken](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Activeringslocatie uitschakelen](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (alleen iOS)
-  [Nieuwe start](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Alleen Windows)
- [Volledige scan](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Alleen In Windows 10)
- [Apparaat zoeken](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (alleen iOS)
- [Modus Verloren](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (alleen iOS)- [Snelle scan](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(alleen in Windows 10)
- [Afstandsbediening voor Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Externe vergrendeling](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Naam van apparaat wijzigen](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Wachtwoordcode opnieuw instellen](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [(](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   alleen windows)
-  Windows Defender Security Intelligence bijwerken (alleen Windows)
-  Pincode opnieuw instellen voor Windows 10 (alleen voor Windows)
-  [Aangepaste meldingen verzenden](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Apparaat synchroniseren](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Zie de documentatie bij Microsoft Intune voor meer informatie over [Intune-acties.](https://docs.microsoft.com/mem/intune/)
