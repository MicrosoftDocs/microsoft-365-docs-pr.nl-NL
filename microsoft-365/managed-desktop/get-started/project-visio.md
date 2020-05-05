---
title: Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten
description: Informatie over het installeren van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 450dbcb08cd0636dae575ecd2d5e9abadc5ceb25
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022094"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="3f8e5-104">Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten</span><span class="sxs-lookup"><span data-stu-id="3f8e5-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="3f8e5-105">Microsoft Project en Microsoft Visio vereisen dat specifieke stappen worden geïnstalleerd op Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="3f8e5-106">In dit onderwerp worden de vereisten en het installatieproces voor deze toepassingen documentaal.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f8e5-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="3f8e5-107">Prerequisites</span></span>

<span data-ttu-id="3f8e5-108">Beheerders moeten controleren of ze aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="3f8e5-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="3f8e5-109">**Licentiehoeveelheden** : het juiste aantal Microsoft Project- en Microsoft Visio-licenties moet beschikbaar zijn voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="3f8e5-110">Microsoft Managed Desktop ondersteunt momenteel alleen 64-bits versies van deze toepassingen.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="3f8e5-111">**Licentienamen** - De juiste licentienamen voor deze toepassingen zijn:</span><span class="sxs-lookup"><span data-stu-id="3f8e5-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="3f8e5-112">**Microsoft Project** - Project Online Professional of Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="3f8e5-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="3f8e5-113">**Microsoft Visio** - Visio Online-abonnement 2</span><span class="sxs-lookup"><span data-stu-id="3f8e5-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="3f8e5-114">**Bedrijfsportal** - De bedrijfsportal moet beschikbaar zijn in uw tenant voor uw gebruikers om deze toepassingen te installeren.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="3f8e5-115">Zie [Bedrijfsportal](company-portal.md)als de bedrijfsportal niet is geïmplementeerd in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="3f8e5-116">Project- en Visio-apparaten implementeren voor Microsoft Managed Desktop-apparaten</span><span class="sxs-lookup"><span data-stu-id="3f8e5-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="3f8e5-117">Nadat u uw ondersteuningsaanvraag hebt ingediend, maakt Microsoft Managed Desktop drie Azure AD-groepen en drie toepassingsimplementaties via Microsoft Intune om de apps naar uw tenant te implementeren.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="3f8e5-118">**Project en Visio implementeren**</span><span class="sxs-lookup"><span data-stu-id="3f8e5-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="3f8e5-119">**Een ondersteuningsverzoek indienen** IT-beheerders moeten een ondersteuningsverzoek indienen om deze toepassingen beschikbaar te maken voor hun gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="3f8e5-120">Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)informatie over het contact opnemen met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="3f8e5-121">**Gebruikers toewijzen aan nieuwe Azure AD-groepen** Microsoft Managed Desktop maakt 3 Azure AD-groepen in uw tenant en 3 bijbehorende toepassingsimplementaties.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="3f8e5-122">IT-beheerders moeten de gebruikers toewijzen aan de juiste groepen.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="3f8e5-123">Gebruikers toewijzen aan slechts één van deze Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="3f8e5-124">Azure AD-groepnaam</span><span class="sxs-lookup"><span data-stu-id="3f8e5-124">Azure AD Group name</span></span> | <span data-ttu-id="3f8e5-125">Welke gebruikers moeten worden toegewezen?</span><span class="sxs-lookup"><span data-stu-id="3f8e5-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="3f8e5-126">Moderne werkplek-office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="3f8e5-126">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="3f8e5-127">Gebruikers die Project nodig hebben</span><span class="sxs-lookup"><span data-stu-id="3f8e5-127">Users needing Project</span></span>
<span data-ttu-id="3f8e5-128">Moderne werkplek-office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="3f8e5-128">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="3f8e5-129">Gebruikers die Visio nodig hebben</span><span class="sxs-lookup"><span data-stu-id="3f8e5-129">Users needing Visio</span></span>

<span data-ttu-id="3f8e5-130">Zodra toepassingen aan deze groepen zijn toegewezen, zijn toepassingen beschikbaar in het bedrijfsportaal.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-130">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="3f8e5-131">Het kan een paar minuten duren om te synchroniseren, maar dan kunnen uw gebruikers de apps installeren via Company Portal.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-131">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="3f8e5-132">Wijzigingen communiceren</span><span class="sxs-lookup"><span data-stu-id="3f8e5-132">Communicate changes</span></span>
<span data-ttu-id="3f8e5-133">Het is belangrijk dat IT-beheerders hun gebruikers laten weten hoe ze Project en Visio moeten installeren.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-133">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="3f8e5-134">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="3f8e5-134">This includes:</span></span> 
- <span data-ttu-id="3f8e5-135">Gebruikers op de hoogte stellen wanneer deze toepassingen voor hen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-135">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="3f8e5-136">Instructies voor het installeren van deze toepassingen via de Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-136">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="3f8e5-137">Gebruikers moeten alle Office-toepassingen sluiten voordat ze Microsoft Project of Microsoft Visio vanuit Bedrijfsportal installeren.</span><span class="sxs-lookup"><span data-stu-id="3f8e5-137">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
