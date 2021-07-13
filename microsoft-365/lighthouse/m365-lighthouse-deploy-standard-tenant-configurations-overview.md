---
title: Overzicht van het gebruik van basislijnen voor het implementeren van standaardtenderconfiguraties
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Voor beheerde serviceproviders (MSP's) met Microsoft 365 Lighthouse informatie over het gebruik van basislijnen voor het implementeren van standaardtenderconfiguraties.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409177"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="471a2-103">Overzicht van het gebruik van basislijnen voor het implementeren van standaardtenderconfiguraties</span><span class="sxs-lookup"><span data-stu-id="471a2-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="471a2-104">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die aan de vereisten [voldoen.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="471a2-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="471a2-105">Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="471a2-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="471a2-106">Microsoft 365 Lighthouse basislijnen bieden een herhaalbare en schaalbare manier om de beveiligingsinstellingen voor meerdere tenants te beoordelen en Microsoft 365 beheren.</span><span class="sxs-lookup"><span data-stu-id="471a2-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="471a2-107">Basislijnen helpen ook bij het controleren van kernbeveiligingsbeleid en tenant compliancestandaarden met configuraties die gebruikers, apparaten en gegevens beveiligen.</span><span class="sxs-lookup"><span data-stu-id="471a2-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="471a2-108">Ontworpen om partners te helpen bij de acceptatie van beveiliging door klanten in hun eigen tempo, Microsoft 365 Lighthouse biedt een standaardset basislijnparameters en vooraf gedefinieerde configuraties voor Microsoft 365 services.</span><span class="sxs-lookup"><span data-stu-id="471a2-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="471a2-109">Deze beveiligingsconfiguraties helpen bij het meten van de Microsoft 365 van uw tenants.</span><span class="sxs-lookup"><span data-stu-id="471a2-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="471a2-110">U kunt de standaardlijnlijn en de implementatiestappen ervan bekijken vanuit Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="471a2-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="471a2-111">Als u basislijnen wilt toepassen op een tenant, selecteert u **Tenants** in het linkernavigatiedeelvenster en selecteert u vervolgens een tenant.</span><span class="sxs-lookup"><span data-stu-id="471a2-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="471a2-112">Ga vervolgens naar het tabblad **Implementatieplannen** en implementeert de gewenste basislijn.</span><span class="sxs-lookup"><span data-stu-id="471a2-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="471a2-113">Standaardbasislijnbeveiligingssjablonen</span><span class="sxs-lookup"><span data-stu-id="471a2-113">Standard baseline security templates</span></span>

<span data-ttu-id="471a2-114">Microsoft 365 Lighthouse standaard basislijnconfiguraties voor beveiligingswerkbelastingen zijn ontworpen om alle beheerde tenants te helpen een acceptabele beveiligingsdekking en naleving te bereiken.</span><span class="sxs-lookup"><span data-stu-id="471a2-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="471a2-115">De basislijnconfiguraties in de volgende tabel worden standaard geleverd Microsoft 365 Lighthouse standaard basislijn.</span><span class="sxs-lookup"><span data-stu-id="471a2-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="471a2-116">Basislijnconfiguratie</span><span class="sxs-lookup"><span data-stu-id="471a2-116">Baseline configuration</span></span> | <span data-ttu-id="471a2-117">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="471a2-117">Description</span></span> |
|--|--|
| <span data-ttu-id="471a2-118">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="471a2-118">Require MFA for admins</span></span> | <span data-ttu-id="471a2-119">Een beleid voor alleen-rapport Voorwaardelijke toegang waarvoor meervoudige verificatie voor beheerders vereist is.</span><span class="sxs-lookup"><span data-stu-id="471a2-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="471a2-120">Dit is vereist voor alle cloudtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="471a2-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="471a2-121">MFA vereisen voor eindgebruikers</span><span class="sxs-lookup"><span data-stu-id="471a2-121">Require MFA for end users</span></span> | <span data-ttu-id="471a2-122">Een beleid voor alleen-rapport Voorwaardelijke toegang dat meervoudige verificatie vereist voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="471a2-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="471a2-123">Dit is vereist voor alle cloudtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="471a2-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="471a2-124">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="471a2-124">Block legacy authentication</span></span> | <span data-ttu-id="471a2-125">Een beleid voor alleen-rapporterende voorwaardelijke toegang om oudere clientverificatie te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="471a2-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="471a2-126">Apparaten registreren in Microsoft Endpoint Manager : Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="471a2-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="471a2-127">Apparaatinschrijving om uw tenantapparaten in te schrijven in Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="471a2-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="471a2-128">Dit wordt gedaan door Automatisch registreren in te stellen tussen Azure Active Directory en Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="471a2-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="471a2-129">Antivirusbeleidsconfiguratie (AV)</span><span class="sxs-lookup"><span data-stu-id="471a2-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="471a2-130">Een apparaatconfiguratieprofiel voor Windows apparaten met vooraf geconfigureerde Microsoft Defender Antivirus instellingen.</span><span class="sxs-lookup"><span data-stu-id="471a2-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="471a2-131">Beleid voor naleving van venster 10 instellen</span><span class="sxs-lookup"><span data-stu-id="471a2-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="471a2-132">Een Windows apparaatbeleid met vooraf geconfigureerde instellingen om te voldoen aan basisvereisten voor naleving.</span><span class="sxs-lookup"><span data-stu-id="471a2-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="471a2-133">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="471a2-133">Related content</span></span>

<span data-ttu-id="471a2-134">[Basislijnen Microsoft 365 Lighthouse implementeren](m365-lighthouse-deploy-baselines.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="471a2-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)</span></span>\
<span data-ttu-id="471a2-135">[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="471a2-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
