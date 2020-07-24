---
title: Gebruik AllowSelfServicePurchase voor de MSCommerce PowerShell-module
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over het gebruik van de PowerShell-cmdlet allowSelfServicePurchase om zelfbedieningsaankoop in of uit te schakelen.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b35b62a97f8dc269be5db232e163391a8ce50658
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391540"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="d95a4-103">Gebruik AllowSelfServicePurchase voor de MSCommerce PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="d95a4-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="d95a4-104">De **MSCommerce** PowerShell module is nu beschikbaar op [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="d95a4-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="d95a4-105">De module bevat een **Parameterwaarde PolicyID** voor **AllowSelfServicePurchase** waarmee u bepalen of gebruikers in uw organisatie selfservice-aankopen kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="d95a4-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="d95a4-106">U de **MSCommerce** PowerShell-module gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="d95a4-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="d95a4-107">De standaardstatus van de parameterwaarde **AllowSelfServicePurchase** weergeven, of deze nu is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="d95a4-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="d95a4-108">Een lijst met toepasselijke producten weergeven en of selfservice-aankopen zijn ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="d95a4-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="d95a4-109">De huidige instelling voor een specifiek product weergeven of wijzigen om het in te schakelen of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="d95a4-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="d95a4-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="d95a4-110">Requirements</span></span>

<span data-ttu-id="d95a4-111">Om de **MSCommerce** PowerShell-module te gebruiken, hebt u het:</span><span class="sxs-lookup"><span data-stu-id="d95a4-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="d95a4-112">Een Windows 10-apparaat</span><span class="sxs-lookup"><span data-stu-id="d95a4-112">A Windows 10 device</span></span>
- <span data-ttu-id="d95a4-113">Beheerdersmachtiging voor het apparaat</span><span class="sxs-lookup"><span data-stu-id="d95a4-113">Administrator permission for the device</span></span>
- <span data-ttu-id="d95a4-114">Rol Globale of Factureringsbeheerder voor uw tenant</span><span class="sxs-lookup"><span data-stu-id="d95a4-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="d95a4-115">Installeer de MSCommerce PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="d95a4-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="d95a4-116">U installeert de **MSCommerce** PowerShell-module één keer op uw Windows 10-apparaat en importeert deze vervolgens in elke PowerShell-sessie die u start.</span><span class="sxs-lookup"><span data-stu-id="d95a4-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="d95a4-117">Download de **MSCommerce** PowerShell-module in de [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="d95a4-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="d95a4-118">Voer de volgende opdracht uit om de **MSCommerce** PowerShell-module met **PowerShellGet**te installeren:</span><span class="sxs-lookup"><span data-stu-id="d95a4-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="d95a4-119">MsCommerce importeren in de PowerShell-sessie</span><span class="sxs-lookup"><span data-stu-id="d95a4-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="d95a4-120">Nadat u de module op uw Windows 10-apparaat hebt geïnstalleerd, importeert u deze in elke PowerShell-sessie die u start.</span><span class="sxs-lookup"><span data-stu-id="d95a4-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="d95a4-121">Voer de volgende opdracht uit om het in een PowerShell-sessie te importeren:</span><span class="sxs-lookup"><span data-stu-id="d95a4-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="d95a4-122">Maak verbinding met MSCommerce met uw referenties</span><span class="sxs-lookup"><span data-stu-id="d95a4-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="d95a4-123">Voer de volgende opdracht uit om verbinding te maken met de PowerShell-module met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="d95a4-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="d95a4-124">Met deze opdracht wordt de huidige PowerShell-sessie verbonden met een Azure Active Directory-tenant.</span><span class="sxs-lookup"><span data-stu-id="d95a4-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="d95a4-125">De opdracht vraagt u om een gebruikersnaam en wachtwoord voor de tenant waarmee u verbinding wilt maken.</span><span class="sxs-lookup"><span data-stu-id="d95a4-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="d95a4-126">Als multi-factor authenticatie is ingeschakeld voor uw referenties, gebruikt u de interactieve optie om in te loggen.</span><span class="sxs-lookup"><span data-stu-id="d95a4-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="d95a4-127">Details weergeven voor AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="d95a4-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="d95a4-128">Voer de volgende opdracht uit om een beschrijving van de parameter **Value AllowSelfServicePurchase** en de standaardstatus op basis van uw organisatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="d95a4-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="d95a4-129">Bekijk een lijst met selfservice-aankoopproducten en hun status</span><span class="sxs-lookup"><span data-stu-id="d95a4-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="d95a4-130">Voer de volgende opdracht uit om een lijst met alle beschikbare selfservice-aankoopproducten en de status van elk te bekijken:</span><span class="sxs-lookup"><span data-stu-id="d95a4-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="d95a4-131">In de volgende tabel worden de beschikbare producten en hun **ProductId weergegeven.**</span><span class="sxs-lookup"><span data-stu-id="d95a4-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="d95a4-132">Product</span><span class="sxs-lookup"><span data-stu-id="d95a4-132">Product</span></span> | <span data-ttu-id="d95a4-133">Productid</span><span class="sxs-lookup"><span data-stu-id="d95a4-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="d95a4-134">Power Apps per gebruiker</span><span class="sxs-lookup"><span data-stu-id="d95a4-134">Power Apps per user</span></span> | <span data-ttu-id="d95a4-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="d95a4-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="d95a4-136">Power Automatiseer per gebruiker</span><span class="sxs-lookup"><span data-stu-id="d95a4-136">Power Automate per user</span></span> | <span data-ttu-id="d95a4-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="d95a4-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="d95a4-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="d95a4-138">Power BI Pro</span></span> | <span data-ttu-id="d95a4-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="d95a4-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="d95a4-140">De status van AllowSelfServicePurchase weergeven of instellen</span><span class="sxs-lookup"><span data-stu-id="d95a4-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="d95a4-141">Nadat u de lijst met producten hebt weergegeven die beschikbaar zijn voor selfservice-aankopen, u de instelling voor een specifiek product bekijken of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d95a4-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="d95a4-142">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product te krijgen:</span><span class="sxs-lookup"><span data-stu-id="d95a4-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="d95a4-143">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="d95a4-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="d95a4-144">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="d95a4-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="d95a4-145">Voorbeeldscript om AllowSelfServicePurchase uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="d95a4-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="d95a4-146">In het volgende voorbeeld u de **MSCommerce-module** importeren, zich aanmelden met uw account, de **ProductId** for Power Automate ophalen en **vervolgens AllowSelfServicePurchase** voor dat product uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="d95a4-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="d95a4-147">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="d95a4-147">Troubleshooting</span></span>

<span data-ttu-id="d95a4-148">**Probleem**</span><span class="sxs-lookup"><span data-stu-id="d95a4-148">**Problem**</span></span>

<span data-ttu-id="d95a4-149">U ziet het volgende foutbericht:</span><span class="sxs-lookup"><span data-stu-id="d95a4-149">You see the following error message:</span></span>

> <span data-ttu-id="d95a4-150">HandleError : Kan het beleid niet ophalen met PolicyId 'AllowSelfServicePurchase', ErrorMessage - De onderliggende verbinding is gesloten: er is een onverwachte fout opgetreden bij een verzenden.</span><span class="sxs-lookup"><span data-stu-id="d95a4-150">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="d95a4-151">Dit kan te wijten zijn aan een oudere versie van Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="d95a4-151">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="d95a4-152">Om deze service aan te sluiten, moet u TLS 1.2 of hoger gebruiken</span><span class="sxs-lookup"><span data-stu-id="d95a4-152">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="d95a4-153">**Oplossing**</span><span class="sxs-lookup"><span data-stu-id="d95a4-153">**Solution**</span></span>

<span data-ttu-id="d95a4-154">Upgrade naar TLS 1.2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="d95a4-154">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
