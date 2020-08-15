---
title: Skype voor bedrijven on-premises configureren voor gebruik van hybride moderne verificatie
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Meer informatie over hoe u Skype voor bedrijven on-premises kunt configureren voor gebruik van de Hybrid modern Authentication (HMA), met een veiligere verificatie van gebruikers en autorisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695008"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="1221f-103">Skype voor bedrijven on-premises configureren voor gebruik van hybride moderne verificatie</span><span class="sxs-lookup"><span data-stu-id="1221f-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="1221f-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1221f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1221f-105">Moderne verificatie is een methode van identiteitsbeheer die veiliger en autorisatie van gebruikers biedt, is beschikbaar voor Skype voor bedrijven server on-premises en Exchange Server on-premises en gesplitste domein Skype voor bedrijven-hybriden.</span><span class="sxs-lookup"><span data-stu-id="1221f-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="1221f-106">**Belangrijk** Wilt u meer weten over moderne verificatie (MA) en waarom u liever deze wilt gebruiken in uw bedrijf of organisatie?</span><span class="sxs-lookup"><span data-stu-id="1221f-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="1221f-107">Bekijk [dit document](hybrid-modern-auth-overview.md) voor een overzicht.</span><span class="sxs-lookup"><span data-stu-id="1221f-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="1221f-108">Als u wilt weten wat de topologie van Skype voor bedrijven met MA moet ondersteunen, wordt deze hier beschreven.</span><span class="sxs-lookup"><span data-stu-id="1221f-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="1221f-109">**Voordat we beginnen**, gebruik ik deze voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="1221f-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="1221f-110">Moderne verificatie (MA)</span><span class="sxs-lookup"><span data-stu-id="1221f-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="1221f-111">Hybrid modern Authentication (HMA)</span><span class="sxs-lookup"><span data-stu-id="1221f-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="1221f-112">Exchange on-premises (uitwisseling)</span><span class="sxs-lookup"><span data-stu-id="1221f-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="1221f-113">Exchange Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="1221f-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="1221f-114">Skype voor bedrijven on-premises (SFB)</span><span class="sxs-lookup"><span data-stu-id="1221f-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="1221f-115">Skype voor bedrijven online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="1221f-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="1221f-116">Ook als een afbeelding in dit artikel een object heeft dat grijs wordt weergegeven of grijs wordt weergegeven, betekent dit dat het element grijs wordt weergegeven en **niet** is opgenomen in de configuratie voor ma-specifiek.</span><span class="sxs-lookup"><span data-stu-id="1221f-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="1221f-117">Lees het overzicht</span><span class="sxs-lookup"><span data-stu-id="1221f-117">Read the summary</span></span>

