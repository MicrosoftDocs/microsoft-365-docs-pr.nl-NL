---
title: Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten
description: Informatie over het installeren van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 30374e603350ecf9d5e5542263f004a22ccb0a67
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2019
ms.locfileid: "42809149"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="cae38-104">Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten</span><span class="sxs-lookup"><span data-stu-id="cae38-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="cae38-105">Microsoft Project en Microsoft Visio vereisen dat specifieke stappen worden geïnstalleerd op Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="cae38-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="cae38-106">In dit onderwerp worden de vereisten en het installatieproces voor deze toepassingen vermeld.</span><span class="sxs-lookup"><span data-stu-id="cae38-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cae38-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="cae38-107">Prerequisites</span></span>

<span data-ttu-id="cae38-108">Beheerders moeten controleren of ze aan deze voorwaarden voldoen:</span><span class="sxs-lookup"><span data-stu-id="cae38-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="cae38-109">**Licentiehoeveelheden** - De juiste hoeveelheid Microsoft Project- en Microsoft Visio-licenties moet beschikbaar zijn voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cae38-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="cae38-110">Microsoft Managed Desktop ondersteunt momenteel alleen 64-bits versies van deze toepassingen.</span><span class="sxs-lookup"><span data-stu-id="cae38-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="cae38-111">**Licentienamen** - De juiste licentienamen voor deze toepassingen zijn:</span><span class="sxs-lookup"><span data-stu-id="cae38-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="cae38-112">**Microsoft Project** - Project Online Professional of Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="cae38-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="cae38-113">**Microsoft Visio** - Visio Online-abonnement 2</span><span class="sxs-lookup"><span data-stu-id="cae38-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="cae38-114">**Bedrijfsportaal** - De bedrijfsportal moet beschikbaar zijn in uw tenant voor uw gebruikers om deze toepassingen te installeren.</span><span class="sxs-lookup"><span data-stu-id="cae38-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="cae38-115">Zie [Bedrijfsportaal als](company-portal.md)de bedrijfsportal niet in uw tenant is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="cae38-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="cae38-116">Project en Visio implementeren voor beheerde desktopapparaten van Microsoft</span><span class="sxs-lookup"><span data-stu-id="cae38-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="cae38-117">Nadat u uw ondersteuningsverzoek hebt ingediend, maakt Microsoft Managed Desktop drie Azure AD-groepen en drie toepassingsimplementaties via Microsoft Intune om de apps naar uw tenant te implementeren.</span><span class="sxs-lookup"><span data-stu-id="cae38-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="cae38-118">**Project en Visio implementeren**</span><span class="sxs-lookup"><span data-stu-id="cae38-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="cae38-119">**Een ondersteuningsverzoek indienen** IT-beheerders moeten een ondersteuningsverzoek indienen om deze toepassingen beschikbaar te maken voor hun gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cae38-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="cae38-120">Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)informatie over het contact opnemen met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="cae38-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="cae38-121">**Gebruikers toewijzen aan nieuwe Azure AD-groepen** Microsoft Managed Desktop maakt 3 Azure AD-groepen in uw tenant en 3 bijbehorende toepassingsimplementaties.</span><span class="sxs-lookup"><span data-stu-id="cae38-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="cae38-122">IT-beheerders moeten de gebruikers toewijzen aan de juiste groepen.</span><span class="sxs-lookup"><span data-stu-id="cae38-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="cae38-123">Wijs gebruikers toe aan slechts één van deze Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="cae38-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="cae38-124">Naam van Azure AD-groep</span><span class="sxs-lookup"><span data-stu-id="cae38-124">Azure AD Group name</span></span> | <span data-ttu-id="cae38-125">Welke gebruikers moeten toewijzen?</span><span class="sxs-lookup"><span data-stu-id="cae38-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="cae38-126">Modern Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="cae38-126">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="cae38-127">Gebruikers die alleen Project nodig hebben</span><span class="sxs-lookup"><span data-stu-id="cae38-127">Users needing only Project</span></span>
<span data-ttu-id="cae38-128">Moderne Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="cae38-128">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="cae38-129">Gebruikers die alleen Visio nodig hebben</span><span class="sxs-lookup"><span data-stu-id="cae38-129">Users needing only Visio</span></span>
<span data-ttu-id="cae38-130">Moderne Workplace-Office-Visio_Project_Install</span><span class="sxs-lookup"><span data-stu-id="cae38-130">Modern Workplace-Office-Visio_Project_Install</span></span> | <span data-ttu-id="cae38-131">Gebruikers die zowel Project als Visio nodig hebben</span><span class="sxs-lookup"><span data-stu-id="cae38-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="cae38-132">Eenmaal toegewezen aan deze groepen, zullen toepassingen beschikbaar zijn in de Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="cae38-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="cae38-133">Het kan enkele minuten duren om te synchroniseren, maar dan kunnen uw gebruikers de apps installeren vanuit Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="cae38-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="cae38-134">Wijzigingen communiceren</span><span class="sxs-lookup"><span data-stu-id="cae38-134">Communicate changes</span></span>
<span data-ttu-id="cae38-135">Het is belangrijk dat IT-beheerders hun gebruikers laten weten hoe ze Project en Visio moeten installeren.</span><span class="sxs-lookup"><span data-stu-id="cae38-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="cae38-136">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="cae38-136">This includes:</span></span> 
- <span data-ttu-id="cae38-137">Gebruikers op de hoogte stellen wanneer deze toepassingen voor hen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="cae38-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="cae38-138">Instructies voor het installeren van deze toepassingen vanuit de Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="cae38-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="cae38-139">Gebruikers moeten alle Office-toepassingen sluiten voordat ze Microsoft Project of Microsoft Visio van Bedrijfsportal installeren.</span><span class="sxs-lookup"><span data-stu-id="cae38-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
