---
title: Preventiebeleid voor gegevensverlies gebruiken voor niet-Microsoft-cloud-apps
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het gebruik van dlp-beleid voor niet-Microsoft-cloud-apps.
ms.openlocfilehash: fbba87fc5bb3bbca7e67ba374e202098a22f4a5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300122"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="f7b44-103">Beleid voor preventie van gegevensverlies gebruiken voor niet-Microsoft-cloud-apps (preview)</span><span class="sxs-lookup"><span data-stu-id="f7b44-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="f7b44-104">DLP-beleid (Data Loss Prevention) voor niet-Microsoft-cloud-apps maakt deel uit van de Microsoft 365 DLP-suite met functies; met behulp van deze functies kunt u gevoelige items ontdekken en beveiligen in Microsoft 365 services.</span><span class="sxs-lookup"><span data-stu-id="f7b44-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="f7b44-105">Zie Meer informatie over preventie van gegevensverlies voor meer informatie over alle Microsoft [DLP-aanbiedingen.](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="f7b44-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="f7b44-106">U kunt DLP-beleid gebruiken om niet-Microsoft-cloud-apps te controleren en te detecteren wanneer gevoelige items worden gebruikt en gedeeld via niet-Microsoft-cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="f7b44-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="f7b44-107">Als u dit beleid gebruikt, hebt u de zichtbaarheid en controle die u nodig hebt om ervoor te zorgen dat ze correct worden gebruikt en beveiligd, en voorkomt u risicovol gedrag dat hen in gevaar kan brengen.</span><span class="sxs-lookup"><span data-stu-id="f7b44-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f7b44-108">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="f7b44-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="f7b44-109">SKU/abonnementenlicenties</span><span class="sxs-lookup"><span data-stu-id="f7b44-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="f7b44-110">Voordat u DLP-beleid gaat gebruiken voor niet-Microsoft-cloud-apps, bevestigt u uw Microsoft 365 [en](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) eventuele invoegtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="f7b44-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="f7b44-111">Als u deze functionaliteit wilt openen en gebruiken, moet u een van deze abonnementen of invoegtoepassingen hebben:</span><span class="sxs-lookup"><span data-stu-id="f7b44-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="f7b44-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f7b44-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="f7b44-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="f7b44-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="f7b44-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="f7b44-114">Microsoft 365 E5 Security</span></span>

