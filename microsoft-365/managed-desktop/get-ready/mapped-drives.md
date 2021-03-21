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
ms.openlocfilehash: cd45d6155fc0e01f6a285f6182aa051281d160e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922906"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Toegewezen stations voorbereiden voor Microsoft Managed Desktop

Veel bedrijfsomgevingen hebben oudere vereisten voor in kaart gebrachte stations om hun gebruikers of teams in staat te stellen bestanden te delen en op te slaan, of voor on-premises toepassingen. Microsoft raadt het gebruik van kaartstations met het beheerde bureaublad van Microsoft af. In plaats daarvan wordt u aangeraden uw oplossingen voor bestandstoegang als volgt te moderniseren:
  
- Gemapte stations die door afzonderlijke gebruikers worden gebruikt migreren naar OneDrive voor Bedrijven. 
- Gemigreerde stations die door teams worden gebruikt om bestanden te delen naar SharePoint Online. 
- Moderniseer of vervang toepassingen die on-premises bestandsaandelen gebruiken om deze vereiste te verwijderen.
  
Als u deze services moderniseert, kunt u de beste gebruikerservaring met Microsoft Managed Desktop gebruiken. Microsoft FastTrack Services kan u helpen bij het moderniseren van uw omgeving met Behulp van Microsoft Cloud Services. U kunt controleren of u in aanmerking komt voor FastTrack-services bij In aanmerking komende [services](/fasttrack/m365-eligible-services-and-plans) en abonnementen en rechtstreeks contact met hen opnemen om u voor te bereiden op Microsoft Managed Desktop. Zie Gegevensmigratie voor achtergrondinformatie over FastTrack OneDrive voor Bedrijven of SharePoint [Online-migratie.](/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>In kaart gebrachte stations op Microsoft Managed Desktop
 
Als u voor bepaalde gebruiksgevallen niet in kaart gebrachte stations kunt verwijderen of vervangen, moet u een ondersteuningsaanvraag indienen in de Microsoft Managed Desktop-beheerportal om ze te laten geïmplementeerd voor Microsoft Managed Desktop-gebruikers.
    
Voor een dergelijke aanvraag moet u de volgende details in de ondersteuningsaanvraag verstrekken: 

- Alle UNC-paden naar locaties voor bestands delen die moeten worden in kaart gebracht voor Microsoft Managed Desktop-apparaten 
- Gebruikersgroepen die toegang nodig hebben tot deze locaties voor het delen van bestanden 
- Een specifieke station letter die moet worden toegewezen (indien nodig)

Bijvoorbeeld:

| Brief van station | UNC-pad | Gebruikersgroep |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Het is volledig uw verantwoordelijkheid ervoor te zorgen dat gebruikers en groepen de juiste machtigingen hebben en behouden voor toegang tot locaties voor bestands delen en dat de on-premises bestandsservices toegankelijk blijven. U moet ook uw vereisten voor dergelijke bestandsaandelen zo snel mogelijk verwijderen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Stations in kaart hebben gebracht die zijn geïmplementeerd in Microsoft Managed Desktop
 
Zorg ervoor dat de in kaart gebrachte stations niet kunnen worden vermeden en dat u de vereisten zorgvuldig hebt gecontroleerd voordat u een serviceaanvraag indient. Volg vervolgens de volgende stappen:

1. Ga naar [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en selecteer 'Probleemoplossing + ondersteuning' en zoek vervolgens naar 'Serviceaanvragen' onder de sectie Beheerd bureaublad van Microsoft.  
2. Verzend een ondersteuningsaanvraag met de titel 'Implementatie van stations in kaart gebracht' en geef alle vereiste gegevens over het delen van bestanden op.  
3. Microsoft Managed Desktop IT Operations adviseert u, met behulp van updates voor ondersteuningsverzoeken, wanneer de aanvraag is voltooid. In eerste instantie wordt deze configuratie alleen geïmplementeerd op apparaten in de groep Test-implementatie.  
4. U moet testen en controleren of de configuratie die is geïmplementeerd door de IT-bewerkingen van Microsoft Managed Desktop werkt zoals u verwacht. Reageer op het tabblad Discussie in de details van dezelfde ondersteuningsaanvraag om Microsoft Managed Desktop IT Operations op de hoogte te stellen nadat u de test hebt voltooid.  
5. Microsoft Managed Desktop IT Operations-team implementeert de configuratie vervolgens naar de andere implementatiegroepen.