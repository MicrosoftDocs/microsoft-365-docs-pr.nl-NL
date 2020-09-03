---
title: Office 365 Management Activity API
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: In dit artikel vindt u een beknopt overzicht van de API van Office 365 Management Activity en de informatie die wordt verstrekt uit activiteitenlogboeken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d51f27f28b0adb84ef43004664ef310567263b9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332302"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="32b75-103">Office 365 Management Activity API</span><span class="sxs-lookup"><span data-stu-id="32b75-103">Office 365 Management Activity API</span></span>

<span data-ttu-id="32b75-104">Microsoft biedt Reporting Services die u kunt gebruiken om een samenvoeging van de Office 365-Tenant te verkrijgen met samenvoeginformatie.</span><span class="sxs-lookup"><span data-stu-id="32b75-104">Microsoft provides reporting services you can use to obtain aggregated transactional information about your Office 365 tenant.</span></span> <span data-ttu-id="32b75-105">De [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) maakt gebruik van een industrie-standaard aanliggend ontwerp en OAuth v2 voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="32b75-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) uses an industry-standard RESTful design and OAuth v2 for authentication.</span></span> <span data-ttu-id="32b75-106">Dit maakt het eenvoudig om te experimenteren met het ophalen van gegevens en het opzeggen van de opname Programma's en toepassingen.</span><span class="sxs-lookup"><span data-stu-id="32b75-106">This makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="32b75-107">De API biedt een gegevensfeed met informatie over gebruikers, beheerders, bewerkingen en beveiligingsactiviteiten in Office 365.</span><span class="sxs-lookup"><span data-stu-id="32b75-107">The API provides a data feed with information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="32b75-108">De gegevens kunnen ter regulering worden bewaard of gecombineerd met logboekgegevens van een on-premises infrastructuur of andere bronnen.</span><span class="sxs-lookup"><span data-stu-id="32b75-108">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources.</span></span> <span data-ttu-id="32b75-109">Dit helpt bij het maken van een toezicht oplossing voor bewerkingen, beveiliging en compliance in de onderneming.</span><span class="sxs-lookup"><span data-stu-id="32b75-109">This helps build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="32b75-110">De Office 365 Management Activity API biedt informatie over diverse acties en gebeurtenissen van gebruikers, beheerders, systemen en beleid uit Office 365 en Azure Active Directory-activiteitenlogboeken.</span><span class="sxs-lookup"><span data-stu-id="32b75-110">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="32b75-111">De API biedt een consistent controleschema met meer dan tien velden die in alle services worden gemeenschappelijk.</span><span class="sxs-lookup"><span data-stu-id="32b75-111">The API provides a consistent audit schema with over 10 fields common across all the services.</span></span> <span data-ttu-id="32b75-112">Met de API kunnen organisaties eenvoudige verbindingen tussen gebeurtenissen aanbrengen en kunnen nieuwe manieren om redenen voor de gegevens worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="32b75-112">The API allows organizations to make easy connections between events, and enables new ways to reason over the data.</span></span>

<span data-ttu-id="32b75-113">Tientallen onafhankelijke software leveranciers (Isv's) die zijn gekoppeld aan Microsoft en die oplossingen hebben gemaakt op basis van de API.</span><span class="sxs-lookup"><span data-stu-id="32b75-113">Dozens of Independent Software Vendors (ISVs) partnered with Microsoft and have built solutions based on the API.</span></span> <span data-ttu-id="32b75-114">Sommige oplossingen zijn alleen gericht op Office 365-gegevens en andere brongegevens van meerdere cloud providers en on-premises systemen, zodat een uniforme weergave wordt gemaakt van activiteiten, beveiliging en compliance-gerelateerde activiteiten.</span><span class="sxs-lookup"><span data-stu-id="32b75-114">Some solutions focus solely on Office 365 data and others source data from multiple cloud providers and on-premises systems to create a unified view of operations, security, and compliance-related activity.</span></span> 

<span data-ttu-id="32b75-115">Zie voor meer informatie de [naslag voor Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="32b75-115">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
