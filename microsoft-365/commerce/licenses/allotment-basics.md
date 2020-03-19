---
title: Basisbeginselen toewijzing
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
description: Meer informatie over de nieuwe toewijzingenfunctie.
ms.openlocfilehash: 22f7c35b1a5baf97fb72f541d57da28adeeffbe4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807335"
---
# <a name="allotment-basics"></a><span data-ttu-id="5d3fe-103">Basisbeginselen toewijzing</span><span class="sxs-lookup"><span data-stu-id="5d3fe-103">Allotment basics</span></span>

<span data-ttu-id="5d3fe-104">Met licentietoewijzingen u licentielimieten instellen en het beheer van licentietoewijzing delegeren aan alleen de producten en licentielimieten die u selecteert.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="5d3fe-105">Toewijzingen gebruiken groepslicenties om licenties toe te wijzen aan uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="5d3fe-106">Licentielimieten bieden extra controle over het aantal licenties dat wordt toegewezen aan de gebruikers in uw groepen.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="5d3fe-107">Dus zelfs als het aantal gebruikers in uw groepen toeneemt, u ervoor zorgen dat u binnen de licentielimiet blijft die u hebt ingesteld voor uw toewijzing.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="5d3fe-108">U ook het beheer van uw toewijzingen delegeren.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="5d3fe-109">Eigenaren van gedelegeerde toewijzingen krijgen toegang tot het beheercentrum, maar kunnen alleen de licenties zien en beheren in de toewijzingen die ze bezitten.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="5d3fe-110">Dit zorgt voor een meer gedetailleerde delegatie van licentiebeheer binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d3fe-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="5d3fe-111">Prerequisites</span></span>

<span data-ttu-id="5d3fe-112">U moet voldoen aan de licentievereisten voor [groepslicenties.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="5d3fe-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="5d3fe-113">U toewijzingen gebruiken met elk Office 365-product dat beschikbaar is voor gebruikers:</span><span class="sxs-lookup"><span data-stu-id="5d3fe-113">You can use allotments with any Office 365 product available to users:</span></span>

- <span data-ttu-id="5d3fe-114">Office-suites en zelfstandige producten</span><span class="sxs-lookup"><span data-stu-id="5d3fe-114">Office suites and standalone products</span></span>
- <span data-ttu-id="5d3fe-115">Enterprise en Mobility producten</span><span class="sxs-lookup"><span data-stu-id="5d3fe-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="5d3fe-116">Dynamics 365 producten</span><span class="sxs-lookup"><span data-stu-id="5d3fe-116">Dynamics 365 products</span></span>

<span data-ttu-id="5d3fe-117">De volgende producten kunnen niet worden gebruikt met toewijzingen:</span><span class="sxs-lookup"><span data-stu-id="5d3fe-117">The following products can’t be used with allotments:</span></span>

- <span data-ttu-id="5d3fe-118">Microsoft Store-apps</span><span class="sxs-lookup"><span data-stu-id="5d3fe-118">Microsoft Store apps</span></span>
- <span data-ttu-id="5d3fe-119">Permanente software of software die rechtstreeks aan een gebruiker is toegewezen als er geen licentie bij betrokken is.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="5d3fe-120">Azure-bronnen</span><span class="sxs-lookup"><span data-stu-id="5d3fe-120">Azure resources</span></span>

<span data-ttu-id="5d3fe-121">U moet een globale of licentiebeheerder zijn om aan de slag te gaan met een toewijzing.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="5d3fe-122">Slag</span><span class="sxs-lookup"><span data-stu-id="5d3fe-122">Getting started</span></span>

<span data-ttu-id="5d3fe-123">De toewijzingenfunctie is beschikbaar in een privévoorbeeld voor slechts een klein aantal klanten.</span><span class="sxs-lookup"><span data-stu-id="5d3fe-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="5d3fe-124">Als u geïnteresseerd bent om lid te [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)worden, vul dan dit formulier in: .</span><span class="sxs-lookup"><span data-stu-id="5d3fe-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
