---
title: Isolatiebesturingselementen voor Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lees hoe isolatiebesturingselementen werken binnen Microsoft 365, zodat services zo nodig kunnen samenwerken of zelfstandig kunnen blijven.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918940"
---
# <a name="microsoft-365-isolation-controls"></a>Isolatiebesturingselementen voor Microsoft 365 

Microsoft werkt voortdurend om ervoor te zorgen dat de architectuur met meerdere tenants van Microsoft 365 ondersteuning biedt voor beveiliging, vertrouwelijkheid, privacy, integriteit, lokale, internationale en beschikbaarheidsstandaarden op [ondernemingsniveau.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) De schaal en het bereik van services die door Microsoft worden geleverd, maken het moeilijk en niet-voordelig om Microsoft 365 te beheren met een aanzienlijke menselijke interactie. Microsoft 365-services worden geleverd via meerdere wereldwijd gedistribueerde datacenters, elk zeer geautomatiseerd met weinig bewerkingen waarvoor een menselijke aanraking of toegang tot klantinhoud vereist is. Ons personeel ondersteunt deze services en datacenters met behulp van geautomatiseerde hulpprogramma's en zeer veilige toegang op afstand. 

Microsoft 365 bestaat uit meerdere services die belangrijke bedrijfsfunctionaliteit bieden en bijdragen aan de volledige Microsoft 365-ervaring. Elk van deze services is op zichzelf staand en ontworpen om met elkaar te integreren.

Microsoft 365 is ontworpen met de volgende principes:

 - **[Servicegeoriënteerde architectuur:](/previous-versions/aa480021(v=msdn.10))** software ontwerpen en ontwikkelen in de vorm van interoperabele services die goed gedefinieerde bedrijfsfunctionaliteit bieden.
 - **[Operational Security Assurance:](https://www.microsoft.com/download/details.aspx?id=40872)** een framework met de kennis die is opgedane via verschillende mogelijkheden die uniek zijn voor Microsoft, waaronder de levenscyclus van Microsoft [Security Development,](https://www.microsoft.com/sdl/default.aspx)het [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)en een uitgebreide kennis van het landschap van cyberbeveiligingsdreigingen.

Microsoft 365-services werken onderling, maar zijn ontworpen en geïmplementeerd, zodat ze onafhankelijk van elkaar kunnen worden geïmplementeerd en beheerd als zelfstandige services. Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets. Microsoft 365-teams hebben rollen gedefinieerd als onderdeel van een uitgebreid toegangsbeheermechanisme op basis van rollen.

## <a name="customer-content-isolation"></a>Isolatie van klantinhoud

Alle klantinhoud in een tenant is geïsoleerd van andere tenants en van bewerkingen en systeemgegevens die worden gebruikt in het beheer van Microsoft 365. Er worden meerdere vormen van beveiliging geïmplementeerd in Microsoft 365 om het risico op compromitteerd gebruik van een Microsoft 365-service of -toepassing tot een minimum te beperken. Meerdere vormen van beveiliging voorkomen ook dat onbevoegden toegang hebben tot de gegevens van tenants of het Microsoft 365-systeem zelf.

Zie Tenant Isolation in Microsoft 365 voor informatie over hoe Microsoft logische isolatie van tenantgegevens implementeert in Microsoft [365.](microsoft-365-tenant-isolation-overview.md)