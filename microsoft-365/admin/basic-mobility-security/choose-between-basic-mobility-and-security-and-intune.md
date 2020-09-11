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
description: Basis mobiliteit en beveiliging maakt deel uit van de Microsoft 365-abonnementen.
ms.openlocfilehash: df52d500c945275b62170ab16260f0c019340f73
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429924"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>Kiezen tussen basis mobiliteit en beveiliging en intune

Microsoft intune is een standalone product dat is inbegrepen bij bepaalde Microsoft 365-abonnementen, terwijl basis & beveiliging deel uitmaakt van de Microsoft 365-abonnementen. Beide zijn opgenomen in diverse plannen, zoals in de volgende tabel wordt beschreven.

|**Abonnement**|**Basis mobiliteit en beveiliging**|**Microsoft Intune**|
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
|Microsoft 365 Eductation a1 |Ja|Ja|
|Microsoft 365 education a3 |Ja|Ja|
|Microsoft 365 education A5 |Ja|Ja|
|Microsoft Intune |Nee|Ja|
|Enterprise Mobility-& Security E3 |Nee|Ja|
|Enterprise Mobility-& Security E5 |Nee|Ja|

>[!NOTE]
>Als u al Microsoft intune gebruikt, kunt u geen eenvoudige mobiliteit en beveiliging gebruiken.

## <a name="differences-in-capabilities"></a>Verschillen in mogelijkheden

Microsoft intune en ingebouwde basis mobiliteit en beveiliging bieden u de mogelijkheid om mobiele apparaten te beheren in uw organisatie, maar er zijn belangrijke verschillen in de mogelijkheid, zoals in de volgende tabel wordt beschreven.

>[!NOTE]
>U kunt gebruikers en hun mobiele apparaten beheren met zowel intune als basis mobiliteit en beveiliging in dezelfde Microsoft 365 Business Standard-organisatie door eerst basis mobiliteit en beveiliging in te stellen en vervolgens Microsoft intune toe te voegen. Hiermee kunt u opgeven of u de apparaten van een gebruiker wilt beheren met basis mobiliteit en beveiliging of met de functie meer-rijke intune-oplossingen. In de modus bepaalt de licentietoewijzing welke service met het apparaat is ingeschreven. Wijs een intune-licentie toe om de functies intune-only in te schakelen.

|**Functiegebied**|**Kenmerken van functies**|**Basis mobiliteit en beveiliging**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|Apparaattypen|Verschillende besturingssysteem platforms en varianten van de hoofdmodus van de beheerder. |Windows<br/>Apparaten<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>Apparaten<br/>Android<br/>Android Samsung KNOX<br/>Mac OS<br/>iPad OS|
|Apparaatcompatibiliteit|Stel beveiligingsbeleid in en beheer dit, zoals pincode vergrendeling op apparaatniveau en detectie van jailbreak. |Beperkingen voor Android 9 en latere apparaten. Zie [mogelijkheden van eenvoudige mobiliteit en beveiliging](capabilities.md)voor meer informatie.|Ja|
|Voorwaardelijke toegang op basis van apparaatcompatibiliteit |Voorkomen dat niet-compatibele apparaten toegang hebben tot zakelijke e-mail en-gegevens vanuit de Cloud. |-Wordt niet ondersteund in Windows 10.<br/>: Beperkt tot het regelen van de toegang tot Exchange Online, SharePoint Online en Outlook services. |Nee|
|Apparaatconfiguratie  |Apparaatinstellingen configureren (bijvoorbeeld de camera uitschakelen). |Beperkte set instellingen.Zie [mogelijkheden van eenvoudige mobiliteit en beveiliging](capabilities.md)voor meer informatie. |Ja|
|Externe acties  |Opdrachten verzenden naar apparaten via internet. Als u bijvoorbeeld Office-gegevens van een apparaat van een werknemer wilt verwijderen, terwijl u persoonlijke gegevens op hun plaats verlaat (buiten gebruik stellen). |Buiten gebruik stellen<br/>Vegen<br/>Wissen|-Auto Pilot-opnieuw instellen (alleen Windows)<br/>- [BitLocker-sneltoets draaien](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Alleen Windows)<br/>- [Wissen](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [Activeer-Loc uitschakelen](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (alleen iOS)<br/>- [Fresh Start](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Alleen Windows)<br/>- [Volledige scan](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Alleen Windows 10)<br/>- [Apparaat zoeken](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (alleen iOS)<br/>- [Verloren modus](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (alleen iOS)<br/>- [Snel scannen](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(alleen Windows 10)<br/>- [Extern beheer voor Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [Extern vergrendelen](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [Naam van apparaat wijzigen](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [Wachtwoord opnieuw instellen](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [Opnieuw opstarten](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (Alleen Windows)<br/>- [Buiten gebruik stellen](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>-Windows Defender-beveiligingsinformatie bijwerken (alleen Windows)<br/>-Windows 10 pincode opnieuw instellen (alleen Windows)<br/>- [Vegen](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [Aangepaste meldingen verzenden](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)<br/>- [Apparaat synchroniseren](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|E-mail profielen  |Het inrichten van een systeemeigen e-mail profiel op het apparaat. |Ja|Ja|
|WIFI-profielen |Het inrichten van een systeemeigen WIFI-profiel op het apparaat. |Nee|Ja|
|VPN-profielen |Het inrichten van een systeemeigen VPN-profiel op het apparaat. |Nee|Ja|
|MDM-Toepassingsbeheer  |Implementeer uw interne line-of-Business-Apps en van apps winkels voor gebruikers. |Nee|Ja|
|Mobiele toepassing beschermen  |Zorg ervoor dat uw gebruikers veilig toegang krijgen tot bedrijfsgegevens met behulp van de Office Mobile-en line-of-Business-Apps waarover ze weten en wat de beveiliging van gegevens kan helpen voor het beperken van acties zoals kopiëren, knippen, plakken en opslaan als voor alleen de apps die zijn erkend voor bedrijfsgegevens. Werkt zelfs als de apparaten niet zijn ingeschreven op MDM. Zie app-gegevens beschermen met behulp van MAM-beleidsregels. |Nee|Ja|
|Beheerde browser  |Veiliger browsen op het web met behulp van de Edge-app. |Nee|Ja|
|Nul aanraak Programma's |Registreer grote nummers van bedrijfseigendoms apparaten, terwijl de gebruikersinstellingen eenvoudiger worden gemaakt. |Nee|Ja|
