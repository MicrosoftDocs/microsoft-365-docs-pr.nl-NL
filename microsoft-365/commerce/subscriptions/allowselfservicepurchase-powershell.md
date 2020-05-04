---
title: AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module
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
ms.custom: ''
search.appverid:
- MET150
description: Meer informatie over het gebruik van de OptieSelfServicePurchase PowerShell-cmdlet om selfservice-aankopen in- of uit te schakelen.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6c0bcec70eab4266674ca2a22f1b2054807a26e8
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011673"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="c08a4-103">AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="c08a4-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="c08a4-104">De **MSCommerce** PowerShell-module is nu beschikbaar op [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="c08a4-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="c08a4-105">De module bevat een **PolicyID-parameterwaarde** voor **AllowSelfServicePurchase** waarmee u bepalen of gebruikers in uw organisatie selfservice-aankopen kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="c08a4-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="c08a4-106">U de **MSCommerce** PowerShell-module gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="c08a4-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="c08a4-107">De standaardstatus van de **parameterwaarde AllowSelfServicePurchase** weergeven , ongeacht of deze is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="c08a4-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="c08a4-108">Bekijk een lijst met toepasselijke producten en of selfservice-aankoop is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="c08a4-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="c08a4-109">De huidige instelling voor een specifiek product weergeven of wijzigen om het in te schakelen of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="c08a4-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="c08a4-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="c08a4-110">Requirements</span></span>

<span data-ttu-id="c08a4-111">Als u de **MSCommerce** PowerShell-module wilt gebruiken, hebt u het:</span><span class="sxs-lookup"><span data-stu-id="c08a4-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="c08a4-112">Een Windows 10-apparaat</span><span class="sxs-lookup"><span data-stu-id="c08a4-112">A Windows 10 device</span></span>
- <span data-ttu-id="c08a4-113">Beheerdersmachtiging voor het apparaat</span><span class="sxs-lookup"><span data-stu-id="c08a4-113">Administrator permission for the device</span></span>
- <span data-ttu-id="c08a4-114">De rol Globale of factureringsbeheerder voor uw tenant</span><span class="sxs-lookup"><span data-stu-id="c08a4-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="c08a4-115">De MSCommerce PowerShell-module installeren</span><span class="sxs-lookup"><span data-stu-id="c08a4-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="c08a4-116">U installeert de **MSCommerce** PowerShell-module één keer op uw Windows 10-apparaat en importeert deze vervolgens in elke PowerShell-sessie die u start.</span><span class="sxs-lookup"><span data-stu-id="c08a4-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="c08a4-117">Download de **MSCommerce** PowerShell-module in de [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="c08a4-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="c08a4-118">Voer de volgende opdracht uit om de **MSCommerce** PowerShell-module met **PowerShellGet**te installeren:</span><span class="sxs-lookup"><span data-stu-id="c08a4-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="c08a4-119">MSCommerce importeren in de PowerShell-sessie</span><span class="sxs-lookup"><span data-stu-id="c08a4-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="c08a4-120">Nadat u de module op uw Windows 10-apparaat hebt geïnstalleerd, importeert u deze in elke PowerShell-sessie die u start.</span><span class="sxs-lookup"><span data-stu-id="c08a4-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="c08a4-121">Voer de volgende opdracht uit om deze in een PowerShell-sessie te importeren:</span><span class="sxs-lookup"><span data-stu-id="c08a4-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="c08a4-122">Verbinding maken met MSCommerce met uw referenties</span><span class="sxs-lookup"><span data-stu-id="c08a4-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="c08a4-123">Voer de volgende opdracht uit om verbinding te maken met de PowerShell-module met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="c08a4-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="c08a4-124">Met deze opdracht wordt de huidige PowerShell-sessie verbonden met een Azure Active Directory-tenant.</span><span class="sxs-lookup"><span data-stu-id="c08a4-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="c08a4-125">De opdracht vraagt u om een gebruikersnaam en wachtwoord voor de tenant waarmee u verbinding wilt maken.</span><span class="sxs-lookup"><span data-stu-id="c08a4-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="c08a4-126">Als meervoudige verificatie is ingeschakeld voor uw referenties, gebruikt u de interactieve optie om u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c08a4-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="c08a4-127">Details weergeven voor AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="c08a4-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="c08a4-128">Als u een beschrijving wilt weergeven van de **parameterwaarde AllowSelfServicePurchase** en de standaardstatus op basis van uw organisatie, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="c08a4-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="c08a4-129">Bekijk een lijst met selfservice-aankoopproducten en hun status</span><span class="sxs-lookup"><span data-stu-id="c08a4-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="c08a4-130">Voer de volgende opdracht uit om een lijst met alle beschikbare selfservice-aankoopproducten en de status van elk van deze producten weer te geven:</span><span class="sxs-lookup"><span data-stu-id="c08a4-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="c08a4-131">In de volgende tabel worden de beschikbare producten en hun **productid weergegeven.**</span><span class="sxs-lookup"><span data-stu-id="c08a4-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="c08a4-132">Product</span><span class="sxs-lookup"><span data-stu-id="c08a4-132">Product</span></span> | <span data-ttu-id="c08a4-133">Productid</span><span class="sxs-lookup"><span data-stu-id="c08a4-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="c08a4-134">Power Apps per gebruiker</span><span class="sxs-lookup"><span data-stu-id="c08a4-134">Power Apps per user</span></span> | <span data-ttu-id="c08a4-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="c08a4-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="c08a4-136">Power automatiseren per gebruiker</span><span class="sxs-lookup"><span data-stu-id="c08a4-136">Power Automate per user</span></span> | <span data-ttu-id="c08a4-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="c08a4-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="c08a4-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="c08a4-138">Power BI Pro</span></span> | <span data-ttu-id="c08a4-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="c08a4-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="c08a4-140">De status voor AllowSelfServicePurchase weergeven of instellen</span><span class="sxs-lookup"><span data-stu-id="c08a4-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="c08a4-141">Nadat u de lijst met producten hebt bekeken die beschikbaar zijn voor selfservice-aankoop, u de instelling voor een specifiek product bekijken of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c08a4-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="c08a4-142">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product op te halen:</span><span class="sxs-lookup"><span data-stu-id="c08a4-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="c08a4-143">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="c08a4-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="c08a4-144">Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="c08a4-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="c08a4-145">Voorbeeldscript om AllowSelfServicePurchase uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="c08a4-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="c08a4-146">In het volgende voorbeeld u de **MSCommerce-module** importeren, inloggen met uw account, de **ProductId** voor Power Automatiseren en vervolgens **AllowSelfServicePurchase** uitschakelen voor dat product.</span><span class="sxs-lookup"><span data-stu-id="c08a4-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="c08a4-147">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="c08a4-147">Troubleshooting</span></span>

<span data-ttu-id="c08a4-148">**Probleem**</span><span class="sxs-lookup"><span data-stu-id="c08a4-148">**Problem**</span></span>

<span data-ttu-id="c08a4-149">U ziet het volgende foutbericht:</span><span class="sxs-lookup"><span data-stu-id="c08a4-149">You see the following error message:</span></span>

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

<span data-ttu-id="c08a4-150">Dit kan te wijten zijn aan een oudere versie van Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="c08a4-150">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="c08a4-151">Om deze service aan te sluiten moet u TLS 1.2 of meer gebruiken</span><span class="sxs-lookup"><span data-stu-id="c08a4-151">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="c08a4-152">**Oplossing**</span><span class="sxs-lookup"><span data-stu-id="c08a4-152">**Solution**</span></span>

<span data-ttu-id="c08a4-153">Upgrade naar TLS 1.2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="c08a4-153">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
