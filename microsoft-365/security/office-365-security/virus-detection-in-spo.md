---
title: Ingebouwde virusbeveiliging in SharePoint Online, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Meer informatie over hoe in SharePoint Online virussen worden gedetecteerd in bestanden die gebruikers uploaden en voorkomen dat gebruikers de bestanden downloaden of synchroniseren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ba3d19c6b04b93d9b1089540b7483d8b2e7246c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727497"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Ingebouwde virusbeveiliging in SharePoint Online, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)

Microsoft 365 gebruikt een veelgebruikte virusdetectie-engine voor het scannen van bestanden die gebruikers uploaden naar SharePoint Online, OneDrive en Microsoft Teams. Deze beveiliging is inbegrepen bij alle abonnementen die SharePoint Online, OneDrive en Microsoft Teams bevatten.

> [!IMPORTANT]
> De ingebouwde anti-virusmogelijkheden zijn een manier om virussen te helpen bevatten. Ze zijn niet bedoeld als één verdedigingspunt tegen malware voor uw omgeving. We raden alle klanten aan om anti-malwarebeveiliging op verschillende lagen te onderzoeken en te implementeren en best practices toe te passen voor het beveiligen van hun bedrijfsinfrastructuur. Zie Routekaart voor beveiliging voor meer informatie over strategieën [en](security-roadmap.md)best practices.

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>Wat gebeurt er als een geïnfecteerd bestand wordt geüpload naar SharePoint Online?

De Microsoft 365-virusdetectie-engine wordt asynchroon uitgevoerd (onafhankelijk van bestands uploads) in SharePoint Online. **Alle bestanden worden niet automatisch gescand.** Heuristische gegevens bepalen de bestanden die moeten worden gescand. Wanneer een bestand een virus bevat, wordt het bestand gemarkeerd. In april 2018 hebben we de limiet van 25 MB voor gescande bestanden verwijderd.

Dit is wat er gebeurt:

1. Een gebruiker uploadt een bestand naar SharePoint Online.
2. SharePoint Online bepaalt later, als onderdeel van de virusscanprocessen, of het bestand voldoet aan de criteria voor een scan.
3. Als het bestand voldoet aan de criteria voor een scan, scant de virusdetectie-engine het bestand.
4. Als er een virus wordt gevonden in het gescande bestand, stelt de virusprogramma een eigenschap in op het bestand waarmee wordt aangegeven dat het is geïnfecteerd.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met behulp van de browser?

Als een bestand is geïnfecteerd, kunnen gebruikers het bestand niet downloaden van SharePoint Online via een browser.

Dit is wat er gebeurt:

1. Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand te downloaden van SharePoint Online.
2. De gebruiker krijgt een waarschuwing dat er een virus is gedetecteerd. Standaard krijgt de gebruiker de optie om het bestand te downloaden en te proberen het op te schonen met de antivirussoftware op zijn eigen apparaat.

> [!NOTE]
>
> Beheerders kunnen de parameter *DisallowInfectedFileDownload* gebruiken op de cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell om te voorkomen dat gebruikers geïnfecteerde bestanden downloaden, zelfs in het waarschuwingsvenster voor virussen. Zie [SharePoint Online PowerShell](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden voor instructies.
>
> Zodra u de parameter *DisallowInfectedFileDownload* inschakelen, wordt de toegang tot de gedetecteerde/geblokkeerde bestanden volledig geblokkeerd voor gebruikers en beheerders.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Wat gebeurt er wanneer de Synchronisatieclient van OneDrive een geïnfecteerd bestand probeert te synchroniseren?

OneDrive-synchronisatiecl clients downloaden geen bestanden die virussen bevatten. De synchronisatieclient geeft een melding weer dat het bestand niet kan worden gesynchroniseerd.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Uitgebreide mogelijkheden met Microsoft Defender voor Office 365

Microsoft 365-organisaties die Microsoft Defender voor [Office 365](office-365-atp.md) hebben opgenomen in hun abonnement of die zijn gekocht als een invoeg hieraan kunnen veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams inschakelen voor verbeterde rapportage en beveiliging. Zie Veilige bijlagen voor [SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)voor meer informatie.

## <a name="related-articles"></a>Verwante artikelen

[Beveiliging tegen malware en ransomware in Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

Zie Beschermen tegen bedreigingen en Veilige bijlagen voor [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)en Microsoft Teams in te zetten voor meer informatie over antivirus in SharePoint Online, OneDrive en Microsoft Teams. [](protect-against-threats.md)
