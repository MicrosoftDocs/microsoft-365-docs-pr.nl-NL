---
title: Overzicht van Microsoft 365-groepen voor beheerders
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over Microsoft 365-groepen.
ms.openlocfilehash: aca6dfee26e05f162b8cc3efb69005d773a9a9dc
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049165"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Overzicht van Microsoft 365-groepen voor beheerders

Microsoft 365 Groups is de fundamentele lidmaatschapsservice die alle teamwork in Microsoft 365 stimuleert. Met Microsoft 365-groepen u een groep mensen toegang geven tot een verzameling samenwerkingsbronnen die deze mensen kunnen delen. Deze bronnen omvatten:

- Een gedeeld Postvak IN van Outlook
- Een gedeelde agenda
- Een SharePoint-documentbibliotheek
- Een planner
- Een OneNote-notitieblok
- Power BI
- Yammer (als de groep is gemaakt vanuit Yammer)
- Een team (als de groep is gemaakt vanuit Teams)
- Roadmap (als je Project voor het web hebt)

Met een Microsoft 365-groep hoeft u geen machtigingen handmatig toe te wijzen aan elk van deze bronnen, omdat het toevoegen van mensen aan de groep hen automatisch de machtigingen geeft die ze nodig hebben voor de hulpprogramma's die de groep biedt.

Elke gebruiker kan een groep maken, tenzij u [het maken van groepen beperkt tot een specifieke groep personen.](manage-creation-of-groups.md) Houd er rekening mee dat als u het maken van groepen beperkt, gebruikers die geen groepen kunnen maken, geen SharePoint-sites, Planners of teams kunnen maken. Deze services vereisen dat de mensen die ze maken, een groep kunnen maken. Gebruikers kunnen nog steeds deelnemen aan groepsactiviteiten, zoals het maken van taken in Planner of het gebruik van Teams chat, op voorwaarde dat ze lid zijn van de groep.

Groepen hebben de volgende rollen:

- **Eigenaren** - Groepseigenaren kunnen leden toevoegen of verwijderen en hebben unieke machtigingen, zoals de mogelijkheid om gesprekken uit het gedeelde postvak in te verwijderen of verschillende instellingen over de groep te wijzigen. Groepseigenaren kunnen de naam van de groep wijzigen, de beschrijving of afbeelding bijwerken en meer.
- **Leden** - Leden hebben toegang tot alles in de groep, maar kunnen de groepsinstellingen niet wijzigen. Standaard kunnen groepsleden gasten uitnodigen om lid te worden van uw groep, maar u [die instelling wel beheren.](manage-guest-access-in-groups.md)
- **Gasten** - Groepsgasten zijn leden van buiten uw organisatie.

Alleen globale beheerders, gebruikersbeheerders en groepenbeheerders kunnen groepen maken en beheren in het Microsoft 365-beheercentrum. U kunt geen gedelegeerde beheerder zijn (bijvoorbeeld een consultant die plaatsvervangend beheerder is).

Als beheerder u:

- [Opgeven wie groepen kan maken](manage-creation-of-groups.md)
- [Een naamgevingsbeleid maken voor groepen in uw organisatie](groups-naming-policy.md)
- [Kiezen welk domein u wilt gebruiken bij het maken van een groep](choose-domain-to-create-groups.md)
- [Gasttoegang tot groepen beheren](manage-guest-access-in-groups.md)
- [Een verwijderde groep herstellen](restore-deleted-group.md) (binnen 30 dagen na verwijdering)

Als u de voorkeur geeft aan een meer geautomatiseerde manier om de levenscyclus van uw Microsoft 365-groepen te beheren, u het verloopbeleid gebruiken om groepen op een bepaald tijdsinterval te verlopen. De eigenaren van de groep krijgen een e-mail 30, 15 en 1 dag voor de groepsvervaldatum waarmee ze de groep eenvoudig kunnen vernieuwen als deze nog nodig is. Zie: [Microsoft 365-groepsverloopbeleid](office-365-groups-expiration-policy.md).

