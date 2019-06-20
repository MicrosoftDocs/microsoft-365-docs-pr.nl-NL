---
title: Bescherming van de bedreiging voor Microsoft 365 Business verhogen
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
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection instellen en vertrouwelijke gegevens te beschermen.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/31/2019
ms.locfileid: "35086300"
---
# <a name="set-up-compliance-features"></a>Naleving van functies instellen

Uw bedrijf Microsoft 365 beschikt u over functies voor uw bedrijf en uw klanten gevoelige informatie beveiligen en beschermen van uw gegevens en apparaten.

## <a name="set-up-dlp-features"></a>DLP-functies instellen

Zie [een DLP-beleid van een sjabloon maken](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) voor een voorbeeld van het instellen van een beleid ter bescherming tegen persoonlijk identificeerbare informatie (PII). 
  
DLP wordt geleverd met een groot aantal kant-en-klare sjablonen voor veel verschillende landinstellingen. Bijvoorbeeld financiële gegevens van Australië, Canada persoonlijk informatie handelen, Amerikaanse financiële gegevens, enz. Zie [Wat de DLP-beleidssjablonen opnemen](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) voor een volledige lijst. Al deze sjablonen kunnen worden ingeschakeld als in het voorbeeld van de sjabloon PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>E-mail bewaren met Exchange Online Archiving instellen

 Functies van **Exchange Online Archiving** licentie ten behoeve van conformiteit en wettelijke normen e-mail behouden voor eDiscovery-inhoud. Ook vermindert het risico in geval van een rechtsgeding en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging of als u verwijderde items herstellen. U kunt de rechtszaak vasthouden gebruiken voor het behoud van de inhoud van een gebruiker of bewaarbeleid gebruiken voor het aanpassen van wat u wilt behouden.
  
**Rechtszaak geblokkeerd:** U kunt alle inhoud met inbegrip van verwijderde items door het volledige postvak van een gebruiker in de rechtszaak plaatsen houdt behouden. 
    
Om een postbus Afwachten rechtszaak, in de Admin center:
    
1. Ga naar **gebruikers** in de Linkernavigatie \> **actieve gebruikers**.
    
2. Selecteer een gebruiker wiens postvak u wilt plaatsen op de rechtszaak houdt en vouw in het deelvenster gebruiker **e-mailinstellingen** en kies **Eigenschappen bewerken Exchange**naast **meer instellingen** .
    
3. Kies op de pagina postvak voor de gebruiker ** postbus functies ** op de Linkernavigatie en kies vervolgens de koppeling **inschakelen** onder **rechtszaak houdt**.
    
4. In de **rechtszaak houdt** in het dialoogvenster kunt u opgeven dat de rechtszaak duur in het veld **rechtszaak duur houdt** ingedrukt, laat het veld leeg als u wilt een oneindige wachtruimte te plaatsen. U kunt ook notities toevoegen en rechtstreeks van de eigenaar van het vak e-mail naar een website die u wellicht meer informatie over de rechtszaak houdt uitgelegd \> **Opslaan**.
    
**Bewaren:** U kunt bijvoorbeeld aangepaste bewaarbeleid behouden gedurende een bepaalde tijd of permanent verwijderen van inhoud aan het einde van de bewaarperiode inschakelen. Voor meer informatie, Zie [overzicht van het bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="set-up-azure-information-protection-features"></a>Azure informatie beveiligingsfuncties instellen

Azure informatie Protection (AIP) helpt u bij het classificeren en bescherming van uw documenten en e-mails, eventueel door labels toe te passen. Labels kunnen automatisch worden toegepast die regels en voorwaarden definiëren door beheerders handmatig door gebruikers of door een combinatie waar gebruikers aanbevelingen krijgen.

U kunt in Outlook op het web de volgende ingebouwde labels en beperkingen toepassen op uw e-mailberichten:
  
- **Niet doorsturen**: geadresseerden kunnen het bericht lezen, maar ze kunnen doorsturen, afdrukken of kopiëren van inhoud
    
- **Coderen**: het hele bericht is gecodeerd. Ontvangers hun identiteit moeten bevestigen voordat deze toegang krijgen tot gecodeerde inhoud en codering niet verwijderen.
    
- **Vertrouwelijk**: de werknemers in uw organisatie biedt volledige machtigingen voor de inhoud van e-mail en bijlagen, maar niet voor personen buiten uw organisatie. Eigenaars van gegevens kunnen bijhouden en de inhoud op elk moment intrekken.
    
- **Zeer vertrouwelijke**: deze beperking tot zeer vertrouwelijke gegevens, zodat werknemers kunnen bekijken, bewerken, en beantwoorden, maar niet doorsturen, afdrukken of kopiëren van de gegevens kan worden toegepast. Eigenaars van gegevens kunnen bijhouden en de inhoud op elk moment intrekken.

### <a name="make-sure-azure-information-protection-is-activated"></a>Zorg ervoor dat informatiebeveiliging Azure is geactiveerd.

Om te verifiëren dat de AIP is geactiveerd:

1. Inloggen op [portal Azure](https://portal.azure.com/).

2. Selecteer **alle services** en typ in *Azure informatiebeveiliging* in het **Vak Zoeken**.

3. Zodra de resultaten worden weergegeven, klikt u op het begin volgende **Informatiebescherming Azure** een favoriet maken en later gemakkelijk te vinden.

4. **Azure informatie** beveiliging \> **activering bescherming** en zorg ervoor dat de status is ingesteld op actief. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>De Azure informatiebeveiliging en de standaard etiketten weergeven 

Als u wilt weergeven en wijzigen, de bestaande labels:

1. Selecteer op het dashboard Azure informatiebescherming **classificaties** \> **etiketten**. <br/>![Standaard etiketten voor informatiebescherming Azure.](media/AIPLabels.png)

2. U kunt een label om opties weer te geven, kunt u de weergavenaam, kleuren, enz.
 
3. Zie [wijzigen en nieuwe labels maken](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) als u wilt uw eigen maken. 

### <a name="install-the-azure-information-protection-client-manually"></a>De client Azure informatiebeveiliging handmatig installeren

De client AIP handmatig installeren:

1. **AzInfoProtection.exe** downloaden van het [Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. U kunt controleren of de installatie heeft gewerkt door een Word-document bekijken en ervoor te zorgen dat de optie **Protect** beschikbaar op het tabblad **Start is** . <br/>![Tabblad Beveiliging vervolgkeuzelijst in een Word-document.](media/Word_Protect.png)

Zie voor meer informatie [de client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
