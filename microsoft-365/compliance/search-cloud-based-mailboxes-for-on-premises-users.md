---
title: Chatgegevens voor Teams zoeken voor on-premises gebruikers
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Gebruik eDiscovery-hulpprogramma's in Microsoft 365 om chatgegevens in Teams te zoeken en te exporteren voor on-premises gebruikers in een hybride implementatie van Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311797"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Chatgegevens voor Teams zoeken voor on-premises gebruikers

Als uw organisatie een hybride implementatie van Exchange heeft (of als uw organisatie een on-premises Exchange-organisatie synchroniseert met Office 365) en Microsoft Teams heeft ingeschakeld, kunnen on-premises gebruikers de chattoepassing Teams gebruiken voor chatberichten. Voor een gebruiker in de cloud worden de chatgegevens van Teams (ook wel *1x1- of 1xN-chats* genoemd) opgeslagen in hun primaire postvak in de cloud. Wanneer een on-premises gebruiker gebruikmaakt van de chattoepassing Teams, kunnen de chatberichten niet worden opgeslagen in het primaire postvak, dat zich on-premises bevindt. Om deze beperking te omzeilen, heeft Microsoft een nieuwe functie uitgebracht waarin een opslaggebied in de cloud wordt gemaakt, zodat u eDiscovery-hulpprogramma's kunt gebruiken om chatgegevens van Teams te zoeken en exporteren voor on-premises gebruikers.
  
Dit zijn de vereisten en beperkingen voor het inschakelen van opslag in de cloud voor on-premises gebruikers:
  
- De gebruikersaccounts in uw on-premises adreslijstservice (zoals Active Directory) moeten worden gesynchroniseerd met Azure Active Directory, de adreslijstservice in Microsoft 365. Dit betekent dat er een e-mailgebruikersaccount wordt gemaakt in Microsoft 365 en is gekoppeld aan een gebruiker waarvan het primaire postvak zich in de on-premises organisatie bevindt.

- Aan de gebruiker waarvan het primaire postvak zich in de on-premises organisatie bevindt, moet een licentie voor Microsoft Teams en minimaal een licentie voor Exchange Online Abonnement 1 worden toegewezen.

- Als uw organisatie geen hybride implementatie van Exchange heeft, moet u uw on-premises Exchange-schema synchroniseren met Azure Active Directory. Als u dit niet doet, bestaat de kans dat u dubbele postvakken in de cloud aanmaakt in Exchange Online voor gebruikers die een postvak hebben in uw on-premises Exchange-organisatie.

- Alleen de chatgegevens van Teams die zijn gekoppeld aan een on-premises gebruiker, worden opgeslagen in het opslaggebied in de cloud. Een on-premises gebruiker heeft op geen enkele manier toegang tot dit opslaggebied.

