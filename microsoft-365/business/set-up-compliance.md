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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Stel de geavanceerde Bedreigingsbeveiliging van Office 365 in en beveilig gevoelige gegevens.
ms.openlocfilehash: 8144bcebe8a0cdf28a5e092f592362922ccbdd48
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288740"
---
# <a name="set-up-compliance-features"></a>Nalevingsfuncties instellen

Uw Microsoft 365 Business wordt geleverd met functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw klanten veilig te houden.

## <a name="set-up-dlp-features"></a>DLP-functies instellen

Zie [een DLP-beleid maken op basis van een sjabloon](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) voor een voorbeeld over het instellen van een beleid ter bescherming tegen persoonlijk identificeerbare informatie (PII). 
  
DLP wordt geleverd met veel gebruiksklare beleidssjablonen voor veel verschillende landinstellingen. Bijvoorbeeld, Australië financiële gegevens, Canada Personal Information Act, Amerikaanse financiële gegevens, enz. Zie [wat de DLP-beleidssjablonen](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) voor een volledige lijst bevatten. Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>E-mail retentie instellen met Exchange Online-archivering

 De licentie functies voor het **archiveren van Exchange Online** helpen de nalevings-en regelgevingsnormen te handhaven door e-mail inhoud voor eDiscovery te behouden Het helpt ook verminderen uw risico in het geval van een rechtszaak en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging, of wanneer u nodig hebt om verwijderde items te herstellen. U rechtszaak blokkering gebruiken om alle inhoud van een gebruiker te behouden, of gebruik bewaarbeleid om aan te passen wat u wilt behouden.
  
**Rechtszaak Hold:** U alle inhoud van de postbus inclusief verwijderde items behouden door het hele postvak van een gebruiker in de rechtszaak te bewaren. 
    
Om een postbus te plaatsen in de rechtszaak Hold, in het Admin Center:
    
1. Ga in de linkernavigatiebalk naar **gebruikers** \> **actieve gebruikers**.
    
2. Selecteer een gebruiker wiens postvak u wilt plaatsen in de rechtszaak blokkering en in de gebruikers deelvenster Vouw **e-mail instellingen** en naast **meer instellingen** kiest u **Exchange-eigenschappen bewerken**.
    
3. Op de postbus pagina voor de gebruiker, kiest u * * mailbox functies * * op de linker NAV, en kies vervolgens de koppeling **inschakelen** onder **rechtszaak vasthouden**.
    
4. In het dialoogvenster **rechtszaak houden** u de duur van de rechtszaak houden in het veld **rechtszaak Hold duur** , laat veld leeg als u wilt plaatsen een oneindige hold. U ook notities toevoegen en de eigenaar van de brievenbus naar een website sturen die u wellicht meer moet uitleggen over de \> **Bewaar**procedure voor rechtszaken.
    
**Retentie:** U aangepaste bewaarbeleid inschakelen, bijvoorbeeld om te behouden voor een bepaalde hoeveelheid tijd of verwijderen van inhoud permanent aan het einde van de bewaarperiode. Zie [overzicht van bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)voor meer informatie.

## <a name="set-up-azure-information-protection-features"></a>Azure Information Protection-functies instellen

Azure Information Protection (AIP) helpt u bij het classificeren en optioneel beveiligen van uw documenten en e-mail berichten, door het toepassen van labels. Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden, handmatig door gebruikers definiëren of met behulp van een combinatie waar gebruikers aanbevelingen worden gegeven.

In Outlook op het web u de volgende ingebouwde labels en beperkingen toepassen op uw e-mails:
  
- **Niet doorsturen**: geadresseerden kunnen het bericht lezen, maar niet doorsturen, afdrukken of inhoud kopiëren
    
- **Versleutelen**: het hele bericht is versleuteld. Ontvangers moeten hun identiteit bevestigen voordat ze toegang krijgen tot versleutelde inhoud en kunnen geen versleuteling verwijderen.
    
- **Vertrouwelijk**: geeft de werknemers in uw organisatie volledige machtigingen voor de e-mail inhoud en bijlagen, maar niet voor mensen buiten uw organisatie. Eigenaren van gegevens kunnen op elk gewenst moment inhoud bijhouden en intrekken.
    
- **Zeer vertrouwelijk**: deze beperking kan worden toegepast op zeer vertrouwelijke gegevens, zodat werknemers de gegevens kunnen bekijken, bewerken en beantwoorden, maar niet doorsturen, afdrukken of kopiëren. Eigenaren van gegevens kunnen op elk gewenst moment inhoud bijhouden en intrekken.

### <a name="make-sure-azure-information-protection-is-activated"></a>Zorg ervoor dat Azure Information Protection is geactiveerd

Om te controleren of AIP is geactiveerd:

1. Meld u aan bij [Azure Portal](https://portal.azure.com/).

2. Selecteer **alle services** en typ *Azure Information Protection* in het **zoekvak**.

3. Zodra de resultaten weergegeven, klikt u op de start naast **Azure Information Protection** om het een favoriet en gemakkelijk te vinden later.

4. Selecteer **Azure Information Protection** \> - **beveiligingsactivering** en zorg ervoor dat de status is ingesteld op geactiveerd. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Het Azure Information Protection-beleid en de standaardlabels weergeven 

De bestaande labels weergeven en wijzigen:

1. Op de Azure Information Protection-dashboard, selecteer **classificaties** \> **labels**. <br/>![Standaard labels voor Azure Information Protection.](media/AIPLabels.png)

2. U elk label kiezen om opties te bekijken, u de weergavenaam, kleuren, etc. wijzigen.
 
3. Zie [wijzigen en maken van nieuwe labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) als u wilt maken van uw eigen. 

### <a name="install-the-azure-information-protection-client-manually"></a>De Azure Information Protection-client handmatig installeren

De AIP-client handmatig installeren:

1. Download **Azinfoprotection. exe** van [het Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. U controleren of de installatie heeft gewerkt door een Word-document te bekijken en ervoor te zorgen dat de optie **beveiligen** beschikbaar is op het tabblad **Start** . <br/>![Drop-down bescherming tabblad in een Word-document.](media/Word_Protect.png)

Zie voor meer informatie, [de client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