<span data-ttu-id="1221f-118">In deze samenvatting wordt het proces in stappen opgesplitst en is dit geschikt voor een algemene controlelijst die u kunt bijhouden waar u zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="1221f-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="1221f-119">Zorg er eerst voor dat u aan alle vereisten voldoet.</span><span class="sxs-lookup"><span data-stu-id="1221f-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="1221f-120">Aangezien veel voor **waarden** voor Skype voor bedrijven en Exchange voor u gelden, [raadpleegt u het artikeloverzicht voor de controlelijst voorafgaand aan de vereisten](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1221f-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="1221f-121">Ga verder  *voordat*  u de stappen in dit artikel begint.</span><span class="sxs-lookup"><span data-stu-id="1221f-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="1221f-122">Verzamel de HMA-specifieke informatie die u nodig hebt in een bestand of OneNote.</span><span class="sxs-lookup"><span data-stu-id="1221f-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="1221f-123">Moderne verificatie voor EXO inschakelen (als dit nog niet is ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="1221f-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="1221f-124">Moderne verificatie voor SFBO inschakelen (als dit nog niet is ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="1221f-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="1221f-125">Hybride moderne verificatie inschakelen voor Exchange on-premises.</span><span class="sxs-lookup"><span data-stu-id="1221f-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="1221f-126">Schakel hybride moderne verificatie in voor Skype voor bedrijven on-premises.</span><span class="sxs-lookup"><span data-stu-id="1221f-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="1221f-127">Met deze stappen wordt de MA voor SFB, SFBO, wisselkoers, en EXO, dat wil zeggen alle producten die kunnen deelnemen aan een HMA-configuratie van SFB en SFBO (inclusief afhankelijkheden voor wissel/EXO).</span><span class="sxs-lookup"><span data-stu-id="1221f-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="1221f-128">Met andere woorden, als uw gebruikers zijn aangemeld/postvakken hebben gemaakt in een deel van de Hybrid (EXO + SFBO, EXO + SFB, SFBO + SFB of +), ziet uw voltooide product er zo uit:</span><span class="sxs-lookup"><span data-stu-id="1221f-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![Een gemengde 6 Skype voor bedrijven HMA-topologie biedt op alle vier mogelijke locaties op de i](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="1221f-130">Zoals u ziet, zijn er vier verschillende locaties waarmee u MA kunt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="1221f-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="1221f-131">Voor de beste ervaring raden we u aan om MA in te schakelen op alle vier deze locaties.</span><span class="sxs-lookup"><span data-stu-id="1221f-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="1221f-132">Als u op al deze locaties de optie MA niet kunt inschakelen, moet u de stappen aanpassen, zodat u MA alleen kunt inschakelen op de locaties die nodig zijn voor uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="1221f-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="1221f-133">Zie het [onderwerp voor ondersteuning voor Skype voor bedrijven met ma](https://technet.microsoft.com/library/mt803262.aspx) voor ondersteunde topologieën.</span><span class="sxs-lookup"><span data-stu-id="1221f-133">See the [Supportability topic for Skype for Business with MA](https://technet.microsoft.com/library/mt803262.aspx) for supported topologies.</span></span>
  
 <span data-ttu-id="1221f-134">**Belangrijk** Controleer nog eens of u aan de vereisten voldoet voordat u begint.</span><span class="sxs-lookup"><span data-stu-id="1221f-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="1221f-135">U vindt deze informatie in de [hybride overzicht van de hybride verificatie en de vereisten](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1221f-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="1221f-136">Verzamel alle HMA-specifieke informatie die u nodig hebt</span><span class="sxs-lookup"><span data-stu-id="1221f-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="1221f-137">Nadat u hebt gecontroleerd of u beschikt over de [vereisten](hybrid-modern-auth-overview.md) voor moderne verificatie (Zie de opmerking hierboven), moet u een bestand maken voor de informatie die u nodig hebt voor het configureren van HMA in de stappen voor het eerst.</span><span class="sxs-lookup"><span data-stu-id="1221f-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="1221f-138">Voorbeelden in dit artikel:</span><span class="sxs-lookup"><span data-stu-id="1221f-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="1221f-139">**SIP/SMTP-domein**</span><span class="sxs-lookup"><span data-stu-id="1221f-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="1221f-140">".</span><span class="sxs-lookup"><span data-stu-id="1221f-140">Ex.</span></span> <span data-ttu-id="1221f-141">contoso.com (is federatief met Office 365)</span><span class="sxs-lookup"><span data-stu-id="1221f-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="1221f-142">**Tenant-ID**</span><span class="sxs-lookup"><span data-stu-id="1221f-142">**Tenant ID**</span></span>

  - <span data-ttu-id="1221f-143">De GUID waarmee uw Office 365-Tenant wordt aangeduid (bij aanmelding van contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="1221f-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="1221f-144">**SFB 2015 CU5 hoger vereist webservice-Url's**</span><span class="sxs-lookup"><span data-stu-id="1221f-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="1221f-145">voor alle SfB 2015 groepen is een interne en externe webservice-URL nodig.</span><span class="sxs-lookup"><span data-stu-id="1221f-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="1221f-146">Voer de volgende stappen uit in de beheer shell van Skype voor bedrijven om deze te verkrijgen:</span><span class="sxs-lookup"><span data-stu-id="1221f-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="1221f-147">".</span><span class="sxs-lookup"><span data-stu-id="1221f-147">Ex.</span></span> <span data-ttu-id="1221f-148">Binnenlandse https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1221f-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="1221f-149">".</span><span class="sxs-lookup"><span data-stu-id="1221f-149">Ex.</span></span> <span data-ttu-id="1221f-150">External https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1221f-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="1221f-151">Als u een Standard Edition-server gebruikt, is de interne URL leeg.</span><span class="sxs-lookup"><span data-stu-id="1221f-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="1221f-152">Gebruik in dit geval de FQDN-naam van de groep voor de interne URL.</span><span class="sxs-lookup"><span data-stu-id="1221f-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="1221f-153">Moderne verificatie voor EXO inschakelen</span><span class="sxs-lookup"><span data-stu-id="1221f-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="1221f-154">Volg de instructies hier: [Exchange Online: de Tenant inschakelen voor moderne verificatie.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="1221f-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="1221f-155">Moderne verificatie voor SFBO inschakelen</span><span class="sxs-lookup"><span data-stu-id="1221f-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="1221f-156">Volg de instructies hier: [Skype voor bedrijven online: uw Tenant inschakelen voor moderne verificatie](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span><span class="sxs-lookup"><span data-stu-id="1221f-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="1221f-157">Hybride moderne verificatie inschakelen voor Exchange on-premises</span><span class="sxs-lookup"><span data-stu-id="1221f-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="1221f-158">Volg de instructies hier: [informatie over het configureren van Exchange Server on-premises voor hybride moderne verificatie](configure-exchange-server-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1221f-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="1221f-159">Hybride moderne verificatie inschakelen voor Skype voor bedrijven on-premises</span><span class="sxs-lookup"><span data-stu-id="1221f-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="1221f-160">On-premises webservice-Url's toevoegen als Spn's in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1221f-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="1221f-161">U moet nu opdrachten uitvoeren om de Url's (eerder verzameld) toe te voegen als service-principals in SFBO.</span><span class="sxs-lookup"><span data-stu-id="1221f-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="1221f-162">**Opmerking** Met Spn's (Service Principal Names) identificeert u webservices en koppelt u deze aan een beveiligingsprincipal (zoals een accountnaam of groep), zodat de service namens een gemachtigde gebruiker kan handelen.</span><span class="sxs-lookup"><span data-stu-id="1221f-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="1221f-163">Clientverificatie op een server gebruikt informatie die zich bevindt in Spn's.</span><span class="sxs-lookup"><span data-stu-id="1221f-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="1221f-164">Maak eerst verbinding met Azure Active Directory (Azure AD) met [de volgende instructies](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1221f-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="1221f-165">Voer deze opdracht, on-premises, uit om een lijst te zien met SFB-Url's voor de web-service.</span><span class="sxs-lookup"><span data-stu-id="1221f-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="1221f-166">Houd er rekening mee dat het Appprincipalid die begint met `00000004` .</span><span class="sxs-lookup"><span data-stu-id="1221f-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="1221f-167">Dit komt overeen met Skype voor bedrijven online.</span><span class="sxs-lookup"><span data-stu-id="1221f-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="1221f-168">Notitie maken van (en schermafbeelding voor later vergelijken) de uitvoer van deze opdracht, die een SE en een WS-URL omvat, maar meestal bestaan uit Spn's die beginnen met `00000004-0000-0ff1-ce00-000000000000/` .</span><span class="sxs-lookup"><span data-stu-id="1221f-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="1221f-169">Als de interne **of** externe SFB-url's van on-premises ontbreken (bijvoorbeeld https://lyncwebint01.contoso.com en https://lyncwebext01.contoso.com) we moeten deze specifieke records toevoegen aan deze lijst.</span><span class="sxs-lookup"><span data-stu-id="1221f-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="1221f-170">Vervang  *de onderstaande voorbeeld url's* door uw werkelijke url's in de opdrachten toevoegen.</span><span class="sxs-lookup"><span data-stu-id="1221f-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="1221f-171">Controleer of de nieuwe records zijn toegevoegd door de opdracht **Get-MsolServicePrincipal** uit stap 2 opnieuw uit te voeren en de uitvoer te bekijken.</span><span class="sxs-lookup"><span data-stu-id="1221f-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="1221f-172">Vergelijk de lijst of schermafbeelding van vóór de nieuwe lijst met Spn's.</span><span class="sxs-lookup"><span data-stu-id="1221f-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="1221f-173">U kunt ook een schermafbeelding van de nieuwe lijst voor uw records weergeven.</span><span class="sxs-lookup"><span data-stu-id="1221f-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="1221f-174">Als u gelukte, ziet u de twee nieuwe Url's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="1221f-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="1221f-175">In ons voorbeeld, de lijst met Spn's bevat nu de specifieke Url's https://lyncwebint01.contoso.com en https://lyncwebext01.contoso.com/ .</span><span class="sxs-lookup"><span data-stu-id="1221f-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="1221f-176">Maak het EvoSTS auth Server-object</span><span class="sxs-lookup"><span data-stu-id="1221f-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="1221f-177">Voer de volgende opdracht uit in de Skype voor bedrijven-beheer shell.</span><span class="sxs-lookup"><span data-stu-id="1221f-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="1221f-178">Hybride moderne verificatie inschakelen</span><span class="sxs-lookup"><span data-stu-id="1221f-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="1221f-179">Dit is de stap waarmee u in het MA MA schakelt.</span><span class="sxs-lookup"><span data-stu-id="1221f-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="1221f-180">U kunt alle vorige stappen vóór de tijd uitvoeren zonder de clientverificatie stroom te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1221f-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="1221f-181">Wanneer u klaar bent om de verificatie stroom te wijzigen, voert u deze opdracht uit in de Skype voor bedrijven-beheer shell.</span><span class="sxs-lookup"><span data-stu-id="1221f-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="1221f-182">Verifiëren</span><span class="sxs-lookup"><span data-stu-id="1221f-182">Verify</span></span>

<span data-ttu-id="1221f-183">Wanneer u HMA hebt ingeschakeld, wordt de nieuwe verificatie stroom gebruikt door de volgende aanmelding van een client.</span><span class="sxs-lookup"><span data-stu-id="1221f-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="1221f-184">Wanneer u een HMA inschakelt, wordt de herauthenticatie voor geen enkele client geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="1221f-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="1221f-185">De client verifieert op basis van de levensduur van de auth-tokens en/of certificeringen.</span><span class="sxs-lookup"><span data-stu-id="1221f-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="1221f-186">Als u wilt testen of het HMA werkt nadat u dit hebt ingeschakeld, meldt u zich af bij een Windows-client voor test SFB en klikt u op ' mijn referenties verwijderen '.</span><span class="sxs-lookup"><span data-stu-id="1221f-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="1221f-187">Meld u opnieuw aan.</span><span class="sxs-lookup"><span data-stu-id="1221f-187">Sign in again.</span></span> <span data-ttu-id="1221f-188">De client dient nu de moderne verificatie stroom te gebruiken, en de aanmelding bevat nu een **Office 365** -prompt voor een werk-of schoolaccount, weergegeven, rechts voordat de client contact maakt met de server en u zich aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="1221f-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="1221f-189">U dient ook de ' configuratiegegevens ' voor Skype voor bedrijven-clients te controleren voor een ' OAuth-autoriteit '.</span><span class="sxs-lookup"><span data-stu-id="1221f-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="1221f-190">Houd de CTRL-toets ingedrukt en klik met de rechtermuisknop op het pictogram van Skype voor bedrijven in het systeemvak van Windows om dit te doen op de clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="1221f-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="1221f-191">In het menu dat wordt weergegeven, klikt u op **configuratiegegevens** .</span><span class="sxs-lookup"><span data-stu-id="1221f-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="1221f-192">In het venster ' Skype voor bedrijven Configuration Information ', dat wordt weergegeven op het bureaublad, raadpleegt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="1221f-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![De configuratiegegevens van een Skype voor bedrijven-client die gebruikmaken van moderne verificatie tonen een URL van Lync en EWS OAUTH-autoriteit https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="1221f-194">Houd de CTRL-toets ook ingedrukt terwijl u met de rechtermuisknop op het pictogram van de Outlook-client klikt (ook in het systeemvak van Windows) en klik op verbindings status.</span><span class="sxs-lookup"><span data-stu-id="1221f-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="1221f-195">Zoek het SMTP-adres van de client tegen een authentication type van ' Bearer \* ', dat staat voor het dragertoken dat wordt gebruikt in OAuth.</span><span class="sxs-lookup"><span data-stu-id="1221f-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="1221f-196">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="1221f-196">Related articles</span></span>

<span data-ttu-id="1221f-197">[Koppeling terug naar het moderne verificatie overzicht](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1221f-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="1221f-198">Wilt u meer weten over het gebruik van moderne verificatie (ADAL) voor uw Skype voor bedrijven-clients?</span><span class="sxs-lookup"><span data-stu-id="1221f-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="1221f-199">We hebben [hier](https://technet.microsoft.com/library/mt710548.aspx)stappen.</span><span class="sxs-lookup"><span data-stu-id="1221f-199">We've got steps [here](https://technet.microsoft.com/library/mt710548.aspx).</span></span>
