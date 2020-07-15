---
title: Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten
description: Informatie over het installeren van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126825"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="740cb-104">Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten</span><span class="sxs-lookup"><span data-stu-id="740cb-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="740cb-105">Voor Microsoft Project en Microsoft Visio moeten specifieke stappen worden geïnstalleerd op Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="740cb-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="740cb-106">Dit onderwerp documenteert de vereisten en het installatieproces voor deze toepassingen.</span><span class="sxs-lookup"><span data-stu-id="740cb-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="740cb-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="740cb-107">Prerequisites</span></span>

<span data-ttu-id="740cb-108">Beheerders moeten controleren of ze aan deze voorwaarden voldoen:</span><span class="sxs-lookup"><span data-stu-id="740cb-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="740cb-109">**Licentiehoeveelheden** - De juiste hoeveelheid Microsoft Project- en Microsoft Visio-licenties moet beschikbaar zijn voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="740cb-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="740cb-110">Microsoft Managed Desktop ondersteunt momenteel alleen 64-bits versies van deze toepassingen.</span><span class="sxs-lookup"><span data-stu-id="740cb-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="740cb-111">**Licentienamen** - De juiste licentienamen voor deze toepassingen zijn:</span><span class="sxs-lookup"><span data-stu-id="740cb-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="740cb-112">**Microsoft Project** - Project Online Professional of Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="740cb-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="740cb-113">**Microsoft Visio** - Visio Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="740cb-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="740cb-114">**Bedrijfsportal** - De Bedrijfsportal moet beschikbaar zijn in uw tenant voor uw gebruikers om deze toepassingen te installeren.</span><span class="sxs-lookup"><span data-stu-id="740cb-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="740cb-115">Zie [Bedrijfsportal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="740cb-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="740cb-116">Project en Visio implementeren voor Microsoft Managed Desktop-apparaten</span><span class="sxs-lookup"><span data-stu-id="740cb-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="740cb-117">Microsoft Managed Desktop voegt Microsoft Project en Microsoft Visio toe als twee Win32-toepassingen in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="740cb-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="740cb-118">We maken ook twee groepen in Azure Active Directory die worden toegewezen aan de bijbehorende toepassing met de intentie 'Beschikbaar'.</span><span class="sxs-lookup"><span data-stu-id="740cb-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="740cb-119">**Project en Visio implementeren** Voeg de gebruiker toe aan de juiste groep en de toepassing wordt beschikbaar in de bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="740cb-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="740cb-120">Het kan enkele minuten duren voordat de synchronisatie is, maar uw gebruikers kunnen de apps installeren vanuit Company Portal.</span><span class="sxs-lookup"><span data-stu-id="740cb-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="740cb-121">Azure AD-groepnaam</span><span class="sxs-lookup"><span data-stu-id="740cb-121">Azure AD Group name</span></span> | <span data-ttu-id="740cb-122">Welke gebruikers moeten ze toewijzen?</span><span class="sxs-lookup"><span data-stu-id="740cb-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="740cb-123">Moderne Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="740cb-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="740cb-124">Gebruikers die Project nodig hebben</span><span class="sxs-lookup"><span data-stu-id="740cb-124">Users needing Project</span></span>
<span data-ttu-id="740cb-125">Moderne Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="740cb-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="740cb-126">Gebruikers die Visio nodig hebben</span><span class="sxs-lookup"><span data-stu-id="740cb-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="740cb-127">Wijzigingen communiceren</span><span class="sxs-lookup"><span data-stu-id="740cb-127">Communicate changes</span></span>
<span data-ttu-id="740cb-128">Het is belangrijk voor IT-beheerders om hun gebruikers te laten weten hoe project en Visio te installeren.</span><span class="sxs-lookup"><span data-stu-id="740cb-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="740cb-129">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="740cb-129">This includes:</span></span> 
- <span data-ttu-id="740cb-130">Gebruikers op de hoogte stellen wanneer deze toepassingen voor hen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="740cb-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="740cb-131">Instructies voor het installeren van deze toepassingen vanuit de Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="740cb-131">Instructions on how to install these applications from the Company Portal.</span></span>
