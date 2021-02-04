---
title: Overzicht van Microsoft 365 Groepen voor beheerders
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
description: Meer informatie over Microsoft 365 Groepen.
ms.openlocfilehash: 5d5c15c13d46738ac9de701b5a39f47274b9f1e5
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094731"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Overzicht van Microsoft 365 Groepen voor beheerders

Microsoft 365 Groepen is de basislidmaatschapsservice die al het teamwerk in Microsoft 365 stimuleert. Met Microsoft 365 Groepen kunt u een groep personen toegang geven tot een verzameling gedeelde bronnen. De volgende bronnen zijn beschikbaar:

- Een gedeeld Postvak IN van Outlook
- Een gedeelde agenda
- Een SharePoint-documentbibliotheek
- Een Planner
- Een OneNote-notitieblok
- Power BI
- Yammer (als de groep is gemaakt vanuit Yammer)
- Een team (als de groep is gemaakt vanuit Teams)
- Routekaart (als u project voor het web hebt)

Met een Microsoft 365-groep hoeft u niet handmatig machtigingen toe te wijzen aan elk van deze bronnen. Als u personen toevoegt aan de groep, krijgt deze automatisch de machtigingen die ze nodig hebben.

Elke gebruiker kan een groep maken, tenzij [u het maken van groepen beperkt tot een bepaalde groep personen.](manage-creation-of-groups.md) Als u het maken van groepen beperkt, kunnen gebruikers die geen groepen kunnen maken geen SharePoint-sites, Planners of teams maken. Voor deze services moeten de personen die ze maken, een groep kunnen maken. Gebruikers kunnen nog steeds deelnemen aan groepsactiviteiten, zoals het maken van taken in Planner of het gebruik van Teams-chat, mits ze lid zijn van de groep.

Groepen hebben de volgende rollen:

- **Eigenaren:** groepseigenaars kunnen leden toevoegen of verwijderen en hebben unieke machtigingen, zoals de mogelijkheid om gesprekken te verwijderen uit het gedeelde Postvak IN of om verschillende instellingen voor de groep te wijzigen. Groepseigenaars kunnen de naam van de groep wijzigen, de beschrijving bijwerken, een foto toevoegen, en meer.
- **Leden:** leden hebben toegang tot alles in de groep, maar kunnen geen groepsinstellingen wijzigen. Standaard kunnen groepsleden gasten uitnodigen om deel te nemen aan uw groep, maar u kunt [deze instelling zelf bepalen.](manage-guest-access-in-groups.md)
- **Gasten:** groeps gasten zijn leden van buiten uw organisatie.

Alleen globale beheerders, gebruikersbeheerders en groepenbeheerders kunnen groepen maken en beheren in het Microsoft 365-beheercentrum. U kunt geen gedelegeerde beheerder zijn (bijvoorbeeld een consultant die plaatsvervangend beheerder is).

Als beheerder kunt u het volgende doen:

- [Opgeven wie groepen kan maken](manage-creation-of-groups.md)
- [Een naamgevingsbeleid maken voor groepen in uw organisatie](groups-naming-policy.md)
- [Kiezen welk domein u wilt gebruiken bij het maken van een groep](choose-domain-to-create-groups.md)
- [Gasttoegang tot groepen beheren](manage-guest-access-in-groups.md)
- [Een verwijderde groep herstellen](restore-deleted-group.md) (binnen 30 dagen na verwijdering)

Als u de voorkeur geeft aan een meer geautomatiseerde manier om de levenscyclus van uw Microsoft 365-groepen te beheren, kunt u verloopbeleid gebruiken om groepen na een bepaalde periode te laten verlopen. De groepseigenaren ontvangen 30, 15 en 1 dag voor de groep een e-mail, zodat ze de groep kunnen verlengen als deze nog nodig is. Meer informatie: [Verloopbeleid voor Microsoft 365-groepen.](office-365-groups-expiration-policy.md)

