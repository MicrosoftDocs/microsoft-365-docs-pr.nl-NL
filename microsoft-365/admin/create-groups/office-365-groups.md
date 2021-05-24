---
title: Overzicht van Microsoft 365 groepen voor beheerders
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Met Microsoft 365 Groepen kunt u teamwerk in verschillende Microsoft 365 stimuleren door een groep personen toegang te geven tot een verzameling gedeelde resources.
ms.openlocfilehash: f940872a3e4ba2aeeb62247c2898d5a4c0dec85f
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635748"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Overzicht van Microsoft 365 groepen voor beheerders

Microsoft 365 Groepen is de basislidmaatschapsservice die alle teamwerk in Microsoft 365. Met Microsoft 365 Groepen kunt u een groep personen toegang geven tot een verzameling gedeelde resources. Deze bronnen zijn:

- Een gedeeld Outlook Postvak IN
- Een gedeelde agenda
- Een SharePoint documentbibliotheek
- Een Planner
- Een OneNote notitieblok
- Power BI
- Yammer (als de groep is gemaakt op Yammer)
- Een team (als de groep is gemaakt op Teams)
- Routekaart (als u Project voor het web)
- Stream

Met een Microsoft 365 groep hoeft u niet handmatig machtigingen toe te wijzen aan elk van deze resources. Als u personen toevoegt aan de groep, krijgen ze automatisch de machtigingen die ze nodig hebben.

Elke gebruiker kan een groep maken, tenzij u het maken van groepen beperkt [tot een specifieke set personen.](../../solutions/manage-creation-of-groups.md) Als u het maken van groepen beperkt, kunnen gebruikers die geen groepen kunnen maken geen SharePoint sites, Planners of teams maken. Voor deze services moeten de personen die ze maken, een groep kunnen maken. Gebruikers kunnen nog steeds deelnemen aan groepsactiviteiten, zoals het maken van taken in Planner of het gebruik Teams chat, mits ze lid zijn van de groep.

Groepen hebben de volgende rollen:

- **Eigenaren:** groepseigenaren kunnen leden toevoegen of verwijderen en hebben unieke machtigingen, zoals de mogelijkheid om gesprekken uit het gedeelde Postvak IN te verwijderen of verschillende instellingen voor de groep te wijzigen. Groepseigenaren kunnen de naam van de groep wijzigen, de beschrijving of afbeelding bijwerken en meer.
- **Leden:** leden hebben toegang tot alles in de groep, maar kunnen de groepsinstellingen niet wijzigen. Standaard kunnen groepsleden gasten uitnodigen om deel te nemen aan uw groep, maar u kunt [deze instelling bepalen.](manage-guest-access-in-groups.md)
- **Gasten** - Groepsgasten zijn leden van buiten uw organisatie.

Alleen globale beheerders, gebruikersbeheerders en groepenbeheerders kunnen groepen maken en beheren in het Microsoft 365 beheercentrum. U kunt geen gedelegeerde beheerder zijn (bijvoorbeeld een consultant die plaatsvervangend beheerder is).

Als beheerder kunt u het volgende doen:

- [Opgeven wie groepen kan maken](../../solutions/manage-creation-of-groups.md)
- [Een naamgevingsbeleid maken voor groepen in uw organisatie](../../solutions/groups-naming-policy.md)
- [Kies welk domein u wilt gebruiken bij het maken van een groep](../../solutions/choose-domain-to-create-groups.md)
- [Gasttoegang tot groepen beheren](manage-guest-access-in-groups.md)
- [Een verwijderde groep herstellen](restore-deleted-group.md) (binnen 30 dagen na verwijdering)

Als u liever een meer geautomatiseerde manier hebt om de levenscyclus van uw Microsoft 365 te beheren, kunt u verloopbeleid gebruiken om groepen met een bepaald tijdsinterval te laten verlopen. De eigenaren van de groep ontvangen een e-mail van 30, 15 en 1 dag vóór de verloopdatum van de groep, zodat ze de groep kunnen verlengen als deze nog steeds nodig is. Zie: [Microsoft 365 groep verloopbeleid](../../solutions/microsoft-365-groups-expiration-policy.md).

U kunt uw groepen beheren vanuit het Microsoft 365 beheercentrum of [met PowerShell.](../../enterprise/manage-microsoft-365-groups-with-powershell.md)

Als u veel gebruikers hebt, zoals in een groot bedrijf of grote onderneming, kunt u veel gebruikers hebben die groepen voor verschillende doeleinden maken. We raden u ten zeerste aan plan [voor beheer in](../../solutions/collaboration-governance-overview.md) Microsoft 365 te controleren op aanbevolen procedures.

## <a name="group-limits"></a>Groepslimieten

De volgende limieten zijn van toepassing op Microsoft 365 Groepen:

