---
title: Bescherming tegen bedreigingen voor Microsoft 365 Business Premium vergroten
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
description: Stel nalevingsfuncties in om gegevensverlies te voorkomen en de gevoelige informatie van u en uw klanten veilig te houden.
ms.openlocfilehash: 18886ff3a0ba5e99e63c70ef083d7a69c75bac91
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785827"
---
# <a name="set-up-compliance-features"></a>Compliancefuncties instellen

Uw Microsoft 365 Business Premium wordt geleverd met functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van u en uw klanten veilig te houden.

## <a name="set-up-dlp-features"></a>DLP-functies instellen

[Zie Een DLP-beleid maken op basis van een sjabloon](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) voor een voorbeeld over het instellen van een beleid ter bescherming tegen persoonlijk identificeerbare informatie (PII). 
  
DLP wordt geleverd met veel kant-en-klare beleidssjablonen voor veel verschillende locaties. Bijvoorbeeld, Australië Financiële Gegevens, Canada Personal Information Act, Amerikaanse financiële gegevens, enzovoort. Zie [Wat de DLP-beleidssjablonen bevatten](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) voor een volledige lijst. Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>E-mailretentie instellen met Exchange Online Archivering

 **Licentiefuncties voor Exchange Online Archivering** helpen de nalevings- en regelgevingsnormen te handhaven door e-mailinhoud voor eDiscovery te behouden. Het helpt ook uw risico te verminderen als er een rechtszaak is, en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging of wanneer u verwijderde items moet herstellen. U geschillenruimte gebruiken om alle inhoud van een gebruiker te behouden of retentiebeleid gebruiken om aan te passen wat u wilt behouden.
  
**Geschillen houden:** U alle inhoud van het postvak, inclusief verwijderde items, behouden door het hele postvak van een gebruiker in de wachtstand te zetten. 
    
Als u een postvak in het wachtvak wilt plaatsen, gaat u in het beheercentrum:
    
1. Ga in het linkernavigatiesysteem **Users** naar \> **Gebruikers actieve gebruikers**.
    
2. Selecteer een gebruiker wiens postvak u in de wacht wilt plaatsen. Vouw in het gebruikersvenster **De instellingen voor E-mail**uit en kies naast **Meer instellingen** **exchange-eigenschappen bewerken**.
    
3. Kies op de postvakpagina voor de gebruiker ** postvakfuncties ** aan de linker navigatie en kies vervolgens de koppeling **Inschakelen** onder **Wachtgreep.**
    
4. In het dialoogvenster **Procesbed** hold u de duur van de resterende procedures opgeven in het veld **Resterende duur van geschillen.** Laat het veld leeg als u een oneindige greep wilt plaatsen. U ook notities toevoegen en de eigenaar van het postvak naar een website leiden die u mogelijk meer moet uitleggen over de procesruimte. \>**Opslaan**.
    
**Retentie:** U aangepaste bewaarbeleid inschakelen, bijvoorbeeld om inhoud aan het einde van de bewaarperiode voor een bepaalde tijd te bewaren of inhoud permanent te verwijderen. Zie [Overzicht van retentiebeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)voor meer informatie.

## <a name="set-up-sensitivity-labels"></a>Gevoeligheidslabels instellen

Gevoeligheidslabels worden geleverd met Azure Information Protection (AIP) Plan 1 en helpen u uw documenten en e-mails te classificeren en optioneel te beschermen door labels toe te passen. Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers, of met behulp van een combinatie waarbij gebruikers aanbevelingen krijgen.

Als u gevoeligheidslabels wilt instellen, bekijkt [u video met gevoeligheidslabels maken en beheren.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)



### <a name="install-the-azure-information-protection-client-manually"></a>De Azure Information Protection-client handmatig installeren

Ga als u de AIP-client handmatig installeert:

1. Download **AzinfoProtection_UL.exe** van [microsoft-downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. U controleren of de installatie heeft gewerkt door een Word-document weer te geven en ervoor te zorgen dat de optie **Gevoeligheid** beschikbaar is op het tabblad **Start.**
<br/>![Vervolgkeuzelijst Beveiliging in een Word-document.](../media/word-sensitivity.png)

Zie [De client installeren voor](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)meer informatie.
