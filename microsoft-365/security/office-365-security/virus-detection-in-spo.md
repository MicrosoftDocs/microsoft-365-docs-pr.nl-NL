---
title: Virusdetectie in SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Meer informatie over antivirusbeveiliging in SharePoint Online.
ms.openlocfilehash: f04cd18bb4880ab631816c90b4976beada436225
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630939"
---
# <a name="virus-detection-in-sharepoint-online"></a>Virusdetectie in SharePoint Online

Microsoft 365 kan uw omgeving beschermen tegen malware door virussen te detecteren in bestanden die gebruikers uploaden naar SharePoint Online. Bestanden kunnen worden gescand op virussen nadat ze zijn geüpload. Als blijkt dat een bestand geïnfecteerd is, wordt een eigenschap zo ingesteld dat gebruikers het bestand niet kunnen downloaden of synchroniseren.

> [!IMPORTANT]
> Deze antivirusmogelijkheden in SharePoint Online zijn een manier om virussen te bevatten. Ze zijn niet bedoeld als een enkel punt van verdediging tegen malware voor uw omgeving. We moedigen alle klanten aan om antimalwarebescherming op verschillende lagen te beoordelen en te implementeren en best practices toe te passen voor het beveiligen van uw bedrijfsinfrastructuur. Zie [Beveiligingsroadmap](security-roadmap.md)voor meer informatie over strategieën en best practices.

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Wat gebeurt er als een geïnfecteerd bestand wordt geüpload naar SharePoint Online?

Microsoft 365 maakt gebruik van een veelgebruikte virusdetectie-engine. De engine draait asynchroon binnen SharePoint Online en scant sommige bestanden nadat ze zijn geüpload. Heuristiek wordt gebruikt om te bepalen welke bestanden worden gescand. Wanneer wordt vastgesteld dat een bestand een virus bevat, wordt het gemarkeerd zodat het niet opnieuw kan worden gedownload. In april 2018 hebben we de limiet van 25 MB voor gescande bestanden verwijderd.

Dit is wat er gebeurt:

1. Een gebruiker uploadt een bestand naar SharePoint Online.

2. SharePoint Online bepaalt of het bestand voldoet aan de criteria voor een scan.

3. De virusdetectie-engine scant het bestand.

4. Als een virus wordt gevonden, stelt de virusengine een eigenschap in op het bestand die aangeeft dat het geïnfecteerd is.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met behulp van de browser?

Als een bestand is geïnfecteerd, kunnen gebruikers het bestand niet downloaden van SharePoint Online met behulp van de browser.

Dit is wat er gebeurt:

1. Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand van SharePoint Online te downloaden.

2. De gebruiker krijgt een waarschuwing dat een virus is gedetecteerd. De gebruiker krijgt de mogelijkheid om het bestand te downloaden en te proberen om het schoon te maken met behulp van hun eigen antivirus software.

> [!NOTE]
> U de parameter *DisallowInfectedFileDownload* gebruiken op de cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell om te voorkomen dat gebruikers een geïnfecteerd bestand downloaden, zelfs in het waarschuwingsvenster voor virussen.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Wat gebeurt er als de synchronisatieclient van OneDrive een geïnfecteerd bestand probeert te synchroniseren?

Of gebruikers bestanden synchroniseren met de nieuwe OneDrive-synchronisatieclient (OneDrive.exe) of de vorige synchronisatieclient van OneDrive voor Bedrijven (Groove.exe), als een bestand een virus bevat, wordt de synchronisatieclient niet gedownload. De synchronisatieclient geeft een melding weer dat het bestand niet kan worden gesynchroniseerd.
