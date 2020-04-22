---
title: Basisbeginselen van toewijzing
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: ''
description: Meer informatie over de nieuwe toewijzingsfunctie.
ms.openlocfilehash: d1f926165678b57ec46195d525f2fcdaa6976501
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632411"
---
# <a name="allotment-basics"></a><span data-ttu-id="df916-103">Basisbeginselen van toewijzing</span><span class="sxs-lookup"><span data-stu-id="df916-103">Allotment basics</span></span>

<span data-ttu-id="df916-104">Met licentietoewijzingen u licentielimieten instellen en het beheer van licentietoewijzing delegeren aan alleen de producten en licentielimieten die u selecteert.</span><span class="sxs-lookup"><span data-stu-id="df916-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="df916-105">Toewijzingen gebruiken groepslicenties om licenties toe te wijzen aan uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="df916-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="df916-106">Licentielimieten bieden extra controle over het aantal licenties dat aan de gebruikers in uw groepen is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="df916-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="df916-107">Dus zelfs als het aantal gebruikers in uw groepen toeneemt, u ervoor zorgen dat u binnen de licentielimiet blijft die u hebt ingesteld voor uw toewijzing.</span><span class="sxs-lookup"><span data-stu-id="df916-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="df916-108">U ook het beheer van uw toewijzingen delegeren.</span><span class="sxs-lookup"><span data-stu-id="df916-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="df916-109">Gedelegeerde toewijzingseigenaren krijgen toegang tot het beheercentrum, maar kunnen alleen de licenties zien en beheren in de toewijzingen die ze bezitten.</span><span class="sxs-lookup"><span data-stu-id="df916-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="df916-110">Dit biedt meer gedetailleerde delegatie van licentiebeheer binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="df916-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df916-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="df916-111">Prerequisites</span></span>

<span data-ttu-id="df916-112">U moet voldoen aan de licentievereisten voor [groepslicenties.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="df916-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="df916-113">U toewijzingen gebruiken met elk product dat beschikbaar is voor gebruikers:</span><span class="sxs-lookup"><span data-stu-id="df916-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="df916-114">Office-suites en zelfstandige producten</span><span class="sxs-lookup"><span data-stu-id="df916-114">Office suites and standalone products</span></span>
- <span data-ttu-id="df916-115">Enterprise en Mobility producten</span><span class="sxs-lookup"><span data-stu-id="df916-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="df916-116">Dynamics 365 producten</span><span class="sxs-lookup"><span data-stu-id="df916-116">Dynamics 365 products</span></span>

<span data-ttu-id="df916-117">De volgende producten kunnen niet worden gebruikt met toewijzingen:</span><span class="sxs-lookup"><span data-stu-id="df916-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="df916-118">Microsoft Store-apps</span><span class="sxs-lookup"><span data-stu-id="df916-118">Microsoft Store apps</span></span>
- <span data-ttu-id="df916-119">Permanente software, of software die rechtstreeks is toegewezen aan een gebruiker als er geen licentie bij betrokken is.</span><span class="sxs-lookup"><span data-stu-id="df916-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="df916-120">Azure-bronnen</span><span class="sxs-lookup"><span data-stu-id="df916-120">Azure resources</span></span>

<span data-ttu-id="df916-121">U moet een globale of licentiebeheerder zijn om aan de slag te gaan met een toewijzing.</span><span class="sxs-lookup"><span data-stu-id="df916-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="df916-122">Slag</span><span class="sxs-lookup"><span data-stu-id="df916-122">Getting started</span></span>

<span data-ttu-id="df916-123">De toewijzingsfunctie is beschikbaar in een privépreview voor slechts een klein aantal klanten.</span><span class="sxs-lookup"><span data-stu-id="df916-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="df916-124">Als je interesse hebt om lid te [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)worden, vul dan dit formulier in: .</span><span class="sxs-lookup"><span data-stu-id="df916-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
