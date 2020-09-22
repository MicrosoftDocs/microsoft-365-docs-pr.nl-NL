---
title: ATP voor SharePoint, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Meer informatie over Office 365 Advanced Threat Protection voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams.
ms.openlocfilehash: 9831b61fafc7cb4696fbad3d569f061612f85fe1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199037"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP voor SharePoint, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Overzicht van Office 365 ATP voor SharePoint, OneDrive en Microsoft teams

Gebruikers delen vaak bestanden en werken met SharePoint, OneDrive en Microsoft teams. Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie op een veiligere manier samenwerken. Met ATP kunt u bestanden detecteren en blokkeren die als schadelijk zijn aangeduid in team sites en documentbibliotheken.

## <a name="how-office-365-atp-operates"></a>De werking van Office 365 ATP

Wanneer een bestand in SharePoint Online, OneDrive voor bedrijven en Microsoft teams als schadelijk is geïdentificeerd, wordt de ATP rechtstreeks geïntegreerd met de bestandsarchieven om dit bestand te vergrendelen. In de volgende afbeelding ziet u een voorbeeld van een schadelijk bestand dat is gevonden in een bibliotheek.

![Bestanden in OneDrive voor bedrijven met een gedetecteerde schadelijke versie](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en Web-, mobiele en bureaubladtoepassingen, kunt u het geblokkeerde bestand niet openen, kopiëren, verplaatsen of delen. Personen kunnen echter wel een geblokkeerd bestand verwijderen. Hier ziet u een voorbeeld van wat u ziet op het mobiele apparaat van een gebruiker:

![Een geblokkeerd bestand verwijderen uit OneDrive voor bedrijven uit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Afhankelijk van de manier waarop Microsoft 365 is geconfigureerd, kunnen personen een geblokkeerd bestand misschien wel of mogelijk niet downloaden. Het downloaden van een geblokkeerd bestand ziet er als volgt uit op het mobiele apparaat van een gebruiker:

![Een geblokkeerd bestand downloaden in OneDrive voor bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="keep-these-points-in-mind"></a>Let op de volgende punten

- Met ATP kunt u niet elk afzonderlijk bestand in SharePoint Online, OneDrive voor bedrijven of Microsoft teams scannen. Dit is inherent aan het ontwerp van het product. Bestanden worden asynchroon gescand, via een proces waarbij gebeurtenissen voordelen en gebeurtenissen met gebeurtenissen worden gebruikt in combinatie met slimme heuristiek en bedreigings signalen om kwaadaardige bestanden te identificeren.

- Zorg ervoor dat de SharePoint-sites zijn geconfigureerd voor gebruik van de [moderne ervaring](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). Wanneer een bestand wordt geïdentificeerd als schadelijk en geblokkeerd, kunnen personen zien dat dit is gebeurd in de moderne ervaring, maar niet in de klassieke weergave. ATP-beveiliging is van toepassing op de meest recente ervaring of de klassieke weergave. bestaande visuele indicatoren die een bestand blokkeert, worden echter alleen weergegeven in de moderne ervaring.

- Bestanden die worden geïdentificeerd als schadelijk in SharePoint Online, OneDrive voor bedrijven of Microsoft teams, worden weergegeven in [rapporten voor Office 365 Advanced Threat Protection](view-reports-for-atp.md) en in [Verkenner (en realtime-detectie)](threat-explorer.md).

- ATP maakt deel uit van de algemene strategie voor risico beveiliging van uw organisatie, waaronder antispam en bescherming tegen malware, en veilige koppelingen en veilige bijlagen. Voor meer informatie raadpleegt u [bescherming tegen bedreigingen in Office 365](protect-against-threats.md).

- Een SharePoint Online-beheerder kan bepalen of personen bestanden kunnen downloaden die als schadelijk zijn gevonden. Dit doet u door de PowerShell-cmdlet Set-SPOTenant uit te voeren met behulp van een parameter DisallowInfectedFileDownload (Zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md)).

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Quarantaine in ATP voor SharePoint Online, OneDrive voor bedrijven en Microsoft teams

 Vanaf te laat mei 2018 worden [quarantaine](quarantine-email-messages.md) functies in het beveiligings &amp; compliance-centrum uitgebreid met ATP voor SharePoint Online, OneDrive voor bedrijven en Microsoft teams.

Wanneer een bestand in SharePoint Online, OneDrive voor bedrijven, OneDrive voor bedrijven of Microsoft teams als schadelijk wordt geïdentificeerd, wordt dat bestand toegevoegd aan een lijst met items in quarantaine. (In de beveiliging &amp; Compliance Center, ga naar **risicobeheer** , ga naar Quarantine, \> **Evalueer** \> **Quarantine** en filter voor **bestanden**.)

Als u deel uitmaakt van het beveiligingsteam van Microsoft 365 voor bedrijven en de benodigde [machtigingen voor het beveiligings &amp; centrum hebt toegewezen](permissions-in-the-security-and-compliance-center.md), kunt u bestanden downloaden, vrijgeven, melden en verwijderen die als schadelijk zijn gedetecteerd in de quarantaine.

- Het uitdelen **en rapporteren** van een bestand: Hiermee verwijdert u het ATP-blok voor het bestand in de desbetreffende team site of documentbibliotheek voor SharePoint, OneDrive of Microsoft teams. Gebruikers kunnen vervolgens het bestand openen, delen en downloaden. Wanneer de optie **rapport verzenden naar Microsoft** is geselecteerd, wordt het bestand als een fout positief naar Microsoft gerapporteerd.

- **Als u een bestand verwijdert** , verwijdert u het bestand in quarantaine. het bestand is echter nog steeds geblokkeerd om te worden geopend of gedeeld. Het bestand moet ook worden verwijderd uit de bijbehorende documentbibliotheek of team site (SharePoint Online, OneDrive voor bedrijven of Microsoft teams).

- Als u **een bestand downloadt** , kunt u het bestand downloaden en analyseren voor willekeurige onwaar positief.

## <a name="next-steps"></a>Volgende stappen

 - [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)

 - [Informatie over schadelijke bestanden weergeven die zijn gevonden in SharePoint, OneDrive of Microsoft teams](malicious-files-detected-in-spo-odb-or-teams.md)

