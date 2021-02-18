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
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Afzonderlijke SharePoint Online-teamsites ontwerpen, waaronder machtigingsniveaus bepalen, machtigingen toewijzen aan gebruikers met toegangsgroepen en geneste Azure AD-groepen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288333"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite ontwerpen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


 **Overzicht:** Stap door het ontwerpproces voor afzonderlijke SharePoint Online-teamsites.

In dit artikel worden de belangrijkste ontwerpbeslissingen genomen die u moet nemen voordat u een afzonderlijke SharePoint Online-teamsite maakt.

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: Uw SharePoint-groepen en machtigingsniveaus bepalen

Elke SharePoint Online-teamsite wordt standaard gemaakt met de volgende SharePoint-groepen:

- \<site name> Leden

- \<site name> Bezoekers

- \<site name> Eigenaren

Deze groepen staan los van Microsoft 365- en Azure Active Directory-groepen (AD) en vormen de basis voor het toewijzen van machtigingen voor de bronnen van de site.

De set specifieke machtigingen die bepaalt wat een lid van een SharePoint-groep op een site kan doen, is een machtigingsniveau. Er zijn standaard drie machtigingsniveaus voor een SharePoint Online-teamsite: Bewerken, Lezen en Volledig beheer. In de volgende tabel ziet u de standaard correlatie van SharePoint-groepen en toegewezen machtigingsniveaus:

****

|SharePoint-groep|Machtigingsniveau|
|---|---|
|\<site name> Leden|Bewerken|
|\<site name> Bezoekers|Lezen|
|\<site name> Eigenaren|Volledig beheer|
|

 **Best practice:** U kunt extra SharePoint-groepen en machtigingsniveaus maken. U wordt echter aangeraden de standaardgroepen en machtigingsniveaus van SharePoint te gebruiken voor uw afzonderlijke SharePoint Online-site.

Dit zijn de sharePoint-standaardgroepen en -machtigingsniveaus.

