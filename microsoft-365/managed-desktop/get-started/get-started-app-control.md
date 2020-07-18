---
title: Aan de slag met app-besturingselement
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170693"
---
# <a name="get-started-with-app-control"></a>Aan de slag met app-besturingselement

Voordat u app-controle in uw omgeving inschakelt, moet u controleren en begrijpen [hoe Microsoft Managed Desktop deze implementeert](../service-description/app-control.md) en uw rollen en verantwoordelijkheden.

Microsoft Managed Desktop vereenvoudigt de app-controle door te zorgen voor de meer uitdagende aspecten van het verkrijgen van een veilig basisbeleid. Uw IT-beheerders moeten uw apps nog steeds testen in de testring en de logboeken controleren op eventuele waarschuwingen of fouten. Als een app een vrijstelling nodig heeft, u een aanvraag indienen of microsoft Managed Desktop Operation mogelijk, afhankelijk van wie deze eerst detecteert.

## <a name="initial-deployment-of-apps"></a>Eerste implementatie van apps

Wanneer u apps voor het eerst implementeert, moet Microsoft Managed Desktop hun huidige gedrag beoordelen. De exacte stappen voor het inschakelen van app-besturingselementen zijn afhankelijk van de vraag of apparaten al in uw omgeving zijn geïmplementeerd.

### <a name="devices-already-in-use"></a>Apparaten die al in gebruik zijn

Als u al ten minste één Microsoft Managed Desktop-apparaat in gebruik hebt, voert u de volgende stappen uit:

1. Open een serviceticket met Microsoft Managed Desktop Operations met het verzoek om app-besturingselement in te schakelen. Operations implementeert een [auditbeleid](../service-description/app-control.md#audit-policy) op alle apparaten.
2. [Test uw toepassingen](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) om te zien of deze worden geblokkeerd. Als een toepassing wordt geblokkeerd, opent u een [aanvraag voor ondertekenaar](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Zodra u uw tests hebt voltooid (ongeacht de resultaten), stelt u Operations hiervan op de hoogte en noteer u eventuele in behandeling zijnde ondertekenaarverzoeken. Operations implementeert geleidelijk beleid naar implementatiegroepen volgens deze planning:

|Implementatiegroep  |Beleidstype  |Timing  |
|---------|---------|---------|
|Test     |  Audit       |  Dag 0       |
|Eerste     | Afgedwongen        | Dag 1        |
|Snel     | Afgedwongen        |  Dag 3       |
|Brede     | Afgedwongen        |  Dag 7       |

U altijd een andere serviceaanvraag openen om een deel van deze implementatie op elk gewenst moment tijdens de implementatie te onderbreken of terug te draaien.

### <a name="devices-not-yet-in-use"></a>Apparaten die nog niet in gebruik zijn

Als u nog geen apparaten in gebruik hebt, opent u een serviceticket met Microsoft Managed Desktop Operations met het verzoek om app-besturingselement in te schakelen. Operations implementeert geleidelijk beleid naar implementatiegroepen volgens deze planning:

|Implementatiegroep  |Beleidstype  |Timing  |
|---------|---------|---------|
|Test     |  Audit       |  Dag 0       |
|Eerste     | Afgedwongen        | Dag 1        |
|Snel     | Afgedwongen        |  Dag 3       |
|Brede     | Afgedwongen        |  Dag 7       |

U altijd een andere serviceaanvraag openen om een deel van deze implementatie op elk gewenst moment tijdens de implementatie te onderbreken of terug te draaien.

