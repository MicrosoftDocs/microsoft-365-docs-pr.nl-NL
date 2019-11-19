---
title: Bedreigingsbeveiliging voor Microsoft 365 Business verhogen
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
search.appverid:
- BCS160
- MET150
description: Stel nalevingsfuncties in om gegevensverlies te voorkomen en gevoelige gegevens te labelen.
ms.openlocfilehash: 6fae95e8c5e6d133e3163dbdfd3c09cfede11382
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715117"
---
# <a name="set-up-compliance-features"></a>Nalevingsfuncties instellen

Uw Microsoft 365 Business wordt geleverd met functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw klanten veilig te houden.

## <a name="set-up-dlp-features"></a>DLP-functies instellen

Zie [een DLP-beleid maken op basis van een sjabloon](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) voor een voorbeeld over het instellen van een beleid ter bescherming tegen persoonlijk identificeerbare informatie (PII). 
  
DLP wordt geleverd met veel gebruiksklare beleidssjablonen voor veel verschillende landinstellingen. Bijvoorbeeld, Australië financiële gegevens, Canada Personal Information Act, Amerikaanse financiële gegevens, enzovoort. Zie [wat de DLP-beleidssjablonen](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) voor een volledige lijst bevatten. Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>E-mail retentie instellen met Exchange Online-archivering

 De licentie functies voor het **archiveren van Exchange Online** helpen de nalevings-en regelgevingsnormen te handhaven door e-mail inhoud voor eDiscovery te behouden Het helpt ook uw risico te verminderen als er een rechtszaak, en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging of wanneer u nodig hebt om verwijderde items te herstellen. U rechtszaak blokkering gebruiken om alle inhoud van een gebruiker te behouden, of gebruik bewaarbeleid om aan te passen wat u wilt behouden.
  
**Rechtszaak Hold:** U alle inhoud van de postbus inclusief verwijderde items behouden door het hele postvak van een gebruiker in de rechtszaak te bewaren. 
    
Om een postbus te plaatsen in de rechtszaak Hold, in het Admin Center:
    
1. Ga in de linkernavigatiebalk naar **gebruikers** \> **actieve gebruikers**.
    
2. Selecteer een gebruiker wiens postvak u wilt plaatsen in de rechtszaak blokkering. In de gebruikers deelvenster uitvouwen **e-mail instellingen**, en naast **meer instellingen**, kiest u **Exchange-eigenschappen bewerken**.
    
3. Op de postbus pagina voor de gebruiker, kiest u * * mailbox functies * * op de linker NAV, en kies vervolgens de koppeling **inschakelen** onder **rechtszaak vasthouden**.
    
4. In het dialoogvenster **rechtszaak** blokkering, u de duur van de bewaarperiode in het veld **rechtszaak Hold duur** . Laat het veld leeg als u een oneindige Hold wilt plaatsen. U ook notities toevoegen en de eigenaar van de postbus naar een website laten gaan die u wellicht meer moet uitleggen over de rechtszaak. \>**Opslaan**.
    
**Retentie:** U aangepaste bewaarbeleid inschakelen, bijvoorbeeld om te behouden voor een bepaalde hoeveelheid tijd of verwijderen van inhoud permanent aan het einde van de bewaarperiode. Zie [overzicht van bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)voor meer informatie.

## <a name="set-up-sensitivity-labels"></a>Gevoeligheids etiketten instellen

Gevoeligheidslabels worden geleverd met Azure Information Protection (AIP) plan 1 en helpen u bij het classificeren en eventueel beveiligen van uw documenten en e-mail berichten door labels toe te passen. Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden, handmatig door gebruikers definiëren of met behulp van een combinatie waar gebruikers aanbevelingen worden gegeven.

Als u gevoeligheids labels wilt instellen, u video met [gevoeligheids etiketten maken en beheren](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .



### <a name="install-the-azure-information-protection-client-manually"></a>De Azure Information Protection-client handmatig installeren

De AIP-client handmatig installeren:

1. Download **AzinfoProtection_UL. exe** van [het Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. U controleren of de installatie heeft gewerkt door een Word-document te bekijken en ervoor te zorgen dat de optie **gevoeligheid** beschikbaar is op het tabblad **Start** .
<br/>![Drop-down bescherming tabblad in een Word-document.](media/word-sensitivity.png)

Zie [de client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)voor meer informatie.
