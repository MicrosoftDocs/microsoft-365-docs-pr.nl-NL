---
title: Exchange Server on-premises configureren voor het gebruik van hybride moderne verificatie
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
description: Meer informatie over het configureren van een on-premises Exchange Server voor het gebruik van HMA (Hybrid Modern Authentication), met een veiligere gebruikersverificatie en autorisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 46646f35d3b41821424269f66721fbf829d339f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928200"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="1dee3-103">Exchange Server on-premises configureren voor het gebruik van hybride moderne verificatie</span><span class="sxs-lookup"><span data-stu-id="1dee3-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="1dee3-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1dee3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1dee3-105">HMA (Hybrid Modern Authentication) is een methode voor identiteitsbeheer die veiligere gebruikersverificatie en autorisatie biedt en beschikbaar is voor on-premises hybride implementaties van Exchange-server.</span><span class="sxs-lookup"><span data-stu-id="1dee3-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="1dee3-106">TER INFORMATIE</span><span class="sxs-lookup"><span data-stu-id="1dee3-106">FYI</span></span>

<span data-ttu-id="1dee3-107">Voordat we beginnen, bel ik:</span><span class="sxs-lookup"><span data-stu-id="1dee3-107">Before we begin, I call:</span></span>

- <span data-ttu-id="1dee3-108">Hybride moderne verificatie \> HMA</span><span class="sxs-lookup"><span data-stu-id="1dee3-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="1dee3-109">Exchange on-premises \> EXCH</span><span class="sxs-lookup"><span data-stu-id="1dee3-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="1dee3-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="1dee3-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="1dee3-111">Als een afbeelding in dit artikel een object bevat dat 'grijs'of 'grijs' is, betekent dit dat het element dat in grijs wordt weergegeven, niet is opgenomen *in HMA-specifieke configuratie.*</span><span class="sxs-lookup"><span data-stu-id="1dee3-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="1dee3-112">Hybride moderne verificatie inschakelen</span><span class="sxs-lookup"><span data-stu-id="1dee3-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="1dee3-113">HMA in- of uitschakelen betekent:</span><span class="sxs-lookup"><span data-stu-id="1dee3-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="1dee3-114">Zorg ervoor dat u aan de prereqs voldoet voordat u begint.</span><span class="sxs-lookup"><span data-stu-id="1dee3-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="1dee3-115">Aangezien veel **vereisten gebruikelijk** zijn voor zowel Skype voor Bedrijven als Exchange, zijn hybride moderne verificatieoverzicht en vereisten voor het gebruik ervan met on-premises Skype voor Bedrijven- en [Exchange-servers vereist.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1dee3-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="1dee3-116">Doe dit voordat u een van de stappen in dit artikel start.</span><span class="sxs-lookup"><span data-stu-id="1dee3-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="1dee3-117">On-premises webservice-URL's toevoegen als **SPN's (Service Principal Names)** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1dee3-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="1dee3-118">Ervoor zorgen dat alle virtuele directories zijn ingeschakeld voor HMA</span><span class="sxs-lookup"><span data-stu-id="1dee3-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="1dee3-119">Controleren op het object Auth Server van EvoSTS</span><span class="sxs-lookup"><span data-stu-id="1dee3-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="1dee3-120">HMA inschakelen in EXCH.</span><span class="sxs-lookup"><span data-stu-id="1dee3-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="1dee3-121">**Opmerking** Ondersteunt uw versie van Office MA?</span><span class="sxs-lookup"><span data-stu-id="1dee3-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="1dee3-122">Zie [Hoe moderne verificatie werkt voor office 2013- en Office 2016-client-apps.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="1dee3-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="1dee3-123">Zorg ervoor dat u aan alle vereisten voldoet</span><span class="sxs-lookup"><span data-stu-id="1dee3-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="1dee3-124">Aangezien veel vereisten gebruikelijk zijn voor zowel Skype voor Bedrijven als Exchange, bekijkt u hybride moderne verificatieoverzicht en vereisten voor het gebruik ervan met on-premises Skype voor Bedrijven- en [Exchange-servers.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1dee3-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="1dee3-125">Doe dit  *voordat*  u een van de stappen in dit artikel start.</span><span class="sxs-lookup"><span data-stu-id="1dee3-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="1dee3-126">On-premises webservice-URL's toevoegen als SPN's in Azure AD</span><span class="sxs-lookup"><span data-stu-id="1dee3-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="1dee3-127">Voer de opdrachten uit die uw on-premises webservice-URL's toewijzen als Azure AD SPN's.</span><span class="sxs-lookup"><span data-stu-id="1dee3-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="1dee3-128">SPN's worden gebruikt door clientapparaten en apparaten tijdens verificatie en autorisatie.</span><span class="sxs-lookup"><span data-stu-id="1dee3-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="1dee3-129">Alle URL's die kunnen worden gebruikt om verbinding te maken van on-premises naar Azure Active Directory (Azure AD) moeten zijn geregistreerd in Azure AD (dit omvat zowel interne als externe naamruimten).</span><span class="sxs-lookup"><span data-stu-id="1dee3-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="1dee3-130">Verzamel eerst alle URL's die u in AAD moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="1dee3-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="1dee3-131">Voer deze opdrachten on-premises uit:</span><span class="sxs-lookup"><span data-stu-id="1dee3-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="1dee3-132">Zorg ervoor dat de URL's waar verbinding mee kan worden gemaakt, worden weergegeven als HTTPS-service principal names in AAD.</span><span class="sxs-lookup"><span data-stu-id="1dee3-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="1dee3-133">Maak eerst verbinding met AAD met [deze instructies.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1dee3-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="1dee3-134">**Opmerking** U moet de optie _Connect-MsolService_ op deze pagina gebruiken om de onderstaande opdracht te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1dee3-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="1dee3-135">Typ de volgende opdracht voor uw Exchange-gerelateerde URL's:</span><span class="sxs-lookup"><span data-stu-id="1dee3-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="1dee3-136">Noteer (en schermafbeelding voor latere vergelijking) de uitvoer van deze opdracht, die een https://  *autodiscover.yourdomain.com*  en https://  *mail.yourdomain.com-URL* moet bevatten, maar meestal bestaat uit SPN's die beginnen met 00000002-0000-0ff1-ce00-0000000000/.</span><span class="sxs-lookup"><span data-stu-id="1dee3-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="1dee3-137">Als er https:// url's van uw on-premises url's ontbreken, moeten we deze specifieke records toevoegen aan deze lijst.</span><span class="sxs-lookup"><span data-stu-id="1dee3-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="1dee3-138">Als u uw interne en externe MAPI/HTTP-, EWS-, ActiveSync-, OAB- en Autodiscover-records niet ziet in deze lijst, moet u deze toevoegen met de onderstaande opdracht (het voorbeeld-URL's zijn ' ' en ' ', maar u vervangt de voorbeeld-URL's door uw `mail.corp.contoso.com` `owa.contoso.com` **eigen** URL's):</span><span class="sxs-lookup"><span data-stu-id="1dee3-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="1dee3-139">Controleer of de nieuwe records zijn toegevoegd door de opdracht Get-MsolServicePrincipal stap 2 opnieuw uit te voeren en door de uitvoer te kijken.</span><span class="sxs-lookup"><span data-stu-id="1dee3-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="1dee3-140">Vergelijk de lijst /schermafbeelding van vóór met de nieuwe lijst met SPN's.</span><span class="sxs-lookup"><span data-stu-id="1dee3-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="1dee3-141">Mogelijk maakt u ook een schermafbeelding van de nieuwe lijst voor uw records.</span><span class="sxs-lookup"><span data-stu-id="1dee3-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="1dee3-142">Als u succes hebt gehad, ziet u de twee nieuwe URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="1dee3-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="1dee3-143">Als u naar ons voorbeeld gaat, bevat de lijst met SPN's nu de specifieke URL's  `https://mail.corp.contoso.com`  en  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1dee3-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="1dee3-144">Controleren of virtuele adresgegevens correct zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="1dee3-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="1dee3-145">Controleer nu of OAuth correct is ingeschakeld in Exchange op alle virtuele adreslijst die Outlook kan gebruiken door de volgende opdrachten uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="1dee3-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="1dee3-146">Controleer de uitvoer om te controleren of **OAuth** is ingeschakeld op elk van deze VDirs, het ziet er zo uit (en het belangrijkste wat u moet bekijken is 'OAuth'):</span><span class="sxs-lookup"><span data-stu-id="1dee3-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="1dee3-147">Als OAuth ontbreekt op een server en een van de vier virtuele directories, moet u deze toevoegen met behulp van de relevante opdrachten voordat u verdergaat ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)en [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="1dee3-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="1dee3-148">Bevestig dat het Object Auth Server van EvoSTS aanwezig is</span><span class="sxs-lookup"><span data-stu-id="1dee3-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="1dee3-149">Ga terug naar de on-premises Exchange Management Shell voor deze laatste opdracht.</span><span class="sxs-lookup"><span data-stu-id="1dee3-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="1dee3-150">U kunt nu valideren dat uw on-premises vermelding een vermelding heeft voor de provider van de verificatieprovider van evoSTS:</span><span class="sxs-lookup"><span data-stu-id="1dee3-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="1dee3-151">De uitvoer moet een AuthServer van de naam EvoSts laten zien en de status 'Ingeschakeld' moet Waar zijn.</span><span class="sxs-lookup"><span data-stu-id="1dee3-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="1dee3-152">Als u dit niet ziet, moet u de meest recente versie van de wizard Hybride configuratie downloaden en uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="1dee3-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="1dee3-153">**Belangrijk** Als u Exchange 2010 in uw omgeving gebruikt, wordt de Verificatieprovider van EvoSTS niet gemaakt.</span><span class="sxs-lookup"><span data-stu-id="1dee3-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="1dee3-154">HMA inschakelen</span><span class="sxs-lookup"><span data-stu-id="1dee3-154">Enable HMA</span></span>

<span data-ttu-id="1dee3-155">Voer de volgende opdracht uit in de On-premises Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="1dee3-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="1dee3-156">Controleren</span><span class="sxs-lookup"><span data-stu-id="1dee3-156">Verify</span></span>

<span data-ttu-id="1dee3-157">Wanneer u HMA hebt ingeschakeld, wordt de nieuwe auth-stroom gebruikt voor de volgende aanmelding van een klant.</span><span class="sxs-lookup"><span data-stu-id="1dee3-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="1dee3-158">Houd er rekening mee dat u met het in-/uitschakelen van HMA geen herauthenticatie voor een client kunt activeren.</span><span class="sxs-lookup"><span data-stu-id="1dee3-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="1dee3-159">De clients reauthenticate op basis van de levensduur van de auth tokens en/of certs die ze hebben.</span><span class="sxs-lookup"><span data-stu-id="1dee3-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="1dee3-160">U moet ook de Ctrl-toets ingedrukt houden terwijl u met de rechtermuisknop op het pictogram voor de Outlook-client klikt (ook in het windows-systeemvak) en klikt u op 'Verbindingsstatus'.</span><span class="sxs-lookup"><span data-stu-id="1dee3-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="1dee3-161">Zoek naar het SMTP-adres van de klant tegen het type 'Authn' van 'Bearer', dat het token voor de toler vertegenwoordigt dat \* in OAuth wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="1dee3-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="1dee3-162">**Opmerking** Wilt u Skype voor Bedrijven configureren met HMA?</span><span class="sxs-lookup"><span data-stu-id="1dee3-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="1dee3-163">U hebt twee artikelen nodig: een met ondersteunde [toologieën](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)en een waarin u kunt zien hoe u [de configuratie kunt doen.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="1dee3-163">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="1dee3-164">Hybride moderne verificatie gebruiken met Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="1dee3-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="1dee3-165">Als u een on-premises klant bent die Exchange-server gebruikt op TCP 443, kunt u de verwerking van verkeer voor de volgende IP-bereik omzeilen:</span><span class="sxs-lookup"><span data-stu-id="1dee3-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="1dee3-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1dee3-166">Related topics</span></span>

[<span data-ttu-id="1dee3-167">Moderne verificatieconfiguratievereisten voor de overgang van Office 365 dedicated/ITAR naar vNext</span><span class="sxs-lookup"><span data-stu-id="1dee3-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)