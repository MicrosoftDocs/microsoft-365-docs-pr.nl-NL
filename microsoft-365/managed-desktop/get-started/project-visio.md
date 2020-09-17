---
title: Microsoft Project of Microsoft Visio installeren op de beheerde bureaublad apparaten van Microsoft
description: Info over het installeren van Microsoft Project of Microsoft Visio op desktop computers met Microsoft beheerd
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950530"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="644fd-104">Microsoft Project of Microsoft Visio installeren op de beheerde bureaublad apparaten van Microsoft</span><span class="sxs-lookup"><span data-stu-id="644fd-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="644fd-105">In Microsoft Project en Microsoft Visio zijn bepaalde stappen vereist voor het installeren van op Microsoft beheerde bureaublad apparaten.</span><span class="sxs-lookup"><span data-stu-id="644fd-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="644fd-106">In dit onderwerp worden de vereisten en installatieprocessen voor deze toepassingen gedocumenteerd.</span><span class="sxs-lookup"><span data-stu-id="644fd-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="644fd-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="644fd-107">Prerequisites</span></span>

<span data-ttu-id="644fd-108">Beheerders moet controleren of ze aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="644fd-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="644fd-109">**Aantal licenties** : de juiste hoeveelheid Microsoft Project-en Microsoft Visio-licenties moeten beschikbaar zijn voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="644fd-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="644fd-110">Microsoft Managed Desktop biedt momenteel alleen ondersteuning voor 64-bits versies van deze toepassingen.</span><span class="sxs-lookup"><span data-stu-id="644fd-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="644fd-111">**Licentie namen** : de juiste licentie namen voor deze toepassingen zijn:</span><span class="sxs-lookup"><span data-stu-id="644fd-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="644fd-112">**Microsoft Project** -project online Professional of project online Premium</span><span class="sxs-lookup"><span data-stu-id="644fd-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="644fd-113">**Microsoft Visio** -Visio online-abonnement 2</span><span class="sxs-lookup"><span data-stu-id="644fd-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="644fd-114">**Bedrijfsportal** : de bedrijfsportal moet beschikbaar zijn in uw Tenant, zodat uw gebruikers deze toepassingen kunnen installeren.</span><span class="sxs-lookup"><span data-stu-id="644fd-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="644fd-115">Zie [Company Portal](company-portal.md)als de bedrijfs portal niet is geïmplementeerd in uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="644fd-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="644fd-116">Project en Visio voor Microsoft beheerde bureaublad apparaten implementeren</span><span class="sxs-lookup"><span data-stu-id="644fd-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="644fd-117">Microsoft Managed Desktop zal Microsoft Project en Microsoft Visio toevoegen als twee Win32-toepassingen in Microsoft intune.</span><span class="sxs-lookup"><span data-stu-id="644fd-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="644fd-118">U maakt ook twee groepen in azure Active Directory, die aan de bijbehorende toepassing wordt toegewezen met de beschikbaarheid ' beschikbare '.</span><span class="sxs-lookup"><span data-stu-id="644fd-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="644fd-119">**Project en Visio implementeren** Voeg de gebruiker toe aan de juiste groep en de toepassing wordt beschikbaar in de bedrijfs portal.</span><span class="sxs-lookup"><span data-stu-id="644fd-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="644fd-120">Het kan een paar minuten duren voor synchronisatie, maar de gebruikers kunnen de apps van de bedrijfs portal installeren.</span><span class="sxs-lookup"><span data-stu-id="644fd-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="644fd-121">Naam van Azure AD-groep</span><span class="sxs-lookup"><span data-stu-id="644fd-121">Azure AD Group name</span></span> | <span data-ttu-id="644fd-122">Welke gebruikers moeten ze toewijzen?</span><span class="sxs-lookup"><span data-stu-id="644fd-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="644fd-123">Modern Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="644fd-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="644fd-124">Gebruikers die project nodig hebben</span><span class="sxs-lookup"><span data-stu-id="644fd-124">Users needing Project</span></span>
<span data-ttu-id="644fd-125">Modern Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="644fd-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="644fd-126">Gebruikers die Visio nodig hebben</span><span class="sxs-lookup"><span data-stu-id="644fd-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="644fd-127">Wijzigingen doorgeven</span><span class="sxs-lookup"><span data-stu-id="644fd-127">Communicate changes</span></span>
<span data-ttu-id="644fd-128">Het is belangrijk dat IT-beheerders hun gebruikers laten weten hoe ze project en Visio moeten installeren.</span><span class="sxs-lookup"><span data-stu-id="644fd-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="644fd-129">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="644fd-129">This includes:</span></span> 
- <span data-ttu-id="644fd-130">Gebruikers op de hoogte stellen van de beschikbare toepassingen.</span><span class="sxs-lookup"><span data-stu-id="644fd-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="644fd-131">Instructies voor het installeren van deze toepassingen via de bedrijfs portal.</span><span class="sxs-lookup"><span data-stu-id="644fd-131">Instructions on how to install these applications from the Company Portal.</span></span>
