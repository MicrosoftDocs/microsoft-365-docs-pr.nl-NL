---
title: Basisinformatie over de toewijzing
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: Meer informatie over de nieuwe functieservice-eenheden.
ms.openlocfilehash: 2ab8efd637bb278faf6065559cab26cb7016975b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638229"
---
# <a name="allotment-basics"></a><span data-ttu-id="d0a95-103">Basisinformatie over de toewijzing</span><span class="sxs-lookup"><span data-stu-id="d0a95-103">Allotment basics</span></span>

<span data-ttu-id="d0a95-104">Met licentie-eenheden kunt u licentie limieten instellen en het beheer van een licentie delegeren aan alleen de producten en de door u geselecteerde licentie limieten.</span><span class="sxs-lookup"><span data-stu-id="d0a95-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="d0a95-105">Toewijs service voor groeps licenties gebruiken voor het toewijzen van licenties aan uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d0a95-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="d0a95-106">Licentie limieten zorgen voor extra controle over het aantal licenties dat is toegewezen aan de gebruikers in uw groepen.</span><span class="sxs-lookup"><span data-stu-id="d0a95-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="d0a95-107">U kunt er ook voor zorgen dat u binnen de toegestane licentielimiet blijft, zelfs als het aantal gebruikers in uw groepen toeneemt.</span><span class="sxs-lookup"><span data-stu-id="d0a95-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="d0a95-108">U kunt ook het beheer van uw service-eenheden delegeren.</span><span class="sxs-lookup"><span data-stu-id="d0a95-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="d0a95-109">Gedelegeerde service-eigenaren krijgen toegang tot het Beheercentrum, maar kunnen de licenties alleen weergeven en beheren in de toegewezen toewijzingen.</span><span class="sxs-lookup"><span data-stu-id="d0a95-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="d0a95-110">Dit biedt een meer granulaire overdracht van Licentiebeheer binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d0a95-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0a95-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="d0a95-111">Prerequisites</span></span>

<span data-ttu-id="d0a95-112">U moet voldoen aan de licentievereisten voor [op groepen gebaseerde licenties](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="d0a95-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="d0a95-113">U kunt de toewijzingsservice gebruiken voor alle producten die beschikbaar zijn voor gebruikers:</span><span class="sxs-lookup"><span data-stu-id="d0a95-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="d0a95-114">Office-suites en zelfstandige producten</span><span class="sxs-lookup"><span data-stu-id="d0a95-114">Office suites and standalone products</span></span>
- <span data-ttu-id="d0a95-115">Enterprise-en mobiliteits producten</span><span class="sxs-lookup"><span data-stu-id="d0a95-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="d0a95-116">Dynamics 365-producten</span><span class="sxs-lookup"><span data-stu-id="d0a95-116">Dynamics 365 products</span></span>

<span data-ttu-id="d0a95-117">De volgende producten kunnen niet worden gebruikt met toewijzingen:</span><span class="sxs-lookup"><span data-stu-id="d0a95-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="d0a95-118">Microsoft Store-apps</span><span class="sxs-lookup"><span data-stu-id="d0a95-118">Microsoft Store apps</span></span>
- <span data-ttu-id="d0a95-119">Permanente software, of software die rechtstreeks aan een gebruiker is toegewezen als er geen licentie is vereist.</span><span class="sxs-lookup"><span data-stu-id="d0a95-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="d0a95-120">Azure-informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="d0a95-120">Azure resources</span></span>

<span data-ttu-id="d0a95-121">U moet een globale beheerder of een licentiebeheerder zijn om aan de slag te gaan met een toewijzing.</span><span class="sxs-lookup"><span data-stu-id="d0a95-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="d0a95-122">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="d0a95-122">Getting started</span></span>

<span data-ttu-id="d0a95-123">De functieservice-eenheden is alleen beschikbaar in een persoonlijke preview-versie van slechts een klein aantal klanten.</span><span class="sxs-lookup"><span data-stu-id="d0a95-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="d0a95-124">Als u wilt deelnemen, vult u dit formulier in: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="d0a95-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
