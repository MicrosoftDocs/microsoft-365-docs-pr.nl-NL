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
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Gebruik AllowSelfServicePurchase voor de MSCommerce PowerShell-module

De **MSCommerce** PowerShell module is nu beschikbaar op [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery) De module bevat een **Parameterwaarde PolicyID** voor **AllowSelfServicePurchase** waarmee u bepalen of gebruikers in uw organisatie selfservice-aankopen kunnen doen.

U de **MSCommerce** PowerShell-module gebruiken om:

- De standaardstatus van de parameterwaarde **AllowSelfServicePurchase** weergeven, of deze nu is ingeschakeld of uitgeschakeld
- Een lijst met toepasselijke producten weergeven en of selfservice-aankopen zijn ingeschakeld of uitgeschakeld
- De huidige instelling voor een specifiek product weergeven of wijzigen om het in te schakelen of uit te schakelen

## <a name="requirements"></a>Vereisten

Om de **MSCommerce** PowerShell-module te gebruiken, hebt u het:

- Een Windows 10-apparaat
- Beheerdersmachtiging voor het apparaat
- Rol Globale of Factureringsbeheerder voor uw tenant

## <a name="install-the-mscommerce-powershell-module"></a>Installeer de MSCommerce PowerShell-module

U installeert de **MSCommerce** PowerShell-module één keer op uw Windows 10-apparaat en importeert deze vervolgens in elke PowerShell-sessie die u start. Download de **MSCommerce** PowerShell-module in de [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Voer de volgende opdracht uit om de **MSCommerce** PowerShell-module met **PowerShellGet**te installeren:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>MsCommerce importeren in de PowerShell-sessie

Nadat u de module op uw Windows 10-apparaat hebt geïnstalleerd, importeert u deze in elke PowerShell-sessie die u start. Voer de volgende opdracht uit om het in een PowerShell-sessie te importeren:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Maak verbinding met MSCommerce met uw referenties

Voer de volgende opdracht uit om verbinding te maken met de PowerShell-module met uw referenties.

```powershell
Connect-MSCommerce
```

Met deze opdracht wordt de huidige PowerShell-sessie verbonden met een Azure Active Directory-tenant. De opdracht vraagt u om een gebruikersnaam en wachtwoord voor de tenant waarmee u verbinding wilt maken. Als multi-factor authenticatie is ingeschakeld voor uw referenties, gebruikt u de interactieve optie om in te loggen.

## <a name="view-details-for-allowselfservicepurchase"></a>Details weergeven voor AllowSelfServicePurchase

Voer de volgende opdracht uit om een beschrijving van de parameter **Value AllowSelfServicePurchase** en de standaardstatus op basis van uw organisatie weer te geven:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Bekijk een lijst met selfservice-aankoopproducten en hun status

Voer de volgende opdracht uit om een lijst met alle beschikbare selfservice-aankoopproducten en de status van elk te bekijken:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

In de volgende tabel worden de beschikbare producten en hun **ProductId weergegeven.**

| Product | Productid |
|-----------------------------|--------------|
| Power Apps per gebruiker | CFQ7TTC0KP0P |
| Power Automatiseer per gebruiker | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>De status van AllowSelfServicePurchase weergeven of instellen

Nadat u de lijst met producten hebt weergegeven die beschikbaar zijn voor selfservice-aankopen, u de instelling voor een specifiek product bekijken of wijzigen.

Voer de volgende opdracht uit om de beleidsinstelling voor een specifiek product te krijgen:

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

In het volgende voorbeeld u de **MSCommerce-module** importeren, zich aanmelden met uw account, de **ProductId** for Power Automate ophalen en **vervolgens AllowSelfServicePurchase** voor dat product uitschakelen.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Problemen oplossen

**Probleem**

U ziet het volgende foutbericht:

> HandleError : Kan het beleid niet ophalen met PolicyId 'AllowSelfServicePurchase', ErrorMessage - De onderliggende verbinding is gesloten: er is een onverwachte fout opgetreden bij een verzenden.

Dit kan te wijten zijn aan een oudere versie van Transport Layer Security (TLS). Om deze service aan te sluiten, moet u TLS 1.2 of hoger gebruiken

**Oplossing**

Upgrade naar TLS 1.2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
