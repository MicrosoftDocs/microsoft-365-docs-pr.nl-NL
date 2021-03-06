---
title: Microsoft Defender voor endpoint-onderdrukkingsregels beheren
description: Mogelijk moet u voorkomen dat waarschuwingen in de portal worden weergegeven met behulp van onderdrukkingsregels. Meer informatie over het beheren van uw onderdrukkingsregels in Microsoft Defender voor Eindpunt.
keywords: onderdrukken, regels, regelnaam, bereik, actie, waarschuwingen beheren, in- en uitschakelen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 74b89d86b770cb47a0855b45d457ea8ce5fb9802
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454755"
---
# <a name="manage-suppression-rules"></a>Onderdrukkende regels beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Er kunnen scenario's zijn waarin u waarschuwingen wilt onderdrukken die worden weergegeven in de portal. U kunt onderdrukkingsregels maken voor specifieke waarschuwingen die onschadelijk zijn, zoals bekende hulpmiddelen of processen in uw organisatie. Zie Waarschuwingen onderdrukken voor meer informatie over het onderdrukken [van waarschuwingen.](manage-alerts.md)

U kunt een lijst met alle onderdrukkingsregels weergeven en deze op één plaats beheren. U kunt ook een regel voor het onderdrukken van waarschuwingen in- of uitschakelen.


1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **endpoints**  >  **Rules**  >  **Alert suppression**. De lijst met onderdrukkingsregels die gebruikers in uw organisatie hebben gemaakt, wordt weergegeven.

2. Selecteer een regel door op het selectievakje naast de naam van de regel te klikken.

3. Klik **op Regel in-,** **Regel bewerken of** Regel  **verwijderen**. Wanneer u wijzigingen aan een regel aan brengt, kunt u ervoor kiezen om waarschuwingen vrij te geven die al zijn onderdrukt, ongeacht of deze waarschuwingen voldoen aan de nieuwe criteria. 


## <a name="view-details-of-a-suppression-rule"></a>Details van een onderdrukkingsregel weergeven

1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **endpoints**  >  **Rules**  >  **Alert suppression**. De lijst met onderdrukkingsregels die gebruikers in uw organisatie hebben gemaakt, wordt weergegeven.

2. Klik op een regelnaam. Details van de regel worden weergegeven. U ziet de regeldetails, zoals status, bereik, actie, aantal overeenkomende waarschuwingen, gemaakt op en datum waarop de regel is gemaakt. U kunt ook gekoppelde waarschuwingen en de regelvoorwaarden bekijken.

## <a name="related-topics"></a>Gerelateerde onderwerpen

- [Waarschuwingen beheren](manage-alerts.md)
