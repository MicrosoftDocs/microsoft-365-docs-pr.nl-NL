---
title: Bedreigingsbeveiliging voor Microsoft 365 Business Premium verbeteren
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: U kunt nalevings functies instellen om verlies van gegevens te voorkomen en de gevoelige informatie van uw klanten veilig te houden.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841168"
---
# <a name="set-up-compliance-features"></a>Compliancefuncties instellen

Uw Microsoft 365 Business Premium biedt functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw klanten veilig te houden.

## <a name="set-up-dlp-features"></a>DLP-functies instellen

Zie [een DLP-beleid maken op basis van een sjabloon](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) voor een voorbeeld over het instellen van een beleid ter bescherming tegen het beschermen van persoonlijke gegevens. 
  
DLP biedt een groot aantal kant-en-klare beleidssjablonen voor veel verschillende landinstellingen. Bijvoorbeeld financiële gegevens voor Australië, persoonlijke gegevens van Canada, Amerikaanse financiële gegevens, enzovoort. Bekijk [wat de DLP-beleidssjablonen zijn](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) voor een volledige lijst. Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>E-mail behoud instellen met Exchange Online Archiving

 **Exchange Online Archiving** -licentie functies helpen bij de naleving van compliance en regelgevings normen door e-mail inhoud voor eDiscovery te behouden. Dit levert ook minder Risico's op als er een nakomend en een manier is om gegevens te herstellen na een schending van de beveiliging of wanneer u verwijderde items moet herstellen. U kunt met behulp van de procedure voor het bewaren van inhoud de inhoud van een gebruiker behouden of het bewaarbeleid gebruiken om de inhoud van de inhoud aan te passen.
  
**Bewaring voor rechtszaken:** U kunt alle inhoud van het postvak met de verwijderde items bewaren door het hele postvak van een gebruiker in te stellen. 
    
In het Beheercentrum kunt u een postvak op het geschil bewaren.
    
1. Ga in het linkernavigatievenster naar gebruikers van **gebruikers** met de \> **actieve gebruikers** .
    
2. Selecteer de gebruiker van wie u het postvak wilt plaatsen. Vouw in het deelvenster gebruiker **e-mail instellingen** uit en kies naast **meer instellingen** de optie **Exchange-eigenschappen bewerken** .
    
3. Ga naar de pagina Postvak voor de gebruiker en kies * * Mailbox features * * aan de linkerkant en kies vervolgens de koppeling **inschakelen** onder voor de bewaring van de **geschil** .
    
4. In het dialoogvenster ter ter ter ter plaatse **bekleedt** u de wachtstand van de gewenste aanbieding in het veld duur van de **geschil** . Laat het veld leeg als u het oneindig in de wacht wilt plaatsen. U kunt ook aantekeningen toevoegen en de eigenaar van het postvak direct naar een website gaan als u meer wilt weten over het bewaren van de geschillen. \>**Save** .
    
**Bewaren:** U kunt een aangepast bewaarbeleid inschakelen, bijvoorbeeld om gedurende een bepaalde periode te behouden of om inhoud permanent te verwijderen aan het einde van de bewaarperiode. Voor meer informatie raadpleegt u [overzicht van bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).

## <a name="set-up-sensitivity-labels"></a>Gevoeligheids labels instellen

Vertrouwelijkheids etiketten komen voor Azure Information Protection (beheerders abonnement 1) en helpen u bij het classificeren van uw documenten en e-mailberichten, door labels toe te passen. Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers of met behulp van een combinatie waarbij gebruikers aanbevelingen doen.

Voor het instellen van laag tekstlabels, bekijkt u de video voor het [maken en beheren van gevoeligheids labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .



### <a name="install-the-azure-information-protection-client-manually"></a>De Azure Information Protection-client handmatig installeren

De beheerders client handmatig installeren:

1. Download **AzinfoProtection_UL.exe** van het [Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. U kunt controleren of de installatie heeft gewerkt door een Word-document te bekijken en ervoor te zorgen dat de optie **gevoeligheid** beschikbaar is op het tabblad **Start** .
<br/>![Vervolgkeuzelijst beveiliging in een Word-document.](../media/word-sensitivity.png)

Zie voor meer informatie [de client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
