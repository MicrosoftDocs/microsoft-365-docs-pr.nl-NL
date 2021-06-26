---
title: Meer informatie over het standaard preventiebeleid voor gegevensverlies in Microsoft Teams (preview)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Meer informatie over het standaardbeleid voor preventie van gegevensverlies in Microsoft Teams
ms.openlocfilehash: c6b7413fdd4017fe1211e804c00a2e9c0684468d
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149116"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="4b680-103">Meer informatie over het standaard preventiebeleid voor gegevensverlies in Microsoft Teams (preview)</span><span class="sxs-lookup"><span data-stu-id="4b680-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="4b680-104">[De mogelijkheden voor preventie van](dlp-learn-about-dlp.md) gegevensverlies zijn uitgebreid met Microsoft Teams chat- en kanaalberichten, inclusief privékanaalberichten.</span><span class="sxs-lookup"><span data-stu-id="4b680-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="4b680-105">Als onderdeel van deze release hebben we een standaard DLP-beleid gemaakt voor Microsoft Teams klanten die voor het eerst naar het Compliancecentrum gaan.</span><span class="sxs-lookup"><span data-stu-id="4b680-105">As a part of this release, we created a default DLP policy for Microsoft Teams for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="4b680-106">Van toepassing op</span><span class="sxs-lookup"><span data-stu-id="4b680-106">Applies to</span></span>

<span data-ttu-id="4b680-107">Elke tenant die een licentie heeft met een of meer van de onderstaande licenties en actieve gebruikers Teams gebruiken</span><span class="sxs-lookup"><span data-stu-id="4b680-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="4b680-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="4b680-108">ME5,</span></span> 
- <span data-ttu-id="4b680-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="4b680-109">MA5,</span></span> 
- <span data-ttu-id="4b680-110">E5/A5 Compliance,</span><span class="sxs-lookup"><span data-stu-id="4b680-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="4b680-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="4b680-111">IP+G,</span></span> 
- <span data-ttu-id="4b680-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="4b680-112">OE5,</span></span> 
- <span data-ttu-id="4b680-113">O365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="4b680-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="4b680-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="4b680-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="4b680-115">Wat doet het standaardbeleid?</span><span class="sxs-lookup"><span data-stu-id="4b680-115">What does the default policy do?</span></span>

<span data-ttu-id="4b680-116">Het standaard DLP-beleid voor Teams houdt alle creditcardnummers bij die intern en extern worden gedeeld met de organisatie.</span><span class="sxs-lookup"><span data-stu-id="4b680-116">The default DLP policy for Teams tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="4b680-117">Dit beleid is standaard ingeschakeld voor alle gebruikers van de tenant.</span><span class="sxs-lookup"><span data-stu-id="4b680-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="4b680-118">Het genereert geen beleidstips voor eindgebruikers, maar genereert wel een waarschuwingsgebeurtenis en activeert ook een e-mail met een lage ernst naar de beheerder (toegevoegd aan het beleid).</span><span class="sxs-lookup"><span data-stu-id="4b680-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="4b680-119">Beheerder kan de activiteiten bekijken en de beleidsdetails bewerken door u aan te melden bij het Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="4b680-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="4b680-120">Beheerders kunnen dit beleid bekijken in het [compliancecentrum](https://compliance.microsoft.com/compliancesettings) > pagina Preventiebeleid voor gegevensverlies.</span><span class="sxs-lookup"><span data-stu-id="4b680-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b680-121">![standaard Teams DLP-beleid](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="4b680-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="4b680-122">Het standaardbeleid bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="4b680-122">Edit or delete the default policy</span></span>

<span data-ttu-id="4b680-123">Als [u het standaardbeleid wilt bewerken voor betere prestaties](create-test-tune-dlp-policy.md#tune-a-dlp-policy)of om het te verwijderen, gebruikt u een account met **DLP Compliance Management-machtigingen.**</span><span class="sxs-lookup"><span data-stu-id="4b680-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="4b680-124">Zie Machtigingen [voor meer informatie.](create-test-tune-dlp-policy.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="4b680-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

