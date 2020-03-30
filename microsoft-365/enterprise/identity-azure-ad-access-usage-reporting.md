---
title: 'Stap 13: tenant- en aanmeldingsactiviteit controleren'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over Azure Active Directory toegang en gebruikersrapportage.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42810400"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="b451a-103">Stap 13: tenant- en aanmeldingsactiviteit controleren</span><span class="sxs-lookup"><span data-stu-id="b451a-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="b451a-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b451a-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="b451a-105">In deze stap bekijkt u de auditlogboeken en de aanmeldingsactiviteiten via rapportage van Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b451a-105">In this step, you'll review audit logs and sign-in activity using Azure AD reporting.</span></span> <span data-ttu-id="b451a-106">Er zijn twee soorten rapporten beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b451a-106">Two types of reports are available.</span></span>

<span data-ttu-id="b451a-107">In het **Auditlogboeken activiteitenrapport** wordt de geschiedenis bijgehouden van elke taak die wordt uitgevoerd in uw Azure Active Directory- tenant.</span><span class="sxs-lookup"><span data-stu-id="b451a-107">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant.</span></span> <span data-ttu-id="b451a-108">Dit rapport beantwoordt vragen als:</span><span class="sxs-lookup"><span data-stu-id="b451a-108">This report answers questions like:</span></span>

- <span data-ttu-id="b451a-109">Wie heeft iemand toegevoegd aan een beheerdersgroep?</span><span class="sxs-lookup"><span data-stu-id="b451a-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="b451a-110">Welke gebruikers melden zich aan bij een specifieke app?</span><span class="sxs-lookup"><span data-stu-id="b451a-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="b451a-111">Hoe vaak worden er wachtwoorden opnieuw ingesteld?</span><span class="sxs-lookup"><span data-stu-id="b451a-111">How many password resets are happening?</span></span>

<span data-ttu-id="b451a-112">De **Aanmeldingsactiviteitenrapport** registreert wie de taken hebben uitgevoerd die zijn gerapporteerd in de auditlogboekenrapportage.</span><span class="sxs-lookup"><span data-stu-id="b451a-112">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report.</span></span> <span data-ttu-id="b451a-113">Dit rapport beantwoordt vragen als:</span><span class="sxs-lookup"><span data-stu-id="b451a-113">This report answers questions like:</span></span>

- <span data-ttu-id="b451a-114">Wat is het patroon van aanmelden van een bepaalde gebruiker in onderzoek?</span><span class="sxs-lookup"><span data-stu-id="b451a-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="b451a-115">Hoe vaak wordt er aangemeld in een dag, week of maand?</span><span class="sxs-lookup"><span data-stu-id="b451a-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="b451a-116">Hoeveel van deze aanmeldingspogingen zijn mislukt en voor welke accounts?</span><span class="sxs-lookup"><span data-stu-id="b451a-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="b451a-117">Zie [Azure Active Directory rapportage](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal) voor meer informatie over rapporten en toegang tot deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="b451a-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="b451a-118">Het gevolg van deze stap is dat u bewust wordt van deze rapporten en hoe u deze kunt gebruiken om inzicht te krijgen in Azure Active Directory-gebeurtenissen en -activiteiten in verband met planning en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="b451a-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="b451a-119">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b451a-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="b451a-120">Gebruikers toelaten om hun eigen groepen te maken en beheren</span><span class="sxs-lookup"><span data-stu-id="b451a-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
