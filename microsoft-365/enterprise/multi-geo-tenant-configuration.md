---
title: Tenant configuratie voor Microsoft 365 multi-geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: In dit artikel vindt u informatie over het toevoegen van satelliet locaties en het configureren van uw Tenant voor Microsoft 365 multi-geo.
ms.openlocfilehash: 4276d8ff70fed99e74f2cbab29386c81da06d17b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689110"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a><span data-ttu-id="c5e68-103">Tenant configuratie voor Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="c5e68-103">Microsoft 365 Multi-Geo tenant configuration</span></span>

<span data-ttu-id="c5e68-104">Voordat u uw Tenant voor Microsoft 365 multi-geo configureert, moet u ervoor zorgen dat u het [abonnement voor Microsoft 365 multi-geo](plan-for-multi-geo.md)hebt.</span><span class="sxs-lookup"><span data-stu-id="c5e68-104">Before you configure your tenant for Microsoft 365 Multi-Geo, be sure you have read [Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span></span> <span data-ttu-id="c5e68-105">Als u de stappen in dit artikel wilt uitvoeren, hebt u een lijst met de geografische locaties nodig die u wilt inschakelen als satelliet locaties en de test gebruikers die u wilt inrichten voor die locaties.</span><span class="sxs-lookup"><span data-stu-id="c5e68-105">To follow the steps in this article, you'll need a list of the geo locations that you want to enable as satellite locations, and the test users that you want to provision for those locations.</span></span>

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a><span data-ttu-id="c5e68-106">De mogelijkheden voor meervoudige geo in uw Microsoft 365-abonnement aan uw Tenant toevoegen</span><span class="sxs-lookup"><span data-stu-id="c5e68-106">Add the Multi-Geo Capabilities in your Microsoft 365 plan to your tenant</span></span>

<span data-ttu-id="c5e68-107">Als u Microsoft 365 multi-geo wilt gebruiken, hebt u de _mogelijkheden voor meervoudige geo in Microsoft 365_ -abonnement nodig.</span><span class="sxs-lookup"><span data-stu-id="c5e68-107">To use Microsoft 365 Multi-Geo, you need the _Multi-Geo Capabilities in Microsoft 365_ plan.</span></span> <span data-ttu-id="c5e68-108">Werk met uw accountteam om dit abonnement toe te voegen aan uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="c5e68-108">Work with your account team to add this plan to your tenant.</span></span> <span data-ttu-id="c5e68-109">Uw accountteam verbindt u met de juiste licentie specialist en de Tenant is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="c5e68-109">Your account team will connect you with the appropriate licensing specialist and get your tenant configured.</span></span>

<span data-ttu-id="c5e68-110">Houd er rekening mee dat de _mogelijkheden voor meervoudige geo in Microsoft 365 van_ een serviceplan op gebruikersniveau zijn.</span><span class="sxs-lookup"><span data-stu-id="c5e68-110">Note that the _Multi-Geo Capabilities in Microsoft 365_ plan are a user-level service plan.</span></span> <span data-ttu-id="c5e68-111">U hebt een licentie nodig voor elke gebruiker die u wilt hosten op een satelliet locatie.</span><span class="sxs-lookup"><span data-stu-id="c5e68-111">You need a license for each user that you want to host in a satellite location.</span></span> <span data-ttu-id="c5e68-112">U kunt meer licenties toevoegen aan de tijd wanneer u gebruikers toevoegt aan locaties van satellieten.</span><span class="sxs-lookup"><span data-stu-id="c5e68-112">You can add more licenses over time as you add users in satellite locations.</span></span>

<span data-ttu-id="c5e68-113">Wanneer uw Tenant is voorzien van de mogelijkheden voor  _Meervoudige geo in Microsoft 365_ , is het tabblad **geografische locaties** beschikbaar in de OneDrive en SharePoint-beheer centra.</span><span class="sxs-lookup"><span data-stu-id="c5e68-113">Once your tenant has been provisioned with the  _Multi-Geo Capabilities in Microsoft 365_ plan, the **Geo locations** tab will become available in the OneDrive and SharePoint admin centers.</span></span>

## <a name="add-satellite-locations-to-your-tenant"></a><span data-ttu-id="c5e68-114">Satelliet locaties toevoegen aan uw Tenant</span><span class="sxs-lookup"><span data-stu-id="c5e68-114">Add satellite locations to your tenant</span></span>

<span data-ttu-id="c5e68-115">U moet een satelliet locatie toevoegen voor elke geografische locatie waar u gegevens wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="c5e68-115">You must add a satellite location for each geo location where you want to store data.</span></span> <span data-ttu-id="c5e68-116">Beschikbare geografische locaties worden weergegeven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="c5e68-116">Available geo locations are shown in the following table:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Schermafbeelding van de pagina geografische locaties in het SharePoint-Beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="c5e68-118">Een locatie voor satelliet toevoegen</span><span class="sxs-lookup"><span data-stu-id="c5e68-118">To add a satellite location</span></span>

1. <span data-ttu-id="c5e68-119">Open het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="c5e68-119">Open the SharePoint admin center.</span></span>

2. <span data-ttu-id="c5e68-120">Ga naar het tabblad **geo locations** .</span><span class="sxs-lookup"><span data-stu-id="c5e68-120">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="c5e68-121">Klik op **locatie toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c5e68-121">Click **Add location**.</span></span>

4. <span data-ttu-id="c5e68-122">Selecteer de locatie die u wilt toevoegen en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5e68-122">Select the location that you want to add, and then click **Next**.</span></span>

5. <span data-ttu-id="c5e68-123">Typ het domein dat u wilt gebruiken met de geografische locatie en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c5e68-123">Type the domain that you want to use with the geo location, and then click **Add**.</span></span>

6. <span data-ttu-id="c5e68-124">Klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c5e68-124">Click **Close**.</span></span>

<span data-ttu-id="c5e68-125">Het inrichten kan van enkele uren tot 72 uur duren, afhankelijk van de grootte van de Tenant.</span><span class="sxs-lookup"><span data-stu-id="c5e68-125">Provisioning may take from a few hours up to 72 hours, depending on the size of your tenant.</span></span> <span data-ttu-id="c5e68-126">Nadat het inrichten van een satelliet locatie is voltooid, ontvangt u een e-mail bevestiging.</span><span class="sxs-lookup"><span data-stu-id="c5e68-126">Once provisioning of a satellite location has completed, you will receive an email confirmation.</span></span> <span data-ttu-id="c5e68-127">Wanneer de nieuwe geografische locatie blauw wordt weergegeven op de kaart op het tabblad **geografische locaties** in het OneDrive-Beheercentrum, kunt u doorgaan met het instellen van de gewenste gegevenslocatie van gebruikers naar die geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="c5e68-127">When the new geo location appears in blue on the map on the **Geo locations** tab in the OneDrive admin center, you can proceed to set users' preferred data location to that geo location.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c5e68-128">De nieuwe locatie van de satelliet wordt ingesteld met de standaardinstellingen.</span><span class="sxs-lookup"><span data-stu-id="c5e68-128">Your new satellite location will be set up with default settings.</span></span> <span data-ttu-id="c5e68-129">Op die manier kunt u die satelliet locatie zo configureren dat dit van toepassing is op uw lokale nalevings behoeften.</span><span class="sxs-lookup"><span data-stu-id="c5e68-129">This will allow you to configure that satellite location as appropriate for your local compliance needs.</span></span>

## <a name="setting-users-preferred-data-location"></a><span data-ttu-id="c5e68-130">Voorkeur van de gebruikerslocatie van de gebruikers instellen</span><span class="sxs-lookup"><span data-stu-id="c5e68-130">Setting users' preferred data location</span></span>
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

<span data-ttu-id="c5e68-131">Wanneer u de benodigde satelliet locaties hebt ingeschakeld, kunt u uw gebruikersaccounts bijwerken voor gebruik van de juiste gegevenslocatie van uw voorkeur.</span><span class="sxs-lookup"><span data-stu-id="c5e68-131">Once you enable the needed satellite locations, you can update your user accounts to use the appropriate preferred data location.</span></span> <span data-ttu-id="c5e68-132">We raden u aan om voor elke gebruiker een voorkeurs gegevenslocatie in te stellen, ook als deze gebruiker op de centrale locatie woont.</span><span class="sxs-lookup"><span data-stu-id="c5e68-132">We recommend that you set a preferred data location for every user, even if that user is staying in the central location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5e68-133">Als de voorkeurs gegevenslocatie van een gebruiker is ingesteld op een locatie die niet is geconfigureerd als een satelliet locatie of de centrale locatie, wordt het systeem standaard ingesteld op de centrale locatie bij het inrichten van OneDrive-en SharePoint-sites en de groeps postvakken.</span><span class="sxs-lookup"><span data-stu-id="c5e68-133">If a user's preferred data location is set to a location that has not been configured as a satellite location or the central location, the system will default to the central location when provisioning OneDrive and SharePoint sites and Group mailboxes.</span></span>

> [!TIP]
> <span data-ttu-id="c5e68-134">U wordt geadviseerd om op basis van validaties te beginnen met een testgebruiker of een kleine groep gebruikers voordat u meerdere geografische rollen gebruikt voor de bredere organisatie.</span><span class="sxs-lookup"><span data-stu-id="c5e68-134">We recommend that you begin validations with a test user or small group of users before rolling out multi-geo to your broader organization.</span></span>

<span data-ttu-id="c5e68-135">In azure Active Directory (Azure AD) zijn twee soorten gebruikersobjecten: alleen Cloud gebruikers en gesynchroniseerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="c5e68-135">In Azure Active Directory (Azure AD) there are two types of user objects: cloud only users and synchronized users.</span></span> <span data-ttu-id="c5e68-136">Volg de juiste instructies voor uw type gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c5e68-136">Please follow the appropriate instructions for your type of user.</span></span>

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a><span data-ttu-id="c5e68-137">De voorkeurs gegevenslocatie van de gebruiker synchroniseren met Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c5e68-137">Synchronize user's Preferred Data Location using Azure AD Connect</span></span> 

<span data-ttu-id="c5e68-138">Als de gebruikers van uw bedrijf worden gesynchroniseerd vanuit een on-premises Active Directory-systeem naar Azure AD, moet hun PreferredDataLocation worden ingevuld in AD en gesynchroniseerd met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c5e68-138">If your company's users are synchronized from an on-premises Active Directory system to Azure AD, their PreferredDataLocation must be populated in AD and synchronized to Azure AD.</span></span>

<span data-ttu-id="c5e68-139">Volg het proces in [Azure Active Directory Connect Sync: Configureer de gewenste gegevenslocatie voor Microsoft 365-bronnen](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) om de synchronisatie van de gewenste gegevenslocatie te configureren vanuit uw on-premises Active Directory Domain Services (AD DS) naar Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c5e68-139">Follow the process in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) to configure Preferred Data Location sync from your on-premises Active Directory Domain Services (AD DS) to Azure AD.</span></span>

<span data-ttu-id="c5e68-140">U wordt aangeraden de voorkeurs gegevenslocatie van de gebruiker in te stellen als onderdeel van uw standaard werkstroom voor het maken van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="c5e68-140">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5e68-141">Als er nieuwe gebruikers zijn met geen OneDrive-ingerichte, wacht u minstens 24 uur nadat de PDL van een gebruiker is gesynchroniseerd met Azure AD zodat de wijzigingen worden doorgevoerd voordat de gebruiker zich aanmeldt bij OneDrive voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="c5e68-141">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is synchronized to Azure AD for the changes to propagate before the user logs in to OneDrive for Business.</span></span> <span data-ttu-id="c5e68-142">(Wanneer de gebruiker zich aanmeldt voor het instellen van de locatie van OneDrive voor bedrijven, kunt u het beste de nieuwe OneDrive van de gebruiker op de juiste locatie inrichten).</span><span class="sxs-lookup"><span data-stu-id="c5e68-142">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

### <a name="setting-preferred-data-location-for-cloud-only-users"></a><span data-ttu-id="c5e68-143">Voorkeurs gegevenslocatie instellen voor gebruikers met Cloud only</span><span class="sxs-lookup"><span data-stu-id="c5e68-143">Setting Preferred Data Location for cloud only users</span></span> 

<span data-ttu-id="c5e68-144">Als de gebruikers van uw bedrijf niet worden gesynchroniseerd vanuit een on-premises Active Directory-systeem naar Azure AD, betekent dit dat ze zijn gemaakt in Microsoft 365 of Azure AD en moet de PDL-module van de Microsoft Azure Active Directory-module voor Windows PowerShell worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="c5e68-144">If your company's users are not synchronized from an on-premises Active Directory system to Azure AD, meaning they are created in Microsoft 365 or Azure AD, then the PDL must be set using the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="c5e68-145">Voor de procedures in deze sectie is de [Microsoft Azure Active Directory-module voor Windows PowerShell module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0)vereist.</span><span class="sxs-lookup"><span data-stu-id="c5e68-145">The procedures in this section require the [Microsoft Azure Active Directory Module for Windows PowerShell Module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span></span> <span data-ttu-id="c5e68-146">Als u deze module al hebt geïnstalleerd, moet u ervoor zorgen dat u de nieuwste versie bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="c5e68-146">If you already have this module installed, please ensure you update to the latest version.</span></span>

1.  <span data-ttu-id="c5e68-147">[Maak verbinding en meld](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) u aan met een set globale beheerdersreferenties voor uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="c5e68-147">[Connect and sign in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) with a set of global administrator credentials for your tenant.</span></span>

2.  <span data-ttu-id="c5e68-148">U kunt de [set-MsolUser-](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) cmdlet gebruiken om de voorkeurs gegevenslocatie voor alle gebruikers in te stellen.</span><span class="sxs-lookup"><span data-stu-id="c5e68-148">Use the [Set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) cmdlet to set the preferred data location for each of your users.</span></span> <span data-ttu-id="c5e68-149">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c5e68-149">For example:</span></span>

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    <span data-ttu-id="c5e68-150">Met de cmdlet Get-MsolUser kunt u controleren of de locatie van de voorkeurs gegevens juist is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="c5e68-150">You can check to confirm that the preferred data location was updated properly by using the Get-MsolUser cmdlet.</span></span> <span data-ttu-id="c5e68-151">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c5e68-151">For example:</span></span>

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Schermafbeelding van het PowerShell-venster met set-msoluser](../media/multi-geo-tenant-configuration-image3.png)

