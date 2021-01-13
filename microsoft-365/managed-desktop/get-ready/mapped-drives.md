---
title: Toegewezen stations voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 34b2186ea3f9129ae7bb602aee879d7d23424136
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841057"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Toegewezen stations voorbereiden voor Microsoft Managed Desktop

Veel ondernemingsomgevingen hebben oudere vereisten voor toegewezen stations, zodat ze hun gebruikers of teams in staat stellen bestanden te delen en op te slaan, of voor on-premises toepassingen. Microsoft adviseert het gebruik van toegewezen stations niet via het Microsoft beheerde bureaublad. U wordt aangeraden om de volgende oplossingen voor bestandstoegang te gebruiken:
  
- Migreer toegewezen stations die door individuele gebruikers worden gebruikt in OneDrive voor bedrijven. 
- Migreer toegewezen stations die door teams worden gebruikt om bestanden te delen met SharePoint Online. 
- U kunt toepassingen die gebruikmaken van on-premises bestandsshares moderniseren of vervangen om die vereiste te verwijderen.
  
Voor de beste gebruikerservaring met Microsoft Managed Desktop is de beste ervaring met de services. Met behulp van Microsoft-Cloud Services kan Microsoft FastTrack Services u helpen uw omgeving te moderniseren. U kunt controleren of u in aanmerking komt voor FastTrack Services in [in aanmerking komende Services en plannen](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) en ze rechtstreeks contact met hen opneemt voor de voorbereiding voor Microsoft Managed Desktop. Zie [gegevensmigratie](https://docs.microsoft.com/fasttrack/o365-data-migration)voor achtergrondinformatie over FastTrack OneDrive voor bedrijven of SharePoint Online-migratie.

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Toegewezen stations op Microsoft Managed Desktop
 
Als u toegewezen stations niet kunt verwijderen of vervangen voor een aantal use cases, moet u een ondersteuningsverzoek indienen in de portal van Microsoft Managed Desktop admin zodat ze kunnen worden geïmplementeerd voor Microsoft Managed desktop users.
    
Voor een dergelijk verzoek dient u de volgende gegevens in het ondersteuningsverzoek te verstrekken: 

- Alle UNC-paden naar locaties voor het delen van bestanden die moeten worden toegewezen voor Microsoft beheerde bureaublad apparaten 
- Gebruikersgroepen die toegang moeten hebben tot deze locaties voor het delen van bestanden 
- Elke specifieke stationsletter die moet worden toegewezen (indien nodig)

Bijvoorbeeld:

| Stationsletter | UNC-pad | Gebruikersgroep |
|--------------|----------|------------|
| X  | \\\server\share\Marketing | ContosoMarketing |

Het is uw verantwoordelijkheid om ervoor te zorgen dat gebruikers en groepen de juiste machtigingen hebben en de juiste machtigingen hebben voor toegang tot de bestandsshare locaties en de on-premises Bestandsservices toegankelijk blijven. Daarnaast dient u zo snel mogelijk uw vereisten voor bestandsshares te verwijderen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Toegewezen stations implementeren in Microsoft Managed Desktop
 
Zorg ervoor dat de stationstoewijzingen niet worden vermeden en dat u de vereisten zorgvuldig door hebt bekeken voordat u een serviceaanvraag verzendt. Voer daarna de volgende stappen uit:

1. Ga naar [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en selecteer ' probleemoplossing + ondersteuning ' en zoek vervolgens naar ' service aanvragen ' onder de sectie beheerde bureaubladversie van Microsoft.  
2. Verzend een ondersteuningsaanvraag met de naam ' toegewezen schijven implementeren ' en geef alle vereiste gegevens voor de bestandsdeling op.  
3. Microsoft Managed Desktop IT IT zal u adviseren met updates van ondersteuningsaanvragen wanneer de aanvraag is voltooid. Deze configuratie wordt in eerste instantie alleen geïmplementeerd op apparaten in de groep test implementatie.  
4. U moet testen en controleren of de configuratie die is geïmplementeerd door het Microsoft beheerde bureaublad IT, werkt zoals u verwacht. Antwoord met het tabblad discussie in de details van hetzelfde ondersteuningsverzoek voor het melden van de bewerkingen van het Microsoft-beheer bureaublad wanneer u klaar bent met het testen.  
5. Microsoft beheerde bureaublad IT Operations team implementeert vervolgens de configuratie naar de andere implementatie groepen. 
