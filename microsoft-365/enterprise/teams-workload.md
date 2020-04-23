---
title: Microsoft Teams voor Microsoft 365 Enterprise implementeren
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft Teams stapsgewijs leren en implementeren in uw organisatie.
ms.openlocfilehash: d34673a412539dfc73296f0139fa2eb555c17099
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636697"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="3c046-103">Microsoft Teams voor Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="3c046-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3c046-104">*Dit scenario geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3c046-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3c046-105">Microsoft Teams verenigt chatten, vergaderen, het delen van documenten en discussielijnen op een manier waardoor het eenvoudig is om inhoud te maken en te delen in groepen.</span><span class="sxs-lookup"><span data-stu-id="3c046-105">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups.</span></span> <span data-ttu-id="3c046-106">Teams is de manier waarop u teamwork en samenwerking bij elkaar brengt voor Microsoft 365 Enterprise en is een belangrijk onderdeel van het Gebouwd voor Teamwerk van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c046-106">Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365.</span></span> 

<span data-ttu-id="3c046-107">Zie [Welkom bij Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview)als u nog geen ervaring hebt met Teams.</span><span class="sxs-lookup"><span data-stu-id="3c046-107">If you're brand new to Teams, see [Welcome to Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> 


## <a name="roll-out-teams-to-your-organization"></a><span data-ttu-id="3c046-108">Teams in uw organisatie uitrollen</span><span class="sxs-lookup"><span data-stu-id="3c046-108">Roll out Teams to your organization</span></span>

<span data-ttu-id="3c046-109">Voordat u begint:</span><span class="sxs-lookup"><span data-stu-id="3c046-109">Before you begin:</span></span>