|Maximum...|Waarde|
|:---------|:----|
|Eigenaren per groep|100|
|Groepen die een gebruiker kan maken|250|
|Groepen die een beheerder kan maken|Maximaal standaard tenantlimiet van 500 K|
|Aantal leden|Meer dan 1.000, maar slechts 1.000 hebben gelijktijdig toegang tot de groepsgesprekken. <br>Gebruikers kunnen vertragingen zien bij het openen van de agenda en gesprekken in grote groepen in Outlook.|
|Aantal groepen waar een gebruiker lid van kan zijn|7,000|
|Bestandsopslag|1 Terabyte + 10 GB per geabonneerde gebruiker + eventuele andere gekochte opslagruimte. U kunt een onbeperkte hoeveelheid extra opslagruimte kopen.|
|Groepspostvakgrootte|50 GB|

Het standaard maximum aantal Microsoft 365 groepen dat een organisatie kan hebben, is 500.000. Als u de standaardlimiet wilt overschrijden, moet u contact opnemen met Microsoft Support. Zie Groepen - Help voor beheerders voor Microsoft 365 meer Microsoft 365 groepen voor [meer informatie.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

Het beheren van Microsoft 365 groepen is effectiever wanneer u actie-informatie hebt over het gebruik van groepen. Het Microsoft 365-beheercentrum heeft een rapportageprogramma waarmee u het opslaggebruik kunt zien, hoeveel actieve groepen u hebt en hoe gebruikers de groepen gebruiken. Zie: [Microsoft 365 rapporten in het beheercentrum voor](../activity-reports/office-365-groups.md) meer informatie.

## <a name="sensitivity-labels"></a>Gevoeligheidslabels

U kunt gevoeligheidslabels maken die de gebruikers in uw organisatie kunnen instellen wanneer ze een Microsoft 365 maken. Met gevoeligheidslabels kunt u het volgende configureren: 

- Privacy (openbaar of privé)
- Toegang van externe gebruikers
- Onbemande toegang tot apparaten

U kunt bijvoorbeeld een label met de naam *Zeer* vertrouwelijk maken en opgeven dat een groep die met dit label is gemaakt privé is en geen externe gebruikers toestaat. Wanneer gebruikers in uw organisatie dit label selecteren tijdens het maken van groepen, wordt de groep ingesteld op privé en kunnen groepsleden geen externe gebruikers aan de groep toevoegen.

> [!IMPORTANT]
> Als u momenteel classificatielabels gebruikt, zijn deze niet meer beschikbaar voor gebruikers die groepen maken zodra gevoeligheidslabels zijn ingeschakeld. 

Zie Gevoeligheidslabels gebruiken om inhoud in Microsoft Teams, Microsoft 365 groepen en SharePoint te beveiligen voor informatie over het maken, beheren en [gebruiken van gevoeligheidslabels.](../../compliance/sensitivity-labels-teams-groups-sites.md)

## <a name="which-microsoft-365-plans-include-groups"></a>Welke Microsoft 365 bestaan uit groepen?

Elk Microsoft 365 abonnement met Exchange Online en SharePoint Online ondersteunt groepen. Dit omvat de Business Essentials- en Business-Premium en de Enterprise E1-, E3- en E5-abonnementen. De groep neemt de licenties over van de persoon die de groep maakt (ook wel de 'organisator' van de groep genoemd). Zolang de organisator de juiste licentie heeft voor de functies die u voor de groep wilt gebruiken, wordt deze licentie overgebracht naar de groep.

> [!NOTE]
> Zie voor meer informatie Microsoft 365 servicefamilies en -abonnementen [Microsoft 365 planopties.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Als u een Exchange-only abonnement hebt, kunt u nog steeds de gedeelde functies voor postvak IN en gedeelde agenda van groepen in Outlook krijgen, maar u krijgt de documentbibliotheek, Planner of een van de andere mogelijkheden niet.

Microsoft 365 groepen werken met Azure Active Directory. Welke groepsfuncties u krijgt, is afhankelijk van Azure Active Directory abonnement dat u hebt en welke licenties zijn toegewezen aan de organisator van de groep.

> [!IMPORTANT]
> Als u een Azure AD-Premium-abonnement hebt voor alle groepen, kunnen gebruikers deelnemen aan de groep, ongeacht of ze een AAD P1-licentie hebben toegewezen. Licenties worden niet afgedwongen.
> Periodiek genereren we gebruiksrapporten waarin wordt verteld welke gebruikers een licentie missen en hebben we er een nodig die aan hen is toegewezen om te voldoen aan de licentievereisten. Stel dat een gebruiker geen licentie heeft en wordt toegevoegd aan een groep waarin het naamgevingsbeleid wordt afgedwongen. Het rapport geeft aan dat ze een licentie nodig hebben.

## <a name="related-content"></a>Verwante onderwerpen

[Meer informatie over Microsoft 365 Groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (artikel)\
[Distributielijsten upgraden naar Microsoft 365 Groepen](../manage/upgrade-distribution-lists.md) (artikel)\
[Groepen Microsoft 365 beheren met PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artikel)\
[SharePoint OnlineLimieten](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (artikel)\
[Groepen en kanalen organiseren in Microsoft Stream](/stream/groups-channels-organization) (artikel)