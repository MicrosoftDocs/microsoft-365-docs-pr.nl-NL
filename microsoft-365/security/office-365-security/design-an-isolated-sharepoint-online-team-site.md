---
title: Een geïsoleerde SharePoint Online-teamsite ontwerpen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: U kunt geïsoleerde, geïsoleerde SharePoint Online-team sites ontwerpen, waaronder machtigingsniveaus bepalen, machtigingen toewijzen aan gebruikers met toegangsgroepen en geneste Azure AD-groepen.
ms.openlocfilehash: 035952c1921443d86602eb94e3965acee86ae3e8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203117"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite ontwerpen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **Overzicht:** Stap voor stap door het ontwerpproces voor geïsoleerde SharePoint Online-team sites.

In dit artikel wordt u stapsgewijs begeleid bij het maken van een geïsoleerde ontwerp site van SharePoint Online.

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: uw SharePoint-groepen en machtigingsniveaus bepalen

Elke SharePoint Online-team site wordt standaard gemaakt met de volgende SharePoint-groepen:

- \<site name> Leden

- \<site name> Plaatst

- \<site name> Sites

Deze groepen zijn gescheiden van de groepen Microsoft 365 en Azure Active Directory (AD) en vormen de basis voor het toewijzen van machtigingen voor de bronnen van de site.

De set specifieke machtigingen waarmee wordt bepaald wat een lid van een SharePoint-groep in een site kan doen, is een machtigingsniveau. Een SharePoint Online-team site bevat standaard drie machtigingsniveaus: bewerken, lezen en volledig beheer. In de volgende tabel wordt de standaard correlatie van SharePoint-groepen en de toegewezen machtigingsniveaus weergegeven:

****

|SharePoint-groep|Machtigingsniveau|
|---|---|
|\<site name> Leden|Bewerken|
|\<site name> Plaatst|Lezen|
|\<site name> Sites|Volledig beheer|
|

 **Aanbevolen procedure:** U kunt extra SharePoint-groepen en machtigingsniveaus maken. We raden u echter aan gebruik te maken van de standaardshare Point-groepen en machtigingsniveaus voor de geïsoleerde SharePoint Online-site.

Hier volgen de standaardshare Point-groepen en machtigingsniveaus.

