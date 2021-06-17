---
title: Aanvullende informatie voor cloudoplossingsproviders
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Overzicht: Aanvullende informatie voor cloudoplossingsproviders die relevant zijn voor de migratie van Microsoft Cloud Deutschland.'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984914"
---
# <a name="additional-information-for-cloud-solution-providers"></a>Aanvullende informatie voor cloudoplossingsproviders

Cloud Solution Providers (CSP's) die klanten ondersteunen, moeten extra stappen ondernemen tijdens de migratie van Microsoft Cloud Deutschland naar de nieuwe Duitse datacenterregio.

## <a name="partner-tenant-migration"></a>Migratie van partner tenant

Partner Microsoft Cloud Deutschland-tenants worden niet gemigreerd. In plaats daarvan wordt een nieuwe Office 365 services tenant gemaakt voor elke Microsoft-partner in de nieuwe Duitse datacenterregio.

CSP-klantten tenants worden gemigreerd naar de nieuwe Duitse datacenterregio en worden gekoppeld aan de nieuwe Office 365 servicesten tenant van dezelfde partner. Na de klantovergang kan de partner de klant beheren met de nieuwe Office 365 services tenant in de Duitse datacenterregio.

## <a name="missing-subscriptions-in-azure"></a>Ontbrekende abonnementen in Azure

Nadat [de abonnements- en licentieovergang (fase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) is voltooid, hebben Cloud Solution Providers geen toegang meer tot het Azure-abonnement.

Als u toegang wilt herstellen, volgt u deze stappen om de toegang tot alle Azure-abonnementen en [beheergroepen te verbeteren.](/azure/role-based-access-control/elevate-access-global-admin)
