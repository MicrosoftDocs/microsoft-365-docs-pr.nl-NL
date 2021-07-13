---
title: Basislijnen Microsoft 365 Lighthouse implementeren
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
description: Voor MSP's (Managed Service Providers) met Microsoft 365 Lighthouse, leert u hoe u Microsoft 365 Lighthouse basislijnen implementeert.
ms.openlocfilehash: f329993443b4bd3003a3e8460d77f9b73ac10fc6
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409102"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a><span data-ttu-id="de47f-103">Basislijnen Microsoft 365 Lighthouse implementeren</span><span class="sxs-lookup"><span data-stu-id="de47f-103">Deploy Microsoft 365 Lighthouse baselines</span></span> 

> [!NOTE]
> <span data-ttu-id="de47f-104">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die aan de vereisten [voldoen.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="de47f-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="de47f-105">Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="de47f-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="de47f-106">Microsoft 365 Lighthouse basislijnen kunt u standaard beheerde tenantconfiguraties implementeren om tenantgebruikers, apparaten en gegevens te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="de47f-106">Microsoft 365 Lighthouse baselines let you deploy standard managed tenant configurations to secure tenant users, devices, and data.</span></span> <span data-ttu-id="de47f-107">Er zijn zes standaardlijnconfiguraties die standaard worden geleverd met Microsoft 365 Lighthouse:</span><span class="sxs-lookup"><span data-stu-id="de47f-107">There are six default baseline configurations that come standard with Microsoft 365 Lighthouse:</span></span>

- <span data-ttu-id="de47f-108">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="de47f-108">Require MFA for admins</span></span>
- <span data-ttu-id="de47f-109">MFA vereisen voor eindgebruikers</span><span class="sxs-lookup"><span data-stu-id="de47f-109">Require MFA for end users</span></span>
- <span data-ttu-id="de47f-110">Oudere verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="de47f-110">Block Legacy Authentication</span></span>
- <span data-ttu-id="de47f-111">Apparaatinschrijving instellen in Microsoft Endpoint Manager : Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="de47f-111">Set up Device Enrollment in Microsoft Endpoint Manager – Azure AD Join</span></span>
- <span data-ttu-id="de47f-112">Defender Anti-virusbeleid configureren voor Windows apparaten</span><span class="sxs-lookup"><span data-stu-id="de47f-112">Configure Defender Anti-virus policy for Windows devices</span></span>
- <span data-ttu-id="de47f-113">Compliancebeleid configureren voor Windows apparaten</span><span class="sxs-lookup"><span data-stu-id="de47f-113">Configure Compliance Policy for Windows devices</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="de47f-114">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="de47f-114">Before you begin</span></span>

<span data-ttu-id="de47f-115">Zorg ervoor dat u en uw klantten tenants voldoen aan de vereisten die worden vermeld in [Vereisten voor Microsoft 365 Lighthouse.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="de47f-115">Make sure you and your customer tenants meet the requirements listed in [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span></span>

## <a name="learn-more-about-the-default-baseline"></a><span data-ttu-id="de47f-116">Meer informatie over de standaardlijnlijn</span><span class="sxs-lookup"><span data-stu-id="de47f-116">Learn more about the default baseline</span></span>

<span data-ttu-id="de47f-117">Selecteer **Basislijnen** in het linkernavigatiedeelvenster om de pagina Basislijnen te openen.</span><span class="sxs-lookup"><span data-stu-id="de47f-117">Select **Baselines** from the left navigation pane to open the Baselines page.</span></span> <span data-ttu-id="de47f-118">U ziet dat de standaardlijnlijn al is toegevoegd aan de standaardten tenantgroep (alle tenants).</span><span class="sxs-lookup"><span data-stu-id="de47f-118">You'll see that the default baseline has already been added to the Default tenant group (all tenants).</span></span> <span data-ttu-id="de47f-119">Als u de standaardconfiguraties voor basislijn wilt weergeven, selecteert u **Basislijn weergeven** om de pagina Standaard basislijn te openen.</span><span class="sxs-lookup"><span data-stu-id="de47f-119">To view the default baseline configurations, select **View baseline** to open the Default baseline page.</span></span> <span data-ttu-id="de47f-120">De configuraties worden weergegeven als implementatiestappen.</span><span class="sxs-lookup"><span data-stu-id="de47f-120">The configurations are listed as deployment steps.</span></span> <span data-ttu-id="de47f-121">Selecteer een van de implementatiestappen om de implementatiedetails en de invloed van de gebruiker weer te geven.</span><span class="sxs-lookup"><span data-stu-id="de47f-121">Select any of the deployment steps to view deployment details and user impact.</span></span>

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Schermafbeelding van de standaardpagina basislijn.>.":::

## <a name="deploy-a-baseline-configuration"></a><span data-ttu-id="de47f-123">Een basislijnconfiguratie implementeren</span><span class="sxs-lookup"><span data-stu-id="de47f-123">Deploy a baseline configuration</span></span>  

1. <span data-ttu-id="de47f-124">Selecteer op de linkernavigatiepagina **Tenants om** een lijst met uw onboarded tenants weer te geven.</span><span class="sxs-lookup"><span data-stu-id="de47f-124">In the left navigation page, select **Tenants** to view a list of your onboarded tenants.</span></span>

2. <span data-ttu-id="de47f-125">Selecteer de tenant waar u de basislijnconfiguratie wilt implementeren.</span><span class="sxs-lookup"><span data-stu-id="de47f-125">Select the tenant you want to deploy the baseline configuration to.</span></span>

3. <span data-ttu-id="de47f-126">Selecteer het **tabblad Implementatieplan** om alle implementatiestappen te zien van de basislijn die zijn toegevoegd aan het implementatieplan van de tenant.</span><span class="sxs-lookup"><span data-stu-id="de47f-126">Select the **Deployment plan** tab to see all the deployment steps from the baseline that have been added to the tenant's deployment plan.</span></span>

4. <span data-ttu-id="de47f-127">Selecteer een implementatiestap om de pagina met de implementatiestap te openen.</span><span class="sxs-lookup"><span data-stu-id="de47f-127">Select a deployment step to open the deployment step page.</span></span>

5. <span data-ttu-id="de47f-128">Selecteer **Toepassen** om de geselecteerde implementatiestap toe te passen op de tenant.</span><span class="sxs-lookup"><span data-stu-id="de47f-128">Select **Apply** to apply the selected deployment step to the tenant.</span></span> <span data-ttu-id="de47f-129">Als de implementatiestap 'Voor deze actie is een handmatige stap vereist' wordt aangegeven, moet u de handmatige stap voltooien, zodat de implementatiestap correct wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="de47f-129">If the deployment step indicates "This action requires a manual step", make sure to complete the manual step so the deployment step is applied correctly.</span></span>

## <a name="related-content"></a><span data-ttu-id="de47f-130">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="de47f-130">Related content</span></span>

<span data-ttu-id="de47f-131">[Overzicht van het gebruik van basislijnen voor het implementeren van standaardtenderconfiguraties](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="de47f-131">[Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (article)</span></span>\
<span data-ttu-id="de47f-132">[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="de47f-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>