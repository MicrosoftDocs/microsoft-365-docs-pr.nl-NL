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
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487574"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ad0f4-103">Licentie en groepslidmaatschap voor uw Microsoft 365 voor Enterprise testomgeving automatiseren</span><span class="sxs-lookup"><span data-stu-id="ad0f4-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ad0f4-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="ad0f4-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ad0f4-105">Voor licenties op basis van een groep worden automatisch licenties toegewezen of verwijderd voor een gebruikersaccount op basis van groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="ad0f4-106">Groepslidmaatschap voor dynamische groepen Hiermee voegt u leden toe of verwijdert u deze aan een groep op basis van de eigenschappen van gebruikersaccounts, zoals **afdeling** of **land**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="ad0f4-107">In dit artikel wordt u stapsgewijs begeleid bij het toevoegen en verwijderen van groepsleden in uw Microsoft 365 voor Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="ad0f4-108">Het instellen van automatische licentieverlening en dynamisch groepslidmaatschap in uw Microsoft 365 voor Enterprise-testomgeving bestaat uit twee fasen:</span><span class="sxs-lookup"><span data-stu-id="ad0f4-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="ad0f4-109">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="ad0f4-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ad0f4-110">Fase 2: dynamisch groepslidmaatschap en automatische licentie configureren en testen</span><span class="sxs-lookup"><span data-stu-id="ad0f4-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ad0f4-112">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ad0f4-113">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="ad0f4-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ad0f4-114">Als u de geautomatiseerde licentie en groepslidmaatschap op een zeer lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ad0f4-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ad0f4-115">Als u automatische licentieverlening en groepslidmaatschap in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ad0f4-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad0f4-116">Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ad0f4-117">Dit wordt hier als optie geboden, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="ad0f4-118">Fase 2: dynamisch groepslidmaatschap en automatische licentie configureren en testen</span><span class="sxs-lookup"><span data-stu-id="ad0f4-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="ad0f4-119">Eerst maakt u een nieuwe groep genaamd verkoop en voegt u een regel voor dynamische groepslidmaatschappen toe, zodat gebruikersaccounts waarbij de **afdeling** is ingesteld op **verkoop** automatisch worden toegevoegd aan de verkoopgroep.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="ad0f4-120">Meld u in een privé-exemplaar van uw internetbrowser aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met het account van de globale beheerder van uw abonnement op microsoft 365 E5-test lab.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="ad0f4-121">Ga op een apart tabblad van uw browser naar de Azure-Portal op [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="ad0f4-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="ad0f4-122">Voer in het vak Zoeken in de Azure-Portal **groepen** in en selecteer **groepen**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="ad0f4-123">Selecteer in het deelvenster **alle groepen** de optie **nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="ad0f4-124">Selecteer bij **type groep**de optie **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="ad0f4-125">Voer in **groepsnaam** **verkopen**in.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="ad0f4-126">Selecteer **dynamische gebruiker**bij **type lidmaatschap**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="ad0f4-127">Selecteer **dynamische gebruikers leden**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="ad0f4-128">In het deelvenster **dynamische lidmaatschapsregels** :</span><span class="sxs-lookup"><span data-stu-id="ad0f4-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="ad0f4-129">Selecteer de eigenschap **afdeling** .</span><span class="sxs-lookup"><span data-stu-id="ad0f4-129">Select the **department** property.</span></span>
   - <span data-ttu-id="ad0f4-130">Selecteer de operator **gelijkteken** .</span><span class="sxs-lookup"><span data-stu-id="ad0f4-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="ad0f4-131">Voer in het vak **waarde de waarde** **verkoop**in.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="ad0f4-132">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-132">Select **Save**.</span></span>
11. <span data-ttu-id="ad0f4-133">Selecteer **Maken**. </span><span class="sxs-lookup"><span data-stu-id="ad0f4-133">Select **Create**.</span></span>

<span data-ttu-id="ad0f4-134">Vervolgens configureert u de groep verkoop, zodat leden automatisch de Microsoft 365 E5-licentie toewijzen.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="ad0f4-135">Selecteer de groep **verkoop** en selecteer vervolgens **licenties**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="ad0f4-136">Selecteer in het deelvenster **licentietoewijzingen bijwerken** de optie **Microsoft 365 E5**en selecteer vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="ad0f4-137">Sluit het tabblad Azure Portal in de browser.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="ad0f4-138">Test vervolgens dynamisch groepslidmaatschap en automatische licentieverlening van de account gebruiker 4:</span><span class="sxs-lookup"><span data-stu-id="ad0f4-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="ad0f4-139">Selecteer op het tabblad **Start van Microsoft Office** in uw browser de optie **beheerder**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="ad0f4-140">Selecteer **actieve gebruikers**op het tabblad **Microsoft 365-Beheercentrum** .</span><span class="sxs-lookup"><span data-stu-id="ad0f4-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="ad0f4-141">Selecteer het account van de **gebruiker 4** op de pagina **actieve gebruikers** .</span><span class="sxs-lookup"><span data-stu-id="ad0f4-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="ad0f4-142">Selecteer in het deelvenster **gebruiker 4** de optie **bewerken** voor **product licenties**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="ad0f4-143">In het deelvenster **product licenties** schakelt u de **Microsoft 365 E5** -licentie uit **en selecteert u**vervolgens  >  **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="ad0f4-144">Ga naar de eigenschappen van de account van de gebruiker 4 en zorg dat er geen productlicenties zijn toegewezen en dat er geen groepslidmaatschappen zijn.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="ad0f4-145">Selecteer voor **contact gegevens**de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="ad0f4-146">Selecteer in het deelvenster **contactgegevens bewerken** de optie **contactgegevens**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="ad0f4-147">Voer in het vak **afdeling** de optie **verkoop**in **en selecteer vervolgens**  >  **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="ad0f4-148">Wacht een paar minuten en selecteer vervolgens periodiek het pictogram **vernieuwen** in de rechterbovenhoek van het deelvenster account van gebruiker 4.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="ad0f4-149">Voor tijd ziet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="ad0f4-149">In time, you should see the:</span></span>

- <span data-ttu-id="ad0f4-150">De eigenschap **groepslidmaatschappen** bijgewerkt met de groep **verkoop** .</span><span class="sxs-lookup"><span data-stu-id="ad0f4-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="ad0f4-151">Eigenschap **product licenties** bijgewerkt met de **Microsoft 365 E5** -licentie.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="ad0f4-152">Zie de volgende artikelen voor meer informatie over het implementeren van dynamische groepslidmaatschappen en automatische licentieverlening in de productie:</span><span class="sxs-lookup"><span data-stu-id="ad0f4-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="ad0f4-153">Op groepen gebaseerde licentieverlening in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ad0f4-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="ad0f4-154">Dynamische groepen in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ad0f4-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="ad0f4-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ad0f4-155">Next step</span></span>

<span data-ttu-id="ad0f4-156">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="ad0f4-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad0f4-157">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ad0f4-157">See also</span></span>

[<span data-ttu-id="ad0f4-158">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="ad0f4-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="ad0f4-159">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="ad0f4-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ad0f4-160">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="ad0f4-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ad0f4-161">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="ad0f4-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
