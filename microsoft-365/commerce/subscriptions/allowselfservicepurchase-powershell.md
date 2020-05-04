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
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module

De **MSCommerce** PowerShell-module is nu beschikbaar op [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery) De module bevat een **PolicyID-parameterwaarde** voor **AllowSelfServicePurchase** waarmee u bepalen of gebruikers in uw organisatie selfservice-aankopen kunnen doen.

U de **MSCommerce** PowerShell-module gebruiken om:

- De standaardstatus van de **parameterwaarde AllowSelfServicePurchase** weergeven , ongeacht of deze is ingeschakeld of uitgeschakeld
- Bekijk een lijst met toepasselijke producten en of selfservice-aankoop is ingeschakeld of uitgeschakeld
- De huidige instelling voor een specifiek product weergeven of wijzigen om het in te schakelen of uit te schakelen

## <a name="requirements"></a>Vereisten

Als u de **MSCommerce** PowerShell-module wilt gebruiken, hebt u het:

- Een Windows 10-apparaat
- Beheerdersmachtiging voor het apparaat
- De rol Globale of factureringsbeheerder voor uw tenant

## <a name="install-the-mscommerce-powershell-module"></a>De MSCommerce PowerShell-module installeren

U installeert de **MSCommerce** PowerShell-module één keer op uw Windows 10-apparaat en importeert deze vervolgens in elke PowerShell-sessie die u start. Download de **MSCommerce** PowerShell-module in de [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Voer de volgende opdracht uit om de **MSCommerce** PowerShell-module met **PowerShellGet**te installeren:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>MSCommerce importeren in de PowerShell-sessie

Nadat u de module op uw Windows 10-apparaat hebt geïnstalleerd, importeert u deze in elke PowerShell-sessie die u start. Voer de volgende opdracht uit om deze in een PowerShell-sessie te importeren:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Verbinding maken met MSCommerce met uw referenties

Voer de volgende opdracht uit om verbinding te maken met de PowerShell-module met uw referenties.

```powershell
Connect-MSCommerce
```

Met deze opdracht wordt de huidige PowerShell-sessie verbonden met een Azure Active Directory-tenant. De opdracht vraagt u om een gebruikersnaam en wachtwoord voor de tenant waarmee u verbinding wilt maken. Als meervoudige verificatie is ingeschakeld voor uw referenties, gebruikt u de interactieve optie om u aan te melden.

## <a name="view-details-for-allowselfservicepurchase"></a>Details weergeven voor AllowSelfServicePurchase

Als u een beschrijving wilt weergeven van de **parameterwaarde AllowSelfServicePurchase** en de standaardstatus op basis van uw organisatie, voert u de volgende opdracht uit:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Bekijk een lijst met selfservice-aankoopproducten en hun status

Voer de volgende opdracht uit om een lijst met alle beschikbare selfservice-aankoopproducten en de status van elk van deze producten weer te geven:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

In de volgende tabel worden de beschikbare producten en hun **productid weergegeven.**

| Product | Productid |
|-----------------------------|--------------|
| Power Apps per gebruiker | CFQ7TTC0KP0P |
| Power automatiseren per gebruiker | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>De status voor AllowSelfServicePurchase weergeven of instellen

Nadat u de lijst met producten hebt bekeken die beschikbaar zijn voor selfservice-aankoop, u de instelling voor een specifiek product bekijken of wijzigen.

Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product op te halen:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product in te schakelen:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product uit te schakelen:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Voorbeeldscript om AllowSelfServicePurchase uit te schakelen

In het volgende voorbeeld u de **MSCommerce-module** importeren, inloggen met uw account, de **ProductId** voor Power Automatiseren en vervolgens **AllowSelfServicePurchase** uitschakelen voor dat product.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Problemen oplossen

**Probleem**

U ziet het volgende foutbericht:

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

Dit kan te wijten zijn aan een oudere versie van Transport Layer Security (TLS). Om deze service aan te sluiten moet u TLS 1.2 of meer gebruiken

**Oplossing**

Upgrade naar TLS 1.2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