U kunt uw groepen beheren vanuit het Microsoft 365-beheercentrum of [via PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

Als u veel gebruikers hebt, zoals in een grote onderneming of een grote onderneming, zijn er mogelijk veel gebruikers die groepen voor verschillende doeleinden maken. We raden u ten zeerste aan om [plan voor beheermodel in Microsoft 365-groepen te controleren](plan-for-groups-governance.md) op aanbevolen procedures.

## <a name="group-limits"></a>Groepslimieten

De volgende limieten gelden voor Microsoft 365 Groepen:

|Maximum...|Value|
|:---------|:----|
|Eigenaren per groep|100|
|Groepen die een gebruiker kan maken|250|
|Groepen die een beheerder kan maken|Tot standaardlimiet van tenant van 500 k|
|Aantal leden|Meer dan 1000, hoewel er slechts 1000 tegelijk toegang hebben tot de groepsgesprekken. <br>Gebruikers kunnen vertraging merken bij het openen van de agenda en gesprekken in grote groepen in Outlook.|
|Het aantal groepen waar een gebruiker lid van kan zijn|7,000|
|Bestandsopslag|1 TB + 10 GB per geabonneerde gebruiker + eventuele andere aangeschafte opslagruimte. U kunt een onbeperkte hoeveelheid extra opslagruimte kopen.|
|Grootte van groepspostvak|50 GB|

Standaard mag een organisatie maximaal 500.000 Microsoft 365-groepen hebben. Als u de standaardlimiet wilt overschrijden, moet u contact opnemen met Microsoft Ondersteuning. Zie Microsoft 365 Groepen - Help voor beheerders voor meer informatie over limieten [voor Microsoft 365 Groepen.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

Het beheren van Uw Microsoft 365-groepen werkt effectiever als u informatie hebt waarop een actie kan worden ondernomen over het gebruik van groepen. Het Microsoft 365-beheercentrum heeft een rapportageprogramma waarmee u het gebruik van opslagruimte kunt bekijken, hoeveel actieve groepen u hebt en hoe gebruikers de groepen gebruiken. Zie: [Microsoft 365-rapporten in het beheercentrum](../activity-reports/office-365-groups.md) voor meer informatie.

## <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

U kunt gevoeligheidslabels maken die de gebruikers in uw organisatie kunnen instellen wanneer ze een Microsoft 365-groep maken. Met gevoeligheidslabels kunt u het volgende configureren: 

- Privacy (openbaar of privé)
- Externe gebruikers hebben toegang
- Niet-bemande apparaattoegang

U kunt bijvoorbeeld een label met de naam *Zeer* vertrouwelijk maken en opgeven dat elke groep die met dit label is gemaakt, privé is en geen externe gebruikers toestaat. Wanneer gebruikers in uw organisatie dit label selecteren tijdens het maken van een groep, wordt de groep ingesteld op Privé en kunnen groepsleden geen externe gebruikers aan de groep toevoegen.

> [!IMPORTANT]
> Als u momenteel classificatielabels gebruikt, zijn ze niet meer beschikbaar voor gebruikers die groepen maken zodra gevoeligheidslabels zijn ingeschakeld. 

Zie Gevoeligheidslabels gebruiken om inhoud te beschermen [in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)voor informatie over het maken, beheren en gebruiken van gevoeligheidslabels.

## <a name="which-microsoft-365-plans-include-groups"></a>Welke Microsoft 365-abonnementen omvatten groepen?

Elk Microsoft 365-abonnement met Exchange Online en SharePoint Online ondersteunt groepen. Dit omvat de abonnementen Business Essentials, Business Premium, Enterprise E1, E3 en E5. De groep krijgt de licentie van de persoon die de groep maakt (ook wel 'organisator' van de groep genoemd). Zolang de organisator de juiste licentie heeft voor de functies die u wilt dat de groep heeft, wordt die licentie overgebracht naar de groep.

> [!NOTE]
> Zie de microsoft 365-abonnementsopties voor meer informatie over [Microsoft 365-servicefamilies en -abonnementen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Als u alleen een abonnement hebt voor Exchange, kunt u nog steeds de functies voor een gedeeld Postvak IN en een gedeelde agenda in Outlook gebruiken, maar hebt u geen gebruik van de documentbibliotheek, Planner of een van de andere functies.

Microsoft 365-groepen werken met Azure Active Directory. Welke groepsfuncties u krijgt, is afhankelijk van welk Azure Active Directory-abonnement u hebt en welke licenties zijn toegewezen aan de organisator van de groep.

> [!IMPORTANT]
> Voor alle groepsfuncties kunnen gebruikers, als u een Azure AD Premium-abonnement hebt, deelnemen aan de groep, ongeacht of er een AAD P1-licentie aan hen is toegewezen. Licentieverlening is niet afgedwongen.
> Regelmatig worden gebruiksrapporten gegenereerd met de melding welke gebruikers een licentie missen en die aan hen moeten worden toegewezen om te voldoen aan de licentievereisten. Stel dat een gebruiker geen licentie heeft en wordt toegevoegd aan een groep waar het naamgevingsbeleid wordt afgedwongen. In het rapport wordt aan u gevlagd dat ze een licentie nodig hebben.

## <a name="related-articles"></a>Verwante artikelen

[Meer informatie over Microsoft 365 Groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Distributielijsten upgraden naar Microsoft 365-groepen](../manage/upgrade-distribution-lists.md)

[Microsoft 365 Groepen beheren met PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[Limieten voor SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
