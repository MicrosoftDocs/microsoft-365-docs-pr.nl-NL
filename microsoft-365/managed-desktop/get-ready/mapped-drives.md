---
title: Toegewezen stations voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: e6311c0ad11d68c870b0c8185974b8913735e2a2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530173"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Toegewezen stations voorbereiden voor Microsoft Managed Desktop

Veel bedrijfsomgevingen hebben verouderde vereisten voor toegewezen stations, zodat hun gebruikers of teams bestanden kunnen delen en opslaan, of voor on-premises toepassingen. Microsoft raadt het gebruik van toegewezen schijven met de Microsoft Managed Desktop af. In plaats daarvan raden we u aan uw oplossingen voor bestandstoegang als volgt te moderniseren:
  
- Gemigreerde stations migreren die door individuele gebruikers worden gebruikt naar OneDrive voor Bedrijven. 
- Gemigreerde stations migreren die door teams worden gebruikt om bestanden te delen naar SharePoint Online. 
- Moderniseer of vervang toepassingen die on-premises bestandsshares gebruiken om die vereiste te verwijderen.
  
Door deze services te moderniseren, u de beste eindgebruikerservaring bieden met Microsoft Managed Desktop. Microsoft FastTrack Services kan u helpen bij het moderniseren van uw omgeving met Behulp van Microsoft Cloud Services. U controleren of u in aanmerking komt voor FastTrack-services bij [in aanmerking komende services en abonnementen](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) en vervolgens rechtstreeks contact met hen opnemen om u voor te bereiden op Microsoft Managed Desktop. Zie [Gegevensmigratie](https://docs.microsoft.com/fasttrack/o365-data-migration)voor achtergrondinformatie over FastTrack OneDrive voor Bedrijven of SharePoint Online-migratie.

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Toegewezen schijven op Microsoft Managed Desktop
 
Als u voor sommige gebruiksaanvragen geen toegewezen stations verwijderen of vervangen, dient u een ondersteuningsverzoek in de Microsoft Managed Desktop-beheerportal in te dienen om deze te laten implementeren voor Microsoft Managed Desktop-gebruikers.
    
Voor een dergelijk verzoek moet u de volgende gegevens opgeven in het ondersteuningsverzoek: 

- Alle UNC-paden naar locaties voor bestandsshare die moeten worden toegewezen voor Microsoft Managed Desktop-apparaten 
- Gebruikersgroepen die toegang tot deze locaties voor bestandsshare vereisen 
- Elke specifieke drive letter die moet worden toegewezen (indien nodig)

Bijvoorbeeld:

| Stationsletter | UNC-pad | Gebruikersgroep |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Het is volledig uw verantwoordelijkheid om ervoor te zorgen dat gebruikers en groepen de juiste machtigingen hebben en behouden om toegang te krijgen tot locaties voor bestandsshare en dat de on-premises bestandsservices toegankelijk blijven. Ook moet u uw vereisten voor dergelijke bestandsshares zo snel mogelijk verwijderen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Stations in kaart brengen die zijn geïmplementeerd in Microsoft Managed Desktop
 
Zorg ervoor dat toegewezen stations niet kunnen worden vermeden en u de vereisten zorgvuldig hebt beoordeeld voordat u een serviceaanvraag indient. Volg dan de volgende stappen:

1. Navigeer naar de [Microsoft Managed Desktop-portal](https://aka.ms/mmdportal).  
2. Dien een ondersteuningsverzoek in met de titel 'Mapped drives deployment' via de sectie **Ondersteuning > Ondersteuningsaanvragen** en alle vereiste gegevens voor bestandsdeling opgeven.  
3. Microsoft Managed Desktop IT Operations adviseert door gebruik te maken van updates voor ondersteuningsverzoeken wanneer de aanvraag is voltooid. In eerste instantie wordt deze configuratie alleen geïmplementeerd op apparaten in de implementatiegroep Testen.  
4. U moet testen en bevestigen of de configuratie die is geïmplementeerd door de Microsoft Managed Desktop IT Operations werkt zoals u verwacht. Antwoord op het tabblad Discussie in het ondersteuningsverzoek om Microsoft Managed Desktop IT Operations op de hoogte te stellen zodra u uw tests hebt voltooid.  
5. Microsoft Managed Desktop IT Operations-team implementeert de configuratie vervolgens naar de andere implementatiegroepen. 
