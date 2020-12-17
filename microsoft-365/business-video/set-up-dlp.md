---
title: Verlies van gegevens voorkomen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het instellen van beleidsregels voor preventie van gegevensverlies.
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702243"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="944d3-103">Verlies van gegevens met DLP voorkomen</span><span class="sxs-lookup"><span data-stu-id="944d3-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="944d3-104">Met beleidsregels voor preventie van gegevensverlies kunt u de gevoelige informatie van uw bedrijf identificeren en beschermen, zoals sofi-nummers of medische gegevens.</span><span class="sxs-lookup"><span data-stu-id="944d3-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="944d3-105">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="944d3-105">Try it!</span></span>

1. <span data-ttu-id="944d3-106">Als u wilt beginnen, gaat u naar het [Beheercentrum](https://admin.microsoft.com)en selecteert u **Setup**.</span><span class="sxs-lookup"><span data-stu-id="944d3-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="944d3-107">Schuif omlaag naar het **instellen van preventie van gegevensverlies**, selecteer **weergeven** en klik vervolgens op **beheren**.</span><span class="sxs-lookup"><span data-stu-id="944d3-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="944d3-108">Als u een beleid wilt bewerken, selecteert u dit, kiest u **beleid bewerken** en selecteert u wat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="944d3-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="944d3-109">Selecteer bijvoorbeeld **locaties** om te wijzigen wat er wordt gescand.</span><span class="sxs-lookup"><span data-stu-id="944d3-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="944d3-110">Als u het zoeken naar inhoud in Microsoft teams wilt inschakelen, zet u de wisselknop **op aan** en selecteert u vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="944d3-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="944d3-111">Selecteer **bewerken** als u beleidsinstellingen wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="944d3-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="944d3-112">U moet aparte regels instellen die van toepassing zijn op kleine en grote hoeveelheden gevoelige inhoud.</span><span class="sxs-lookup"><span data-stu-id="944d3-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="944d3-113">Vouw de regel voor een laag volume uit.</span><span class="sxs-lookup"><span data-stu-id="944d3-113">Expand your low volume rule.</span></span> <span data-ttu-id="944d3-114">Kies **regel bewerken**.</span><span class="sxs-lookup"><span data-stu-id="944d3-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="944d3-115">Controleer de instellingen en pas deze naar wens aan.</span><span class="sxs-lookup"><span data-stu-id="944d3-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="944d3-116">U kunt bijvoorbeeld kiezen om **de e-mail tekst** aan te passen en **de tiptekst voor het Beleidstip** aan te passen.</span><span class="sxs-lookup"><span data-stu-id="944d3-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="944d3-117">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="944d3-117">Select **Save**.</span></span>
1. <span data-ttu-id="944d3-118">Herhaal dit voor de regel hoog volume.</span><span class="sxs-lookup"><span data-stu-id="944d3-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="944d3-119">Selecteer **Opslaan** en vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="944d3-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="944d3-120">Selecteer **een beleid maken** om een nieuw beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="944d3-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="944d3-121">U kunt een aangepast beleid maken of beginnen met een sjabloon.</span><span class="sxs-lookup"><span data-stu-id="944d3-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="944d3-122">Als u bijvoorbeeld een HIPAA-beleid wilt maken, selecteert u de sjabloon **medisch en gezondheidszorg** en selecteert u vervolgens **US Health Insurance Act (HIPAA)**.</span><span class="sxs-lookup"><span data-stu-id="944d3-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="944d3-123">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="944d3-123">Select **Next**.</span></span>
1. <span data-ttu-id="944d3-124">Voer een naam en beschrijving voor het beleid in.</span><span class="sxs-lookup"><span data-stu-id="944d3-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="944d3-125">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="944d3-125">Select **Next**.</span></span>
1. <span data-ttu-id="944d3-126">Kies de locaties die u wilt scannen.</span><span class="sxs-lookup"><span data-stu-id="944d3-126">Choose the locations to scan.</span></span> <span data-ttu-id="944d3-127">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="944d3-127">Select **Next**.</span></span>
1. <span data-ttu-id="944d3-128">Kies het type inhoud dat u wilt beveiligen.</span><span class="sxs-lookup"><span data-stu-id="944d3-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="944d3-129">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="944d3-129">Select **Next**.</span></span>
1. <span data-ttu-id="944d3-130">Kies wat u wilt doen als gevoelige informatie wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="944d3-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="944d3-131">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="944d3-131">Select **Next**.</span></span>
1. <span data-ttu-id="944d3-132">Uw toegang aanpassen en machtigingen negeren.</span><span class="sxs-lookup"><span data-stu-id="944d3-132">Customize your access and override permissions.</span></span> <span data-ttu-id="944d3-133">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="944d3-133">Select **Next**.</span></span>
1. <span data-ttu-id="944d3-134">Kies wanneer het beleid van kracht moet worden.</span><span class="sxs-lookup"><span data-stu-id="944d3-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="944d3-135">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="944d3-135">Select **Next**.</span></span>
1. <span data-ttu-id="944d3-136">Controleer de instellingen en selecteer **maken**.</span><span class="sxs-lookup"><span data-stu-id="944d3-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="944d3-137">Als het beleid is doorgevoerd, wordt er een waarschuwing weergegeven in de e-mailberichten met de besproken gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="944d3-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>