<span data-ttu-id="c5e68-153">U wordt aangeraden de voorkeurs gegevenslocatie van de gebruiker in te stellen als onderdeel van uw standaard werkstroom voor het maken van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="c5e68-153">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5e68-154">Als er nieuwe gebruikers zijn met geen OneDrive, wacht u minstens 24 uur nadat de PDL van een gebruiker is ingesteld op de wijzigingen doorgeven voordat de gebruiker zich aanmeldt bij OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c5e68-154">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is set for the changes to propagate before the user logs in to OneDrive.</span></span> <span data-ttu-id="c5e68-155">(Wanneer de gebruiker zich aanmeldt voor het instellen van de locatie van OneDrive voor bedrijven, kunt u het beste de nieuwe OneDrive van de gebruiker op de juiste locatie inrichten).</span><span class="sxs-lookup"><span data-stu-id="c5e68-155">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a><span data-ttu-id="c5e68-156">OneDrive inrichten en het effect van PDL</span><span class="sxs-lookup"><span data-stu-id="c5e68-156">OneDrive Provisioning and the effect of PDL</span></span>

<span data-ttu-id="c5e68-157">Als de gebruiker al een OneDrive-site in de Tenant heeft gemaakt, wordt de bestaande OneDrive niet automatisch verplaatst via de team site.</span><span class="sxs-lookup"><span data-stu-id="c5e68-157">If the user already has a OneDrive site created in the tenant, setting their PDL will not automatically move their existing OneDrive.</span></span> <span data-ttu-id="c5e68-158">Als u OneDrive van een gebruiker wilt verplaatsen, raadpleegt u [overstappen op onedrive voor bedrijven](move-onedrive-between-geo-locations.md) en volgt u de instructies in onedrive verplaatsen tussen geo-locaties.</span><span class="sxs-lookup"><span data-stu-id="c5e68-158">To move a user's OneDrive, see [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md) please follow the instructions in Moving OneDrive between geo locations.</span></span> <span data-ttu-id="c5e68-159">(Houd er rekening mee dat het Exchange-postvak van de gebruiker automatisch wordt verplaatst wanneer u de PDL van de gebruiker instelt.)</span><span class="sxs-lookup"><span data-stu-id="c5e68-159">(Note that the user's Exchange mailbox does move automatically when you set the user's PDL.)</span></span>

