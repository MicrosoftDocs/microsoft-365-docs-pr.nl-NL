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
description: Meer informatie over hoe SharePoint Online virussen detecteert in bestanden die gebruikers uploaden en voorkomt dat gebruikers de bestanden kunnen downloaden of synchroniseren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60d696769ea402e6e2d0e52a1f6633e7962b8329
ms.sourcegitcommit: f2275d2fbc17a8b5b5da723c7353d3f36c6fb2a7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2020
ms.locfileid: "45029606"
---
# <a name="virus-detection-in-sharepoint-online"></a>Virusdetectie in SharePoint Online

Microsoft 365 kan uw omgeving beschermen tegen malware door virussen te detecteren in bestanden die gebruikers uploaden naar SharePoint Online. Bestanden kunnen worden gescand op virussen nadat ze zijn geüpload. Als een bestand geïnfecteerd blijkt te zijn, wordt een eigenschap zo ingesteld dat gebruikers het bestand niet kunnen downloaden of synchroniseren.

> [!IMPORTANT]
> Deze antivirusmogelijkheden in SharePoint Online zijn een manier om virussen te bevatten. Ze zijn niet bedoeld als een enkel punt van verdediging tegen malware voor uw omgeving. We moedigen alle klanten aan om antimalwarebescherming op verschillende lagen te beoordelen en te implementeren en best practices toe te passen voor het beveiligen van uw bedrijfsinfrastructuur. Zie [Roadmap beveiliging](security-roadmap.md)voor meer informatie over strategieën en best practices.

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Wat gebeurt er als een geïnfecteerd bestand wordt geüpload naar SharePoint Online?

Microsoft 365 maakt gebruik van een veel voorkomende virusdetectie-engine. De engine draait asynchroon binnen SharePoint Online en scant sommige bestanden nadat deze zijn geüpload. Heuristiek wordt gebruikt om te bepalen welke bestanden worden gescand. Wanneer wordt vastgesteld dat een bestand een virus bevat, wordt het gemarkeerd zodat het niet opnieuw kan worden gedownload. In april 2018 hebben we de limiet van 25 MB voor gescande bestanden verwijderd.

Dit is wat er gebeurt:

1. Een gebruiker uploadt een bestand naar SharePoint Online.

2. SharePoint Online bepaalt of het bestand voldoet aan de criteria voor een scan.

3. De virusdetectie-engine scant het bestand.

4. Als een virus wordt gevonden, stelt de virusengine een eigenschap in het bestand aan die aangeeft dat het is geïnfecteerd.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Wat gebeurt er als een gebruiker een geïnfecteerd bestand probeert te downloaden met behulp van de browser?

Als een bestand is geïnfecteerd, kunnen gebruikers het bestand niet downloaden van SharePoint Online met behulp van de browser.

Dit is wat er gebeurt:

1. Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand te downloaden van SharePoint Online.

2. De gebruiker krijgt een waarschuwing dat een virus is gedetecteerd. De gebruiker krijgt de optie om het bestand te downloaden en te proberen om het schoon te maken met behulp van hun eigen antivirus software.

> [!NOTE]
> U de parameter *DisallowInfectedFileDownload* op de cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers een geïnfecteerd bestand downloaden, zelfs in het anti-viruswaarschuwingsvenster.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Wat gebeurt er als de OneDrive-synchronisatieclient een geïnfecteerd bestand probeert te synchroniseren?

Of gebruikers nu bestanden synchroniseren met de nieuwe OneDrive-synchronisatieclient (OneDrive.exe) of de vorige synchronisatieclient van OneDrive voor Bedrijven (Groove.exe), als een bestand een virus bevat, wordt deze niet gedownload door de synchronisatieclient. De synchronisatieclient geeft een melding weer dat het bestand niet kan worden gesynchroniseerd.

## <a name="more-information"></a>Meer informatie

Zie [Beveiligen tegen bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) en [ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) voor meer informatie over het configureren van SharePoint Online antivirus.


