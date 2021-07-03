---
title: Configureerbare instellingen implementeren in Microsoft Managed Desktop
description: Configureerbare instellingen wijzigen implementeren en bijhouden in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, implementeren, gefaseerd implementeren, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287793"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Configureerbare instellingen implementeren en bijhouden - Microsoft Managed Desktop

Nadat u wijzigingen hebt aangebracht in uw instellingscategorieën en een implementatie hebt geïmplementeerd, kunt u op de pagina Implementatiestatus beginnen met het implementeren van uw instellingen naar groepen. Op deze pagina ziet u een overzicht van elke configureerbare instelling. Door een instellingscategorie te openen, kunt u instellingen implementeren voor groepen en de voortgang van deze implementaties bijhouden.

## <a name="deployment-statuses"></a>Implementatiestatussen

Dit zijn de statussen die u voor elke implementatie ziet.

Status | Uitleg
--- | ---
Implementeren | Uw wijziging wacht op de geïmplementeerde wijziging in deze groep.
In uitvoering | De wijziging wordt toegepast op actieve apparaten in deze groep.
Voltooien | De wijziging is voltooid op alle actieve apparaten in deze groep.
Mislukt | De wijziging is mislukt op een 10 procent van de actieve apparaten in de groep, dus de implementatie is gestopt.<br><br> Er wordt automatisch een ondersteuningsaanvraag geopend met Microsoft Managed Desktop om de implementatie op te lossen.
Teruggevormd | De wijziging is teruggezet naar de laatste wijziging die is geïmplementeerd voor alle implementatiegroepen.

## <a name="deploy-changes"></a>Wijzigingen implementeren

In deze instructies wordt een bureaubladachtergrondafbeelding weergeven. Nadat u een implementatie hebt gefaseerd, implementeert u wijzigingen vanaf de pagina Implementatiestatus.

**Wijzigingen implementeren**

1. Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar **het** menu Apparaten
2. Zoek naar de Microsoft Managed Desktop sectie en selecteer **Instellingen.**
3. Selecteer **in de werkruimte** Implementatiestatus de instelling die u wilt implementeren en selecteer vervolgens de gefaseerd implementatie die u wilt implementeren.
4. Selecteer **Implementeren** om de wijziging te implementeren in een van de implementatiegroepen.

> [!NOTE]
> Het oranje waarschuwingspictogram geeft aan dat er een vorige groep beschikbaar is voor implementatie, omdat het wordt aanbevolen om deze in volgorde uit te rollen.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

We raden u aan om in deze volgorde te implementeren voor implementatiegroepen: Test, First, Fast en vervolgens Broad. 

Wanneer wijzigingen in elke groep zijn voltooid, wordt de status gewijzigd in **Voltooid.**

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Implementatie terugdraaien

Nadat u een wijziging hebt geïmplementeerd, kunt u terugkeren van de **implementatiestatus.** Wanneer u een wijziging die In uitvoering **of** Voltooid **is,** terugzet, wordt de huidige implementatie gestopt. De instelling wordt terug naar de laatste versie die is geïmplementeerd voor alle groepen.

We laten de stappen zien om een wijziging terug te zetten met de achtergrondafbeelding bureaublad als voorbeeld. 

**Een wijziging terugdraaien**

1. Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar **het** menu Apparaten
2. Zoek naar de Microsoft Managed Desktop sectie en selecteer **Instellingen.**
3. Selecteer **in de** werkruimte Implementatiestatus de instelling die u wilt terugdraaien en selecteer vervolgens de gefaseerd implementatie die u wilt terugdraaien.
4. Selecteer **onder Wilt u deze wijziging terugdraaien?** de optie Implementatie **terugdraaien.**

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Aanvullende bronnen

- [Overzicht van configureerbare instellingen](config-setting-overview.md)
- [Verwijzing naar configureerbare instellingen](config-setting-ref.md) 
