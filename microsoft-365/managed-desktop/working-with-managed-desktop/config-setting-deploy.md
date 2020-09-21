---
title: Configureerbare instellingen implementeren in Microsoft Managed Desktop
description: Wijzigingen in de configureerbare instellingen in Microsoft beheerde Bureaubladimplementatie en bijhouden.
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, implementatie, gefaseerde implementatie, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104532"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Configureerbare instellingen implementeren en bijhouden: Microsoft Managed Desktop

Nadat u de instellings categorieën en de implementatie van een fase hebt gewijzigd, kunt u de instellingen van de pagina voor de implementatie van de instellingen wijzigen in groepen. Op deze pagina ziet u een overzicht van elke configureerbare instelling. Als u een instellings categorie opent, kunt u instellingen implementeren voor groepen en de voortgang van deze implementaties bijhouden.

## <a name="deployment-statuses"></a>Implementatiestatus 

Dit zijn de statussen die u ziet voor elke implementatie.

Status  | Uitleg 
--- | --- 
Implementeren | De wijziging wacht op de implementatie van deze groep.
Wordt uitgevoerd | De wijziging wordt toegepast op actieve apparaten in deze groep. 
Vul | De wijziging is voltooid op alle actieve apparaten in deze groep. 
Mislukt | De wijziging mislukt op een 10 procent van de actieve apparaten in de groep, dus de implementatie is gestopt.<br><br> Er wordt automatisch een ondersteuningsverzoek geopend met Microsoft beheerde bureaublad bewerkingen voor het oplossen van problemen met de implementatie. 
Teruggezet | De wijziging keert terug naar de laatste wijziging die is geïmplementeerd voor alle implementatie groepen.

## <a name="deploy-changes"></a>Wijzigingen implementeren

In deze instructies wordt de achtergrondafbeelding op het bureaublad weergegeven. Wanneer u een implementatie hebt klaargezet, implementeert u de wijzigingen op de pagina implementatiestatus. 

**Wijzigingen implementeren**

1. Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .
2. Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.
3. Selecteer in de werkruimte voor **implementatiestatus** de instelling die u wilt implementeren en selecteer vervolgens de gefaseerde implementatie die u wilt implementeren.
4. Selecteer **implementeren** om de wijziging te implementeren voor een van de implementatie groepen.

> [!NOTE] 
> Het oranje waarschuwingspictogram geeft aan dat er een eerdere groep beschikbaar is om te worden geïmplementeerd. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

We raden u aan om in deze volgorde implementatie groepen te implementeren: testen, voor het eerst, snel en vervolgens algemeen. 

Wanneer wijzigingen in elke groep worden doorgevoerd, wordt de status gewijzigd in **Voltooien**.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Implementatie herstellen

Nadat u een wijziging hebt geïmplementeerd, kunt u de **implementatiestatus**herstellen. Wanneer u een wijziging **doorvoert**die wordt **uitgevoerd** of voltooid, stopt de huidige implementatie. De instelling keert terug naar de laatste versie die is geïmplementeerd voor alle groepen. 

De stappen voor het herstellen van een wijziging met de bureaubladachtergrond afbeelding als voorbeeld worden weergegeven. 

**Een wijziging ongedaan maken**
1. Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .
2. Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.
3. Selecteer in de werkruimte voor **implementatiestatus** de instelling die u wilt herstellen en selecteer de gefaseerde implementatie die u wilt herstellen.
4. Selecteer onder **wilt u deze wijziging herstellen? de**optie **herstel herstellen**.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Aanvullende bronnen
- [Overzicht van configureerbare instellingen](config-setting-overview.md)
- [Verwijzing naar configureerbare instellingen](config-setting-ref.md) 