![De standaardshare Point-groepen en machtigingsniveaus voor een SharePoint Online-site.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: machtigingen toewijzen aan gebruikers met toegangsgroepen

U kunt machtigingen toewijzen aan gebruikers door hun gebruikersaccount toe te voegen of een Microsoft 365-of Azure AD-groep waarvan het gebruikersaccount lid is van de SharePoint-groepen. Wanneer u eenmaal hebt toegevoegd, worden de gebruikersaccounts direct of indirect via lidmaatschap van een groep van Microsoft 365 of Azure AD toegewezen aan het machtigingsniveau dat is gekoppeld aan de SharePoint-groep.

Het gebruik van de standaardshare Point-groepen als voorbeeld:

- Leden van de SharePoint-groep ** \<site name> leden** , die beide gebruikersaccounts en groepen kunnen bevatten, krijgen het machtigingsniveau **bewerken**

- Leden van de SharePoint-groep ** \<site name> bezoekers** , die zowel gebruikersaccounts als groepen kunnen bevatten, hebben het machtigingsniveau **lezen** toegewezen

- Leden van de SharePoint-groep ** \<site name> eigenaren** , waaronder gebruikersaccounts en groepen, kunnen het machtigingsniveau **volledig beheer** hebben.

 **Aanbevolen procedure:** Hoewel u machtigingen kunt beheren via afzonderlijke gebruikersaccounts, kunt u het beste één Azure AD-groep gebruiken, ook wel een Access-groep genoemd. Dit vergemakkelijkt het beheer van machtigingen door lidmaatschap van de Access-groep, in plaats van de lijst met gebruikersaccounts voor elke SharePoint-groep te beheren.

Azure AD-groepen voor Microsoft 365 zijn verschillend tha Microsoft 365 groepen. Azure AD-groepen worden weergegeven in het Microsoft 365-Beheercentrum, waarbij hun **type** is ingesteld op **beveiliging** en geen e-mailadres heeft. Azure AD-groepen kunnen worden beheerd binnen:

- Active Directory Domain Services (AD DS)

    Dit zijn groepen die zijn gemaakt in uw on-premises AD DS-infrastructuur en die zijn gesynchroniseerd met uw Microsoft 365-abonnement. In het Microsoft 365-Beheercentrum hebben deze groepen **Status** de status **gesynchroniseerd met Active Directory**.

- Office 365

    Dit zijn groepen die zijn gemaakt met het Microsoft 365-Beheercentrum, de Azure-portal of Microsoft PowerShell. In het Microsoft 365-Beheercentrum hebben deze groepen **Status** de status **Cloud**.

 **Aanbevolen procedure:** Als u AD DS on-premises gebruikt en synchroniseert met uw Microsoft 365-abonnement, voert u uw gebruikers-en groepsbeheer met AD DS uit.

Voor geïsoleerde SharePoint Online-team sites ziet de aanbevolen groepsstructuur er als volgt uit:

****

|SharePoint-groep|Azure AD-basis toegangsgroep|Machtigingsniveau|
|---|---|---|
|\<site name> Leden|\<site name> Leden|Bewerken|
|\<site name> Plaatst|\<site name> Mensen|Lezen|
|\<site name> Sites|\<site name> Beheerders|Volledig beheer|
|

 **Aanbevolen procedure:** Hoewel u Microsoft 365 of een Azure AD-groep als lid van SharePoint-groepen kunt gebruiken, kunt u het beste gebruikmaken van Azure AD-groepen. Azure AD-groepen die worden beheerd via de AD DS of Microsoft 365, bieden u meer flexibiliteit bij het toewijzen van geneste groepen aan machtigingen.

Hier volgen de standaardshare Point-groepen die zijn geconfigureerd voor het gebruik van Azure AD-gebaseerde toegangsgroepen.

![Toegangsgroepen gebruiken als leden van standaardsitegroepen van SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

Houd bij het ontwerpen van de drie toegangsgroepen rekening met het volgende:

- U moet slechts enkele leden in de groep ** \<site name> beheerders** toegang hebben, dat overeenkomt met een klein aantal beheerders van SharePoint Online dat de team site beheert.

- De meeste van de siteleden bevinden zich in de groepen ** \<site name> leden** en ** \<site name> kijkers** . Aangezien siteleden in de groep ** \<site name> leden** toegang de mogelijkheid hebben om bronnen op de site te verwijderen of te wijzigen, is het belangrijk om rekening te houden met het lidmaatschap. Wanneer u twijfelt, voegt u de site lid toe aan de groep ** \<site name> gebruikers** toegang.

Hier ziet u een voorbeeld van de SharePoint-groepen en toegangsgroepen voor een afzonderlijke site met de naam Projectx.

![Een voorbeeld van het gebruik van toegangsgroepen voor een SharePoint Online-site met de naam Projectx.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: geneste Azure AD-groepen gebruiken

Voor een project dat is afgestemd op een klein aantal personen, passen de meeste scenario's in één niveau van Azure AD-based Access-groepen die aan de SharePoint-groepen van de site zijn toegevoegd. Als u echter een groot aantal personen hebt en deze personen al deel uitmaken van de gevestigde Azure AD-groepen, kunt u eenvoudiger SharePoint-machtigingen toewijzen met geneste groepen of groepen die andere groepen als leden hebben.

U wilt bijvoorbeeld een geïsoleerde SharePoint Online-team site maken voor samenwerking tussen de leidinggevenden van de afdelingen voor verkoop, marketing, engineering, juridisch en ondersteunings afdelingen en van deze afdelingen al hun eigen groepen met lidmaatschap van het account van de beheerder. In plaats van een nieuwe groep te maken voor de nieuwe siteleden en alle afzonderlijke gebruikersaccounts voor de beheerder in de groep te plaatsen, moet u de bestaande Executive groepen voor elke afdeling in de nieuwe groep.

 Als u een Microsoft 365-abonnement deelt tussen meerdere organisaties, kan het lastig zijn om een bepaald niveau van groepslidmaatschappen voor een geïsoleerde site van een organisatie te beheren vanwege het doorschijnende-aantal gebruikersaccounts. In dit geval kunt u geneste Azure AD-groepen gebruiken voor elke organisatie die de groepen binnen hun organisatie bevat om de machtigingen te beheren.

Geneste Azure AD-groepen gebruiken:

1. Identificeer of maak de Azure AD-groepen die gebruikersaccounts moeten bevatten en voeg de juiste gebruikersaccounts toe als leden.

2. Maak de in de container Azure AD gebaseerde toegangsgroep die de andere Azure AD-groepen moet bevatten en voeg deze groepen toe als leden.

3. Identificeer de SharePoint-groep en het bijbehorende machtigingsniveau voor het juiste toegangsniveau voor de groep container toegang.

> [!NOTE]
> U kunt geneste Microsoft 365-groepen niet gebruiken.

Hier ziet u een voorbeeld van geneste Azure AD-groepen voor de groep leden toegang van Projectx.

![Een voorbeeld van het gebruik van geneste toegangsgroepen voor de groep leden toegang voor de Projectx-site.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

Aangezien alle gebruikersaccounts in de teams voor onderzoek, engineering en project bedoeld zijn om siteleden te zijn, is het eenvoudiger om Azure AD-groepen toe te voegen aan de groep toegang tot leden van Projectx.

## <a name="next-step"></a>Volgende stap

Wanneer u klaar bent om een geïsoleerde site te maken en te configureren, raadpleegt u [een geïsoleerde SharePoint Online-team site implementeren](deploy-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Een geïsoleerde SharePoint Online-teamsite beheren](manage-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)
