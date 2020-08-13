---
title: AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over het gebruik van de AllowSelfServicePurchase PowerShell-cmdlet voor het in-of uitschakelen van selfservice aankopen.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653711"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="5febb-103">AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="5febb-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="5febb-104">De **MSCommerce** PowerShell-module is nu beschikbaar in de [PowerShell-galerie](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="5febb-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="5febb-105">De module bevat een **PolicyID** -parameterwaarde voor **AllowSelfServicePurchase** waarmee u kunt bepalen of gebruikers in uw organisatie selfservice aankopen kunnen verrichten.</span><span class="sxs-lookup"><span data-stu-id="5febb-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="5febb-106">U kunt de **MSCommerce** PowerShell-module gebruiken voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="5febb-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="5febb-107">De standaardstatus van de parameterwaarde van **AllowSelfServicePurchase** weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="5febb-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="5febb-108">Een lijst met beschikbare producten weergeven en of selfservice aankoop is in-of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="5febb-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="5febb-109">De huidige instelling voor een specifiek product weergeven of wijzigen om dit in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="5febb-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="5febb-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="5febb-110">Requirements</span></span>

<span data-ttu-id="5febb-111">Als u de **MSCommerce** PowerShell-module wilt gebruiken, hebt u het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="5febb-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="5febb-112">Een Windows 10-apparaat</span><span class="sxs-lookup"><span data-stu-id="5febb-112">A Windows 10 device</span></span>
- <span data-ttu-id="5febb-113">Beheerdersmachtiging voor het apparaat</span><span class="sxs-lookup"><span data-stu-id="5febb-113">Administrator permission for the device</span></span>
- <span data-ttu-id="5febb-114">Globale beheerder of facturerings beheerdersrol voor uw Tenant</span><span class="sxs-lookup"><span data-stu-id="5febb-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="5febb-115">De MSCommerce PowerShell-module installeren</span><span class="sxs-lookup"><span data-stu-id="5febb-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="5febb-116">U installeert de **MSCommerce** PowerShell-module op uw Windows 10-apparaat eenmaal en importeert u deze in elke PowerShell-sessie die u start.</span><span class="sxs-lookup"><span data-stu-id="5febb-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="5febb-117">Download de **MSCommerce** PowerShell-module vanuit de [PowerShell-galerie](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="5febb-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="5febb-118">Voer de volgende opdracht uit om de **MSCommerce** PowerShell-module te installeren met **PowerShellGet**:</span><span class="sxs-lookup"><span data-stu-id="5febb-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="5febb-119">MSCommerce in de PowerShell-sessie importeren</span><span class="sxs-lookup"><span data-stu-id="5febb-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="5febb-120">Wanneer u de module hebt geïnstalleerd op uw Windows 10-apparaat, importeert u deze in elke PowerShell-sessie die u start.</span><span class="sxs-lookup"><span data-stu-id="5febb-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="5febb-121">Voer de volgende opdracht uit als u het bestand wilt importeren in een PowerShell-sessie:</span><span class="sxs-lookup"><span data-stu-id="5febb-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="5febb-122">Maak verbinding met MSCommerce met uw referenties</span><span class="sxs-lookup"><span data-stu-id="5febb-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="5febb-123">Voer de volgende opdracht uit om verbinding te maken met de PowerShell-module met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="5febb-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="5febb-124">Met deze opdracht verbindt u de huidige PowerShell-sessie met een Azure Active Directory-Tenant.</span><span class="sxs-lookup"><span data-stu-id="5febb-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="5febb-125">Met de opdracht wordt u gevraagd om een gebruikersnaam en wachtwoord voor de Tenant waarmee u verbinding wilt maken.</span><span class="sxs-lookup"><span data-stu-id="5febb-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="5febb-126">Als multi-factor Authentication is ingeschakeld voor uw referenties, gebruikt u de interactieve optie om u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5febb-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="5febb-127">Details voor AllowSelfServicePurchase weergeven</span><span class="sxs-lookup"><span data-stu-id="5febb-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="5febb-128">Voer de volgende opdracht uit als u een beschrijving van de waarde van de **AllowSelfServicePurchase** -parameter en de standaardstatus op basis van uw organisatie wilt bekijken:</span><span class="sxs-lookup"><span data-stu-id="5febb-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="5febb-129">Een lijst met producten en hun status voor selfservice kopen weergeven</span><span class="sxs-lookup"><span data-stu-id="5febb-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="5febb-130">Voer de volgende opdracht uit om een lijst met alle beschikbare producten voor selfservice aankopen en de status ervan weer te geven:</span><span class="sxs-lookup"><span data-stu-id="5febb-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="5febb-131">De volgende tabel bevat een overzicht van de beschikbare producten en hun **product**-id.</span><span class="sxs-lookup"><span data-stu-id="5febb-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="5febb-132">Product</span><span class="sxs-lookup"><span data-stu-id="5febb-132">Product</span></span> | <span data-ttu-id="5febb-133">Product id</span><span class="sxs-lookup"><span data-stu-id="5febb-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="5febb-134">Power apps per gebruiker</span><span class="sxs-lookup"><span data-stu-id="5febb-134">Power Apps per user</span></span> | <span data-ttu-id="5febb-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="5febb-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="5febb-136">Automatisch automatiseren per gebruiker</span><span class="sxs-lookup"><span data-stu-id="5febb-136">Power Automate per user</span></span> | <span data-ttu-id="5febb-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="5febb-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="5febb-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="5febb-138">Power BI Pro</span></span> | <span data-ttu-id="5febb-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="5febb-139">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="5febb-140">Project abonnement 1</span><span class="sxs-lookup"><span data-stu-id="5febb-140">Project Plan 1</span></span> | <span data-ttu-id="5febb-141">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="5febb-141">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="5febb-142">Project abonnement 3</span><span class="sxs-lookup"><span data-stu-id="5febb-142">Project Plan 3</span></span> | <span data-ttu-id="5febb-143">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="5febb-143">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="5febb-144">Visio abonnement 1</span><span class="sxs-lookup"><span data-stu-id="5febb-144">Visio Plan 1</span></span> | <span data-ttu-id="5febb-145">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="5febb-145">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="5febb-146">Visio abonnement 2</span><span class="sxs-lookup"><span data-stu-id="5febb-146">Visio Plan 2</span></span> | <span data-ttu-id="5febb-147">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="5febb-147">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="5febb-148">De status voor AllowSelfServicePurchase weergeven of instellen</span><span class="sxs-lookup"><span data-stu-id="5febb-148">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="5febb-149">Nadat u de lijst met beschikbare producten voor selfservice aankoop hebt weergegeven, kunt u de instelling voor een specifiek product weergeven of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5febb-149">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="5febb-150">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product weer te geven:</span><span class="sxs-lookup"><span data-stu-id="5febb-150">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="5febb-151">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="5febb-151">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="5febb-152">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="5febb-152">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="5febb-153">Voorbeeld van script om AllowSelfServicePurchase uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="5febb-153">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="5febb-154">In het volgende voorbeeld wordt u begeleid bij het importeren van de **MSCommerce** -module, meldt u zich aan met uw account, haalt u de **product** -id voor Power Automatiseer en schakelt u **AllowSelfServicePurchase** uit voor dat product.</span><span class="sxs-lookup"><span data-stu-id="5febb-154">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="5febb-155">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="5febb-155">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="5febb-156">Doet</span><span class="sxs-lookup"><span data-stu-id="5febb-156">Problem</span></span>

<span data-ttu-id="5febb-157">Het volgende foutbericht wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5febb-157">You see the following error message:</span></span>

> <span data-ttu-id="5febb-158">HandleError: kan geen beleid ophalen met PolicyId ' AllowSelfServicePurchase ', ErrorMessage-de onderliggende verbinding is gesloten: er is een onverwachte fout opgetreden bij het verzenden.</span><span class="sxs-lookup"><span data-stu-id="5febb-158">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="5febb-159">Dit kan zijn vanwege een oudere versie van TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="5febb-159">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="5febb-160">U moet TLS 1,2 of hoger gebruiken om verbinding te maken met deze service.</span><span class="sxs-lookup"><span data-stu-id="5febb-160">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="5febb-161">Oplossing</span><span class="sxs-lookup"><span data-stu-id="5febb-161">Solution</span></span>

<span data-ttu-id="5febb-162">Een upgrade uitvoeren naar TLS 1,2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="5febb-162">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
