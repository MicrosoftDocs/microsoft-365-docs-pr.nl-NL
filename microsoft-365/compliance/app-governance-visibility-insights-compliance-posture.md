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
ms.openlocfilehash: 152f68e8fe0e7d7340d2e048bc73684bc079386f
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438022"
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

  - Totaal gegevens dat door apps in de tenant is geopend via Graph API in de huidige en vorige drie kalendermaanden. (Bevat momenteel alleen verbruik voor uploaden en downloaden van e-mail en bestanden)
  - Dataverbruik in de huidige en vorige drie kalendermaanden, opgesplitst per resourcetype. (Bevat momenteel alleen verbruik voor uploaden en downloaden van e-mail en bestanden)

  Op basis van deze informatie kan je bepalen of er ongewone pieken zijn in de toegang tot de gegevens in de Microsoft 365-tenant.
