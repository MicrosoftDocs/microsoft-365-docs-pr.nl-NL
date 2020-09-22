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
description: In dit artikel leest u hoe u met SharePoint Online virussen kunt herkennen aan bestanden die gebruikers uploaden en voorkomen dat gebruikers de bestanden downloaden of synchroniseren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c65db566f165939d72429bcd61b7d0a880814e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196509"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Virus detectie in SharePoint Online, OneDrive en Microsoft teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365 kan u helpen uw omgeving te beschermen tegen malware door virussen te detecteren in bestanden die gebruikers uploaden naar SharePoint Online, OneDrive en Microsoft teams. Het kan zijn dat bestanden worden gecontroleerd op virussen nadat ze zijn geüpload. Als een bestand is geïnfecteerd met infectie, wordt er een eigenschap ingesteld, zodat gebruikers het bestand niet kunnen downloaden of synchroniseren.

> [!IMPORTANT]
> Deze antivirusfuncties in SharePoint Online zijn een manier om virussen te bevatten. Ze zijn niet bedoeld als één verdedigings punt tegen malware van uw omgeving. We raden u aan alle klanten te beschermen tegen antimalware-beveiliging op verschillende lagen en best practices toe te passen om uw bedrijfsinfrastructuur te beveiligen. Zie voor meer informatie over strategieën en best practices voor [beveiliging](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Wat gebeurt er wanneer een geïnfecteerd bestand wordt geüpload naar SharePoint Online?

Microsoft 365 gebruikt een gangbare virusdetectie-engine. De engine wordt asynchroon uitgevoerd in SharePoint Online en scant sommige bestanden nadat deze zijn geüpload. Heuristiek wordt gebruikt om te bepalen welke bestanden worden gescand. Wanneer een bestand een virus bevat, is dit gemarkeerd zodat het niet meer kan worden gedownload. In april 2018 is de limiet van 25 MB voor gescande bestanden verwijderd.

Dit is wat er gebeurt:

1. Een gebruiker uploadt een bestand naar SharePoint Online.

2. In SharePoint Online wordt bepaald of het bestand voldoet aan de criteria voor een scan.

3. De virusdetectie-engine scant het bestand.

4. Als er een virus wordt gevonden, stelt de virus engine een eigenschap in op het bestand om aan te geven dat het geïnfecteerd is.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met de browser?

Als een bestand is geïnfecteerd, kunnen gebruikers het niet downloaden van SharePoint Online met behulp van de browser.

Dit is wat er gebeurt:

1. Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand te downloaden van SharePoint Online.

2. De gebruiker krijgt een waarschuwing dat er een virus is gedetecteerd. De gebruiker krijgt de mogelijkheid om het bestand te downloaden en te proberen te wissen met behulp van hun eigen antivirussoftware.

> [!NOTE]
>
> U kunt de parameter *DisallowInfectedFileDownload* van de cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers een geïnfecteerd bestand downloaden, zelfs in het waarschuwingsvenster van antivirusprogramma's.
>
> Houd er ook rekening mee dat zodra u de parameter *DisallowInfectedFileDownload* inschakelt, de toegang tot de gedetecteerde/geblokkeerde bestanden volledig wordt geblokkeerd voor gebruikers en beheerders.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Wat gebeurt er wanneer de OneDrive-synchronisatieclient een geïnfecteerd bestand probeert te synchroniseren?

Of gebruikers bestanden synchroniseren met de nieuwe OneDrive-synchronisatieclient (OneDrive.exe) of de vorige synchronisatieclient van OneDrive voor bedrijven (Groove.exe), als een bestand een virus bevat, kan de synchronisatieclient dit niet downloaden. Met de synchronisatieclient wordt een melding weergegeven dat het bestand niet kan worden gesynchroniseerd.

## <a name="extended-capabilities-with-office-365-atp"></a>Uitgebreide mogelijkheden met Office 365 ATP

Voor klanten die Office 365 ATP voor SharePoint, OneDrive en Microsoft teams hebben ingeschakeld, kunt u de beschikbaarheid [voor SharePoint, onedrive en micro](turn-on-atp-for-spo-odb-and-teams.md) Soft teams gebruiken om het beveiligings & voor het beheren van gequarantinee bestanden voor AV-en ATP-detecties te beheren. [Alleen ATP: gebruik de beveiligings & voor nalevings centrum voor het beheren van bestanden die in quarantaine zijn geplaatst](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="more-information"></a>Meer informatie

Zie [beschermen tegen bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) en [Schakel ATP in voor SharePoint, OneDrive en Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) voor meer informatie over het configureren van SharePoint Online-antivirusprogramma.


