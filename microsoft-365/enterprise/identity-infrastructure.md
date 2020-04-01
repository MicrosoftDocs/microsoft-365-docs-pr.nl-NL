---
title: 'Fase 2 : Identiteit'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: De stappen om de identiteitsinfrastructuur voor Microsoft 365 Enterprise te implementeren.
ms.openlocfilehash: 0189da0814d1d526d9e07ad35dbbabcbfe82a4cd
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42952028"
---
# <a name="phase-2-identity"></a><span data-ttu-id="b0561-103">Fase 2 : Identiteit</span><span class="sxs-lookup"><span data-stu-id="b0561-103">Phase 2: Identity</span></span>

![Fase 2 : Identiteit](../media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="b0561-105">In Microsoft 365 Enterprise zorgt een goed geplande en uitgevoerde identiteitsinfrastructuur voor betere beveiliging en krijgen alleen geverifieerde gebruikers en apparaten toegang tot de productiviteitsworkloads en de bijbehorende gegevens.</span><span class="sxs-lookup"><span data-stu-id="b0561-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="b0561-106">Bekijk deze video voor een overzicht van identiteitsmodellen en verificatie voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b0561-106">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="b0561-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="b0561-107"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="b0561-108">Als u al een identiteitsinfrastructuur hebt geïmplementeerd, bekijkt u het [afsluitcriterium voor identiteit](identity-exit-criteria.md) om er zeker van te zijn dat u voldoet aan de vereiste en optionele voorwaarden voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b0561-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="b0561-109">Zie de [poster Identiteitsinfrastructuur](../media/identity-infrastructure/M365E-ID-Infra.pdf) voor de identiteitskenmerken van elk Microsoft 365 Enterprise-abonnement, de rol van Azure Active Directory (Azure AD), on-premises en cloudonderdelen en de meestgebruikte verificatieconfiguraties.</span><span class="sxs-lookup"><span data-stu-id="b0561-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="b0561-110">[![De poster Identiteitsinfrastructuur](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="b0561-110">[![The Identity Infrastructure poster](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="b0561-111">Via deze poster met twee pagina's krijgt u snel inzicht in de identiteitsconcepten en configuraties voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b0561-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="b0561-112">U kunt ook [deze poster downloaden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) en afdrukken in het formaat Letter, Legal of Tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="b0561-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="b0561-113">Uw identiteitsinfrastructuur voor Microsoft 365 Enterprise plannen en implementeren</span><span class="sxs-lookup"><span data-stu-id="b0561-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="b0561-114">Voer de volgende stappen uit om uw nieuwe identiteitsinfrastructuur in de cloud te plannen en te implementeren.</span><span class="sxs-lookup"><span data-stu-id="b0561-114">Use the following steps to plan and deploy your new identity infrastructure in the cloud.</span></span> <span data-ttu-id="b0561-115">U kunt deze stappen ook gebruiken om uw bestaande on-premises of hybride identiteitsinfrastructuur aan te passen, zodat u kunt werken met Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b0561-115">You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="b0561-117">Globale beheerdersaccounts maken en beveiligen</span><span class="sxs-lookup"><span data-stu-id="b0561-117">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![Stap 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="b0561-119">Wachtwoorden beveiligen</span><span class="sxs-lookup"><span data-stu-id="b0561-119">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![Stap 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="b0561-121">Gebruikersaanmeldingen beveiligen en beheren</span><span class="sxs-lookup"><span data-stu-id="b0561-121">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![Stap 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="b0561-123">Gebruikersaccounts toevoegen</span><span class="sxs-lookup"><span data-stu-id="b0561-123">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![Stap 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="b0561-125">Groepen gebruiken voor beheer</span><span class="sxs-lookup"><span data-stu-id="b0561-125">Use groups for management</span></span>](identity-use-group-management.md) |
|![Stap 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="b0561-127">Identiteitsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="b0561-127">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="b0561-128">Wanneer u deze stappen hebt voltooid, gaat u naar het [afsluitcriterium](identity-exit-criteria.md) voor deze fase om er zeker van te zijn dat u voldoet aan de vereiste en optionele voorwaarden voor Microsoft 365 Enterprise-identiteiten.</span><span class="sxs-lookup"><span data-stu-id="b0561-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise identity.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="b0561-129">Aanbevelingen voor identiteits- en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="b0561-129">Identity and device access recommendations</span></span>

<span data-ttu-id="b0561-130">Microsoft biedt een aantal aanbevelingen voor [identiteits- en apparaattoegang](microsoft-365-policies-configurations.md) om te zorgen dat uw personeel veilig en productief blijft.</span><span class="sxs-lookup"><span data-stu-id="b0561-130">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="b0561-131">Gebruik voor identiteit de aanbevelingen en instellingen in de volgende artikelen, samen met de stappen in deze fase:</span><span class="sxs-lookup"><span data-stu-id="b0561-131">For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="b0561-132">Vereisten</span><span class="sxs-lookup"><span data-stu-id="b0561-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="b0561-133">Algemeen beleid voor identiteits- en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="b0561-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="b0561-134">Hoe Microsoft omgaat met Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b0561-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b0561-135">Lees hoe IT-experts bij Microsoft [identiteiten en beveiligde toegang beheren](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="b0561-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="b0561-136">Hoe Contoso Microsoft 365 Enterprise gebruikt</span><span class="sxs-lookup"><span data-stu-id="b0561-136">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b0561-137">Bekijk hoe Contoso Corporation, een fictieve maar representatieve multinational, [een hybride identiteitsinfrastructuur heeft geïmplementeerd](contoso-identity.md) voor Microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="b0561-137">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="b0561-139">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b0561-139">Next step</span></span>

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="b0561-141">Globale beheerdersaccounts maken en beveiligen</span><span class="sxs-lookup"><span data-stu-id="b0561-141">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
