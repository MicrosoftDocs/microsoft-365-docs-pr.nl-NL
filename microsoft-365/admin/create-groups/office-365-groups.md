---
title: Overzicht van Microsoft 365 groepen voor beheerders
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over Microsoft 365 groepen.
ms.openlocfilehash: 711ab7e7818b266d7cbdbe076e30355d29bc3eeb
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307263"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Overzicht van Microsoft 365 groepen voor beheerders

Microsoft 365 groepen is de Foundation-lidmaatschaps service waarmee alle teamwerk wordt bestuurd in Microsoft 365. Met de groepen Microsoft 365 kunt u een groep mensen toegang geven tot een verzameling samenwerkings bronnen, zodat de personen die u wilt delen. Deze informatiebronnen omvatten:

- Een gedeeld postvak in van Outlook
- Een gedeelde agenda
- Een SharePoint-documentbibliotheek
- Een planner
- Een OneNote-notitieblok
- Power BI
- Yammer (als de groep is gemaakt op basis van Yammer)
- Een team (als de groep is gemaakt op basis van teams)
- Routekaart (als u project voor het web hebt)

Met een Microsoft 365-groep hoeft u niet handmatig machtigingen toe te wijzen voor elk van deze resources, aangezien het toevoegen van personen aan de groep automatisch de juiste machtigingen biedt voor de hulpmiddelen die de groep biedt.

Gebruikers kunnen een groep maken, tenzij u het [maken van groepen beperkt tot een bepaalde groep personen](manage-creation-of-groups.md). Als u het maken van een groep beperkt, kunnen gebruikers die geen groepen maken, geen SharePoint-sites, planners of teams maken. Voor deze services moeten de personen die de persoon maken een groep kunnen maken. Gebruikers kunnen nog steeds deelnemen aan groepsactiviteiten, zoals het maken van taken in planner of het gebruik van teams-chat, mits ze lid zijn van de groep.

Groepen hebben de volgende functies:

- **Eigen** aren-groepseigenaren kunnen leden toevoegen of verwijderen en unieke machtigingen hebben, zoals de mogelijkheid om gesprekken te verwijderen uit het gedeelde Postvak in of andere instellingen voor de groep te wijzigen. Groepseigenaren kunnen de naam van de groep wijzigen, de beschrijving of afbeelding bijwerken.
- **Leden** hebben toegang tot alles in de groep, maar kunnen de groepsinstellingen niet wijzigen. Standaard kunnen groepsleden gasten uitnodigen om lid te worden van de groep, maar u kunt [deze instelling wel zelf instellen](manage-guest-access-in-groups.md).
- **Gasten** : gasten van een groep zijn leden van buiten uw organisatie.

Alleen globale beheerders, gebruikers beheerders en groepen beheerders kunnen groepen maken en beheren in het Microsoft 365-Beheercentrum. U kunt geen gedelegeerde beheerder zijn (bijvoorbeeld een consultant die plaatsvervangend beheerder is).

Als beheerder kunt u het volgende doen:

- [Opgeven wie groepen kan maken](manage-creation-of-groups.md)
- [Een naamgevingsbeleid maken voor groepen in uw organisatie](groups-naming-policy.md)
- [Het domein kiezen dat u wilt gebruiken om een groep te maken](choose-domain-to-create-groups.md)
- [Gasttoegang tot groepen beheren](manage-guest-access-in-groups.md)
- [Een verwijderde groep herstellen](restore-deleted-group.md) (binnen 30 dagen na verwijdering)

Als u een meer geautomatiseerde manier wilt gebruiken voor het beheren van de levenscyclus van uw Microsoft 365-groepen, kunt u gebruikmaken van verloopbeleid voor het verlopen van groepen met een specifiek tijdsinterval. De eigenaren van de groep krijgen een e-mail van 30, 15 en 1 dag voor de groeps vervaldatum, zodat ze de groep gemakkelijk kunnen verlengen als dit nog niet het geval is. Zie: [verloopbeleid voor groepen van Microsoft 365](office-365-groups-expiration-policy.md).

U kunt groepen beheren via het Microsoft 365-Beheercentrum of via [PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel).

Als u veel gebruikers hebt, bijvoorbeeld in een grote onderneming of Enterprise, hebt u mogelijk veel gebruikers die groepen maken voor verschillende doeleinden. We raden u ten zeerste aan om te controleren of het [plan voor beheer in Microsoft 365 groepen](plan-for-groups-governance.md) geschikt is voor aanbevolen procedures.

## <a name="group-limits"></a>Groeps limieten

De volgende limieten gelden voor Microsoft 365 groepen:

