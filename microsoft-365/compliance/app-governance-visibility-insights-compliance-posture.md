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
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="934e2-103">Bepaal jouw compliance-houding</span><span class="sxs-lookup"><span data-stu-id="934e2-103">Determine your app compliance posture</span></span>

><span data-ttu-id="934e2-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="934e2-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="934e2-105">Met Microsoft-app-governance kan je snel toegang krijgen tot de compliance-houding van externe apps en hun toegang tot gegevens in de Microsoft 365-tenant uit de overzichtpagina van de app-governance in het [Microsoft 365-compliancecentrum](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="934e2-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://aka.ms/appgovernance).</span></span>

![De overzichtpagina van de app-governance in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="934e2-107">Het aanmeldingsaccount moet één van [deze rollen](app-governance-get-started.md#administrator-roles) hebben om app-governancegegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="934e2-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="934e2-108">Op deze pagina kan je het volgende bekijken:</span><span class="sxs-lookup"><span data-stu-id="934e2-108">From this page, you can see:</span></span>

- <span data-ttu-id="934e2-109">Voor apps met OAuth die gebruik maken van Microsoft Graph API:</span><span class="sxs-lookup"><span data-stu-id="934e2-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="934e2-110">Hoeveel zijn er in de tenant</span><span class="sxs-lookup"><span data-stu-id="934e2-110">How many are in your tenant</span></span>
  - <span data-ttu-id="934e2-111">Hoeveel hebben er te veel machtigingen</span><span class="sxs-lookup"><span data-stu-id="934e2-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="934e2-112">Hoeveel hebben er hoge bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="934e2-112">How many are high privilege</span></span>

  <span data-ttu-id="934e2-113">Op basis van deze informatie kan je het risiconiveau bepalen voor jouw organisatie volgens apps met te veel machtigingen en hoge bevoegdheid.</span><span class="sxs-lookup"><span data-stu-id="934e2-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="934e2-114">Voor waarschuwingen:</span><span class="sxs-lookup"><span data-stu-id="934e2-114">For alerts:</span></span>

  - <span data-ttu-id="934e2-115">Hoeveel actieve waarschuwingen heeft de tenant</span><span class="sxs-lookup"><span data-stu-id="934e2-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="934e2-116">Hoeveel ervan zijn gebaseerd op app-governancedetecties (**Bedreigingswaarschuwingen**)</span><span class="sxs-lookup"><span data-stu-id="934e2-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="934e2-117">Hoeveel ervan zijn gebaseerd op actief app-beleid (**Beleidswaarschuwingen**)</span><span class="sxs-lookup"><span data-stu-id="934e2-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="934e2-118">De laatste 10 waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="934e2-118">The 10 latest alerts</span></span>

  <span data-ttu-id="934e2-119">Op basis van deze informatie kan je bepalen hoe snel waarschuwingen worden gegenereerd en het relatief aantal van gedetecteerde beleidswaarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="934e2-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="934e2-120">Voor toegang tot gegevens en resources:</span><span class="sxs-lookup"><span data-stu-id="934e2-120">For data and resources access:</span></span>

  - <span data-ttu-id="934e2-121">Totaal gegevens dat door apps in de tenant is geopend via Graph API in de huidige en vorige drie kalendermaanden.</span><span class="sxs-lookup"><span data-stu-id="934e2-121">Total data accessed by apps in the tenant through Graph API over the current and previous three calendar months.</span></span> <span data-ttu-id="934e2-122">(Bevat momenteel alleen verbruik voor uploaden en downloaden van e-mail en bestanden)</span><span class="sxs-lookup"><span data-stu-id="934e2-122">(Currently only includes Mail and File upload and download usage)</span></span>
  - <span data-ttu-id="934e2-123">Dataverbruik in de huidige en vorige drie kalendermaanden, opgesplitst per resourcetype.</span><span class="sxs-lookup"><span data-stu-id="934e2-123">Data usage over the current and previous three calendar months, broken down by resource type.</span></span> <span data-ttu-id="934e2-124">(Bevat momenteel alleen verbruik voor uploaden en downloaden van e-mail en bestanden)</span><span class="sxs-lookup"><span data-stu-id="934e2-124">(Currently only includes Mail and File upload and download usage)</span></span>

  <span data-ttu-id="934e2-125">Op basis van deze informatie kan je bepalen of er ongewone pieken zijn in de toegang tot de gegevens in de Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="934e2-125">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>