---
title: De on-premises implementatie van Exchange server configureren voor gebruik van hybride moderne verificatie
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lees meer over het configureren van een on-premises Exchange-Server voor hybride implementatie van gebruikers, met een uitgebreide verificatie van gebruikers en autorisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 291c7c220fb4ee56db2a42409d5b81724de5da32
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688913"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="2f117-103">De on-premises implementatie van Exchange server configureren voor gebruik van hybride moderne verificatie</span><span class="sxs-lookup"><span data-stu-id="2f117-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="2f117-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2f117-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2f117-105">Hybrid modern Authentication (HMA) is een methode van identiteitsbeheer die veiliger en autorisatie van gebruikers biedt en beschikbaar is voor Exchange Server on-premises hybride implementaties.</span><span class="sxs-lookup"><span data-stu-id="2f117-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>
  
## <a name="fyi"></a><span data-ttu-id="2f117-106">TER informatie</span><span class="sxs-lookup"><span data-stu-id="2f117-106">FYI</span></span>

<span data-ttu-id="2f117-107">Voordat we beginnen, bel ik het volgende:</span><span class="sxs-lookup"><span data-stu-id="2f117-107">Before we begin, I call:</span></span>
  
- <span data-ttu-id="2f117-108">Hybrid modern Authentication \> HMA</span><span class="sxs-lookup"><span data-stu-id="2f117-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="2f117-109">Exchange on \> -premises uitwisseling</span><span class="sxs-lookup"><span data-stu-id="2f117-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="2f117-110">Exchange Online \> Exo</span><span class="sxs-lookup"><span data-stu-id="2f117-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="2f117-111">Ook *als een afbeelding in dit artikel een object heeft dat niet beschikbaar is (grijs) of lichter gekleurd, betekent dit dat het element dat grijs wordt weergegeven, niet is opgenomen in de HMA-specifieke configuratie* .</span><span class="sxs-lookup"><span data-stu-id="2f117-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration* .</span></span>
  
## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="2f117-112">Hybride authenticatie inschakelen</span><span class="sxs-lookup"><span data-stu-id="2f117-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="2f117-113">Als u het HMA wilt uitschakelen, doet u dit:</span><span class="sxs-lookup"><span data-stu-id="2f117-113">Turning HMA on means:</span></span>
  
1. <span data-ttu-id="2f117-114">Zorg ervoor dat u voldoet aan de prereqs voordat u begint.</span><span class="sxs-lookup"><span data-stu-id="2f117-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="2f117-115">Aangezien veel voor **waarden** van toepassing zijn op Skype voor bedrijven en Exchange, de [hybride verificatie-overzicht van de hybride versie en vereisten voor het gebruik van on-premises Skype voor bedrijven en Exchange-servers](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2f117-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="2f117-116">Ga verder voordat u de stappen in dit artikel begint.</span><span class="sxs-lookup"><span data-stu-id="2f117-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="2f117-117">On-premises Url's voor webservice toevoegen als **spn's (Service Principal Names)** in azure AD.</span><span class="sxs-lookup"><span data-stu-id="2f117-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="2f117-118">Ervoor zorgen dat alle virtuele mappen worden ingeschakeld voor HMA</span><span class="sxs-lookup"><span data-stu-id="2f117-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="2f117-119">Controleren op het EvoSTS auth Server-object</span><span class="sxs-lookup"><span data-stu-id="2f117-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="2f117-120">Enable HMA in wisselkoers.</span><span class="sxs-lookup"><span data-stu-id="2f117-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="2f117-121">**Opmerking** Biedt uw versie van Office ondersteuning voor MA?</span><span class="sxs-lookup"><span data-stu-id="2f117-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="2f117-122">Zie [hoe moderne verificatie werkt voor office 2013-en office 2016-clienttoepassingen](modern-auth-for-office-2013-and-2016.md).</span><span class="sxs-lookup"><span data-stu-id="2f117-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>
  
## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="2f117-123">Zorg dat u aan alle vereisten voldoet.</span><span class="sxs-lookup"><span data-stu-id="2f117-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="2f117-124">Aangezien veel voorwaarden voor Skype voor bedrijven en Exchange voor u gelden, moet [u het overzicht van hybride verificatie en vereisten voor het gebruik van on-premises Skype voor bedrijven en Exchange-servers](hybrid-modern-auth-overview.md)raadplegen.</span><span class="sxs-lookup"><span data-stu-id="2f117-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="2f117-125">Ga verder  *voordat*  u de stappen in dit artikel begint.</span><span class="sxs-lookup"><span data-stu-id="2f117-125">Do this  *before*  you begin any of the steps in this article.</span></span>
  
## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="2f117-126">On-premises webservice-Url's toevoegen als Spn's in azure AD</span><span class="sxs-lookup"><span data-stu-id="2f117-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="2f117-127">Voer de opdrachten uit waarop u de on-premises Url's voor de web-service aanwijst als Azure AD-Spn's.</span><span class="sxs-lookup"><span data-stu-id="2f117-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="2f117-128">Spn's worden door clients en apparaten van de client gebruikt tijdens verificatie en autorisatie.</span><span class="sxs-lookup"><span data-stu-id="2f117-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="2f117-129">Alle Url's die kunnen worden gebruikt voor het maken van verbinding tussen locaties en Azure Active Directory (Azure AD), moeten worden geregistreerd in azure AD (dit geldt ook voor interne en externe naamruimten).</span><span class="sxs-lookup"><span data-stu-id="2f117-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>
  
<span data-ttu-id="2f117-130">Verzamel eerst alle Url's die u wilt toevoegen in AAD.</span><span class="sxs-lookup"><span data-stu-id="2f117-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="2f117-131">Voer deze opdrachten on-premises uit:</span><span class="sxs-lookup"><span data-stu-id="2f117-131">Run these commands on-premises:</span></span>
  
```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```
    
<span data-ttu-id="2f117-132">Zorg ervoor dat de Url's clients kunnen verbinding maken met behulp van HTTPS-service-principal-namen in AAD.</span><span class="sxs-lookup"><span data-stu-id="2f117-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>
  
