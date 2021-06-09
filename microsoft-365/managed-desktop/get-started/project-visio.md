---
title: Installatie Microsoft Project of Microsoft Visio op Microsoft Managed Desktop apparaten
description: Informatie over het installeren van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop apparaten
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="ccea4-104">Installatie Microsoft Project of Microsoft Visio op Microsoft Managed Desktop apparaten</span><span class="sxs-lookup"><span data-stu-id="ccea4-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="ccea4-105">Microsoft Project en Microsoft Visio moeten specifieke stappen worden geïnstalleerd op Microsoft Managed Desktop apparaten.</span><span class="sxs-lookup"><span data-stu-id="ccea4-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ccea4-106">Dit onderwerp documenteert de vereisten en het installatieproces voor deze toepassingen.</span><span class="sxs-lookup"><span data-stu-id="ccea4-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ccea4-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="ccea4-107">Prerequisites</span></span>

<span data-ttu-id="ccea4-108">Beheerders moeten controleren of ze aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="ccea4-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="ccea4-109">**Licentiehoeveelheden:** de juiste hoeveelheid Microsoft Project microsoft-Visio moet beschikbaar zijn voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ccea4-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="ccea4-110">Microsoft Managed Desktop ondersteunt momenteel alleen 64-bits versies van deze toepassingen.</span><span class="sxs-lookup"><span data-stu-id="ccea4-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="ccea4-111">**Licentienamen:** de juiste licentienamen voor deze toepassingen zijn:</span><span class="sxs-lookup"><span data-stu-id="ccea4-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="ccea4-112">**Microsoft Project** - Project Online Professional of Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="ccea4-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="ccea4-113">**Microsoft Visio** - Visio Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="ccea4-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="ccea4-114">**Bedrijfsportal-** De Bedrijfsportal moet beschikbaar zijn in uw tenant zodat uw gebruikers deze toepassingen kunnen installeren.</span><span class="sxs-lookup"><span data-stu-id="ccea4-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="ccea4-115">Als de Bedrijfsportal niet is geïmplementeerd in uw tenant, bekijkt [u Bedrijfsportal.](company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="ccea4-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="ccea4-116">Implementatie Project en Visio voor Microsoft Managed Desktop apparaten</span><span class="sxs-lookup"><span data-stu-id="ccea4-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ccea4-117">Microsoft Managed Desktop worden Microsoft Project en Microsoft Visio als twee Win32-toepassingen in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ccea4-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="ccea4-118">We maken ook twee groepen in Azure Active Directory die worden toegewezen aan de bijbehorende toepassing met de bedoeling 'Beschikbaar'.</span><span class="sxs-lookup"><span data-stu-id="ccea4-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="ccea4-119">**Uw Project en Visio** Voeg de gebruiker toe aan de juiste groep en de toepassing wordt beschikbaar in de Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="ccea4-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="ccea4-120">Het kan enkele minuten duren voordat de synchronisatie is, maar uw gebruikers kunnen de apps vervolgens installeren vanaf Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="ccea4-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="ccea4-121">Naam van Azure AD-groep</span><span class="sxs-lookup"><span data-stu-id="ccea4-121">Azure AD Group name</span></span> | <span data-ttu-id="ccea4-122">Welke gebruikers moeten worden toegewezen?</span><span class="sxs-lookup"><span data-stu-id="ccea4-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="ccea4-123">Modern Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="ccea4-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="ccea4-124">Gebruikers die een Project</span><span class="sxs-lookup"><span data-stu-id="ccea4-124">Users needing Project</span></span>
<span data-ttu-id="ccea4-125">Modern Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="ccea4-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="ccea4-126">Gebruikers die een Visio</span><span class="sxs-lookup"><span data-stu-id="ccea4-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="ccea4-127">Wijzigingen communiceren</span><span class="sxs-lookup"><span data-stu-id="ccea4-127">Communicate changes</span></span>
<span data-ttu-id="ccea4-128">It-beheerders moeten hun gebruikers laten weten hoe ze Project en Visio.</span><span class="sxs-lookup"><span data-stu-id="ccea4-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="ccea4-129">Dit zijn:</span><span class="sxs-lookup"><span data-stu-id="ccea4-129">This includes:</span></span> 
- <span data-ttu-id="ccea4-130">Gebruikers op de hoogte stellen wanneer deze toepassingen voor hen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="ccea4-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="ccea4-131">Instructies voor het installeren van deze toepassingen vanaf de Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="ccea4-131">Instructions on how to install these applications from the Company Portal.</span></span>