<span data-ttu-id="c5e68-160">Als de gebruiker geen OneDrive-site in de Tenant heeft, wordt deze in overeenstemming met hun PDL-waarde ingericht, op voorwaarde dat de PDL voor de gebruiker overeenkomt met een van de satelliet locaties van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="c5e68-160">If the user does not have a OneDrive site within the tenant, OneDrive will be provisioned for them in accordance to their PDL value, assuming the PDL for the user matches one of the company's satellite locations.</span></span>

## <a name="configuring-multi-geo-search"></a><span data-ttu-id="c5e68-161">Meerdere geografische zoekopdrachten configureren</span><span class="sxs-lookup"><span data-stu-id="c5e68-161">Configuring Multi-Geo search</span></span>

<span data-ttu-id="c5e68-162">Uw Tenant voor meervoudige geo-en zoekmogelijkheden biedt een zoekopdracht waarmee een zoekopdracht de resultaten van een willekeurige plaats binnen de Tenant kan retourneren.</span><span class="sxs-lookup"><span data-stu-id="c5e68-162">Your multi-geo tenant will have aggregate search capabilities allowing a search query to return results from anywhere within the tenant.</span></span>

<span data-ttu-id="c5e68-163">Standaard worden in zoekresultaten samengestelde resultaten geretourneerd, zelfs als elke zoekindex zich in de betreffende geografische locatie bevindt:</span><span class="sxs-lookup"><span data-stu-id="c5e68-163">By default, searches from these entry points will return aggregate results, even though each search index is located within its relevant geo location:</span></span>

