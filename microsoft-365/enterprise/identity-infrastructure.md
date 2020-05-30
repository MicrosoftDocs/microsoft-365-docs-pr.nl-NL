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
ms.openlocfilehash: 6f237f779df16f2a2a03eab29af78a89c5f7a5ae
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371416"
---
# <a name="phase-2-identity"></a><span data-ttu-id="2d105-103">Fase 2 : Identiteit</span><span class="sxs-lookup"><span data-stu-id="2d105-103">Phase 2: Identity</span></span>

![Fase 2 : Identiteit](../media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="2d105-105">In Microsoft 365 Enterprise zorgt een goed geplande en uitgevoerde identiteitsinfrastructuur voor betere beveiliging en krijgen alleen geverifieerde gebruikers en apparaten toegang tot de productiviteitsworkloads en de bijbehorende gegevens.</span><span class="sxs-lookup"><span data-stu-id="2d105-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="2d105-106">Bekijk deze video voor een overzicht van identiteitsmodellen en verificatie voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2d105-106">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="2d105-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="2d105-107"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="2d105-108">Als u al een identiteitsinfrastructuur hebt geïmplementeerd, bekijkt u het [afsluitcriterium voor identiteit](identity-exit-criteria.md) om er zeker van te zijn dat u voldoet aan de vereiste en optionele voorwaarden voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2d105-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="2d105-109">Zie de [poster Identiteitsinfrastructuur](../media/identity-infrastructure/M365E-ID-Infra.pdf) voor de identiteitskenmerken van elk Microsoft 365 Enterprise-abonnement, de rol van Azure Active Directory (Azure AD), on-premises en cloudonderdelen en de meestgebruikte verificatieconfiguraties.</span><span class="sxs-lookup"><span data-stu-id="2d105-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="2d105-110">[![De poster Identiteitsinfrastructuur](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="2d105-110">[![The Identity Infrastructure poster](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="2d105-111">Via deze poster met twee pagina's krijgt u snel inzicht in de identiteitsconcepten en configuraties voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2d105-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="2d105-112">U kunt [deze poster ook downloaden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) en afdrukken in het formaat Letter, Legal of Tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="2d105-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="2d105-113">Uw identiteitsinfrastructuur voor Microsoft 365 Enterprise plannen en implementeren</span><span class="sxs-lookup"><span data-stu-id="2d105-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="2d105-114">Voer de volgende stappen uit om uw nieuwe identiteitsinfrastructuur in de cloud te plannen en te implementeren.</span><span class="sxs-lookup"><span data-stu-id="2d105-114">Use the following steps to plan and deploy your new identity infrastructure in the cloud.</span></span> <span data-ttu-id="2d105-115">U kunt deze stappen ook gebruiken om uw bestaande on-premises of hybride identiteitsinfrastructuur aan te passen om met Microsoft 365 Enterprise te werken.</span><span class="sxs-lookup"><span data-stu-id="2d105-115">You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="2d105-117">Globale beheerdersaccounts maken en beveiligen</span><span class="sxs-lookup"><span data-stu-id="2d105-117">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![Stap 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="2d105-119">Wachtwoorden beveiligen</span><span class="sxs-lookup"><span data-stu-id="2d105-119">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![Stap 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="2d105-121">Gebruikersaanmeldingen beveiligen en beheren</span><span class="sxs-lookup"><span data-stu-id="2d105-121">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![Stap 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="2d105-123">Gebruikersaccounts toevoegen</span><span class="sxs-lookup"><span data-stu-id="2d105-123">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![Stap 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="2d105-125">Groepen gebruiken voor beheer</span><span class="sxs-lookup"><span data-stu-id="2d105-125">Use groups for management</span></span>](identity-use-group-management.md) |
|![Stap 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="2d105-127">Identiteitsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="2d105-127">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="2d105-128">Wanneer u deze stappen hebt voltooid, gaat u naar het [afsluitcriterium](identity-exit-criteria.md) voor deze fase om er zeker van te zijn dat u voldoet aan de vereiste en optionele voorwaarden voor Microsoft 365 Enterprise-identiteiten.</span><span class="sxs-lookup"><span data-stu-id="2d105-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise identity.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="2d105-129">Aanbevelingen voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="2d105-129">Identity and device access recommendations</span></span>

<span data-ttu-id="2d105-130">Microsoft biedt een aantal aanbevelingen voor [identiteiten en apparaattoegang](microsoft-365-policies-configurations.md) om te zorgen dat uw personeel veilig en productief blijft.</span><span class="sxs-lookup"><span data-stu-id="2d105-130">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="2d105-131">Gebruik voor identiteiten de aanbevelingen en instellingen in de volgende artikelen, samen met de stappen in deze fase:</span><span class="sxs-lookup"><span data-stu-id="2d105-131">For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="2d105-132">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2d105-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="2d105-133">Algemeen beleid voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="2d105-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="2d105-134">Hoe Microsoft omgaat met Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2d105-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2d105-135">Lees hoe IT-experts bij Microsoft [identiteiten en beveiligde toegang beheren](https://www.microsoft.com/nl-NL/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span><span class="sxs-lookup"><span data-stu-id="2d105-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/nl-NL/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span></span>

>[!Note]
><span data-ttu-id="2d105-136">Deze IT-presentatie is alleen beschikbaar in het Engels.</span><span class="sxs-lookup"><span data-stu-id="2d105-136">This IT Showcase resource is only available in English.</span></span>
>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="2d105-137">Hoe Contoso Microsoft 365 Enterprise gebruikt</span><span class="sxs-lookup"><span data-stu-id="2d105-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2d105-138">Bekijk hoe Contoso Corporation, een fictieve maar representatieve multinational, [een hybride identiteitsinfrastructuur heeft geïmplementeerd](contoso-identity.md) voor Microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="2d105-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="2d105-140">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="2d105-140">Next step</span></span>

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="2d105-142">Globale beheerdersaccounts maken en beveiligen</span><span class="sxs-lookup"><span data-stu-id="2d105-142">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
