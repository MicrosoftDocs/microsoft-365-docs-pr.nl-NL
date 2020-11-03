---
title: Ingebouwde antivirusbeveiliging in SharePoint Online, OneDrive en Microsoft teams
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
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844234"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Ingebouwde antivirusbeveiliging in SharePoint Online, OneDrive en Microsoft teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 gebruikt een gangbare virusdetectie-engine voor het scannen van bestanden die gebruikers uploaden naar SharePoint Online, OneDrive en Microsoft teams. Deze bescherming is inbegrepen in alle abonnementen, waaronder SharePoint Online, OneDrive en Microsoft teams.

> [!IMPORTANT]
> De ingebouwde anti-virus functies vormen een manier om virussen te kunnen bevatten. Ze zijn niet bedoeld als één verdedigings punt tegen malware van uw omgeving. We raden u aan alle klanten te beschermen tegen beveiliging tegen malware tegen verschillende lagen en best practices op te zetten voor de beveiliging van hun bedrijfsinfrastructuur. Zie voor meer informatie over strategieën en best practices voor [beveiliging](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Wat gebeurt er wanneer een geïnfecteerd bestand wordt geüpload naar SharePoint Online?

De Microsoft 365-virusdetectie-engine wordt asynchroon uitgevoerd in SharePoint Online. **Alle bestanden worden niet automatisch gescand tijdens het uploaden**. Heuristiek bepaalt welke bestanden moeten worden gescand. Wanneer een bestand een virus bevat, wordt het bestand gemarkeerd zodat het niet opnieuw kan worden gedownload. In april 2018 is de limiet van 25 MB voor gescande bestanden verwijderd.

Dit is wat er gebeurt:

1. Een gebruiker uploadt een bestand naar SharePoint Online.
2. In SharePoint Online wordt bepaald of het bestand voldoet aan de criteria voor een scan.
3. De virusdetectie-engine scant het bestand.
4. Als er een virus wordt gevonden, stelt de virus engine een eigenschap in op het bestand om aan te geven dat het geïnfecteerd is.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met de browser?

Als een bestand is geïnfecteerd, kunnen gebruikers het niet downloaden van SharePoint Online met behulp van een browser.

Dit is wat er gebeurt:

1. Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand te downloaden van SharePoint Online.
2. De gebruiker krijgt een waarschuwing dat er een virus is gedetecteerd. Standaard krijgt de gebruiker de mogelijkheid om het bestand te downloaden en proberen het te wissen met de antivirussoftware op hun eigen apparaat.

> [!NOTE]
>
> Beheerders kunnen de parameter *DisallowInfectedFileDownload* van de cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) van SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers geïnfecteerde bestanden downloaden, ook in het waarschuwingsvenster van antivirusprogramma's. Zie [SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)voor instructies.
>
> Zodra u de parameter *DisallowInfectedFileDownload* inschakelt, wordt de toegang tot de gedetecteerde/geblokkeerde bestanden volledig geblokkeerd voor gebruikers en beheerders.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Wat gebeurt er wanneer de OneDrive-synchronisatieclient een geïnfecteerd bestand probeert te synchroniseren?

OneDrive-synchronisatieclient downloaden geen bestanden die virussen bevatten. Met de synchronisatieclient wordt een melding weergegeven dat het bestand niet kan worden gesynchroniseerd.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Uitgebreide mogelijkheden met Microsoft Defender voor Office 365

Microsoft 365-organisaties waarop [Microsoft Defender for Office 365](office-365-atp.md) in hun abonnement is opgenomen of als een invoegtoepassing zijn gekocht, kunnen ATP voor SharePoint, OneDrive en Microsoft teams gebruiken voor uitgebreide rapportage en bescherming. Zie [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md)voor meer informatie.

## <a name="more-information"></a>Meer informatie

Zie voor meer informatie over anti-virus in SharePoint Online, OneDrive en Microsoft teams voor meer informatie over [bedreigingen](protect-against-threats.md) [voor SharePoint, Onedrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).
