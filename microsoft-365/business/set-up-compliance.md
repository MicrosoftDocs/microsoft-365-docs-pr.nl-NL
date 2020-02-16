---
title: Meer bescherming tegen bedreigingen voor Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
description: Stel nalevingsfuncties in om gegevensverlies te voorkomen en gevoelige gegevens te labelen.
ms.openlocfilehash: d569ff8d84faf82881035f0ed54e5d175605776f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42064695"
---
# <a name="set-up-compliance-features"></a>Nalevingsfuncties instellen

Uw Microsoft 365 Business wordt geleverd met functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige gegevens van u en uw klanten veilig te houden.

## <a name="set-up-dlp-features"></a>DLP-functies instellen

Zie [Een DLP-beleid](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) maken vanuit een sjabloon voor een voorbeeld over het instellen van een beleid dat u moet beschermen tegen persoonlijk identificeerbare informatie (PII). 
  
DLP wordt geleverd met veel kant-en-klare beleidssjablonen voor veel verschillende locaties. Bijvoorbeeld, Australië Financiële Gegevens, Canada Personal Information Act, Amerikaanse financiële gegevens, en ga zo maar door. Bekijk [Wat de DLP-beleidssjablonen bevatten](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) voor een volledige lijst. Al deze sjablonen kunnen worden ingeschakeld vergelijkbaar met het voorbeeld van de PII-sjabloon. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>E-mailretentie instellen met Exchange Online Archivering

 **Exchange Online Archiveringslicentiefuncties** helpen nalevings- en regelgevingsnormen te handhaven door e-mailinhoud voor eDiscovery te behouden. Het helpt ook uw risico te verminderen als er een rechtszaak is en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging of wanneer u verwijderde items moet herstellen. U geschillengebruiken om alle inhoud van een gebruiker te behouden of bewaarbeleid gebruiken om aan te passen wat u wilt behouden.
  
**Geschillenhouden:** U alle postvakinhoud, inclusief verwijderde items, behouden door het hele postvak van een gebruiker in de wachtstand van geschillen te zetten. 
    
Als u een postvak wilt plaatsen in de greep van geschillen, gaat u in het beheercentrum:
    
1. Ga in de linkernavigatienaar **Gebruikers** \> **Actieve gebruikers.**
    
2. Selecteer een gebruiker wiens postvak u in de greep van geschillen wilt plaatsen. Vouw in het gebruikersvenster **de instellingen voor e-mail**uit en kies naast **Meer instellingen** **exchange-eigenschappen bewerken**.
    
3. Kies op de postvakpagina voor de gebruiker ** postvakfuncties ** op het linkernavigatiesysteem en kies vervolgens de koppeling **Inschakelen** onder **Procesvoering.**
    
4. In het dialoogvenster **Geschillengreep** u de duur van de procesblokkering opgeven in het veld **Duur van de stand van zaken.** Laat het veld leeg als u een oneindige greep wilt plaatsen. U ook notities toevoegen en de eigenaar van de mailbox doorverwijzen naar een website die u mogelijk meer moet uitleggen over de geschillenhouder. \>**Opslaan**.
    
**Retentie:** U aangepaste bewaarbeleid bijvoorbeeld inschakelen om een bepaalde tijd te behouden of inhoud aan het einde van de bewaarperiode permanent te verwijderen. Zie [Overzicht van bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)voor meer informatie .

## <a name="set-up-sensitivity-labels"></a>Gevoeligheidslabels instellen

Gevoeligheidslabels worden geleverd met Azure Information Protection (AIP) Plan 1 en helpen u bij het classificeren en optioneel beveiligen van uw documenten en e-mails door labels toe te passen. Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers, of door een combinatie te gebruiken waarbij gebruikers aanbevelingen krijgen.

Als u Gevoeligheidslabels wilt instellen, bekijkt u video voor het maken en beheren van [gevoeligheidslabels.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)



### <a name="install-the-azure-information-protection-client-manually"></a>De Azure Information Protection-client handmatig installeren

Ga als basis voor de handmatige installatie van de AIP-client:

1. Download **AzinfoProtection_UL.exe** van [microsoft downloadcenter](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. U controleren of de installatie is uitgevoerd door een Word-document te bekijken en ervoor te zorgen dat de optie **Gevoeligheid** beschikbaar is op het tabblad **Start.**
<br/>![Vervolgkeuzelijst op het tabblad Beveiliging in een Word-document.](../media/word-sensitivity.png)

Zie [De client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)voor meer informatie.