![De sharePoint-standaardgroepen en -machtigingsniveaus voor een SharePoint Online-site.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: Machtigingen toewijzen aan gebruikers met toegangsgroepen

U kunt machtigingen toewijzen aan gebruikers door hun gebruikersaccount of een Microsoft 365- of Azure AD-groep waarvan het gebruikersaccount lid is, toe te voegen aan de SharePoint-groepen. Nadat ze zijn toegevoegd, wordt aan de gebruikersaccounts, direct of indirect via lidmaatschap in een Microsoft 365- of Azure AD-groep, het machtigingsniveau toegewezen dat is gekoppeld aan de SharePoint-groep.

De standaard SharePoint-groepen als voorbeeld gebruiken:

- Leden van **\<site name> de** SharePoint-groep Leden, die zowel gebruikersaccounts als groepen kan bevatten, krijgen het **machtigingsniveau** Bewerken toegewezen

- Leden van **\<site name> de** SharePoint-groep Bezoekers, die zowel gebruikersaccounts als groepen kan bevatten, krijgen het **machtigingsniveau** Lezen

- Leden van **\<site name> de** SharePoint-groep Eigenaren, die zowel gebruikersaccounts  als groepen kan bevatten, krijgen het machtigingsniveau Volledig beheer

 **Best practice:** Hoewel u machtigingen kunt beheren via afzonderlijke gebruikersaccounts, raden we u aan slechts één Azure AD-groep, ook wel een toegangsgroep genoemd, te gebruiken. Dit vereenvoudigt het beheer van machtigingen via lidmaatschap van de toegangsgroep in plaats van de lijst met gebruikersaccounts voor elke SharePoint-groep te beheren.

Azure AD-groepen voor Microsoft 365 verschillen van de Microsoft 365-groepen. Azure AD-groepen worden weergegeven in het Microsoft 365-beheercentrum met hun **Type** ingesteld op **Beveiliging** en hebben geen e-mailadres. Azure AD-groepen kunnen worden beheerd binnen:

- Active Directory Domain Services (AD DS)

    Dit zijn groepen die zijn gemaakt in uw on-premises AD DS-infrastructuur en zijn gesynchroniseerd met uw Microsoft 365-abonnement. In het Microsoft 365-beheercentrum hebben deze groepen de **status** **Gesynchroniseerd met active directory.**

- Office 365

    Dit zijn groepen die zijn gemaakt met behulp van het Microsoft 365-beheercentrum, de Azure Portal of Microsoft PowerShell. In het Microsoft 365-beheercentrum hebben deze groepen de **status** **Cloud.**

 **Best practice:** Als u AD DS on-premises gebruikt en synchroniseert met uw Microsoft 365-abonnement, voert u het beheer van gebruikers en groepen uit met AD DS.

Voor afzonderlijke SharePoint Online-teamsites ziet de aanbevolen groepsstructuur er als volgende uit:

****

|SharePoint-groep|Toegangsgroep op basis van Azure AD|Machtigingsniveau|
|---|---|---|
|\<site name> Leden|\<site name> Leden|Bewerken|
|\<site name> Bezoekers|\<site name> Kijkers|Lezen|
|\<site name> Eigenaren|\<site name> Beheerders|Volledig beheer|
|

 **Best practice:** Hoewel u Microsoft 365- of Azure AD-groepen kunt gebruiken als leden van SharePoint-groepen, raden we u aan Azure AD-groepen te gebruiken. Azure AD-groepen, beheerd via AD DS of Microsoft 365, bieden u meer flexibiliteit bij het gebruik van geneste groepen om machtigingen toe te wijzen.

Hier zijn de standaard SharePoint-groepen die zijn geconfigureerd voor toegangsgroepen op basis van Azure AD.

![Toegangsgroepen gebruiken als leden van standaard SharePoint Online-sitegroepen.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

Houd bij het ontwerpen van de drie toegangsgroepen rekening met het volgende:

- De **\<site name> toegangsgroep** Beheerders moet slechts een paar leden hebben, die betrekking hebben op een klein aantal SharePoint Online-beheerders die de teamsite beheren.

- De meeste leden van uw site maken deel uit van de **\<site name> groepen Leden** **\<site name> of Viewers.** Omdat siteleden in de **\<site name> groep Leden** toegang hebben tot de mogelijkheid resources op de site te verwijderen of te wijzigen, moet u zorgvuldig rekening houden met het lidmaatschap van de groep. Als u twijfelt, voegt u het sitelid toe aan de **\<site name> toegangsgroep Viewers.**

Hier volgen een voorbeeld van de SharePoint-groepen en toegangsgroepen voor een afzonderlijke site met de naam ProjectX.

![Een voorbeeld van het gebruik van toegangsgroepen voor een SharePoint Online-site met de naam ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: Geneste Azure AD-groepen gebruiken

Voor een project dat wordt beperkt tot een klein aantal personen, past één niveau van op Azure AD gebaseerde toegangsgroepen die zijn toegevoegd aan de SharePoint-groepen van de site, in de meeste scenario's. Als u echter een groot aantal personen hebt en die personen al lid zijn van bestaande Azure AD-groepen, kunt u gemakkelijker SharePoint-machtigingen toewijzen met behulp van geneste groepen of groepen die andere groepen als leden bevatten.

U wilt bijvoorbeeld een afzonderlijke SharePoint Online-teamsite maken om samen te werken tussen de leidinggevenden van de afdelingen Verkoop, Marketing, Engineering, Legal en Support, en die afdelingen hebben al hun eigen groepen met het lidmaatschap van een executive gebruikersaccount. In plaats van een nieuwe groep te maken voor de nieuwe siteleden en alle afzonderlijke gebruikersaccounts voor leidinggevenden in de groep te plaatsen, zet u de bestaande managementgroepen voor elke afdeling in de nieuwe groep.

 Als u een Microsoft 365-abonnement deelt tussen meerdere organisaties, kan één groepslidmaatschap voor een afzonderlijke site voor een organisatie moeilijk te beheren worden vanwege het grote aantal gebruikersaccounts. In dit geval kunt u geneste Azure AD-groepen gebruiken voor elke organisatie die de groepen binnen de organisatie bevat om de machtigingen te beheren.

Geneste Azure AD-groepen gebruiken:

1. Identificeer of maak de Azure AD-groepen die gebruikersaccounts bevatten en voeg de juiste gebruikersaccounts toe als leden.

2. Maak de op Azure AD gebaseerde toegangsgroep van de container die de andere Azure AD-groepen bevat en voeg deze groepen toe als leden.

3. Identificeer de SharePoint-groep en het bijbehorende machtigingsniveau voor het juiste toegangsniveau voor de containertoegangsgroep.

> [!NOTE]
> U kunt geen geneste Microsoft 365-groepen gebruiken.

Hier is een voorbeeld van geneste Azure AD-groepen voor de toegangsgroep voor ProjectX-leden.

![Een voorbeeld van het gebruik van geneste toegangsgroepen voor de ledentoegangsgroep voor de ProjectX-site.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

Omdat alle gebruikersaccounts in de teams Research, Engineering en Project zijn bedoeld als siteleden, is het eenvoudiger om hun Azure AD-groepen toe te voegen aan de toegangsgroep ProjectX-leden.

## <a name="next-step"></a>Volgende stap

Zie Een afzonderlijke [SharePoint Online-teamsite](deploy-an-isolated-sharepoint-online-team-site.md)implementeren wanneer u klaar bent om een geïsoleerd site in productie te maken en te configureren.

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Een geïsoleerde SharePoint Online-teamsite beheren](manage-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)
