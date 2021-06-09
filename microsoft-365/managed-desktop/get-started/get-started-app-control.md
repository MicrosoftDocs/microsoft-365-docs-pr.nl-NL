---
title: Aan de slag met App-beheer
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430457"
---
# <a name="get-started-with-app-control"></a>Aan de slag met App-beheer

Voordat u app-beheer in uw omgeving inschakelen, moet u controleren en begrijpen [hoe Microsoft Managed Desktop](../service-description/app-control.md) implementeert en uw rollen en verantwoordelijkheden.

Microsoft Managed Desktop vereenvoudigt de besturing van apps door te zorgen voor de meer uitdagende aspecten van het verkrijgen van een veilig basisbeleid. Uw IT-beheerders moeten uw apps nog steeds testen in de ring Testen en de logboeken controleren op eventuele waarschuwingen of fouten. Als een app een uitzondering nodig heeft, kunt u een aanvraag indienen of Microsoft Managed Desktop, afhankelijk van wie de app het eerst detecteert.

## <a name="initial-deployment-of-apps"></a>Eerste implementatie van apps

Wanneer u apps voor het eerst implementeert, Microsoft Managed Desktop moet u hun huidige gedrag beoordelen. De exacte stappen voor het inschakelen van app-besturingselementen zijn afhankelijk van of apparaten al in uw omgeving zijn geïmplementeerd.

### <a name="devices-not-yet-in-use"></a>Apparaten die nog niet in gebruik zijn

Als u nog geen apparaten in gebruik hebt, opent u een serviceticket met Microsoft Managed Desktop Operations waarin u wordt gevraagd om app-besturingselement in te zetten. In Operations worden beleidsregels geleidelijk geïmplementeerd voor implementatiegroepen volgens deze planning:

|Implementatiegroep  |Beleidstype  |Tijdsinstellingen  |
|---------|---------|---------|
|Test     |  Controle       |  Dag 0       |
|Eerst     | Afgedwongen        | Dag 1        |
|Snel     | Afgedwongen        |  Dag 2       |
|Breed     | Afgedwongen        |  Dag 3       |

U kunt altijd een andere serviceaanvraag openen om een deel van deze implementatie op elk moment tijdens de implementatie te onderbreken of terug te draaien.

### <a name="devices-already-in-use"></a>Apparaten die al in gebruik zijn

Als er al ten minste één apparaat Microsoft Managed Desktop gebruikt, volgt u de volgende stappen:

1. Open een serviceticket met Microsoft Managed Desktop operations die vragen om app-besturingselement in te zetten. Operations implementeert een [auditbeleid](../service-description/app-control.md#audit-policy) op alle apparaten.
2. [Test uw toepassingen](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) om te zien of deze worden geblokkeerd. Als een toepassing wordt geblokkeerd, opent u een [aanmeldingsaanvraag.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer) 
3. Nadat u het testen hebt voltooid (ongeacht de resultaten), meldt u Operations, met de melding van aanvragen voor in behandeling zijnde ondertekenaars. In Operations worden beleidsregels geleidelijk geïmplementeerd voor implementatiegroepen volgens deze planning:

|Implementatiegroep  |Beleidstype  |Tijdsinstellingen  |
|---------|---------|---------|
|Test     |  Controle       |  Dag 0       |
|Eerst     | Afgedwongen        | Dag 1        |
|Snel     | Afgedwongen        |  Onderbroken, uitrol op aanvraag       |
|Breed     | Afgedwongen        |  Onderbroken, uitrol op aanvraag       |

U kunt altijd een andere serviceaanvraag openen om een deel van deze implementatie op elk moment tijdens de implementatie te onderbreken of terug te draaien.