1. <span data-ttu-id="2f117-133">Maak eerst verbinding met AAD met [deze instructies](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2f117-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

 <span data-ttu-id="2f117-134">**Opmerking** U moet de optie _verbinding-MsolService_ van deze pagina gebruiken om de onderstaande opdracht te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2f117-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="2f117-135">Voor de verwante Url's voor Exchange typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="2f117-135">For your Exchange related URLs, type the following command:</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
```

<span data-ttu-id="2f117-136">Let op (en schermafbeelding voor een latere vergelijking) de uitvoer van deze opdracht, die een https://  *Autodiscover.yourdomain.com*  en https://  *mail.yourdomain.com* -URL moet bevatten, maar meestal bestaat uit spn's die beginnen met 00000002-0000-0ff1-CE00-000000000000/.</span><span class="sxs-lookup"><span data-stu-id="2f117-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="2f117-137">Als er https://-Url's zijn van uw on-premises die ontbreken, moeten ze deze specifieke records toevoegen aan deze lijst.</span><span class="sxs-lookup"><span data-stu-id="2f117-137">If there are https:// URLs from your on-premises that are missing we will need to add those specific records to this list.</span></span>
  
3. <span data-ttu-id="2f117-138">Als u uw interne en externe MAPI-, EWS-, ActiveSync-, OAB-en Autodiscover-records niet in deze lijst ziet, moet u deze toevoegen met behulp van de volgende opdracht (de voorbeeld Url's zijn ' `mail.corp.contoso.com` ' en ' `owa.contoso.com` ', maar **vervangt u de url's met uw eigen** url's wel.</span><span class="sxs-lookup"><span data-stu-id="2f117-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own** ):</span></span> <br/>
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
$x.ServicePrincipalnames.Add("https://owa.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. <span data-ttu-id="2f117-139">Controleer of de nieuwe records zijn toegevoegd door de opdracht Get-MsolServicePrincipal uit stap 2 opnieuw uit te voeren en de uitvoer te bekijken.</span><span class="sxs-lookup"><span data-stu-id="2f117-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="2f117-140">Vergelijk de lijst/schermafbeelding van vóór de nieuwe lijst met Spn's (u kunt ook een schermafbeelding van de nieuwe lijst voor uw records weergeven).</span><span class="sxs-lookup"><span data-stu-id="2f117-140">Compare the list / screenshot from before to the new list of SPNs (you may also screenshot the new list for your records).</span></span> <span data-ttu-id="2f117-141">Als u slaagt, worden de twee nieuwe Url's in de lijst weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2f117-141">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="2f117-142">In ons voorbeeld, de lijst met Spn's bevat nu de specifieke Url's  `https://mail.corp.contoso.com`  en  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="2f117-142">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span> 
  
## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="2f117-143">Controleren of virtuele mappen correct zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="2f117-143">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="2f117-144">Op deze manier controleert u of OAuth correct is ingeschakeld in Exchange voor alle virtuele mappen die in Outlook kunnen worden gebruikt door de volgende opdrachten uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="2f117-144">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth* 
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="2f117-145">Controleer de uitvoer om er voor elk van deze VDirs in te schakelen, wat er ongeveer zo uitziet (en de naam van het bestand dat u **wilt controleren is** ' OAuth '):</span><span class="sxs-lookup"><span data-stu-id="2f117-145">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```
  
<span data-ttu-id="2f117-146">Als er geen OAuth-server en een van de vier virtuele mappen ontbreken, moet u deze toevoegen aan de hand van de betreffende opdrachten voordat u verdergaat ([set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps)en [set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).</span><span class="sxs-lookup"><span data-stu-id="2f117-146">If OAuth is missing from any server and any of the four virtual directories then you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).</span></span>
  
## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="2f117-147">Bevestig dat het object van de EvoSTS Authentication server aanwezig is</span><span class="sxs-lookup"><span data-stu-id="2f117-147">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="2f117-148">Keer terug naar de on-premises Exchange Management Shell voor deze laatste opdracht.</span><span class="sxs-lookup"><span data-stu-id="2f117-148">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="2f117-149">U kunt nu controleren of uw on-premises een vermelding heeft voor de evoSTS-verificatieprovider:</span><span class="sxs-lookup"><span data-stu-id="2f117-149">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>
  
```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="2f117-150">Voor de uitvoer moet een AuthServer worden weergegeven van de naam EvoSts en moet de ' ingeschakelde ' status waar zijn.</span><span class="sxs-lookup"><span data-stu-id="2f117-150">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="2f117-151">Als u dit niet ziet, dient u de meest recente versie van de wizard hybride configuratie te downloaden en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2f117-151">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>
  
 <span data-ttu-id="2f117-152">**Belangrijk** Als u Exchange 2010 gebruikt in uw omgeving, wordt de EvoSTS-verificatieprovider niet gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2f117-152">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span> 
  
## <a name="enable-hma"></a><span data-ttu-id="2f117-153">HMA inschakelen</span><span class="sxs-lookup"><span data-stu-id="2f117-153">Enable HMA</span></span>

<span data-ttu-id="2f117-154">Voer de volgende opdracht uit in de Exchange-beheer shell, on-premises:</span><span class="sxs-lookup"><span data-stu-id="2f117-154">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true  
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="2f117-155">Verifiëren</span><span class="sxs-lookup"><span data-stu-id="2f117-155">Verify</span></span>

<span data-ttu-id="2f117-156">Wanneer u HMA hebt ingeschakeld, wordt de nieuwe verificatie stroom gebruikt door de volgende aanmelding van een client.</span><span class="sxs-lookup"><span data-stu-id="2f117-156">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="2f117-157">Als u geen gebruik maakt van HMA, wordt een nieuwe verificatie niet geactiveerd voor elke client.</span><span class="sxs-lookup"><span data-stu-id="2f117-157">Note that just turning on HMA won't trigger a re-authentication for any client.</span></span> <span data-ttu-id="2f117-158">De client verifieert opnieuw op basis van de levensduur van de auth-tokens en/of-certificaten.</span><span class="sxs-lookup"><span data-stu-id="2f117-158">The clients re-authenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="2f117-159">Houd de CTRL-toets ook ingedrukt terwijl u met de rechtermuisknop op het pictogram van de Outlook-client klikt (ook in het systeemvak van Windows) en klik op verbindings status.</span><span class="sxs-lookup"><span data-stu-id="2f117-159">You should also hold down the CTRL key at the same time you right click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="2f117-160">Let op het SMTP-adres van de client tegen een ' auth '-type ' Bearer \* ', dat staat voor het dragertoken dat in OAuth wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2f117-160">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
 <span data-ttu-id="2f117-161">**Opmerking** Wilt u Skype voor bedrijven configureren met HMA?</span><span class="sxs-lookup"><span data-stu-id="2f117-161">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="2f117-162">U hebt twee artikelen nodig: een die de [ondersteunde topologieën](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)bevat, en een ervan waarin u ziet [hoe u de configuratie kunt uitvoeren](configure-skype-for-business-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2f117-162">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>
 
## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="2f117-163">Hybride moderne verificatie gebruiken met Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="2f117-163">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="2f117-164">Als u een on-premises klant bent met Exchange Server op TCP 443, moet u de volgende IP-bereiken whitelist:  </span><span class="sxs-lookup"><span data-stu-id="2f117-164">If you are an on-premises customer using Exchange server on TCP 443, please whitelist the following IP ranges:  </span></span><BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR>

## <a name="related-topics"></a><span data-ttu-id="2f117-165">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2f117-165">Related topics</span></span>

[<span data-ttu-id="2f117-166">Configuratievereisten voor moderne verificatie voor overgang van Office 365 dedicated/ITAR naar vNext ontgrendelen</span><span class="sxs-lookup"><span data-stu-id="2f117-166">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
