---
title: Interoperabiliteit OneDrive Learning hulpprogramma's gebruiken
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Maak opdrachten en cijfertoewijzingen, bouw en beheer cursusinhoud en werk in realtime samen aan bestanden met de nieuwe OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256952"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>LTI Microsoft OneDrive canvas gebruiken

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

## <a name="integrate-with-canvas"></a>Integreren met Canvas

De persoon die deze integratie uitvoert, moet een beheerder van Canvas zijn en een beheerder van de Microsoft 365 tenant.

1. Meld u aan bij de Microsoft Azure portal met het tenantbeheerderaccount. De Azure-tenantbeheerder moet ook de rol groepsbeheerder hebben.

    ![groepsbeheerder gemarkeerd](../media/lti-media/lti-group-admin.png)

2. Meld u aan bij de Microsoft [OneDrive LTI-portal](https://odltiappnl.azurewebsites.net/admin).

3. Accepteer de machtigingen om de aanmelding te voltooien.

    ![machtigingen accepteren](../media/lti-media/lti-permissions.png)

4. Selecteer **LTI-tenant toevoegen.**

     ![LTI-tenant toevoegen](../media/lti-media/lti-add-tenant.png)

5. Selecteer **LTI Consumer Platform** als **Canvas** in de vervolgkeuzekeuze.

6. Selecteer **Canvas Base URL** en selecteer vervolgens **Volgende**.

    ![canvas selecteren en basis-URL toevoegen](../media/lti-media/lti-canvas-base-url.png)

   In het volgende scherm ziet u velden die vertrouwelijk voor u zijn.

7. Selecteer **Volgende** van ?? (U bent bijna klaar). KUNNEN REVISOREN DE LEGE HIER INVULLEN?

8. Selecteer **Volgende** in het scherm met informatie die vertrouwelijk voor u is.

   In het laatste scherm van de Azure-portal ziet u de volgende stappen voor het toevoegen van uw Canvas-exemplaar.

9. Kopieer de ontwikkelaarssleutels vanuit dit scherm. U wordt gebruikt wanneer u het canvas-exemplaar maakt.

## <a name="add-the-canvas-instance"></a>Het canvas-exemplaar toevoegen

1. Schakel in het canvas-exemplaar **deselecteer**  >  **beheerdersontwikkelaarssleutels uit.**

2. Kies **LTI-toets** in de vervolgkeuzekeuze op **Ontwikkelaarssleutel.**

   ![De LTI-ontwikkelaarssleutels ophalen](../media/lti-media/lti-developer-keys.png)

3. Plak de ontwikkelaarssleutels hier.

     ![De ontwikkelaarssleutels plakken](../media/lti-media/lti-developer-keys.png)

   De sleutel wordt gemaakt in **de UIT-modus**

   ![De gemaakte ontwikkelaarssleutels in de uit-modus](../media/lti-media/lti-copy-developer-keys.png)

4. Kopieer de gemarkeerde tekst.
    Dit fungeert als client-id in Microsoft OneDrive LTI-portal.

5. Plak de tekst in het **veld Client-id** in Microsoft OneDrive LTI-portal en selecteer **volgende**.

6. Selecteer **Opslaan**.

7. Bekijk de instellingen door **LTI-tenants weergeven te selecteren.**
