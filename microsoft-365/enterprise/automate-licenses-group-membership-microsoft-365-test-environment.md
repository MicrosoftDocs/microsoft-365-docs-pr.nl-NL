---
title: Licentie en groepslidmaatschap voor uw Microsoft 365 voor Enterprise testomgeving automatiseren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configureer licenties voor op groepen gebaseerde licenties en groepslidmaatschap voor dynamische groepen in uw Microsoft 365 voor Enterprise testomgeving.
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685556"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="eeb0e-103">Licentie en groepslidmaatschap voor uw Microsoft 365 voor Enterprise testomgeving automatiseren</span><span class="sxs-lookup"><span data-stu-id="eeb0e-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="eeb0e-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="eeb0e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="eeb0e-105">Voor licenties op basis van een groep worden automatisch licenties toegewezen of verwijderd voor een gebruikersaccount op basis van groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="eeb0e-106">Groepslidmaatschap voor dynamische groepen Hiermee voegt u leden toe of verwijdert u deze aan een groep op basis van de eigenschappen van gebruikersaccounts, zoals afdeling of land.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="eeb0e-107">In dit artikel wordt u stapsgewijs begeleid bij het uitvoeren van de testomgeving van Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-107">This article steps you through a demonstration of both in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="eeb0e-108">Voor het instellen van automatische licentieverlening en dynamisch groepslidmaatschap in uw Microsoft 365 voor Enterprise testomgeving bestaan twee fasen:</span><span class="sxs-lookup"><span data-stu-id="eeb0e-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="eeb0e-109">Maak de testomgeving Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-109">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="eeb0e-110">Dynamische groepslidmaatschappen en automatische licentieverlening configureren en testen.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="eeb0e-112">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="eeb0e-113">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="eeb0e-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="eeb0e-114">Als u alleen de automatische licentieverlening en groepslidmaatschap op een lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="eeb0e-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="eeb0e-115">Als u automatische licentieverlening en groepslidmaatschap in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="eeb0e-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eeb0e-116">Voor het testen van de geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="eeb0e-117">U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="eeb0e-118">Fase 2: dynamisch groepslidmaatschap en automatische licentie configureren en testen</span><span class="sxs-lookup"><span data-stu-id="eeb0e-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="eeb0e-119">Eerst maakt u een nieuwe verkoopgroep en voegt u een regel voor dynamische groepslidmaatschappen toe, zodat gebruikersaccounts waarbij de afdeling is ingesteld op verkoop, automatisch worden toegevoegd aan de groep verkopen.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="eeb0e-120">Meld u met een persoonlijk exemplaar van uw Internet browser aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met het account van de globale beheerder van uw abonnement op microsoft 365 E5-test lab.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-120">Using a private instance of your Internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="eeb0e-121">Ga op een apart tabblad van uw browser naar de Azure-Portal op [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="eeb0e-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="eeb0e-122">Typ in het dialoogvenster van Azure Portal **groepen** in het zoekvak en klik vervolgens op **groepen**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="eeb0e-123">Klik in het deelvenster **alle groepen** op **nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="eeb0e-124">Selecteer bij **type groep**de optie **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="eeb0e-125">Typ in **groepsnaam** **verkopen**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="eeb0e-126">Selecteer **dynamische gebruiker**bij **type lidmaatschap**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="eeb0e-127">Klik op **dynamische gebruikers leden**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="eeb0e-128">In het deelvenster **dynamische lidmaatschapsregels** :</span><span class="sxs-lookup"><span data-stu-id="eeb0e-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="eeb0e-129">Selecteer de eigenschap **afdeling** .</span><span class="sxs-lookup"><span data-stu-id="eeb0e-129">Select the **department** property.</span></span>
   - <span data-ttu-id="eeb0e-130">Selecteer de operator **gelijkteken** .</span><span class="sxs-lookup"><span data-stu-id="eeb0e-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="eeb0e-131">Typ **verkoop** in **waarde**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="eeb0e-132">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-132">Click **Save**.</span></span>
11. <span data-ttu-id="eeb0e-133">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-133">Click **Create**.</span></span>

<span data-ttu-id="eeb0e-134">Vervolgens configureert u de groep verkoop, zodat leden automatisch de Microsoft 365 E5-licentie toewijzen.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="eeb0e-135">Klik op de groep **verkoop** en klik vervolgens op **licenties**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="eeb0e-136">Selecteer in het deelvenster **licentietoewijzingen bijwerken** de optie **Microsoft 365 E5**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="eeb0e-137">Sluit het tabblad Microsoft Azure-portal in uw browser.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="eeb0e-138">Test vervolgens dynamisch groepslidmaatschap en automatische licentieverlening op de account gebruiker 4.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="eeb0e-139">Klik op het tabblad **Start van Microsoft Office** in uw browser op **beheerder**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="eeb0e-140">Klik op het tabblad **Microsoft 365-Beheercentrum** op **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="eeb0e-141">Klik op de pagina **actieve gebruikers** op de account **gebruiker 4** .</span><span class="sxs-lookup"><span data-stu-id="eeb0e-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="eeb0e-142">Klik in het deelvenster **gebruiker 4** op **bewerken** voor **product licenties**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="eeb0e-143">Schakel in het deelvenster **product licenties** de **Microsoft 365 E5** -licentie uit en klik op **Opslaan > sluiten**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="eeb0e-144">Ga naar de eigenschappen van de account van de gebruiker 4 en zorg dat er geen productlicenties zijn toegewezen en dat er geen groepslidmaatschappen zijn.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="eeb0e-145">Klik op **bewerken** voor **contact gegevens**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="eeb0e-146">Klik in het deelvenster **contactgegevens bewerken** op **contactgegevens**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="eeb0e-147">In het veld **afdeling** typt u **verkoop**en klikt u op **Opslaan > sluiten**.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="eeb0e-148">Wacht een paar minuten en klik vervolgens regelmatig op het pictogram Vernieuwen in de rechterbovenhoek van het deelvenster account van gebruiker 4.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="eeb0e-149">U ziet nu het volgende:</span><span class="sxs-lookup"><span data-stu-id="eeb0e-149">In time you should see the:</span></span>

- <span data-ttu-id="eeb0e-150">De eigenschap **groepslidmaatschappen** bijgewerkt met de groep **verkoop** .</span><span class="sxs-lookup"><span data-stu-id="eeb0e-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="eeb0e-151">Eigenschap **product licenties** bijgewerkt met de **Microsoft 365 E5** -licentie.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="eeb0e-152">Zie de volgende artikelen voor meer informatie over het implementeren van dynamische groepslidmaatschappen en automatische licentieverlening in de productie:</span><span class="sxs-lookup"><span data-stu-id="eeb0e-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- <span data-ttu-id="eeb0e-153">TBD AANKOPPELEN</span><span class="sxs-lookup"><span data-stu-id="eeb0e-153">LINK TBD</span></span>
- <span data-ttu-id="eeb0e-154">TBD AANKOPPELEN</span><span class="sxs-lookup"><span data-stu-id="eeb0e-154">LINK TBD</span></span>

## <a name="next-step"></a><span data-ttu-id="eeb0e-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="eeb0e-155">Next step</span></span>

<span data-ttu-id="eeb0e-156">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="eeb0e-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="eeb0e-157">Zie ook</span><span class="sxs-lookup"><span data-stu-id="eeb0e-157">See also</span></span>

[<span data-ttu-id="eeb0e-158">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="eeb0e-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="eeb0e-159">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="eeb0e-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="eeb0e-160">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="eeb0e-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="eeb0e-161">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="eeb0e-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
