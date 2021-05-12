---
title: Basisprincipes van toewijzing
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: ''
ms.custom:
- commerce_licensing
description: Meer informatie over de nieuwe toewijzingsfunctie.
ms.date: 03/17/2021
ms.openlocfilehash: 949e06d4bf54405e0045f8c7512a04b1b5cc22c0
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327128"
---
# <a name="allotment-basics"></a><span data-ttu-id="9617c-103">Basisprincipes van toewijzing</span><span class="sxs-lookup"><span data-stu-id="9617c-103">Allotment basics</span></span>

<span data-ttu-id="9617c-104">Met licentietoewijzingen kunt u licentielimieten en gedelegeerdenbeheer van licentietoewijzingen instellen voor alleen de producten en licentielimieten die u selecteert.</span><span class="sxs-lookup"><span data-stu-id="9617c-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="9617c-105">Toewijzingen gebruiken groepslicenties om licenties toe te wijzen aan uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9617c-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="9617c-106">Licentielimieten bieden extra controle over het aantal licenties dat aan de gebruikers in uw groepen wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="9617c-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="9617c-107">Dus zelfs als het aantal gebruikers in uw groepen toeneemt, kunt u ervoor zorgen dat u binnen de licentielimiet blijft die u hebt ingesteld voor uw toewijzing.</span><span class="sxs-lookup"><span data-stu-id="9617c-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="9617c-108">U kunt ook het beheer van uw toewijzingen delegeren.</span><span class="sxs-lookup"><span data-stu-id="9617c-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="9617c-109">Gedelegeerde toewijzingseigenaren krijgen toegang tot het beheercentrum, maar kunnen de licenties alleen zien en beheren in de toewijzingen die ze bezitten.</span><span class="sxs-lookup"><span data-stu-id="9617c-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="9617c-110">Dit biedt een gedetailleerdere delegatie van licentiebeheer binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9617c-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9617c-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="9617c-111">Prerequisites</span></span>

<span data-ttu-id="9617c-112">U moet voldoen aan de licentievereisten voor [groepslicenties.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="9617c-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="9617c-113">U kunt toewijzingen gebruiken met elk product dat beschikbaar is voor gebruikers:</span><span class="sxs-lookup"><span data-stu-id="9617c-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="9617c-114">Office-suites en zelfstandige producten</span><span class="sxs-lookup"><span data-stu-id="9617c-114">Office suites and standalone products</span></span>
- <span data-ttu-id="9617c-115">Ondernemings- en mobiliteitsproducten</span><span class="sxs-lookup"><span data-stu-id="9617c-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="9617c-116">Dynamics 365-producten</span><span class="sxs-lookup"><span data-stu-id="9617c-116">Dynamics 365 products</span></span>

<span data-ttu-id="9617c-117">De volgende producten kunnen niet worden gebruikt met toewijzingen:</span><span class="sxs-lookup"><span data-stu-id="9617c-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="9617c-118">Microsoft Store-apps</span><span class="sxs-lookup"><span data-stu-id="9617c-118">Microsoft Store apps</span></span>
- <span data-ttu-id="9617c-119">Eeuwigdurende software of software die rechtstreeks aan een gebruiker is toegewezen als er geen licentie bij betrokken is.</span><span class="sxs-lookup"><span data-stu-id="9617c-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="9617c-120">Azure-resources</span><span class="sxs-lookup"><span data-stu-id="9617c-120">Azure resources</span></span>

<span data-ttu-id="9617c-121">U moet een globale beheerder of licentiebeheerder zijn om aan de slag te gaan met een toewijzing.</span><span class="sxs-lookup"><span data-stu-id="9617c-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="9617c-122">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="9617c-122">Getting started</span></span>

<span data-ttu-id="9617c-123">De toewijzingsfunctie is beschikbaar in een privévoorbeeld voor slechts een klein aantal klanten.</span><span class="sxs-lookup"><span data-stu-id="9617c-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="9617c-124">Als u wilt deelnemen, vult u dit formulier in: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="9617c-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>