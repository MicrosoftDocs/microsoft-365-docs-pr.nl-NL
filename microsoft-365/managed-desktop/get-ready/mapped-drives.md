---
title: Toegewezen stations voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8bdbbefb1fc3bfff324787eedb497afe781184f0
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/26/2020
ms.locfileid: "42809846"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Toegewezen stations voorbereiden voor Microsoft Managed Desktop

Veel bedrijfsomgevingen hebben verouderde vereisten voor toegewezen stations, zodat hun gebruikers of teams bestanden kunnen delen en opslaan, of voor on-premises toepassingen. Microsoft raadt het gebruik van toegewezen schijven met het Microsoft Managed Desktop niet aan. In plaats daarvan raden we u aan om oplossingen voor bestandstoegang te moderniseren:
  
- Migreer toegewezen stations die door individuele gebruikers worden gebruikt naar OneDrive voor Bedrijven. 
- Migreer toegewezen stations die door teams worden gebruikt om bestanden te delen met SharePoint Online. 
- Alle toepassingen die on-premises bestandsshares gebruiken om die vereiste te verwijderen moderniseren of vervangen.
  
Het moderniseren van deze services biedt de beste eindgebruikerservaring met Microsoft Managed Desktop. Microsoft FastTrack Services kan u helpen bij het moderniseren van uw omgeving met behulp van Microsoft Cloud Services. U controleren of u in aanmerking komt voor FastTrack-services bij [in aanmerking komende services en abonnementen](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) en vervolgens rechtstreeks contact met hen opnemen om u voor te bereiden op Microsoft Managed Desktop. Zie Gegevensmigratie voor achtergrondinformatie over FastTrack OneDrive voor Bedrijven of SharePoint [Online-migratie.](https://docs.microsoft.com/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Toegewezen stations op Microsoft Managed Desktop
 
Als u toegewezen stations voor bepaalde use cases niet verwijderen of vervangen, moet u een ondersteuningsverzoek indienen in de beheerportal van Microsoft Managed Desktop om ze te laten implementeren bij Microsoft Managed Desktop-gebruikers.
    
Voor een dergelijk verzoek moet u de volgende gegevens in het ondersteuningsverzoek opgeven: 

- Alle UNC-paden naar bestandssharelocaties die moeten worden toegewezen voor Beheerde bureaubladapparaten van Microsoft 
- Gebruikersgroepen die toegang tot deze locaties voor bestandsdelen vereisen 
- Een specifieke drive letter die moet worden toegewezen (indien nodig)

Bijvoorbeeld:

| Stationsletter | UNC-pad | Gebruikersgroep |
|--------------|----------|------------|
| X:  | \\\server\delen\Marketing | ContosoMarketing ContosoMarketing |

Het is volledig uw verantwoordelijkheid om ervoor te zorgen dat gebruikers en groepen over de juiste machtigingen beschikken en behouden om toegang te krijgen tot locaties voor bestandsshare en dat de on-premises bestandsservices toegankelijk blijven. Ook moet u uw vereisten voor dergelijke bestandsshares zo snel mogelijk verwijderen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Stations in kaart hebben gebracht die zijn geïmplementeerd in Microsoft Managed Desktop
 
Zorg ervoor dat toegewezen schijven niet kunnen worden vermeden en u de vereisten zorgvuldig hebt gecontroleerd voordat u een serviceaanvraag indient. Volg vervolgens de volgende stappen:

1. Navigeer naar de [Microsoft Managed Desktop-portal](https://aka.ms/mmdportal).  
2. Dien een ondersteuningsverzoek in met de titel 'Toegewezen schijven-implementatie' via de sectie **Ondersteuningsverzoeken > ondersteuningsverzoeken** en geef alle vereiste gegevens over bestandsshare.  
3. Microsoft Managed Desktop IT Operations zal u adviseren, door ondersteuningaanvraag-updates te gebruiken, wanneer het verzoek is voltooid. In eerste instantie wordt deze configuratie alleen geïmplementeerd op apparaten in de groep Implementatie testen.  
4. U moet testen en bevestigen of de configuratie die is geïmplementeerd door de Microsoft Managed Desktop IT Operations werkt zoals u verwacht. Antwoord via het tabblad Discussie in het ondersteuningsverzoek om Microsoft Managed Desktop IT Operations op de hoogte te stellen zodra u uw test hebt voltooid.  
5. Het Microsoft Managed Desktop IT Operations-team implementeert de configuratie vervolgens voor de andere implementatiegroepen. 