- <span data-ttu-id="c5e68-164">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="c5e68-164">OneDrive for Business</span></span>

- <span data-ttu-id="c5e68-165">Delve</span><span class="sxs-lookup"><span data-stu-id="c5e68-165">Delve</span></span>

- <span data-ttu-id="c5e68-166">SharePoint-Startpagina</span><span class="sxs-lookup"><span data-stu-id="c5e68-166">SharePoint Home</span></span>

- <span data-ttu-id="c5e68-167">Zoekcentrum</span><span class="sxs-lookup"><span data-stu-id="c5e68-167">Search Center</span></span>

<span data-ttu-id="c5e68-168">U kunt ook de zoekfuncties voor meervoudige geo configureren voor uw aangepaste zoektoepassingen die gebruikmaken van de SharePoint-zoek-API.</span><span class="sxs-lookup"><span data-stu-id="c5e68-168">Additionally, multi-geo search capabilities can be configured for your custom search applications that use the SharePoint search API.</span></span>

<span data-ttu-id="c5e68-169">Kijk voor meer informatie [over het configureren van de zoekfunctie voor OneDrive voor bedrijven,](configure-search-for-multi-geo.md) waaronder eventuele beperkingen en verschillen.</span><span class="sxs-lookup"><span data-stu-id="c5e68-169">Please review [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for instructions including any limitations and differences.</span></span>

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a><span data-ttu-id="c5e68-170">De configuratie van Microsoft 365 meerdere geo-geografische configuraties valideren</span><span class="sxs-lookup"><span data-stu-id="c5e68-170">Validating the Microsoft 365 Multi-Geo configuration</span></span>

<span data-ttu-id="c5e68-171">Hieronder vindt u enkele basis situaties die u mogelijk wilt opnemen in uw validatie plan voordat u Microsoft 365 meerdere geografische rollen uitvoert voor uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="c5e68-171">Below are some basic use cases you may wish to include in your validation plan before broadly rolling out Microsoft 365 Multi-Geo to your company.</span></span> <span data-ttu-id="c5e68-172">Wanneer u deze tests en eventuele extra use cases die relevant zijn voor uw bedrijf hebt voltooid, kunt u ervoor kiezen om de gebruikers toe te voegen aan de aanvankelijke testgroep.</span><span class="sxs-lookup"><span data-stu-id="c5e68-172">Once you have completed these tests and any additional use cases that are relevant to your company, you may choose to move on to adding the users in your initial pilot group.</span></span>

<span data-ttu-id="c5e68-173">**OneDrive voor Bedrijven**</span><span class="sxs-lookup"><span data-stu-id="c5e68-173">**OneDrive for Business**</span></span>

<span data-ttu-id="c5e68-174">Selecteer OneDrive in het startprogramma voor apps van Microsoft 365 en bevestig dat u automatisch wordt doorgestuurd naar de juiste geografische locatie voor de gebruiker, op basis van de PDL van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c5e68-174">Select OneDrive from the Microsoft 365 app launcher and confirm that you are automatically directed to the appropriate geo location for the user, based on the user's PDL.</span></span> <span data-ttu-id="c5e68-175">OneDrive voor bedrijven moet nu op die locatie beginnen met inrichten.</span><span class="sxs-lookup"><span data-stu-id="c5e68-175">OneDrive for Business should now begin provisioning at that location.</span></span> <span data-ttu-id="c5e68-176">Probeer een aantal documenten te uploaden en te downloaden als u dit hebt ingericht.</span><span class="sxs-lookup"><span data-stu-id="c5e68-176">Once provisioned, try uploading and downloading some documents.</span></span>

<span data-ttu-id="c5e68-177">**Mobiele OneDrive-app**</span><span class="sxs-lookup"><span data-stu-id="c5e68-177">**OneDrive Mobile App**</span></span>

<span data-ttu-id="c5e68-178">Meld u aan bij uw mobiele OneDrive-app met de referenties van uw testaccount.</span><span class="sxs-lookup"><span data-stu-id="c5e68-178">Log into your OneDrive mobile App with your test account credentials.</span></span> <span data-ttu-id="c5e68-179">Ga na of u de bestanden van OneDrive voor bedrijven kunt zien en er met ze op kunt werken vanaf uw mobiele apparaat.</span><span class="sxs-lookup"><span data-stu-id="c5e68-179">Confirm that you can see your OneDrive for Business files and can interact with them from your mobile device.</span></span>

<span data-ttu-id="c5e68-180">**OneDrive-synchronisatieclient**</span><span class="sxs-lookup"><span data-stu-id="c5e68-180">**OneDrive sync client**</span></span>

<span data-ttu-id="c5e68-181">Ga na of de OneDrive-synchronisatieclient automatisch de geo-locatie van OneDrive voor bedrijven detecteert wanneer u zich aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="c5e68-181">Confirm that the OneDrive sync client automatically detects your OneDrive for Business geo location upon login.</span></span> <span data-ttu-id="c5e68-182">Als u de synchronisatieclient moet downloaden, kunt u op **synchroniseren** klikken in de OneDrive-bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="c5e68-182">If you need to download the sync client, you can click **Sync** in the OneDrive library.</span></span>

<span data-ttu-id="c5e68-183">**Office-toepassingen**</span><span class="sxs-lookup"><span data-stu-id="c5e68-183">**Office applications**</span></span>

<span data-ttu-id="c5e68-184">Ga na of u toegang hebt tot OneDrive voor bedrijven door u aan te melden bij een Office-toepassing, zoals Word.</span><span class="sxs-lookup"><span data-stu-id="c5e68-184">Confirm that you can access OneDrive for Business by logging in from an Office application, such as Word.</span></span> <span data-ttu-id="c5e68-185">Open de Office-toepassing en selecteer OneDrive- <TenantName> .</span><span class="sxs-lookup"><span data-stu-id="c5e68-185">Open the Office application and select "OneDrive – <TenantName>".</span></span> <span data-ttu-id="c5e68-186">Uw OneDrive-locatie wordt door Office herkend en u ziet de bestanden die u kunt openen.</span><span class="sxs-lookup"><span data-stu-id="c5e68-186">Office will detect your OneDrive location and show you the files that you can open.</span></span>

<span data-ttu-id="c5e68-187">**Delen**</span><span class="sxs-lookup"><span data-stu-id="c5e68-187">**Sharing**</span></span>

<span data-ttu-id="c5e68-188">Probeer OneDrive-bestanden te delen.</span><span class="sxs-lookup"><span data-stu-id="c5e68-188">Try sharing OneDrive files.</span></span> <span data-ttu-id="c5e68-189">Ga na of de persoon kiezen al uw SharePoint Online-gebruikers ziet, ongeacht hun geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="c5e68-189">Confirm that the people picker shows you all your SharePoint online users regardless of their geo location.</span></span>