### <a name="permissions"></a><span data-ttu-id="f7b44-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="f7b44-115">Permissions</span></span>
<span data-ttu-id="f7b44-116">De gebruiker die het DLP-beleid maakt, moet het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="f7b44-116">The user who creates the DLP policy should be a:</span></span>
- <span data-ttu-id="f7b44-117">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="f7b44-117">Global administrator</span></span>
- <span data-ttu-id="f7b44-118">Beheerder voor naleving</span><span class="sxs-lookup"><span data-stu-id="f7b44-118">Compliance administrator</span></span>
- <span data-ttu-id="f7b44-119">Beheerder van nalevingsgegevens</span><span class="sxs-lookup"><span data-stu-id="f7b44-119">Compliance data administrator</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="f7b44-120">Uw Cloud App Security voorbereiden</span><span class="sxs-lookup"><span data-stu-id="f7b44-120">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="f7b44-121">DLP-beleid voor niet-Microsoft-cloud-apps gebruikt Cloud App Security DLP-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="f7b44-121">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="f7b44-122">Als u het wilt gebruiken, moet u uw Cloud App Security voorbereiden.</span><span class="sxs-lookup"><span data-stu-id="f7b44-122">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="f7b44-123">Zie Direct zichtbaarheids-, beveiligings- en beheeracties instellen voor [uw apps voor instructies.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="f7b44-123">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="f7b44-124">Verbinding maken een niet-Microsoft-cloud-app</span><span class="sxs-lookup"><span data-stu-id="f7b44-124">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="f7b44-125">Als u DLP-beleid wilt gebruiken voor een specifieke niet-Microsoft-cloud-app, moet de app zijn verbonden met Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="f7b44-125">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="f7b44-126">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="f7b44-126">For information, see:</span></span>

- [<span data-ttu-id="f7b44-127">Verbinding maken Vak</span><span class="sxs-lookup"><span data-stu-id="f7b44-127">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="f7b44-128">Verbinding maken Dropbox</span><span class="sxs-lookup"><span data-stu-id="f7b44-128">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="f7b44-129">Verbinding maken G-Suite</span><span class="sxs-lookup"><span data-stu-id="f7b44-129">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="f7b44-130">Verbinding maken Salesforce</span><span class="sxs-lookup"><span data-stu-id="f7b44-130">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="f7b44-131">Verbinding maken Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="f7b44-131">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="f7b44-132">Nadat u uw cloud-apps hebt verbonden met Cloud App Security, kunt u Microsoft 365 DLP-beleid voor hen maken.</span><span class="sxs-lookup"><span data-stu-id="f7b44-132">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

> [!NOTE]
> <span data-ttu-id="f7b44-133">Het is ook mogelijk om DLP-Microsoft Cloud App Security te maken voor Microsoft-cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="f7b44-133">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="f7b44-134">U wordt echter aangeraden om DLP-Microsoft 365 te gebruiken voor het maken en beheren van DLP-beleid voor Microsoft-cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="f7b44-134">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="f7b44-135">Een DLP-beleid maken voor een niet-Microsoft-cloud-app</span><span class="sxs-lookup"><span data-stu-id="f7b44-135">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="f7b44-136">Wanneer u een locatie voor het DLP-beleid selecteert, zet u de **Microsoft Cloud App Security** in.</span><span class="sxs-lookup"><span data-stu-id="f7b44-136">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="f7b44-137">Als u een specifieke app of exemplaar wilt selecteren, selecteert u **Exemplaar kiezen.**</span><span class="sxs-lookup"><span data-stu-id="f7b44-137">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="f7b44-138">Als u geen exemplaar selecteert, worden in het beleid alle verbonden apps in uw Microsoft Cloud App Security gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f7b44-138">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Locaties om het beleid toe te passen](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US en Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="f7b44-141">U kunt verschillende acties kiezen voor elke ondersteunde niet-Microsoft-cloud-app.</span><span class="sxs-lookup"><span data-stu-id="f7b44-141">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="f7b44-142">Voor elke app zijn er verschillende mogelijke acties (afhankelijk van de CLOUD-app-API).</span><span class="sxs-lookup"><span data-stu-id="f7b44-142">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Regel maken](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="f7b44-144">Wanneer u een regel maakt in het DLP-beleid, kunt u een actie selecteren voor niet-Microsoft-cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="f7b44-144">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="f7b44-145">Als u apps van derden wilt beperken, **selecteert u Apps van derden beperken.**</span><span class="sxs-lookup"><span data-stu-id="f7b44-145">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Apps van derden beperken](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> <span data-ttu-id="f7b44-147">DLP-beleid dat is toegepast op niet-Microsoft-apps Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="f7b44-147">DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="f7b44-148">Wanneer het DLP-beleid voor een niet-Microsoft-app wordt gemaakt, wordt automatisch hetzelfde beleid gemaakt in Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="f7b44-148">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="f7b44-149">Zie Een DLP-beleid maken en afstemmen voor informatie over het maken en configureren van [DLP-beleid.](./create-test-tune-dlp-policy.md)</span><span class="sxs-lookup"><span data-stu-id="f7b44-149">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7b44-150">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f7b44-150">See Also</span></span>

- [<span data-ttu-id="f7b44-151">Test maken en een DLP-beleid afstemmen</span><span class="sxs-lookup"><span data-stu-id="f7b44-151">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md)
- [<span data-ttu-id="f7b44-152">Aan de slag met het standaard DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="f7b44-152">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="f7b44-153">Een DLP-beleid maken vanuit een sjabloon</span><span class="sxs-lookup"><span data-stu-id="f7b44-153">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md)
