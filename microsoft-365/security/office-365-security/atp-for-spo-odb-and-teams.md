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
description: Meer informatie over Geavanceerde bedreigingsbeveiliging van Office 365 voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.openlocfilehash: e4a711d6554ffcb8e291d5b2154120d078995e94
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815407"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP voor SharePoint, OneDrive en Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Overzicht van Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams

Mensen delen regelmatig bestanden en werken samen met SharePoint, OneDrive en Microsoft Teams. Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie op een veiligere manier samenwerken. ATP helpt bij het detecteren en blokkeren van bestanden die zijn geïdentificeerd als kwaadaardig in teamsites en documentbibliotheken.

## <a name="how-office-365-atp-operates"></a>Hoe Office 365 ATP werkt

Wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams als kwaadaardig is aangemerkt, integreert ATP rechtstreeks met de bestandsopslag om dat bestand te vergrendelen. De volgende afbeelding toont een voorbeeld van een kwaadaardig bestand dat in een bibliotheek is gedetecteerd.

![Bestanden in OneDrive voor Bedrijven met een gedetecteerd als kwaadaardig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en web-, mobiele of bureaubladtoepassingen, kan het geblokkeerde bestand niet worden geopend, gekopieerd, verplaatst of gedeeld. Mensen kunnen echter een geblokkeerd bestand verwijderen. Hier volgt een voorbeeld van hoe dat eruit ziet op het mobiele apparaat van een gebruiker:

![Een geblokkeerd bestand verwijderen uit OneDrive voor Bedrijven uit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Afhankelijk van hoe Microsoft 365 is geconfigureerd, kunnen mensen al dan niet de mogelijkheid hebben om een geblokkeerd bestand te downloaden. Zo ziet het downloaden van een geblokkeerd bestand eruit op het mobiele apparaat van een gebruiker:

![Een geblokkeerd bestand downloaden in OneDrive voor Bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="keep-these-points-in-mind"></a>Houd deze punten in gedachten

- ATP scant niet elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams. Dit is normaal. Bestanden worden asynchroon gescand, via een proces dat het delen en gastactiviteitsgebeurtenissen gebruikt, samen met slimme heuristiek en bedreigingssignalen om schadelijke bestanden te identificeren.

- Controleer of uw SharePoint-sites zijn geconfigureerd om de [moderne ervaring](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)te gebruiken. Wanneer een bestand wordt geïdentificeerd als kwaadaardig en geblokkeerd, kunnen mensen zien dat dit is gebeurd in de moderne ervaring, maar niet in de klassieke weergave. ATP-bescherming is van toepassing of de moderne ervaring of de Classic-weergave wordt gebruikt; Visuele indicatoren die een bestand blokkeren, zijn echter alleen aanwezig in de moderne ervaring.

- Bestanden die als kwaadaardig zijn geïdentificeerd in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams worden weergegeven in [rapporten voor Geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md) en in Explorer [(en realtime detecties).](threat-explorer.md)

- ATP maakt deel uit van de algemene strategie voor bedreigingsbescherming van uw organisatie, die anti-spam- en anti-malwarebescherming omvat, evenals veilige links en veilige bijlagen. Zie [Beschermen tegen bedreigingen in Office 365](protect-against-threats.md)voor meer informatie.

- Een SharePoint Online-beheerder kan bepalen of mensen bestanden kunnen downloaden die als kwaadaardig worden gedetecteerd. Dit wordt gedaan door de PowerShell-cmdlet Set-SPOTenant uit te voeren met een parameter DisallowInfectedFileDownload (zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Quarantaine in ATP voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams

 Vanaf eind mei 2018 worden [quarantainemogelijkheden](quarantine-email-messages.md) in het Security &amp; Compliance Center uitgebreid naar ATP voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

Wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams als kwaadaardig wordt aangemerkt, wordt dit bestand niet alleen als kwaadaardig aangemerkt, maar ook dat het bestand niet wordt geopend of gedeeld, maar ook in een lijst met in quarantaine geplaatste items wordt opgenomen. (In de beveiliging &amp; Compliance Center, ga naar **Quarantaine voor bedreigingsbeheercontrole** \> **Review** \> **Quarantine** en filter **op Bestanden**.)

Als u deel uitmaakt van het Microsoft 365 for Business Security-team van uw organisatie en de benodigde [machtigingen hebt toegewezen in het Security &amp; Compliance Center,](permissions-in-the-security-and-compliance-center.md)u bestanden downloaden, vrijgeven, rapporteren en verwijderen die door ATP als kwaadaardig worden gedetecteerd uit quarantaine.

- Als u een bestand **vrijgeeft en rapporteert,** wordt het ATP-blok in het bestand in de desbetreffende teamsite of documentbibliotheek voor SharePoint, OneDrive of Microsoft Teams verwijderd. Gebruikers kunnen het bestand vervolgens openen, delen en downloaden. En wanneer de optie **Rapport verzenden naar Microsoft** is geselecteerd, wordt het bestand gerapporteerd als een fout-positief aan Microsoft.

- **Als u een bestand verwijdert,** wordt het bestand uit quarantaine verwijderd. Het bestand wordt echter nog steeds geblokkeerd omdat het wordt geopend of gedeeld. Het bestand moet ook worden verwijderd in de respectievelijke documentbibliotheek of teamsite (SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams).

- Als u **een bestand downloadt,** u het bestand downloaden en analyseren op fout-positieven.

## <a name="next-steps"></a>Volgende stappen

 - [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)

 - [Informatie weergeven over schadelijke bestanden die zijn gedetecteerd in SharePoint, OneDrive of Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

