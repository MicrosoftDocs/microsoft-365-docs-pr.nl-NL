---
title: Apparaatnamen
description: Hoe Microsoft Managed Desktop apparaatnamen beheert
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893774"
---
# <a name="device-names"></a>Apparaatnamen

Microsoft Managed Desktop gebruikt Windows Autopilot, Azure Active Directory en Microsoft Intune. Om deze services naadloos samen te laten werken, hebben apparaten consistente, gestandaardiseerde namen nodig. Microsoft Managed Desktop past een gestandaardiseerde naamnotatie toe (van het formulier *MMD-%RAND11)* wanneer apparaten zijn geregistreerd. Deze namen worden toegewezen door Windows Autopilot. Zie [First-run experience with Autopilot and the Enrollment Status Page (First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md)) voor meer informatie over Autopilot.

## <a name="automated-name-changes"></a>Geautomatiseerde naamwijzigingen

Als de naam van een apparaat later wordt gewijzigd, wordt de naam van een apparaat automatisch gewijzigd in een nieuwe naam in de gestandaardiseerde indeling. Dit proces vindt elke vier uur plaats. De naamswijziging vindt plaats de volgende keer dat de gebruiker het apparaat opnieuw start.

> [!IMPORTANT]
> Als uw omgeving afhankelijk is van specifieke apparaatnamen (bijvoorbeeld om een bepaalde netwerkconfiguratie te ondersteunen), moet u opties onderzoeken om die afhankelijkheid te verwijderen voordat u zich inschrijft bij Microsoft Managed Desktop. Als u de naamafhankelijkheid moet behouden, kunt u een aanvraag indienen via de [beheerportal](../working-with-managed-desktop/admin-support.md) om de naamswijzigingsfunctie uit te schakelen en de gewenste naamnotatie te gebruiken.