> [!NOTE]
> Gesprekken in Teams-kanalen worden altijd opgeslagen in het postvak in de cloud dat is gekoppeld aan het team. Dit betekent dat u kunt zoeken naar kanaalgesprekken. Zie voor meer informatie over het zoeken in kanaalgesprekken van Teams [In Microsoft Teams en Microsoft 365 Groepen](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Hoe het werkt

Als een gebruiker met ondersteuning van Microsoft Teams een on-premises postvak heeft en zijn of haar gebruikersaccount/-identiteit is gesynchroniseerd met de cloud, maakt Microsoft opslag in de cloud om de chatgegevens van de on-premises gebruiker te koppelen aan de chatgegevens van 1xN Teams. Chatgegevens van teams voor on-premises gebruikers worden geïndexeerd voor zoekopdrachten. Hiermee kunt u inhoud zoeken (en zoekopdrachten die zijn gekoppeld aan kern-eDiscovery- en geavanceerde eDiscovery-zaken) gebruiken om chatgegevens van Teams te zoeken, te bekijken en te exporteren voor on-premises gebruikers. U kunt ook **\*ComplianceSearch**-cmdlets in het Beveiligings- en compliancecentrum PowerShell gebruiken om te zoeken naar chatgegevens van Teams voor on-premises gebruikers.
  
In de volgende afbeelding ziet u de workflow van de manier waarop chatgegevens van Teams voor on-premises gebruikers beschikbaar zijn voor zoeken, bekijken en exporteren.
  
![Cloudopslag voor on-premises gebruikers in Microsoft Teams](../media/EHAMShard1.png)
  
Naast deze mogelijkheid kunt u ook eDiscovery-hulpprogramma's gebruiken voor het zoeken, bekijken en exporteren van teams-inhoud in de SharePoint-cloudsite en het Exchange-postvak dat is gekoppeld aan elk Microsoft-team en 1xN Teams-chatgegevens in het Exchange Online-postvak voor gebruikers in de cloud.

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a>Hoe deze functie wordt ondersteund in Inhoud zoeken en Basishulpmiddelen voor eDiscovery

De volgende gebruikersinterface-elementen in Inhoud zoeken en in het zoekprogramma dat is gekoppeld aan Core eDiscovery-zaken in het Microsoft 365-compliancecentrum:
  
- Het selectievakje **App-inhoud toevoegen voor on-premises gebruikers** wordt weergegeven op de pagina **Locaties** van de wizard in de zoekfunctie voor inhoud en is standaard geselecteerd. Schakel dit selectievakje in als u de opslag in de cloud voor on-premises gebruikers wilt opnemen in een inhoudszoekactie.

    ![Het selectievakje Office-app-inhoud toevoegen voor on-premises gebruikers wordt toegevoegd aan de gebruikersinterface voor inhoud zoeken](../media/EHAMShardCheckBox.png)
  
- U kunt zoeken naar on-premises gebruikers wanneer u specifieke gebruikers kiest om naar te zoeken.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Chatgegevens voor Teams zoeken voor on-premises gebruikers

U kunt inhoud zoeken in het Microsoft 365-compliancecentrum als u wilt zoeken naar chatgegevens van Teams voor on-premises gebruikers.
  
1. Ga in het Microsoft 365-compliancecentrum naar **Inhoud zoeken**.

2. Klik op **tabblad** zoeken op **Nieuwe zoekopdracht** en benoem de nieuwe zoekopdracht.

3. Zet op de pagina **Locaties** de schakelaar op **Aan** voor Exchange-postvakken. U ziet dat het selectievakje **App-inhoud voor on-premises gebruikers** wordt weergegeven en standaard is ingeschakeld.

4. Als u Teams-inhoud voor specifieke gebruikers wilt zoeken, selecteert u **Gebruiker, groepen of teams** en kiest u specifieke gebruikers die u wilt opnemen in de zoekopdracht. Klik anders op **Volgende** om Teams-inhoud te zoeken voor alle gebruikers, inclusief on-premises gebruikers

5. Typ op de pagina **Uw zoekvoorwaarden definiëren** een trefwoordquery en voeg zo nodig voorwaarden aan de zoekquery toe. Als u alleen wilt zoeken naar gegevens van chats in Teams, kunt u de volgende query toevoegen in het vak **Trefwoorden**:

    ```text
    kind:im AND kind:microsoftteams
    ```

6. Zoekopdracht indienen en uitvoeren. U kunt een voorbeeld bekijken van alle zoekresultaten voor on-premises gebruikers, net zoals andere zoekresultaten. U kunt de zoekresultaten (inclusief de chatgegevens van Teams) ook exporteren naar een PST-bestand. Zie voor meer informatie:

    - [Een zoekactie maken](content-search.md)

    - [Zoekresultaten vooraf bekijken](preview-ediscovery-search-results.md)

    - [Zoekresultaten exporteren](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>PowerShell gebruiken om te zoeken naar chatgegevens van Teams voor on-premises gebruikers

U kunt de **New-ComplianceSearch**- en **Set-ComplianceSearch**-cmdlets in het Beveiligings- en compliancecentrum PowerShell gebruiken om te zoeken naar chatgegevens van Teams voor on-premises gebruikers. Zoals eerder uitgelegd, hoeft u geen ondersteuningsaanvraag in te dienen om PowerShell te gebruiken voor het zoeken naar chatgegevens van Teams voor on-premises gebruikers.
  
1. [Verbinding maken met Beveiligings- en compliancecentrum van Powershell](/powershell/exchange/connect-to-scc-powershell).

2. Voer de volgende PowerShell-opdracht uit om een inhoudszoekopdracht te maken die zoekt naar chatgegevens van Teams voor on-premises gebruikers.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    De parameter *IncludeUserAppContent*  wordt gebruikt om de cloudopslag op te geven voor de gebruiker of gebruikers die zijn opgegeven met de parameter  *ExchangeLocation*  . Met *AllowNotFoundExchangeLocationsEnabled*  kunt u in de cloud zoeken naar on-premises gebruikers. Wanneer u de waarde `$true` voor deze parameter gebruikt, wordt er niet geprobeerd om de aanwezigheid van het postvak te valideren voordat deze wordt uitgevoerd. Dit is vereist om on-premises gebruikers te zoeken in de cloudopslag, omdat deze opslag in de cloud niet wordt verwerkt als een gewoon postvak in de cloud.

    In het volgende voorbeeld wordt gezocht naar Teams-chats die het trefwoord 'redstone' bevatten in de opslag in de cloud voor Sara Davis, zij is een on-premises gebruiker in de Contoso-organisatie.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Nadat u een zoekopdracht hebt gemaakt, moet u de cmdlet **Start-ComplianceSearch** gebruiken om de zoekopdracht uit te voeren.
  
Zie voor meer informatie over het gebruik van deze cmdlets:
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Bekende problemen

- Op dit moment kunt u chatgegevens in Teams zoeken, bekijken en exporteren voor on-premises gebruikers. U kunt de Teams-chatgegevens voor een on-premises gebruiker ook in een opslag plaatsen die is gekoppeld aan een basis- of geavanceerde eDiscovery-case, en een bewaarbeleid toepassen voor Teams-chats of kanaalberichten voor on-premises gebruikers. Op dit moment kunt u echter geen bewaarbeleid toepassen voor andere opslaglocaties (zoals Exchange-postvakken en SharePoint-sites) voor on-premises gebruikers.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Moet ik een ondersteuningsaanvraag indienen om te zoeken naar chatberichten voor on-premises gebruikers?**

Nee. Deze functie is standaard ingeschakeld voor alle organisaties. Op een bepaald moment moest u contact opnemen met Microsoft Support, maar dat is niet meer het geval.
  
 **Kunnen eDiscovery-hulpprogramma's oudere chatgegevens van Teams voor on-premises gebruikers vinden vóór de tijd dat deze functie standaard voor alle organisaties was ingeschakeld?**
  
Microsoft is op 31 januari 2018 begonnen met het opslaan van de Teams-chatgegevens voor on-premises gebruikers. Dus als de identiteit van een on-premises Teams-gebruiker is gesynchroniseerd tussen uw on-premises Active Directory en Azure Active Directory in Microsoft 365, worden de chatgegevens van Teams opgeslagen in de cloud en kunnen deze worden doorzocht met eDiscovery-hulpprogramma's.

 **Hebben on-premises gebruikers een licentie nodig voor het opslaan van hun chatgegevens voor Teams in de cloud?**
  
Ja. Als u de chatgegevens van Teams voor een on-premises gebruiker wilt opslaan in een opslag in de cloud, moet aan de gebruiker een licentie voor Microsoft Teams en een licentie voor een Exchange Online-abonnement worden toegewezen in Office 365 (of Microsoft 365).

**Waar bevindt zich de cloudopslag voor on-premises gebruikers?**
  
De chatgegevens van Teams worden voor een on-premises gebruiker opgeslagen in de voorkeursgegevenslocatie (PDL). De PDL-omgeving is onderscheiden in zowel de omgeving met enkele geografische als de multi-geografische omgeving. Zie [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md) voor meer informatie.

**Bestaat de kans dat de chatgegevens van Teams verloren gaan als het on-premises postvak van de gebruiker naar de cloud wordt gemigreerd?**
  
Nee. Wanneer u het primaire postvak van een on-premises gebruiker migreert naar de cloud, worden de chatgegevens van Teams voor die gebruiker gemigreerd naar het nieuwe primaire postvak in de cloud.
  
 **Kan ik een eDiscovery-bewarings- of bewaarbeleid toepassen op on-premises gebruikers?**
  
Ja. U kunt eDiscovery-opslag of -bewaarbeleid toepassen voor teams-chats en kanaalberichten van on-premises gebruikers. Als u de inhoud van Teams echter wilt opslaan of behouden voor on-premises gebruikers, moet aan een on-premises gebruiker een licentie voor Exchange Online (Abonnement 2) worden toegewezen.
