---
title: Microsoft 365 Multi-Geo tenantconfiguratie
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
description: In dit artikel leert u hoe u satellietlocaties toevoegt en uw tenant configureert voor Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9176c66e8d0aa7e893ef137131147f8e0c85d3ac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923646"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a><span data-ttu-id="d39ae-103">Microsoft 365 Multi-Geo tenantconfiguratie</span><span class="sxs-lookup"><span data-stu-id="d39ae-103">Microsoft 365 Multi-Geo tenant configuration</span></span>

<span data-ttu-id="d39ae-104">Voordat u uw tenant configureert voor Microsoft 365 [Multi-Geo, moet u Plan voor Microsoft 365 Multi-Geo hebben gelezen.](plan-for-multi-geo.md)</span><span class="sxs-lookup"><span data-stu-id="d39ae-104">Before you configure your tenant for Microsoft 365 Multi-Geo, be sure you have read [Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span></span> <span data-ttu-id="d39ae-105">Als u de stappen in dit artikel wilt volgen, hebt u een lijst nodig met de geografische locaties die u wilt inschakelen als satellietlocaties en de testgebruikers die u wilt inrichten voor die locaties.</span><span class="sxs-lookup"><span data-stu-id="d39ae-105">To follow the steps in this article, you'll need a list of the geo locations that you want to enable as satellite locations, and the test users that you want to provision for those locations.</span></span>

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a><span data-ttu-id="d39ae-106">De multi-geo-mogelijkheden in uw Microsoft 365-abonnement toevoegen aan uw tenant</span><span class="sxs-lookup"><span data-stu-id="d39ae-106">Add the Multi-Geo Capabilities in your Microsoft 365 plan to your tenant</span></span>

<span data-ttu-id="d39ae-107">Als u Microsoft 365 Multi-Geo wilt gebruiken, hebt u de _Multi-Geo-mogelijkheden in microsoft 365-abonnement_ nodig.</span><span class="sxs-lookup"><span data-stu-id="d39ae-107">To use Microsoft 365 Multi-Geo, you need the _Multi-Geo Capabilities in Microsoft 365_ plan.</span></span> <span data-ttu-id="d39ae-108">Werk samen met uw accountteam om dit plan toe te voegen aan uw tenant.</span><span class="sxs-lookup"><span data-stu-id="d39ae-108">Work with your account team to add this plan to your tenant.</span></span> <span data-ttu-id="d39ae-109">Uw accountteam verbindt u met de juiste licentiespecialist en laat uw tenant configureren.</span><span class="sxs-lookup"><span data-stu-id="d39ae-109">Your account team will connect you with the appropriate licensing specialist and get your tenant configured.</span></span>

<span data-ttu-id="d39ae-110">Houd er rekening _mee dat de Multi-Geo Capabilities in Microsoft 365-abonnement_ een serviceplan op gebruikersniveau zijn.</span><span class="sxs-lookup"><span data-stu-id="d39ae-110">Note that the _Multi-Geo Capabilities in Microsoft 365_ plan are a user-level service plan.</span></span> <span data-ttu-id="d39ae-111">U hebt een licentie nodig voor elke gebruiker die u wilt hosten op een satellietlocatie.</span><span class="sxs-lookup"><span data-stu-id="d39ae-111">You need a license for each user that you want to host in a satellite location.</span></span> <span data-ttu-id="d39ae-112">U kunt in de tijd meer licenties toevoegen als u gebruikers toevoegt op satellietlocaties.</span><span class="sxs-lookup"><span data-stu-id="d39ae-112">You can add more licenses over time as you add users in satellite locations.</span></span>

<span data-ttu-id="d39ae-113">Zodra uw tenant is ingericht met de  _multi-geo-mogelijkheden in microsoft 365-abonnement,_ wordt het tabblad Geolocaties beschikbaar in de OneDrive- en SharePoint-beheercentra.</span><span class="sxs-lookup"><span data-stu-id="d39ae-113">Once your tenant has been provisioned with the  _Multi-Geo Capabilities in Microsoft 365_ plan, the **Geo locations** tab will become available in the OneDrive and SharePoint admin centers.</span></span>

## <a name="add-satellite-locations-to-your-tenant"></a><span data-ttu-id="d39ae-114">Satellietlocaties toevoegen aan uw tenant</span><span class="sxs-lookup"><span data-stu-id="d39ae-114">Add satellite locations to your tenant</span></span>

<span data-ttu-id="d39ae-115">U moet een satellietlocatie toevoegen voor elke geografische locatie waar u gegevens wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="d39ae-115">You must add a satellite location for each geo location where you want to store data.</span></span> <span data-ttu-id="d39ae-116">Beschikbare geografische locaties worden weergegeven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="d39ae-116">Available geo locations are shown in the following table:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Schermafbeelding van de pagina geolocaties in het SharePoint-beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="d39ae-118">Een satellietlocatie toevoegen</span><span class="sxs-lookup"><span data-stu-id="d39ae-118">To add a satellite location</span></span>

1. <span data-ttu-id="d39ae-119">Open het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d39ae-119">Open the SharePoint admin center.</span></span>

2. <span data-ttu-id="d39ae-120">Ga naar het **tabblad Geolocaties.**</span><span class="sxs-lookup"><span data-stu-id="d39ae-120">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="d39ae-121">Klik **op Locatie toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d39ae-121">Click **Add location**.</span></span>

4. <span data-ttu-id="d39ae-122">Selecteer de locatie die u wilt toevoegen en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="d39ae-122">Select the location that you want to add, and then click **Next**.</span></span>

5. <span data-ttu-id="d39ae-123">Typ het domein dat u wilt gebruiken met de geografische locatie en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d39ae-123">Type the domain that you want to use with the geo location, and then click **Add**.</span></span>

6. <span data-ttu-id="d39ae-124">Klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d39ae-124">Click **Close**.</span></span>

<span data-ttu-id="d39ae-125">Inrichting kan enkele uren tot 72 uur duren, afhankelijk van de grootte van uw tenant.</span><span class="sxs-lookup"><span data-stu-id="d39ae-125">Provisioning may take from a few hours up to 72 hours, depending on the size of your tenant.</span></span> <span data-ttu-id="d39ae-126">Wanneer de inrichting van een satellietlocatie is voltooid, ontvangt u een bevestiging per e-mail.</span><span class="sxs-lookup"><span data-stu-id="d39ae-126">Once provisioning of a satellite location has completed, you will receive an email confirmation.</span></span> <span data-ttu-id="d39ae-127">Wanneer de nieuwe geografische locatie blauw wordt  weergegeven op de kaart op het tabblad Geolocaties in het OneDrive-beheercentrum, kunt u doorgaan met het instellen van de gewenste gegevenslocatie van gebruikers op die geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="d39ae-127">When the new geo location appears in blue on the map on the **Geo locations** tab in the OneDrive admin center, you can proceed to set users' preferred data location to that geo location.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d39ae-128">Uw nieuwe satellietlocatie wordt ingesteld met standaardinstellingen.</span><span class="sxs-lookup"><span data-stu-id="d39ae-128">Your new satellite location will be set up with default settings.</span></span> <span data-ttu-id="d39ae-129">Op deze manier kunt u die satellietlocatie zo configureren dat deze geschikt is voor uw lokale nalevingsbehoeften.</span><span class="sxs-lookup"><span data-stu-id="d39ae-129">This will allow you to configure that satellite location as appropriate for your local compliance needs.</span></span>

## <a name="setting-users-preferred-data-location"></a><span data-ttu-id="d39ae-130">De gewenste gegevenslocatie van gebruikers instellen</span><span class="sxs-lookup"><span data-stu-id="d39ae-130">Setting users' preferred data location</span></span>
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

<span data-ttu-id="d39ae-131">Nadat u de benodigde satellietlocaties hebt ingeschakeld, kunt u uw gebruikersaccounts bijwerken om de gewenste gegevenslocatie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d39ae-131">Once you enable the needed satellite locations, you can update your user accounts to use the appropriate preferred data location.</span></span> <span data-ttu-id="d39ae-132">We raden u aan een voorkeurslocatie voor gegevens in te stellen voor elke gebruiker, zelfs als deze gebruiker zich op de centrale locatie bevindt.</span><span class="sxs-lookup"><span data-stu-id="d39ae-132">We recommend that you set a preferred data location for every user, even if that user is staying in the central location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d39ae-133">Als de gewenste gegevenslocatie van een gebruiker is ingesteld op een locatie die niet is geconfigureerd als een satellietlocatie of de centrale locatie, wordt het systeem standaard op de centrale locatie ingesteld bij het inrichten van OneDrive- en SharePoint-sites en Groepspostvakken.</span><span class="sxs-lookup"><span data-stu-id="d39ae-133">If a user's preferred data location is set to a location that has not been configured as a satellite location or the central location, the system will default to the central location when provisioning OneDrive and SharePoint sites and Group mailboxes.</span></span>

> [!TIP]
> <span data-ttu-id="d39ae-134">U wordt aangeraden validaties te starten met een testgebruiker of een kleine groep gebruikers voordat u multi-geo uitrolt naar uw bredere organisatie.</span><span class="sxs-lookup"><span data-stu-id="d39ae-134">We recommend that you begin validations with a test user or small group of users before rolling out multi-geo to your broader organization.</span></span>

<span data-ttu-id="d39ae-135">In Azure Active Directory (Azure AD) zijn er twee typen gebruikersobjecten: alleen cloudgebruikers en gesynchroniseerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d39ae-135">In Azure Active Directory (Azure AD) there are two types of user objects: cloud only users and synchronized users.</span></span> <span data-ttu-id="d39ae-136">Volg de juiste instructies voor uw type gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d39ae-136">Please follow the appropriate instructions for your type of user.</span></span>

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a><span data-ttu-id="d39ae-137">De voorkeurslocatie voor gegevens van de gebruiker synchroniseren met Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="d39ae-137">Synchronize user's Preferred Data Location using Azure AD Connect</span></span> 

<span data-ttu-id="d39ae-138">Als de gebruikers van uw bedrijf worden gesynchroniseerd van een on-premises Active Directory-systeem naar Azure AD, moet hun PreferredDataLocation worden ingevuld in AD en worden gesynchroniseerd met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d39ae-138">If your company's users are synchronized from an on-premises Active Directory system to Azure AD, their PreferredDataLocation must be populated in AD and synchronized to Azure AD.</span></span>

<span data-ttu-id="d39ae-139">Volg het proces in Azure Active Directory Connect-synchronisatie: Configureer voorkeursgegevenslocatie voor [Microsoft 365-resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) om synchronisatie van voorkeursgegevenslocatie te configureren van uw on-premises Active Directory Domain Services (AD DS) naar Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d39ae-139">Follow the process in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) to configure Preferred Data Location sync from your on-premises Active Directory Domain Services (AD DS) to Azure AD.</span></span>

<span data-ttu-id="d39ae-140">U wordt aangeraden de voorkeurslocatie voor gegevens van de gebruiker in te stellen als onderdeel van uw standaardwerkstroom voor het maken van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d39ae-140">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d39ae-141">Voor nieuwe gebruikers zonder OneDrive-inrichting moet u ten minste 24 uur wachten nadat de PDL van een gebruiker is gesynchroniseerd met Azure AD voordat de gebruiker zich aanmeldt bij OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="d39ae-141">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is synchronized to Azure AD for the changes to propagate before the user logs in to OneDrive for Business.</span></span> <span data-ttu-id="d39ae-142">(Als u de gewenste gegevenslocatie instelt voordat de gebruiker zich aanmeldt om zijn of haar OneDrive voor Bedrijven in te delen, zorgt u ervoor dat de nieuwe OneDrive van de gebruiker op de juiste locatie wordt ingericht.)</span><span class="sxs-lookup"><span data-stu-id="d39ae-142">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

### <a name="setting-preferred-data-location-for-cloud-only-users"></a><span data-ttu-id="d39ae-143">Voorkeursgegevenslocatie instellen voor alleen gebruikers in de cloud</span><span class="sxs-lookup"><span data-stu-id="d39ae-143">Setting Preferred Data Location for cloud only users</span></span> 

<span data-ttu-id="d39ae-144">Als de gebruikers van uw bedrijf niet worden gesynchroniseerd van een on-premises Active Directory-systeem naar Azure AD, wat betekent dat ze worden gemaakt in Microsoft 365 of Azure AD, moet de PDL worden ingesteld met de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d39ae-144">If your company's users are not synchronized from an on-premises Active Directory system to Azure AD, meaning they are created in Microsoft 365 or Azure AD, then the PDL must be set using the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="d39ae-145">Voor de procedures in deze sectie is de [Microsoft Azure Active Directory-module voor Windows PowerShell-module vereist.](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0)</span><span class="sxs-lookup"><span data-stu-id="d39ae-145">The procedures in this section require the [Microsoft Azure Active Directory Module for Windows PowerShell Module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span></span> <span data-ttu-id="d39ae-146">Als u deze module al hebt geïnstalleerd, controleert u of u de nieuwste versie hebt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d39ae-146">If you already have this module installed, please ensure you update to the latest version.</span></span>

1.  <span data-ttu-id="d39ae-147">[Maak verbinding en meld u aan](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) met een set globale beheerdersreferenties voor uw tenant.</span><span class="sxs-lookup"><span data-stu-id="d39ae-147">[Connect and sign in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) with a set of global administrator credentials for your tenant.</span></span>

2.  <span data-ttu-id="d39ae-148">Gebruik de [cmdlet Set-MsolUser](/powershell/msonline/v1/set-msoluser) om de gewenste gegevenslocatie in te stellen voor elk van uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d39ae-148">Use the [Set-MsolUser](/powershell/msonline/v1/set-msoluser) cmdlet to set the preferred data location for each of your users.</span></span> <span data-ttu-id="d39ae-149">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d39ae-149">For example:</span></span>

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    <span data-ttu-id="d39ae-150">U kunt controleren of de gewenste gegevenslocatie correct is bijgewerkt met de Get-MsolUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d39ae-150">You can check to confirm that the preferred data location was updated properly by using the Get-MsolUser cmdlet.</span></span> <span data-ttu-id="d39ae-151">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d39ae-151">For example:</span></span>

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Schermafbeelding van PowerShell-venster met set-msoluser](../media/multi-geo-tenant-configuration-image3.png)

