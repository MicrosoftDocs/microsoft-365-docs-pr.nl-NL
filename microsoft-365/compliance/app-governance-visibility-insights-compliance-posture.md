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
ms.openlocfilehash: 2fde19e385d4797e04c8f991efa673d33cea3b58
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430670"
---
# <a name="determine-your-app-compliance-posture"></a>Bepaal jouw compliance-houding

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

Met Microsoft-app-governance kan je snel toegang krijgen tot de compliance-houding van externe apps en hun toegang tot gegevens in de Microsoft 365-tenant uit de overzichtpagina van de app-governance in het [Microsoft 365-compliancecentrum](https://aka.ms/appgovernance).

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
