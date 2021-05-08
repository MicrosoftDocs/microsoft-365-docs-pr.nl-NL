---
title: On-premises Exchange Server configureren voor het gebruik van hybride moderne verificatie
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
description: Meer informatie over het configureren Exchange Server on-premises voor het gebruik van HMA (Hybrid Modern Authentication), met veiligere gebruikersverificatie en autorisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cb6d25a346ac48c9875a26f385cb733f1ff051f
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259449"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="30130-103">On-premises Exchange Server configureren voor het gebruik van hybride moderne verificatie</span><span class="sxs-lookup"><span data-stu-id="30130-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="30130-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="30130-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="30130-105">HMA (Hybrid Modern Authentication) is een methode voor identiteitsbeheer die veiligere gebruikersverificatie en autorisatie biedt en beschikbaar is voor on-premises Exchange-server.</span><span class="sxs-lookup"><span data-stu-id="30130-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="30130-106">TER INFORMATIE</span><span class="sxs-lookup"><span data-stu-id="30130-106">FYI</span></span>

<span data-ttu-id="30130-107">Voordat we beginnen, bel ik:</span><span class="sxs-lookup"><span data-stu-id="30130-107">Before we begin, I call:</span></span>

- <span data-ttu-id="30130-108">Hybride moderne verificatie \> HMA</span><span class="sxs-lookup"><span data-stu-id="30130-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="30130-109">Exchange on-premises \> EXCH</span><span class="sxs-lookup"><span data-stu-id="30130-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="30130-110">\>Exchange Online EXO</span><span class="sxs-lookup"><span data-stu-id="30130-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="30130-111">Als een afbeelding in dit artikel een object bevat dat 'grijs'of 'grijs' is, betekent dit dat het element dat in grijs wordt weergegeven, niet is opgenomen *in HMA-specifieke configuratie.*</span><span class="sxs-lookup"><span data-stu-id="30130-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="30130-112">Hybride moderne verificatie inschakelen</span><span class="sxs-lookup"><span data-stu-id="30130-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="30130-113">HMA in- of uitschakelen betekent:</span><span class="sxs-lookup"><span data-stu-id="30130-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="30130-114">Zorg ervoor dat u aan de prereqs voldoet voordat u begint.</span><span class="sxs-lookup"><span data-stu-id="30130-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="30130-115">Aangezien veel **vereisten** gebruikelijk zijn voor zowel Skype voor Bedrijven als Exchange, zijn hybride moderne verificatieoverzicht en vereisten voor het gebruik ervan met [on-premises Skype voor Bedrijven](hybrid-modern-auth-overview.md)en Exchange servers.</span><span class="sxs-lookup"><span data-stu-id="30130-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="30130-116">Doe dit voordat u een van de stappen in dit artikel start.</span><span class="sxs-lookup"><span data-stu-id="30130-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="30130-117">On-premises webservice-URL's toevoegen als **SPN's (Service Principal Names)** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="30130-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="30130-118">Als EXCH hybride is met meerdere **tenants,** moeten deze on-premises webservice-URL's worden toegevoegd als SPN's in de Azure AD van alle tenants die hybride zijn met EXCH.</span><span class="sxs-lookup"><span data-stu-id="30130-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="30130-119">Ervoor zorgen dat alle virtuele directories zijn ingeschakeld voor HMA</span><span class="sxs-lookup"><span data-stu-id="30130-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="30130-120">Controleren op het object Auth Server van EvoSTS</span><span class="sxs-lookup"><span data-stu-id="30130-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="30130-121">HMA inschakelen in EXCH.</span><span class="sxs-lookup"><span data-stu-id="30130-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="30130-122">Ondersteunt uw versie van Office ma?</span><span class="sxs-lookup"><span data-stu-id="30130-122">Does your version of Office support MA?</span></span> <span data-ttu-id="30130-123">Zie [Hoe moderne verificatie werkt voor Office 2013 en Office 2016-client-apps.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="30130-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="30130-124">Zorg ervoor dat u aan alle vereisten voldoet</span><span class="sxs-lookup"><span data-stu-id="30130-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="30130-125">Aangezien veel vereisten gebruikelijk zijn voor zowel Skype voor Bedrijven als Exchange, controleert u het overzicht van hybride moderne verificatie en vereisten voor het gebruik ervan met [on-premises Skype voor Bedrijven](hybrid-modern-auth-overview.md)en Exchange servers.</span><span class="sxs-lookup"><span data-stu-id="30130-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="30130-126">Doe dit  *voordat*  u een van de stappen in dit artikel start.</span><span class="sxs-lookup"><span data-stu-id="30130-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="30130-127">Outlook Web App en Exchange configuratiescherm werkt niet met hybride moderne verificatie.</span><span class="sxs-lookup"><span data-stu-id="30130-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="30130-128">On-premises webservice-URL's toevoegen als SPN's in Azure AD</span><span class="sxs-lookup"><span data-stu-id="30130-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="30130-129">Voer de opdrachten uit die uw on-premises webservice-URL's toewijzen als Azure AD SPN's.</span><span class="sxs-lookup"><span data-stu-id="30130-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="30130-130">SPN's worden gebruikt door clientapparaten en apparaten tijdens verificatie en autorisatie.</span><span class="sxs-lookup"><span data-stu-id="30130-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="30130-131">Alle URL's die kunnen worden gebruikt om verbinding te maken van on-premises naar Azure Active Directory (Azure AD) moeten zijn geregistreerd in Azure AD (dit omvat zowel interne als externe naamruimten).</span><span class="sxs-lookup"><span data-stu-id="30130-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="30130-132">Verzamel eerst alle URL's die u in AAD moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="30130-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="30130-133">Voer deze opdrachten on-premises uit:</span><span class="sxs-lookup"><span data-stu-id="30130-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

<span data-ttu-id="30130-134">Zorg ervoor dat de URL's waar verbinding mee kan worden gemaakt, worden weergegeven als HTTPS-service principal names in AAD.</span><span class="sxs-lookup"><span data-stu-id="30130-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="30130-135">Als EXCH hybride is met meerdere **tenants,** moeten deze HTTPS-SPN's worden toegevoegd in de AAD van alle tenants in hybride versie van EXCH.</span><span class="sxs-lookup"><span data-stu-id="30130-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="30130-136">Maak eerst verbinding met AAD met [deze instructies.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="30130-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="30130-137">U moet de optie _Verbinding maken-MsolService_ op deze pagina gebruiken om de onderstaande opdracht te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="30130-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="30130-138">Voor uw Exchange-gerelateerde URL's typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="30130-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="30130-139">Noteer (en schermafbeelding voor latere vergelijking) de uitvoer van deze opdracht, die een https://  *autodiscover.yourdomain.com*  en https://  *mail.yourdomain.com-URL* moet bevatten, maar meestal bestaat uit SPN's die beginnen met 00000002-0000-0ff1-ce00-0000000000/.</span><span class="sxs-lookup"><span data-stu-id="30130-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="30130-140">Als er https:// url's van uw on-premises url's ontbreken, moeten we deze specifieke records toevoegen aan deze lijst.</span><span class="sxs-lookup"><span data-stu-id="30130-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="30130-141">Als u uw interne en externe MAPI/HTTP-, EWS-, ActiveSync-, OAB- en Autodiscover-records niet ziet in deze lijst, moet u deze toevoegen met de onderstaande opdracht (het voorbeeld-URL's zijn ' ' en ' ', maar u vervangt de voorbeeld-URL's door uw `mail.corp.contoso.com` `owa.contoso.com` **eigen** URL's):</span><span class="sxs-lookup"><span data-stu-id="30130-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="30130-142">Controleer of de nieuwe records zijn toegevoegd door de opdracht Get-MsolServicePrincipal stap 2 opnieuw uit te voeren en door de uitvoer te kijken.</span><span class="sxs-lookup"><span data-stu-id="30130-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="30130-143">Vergelijk de lijst /schermafbeelding van vóór met de nieuwe lijst met SPN's.</span><span class="sxs-lookup"><span data-stu-id="30130-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="30130-144">Mogelijk maakt u ook een schermafbeelding van de nieuwe lijst voor uw records.</span><span class="sxs-lookup"><span data-stu-id="30130-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="30130-145">Als u succes hebt gehad, ziet u de twee nieuwe URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="30130-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="30130-146">Als u naar ons voorbeeld gaat, bevat de lijst met SPN's nu de specifieke URL's  `https://mail.corp.contoso.com`  en  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="30130-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="30130-147">Controleren of virtuele adresgegevens correct zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="30130-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="30130-148">Controleer nu of OAuth correct is ingeschakeld in Exchange op alle virtuele Outlook door de volgende opdrachten uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="30130-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="30130-149">Controleer de uitvoer om te controleren of **OAuth** is ingeschakeld op elk van deze VDirs, het ziet er zo uit (en het belangrijkste wat u moet bekijken is 'OAuth'):</span><span class="sxs-lookup"><span data-stu-id="30130-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="30130-150">Als OAuth ontbreekt op een server en een van de vier virtuele directories, moet u deze toevoegen met behulp van de relevante opdrachten voordat u verdergaat ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)en [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="30130-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="30130-151">Bevestig dat het Object Auth Server van EvoSTS aanwezig is</span><span class="sxs-lookup"><span data-stu-id="30130-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="30130-152">Ga terug naar de on-premises Exchange Management Shell voor deze laatste opdracht.</span><span class="sxs-lookup"><span data-stu-id="30130-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="30130-153">U kunt nu valideren dat uw on-premises vermelding een vermelding heeft voor de provider van de verificatieprovider van evoSTS:</span><span class="sxs-lookup"><span data-stu-id="30130-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

<span data-ttu-id="30130-154">De uitvoer moet een AuthServer van de naam EvoSts laten zien en de status 'Ingeschakeld' moet Waar zijn.</span><span class="sxs-lookup"><span data-stu-id="30130-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="30130-155">Als u dit niet ziet, moet u de meest recente versie van de wizard Hybride configuratie downloaden en uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="30130-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="30130-156">Als EXCH hybride is met meerdere **tenants,** moet in de uitvoer één AuthServer van de naam EvoSts worden getoond : {GUID} voor elke tenant in hybride versie met EXCH en moet de status 'Ingeschakeld' Waar zijn voor al deze AuthServer-objecten.</span><span class="sxs-lookup"><span data-stu-id="30130-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="30130-157">**Belangrijk** Als u een Exchange 2010 in uw omgeving gebruikt, wordt de Provider voor Verificatie van EvoSTS niet gemaakt.</span><span class="sxs-lookup"><span data-stu-id="30130-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="30130-158">HMA inschakelen</span><span class="sxs-lookup"><span data-stu-id="30130-158">Enable HMA</span></span>

<span data-ttu-id="30130-159">Voer de volgende opdracht uit in de Exchange Management Shell, on-premises:</span><span class="sxs-lookup"><span data-stu-id="30130-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="30130-160">Als de EXCH-versie Exchange 2016 (CU18 of hoger) of Exchange 2019 (CU7 of hoger) is en hybride is geconfigureerd met HCW die is gedownload na september 2020, voer dan de volgende opdracht uit in de Exchange Management Shell, on-premises:</span><span class="sxs-lookup"><span data-stu-id="30130-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="30130-161">Als EXCH hybride is met meerdere **tenants,** zijn er meerdere AuthServer-objecten aanwezig in EXCH met domeinen die overeenkomen met elke tenant.</span><span class="sxs-lookup"><span data-stu-id="30130-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="30130-162">De **vlag IsDefaultAuthorizationEndpoint** moet zijn ingesteld op waar (met de **cmdlet IsDefaultAuthorizationEndpoint)** voor een van deze AuthServer-objecten.</span><span class="sxs-lookup"><span data-stu-id="30130-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="30130-163">Deze vlag kan niet worden ingesteld op waar voor alle Authserver-objecten en HMA is zelfs ingeschakeld als een van de **isDefaultAuthorizationEndpoint-vlag** van een van deze AuthServer-objecten is ingesteld op waar.</span><span class="sxs-lookup"><span data-stu-id="30130-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="30130-164">Controleren</span><span class="sxs-lookup"><span data-stu-id="30130-164">Verify</span></span>

<span data-ttu-id="30130-165">Wanneer u HMA hebt ingeschakeld, wordt de nieuwe auth-stroom gebruikt voor de volgende aanmelding van een klant.</span><span class="sxs-lookup"><span data-stu-id="30130-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="30130-166">Houd er rekening mee dat u met het in-/uitschakelen van HMA geen herauthenticatie voor een client kunt activeren.</span><span class="sxs-lookup"><span data-stu-id="30130-166">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="30130-167">De clients reauthenticate op basis van de levensduur van de auth tokens en/of certs die ze hebben.</span><span class="sxs-lookup"><span data-stu-id="30130-167">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="30130-168">U moet ook de Ctrl-toets ingedrukt houden terwijl u met de rechtermuisknop op het pictogram voor de Outlook-client (ook in het Windows-systeemvak) klikt en klikt u op 'Verbindingsstatus'.</span><span class="sxs-lookup"><span data-stu-id="30130-168">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="30130-169">Zoek naar het SMTP-adres van de klant tegen het type 'Authn' van 'Bearer', dat het token voor de toler vertegenwoordigt dat \* in OAuth wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="30130-169">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="30130-170">Wilt u Skype voor Bedrijven met HMA configureren?</span><span class="sxs-lookup"><span data-stu-id="30130-170">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="30130-171">U hebt twee artikelen nodig: een met ondersteunde [toologieën](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)en een waarin u kunt zien hoe u [de configuratie kunt doen.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="30130-171">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="30130-172">Hybride moderne verificatie gebruiken met Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="30130-172">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="30130-173">Als u een on-premises klant bent met Exchange server op TCP 443, kunt u de verwerking van verkeer voor de volgende IP-adresbereiken omzeilen:</span><span class="sxs-lookup"><span data-stu-id="30130-173">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="30130-174">De Outlook-app voor iOS en Android is ontworpen als de beste manier om Microsoft 365 of Office 365 op uw mobiele apparaat te ervaren met behulp van Microsoft-services om uw dagelijkse leven en werk te vinden, plannen en prioriteit te geven.</span><span class="sxs-lookup"><span data-stu-id="30130-174">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="30130-175">Zie Hybride moderne verificatie gebruiken met Outlook [voor iOS en Android voor meer informatie.](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019)</span><span class="sxs-lookup"><span data-stu-id="30130-175">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span></span>

## <a name="related-topics"></a><span data-ttu-id="30130-176">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="30130-176">Related topics</span></span>

[<span data-ttu-id="30130-177">Moderne verificatieconfiguratievereisten voor de overgang van Office 365 dedicated/ITAR naar vNext</span><span class="sxs-lookup"><span data-stu-id="30130-177">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
