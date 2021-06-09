---
title: Toegewezen stations voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat gebruikers toegang hebben tot gegevens op kaartstations
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f770f5083fe9193660b03e7971b09a127f2dae16
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574557"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Toegewezen stations voorbereiden voor Microsoft Managed Desktop

Veel bedrijfsomgevingen hebben oudere vereisten voor in kaart gebrachte stations om hun gebruikers of teams in staat te stellen bestanden te delen en op te slaan, of voor on-premises toepassingen. Microsoft raadt het gebruik van kaartstations met de Microsoft Managed Desktop. In plaats daarvan wordt u aangeraden uw oplossingen voor bestandstoegang als volgt te moderniseren:
  
- Gemigreerde stations die door afzonderlijke gebruikers worden gebruikt, migreren naar OneDrive voor Bedrijven. 
- Gemigreerde stations die door teams worden gebruikt om bestanden te delen SharePoint Online. 
- Moderniseer of vervang toepassingen die on-premises bestandsaandelen gebruiken om deze vereiste te verwijderen.
  
Als u deze services moderniseert, kunt u de beste gebruikerservaring met Microsoft Managed Desktop. Microsoft FastTrack Services kan u helpen bij het moderniseren van uw omgeving met Behulp van Microsoft Cloud Services. U kunt controleren of u in aanmerking komt voor FastTrack-services bij In aanmerking komende [services](/fasttrack/m365-eligible-services-and-plans) en abonnementen en rechtstreeks contact met hen opnemen om u voor te bereiden op Microsoft Managed Desktop. Zie Gegevensmigratie voor achtergrondinformatie over FastTrack OneDrive voor Bedrijven of SharePoint [onlinemigratie.](/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>In kaart gebrachte stations op Microsoft Managed Desktop
 
Als u voor bepaalde gebruiksgevallen niet in kaart gebrachte stations kunt verwijderen of vervangen, moet u een ondersteuningsaanvraag indienen in de Microsoft Managed Desktop-beheerportal om ze te laten geïmplementeerd voor Microsoft Managed Desktop gebruikers.
    
Voor een dergelijke aanvraag moet u de volgende details in de ondersteuningsaanvraag verstrekken: 

- Alle UNC-paden naar locaties voor bestands delen die moeten worden in kaart gebracht voor Microsoft Managed Desktop apparaten 
- Gebruikersgroepen die toegang nodig hebben tot deze locaties voor het delen van bestanden 
- Een specifieke station letter die moet worden toegewezen (indien nodig)

Bijvoorbeeld:

| Brief van station | UNC-pad | Gebruikersgroep |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Het is volledig uw verantwoordelijkheid ervoor te zorgen dat gebruikers en groepen de juiste machtigingen hebben en behouden voor toegang tot locaties voor bestands delen en dat de on-premises bestandsservices toegankelijk blijven. U moet ook uw vereisten voor dergelijke bestandsaandelen zo snel mogelijk verwijderen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Stations in kaart brengen die zijn geïmplementeerd in Microsoft Managed Desktop
 
Zorg ervoor dat de in kaart gebrachte stations niet kunnen worden vermeden en dat u de vereisten zorgvuldig hebt gecontroleerd voordat u een serviceaanvraag indient. Volg vervolgens de volgende stappen:

1. Ga naar [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en selecteer 'Probleemoplossing + ondersteuning' en zoek vervolgens naar 'Serviceaanvragen' onder de Microsoft Managed Desktop sectie.  
2. Verzend een ondersteuningsaanvraag met de titel 'Implementatie van stations in kaart gebracht' en geef alle vereiste gegevens over het delen van bestanden op.  
3. Microsoft Managed Desktop IT Operations adviseert u door updates voor ondersteuningsverzoeken te gebruiken wanneer de aanvraag is voltooid. In eerste instantie wordt deze configuratie alleen geïmplementeerd op apparaten in de groep Test-implementatie.  
4. U moet testen en controleren of de configuratie die is geïmplementeerd door de Microsoft Managed Desktop IT-bewerkingen werkt zoals u verwacht. Beantwoorden via het tabblad Discussie in de details van dezelfde ondersteuningsaanvraag om de it-Microsoft Managed Desktop te melden nadat u de test hebt voltooid.  
5. Microsoft Managed Desktop Het IT-operations-team implementeert de configuratie vervolgens naar de andere implementatiegroepen. 

## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Controleer [Vereisten voor Microsoft Managed Desktop.](prerequisites.md)
2. [Gebruik gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)
3. [Vereisten voor gast-accounts](guest-accounts.md)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Kaartstations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md) (dit artikel)
9. [Afdrukbronnen voorbereiden voor Microsoft Managed Desktop](printing.md)
