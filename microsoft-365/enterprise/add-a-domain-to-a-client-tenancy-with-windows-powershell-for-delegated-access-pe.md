---
title: Een domein toevoegen aan een client tenancy met Windows PowerShell voor DAP-partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Overzicht: Gebruik PowerShell voor Microsoft 365 om een alternatieve domeinnaam toe te voegen aan een bestaande klant tenant.'
ms.openlocfilehash: b6a40f387f9fc7e513137cda4253a62be2455aad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905570"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="9fdfa-103">Een domein toevoegen aan een client tenancy met Windows PowerShell voor DAP-partners (Gedelegeerde toegangsmachtiging)</span><span class="sxs-lookup"><span data-stu-id="9fdfa-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="9fdfa-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9fdfa-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9fdfa-105">U kunt sneller nieuwe domeinen maken en koppelen aan de huurovereenkomst van uw klant met PowerShell voor Microsoft 365 dan met het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="9fdfa-106">DAP-partners (Gedelegeerde Access Permission) zijn Syndication- en Cloud Solution Providers (CSP)-partners.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="9fdfa-107">Ze zijn vaak netwerk- of telecomproviders voor andere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="9fdfa-108">Ze bundelen Microsoft 365-abonnementen in hun serviceaanbiedingen voor hun klanten.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="9fdfa-109">Wanneer ze een Microsoft 365-abonnement verkopen, krijgen ze automatisch machtigingen voor beheer namens (AOBO) aan de klanten, zodat ze de klantentenancies kunnen beheren en rapporteren.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9fdfa-110">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="9fdfa-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="9fdfa-111">Voor de procedures in dit onderwerp moet u verbinding maken met [Microsoft 365 met PowerShell.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9fdfa-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="9fdfa-112">U hebt ook de referenties van de partnertenatiebeheerder nodig.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-112">You also need your partner tenant administrator credentials.</span></span>
  
<span data-ttu-id="9fdfa-113">U hebt ook de volgende informatie nodig:</span><span class="sxs-lookup"><span data-stu-id="9fdfa-113">You also need the following information:</span></span>
  
- <span data-ttu-id="9fdfa-114">U hebt de volledig gekwalificeerde domeinnaam (FQDN) nodig die uw klant wil.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>
    
- <span data-ttu-id="9fdfa-115">U hebt de **TenantId** van de klant nodig.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-115">You need the customer's **TenantId**.</span></span>
    
- <span data-ttu-id="9fdfa-116">De FQDN moet zijn geregistreerd bij een DNS-registrar (Internet Domain Name Service), zoals GoDaddy.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-116">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy.</span></span> <span data-ttu-id="9fdfa-117">Zie Een domeinnaam kopen voor meer informatie over het openbaar registreren van [een domeinnaam.](../admin/get-help-with-domains/buy-a-domain-name.md)</span><span class="sxs-lookup"><span data-stu-id="9fdfa-117">For more information on how to publically register a domain name, see [How to buy a domain name](../admin/get-help-with-domains/buy-a-domain-name.md).</span></span>
    
- <span data-ttu-id="9fdfa-118">U moet weten hoe u een TXT-record toevoegt aan de geregistreerde DNS-zone voor uw DNS-registrar.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="9fdfa-119">Zie [DNS-records](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)toevoegen om uw domein te verbinden voor meer informatie over het toevoegen van een TXT-record.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="9fdfa-120">Als deze procedures niet voor u werken, moet u de procedures voor uw DNS-registrar vinden.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>
    
## <a name="create-domains"></a><span data-ttu-id="9fdfa-121">Domeinen maken</span><span class="sxs-lookup"><span data-stu-id="9fdfa-121">Create domains</span></span>

 <span data-ttu-id="9fdfa-122">Uw klanten zullen u waarschijnlijk vragen om extra domeinen te maken om te koppelen aan hun huurovereenkomst, omdat ze niet willen dat het standaard .onmicrosoft.com-domein het primaire domein is dat hun bedrijfsidentiteiten aan de wereld <domain> vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-122">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world.</span></span> <span data-ttu-id="9fdfa-123">Met deze procedure maakt u een nieuw domein dat is gekoppeld aan de huurovereenkomst van uw klant.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-123">This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fdfa-124">Als u een aantal van deze bewerkingen wilt uitvoeren,  moet het  account van de partnerbeheerder bij wie u zich aanlogt, zijn ingesteld op Volledig beheer voor de instelling Beheerderstoegang toewijzen aan bedrijven die u ondersteunt in de details van het beheerdersaccount in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9fdfa-125">Zie Partners: Gedelegeerd beheer aanbieden voor meer informatie over het beheren van rollen van [partnerbeheerders.](https://go.microsoft.com/fwlink/p/?LinkId=532435)</span><span class="sxs-lookup"><span data-stu-id="9fdfa-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span> 
  
### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="9fdfa-126">Het domein maken in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9fdfa-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="9fdfa-127">Met deze opdracht wordt het domein gemaakt in Azure Active Directory, maar wordt het niet aan het openbaar geregistreerde domein koppelen.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="9fdfa-128">Dat komt wanneer u bewijst dat u eigenaar bent van het openbaar geregistreerde domein bij Microsoft Microsoft 365 voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
><span data-ttu-id="9fdfa-129">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="9fdfa-130">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="9fdfa-131">De gegevens voor de DNS TXT-verificatierecord</span><span class="sxs-lookup"><span data-stu-id="9fdfa-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="9fdfa-132">Microsoft 365 genereert de specifieke gegevens die u in de DNS TXT-verificatierecord moet plaatsen.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="9fdfa-133">Voer deze opdracht uit om de gegevens op te halen.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-133">To get the data, run this command.</span></span>
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="9fdfa-134">Hierdoor krijgt u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="9fdfa-134">This will give you output like:</span></span>
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> <span data-ttu-id="9fdfa-135">U hebt deze tekst nodig om de TXT-record te maken in de openbaar geregistreerde DNS-zone.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="9fdfa-136">Kopieer en sla het op.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-136">Be sure to copy and save it.</span></span> 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="9fdfa-137">Een TXT-record toevoegen aan de openbaar geregistreerde DNS-zone</span><span class="sxs-lookup"><span data-stu-id="9fdfa-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="9fdfa-138">Voordat Microsoft 365 verkeer accepteert dat is doorgestuurd naar de openbaar geregistreerde domeinnaam, moet u aantonen dat u de eigenaar bent van het domein en dat u beheerdersmachtigingen voor het domein hebt.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="9fdfa-139">U bewijst dat u de eigenaar bent van het domein door een TXT-record in het domein te maken.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="9fdfa-140">Een TXT-record doet niets in uw domein en kan worden verwijderd nadat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="9fdfa-141">Als u de TXT-records wilt maken, volgt u de procedures bij [DNS-records toevoegen om uw domein te verbinden.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="9fdfa-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="9fdfa-142">Als deze procedures niet voor u werken, moet u de procedures voor uw DNS-registrar vinden.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>
  
<span data-ttu-id="9fdfa-143">Bevestig de succesvolle creatie van de TXT-record via nslookup.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-143">Confirm the successful creation of the TXT record via nslookup.</span></span> <span data-ttu-id="9fdfa-144">Volg deze syntaxis.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-144">Follow this syntax.</span></span>
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="9fdfa-145">Hierdoor krijgt u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="9fdfa-145">This will give you output like:</span></span>
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="9fdfa-146">Domeineigendom valideren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9fdfa-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="9fdfa-147">In deze laatste stap valideert u bij Microsoft 365 dat u eigenaar bent van het openbaar geregistreerde domein.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="9fdfa-148">Na deze stap accepteert Microsoft 365 verkeer dat is doorgeleid naar de nieuwe domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="9fdfa-149">Voer deze opdracht uit om het proces voor het maken en registreren van domeinen te voltooien.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-149">To complete the domain creation and registration process, run this command.</span></span> 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="9fdfa-150">Met deze opdracht wordt geen uitvoer als resultaat gegeven, dus voer deze opdracht uit om te bevestigen dat dit heeft gewerkt.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="9fdfa-151">Dit zal zoiets als dit retourneren</span><span class="sxs-lookup"><span data-stu-id="9fdfa-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a><span data-ttu-id="9fdfa-152">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9fdfa-152">See also</span></span>

#### 

[<span data-ttu-id="9fdfa-153">Help voor partners</span><span class="sxs-lookup"><span data-stu-id="9fdfa-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)