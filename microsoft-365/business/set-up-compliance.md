---
title: Bedreigingsbeveiliging voor Microsoft 365 Business Premium verhogen
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Stel compliancefuncties in om gegevensverlies te voorkomen en om de gevoelige informatie van uw en uw klanten veilig te houden.
ms.openlocfilehash: c0accc37d3dcda9ba75813f01a98a3233c5a8369
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579949"
---
# <a name="set-up-compliance-features"></a>Compliancefuncties instellen

Uw Microsoft 365 Business Premium bevat functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw en uw klanten veilig te houden.

## <a name="set-up-dlp-features"></a>DLP-functies instellen

Zie [Een DLP-beleid maken op basis](../compliance/create-a-dlp-policy-from-a-template.md) van een sjabloon voor een voorbeeld van het instellen van een beleid ter bescherming tegen verlies van persoonlijke gegevens. 
  
DLP wordt geleverd met veel kant-en-klare beleidssjablonen voor veel verschillende locales. Bijvoorbeeld: Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, en meer. Zie [Wat de DLP-beleidsjablonen bevatten voor](../compliance/what-the-dlp-policy-templates-include.md) een volledige lijst. Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>E-mailretentie instellen met Archivering van Exchange Online

 **Exchange Online Archiving-licentiefuncties** helpen bij het handhaven van nalevings- en regelgevingsstandaarden door e-mailinhoud voor eDiscovery te behouden. Het helpt ook uw risico te beperken als er een proces is en biedt een manier om gegevens te herstellen na een beveiligingsinbreuk of wanneer u verwijderde items moet herstellen. U kunt de bewaring van rechtszaken gebruiken om alle inhoud van een gebruiker te behouden of bewaarbeleid gebruiken om aan te passen wat u wilt behouden.
  
**Procesrecht in de wacht:** U kunt alle postvakinhoud, inclusief verwijderde items, behouden door het hele postvak van een gebruiker in de wacht te zetten. 
    
Als u een postvak in de wacht wilt zetten voor rechtszaken, gaat u naar het beheercentrum:
    
1. Ga in de linkernavigatiebalk naar **Gebruikers** \> **Actieve gebruikers.**
    
2. Selecteer een gebruiker van wie u het postvak in de wacht wilt zetten. Vouw in het gebruikersvenster **E-mailinstellingen** uit en kies naast **Meer instellingen** de optie **Exchange-eigenschappen bewerken.**
    
3. Kies op de postvakpagina voor de gebruiker ** postvakfuncties ** aan de linkerkant en kies vervolgens de **koppeling** Inschakelen onder **Procesvoering.**
    
4. In het **dialoogvenster Procesrecht** kunt u de duur van de procesduur opgeven in het veld Duur van de duur van **de procesduur.** Laat het veld leeg als u een oneindige greep wilt plaatsen. U kunt ook notities toevoegen en de eigenaar van het postvak naar een website leiden die u mogelijk meer moet uitleggen over de procedure. \>**Opslaan**.
    
**Bewaring:** U kunt aangepaste bewaarbeleidsregels inschakelen, bijvoorbeeld om inhoud voor een bepaalde periode te bewaren of inhoud permanent te verwijderen aan het einde van de bewaarperiode. Zie Overzicht van [bewaarbeleid voor](../compliance/retention.md)meer informatie.

## <a name="set-up-sensitivity-labels"></a>Gevoeligheidslabels instellen

Gevoeligheidslabels worden bij Azure Information Protection (AIP) Plan 1 gebruikt, en u kunt uw documenten en e-mailberichten classificeren en desgewenst beveiligen door etiketten toe te passen. Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers, of door een combinatie te gebruiken waarin gebruikers aanbevelingen krijgen.

Als u Gevoeligheidslabels wilt instellen, bekijkt u video over het maken en beheren [van gevoeligheidslabels.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)



### <a name="install-the-azure-information-protection-client-manually"></a>De Azure Information Protection-client handmatig installeren

De AIP-client handmatig installeren:

1. Download **AzinfoProtection_UL.exe** downloadcentrum [van Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)
 
2. U kunt controleren of de installatie heeft gewerkt door  een Word-document weer te geven en ervoor te zorgen dat de optie Gevoeligheid beschikbaar is op het **tabblad** Start.
<br/>![Vervolgkeuzevenster Beveiliging in een Word-document.](../media/word-sensitivity.png)

Zie De [client installeren voor meer informatie.](/azure/information-protection/infoprotect-tutorial-step3)