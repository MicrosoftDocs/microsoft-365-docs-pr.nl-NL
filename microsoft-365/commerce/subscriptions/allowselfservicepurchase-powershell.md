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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Meer informatie over het gebruik van de Cmdlet AllowSelfServicePurchase PowerShell om selfserviceaankoop in of uit te schakelen.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9fb5593855f9523198a3d70548e444a831e82c80
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918240"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="adb94-103">AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="adb94-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="adb94-104">De **MSCommerce** PowerShell-module is nu beschikbaar in [powershellgalerie.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="adb94-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="adb94-105">De module bevat een **parameterwaarde PolicyID** voor **AllowSelfServicePurchase** waarmee u kunt bepalen of gebruikers in uw organisatie selfserviceaankopen kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="adb94-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="adb94-106">U kunt de **MSCommerce** PowerShell-module gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="adb94-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="adb94-107">De standaardtoestand van de **parameterwaarde AllowSelfServicePurchase** weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="adb94-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="adb94-108">Een lijst met toepasselijke producten weergeven en controleren of selfserviceaankoop is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="adb94-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="adb94-109">De huidige instelling voor een specifiek product weergeven of wijzigen om het in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="adb94-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="adb94-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="adb94-110">Requirements</span></span>

<span data-ttu-id="adb94-111">Als u de **MSCommerce** PowerShell-module wilt gebruiken, hebt u het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="adb94-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="adb94-112">Een Windows 10-apparaat</span><span class="sxs-lookup"><span data-stu-id="adb94-112">A Windows 10 device</span></span>
- <span data-ttu-id="adb94-113">Beheerdersmachtiging voor het apparaat</span><span class="sxs-lookup"><span data-stu-id="adb94-113">Administrator permission for the device</span></span>
- <span data-ttu-id="adb94-114">Globale rol of factureringsbeheerder voor uw tenant</span><span class="sxs-lookup"><span data-stu-id="adb94-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="adb94-115">De MSCommerce PowerShell-module installeren</span><span class="sxs-lookup"><span data-stu-id="adb94-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="adb94-116">U installeert de **MSCommerce** PowerShell-module eenmaal op uw Windows 10-apparaat en importeert deze vervolgens in elke PowerShell-sessie die u start.</span><span class="sxs-lookup"><span data-stu-id="adb94-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="adb94-117">Download de **MSCommerce** PowerShell-module in de [PowerShell-galerie.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="adb94-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="adb94-118">Voer de volgende opdracht uit om de **MSCommerce** PowerShell-module te installeren met **PowerShellGet:**</span><span class="sxs-lookup"><span data-stu-id="adb94-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="adb94-119">MSCommerce importeren in de PowerShell-sessie</span><span class="sxs-lookup"><span data-stu-id="adb94-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="adb94-120">Nadat u de module op uw Windows 10-apparaat hebt geïnstalleerd, importeert u de module in elke PowerShell-sessie die u start.</span><span class="sxs-lookup"><span data-stu-id="adb94-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="adb94-121">Voer de volgende opdracht uit om deze te importeren in een PowerShell-sessie:</span><span class="sxs-lookup"><span data-stu-id="adb94-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="adb94-122">Verbinding maken met MSCommerce met uw referenties</span><span class="sxs-lookup"><span data-stu-id="adb94-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="adb94-123">Voer de volgende opdracht uit om verbinding te maken met de PowerShell-module met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="adb94-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="adb94-124">Met deze opdracht wordt de huidige PowerShell-sessie verbonden met een Azure Active Directory-tenant.</span><span class="sxs-lookup"><span data-stu-id="adb94-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="adb94-125">De opdracht vraagt u om een gebruikersnaam en wachtwoord voor de tenant met wie u verbinding wilt maken.</span><span class="sxs-lookup"><span data-stu-id="adb94-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="adb94-126">Als meervoudige verificatie is ingeschakeld voor uw referenties, gebruikt u de interactieve optie om u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="adb94-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="adb94-127">Details weergeven voor AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="adb94-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="adb94-128">Voer de volgende opdracht uit als u een beschrijving wilt weergeven van de **parameterwaarde AllowSelfServicePurchase** en de standaardstatus op basis van uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="adb94-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="adb94-129">Een lijst met selfservice-aankoopproducten en hun status weergeven</span><span class="sxs-lookup"><span data-stu-id="adb94-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="adb94-130">Voer de volgende opdracht uit als u een lijst wilt weergeven met alle beschikbare selfservice-aankoopproducten en de status van elk product:</span><span class="sxs-lookup"><span data-stu-id="adb94-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="adb94-131">In de volgende tabel worden de beschikbare producten en hun **ProductId vermeld.**</span><span class="sxs-lookup"><span data-stu-id="adb94-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="adb94-132">Product</span><span class="sxs-lookup"><span data-stu-id="adb94-132">Product</span></span> | <span data-ttu-id="adb94-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="adb94-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="adb94-134">Power Apps per gebruiker</span><span class="sxs-lookup"><span data-stu-id="adb94-134">Power Apps per user</span></span> | <span data-ttu-id="adb94-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="adb94-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="adb94-136">Power Automate per gebruiker</span><span class="sxs-lookup"><span data-stu-id="adb94-136">Power Automate per user</span></span> | <span data-ttu-id="adb94-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="adb94-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="adb94-138">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="adb94-138">Power Automate RPA</span></span> | <span data-ttu-id="adb94-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="adb94-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="adb94-140">Power BI Premium (zelfstandig)</span><span class="sxs-lookup"><span data-stu-id="adb94-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="adb94-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="adb94-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="adb94-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="adb94-142">Power BI Pro</span></span> | <span data-ttu-id="adb94-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="adb94-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="adb94-144">Projectplan 1</span><span class="sxs-lookup"><span data-stu-id="adb94-144">Project Plan 1</span></span> | <span data-ttu-id="adb94-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="adb94-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="adb94-146">Projectplan 3</span><span class="sxs-lookup"><span data-stu-id="adb94-146">Project Plan 3</span></span> | <span data-ttu-id="adb94-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="adb94-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="adb94-148">Visio-abonnement 1</span><span class="sxs-lookup"><span data-stu-id="adb94-148">Visio Plan 1</span></span> | <span data-ttu-id="adb94-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="adb94-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="adb94-150">Visio Plan 2</span><span class="sxs-lookup"><span data-stu-id="adb94-150">Visio Plan 2</span></span> | <span data-ttu-id="adb94-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="adb94-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="adb94-152">De status van AllowSelfServicePurchase weergeven of instellen</span><span class="sxs-lookup"><span data-stu-id="adb94-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="adb94-153">Nadat u de lijst met producten hebt weergegeven die beschikbaar zijn voor selfserviceaankopen, kunt u de instelling voor een bepaald product bekijken of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="adb94-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="adb94-154">Voer de volgende opdracht uit om de beleidsinstelling voor een bepaald product op te halen:</span><span class="sxs-lookup"><span data-stu-id="adb94-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="adb94-155">Voer de volgende opdracht uit als u de beleidsinstelling voor een bepaald product wilt inschakelen:</span><span class="sxs-lookup"><span data-stu-id="adb94-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="adb94-156">Voer de volgende opdracht uit om de beleidsinstelling voor een bepaald product uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="adb94-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="adb94-157">Voorbeeldscript om AllowSelfServicePurchase uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="adb94-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="adb94-158">In het volgende voorbeeld ziet u hoe u de **MSCommerce-module** importeert, zich met uw account kunt aanmelden, **de ProductId** voor Power Automate kunt krijgen en **vervolgens AllowSelfServicePurchase** voor dat product kunt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="adb94-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="adb94-159">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="adb94-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="adb94-160">Probleem</span><span class="sxs-lookup"><span data-stu-id="adb94-160">Problem</span></span>

<span data-ttu-id="adb94-161">U ziet het volgende foutbericht:</span><span class="sxs-lookup"><span data-stu-id="adb94-161">You see the following error message:</span></span>

> <span data-ttu-id="adb94-162">HandleError: Kan beleid niet ophalen met PolicyId 'AllowSelfServicePurchase', ErrorMessage - De onderliggende verbinding is gesloten: er is een onverwachte fout opgetreden bij een verzenden.</span><span class="sxs-lookup"><span data-stu-id="adb94-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="adb94-163">Dit kan het gevolg zijn van een oudere versie van Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="adb94-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="adb94-164">Als u deze service wilt verbinden, moet u TLS 1.2 of hoger gebruiken</span><span class="sxs-lookup"><span data-stu-id="adb94-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="adb94-165">Oplossing</span><span class="sxs-lookup"><span data-stu-id="adb94-165">Solution</span></span>

<span data-ttu-id="adb94-166">Upgrade naar TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="adb94-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->