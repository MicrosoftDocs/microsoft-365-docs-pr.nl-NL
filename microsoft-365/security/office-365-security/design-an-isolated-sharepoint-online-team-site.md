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
description: Ontwerp geïsoleerde SharePoint Online-teamsites, waaronder het bepalen van machtigingsniveaus, het toewijzen van machtigingen aan gebruikers met toegangsgroepen en geneste Azure AD-groepen.
ms.openlocfilehash: 4663a0b9710fc05d0b063a3100d3b5ac223a2161
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034838"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite ontwerpen

 **Samenvatting:** Stap door het ontwerpproces voor geïsoleerde SharePoint Online-teamsites.
  
In dit artikel neemt u de belangrijkste ontwerpbeslissingen mee die u moet nemen voordat u een geïsoleerde SharePoint Online-teamsite maakt.
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: Uw SharePoint-groepen en machtigingsniveaus bepalen

Elke SharePoint Online-teamsite wordt standaard gemaakt met de volgende SharePoint-groepen:
  
- \<sitenaam> leden
    
- \<sitenaam> Bezoekers
    
- \<sitenaam> Eigenaren
    
Deze groepen staan los van microsoft 365- en Azure Active Directory -groepen (AD) en vormen de basis voor het toewijzen van machtigingen voor de bronnen van de site.
  
De set specifieke machtigingen die bepaalt wat een lid van een SharePoint-groep kan doen in een site is een machtigingsniveau. Er zijn standaard drie machtigingsniveaus voor een SharePoint Online-teamsite: Bewerken, Lezen en Volledig beheer. In de volgende tabel ziet u de standaardcorrelatie van SharePoint-groepen en toegewezen machtigingsniveaus:
  
|**SharePoint-groep**|**Machtigingsniveau**|
|:-----|:-----|
|\<sitenaam> leden  <br/> |Bewerken  <br/> |
|\<sitenaam> Bezoekers  <br/> |Lezen  <br/> |
|\<sitenaam> Eigenaren  <br/> |Volledige controle  <br/> |
   
 **Beste praktijken:** U extra SharePoint-groepen en machtigingsniveaus maken. We raden u echter aan de standaardSharePoint-groepen en machtigingsniveaus te gebruiken voor uw geïsoleerde SharePoint Online-site.
  
Hier volgen de standaard SharePoint-groepen en machtigingsniveaus.
  
