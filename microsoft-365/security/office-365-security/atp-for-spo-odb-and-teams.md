---
title: Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams
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
description: Breid Geavanceerde bedreigingsbeveiliging van Office 365 uit naar bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams om een veiligere samenwerking voor uw organisatie mogelijk te maken.
ms.openlocfilehash: 3105a9443ddab483bc5ac4037e5260b354d64de9
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806843"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Overzicht van Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams

Mensen delen regelmatig bestanden en werken samen met SharePoint, OneDrive en Microsoft Teams. Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie op een veiligere manier samenwerken. ATP helpt bij het detecteren en blokkeren van bestanden die zijn geïdentificeerd als kwaadaardig in teamsites en documentbibliotheken.

## <a name="how-it-works"></a>Hoe het werkt

Wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams is geïdentificeerd als kwaadaardig, integreert ATP rechtstreeks met de bestandsstores om dat bestand te vergrendelen. De volgende afbeelding toont een voorbeeld van een kwaadaardig bestand dat in een bibliotheek is gedetecteerd.

![Bestanden in OneDrive voor Bedrijven met een gedetecteerd als kwaadaardig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en web-, mobiele of bureaubladtoepassingen, kan het geblokkeerde bestand niet worden geopend, gekopieerd, verplaatst of gedeeld. Mensen kunnen echter wel een geblokkeerd bestand verwijderen. Hier volgt een voorbeeld van hoe dat eruit ziet op het mobiele apparaat van een gebruiker:

![Een geblokkeerd bestand verwijderen uit OneDrive voor Bedrijven vanuit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Afhankelijk van hoe Office 365 is geconfigureerd, kunnen mensen wel of niet de mogelijkheid hebben om een geblokkeerd bestand te downloaden. Zo ziet het downloaden van een geblokkeerd bestand eruit op het mobiele apparaat van een gebruiker:

![Een geblokkeerd bestand downloaden in OneDrive voor Bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)voor meer informatie.

## <a name="keep-these-points-in-mind"></a>Houd deze punten in gedachten

- ATP scant niet elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams. Dit is normaal. Bestanden worden asynchroon gescand, via een proces dat gebruik maakt van gebeurtenissen op het gebied van delen en gastactiviteiten, samen met slimme heuristiek en bedreigingssignalen om schadelijke bestanden te identificeren.

- Controleer of uw SharePoint-sites zijn geconfigureerd om de [moderne ervaring](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)te gebruiken. Wanneer een bestand wordt geïdentificeerd als kwaadaardig en geblokkeerd, kunnen mensen zien dat dit is opgetreden in de moderne ervaring, maar niet in de klassieke weergave. ATP-bescherming is van toepassing of de moderne ervaring of de klassieke weergave wordt gebruikt; Visuele indicatoren dat een bestand wordt geblokkeerd, zijn echter alleen aanwezig in de moderne ervaring.

- Bestanden die zijn geïdentificeerd als kwaadaardig in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams, worden weergegeven in [rapporten voor Geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md) en in [Explorer (en realtime detecties).](threat-explorer.md)

- ATP maakt deel uit van de algemene strategie voor bedreigingsbescherming van uw organisatie, die antispam- en anti-malwarebescherming omvat, evenals veilige koppelingen en veilige bijlagen. Zie [Beschermen tegen bedreigingen in Office 365](protect-against-threats.md)voor meer informatie.

- Een SharePoint Online-beheerder kan bepalen of mensen bestanden kunnen downloaden die als kwaadaardig worden gedetecteerd. Dit wordt gedaan door de PowerDlet Set-SPOTenant PowerShell uit te voeren met behulp van een parameter DisallowInfectedFileDownload (zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams).](turn-on-atp-for-spo-odb-and-teams.md)

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Quarantaine in ATP voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams

 Vanaf eind mei 2018 worden de &amp; [quarantainemogelijkheden](quarantine-email-messages.md) in het Security Compliance Center uitgebreid naar ATP voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

Wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams als kwaadaardig wordt aangemerkt, wordt dat bestand naast het blokkeren van het bestand dat wordt geopend of gedeeld, naast het blokkeren van het bestand dat wordt geopend of gedeeld, opgenomen in een lijst met in quarantaine geplaatste items. (Ga in &amp; het Security Compliance Center naar **Quarantine controleren van** \> het risicobeheer **en** \> **Quarantine** filter voor **inhoud**.)

Als u deel uitmaakt van het Office 365-beveiligingsteam van uw organisatie en de [benodigde machtigingen hebt toegewezen in het Office 365 Security &amp; Compliance Center,](permissions-in-the-security-and-compliance-center.md)u bestanden die door ATP als kwaadaardig zijn gedetecteerd, downloaden, vrijgeven, rapporteren en verwijderen uit quarantaine.

- Als u een bestand **vrijgeeft en rapporteert,** wordt het ATP-blok in het bestand in de betreffende teamsite of documentbibliotheek voor SharePoint, OneDrive of Microsoft Teams verwijderd. Gebruikers kunnen het bestand vervolgens openen, delen en downloaden. En wanneer de optie **Rapport verzenden naar Microsoft** is geselecteerd, wordt het bestand gerapporteerd als een false positive voor Microsoft.

- **Als u een bestand verwijdert,** wordt het bestand uit quarantaine verwijderd. Het bestand wordt echter nog steeds geblokkeerd voor het openen of delen van het bestand. Het bestand moet ook worden verwijderd in de desbetreffende documentbibliotheek of teamsite (SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams).

- **Het downloaden van een bestand** stelt u in staat om het bestand te downloaden en te analyseren op eventuele false positives.

## <a name="next-steps"></a>Volgende stappen

1. [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)

2. [Informatie weergeven over schadelijke bestanden die zijn gedetecteerd in SharePoint, OneDrive of Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