<span data-ttu-id="d39ae-153">U wordt aangeraden de voorkeurslocatie voor gegevens van de gebruiker in te stellen als onderdeel van uw standaardwerkstroom voor het maken van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d39ae-153">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d39ae-154">Voor nieuwe gebruikers zonder OneDrive-inrichting moet u ten minste 24 uur wachten nadat de PDL van een gebruiker is ingesteld om de wijzigingen door te voeren voordat de gebruiker zich aanmeldt bij OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d39ae-154">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is set for the changes to propagate before the user logs in to OneDrive.</span></span> <span data-ttu-id="d39ae-155">(Als u de gewenste gegevenslocatie instelt voordat de gebruiker zich aanmeldt om zijn of haar OneDrive voor Bedrijven in te delen, zorgt u ervoor dat de nieuwe OneDrive van de gebruiker op de juiste locatie wordt ingericht.)</span><span class="sxs-lookup"><span data-stu-id="d39ae-155">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a><span data-ttu-id="d39ae-156">OneDrive-inrichting en het effect van PDL</span><span class="sxs-lookup"><span data-stu-id="d39ae-156">OneDrive Provisioning and the effect of PDL</span></span>

<span data-ttu-id="d39ae-157">Als de gebruiker al een OneDrive-site heeft gemaakt in de tenant, wordt de bestaande OneDrive niet automatisch verplaatst door de PDL in te stellen.</span><span class="sxs-lookup"><span data-stu-id="d39ae-157">If the user already has a OneDrive site created in the tenant, setting their PDL will not automatically move their existing OneDrive.</span></span> <span data-ttu-id="d39ae-158">Zie OneDrive voor Bedrijven Geo Move als u oneDrive van een gebruiker [wilt verplaatsen.](move-onedrive-between-geo-locations.md)</span><span class="sxs-lookup"><span data-stu-id="d39ae-158">To move a user's OneDrive, see [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d39ae-159">Exchange Online verplaatst automatisch het postvak van de gebruiker als de PLD wordt gewijzigd en de Postvakregio niet meer overeenkomt met de geolocatiecode van de postvakdatabase.</span><span class="sxs-lookup"><span data-stu-id="d39ae-159">Exchange Online automatically relocates the user's mailbox if the PLD changes and the MailboxRegion no longer matches the Mailbox Database Geo Location code.</span></span> <span data-ttu-id="d39ae-160">Zie Exchange Online-postvakken beheren in een [multi-geoomgeving](./administering-exchange-online-multi-geo.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d39ae-160">For more information, see [Administering Exchange Online mailboxes in a multi-geo environment](./administering-exchange-online-multi-geo.md).</span></span>

<span data-ttu-id="d39ae-161">Als de gebruiker geen OneDrive-site binnen de tenant heeft, wordt OneDrive voor de gebruiker ingericht op basis van de PDL-waarde, ervan uitgaande dat de PDL voor de gebruiker overeenkomt met een van de satellietlocaties van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="d39ae-161">If the user does not have a OneDrive site within the tenant, OneDrive will be provisioned for them in accordance to their PDL value, assuming the PDL for the user matches one of the company's satellite locations.</span></span>

## <a name="configuring-multi-geo-search"></a><span data-ttu-id="d39ae-162">Zoeken met meerdere geografische gegevens configureren</span><span class="sxs-lookup"><span data-stu-id="d39ae-162">Configuring Multi-Geo search</span></span>

<span data-ttu-id="d39ae-163">Uw multi-geoten tenant heeft statistische zoekmogelijkheden waarmee een zoekquery resultaten kan retourneren vanaf elke locatie in de tenant.</span><span class="sxs-lookup"><span data-stu-id="d39ae-163">Your multi-geo tenant will have aggregate search capabilities allowing a search query to return results from anywhere within the tenant.</span></span>

<span data-ttu-id="d39ae-164">Zoekopdrachten op deze invoerpunten leveren standaard statistische resultaten op, ook al bevindt elke zoekindex zich op de relevante geografische locatie:</span><span class="sxs-lookup"><span data-stu-id="d39ae-164">By default, searches from these entry points will return aggregate results, even though each search index is located within its relevant geo location:</span></span>

- <span data-ttu-id="d39ae-165">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="d39ae-165">OneDrive for Business</span></span>

- <span data-ttu-id="d39ae-166">Delve</span><span class="sxs-lookup"><span data-stu-id="d39ae-166">Delve</span></span>

- <span data-ttu-id="d39ae-167">SharePoint Home</span><span class="sxs-lookup"><span data-stu-id="d39ae-167">SharePoint Home</span></span>

- <span data-ttu-id="d39ae-168">Zoekcentrum</span><span class="sxs-lookup"><span data-stu-id="d39ae-168">Search Center</span></span>

<span data-ttu-id="d39ae-169">Bovendien kunnen zoekmogelijkheden met meerdere geografische functies worden geconfigureerd voor uw aangepaste zoektoepassingen die gebruikmaken van de SharePoint-zoek-API.</span><span class="sxs-lookup"><span data-stu-id="d39ae-169">Additionally, multi-geo search capabilities can be configured for your custom search applications that use the SharePoint search API.</span></span>

<span data-ttu-id="d39ae-170">Raadpleeg [Zoeken naar OneDrive voor Bedrijven Multi-Geo](configure-search-for-multi-geo.md) configureren voor instructies, inclusief eventuele beperkingen en verschillen.</span><span class="sxs-lookup"><span data-stu-id="d39ae-170">Please review [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for instructions including any limitations and differences.</span></span>

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a><span data-ttu-id="d39ae-171">De Configuratie van Microsoft 365 Multi-Geo valideren</span><span class="sxs-lookup"><span data-stu-id="d39ae-171">Validating the Microsoft 365 Multi-Geo configuration</span></span>

<span data-ttu-id="d39ae-172">Hieronder vindt u enkele basisgebruiksgevallen die u mogelijk wilt opnemen in uw validatieplan voordat u Microsoft 365 Multi-Geo breed uitrolt naar uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="d39ae-172">Below are some basic use cases you may wish to include in your validation plan before broadly rolling out Microsoft 365 Multi-Geo to your company.</span></span> <span data-ttu-id="d39ae-173">Nadat u deze tests en eventuele aanvullende gebruiksgevallen hebt voltooid die relevant zijn voor uw bedrijf, kunt u ervoor kiezen om door te gaan met het toevoegen van de gebruikers in uw eerste testgroep.</span><span class="sxs-lookup"><span data-stu-id="d39ae-173">Once you have completed these tests and any additional use cases that are relevant to your company, you may choose to move on to adding the users in your initial pilot group.</span></span>

<span data-ttu-id="d39ae-174">**OneDrive voor Bedrijven**</span><span class="sxs-lookup"><span data-stu-id="d39ae-174">**OneDrive for Business**</span></span>

<span data-ttu-id="d39ae-175">Selecteer OneDrive in het start programma voor apps van Microsoft 365 en bevestig dat u automatisch wordt doorgestuurd naar de juiste geografische locatie voor de gebruiker, op basis van de PDL van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d39ae-175">Select OneDrive from the Microsoft 365 app launcher and confirm that you are automatically directed to the appropriate geo location for the user, based on the user's PDL.</span></span> <span data-ttu-id="d39ae-176">OneDrive voor Bedrijven moet nu beginnen met de inrichting op die locatie.</span><span class="sxs-lookup"><span data-stu-id="d39ae-176">OneDrive for Business should now begin provisioning at that location.</span></span> <span data-ttu-id="d39ae-177">Wanneer u deze hebt ingericht, kunt u proberen om bepaalde documenten te uploaden en te downloaden.</span><span class="sxs-lookup"><span data-stu-id="d39ae-177">Once provisioned, try uploading and downloading some documents.</span></span>

<span data-ttu-id="d39ae-178">**OneDrive Mobile App**</span><span class="sxs-lookup"><span data-stu-id="d39ae-178">**OneDrive Mobile App**</span></span>

<span data-ttu-id="d39ae-179">Meld u aan bij uw mobiele OneDrive-app met uw testaccountreferenties.</span><span class="sxs-lookup"><span data-stu-id="d39ae-179">Log into your OneDrive mobile App with your test account credentials.</span></span> <span data-ttu-id="d39ae-180">Bevestig dat u uw OneDrive voor Bedrijven-bestanden kunt zien en dat u er vanaf uw mobiele apparaat mee kunt werken.</span><span class="sxs-lookup"><span data-stu-id="d39ae-180">Confirm that you can see your OneDrive for Business files and can interact with them from your mobile device.</span></span>

<span data-ttu-id="d39ae-181">**OneDrive-synchronisatieclient**</span><span class="sxs-lookup"><span data-stu-id="d39ae-181">**OneDrive sync client**</span></span>

<span data-ttu-id="d39ae-182">Controleer of de OneDrive-synchronisatieclient automatisch uw oneDrive voor Bedrijven-geografische locatie detecteert wanneer u zich aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="d39ae-182">Confirm that the OneDrive sync client automatically detects your OneDrive for Business geo location upon login.</span></span> <span data-ttu-id="d39ae-183">Als u de synchronisatieclient wilt downloaden, klikt u op **Synchroniseren** in de OneDrive-bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="d39ae-183">If you need to download the sync client, you can click **Sync** in the OneDrive library.</span></span>

<span data-ttu-id="d39ae-184">**Office-toepassingen**</span><span class="sxs-lookup"><span data-stu-id="d39ae-184">**Office applications**</span></span>

<span data-ttu-id="d39ae-185">Bevestig dat u toegang hebt tot OneDrive voor Bedrijven door u aan te melden vanuit een Office-toepassing, zoals Word.</span><span class="sxs-lookup"><span data-stu-id="d39ae-185">Confirm that you can access OneDrive for Business by logging in from an Office application, such as Word.</span></span> <span data-ttu-id="d39ae-186">Open de Office-toepassing en selecteer 'OneDrive – <TenantName> '.</span><span class="sxs-lookup"><span data-stu-id="d39ae-186">Open the Office application and select "OneDrive – <TenantName>".</span></span> <span data-ttu-id="d39ae-187">Office detecteert uw OneDrive-locatie en toont u de bestanden die u kunt openen.</span><span class="sxs-lookup"><span data-stu-id="d39ae-187">Office will detect your OneDrive location and show you the files that you can open.</span></span>

<span data-ttu-id="d39ae-188">**Delen**</span><span class="sxs-lookup"><span data-stu-id="d39ae-188">**Sharing**</span></span>

<span data-ttu-id="d39ae-189">Probeer OneDrive-bestanden te delen.</span><span class="sxs-lookup"><span data-stu-id="d39ae-189">Try sharing OneDrive files.</span></span> <span data-ttu-id="d39ae-190">Controleer of de personen picker u al uw SharePoint Online-gebruikers laat zien, ongeacht hun geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="d39ae-190">Confirm that the people picker shows you all your SharePoint online users regardless of their geo location.</span></span>