![De standaardSharePoint-groepen en machtigingsniveaus voor een SharePoint Online-site.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: Machtigingen toewijzen aan gebruikers met toegangsgroepen

U machtigingen toewijzen aan gebruikers door hun gebruikersaccount of een Microsoft 365- of Azure AD-groep waarvan het gebruikersaccount lid is, toe te voegen aan de SharePoint-groepen. Eenmaal toegevoegd, krijgen de gebruikersaccounts, direct of indirect via lidmaatschap in een Microsoft 365- of Azure AD-groep, het machtigingsniveau toegewezen dat is gekoppeld aan de SharePoint-groep.
  
Als voorbeeld de standaardSharePoint-groepen gebruiken:
  
- Leden van de ** \<sitenaam> SharePoint-groep van leden,** die zowel gebruikersaccounts als groepen kunnen bevatten, krijgen het **machtigingsniveau bewerken** toegewezen
    
- Leden van de ** \<sitenaam> SharePoint-groep bezoekers,** die zowel gebruikersaccounts als groepen kan bevatten, krijgen het **machtigingsniveau lezen** toegewezen
    
- Leden van de ** \<sitenaam> SharePoint-groep Eigenaren,** die zowel gebruikersaccounts als groepen kunnen bevatten, krijgen het **machtigingsniveau Volledig beheer** toegewezen
    
 **Beste praktijken:** Hoewel u machtigingen beheren via afzonderlijke gebruikersaccounts, raden we u aan in plaats daarvan één Azure AD-groep te gebruiken, die een toegangsgroep wordt genoemd. Dit vereenvoudigt het beheer van machtigingen via het lidmaatschap van de toegangsgroep, in plaats van het beheren van de lijst met gebruikersaccounts voor elke SharePoint-groep.
  
Azure AD-groepen voor Microsoft 365 zijn anders dan Microsoft 365-groepen. Azure AD-groepen worden weergegeven in het Microsoft 365-beheercentrum met hun **type** ingesteld op **Beveiliging** en hebben geen e-mailadres. Azure AD-groepen kunnen worden beheerd binnen:
  
- Active Directory Domain Services (AD DS)
    
    Dit zijn groepen die zijn gemaakt in uw on-premises AD DS-infrastructuur en zijn gesynchroniseerd met uw Microsoft 365-abonnement. In het Microsoft 365-beheercentrum hebben deze groepen een **status** van **gesynchroniseerd met active directory.**
    
- Office 365
    
    Dit zijn groepen die zijn gemaakt met behulp van het Microsoft 365-beheercentrum, de Azure-portal of Microsoft PowerShell. In het Microsoft 365-beheercentrum hebben deze groepen een **status** van **cloud**.
    
 **Beste praktijken:** Als u ad DS on-premises gebruikt en synchroniseert met uw Microsoft 365-abonnement, voert u uw gebruikers- en groepsbeheer uit met AD DS.
  
Voor geïsoleerde SharePoint Online-teamsites ziet de aanbevolen groepsstructuur er als volgt uit:
  
|**SharePoint-groep**|**Azure AD-gebaseerde toegangsgroep**|**Machtigingsniveau**|
|:-----|:-----|:-----|
|\<sitenaam> leden  <br/> |\<sitenaam> leden  <br/> |Bewerken  <br/> |
|\<sitenaam> Bezoekers  <br/> |\<sitenaam> Kijkers  <br/> |Lezen  <br/> |
|\<sitenaam> Eigenaren  <br/> |\<sitenaam> Beheerders  <br/> |Volledige controle  <br/> |
   
 **Beste praktijken:** Hoewel u Microsoft 365- of Azure AD-groepen gebruiken als leden van SharePoint-groepen, raden we u aan Azure AD-groepen te gebruiken. Azure AD-groepen, beheerd via AD DS of Microsoft 365, bieden u meer flexibiliteit om geneste groepen te gebruiken om machtigingen toe te wijzen.
  
Hier volgen de standaard SharePoint-groepen die zijn geconfigureerd om op Azure AD gebaseerde toegangsgroepen te gebruiken.
  
![Toegangsgroepen gebruiken als leden van standaard SharePoint Online-sitegroepen.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
Houd bij het ontwerpen van de drie toegangsgroepen rekening met het volgende:
  
- Er mogen slechts een paar leden in de ** \<sitenaam>** beheerders-toegangsgroep zijn, wat overeenkomt met een klein aantal SharePoint Online-beheerders die de teamsite beheren.
    
- De meeste van uw siteleden staan in de ** \<sitenaam> leden** of ** \<sitenaam> kijkers** toegang tot groepen. Omdat siteleden in de ** \<sitenaam> ledende** toegangsgroep de mogelijkheid hebben om bronnen op de site te verwijderen of te wijzigen, moet u het lidmaatschap zorgvuldig overwegen. Voeg bij twijfel het sitelid toe aan de ** \<sitenaam>** kijkerstoegangsgroep.
    
Hier vindt u een voorbeeld van de SharePoint-groepen en toegangsgroepen voor een geïsoleerde site met de naam ProjectX.
  
![Een voorbeeld van het gebruik van toegangsgroepen voor een SharePoint Online-site met de naam ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: Geneste Azure AD-groepen gebruiken

Voor een project dat beperkt is tot een klein aantal personen, past één niveau van op Azure AD gebaseerde toegangsgroepen die zijn toegevoegd aan de SharePoint-groepen van de site, de meeste scenario's. Als u echter een groot aantal mensen hebt en deze mensen al lid zijn van gevestigde Azure AD-groepen, u gemakkelijker SharePoint-machtigingen toewijzen door geneste groepen of groepen te gebruiken die andere groepen als leden bevatten.
  
U wilt bijvoorbeeld een geïsoleerde SharePoint online teamsite maken voor samenwerking tussen de leidinggevenden van de afdelingen verkoop, marketing, engineering, juridische en ondersteuningsen en die afdelingen die al hun eigen groepen hebben met een lidmaatschap van een uitvoerend gebruikersaccount. In plaats van het creëren van een nieuwe groep voor de nieuwe site leden en het plaatsen van alle individuele executive user accounts in, zet de bestaande uitvoerende groepen voor elke afdeling in de nieuwe groep.
  
 Als u een Microsoft 365-abonnement deelt tussen meerdere organisaties, kan een enkel groepslidmaatschap voor een geïsoleerde site voor een organisatie moeilijk te beheren zijn vanwege het grote aantal gebruikersaccounts. In dit geval u geneste Azure AD-groepen gebruiken voor elke organisatie die de groepen binnen hun organisatie bevatten om de machtigingen te beheren.
  
Ga als een gebruiksaanwijzing voor geneste Azure AD-groepen:
  
1. Identificeer of maak de Azure AD-groepen die gebruikersaccounts bevatten en voeg de juiste gebruikersaccounts toe als leden.
    
2. Maak de op container Azure AD gebaseerde toegangsgroep die de andere Azure AD-groepen bevat en voeg deze groepen toe als leden.
    
3.  Voor het juiste toegangsniveau voor de groep containertoegang u de SharePoint-groep en het bijbehorende machtigingsniveau identificeren.
    
> [!NOTE]
> U geneste Microsoft 365-groepen niet gebruiken. 
  
Hier vindt u een voorbeeld van geneste Azure AD-groepen voor de projectx-toegangsgroep voor leden.
  
![Een voorbeeld van het gebruik van geneste toegangsgroepen voor de ledentoegangsgroep voor de ProjectX-site.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
Omdat alle gebruikersaccounts in de leadsteams Voor Onderzoek, Engineering en Project bedoeld zijn om siteleden te zijn, is het eenvoudiger om hun Azure AD-groepen toe te voegen aan de toegangsgroep voor ProjectX-leden.
  
## <a name="next-step"></a>Volgende stap

Zie [Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)wanneer u een geïsoleerde site in productie wilt maken en configureren.
  
## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)
  
[Een geïsoleerde SharePoint Online-teamsite beheren](manage-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)