- <span data-ttu-id="3c046-110">Zorg ervoor dat u de juiste [Basisinfrastructuur](deploy-foundation-infrastructure.md)-fasen hebt geconfigureerd, zodat uw teams de benodigde gebruikersaccounts en de beveiligingsmogelijkheden hebben.</span><span class="sxs-lookup"><span data-stu-id="3c046-110">Make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the user accounts and security capabilities you need.</span></span> <span data-ttu-id="3c046-111">De Identiteits- en Gegevensbeveiligingsfasen zijn het belangrijkste voor het aanmelden en het gebruik van e-mail en bestanden met het retentie- en vertrouwelijkheidslabel.</span><span class="sxs-lookup"><span data-stu-id="3c046-111">The Identity and Information Protection phases are the most important for signing on and using securing email and files with retention and sensitivity labels.</span></span>
- <span data-ttu-id="3c046-112">Meer informatie over beveiliging en naleving in Teams in [dit artikel](https://docs.microsoft.com/microsoftteams/security-compliance-overview).</span><span class="sxs-lookup"><span data-stu-id="3c046-112">Learn about security and compliance in Teams with [this article](https://docs.microsoft.com/microsoftteams/security-compliance-overview).</span></span>
- <span data-ttu-id="3c046-113">Meer informatie over licenties voor Teams in [dit artikel](https://docs.microsoft.com/microsoftteams/office-365-licensing).</span><span class="sxs-lookup"><span data-stu-id="3c046-113">Learn about licensing for Teams with [this article](https://docs.microsoft.com/microsoftteams/office-365-licensing).</span></span>

<span data-ttu-id="3c046-114">Als u Teams in uw organisatie wilt uitrollen, leest u [Hoe rol ik Teams uit](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span><span class="sxs-lookup"><span data-stu-id="3c046-114">To roll out Teams in your organization, read [How to roll out Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span></span>

<span data-ttu-id="3c046-115">Zie [chatten, teams, kanalen en apps in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page)voor de eerste set met Teams-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="3c046-115">For your first set of Teams capabilities, see [Chat, teams, channels, and apps in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span></span>

<span data-ttu-id="3c046-116">Zie de volgende onderwerpen voor geavanceerde Teams-mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="3c046-116">For more advanced Teams capabilities, see:</span></span>

- [<span data-ttu-id="3c046-117">Besprekingen en vergaderingen</span><span class="sxs-lookup"><span data-stu-id="3c046-117">Meetings and Conferencing</span></span>](https://docs.microsoft.com/microsoftteams/deploy-meetings-microsoft-teams-landing-page)
- <span data-ttu-id="3c046-118">[Spraak in de cloud](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (hiervoor is Microsoft 365 E5 vereist)</span><span class="sxs-lookup"><span data-stu-id="3c046-118">[Cloud voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (requires Microsoft 365 E5)</span></span>

<span data-ttu-id="3c046-119">Als u het gebruik van Teams in uw organisatie wilt controleren, raadpleegt u:</span><span class="sxs-lookup"><span data-stu-id="3c046-119">To monitor your organization's usage of Teams, see:</span></span>

- [<span data-ttu-id="3c046-120">Analyses voor meerdere teams en per team bekijken in Teams</span><span class="sxs-lookup"><span data-stu-id="3c046-120">Cross-team and per-team analytics in Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/cross-team-per-team-analytics)
- [<span data-ttu-id="3c046-121">Analyse en rapportage</span><span class="sxs-lookup"><span data-stu-id="3c046-121">Analytics and reporting</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)


## <a name="upgrade-to-teams"></a><span data-ttu-id="3c046-122">Upgraden naar Teams</span><span class="sxs-lookup"><span data-stu-id="3c046-122">Upgrade to Teams</span></span>

<span data-ttu-id="3c046-123">Als dit nog niet is gebeurd, zult u binnenkort upgraden van Skype voor Bedrijven naar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3c046-123">If it hasn’t happened already, you will soon upgrade from Skype for Business to Microsoft Teams.</span></span> <span data-ttu-id="3c046-124">Of u nu net begint met Teams, Teams al gebruikt naast Skype voor Bedrijven of klaar bent om te upgraden, we willen ervoor zorgen dat u over alles beschikt wat u nodig hebt om succesvol met Teams te werken.</span><span class="sxs-lookup"><span data-stu-id="3c046-124">Whether you’re just getting started with Teams, already using Teams alongside Skype for Business, or ready to upgrade, we want to ensure you have everything you need to navigate a successful journey to Teams.</span></span>

<span data-ttu-id="3c046-125">Ongeacht of u een upgrade uitvoert van een webversie van Skype voor Bedrijven naar Teams of van een on-premises omgeving van Skype voor Bedrijven naar Teams, het upgradeframework biedt stapsgewijze instructies voor het proces op basis van uw bedrijfsscenario.</span><span class="sxs-lookup"><span data-stu-id="3c046-125">Whether you are upgrading from Skype for Business Online to Teams or from a Skype for Business on-premises environment to Teams, the upgrade framework will guide you through the process based on your business scenario.</span></span>
 
<span data-ttu-id="3c046-126">Zie [Aan de slag met uw Microsoft Teams-upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c046-126">See the [Getting started with your Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) for more information.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="3c046-127">Hoe Microsoft omgaat met Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c046-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3c046-128">Zie de volgende onderwerpen voor informatie over hoe Microsoft Teams heeft uitgerold en hoe het Teams gebruikt voor samenwerking:</span><span class="sxs-lookup"><span data-stu-id="3c046-128">To peek inside Microsoft and learn how we deployed and are using Teams for collaboration, see:</span></span>

- [<span data-ttu-id="3c046-129">Strategie voor acceptatie van Microsoft Teams om werknemers voor te bereiden op een nieuwe manier van werken</span><span class="sxs-lookup"><span data-stu-id="3c046-129">Microsoft Teams adoption strategy prepares employees for a new culture of work</span></span>](https://www.microsoft.com/itshowcase/microsoft-teams-adoption-strategy-prepares-employees-for-a-new-culture-of-work)
- [<span data-ttu-id="3c046-130">Met Microsoft Teams-ruimten krijgt u een wereldwijd schaalbare moderne vergader-ervaring</span><span class="sxs-lookup"><span data-stu-id="3c046-130">With Microsoft Teams Rooms, comes a globally scalable modern meeting experience</span></span>](https://www.microsoft.com/itshowcase/with-microsoft-teams-rooms-comes-a-globally-scalable-modern-meeting-experience)

## <a name="next-steps"></a><span data-ttu-id="3c046-131">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="3c046-131">Next steps</span></span>

- [<span data-ttu-id="3c046-132">Microsoft Teams-functies voor uw organisatie beheren</span><span class="sxs-lookup"><span data-stu-id="3c046-132">Manage Microsoft Teams features for your organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="3c046-133">Beheerderstraining voor Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c046-133">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)

