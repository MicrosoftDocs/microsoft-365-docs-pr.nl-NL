---
title: Een domein toevoegen aan een client, pacht met Windows PowerShell voor DAP partners
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
description: 'Overzicht: gebruik PowerShell voor Microsoft 365 om een alternatieve domeinnaam toe te voegen aan een bestaande Tenant van de klant.'
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689527"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="690dc-103">Een domein toevoegen aan een client, pacht met Windows PowerShell voor gedelegeerde toegangsrechten (DAP)-partners</span><span class="sxs-lookup"><span data-stu-id="690dc-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="690dc-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="690dc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="690dc-105">U kunt nieuwe domeinen maken en aan de pacht van de klant koppelen met behulp van PowerShell voor Microsoft 365, dan via het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="690dc-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="690dc-106">De partners van de gedelegeerde toegang (machtigingen) zijn syndicaties en partners van een Cloud solution provider.</span><span class="sxs-lookup"><span data-stu-id="690dc-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="690dc-107">Vaak zijn ze netwerk-of telecommunicatie providers van andere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="690dc-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="690dc-108">Ze bundelt Microsoft 365-abonnementen in hun serviceaanbiedingen voor hun klanten.</span><span class="sxs-lookup"><span data-stu-id="690dc-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="690dc-109">Wanneer iemand een Microsoft 365-abonnement verkoopt, worden er automatisch beheermachtigingen verleend namens (AOBO) aan de klant tenancies zodat ze de klant tenancies kunnen beheren en rapporteren.</span><span class="sxs-lookup"><span data-stu-id="690dc-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="690dc-110">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="690dc-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="690dc-111">Voor de procedures in dit onderwerp moet u verbinding kunnen maken met [Microsoft 365 met PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="690dc-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="690dc-112">U hebt ook uw Tenant-beheerderreferenties voor uw partners nodig.</span><span class="sxs-lookup"><span data-stu-id="690dc-112">You also need your partner tenant administrator credentials.</span></span>
  
<span data-ttu-id="690dc-113">Ook hebt u de volgende gegevens nodig:</span><span class="sxs-lookup"><span data-stu-id="690dc-113">You also need the following information:</span></span>
  
- <span data-ttu-id="690dc-114">U hebt de FQDN-naam (Fully Qualified Domain Name) nodig die de klant wil.</span><span class="sxs-lookup"><span data-stu-id="690dc-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>
    
- <span data-ttu-id="690dc-115">U hebt de **TenantId**van de klant nodig.</span><span class="sxs-lookup"><span data-stu-id="690dc-115">You need the customer's **TenantId**.</span></span>
    
- <span data-ttu-id="690dc-116">U moet de FQDN registreren bij een DNS-registratie (Internet Domain Name Service), zoals GoDaddy.</span><span class="sxs-lookup"><span data-stu-id="690dc-116">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy.</span></span> <span data-ttu-id="690dc-117">Zie [een domeinnaam kopen](https://go.microsoft.com/fwlink/p/?LinkId=532541)voor meer informatie over het openbaar registreren van een domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="690dc-117">For more information on how to publically register a domain name, see [How to buy a domain name](https://go.microsoft.com/fwlink/p/?LinkId=532541).</span></span>
    
- <span data-ttu-id="690dc-118">U wilt weten hoe u een TXT-record kunt toevoegen aan de geregistreerde DNS-zone voor uw DNS-registratie.</span><span class="sxs-lookup"><span data-stu-id="690dc-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="690dc-119">Zie [DNS-records toevoegen om uw domein te koppelen](https://go.microsoft.com/fwlink/p/?LinkId=532542)voor meer informatie over het toevoegen van een TXT-record.</span><span class="sxs-lookup"><span data-stu-id="690dc-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="690dc-120">Als deze procedures niet voor u werken, moet u de procedures voor uw DNS-registratieservice vinden.</span><span class="sxs-lookup"><span data-stu-id="690dc-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>
    
## <a name="create-domains"></a><span data-ttu-id="690dc-121">Domeinen maken</span><span class="sxs-lookup"><span data-stu-id="690dc-121">Create domains</span></span>

 <span data-ttu-id="690dc-122">Uw klanten vragen u waarschijnlijk om extra domeinen te maken die u wilt koppelen aan hun pacht, omdat ze het standaarddomein van de <domain> onmicrosoft.com niet als primaire domein voor hun bedrijfsidentiteit voor de wereld vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="690dc-122">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world.</span></span> <span data-ttu-id="690dc-123">In deze procedure wordt u begeleid bij het maken van een nieuw domein dat is gekoppeld aan de pacht van uw klant.</span><span class="sxs-lookup"><span data-stu-id="690dc-123">This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="690dc-124">Voor het uitvoeren van enkele van deze bewerkingen moet het partner beheerdersaccount waarmee u zich aanmeldt, worden ingesteld op **volledig beheer** van de instelling **beheerderstoegang verlenen tot bedrijven die u** kunt instellen in de details van het beheerdersaccount in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="690dc-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="690dc-125">Voor meer informatie over het beheren van partner beheerdersrollen raadpleegt u [partners: gedelegeerd beheer bieden](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span><span class="sxs-lookup"><span data-stu-id="690dc-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span> 
  
### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="690dc-126">Het domein maken in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="690dc-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="690dc-127">Met deze opdracht maakt u het domein in azure Active Directory, maar wordt het niet gekoppeld aan het openbaar geregistreerde domein.</span><span class="sxs-lookup"><span data-stu-id="690dc-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="690dc-128">Dit wordt geleverd wanneer u bewijzen dat u de eigenaar bent van het domein dat u de eigenaar bent van het domein voor Microsoft 365 voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="690dc-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
><span data-ttu-id="690dc-129">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="690dc-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="690dc-130">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="690dc-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="690dc-131">De gegevens voor de DNS TXT-verificatie record weergeven</span><span class="sxs-lookup"><span data-stu-id="690dc-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="690dc-132">In Microsoft 365 worden de specifieke gegevens gegenereerd die u in de DNS-TXT-verificatie record moet plaatsen.</span><span class="sxs-lookup"><span data-stu-id="690dc-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="690dc-133">Als u de gegevens wilt weergeven, voert u deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="690dc-133">To get the data, run this command.</span></span>
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="690dc-134">U krijgt dan de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="690dc-134">This will give you output like:</span></span>
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> <span data-ttu-id="690dc-135">U hebt deze tekst nodig voor het maken van de TXT-record in de algemeen geregistreerde DNS-zone.</span><span class="sxs-lookup"><span data-stu-id="690dc-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="690dc-136">Zorg ervoor dat u het bestand kopieert en opslaat.</span><span class="sxs-lookup"><span data-stu-id="690dc-136">Be sure to copy and save it.</span></span> 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="690dc-137">Een TXT-record toevoegen aan de algemeen geregistreerde DNS-zone</span><span class="sxs-lookup"><span data-stu-id="690dc-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="690dc-138">Voordat Microsoft 365 het verkeer voor de naam van de algemeen geregistreerde domeinnaam accepteert, moet u bewijzen dat u de eigenaar bent van het domein en dat u beschikt over beheerdersmachtigingen voor het domein.</span><span class="sxs-lookup"><span data-stu-id="690dc-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="690dc-139">U bewijzen dat u de eigenaar bent van het domein door een TXT-record in het domein te maken.</span><span class="sxs-lookup"><span data-stu-id="690dc-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="690dc-140">Een TXT-record doet niets in uw domein en kan worden verwijderd nadat het eigendom van het domein is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="690dc-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="690dc-141">U maakt de TXT-records door de procedures te volgen bij [DNS-records toevoegen om uw domein te verbinden](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span><span class="sxs-lookup"><span data-stu-id="690dc-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="690dc-142">Als deze procedures niet voor u werken, moet u de procedures voor uw DNS-registratieservice vinden.</span><span class="sxs-lookup"><span data-stu-id="690dc-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>
  
<span data-ttu-id="690dc-143">Bevestig dat het maken van de TXT-record via nslookup is gelukt.</span><span class="sxs-lookup"><span data-stu-id="690dc-143">Confirm the successful creation of the TXT record via nslookup.</span></span> <span data-ttu-id="690dc-144">Volg deze syntaxis.</span><span class="sxs-lookup"><span data-stu-id="690dc-144">Follow this syntax.</span></span>
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="690dc-145">U krijgt dan de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="690dc-145">This will give you output like:</span></span>
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="690dc-146">Domein eigendom valideren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="690dc-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="690dc-147">In deze laatste stap valideert u met Microsoft 365 dat u de eigenaar bent van het algemeen geregistreerde domein.</span><span class="sxs-lookup"><span data-stu-id="690dc-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="690dc-148">Na deze stap gaat Microsoft 365 met het accepteren van verkeer naar de nieuwe domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="690dc-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="690dc-149">Voer deze opdracht uit om het maken en registreren van het domein te voltooien.</span><span class="sxs-lookup"><span data-stu-id="690dc-149">To complete the domain creation and registration process, run this command.</span></span> 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="690dc-150">Met deze opdracht worden geen uitvoer geretourneerd, zodat u kunt controleren of dit heeft gewerkt, en voer deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="690dc-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="690dc-151">Dit retourneert iets zoals dit</span><span class="sxs-lookup"><span data-stu-id="690dc-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a><span data-ttu-id="690dc-152">Zie ook</span><span class="sxs-lookup"><span data-stu-id="690dc-152">See also</span></span>

#### 

[<span data-ttu-id="690dc-153">Help voor partners</span><span class="sxs-lookup"><span data-stu-id="690dc-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)

