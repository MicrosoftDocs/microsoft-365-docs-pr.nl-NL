---
title: Informatie over app-beleid
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
description: Informatie over app-beleid.
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420187"
---
# <a name="learn-about-app-policies"></a>Informatie over app-beleid

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

Microsoft app governance detecteert afwijkend app-gedrag in uw Microsoft 365 tenant en genereert waarschuwingen die u kunt zien, onderzoeken en oplossen. Naast deze ingebouwde detectiemogelijkheid kunt u een set standaardsjablonen gebruiken om uw eigen app-beleid te maken waarmee andere waarschuwingen worden gegenereerd.

Dit beleid voor app- en gebruikerspatronen en -gedrag en beschermt uw gebruikers tegen het gebruik van niet-conforme of schadelijke apps en beperkt de toegang van risicovolle apps tot uw gegevens.

Hier is een kort overzicht van de vereiste beheerdersrollen voor app-beleidsbeheer.

| Rol | Beleid lezen | Beleid maken, bijwerken of verwijderen |
|:-------|:-----|:-------|
| Beheerder voor naleving | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| Nalevingslezer | ![Vinkje](..\media\checkmark.png) |  |
| Globale beheerder | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| Globale lezer  | ![Vinkje](..\media\checkmark.png) |  |
| Beveiligingsbeheerder | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| Beveiligingslezer  | ![Vinkje](..\media\checkmark.png) |  |
| Beveiligingsoperator | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a>Volgende stap

[Aan de slag met app-beleid.](app-governance-app-policies-get-started.md)
