---
title: Bedreigingenbescherming voor Microsoft 365 Business Premium vergroten
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
search.appverid:
- BCS160
- MET150
description: Stel nalevingsfuncties in om gegevensverlies te voorkomen en de gevoelige informatie van uw en uw klanten veilig te houden.
ms.openlocfilehash: 523d020587bcf16e46263b88ee7654b9c786e7a2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048060"
---
# <a name="set-up-compliance-features"></a>Compliancefuncties instellen

Uw Microsoft 365 Business Premium wordt geleverd met functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw en uw klanten veilig te houden.

## <a name="set-up-dlp-features"></a>DLP-functies instellen

Zie [Een DLP-beleid maken op basis van een sjabloon](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) voor een voorbeeld over het instellen van een beleid om te beschermen tegen persoonlijk identificeerbare informatie (PII). 
  
DLP wordt geleverd met veel kant-en-klare beleidssjablonen voor veel verschillende locaties. Bijvoorbeeld, Australia Financial Data, Canada Personal Information Act, Amerikaanse financiële gegevens, enzovoort. Zie [wat de DLP-beleidssjablonen bevatten](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) voor een volledige lijst. Al deze sjablonen kunnen worden ingeschakeld vergelijkbaar met de PII-sjabloon voorbeeld. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>E-mailretentie instellen met Exchange Online Archivering

 **Licentiefuncties voor Exchange Online Archiveren** helpen nalevings- en regelgevingsnormen te handhaven door e-mailinhoud voor eDiscovery te bewaren. Het helpt ook uw risico te verminderen als er een rechtszaak, en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging of wanneer u nodig hebt om verwijderde items te herstellen. U het bewaren van geschillen gebruiken om alle inhoud van een gebruiker te behouden of bewaarbeleid gebruiken om aan te passen wat u wilt behouden.
  
**Geschillen houden:** U alle postvakinhoud inclusief verwijderde items behouden door het volledige postvak van een gebruiker in de wachtstand te plaatsen. 
    
Als u een postvak in de wachtstand voor geschillen wilt plaatsen, gaat u in het beheercentrum:
    
1. Ga in de linkernavigatie naar **Gebruikers** \> **Actief-gebruikers**.
    
2. Selecteer een gebruiker wiens postvak u wilt plaatsen in een proceswacht. Kies in het gebruikersvenster **E-mailinstellingen**en naast **Meer instellingen**de optie **Exchange-eigenschappen bewerken**.
    
3. Kies op de postvakpagina voor de gebruiker ** postvakfuncties ** op de linkernavigatie en kies vervolgens de koppeling **Inschakelen** onder **Proceshouden .**
    
4. In het dialoogvenster **Procesblokkering** u de duur van de procesperiode opgeven in het veld **Duurduur van de procesperiode.** Laat het veld leeg als u een oneindige greep wilt plaatsen. U ook notities toevoegen en de eigenaar van de mailbox doorverwijzen naar een website die u mogelijk meer moet uitleggen over de blokkering van geschillen. \>**Opslaan**.
    
**Retentie:** U aangepaste bewaarbeleidsregels inschakelen, bijvoorbeeld om voor een bepaalde tijd te behouden of inhoud permanent te verwijderen aan het einde van de bewaarperiode. Zie [Overzicht van bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)voor meer informatie .

## <a name="set-up-sensitivity-labels"></a>Gevoeligheidslabels instellen

Gevoeligheidslabels worden geleverd met Azure Information Protection (AIP) Plan 1 en helpen u bij het classificeren en optioneel beveiligen van uw documenten en e-mails door labels toe te passen. Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers of met behulp van een combinatie waarbij gebruikers aanbevelingen krijgen.

Als u Gevoeligheidslabels wilt instellen, bekijkt [u de video voor het maken en beheren van gevoeligheidslabels.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)



### <a name="install-the-azure-information-protection-client-manually"></a>De Azure Information Protection-client handmatig installeren

Ga als lid van het werk om de AIP-client handmatig te installeren:

1. Download **AzinfoProtection_UL.exe** van [het Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018)van Microsoft.
 
2. U controleren of de installatie heeft gewerkt door een Word-document te bekijken en ervoor te zorgen dat de **optie Gevoeligheid** beschikbaar is op het tabblad **Start.**
<br/>![Vervolgkeuzelijst op het tabblad Beveiliging in een Word-document.](../media/word-sensitivity.png)

Zie [De client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)voor meer informatie.
