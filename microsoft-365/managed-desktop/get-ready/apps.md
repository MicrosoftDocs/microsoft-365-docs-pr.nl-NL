---
title: Apps in Microsoft Managed Desktop
description: Hier wordt uitgelegd hoe apps worden verwerkt, inclusief hoe u ze kunt verpakken, implementeren en ondersteunen.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 37f533f34753d66d975cb557239b2b168ac78f8e
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430766"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="78e7d-104">Apps in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="78e7d-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="78e7d-105">Apps in het algemeen</span><span class="sxs-lookup"><span data-stu-id="78e7d-105">Apps generally</span></span>

<span data-ttu-id="78e7d-106">Microsoft bevat bepaalde belangrijke apps samen met de Microsoft 365 E3 of E5-licentie die nodig is om deel te nemen aan Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="78e7d-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="78e7d-107">Hoewel we deze apps leveren, hebt u echter nog steeds bepaalde verantwoordelijkheden en acties die u moet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="78e7d-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="78e7d-108">U kunt ook extra niet-Microsoft-apps implementeren voor uw gebruikers voor selfservice via de Bedrijfsportal of een vereiste achtergrondinstallatie, allemaal via de implementatiepijplijn van Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="78e7d-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="78e7d-109">Apps van Microsoft</span><span class="sxs-lookup"><span data-stu-id="78e7d-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="78e7d-110">Inbegrepen bij uw Microsoft Managed Desktop-licentie zijn 64-bits versies van de apps in de Microsoft 365-apps voor ondernemingen Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams en OneNote.) Klik-en-Run-versies van Microsoft Project en Visio zijn  standaard niet opgenomen, maar u kunt ze wel vragen om ze toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="78e7d-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="78e7d-111">Zie Installatie van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop [apps voor meer informatie over deze apps.](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="78e7d-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="78e7d-112">Wat Microsoft doet om de apps die we bieden te ondersteunen</span><span class="sxs-lookup"><span data-stu-id="78e7d-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="78e7d-113">Microsoft biedt volledige service voor de implementatie, update en ondersteuning voor de meegeleverde Microsoft 365-apps voor ondernemingen apps.</span><span class="sxs-lookup"><span data-stu-id="78e7d-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="78e7d-114">Klik-en-Werkversies van Microsoft Project en Visio zijn  niet standaard opgenomen, maar Microsoft Managed Desktop biedt implementatiegroepen waarmee uw IT-beheerder licenties kan beheren en deze toepassingen op de juiste manier voor uw organisatie kan implementeren.</span><span class="sxs-lookup"><span data-stu-id="78e7d-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="78e7d-115">Microsoft ondersteunt gebruikers van deze toepassingen via de Microsoft Managed Desktop ondersteuningskanalen.</span><span class="sxs-lookup"><span data-stu-id="78e7d-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="78e7d-116">Wat u moet doen om de apps te ondersteunen die we bieden</span><span class="sxs-lookup"><span data-stu-id="78e7d-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="78e7d-117">Er zijn nog bepaalde dingen die u met deze apps moet doen:</span><span class="sxs-lookup"><span data-stu-id="78e7d-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="78e7d-118">**Licenties toewijzen:** u bent verantwoordelijk voor het verkrijgen en toewijzen van de juiste licenties aan gebruikers voor Microsoft 365-apps voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="78e7d-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="78e7d-119">**Gebruikers toevoegen aan beveiligingsgroepen:** als u een Microsoft Project of Visio gebruikt, moet de IT-beheerder deze gebruikers toevoegen aan de juiste implementatiegroepen.</span><span class="sxs-lookup"><span data-stu-id="78e7d-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="78e7d-120">IT-beheerders zijn ook verantwoordelijk voor het terugvorderen van licenties van deze gebruikers als ze het bedrijf verlaten.</span><span class="sxs-lookup"><span data-stu-id="78e7d-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="78e7d-121">**Implementeer Microsoft 365-invoegtoepassingen:** als u invoegtoepassingen nodig hebt voor een van de Microsoft 365-apps voor ondernemingen-apps, implementeert u deze centraal, net als elke andere app Windows 32.</span><span class="sxs-lookup"><span data-stu-id="78e7d-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="78e7d-122">Apps die u verstrekt</span><span class="sxs-lookup"><span data-stu-id="78e7d-122">Apps you provide</span></span>

<span data-ttu-id="78e7d-123">U hebt waarschijnlijk andere apps die u nodig hebt voor uw bedrijfsactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="78e7d-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="78e7d-124">Deze apps kunnen alleen worden geïmplementeerd op Microsoft Managed Desktop apparaten met Microsoft Intune implementatiepijplijn van de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="78e7d-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="78e7d-125">Voor meer informatie over toepassingsimplementatie volgt u de stappen in [Apps implementeren Microsoft Managed Desktop apparaten.](../get-started/deploy-apps.md)</span><span class="sxs-lookup"><span data-stu-id="78e7d-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="78e7d-126">Uw eigen apps voorbereiden voor opname in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="78e7d-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="78e7d-127">Controleer uw apps en controleer:</span><span class="sxs-lookup"><span data-stu-id="78e7d-127">Review your apps, checking:</span></span>

- <span data-ttu-id="78e7d-128">Geen van de apps is verboden of heeft beperkt gedrag, zoals beschreven in [Microsoft Managed Desktop app-vereisten.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="78e7d-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="78e7d-129">Apps moeten klaar zijn voor beheer door Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="78e7d-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="78e7d-130">Zie voor meer informatie over [dit onderwerp Windows 10 app-implementatie met Microsoft Intune](/intune/apps-windows-10-app-deploy) en Apps toevoegen aan [Microsoft Intune.](/intune/apps-add)</span><span class="sxs-lookup"><span data-stu-id="78e7d-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="78e7d-131">Andere vereisten voor het vooraf verpakken, zoals het verstrekken van licentiesleutels, het akkoord met licentievoorwaarden en het vooraf instellen van serververbindingen.</span><span class="sxs-lookup"><span data-stu-id="78e7d-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="78e7d-132">Stappen om u klaar te maken</span><span class="sxs-lookup"><span data-stu-id="78e7d-132">Steps to get ready</span></span>

1. <span data-ttu-id="78e7d-133">Controleer [Vereisten voor Microsoft Managed Desktop.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="78e7d-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="78e7d-134">Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="78e7d-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="78e7d-135">Vereisten voor gast-accounts</span><span class="sxs-lookup"><span data-stu-id="78e7d-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="78e7d-136">Netwerkconfiguratie voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="78e7d-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="78e7d-137">Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="78e7d-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="78e7d-138">Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="78e7d-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="78e7d-139">[Apps in Microsoft Managed Desktop](apps.md) (Dit artikel)</span><span class="sxs-lookup"><span data-stu-id="78e7d-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="78e7d-140">Toegewezen stations voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="78e7d-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="78e7d-141">Afdrukbronnen voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="78e7d-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
