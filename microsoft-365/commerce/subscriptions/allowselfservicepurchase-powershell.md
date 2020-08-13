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
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module

De **MSCommerce** PowerShell-module is nu beschikbaar in de [PowerShell-galerie](https://aka.ms/allowselfservicepurchase-powershell-gallery). De module bevat een **PolicyID** -parameterwaarde voor **AllowSelfServicePurchase** waarmee u kunt bepalen of gebruikers in uw organisatie selfservice aankopen kunnen verrichten.

U kunt de **MSCommerce** PowerShell-module gebruiken voor het volgende:

- De standaardstatus van de parameterwaarde van **AllowSelfServicePurchase** weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld
- Een lijst met beschikbare producten weergeven en of selfservice aankoop is in-of uitgeschakeld
- De huidige instelling voor een specifiek product weergeven of wijzigen om dit in of uit te schakelen

## <a name="requirements"></a>Vereisten

Als u de **MSCommerce** PowerShell-module wilt gebruiken, hebt u het volgende nodig:

- Een Windows 10-apparaat
- Beheerdersmachtiging voor het apparaat
- Globale beheerder of facturerings beheerdersrol voor uw Tenant

## <a name="install-the-mscommerce-powershell-module"></a>De MSCommerce PowerShell-module installeren

U installeert de **MSCommerce** PowerShell-module op uw Windows 10-apparaat eenmaal en importeert u deze in elke PowerShell-sessie die u start. Download de **MSCommerce** PowerShell-module vanuit de [PowerShell-galerie](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Voer de volgende opdracht uit om de **MSCommerce** PowerShell-module te installeren met **PowerShellGet**:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>MSCommerce in de PowerShell-sessie importeren

Wanneer u de module hebt geïnstalleerd op uw Windows 10-apparaat, importeert u deze in elke PowerShell-sessie die u start. Voer de volgende opdracht uit als u het bestand wilt importeren in een PowerShell-sessie:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Maak verbinding met MSCommerce met uw referenties

Voer de volgende opdracht uit om verbinding te maken met de PowerShell-module met uw referenties.

```powershell
Connect-MSCommerce
```

Met deze opdracht verbindt u de huidige PowerShell-sessie met een Azure Active Directory-Tenant. Met de opdracht wordt u gevraagd om een gebruikersnaam en wachtwoord voor de Tenant waarmee u verbinding wilt maken. Als multi-factor Authentication is ingeschakeld voor uw referenties, gebruikt u de interactieve optie om u aan te melden.

## <a name="view-details-for-allowselfservicepurchase"></a>Details voor AllowSelfServicePurchase weergeven

Voer de volgende opdracht uit als u een beschrijving van de waarde van de **AllowSelfServicePurchase** -parameter en de standaardstatus op basis van uw organisatie wilt bekijken:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Een lijst met producten en hun status voor selfservice kopen weergeven

Voer de volgende opdracht uit om een lijst met alle beschikbare producten voor selfservice aankopen en de status ervan weer te geven:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

De volgende tabel bevat een overzicht van de beschikbare producten en hun **product**-id.

| Product | Product id |
|-----------------------------|--------------|
| Power apps per gebruiker | CFQ7TTC0KP0P |
| Automatisch automatiseren per gebruiker | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| Project abonnement 1 | CFQ7TTC0KXND |
| Project abonnement 3 | CFQ7TTC0KXNC |
| Visio abonnement 1 | CFQ7TTC0KXN9 |
| Visio abonnement 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>De status voor AllowSelfServicePurchase weergeven of instellen

Nadat u de lijst met beschikbare producten voor selfservice aankoop hebt weergegeven, kunt u de instelling voor een specifiek product weergeven of wijzigen.

Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product weer te geven:

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

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Voorbeeld van script om AllowSelfServicePurchase uit te schakelen

In het volgende voorbeeld wordt u begeleid bij het importeren van de **MSCommerce** -module, meldt u zich aan met uw account, haalt u de **product** -id voor Power Automatiseer en schakelt u **AllowSelfServicePurchase** uit voor dat product.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Problemen oplossen

### <a name="problem"></a>Doet

Het volgende foutbericht wordt weergegeven:

> HandleError: kan geen beleid ophalen met PolicyId ' AllowSelfServicePurchase ', ErrorMessage-de onderliggende verbinding is gesloten: er is een onverwachte fout opgetreden bij het verzenden.

Dit kan zijn vanwege een oudere versie van TLS (Transport Layer Security). U moet TLS 1,2 of hoger gebruiken om verbinding te maken met deze service.

### <a name="solution"></a>Oplossing

Een upgrade uitvoeren naar TLS 1,2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
