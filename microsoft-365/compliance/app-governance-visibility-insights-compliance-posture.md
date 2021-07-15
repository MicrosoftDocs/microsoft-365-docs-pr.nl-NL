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
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="cd7c6-103">Bepaal jouw compliance-houding</span><span class="sxs-lookup"><span data-stu-id="cd7c6-103">Determine your app compliance posture</span></span>

><span data-ttu-id="cd7c6-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="cd7c6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="cd7c6-105">Met Microsoft-app-governance kan je snel toegang krijgen tot de compliance-houding van externe apps en hun toegang tot gegevens in de Microsoft 365-tenant uit de overzichtpagina van de app-governance in het [Microsoft 365-compliancecentrum](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="cd7c6-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://aka.ms/appgovernance).</span></span>

![De overzichtpagina van de app-governance in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="cd7c6-107">Het aanmeldingsaccount moet één van [deze rollen](app-governance-get-started.md#administrator-roles) hebben om app-governancegegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="cd7c6-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="cd7c6-108">Op deze pagina kan je het volgende bekijken:</span><span class="sxs-lookup"><span data-stu-id="cd7c6-108">From this page, you can see:</span></span>

- <span data-ttu-id="cd7c6-109">Voor apps met OAuth die gebruik maken van Microsoft Graph API:</span><span class="sxs-lookup"><span data-stu-id="cd7c6-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="cd7c6-110">Hoeveel zijn er in de tenant</span><span class="sxs-lookup"><span data-stu-id="cd7c6-110">How many are in your tenant</span></span>
  - <span data-ttu-id="cd7c6-111">Hoeveel hebben er te veel machtigingen</span><span class="sxs-lookup"><span data-stu-id="cd7c6-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="cd7c6-112">Hoeveel hebben er hoge bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="cd7c6-112">How many are high privilege</span></span>

  <span data-ttu-id="cd7c6-113">Op basis van deze informatie kan je het risiconiveau bepalen voor jouw organisatie volgens apps met te veel machtigingen en hoge bevoegdheid.</span><span class="sxs-lookup"><span data-stu-id="cd7c6-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="cd7c6-114">Voor waarschuwingen:</span><span class="sxs-lookup"><span data-stu-id="cd7c6-114">For alerts:</span></span>

  - <span data-ttu-id="cd7c6-115">Hoeveel actieve waarschuwingen heeft de tenant</span><span class="sxs-lookup"><span data-stu-id="cd7c6-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="cd7c6-116">Hoeveel ervan zijn gebaseerd op app-governancedetecties (**Bedreigingswaarschuwingen**)</span><span class="sxs-lookup"><span data-stu-id="cd7c6-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="cd7c6-117">Hoeveel ervan zijn gebaseerd op actief app-beleid (**Beleidswaarschuwingen**)</span><span class="sxs-lookup"><span data-stu-id="cd7c6-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="cd7c6-118">De laatste 10 waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="cd7c6-118">The 10 latest alerts</span></span>

  <span data-ttu-id="cd7c6-119">Op basis van deze informatie kan je bepalen hoe snel waarschuwingen worden gegenereerd en het relatief aantal van gedetecteerde beleidswaarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="cd7c6-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="cd7c6-120">Voor toegang tot gegevens en resources:</span><span class="sxs-lookup"><span data-stu-id="cd7c6-120">For data and resources access:</span></span>

  - <span data-ttu-id="cd7c6-121">De toegang tot API-gegevens van de toepassing in de afgelopen 90 dagen</span><span class="sxs-lookup"><span data-stu-id="cd7c6-121">The application API data access in the last 90 days</span></span>
  - <span data-ttu-id="cd7c6-122">Het gebruik van de belangrijkste resources in de afgelopen 90 dagen</span><span class="sxs-lookup"><span data-stu-id="cd7c6-122">The usage of the top resources in the last 90 days</span></span>

  <span data-ttu-id="cd7c6-123">Op basis van deze informatie kan je bepalen of er ongewone pieken zijn in de toegang tot de gegevens in de Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="cd7c6-123">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