|Maximum...|Value|
|:---------|:----|
|Eigenaren per groep|100|
|Groepen die een gebruiker kan maken|250|
|Groepen die een beheerder kan maken|Tot standaard Tenant limiet van 500K|
|Aantal leden|Meer dan 1.000, hoewel alleen 1.000 de groepsgesprekken tegelijkertijd kunnen openen. <br>Gebruikers kunnen vertraging ondervinden bij het openen van de agenda en gesprekken in zeer grote groepen in Outlook.|
|Aantal groepen waarvan een gebruiker lid kan zijn|1.000|
|Bestandsopslag|1 terabyte + 10 GB per geabonneerde gebruiker + extra aangeschafte opslagruimte. U kunt een onbeperkte hoeveelheid extra opslagruimte aanschaffen.|
|Grootte van groeps Postvak|50 GB|

Het standaard maximum aantal Microsoft 365-groepen dat een organisatie kan hebben, is 500.000. Neem contact op met Microsoft ondersteuning voor meer dan de standaardlimiet. Zie [Microsoft 365 groepen-Help voor beheerders](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)voor meer informatie over limieten voor microsoft 365 groepen.

Het beheren van uw Microsoft 365-groepen is effectiever wanneer u informatie over de juiste actie wilt gebruiken voor groepen. Het Microsoft 365-Beheercentrum heeft een rapportage middel waarmee u zaken kunt zien zoals de opslagruimte, het aantal actieve groepen en zelfs hoe uw gebruikers de groepen gebruiken. Zie: [Microsoft 365-rapporten in het Beheercentrum](../activity-reports/office-365-groups.md) voor meer informatie.

## <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

U kunt met de gebruikers in uw organisatie tekstlabels labels maken die door gebruikers in uw organisatie worden ingesteld wanneer ze een Microsoft 365-groep maken. Met behulp van een vertrouwelijkheids label kunt u het volgende configureren: 

- Privacy (openbaar of privé)
- Toegang tot externe gebruikers
- Toegang tot niet-beheerde apparaten

U kunt bijvoorbeeld een etiket met de naam *zeer vertrouwelijk* maken en opgeven dat een groep die met dit etiket is gemaakt, privé is en geen externe gebruikers toestaat. Wanneer gebruikers in uw organisatie dit label selecteren tijdens het maken van een groep, wordt de groep ingesteld op privé-en groepsleden is niet gemachtigd om externe gebruikers toe te voegen aan de groep.

> [!IMPORTANT]
> Als u momenteel classificatie labels gebruikt, zijn deze niet langer beschikbaar voor gebruikers die groepen maken wanneer de functie gevoelige labels zijn ingeschakeld. 

Zie voor meer informatie over het maken, beheren en gebruiken van palletlabels labels voor het maken van palletlabels de [inhoud in Microsoft teams, Microsoft 365-groepen en SharePoint-sites gebruiken](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="which-microsoft-365-plans-include-groups"></a>Welke Microsoft 365-abonnementen bevatten groepen?

Een Microsoft 365-abonnement met Exchange Online en SharePoint Online ondersteunt groepen. Waaronder de abonnementen Business Essentials en Business Premium, en de Enterprise E1-, E3-en E5-abonnementen. De groep gaat over de licenties van de persoon die de groep maakt (ook wel bekend als de organisator van de groep). Zolang de organisator de juiste licentie heeft voor de functies die u wilt hebben voor de groep, wordt die licentie overgebracht naar de groep.

> [!NOTE]
> Zie voor meer informatie over Microsoft 365-service families en-abonnementen [Microsoft 365-abonnement opties](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Als u een abonnement hebt dat alleen Exchange is, kunt u nog steeds de functies gedeeld postvak in en gedeelde agenda van groepen in Outlook weergeven, maar krijgt u geen documentbibliotheek, planner of andere mogelijkheden.

Microsoft 365-groepen werken met Azure Active Directory (AAD). Welke functies van Azure Active Directory u hebt, is afhankelijk van het Azure Active Directory-abonnement dat u hebt en welke licentie (s) aan de organisator van de groep is toegewezen.

> [!IMPORTANT]
> Voor alle groepsfuncties, als u een Azure AD Premium-abonnement hebt, kunnen gebruikers deelnemen aan de groep, ongeacht of hieraan een licentie voor AAD P1 is toegewezen. Licentieverlening wordt niet afgedwongen.
> Periodieke rapporten genereren op basis van de gebruikers die een licentie missen en aan de vereisten voor de licentievereisten voldoen. Stel dat een gebruiker geen licentie heeft en ze worden toegevoegd aan een groep waarbij het naamgevingsbeleid wordt afgedwongen. Het rapport wordt gemarkeerd voor u dat ze een licentie nodig hebben.

## <a name="related-articles"></a>Verwante artikelen

[Meer informatie over Microsoft 365-groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Distributielijsten upgraden naar Microsoft 365-groepen](../manage/upgrade-distribution-lists.md)

[Microsoft 365-groepen beheren met PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[Limieten voor SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
