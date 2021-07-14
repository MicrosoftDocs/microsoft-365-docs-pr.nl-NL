---
title: Bepaal jouw compliance-houding
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Bepaal jouw compliance-houding.
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420060"
---
# <a name="determine-your-app-compliance-posture"></a>Bepaal jouw compliance-houding

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

Met Microsoft-app-governance kan je snel toegang krijgen tot de compliance-houding van externe apps en hun toegang tot gegevens in de Microsoft 365-tenant uit de overzichtpagina van de app-governance in het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/appgovernance).

![De overzichtpagina van de app-governance in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> Het aanmeldingsaccount moet één van [deze rollen](app-governance-get-started.md#administrator-roles) hebben om app-governancegegevens weer te geven.
>

Op deze pagina kan je het volgende bekijken:

- Voor apps met OAuth die gebruik maken van Microsoft Graph API:

  - Hoeveel zijn er in de tenant
  - Hoeveel hebben er te veel machtigingen
  - Hoeveel hebben er hoge bevoegdheid

  Op basis van deze informatie kan je het risiconiveau bepalen voor jouw organisatie volgens apps met te veel machtigingen en hoge bevoegdheid.

- Voor waarschuwingen:

  - Hoeveel actieve waarschuwingen heeft de tenant
  - Hoeveel ervan zijn gebaseerd op app-governancedetecties (**Bedreigingswaarschuwingen**)
  - Hoeveel ervan zijn gebaseerd op actief app-beleid (**Beleidswaarschuwingen**)
  - De laatste 10 waarschuwingen

  Op basis van deze informatie kan je bepalen hoe snel waarschuwingen worden gegenereerd en het relatief aantal van gedetecteerde beleidswaarschuwingen.

- Voor toegang tot gegevens en resources:

  - De toegang tot API-gegevens van de toepassing in de afgelopen 90 dagen
  - Het gebruik van de belangrijkste resources in de afgelopen 90 dagen

  Op basis van deze informatie kan je bepalen of er ongewone pieken zijn in de toegang tot de gegevens in de Microsoft 365-tenant.