U uw groepen beheren vanuit het Microsoft 365-beheercentrum of [met PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

Als u veel gebruikers hebt, zoals in een groot bedrijf of onderneming, u veel gebruikers hebben die groepen maken voor verschillende doeleinden. We raden u ten zeerste aan [plan voor governance in Microsoft 365-groepen](plan-for-groups-governance.md) te bekijken voor aanbevolen procedures.

## <a name="group-limits"></a>Groepslimieten

De volgende limieten zijn van toepassing op Microsoft 365-groepen:

|Maximale...|Value|
|:---------|:----|
|Eigenaren per groep|100|
|Groepen die een gebruiker kan maken|250|
|Groepen die een beheerder kan maken|Maximaal standaard tenantlimiet van 500K|
|Aantal leden|Meer dan 1.000, hoewel slechts 1.000 gelijktijdig toegang hebben tot de groepsgesprekken. <br>Gebruikers kunnen vertragingen opmerken bij het openen van de agenda en gesprekken in zeer grote groepen in Outlook.|
|Aantal groepen waarvan een gebruiker lid kan zijn|1,000|
|Bestandsopslag|1 Terabyte + 10 GB per geabonneerde gebruiker + eventuele extra opslagruimte aangeschaft. U een onbeperkte hoeveelheid extra opslagruimte aanschaffen.|
|Grootte van postvak groeperen|50 GB|

Het standaard maximumaantal Microsoft 365-groepen dat een organisatie kan hebben, is 500.000, maar kan op aanvraag worden verhoogd. Zie Microsoft 365-groepen - Help voor beheerders voor meer informatie over de limieten van Microsoft [365-groepen.](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

Het beheren van uw Microsoft 365-groepen is effectiever wanneer u bruikbare informatie hebt over het gebruik van groepen. Het Microsoft 365-beheercentrum heeft een rapportagetool waarmee u dingen zien zoals opslaggebruik, hoeveel actieve groepen u hebt en zelfs hoe uw gebruikers de groepen gebruiken. Zie: [Microsoft 365 Rapporten in het beheercentrum](../activity-reports/office-365-groups.md) voor meer informatie.

## <a name="which-microsoft-365-plans-include-groups"></a>Welke Microsoft 365-abonnementen bevatten groepen?

Elk Microsoft 365-abonnement met Exchange Online en SharePoint Online ondersteunt groepen. Dat geldt ook voor de Business Essentials- en Business Premium-abonnementen en de Enterprise E1-, E3- en E5-abonnementen. De groep neemt de licentie van de persoon die de groep maakt (ook bekend als de "organisator" van de groep). Zolang de organisator de juiste licentie heeft voor welke functies u wilt dat de groep heeft, zal die licentie aan de groep worden overgegeven.

> [!NOTE]
> Zie [Microsoft 365-abonnementsopties](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) voor meer informatie over Microsoft 365-servicefamilies en -abonnementen

Als u een Exchange-abonnement hebt, u nog steeds de gedeelde inbox- en gedeelde agendafuncties van groepen in Outlook krijgen, maar u krijgt de documentbibliotheek, planner of een van de andere mogelijkheden niet.

Microsoft 365-groepen werken met Azure Active Directory (AAD). Welke groepenfuncties u krijgt, is afhankelijk van welk Azure Active Directory-abonnement u hebt en welke licentie(s) is toegewezen aan de organisator van de groep.

> [!IMPORTANT]
> Voor alle groepenfuncties kunnen gebruikers, als u een Azure AD Premium-abonnement hebt, lid worden van de groep, ongeacht of ze al dan niet een AAD P1-licentie aan hen hebben toegewezen. Licenties worden niet afgedwongen.
> Periodiek zullen we gebruiksrapporten genereren die u vertellen welke gebruikers een licentie missen en er een nodig hebben die aan hen is toegewezen om te voldoen aan de licentievereisten. Stel dat een gebruiker geen licentie heeft en wordt toegevoegd aan een groep waarin het naamgevingsbeleid wordt afgedwongen. Het rapport zal vlag voor u dat ze een licentie nodig hebben.

## <a name="related-articles"></a>Verwante artikelen

[Meer informatie over Microsoft 365-groepen](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Distributielijsten upgraden naar Microsoft 365-groepen](../manage/upgrade-distribution-lists.md)

[Microsoft 365-groepen beheren met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[Limieten voor SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
