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
# <a name="learn-about-app-policies"></a><span data-ttu-id="51a2a-103">Informatie over app-beleid</span><span class="sxs-lookup"><span data-stu-id="51a2a-103">Learn about app policies</span></span>

><span data-ttu-id="51a2a-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="51a2a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="51a2a-105">Microsoft app governance detecteert afwijkend app-gedrag in uw Microsoft 365 tenant en genereert waarschuwingen die u kunt zien, onderzoeken en oplossen.</span><span class="sxs-lookup"><span data-stu-id="51a2a-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="51a2a-106">Naast deze ingebouwde detectiemogelijkheid kunt u een set standaardsjablonen gebruiken om uw eigen app-beleid te maken waarmee andere waarschuwingen worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="51a2a-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="51a2a-107">Dit beleid voor app- en gebruikerspatronen en -gedrag en beschermt uw gebruikers tegen het gebruik van niet-conforme of schadelijke apps en beperkt de toegang van risicovolle apps tot uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="51a2a-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="51a2a-108">Hier is een kort overzicht van de vereiste beheerdersrollen voor app-beleidsbeheer.</span><span class="sxs-lookup"><span data-stu-id="51a2a-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="51a2a-109">Rol</span><span class="sxs-lookup"><span data-stu-id="51a2a-109">Role</span></span> | <span data-ttu-id="51a2a-110">Beleid lezen</span><span class="sxs-lookup"><span data-stu-id="51a2a-110">Read policies</span></span> | <span data-ttu-id="51a2a-111">Beleid maken, bijwerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="51a2a-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="51a2a-112">Beheerder voor naleving</span><span class="sxs-lookup"><span data-stu-id="51a2a-112">Compliance Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| <span data-ttu-id="51a2a-115">Nalevingslezer</span><span class="sxs-lookup"><span data-stu-id="51a2a-115">Compliance Reader</span></span> | ![Vinkje](..\media\checkmark.png) |  |
| <span data-ttu-id="51a2a-117">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="51a2a-117">Global Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| <span data-ttu-id="51a2a-120">Globale lezer</span><span class="sxs-lookup"><span data-stu-id="51a2a-120">Global Reader</span></span>  | ![Vinkje](..\media\checkmark.png) |  |
| <span data-ttu-id="51a2a-122">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="51a2a-122">Security Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| <span data-ttu-id="51a2a-125">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="51a2a-125">Security Reader</span></span>  | ![Vinkje](..\media\checkmark.png) |  |
| <span data-ttu-id="51a2a-127">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="51a2a-127">Security Operator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
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

## <a name="next-step"></a><span data-ttu-id="51a2a-130">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="51a2a-130">Next step</span></span>

[<span data-ttu-id="51a2a-131">Aan de slag met app-beleid.</span><span class="sxs-lookup"><span data-stu-id="51a2a-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
