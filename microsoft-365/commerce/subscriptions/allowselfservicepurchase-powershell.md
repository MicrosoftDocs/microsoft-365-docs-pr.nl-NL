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
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module

De **MSCommerce** PowerShell-module is nu beschikbaar in [powershellgalerie.](https://aka.ms/allowselfservicepurchase-powershell-gallery) De module bevat een **parameterwaarde PolicyID** voor **AllowSelfServicePurchase** waarmee u kunt bepalen of gebruikers in uw organisatie selfserviceaankopen kunnen doen.

U kunt de **MSCommerce** PowerShell-module gebruiken om:

- De standaardtoestand van de **parameterwaarde AllowSelfServicePurchase** weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld
- Een lijst met toepasselijke producten weergeven en controleren of selfserviceaankoop is ingeschakeld of uitgeschakeld
- De huidige instelling voor een specifiek product weergeven of wijzigen om het in of uit te schakelen

## <a name="requirements"></a>Vereisten

Als u de **MSCommerce** PowerShell-module wilt gebruiken, hebt u het volgende nodig:

- Een Windows 10-apparaat
- Beheerdersmachtiging voor het apparaat
- Globale rol of factureringsbeheerder voor uw tenant

## <a name="install-the-mscommerce-powershell-module"></a>De MSCommerce PowerShell-module installeren

U installeert de **MSCommerce** PowerShell-module eenmaal op uw Windows 10-apparaat en importeert deze vervolgens in elke PowerShell-sessie die u start. Download de **MSCommerce** PowerShell-module in de [PowerShell-galerie.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Voer de volgende opdracht uit om de **MSCommerce** PowerShell-module te installeren met **PowerShellGet:**

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>MSCommerce importeren in de PowerShell-sessie

Nadat u de module op uw Windows 10-apparaat hebt geïnstalleerd, importeert u de module in elke PowerShell-sessie die u start. Voer de volgende opdracht uit om deze te importeren in een PowerShell-sessie:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Verbinding maken met MSCommerce met uw referenties

Voer de volgende opdracht uit om verbinding te maken met de PowerShell-module met uw referenties.

```powershell
Connect-MSCommerce
```

Met deze opdracht wordt de huidige PowerShell-sessie verbonden met een Azure Active Directory-tenant. De opdracht vraagt u om een gebruikersnaam en wachtwoord voor de tenant met wie u verbinding wilt maken. Als meervoudige verificatie is ingeschakeld voor uw referenties, gebruikt u de interactieve optie om u aan te melden.

## <a name="view-details-for-allowselfservicepurchase"></a>Details weergeven voor AllowSelfServicePurchase

Voer de volgende opdracht uit als u een beschrijving wilt weergeven van de **parameterwaarde AllowSelfServicePurchase** en de standaardstatus op basis van uw organisatie:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Een lijst met selfservice-aankoopproducten en hun status weergeven

Voer de volgende opdracht uit als u een lijst wilt weergeven met alle beschikbare selfservice-aankoopproducten en de status van elk product:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

In de volgende tabel worden de beschikbare producten en hun **ProductId vermeld.**

| Product | ProductId |
|-----------------------------|--------------|
| Power Apps per gebruiker | CFQ7TTC0KP0P |
| Power Automate per gebruiker | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (zelfstandig) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Projectplan 1 | CFQ7TTC0KXND |
| Projectplan 3 | CFQ7TTC0KXNC |
| Visio-abonnement 1 | CFQ7TTC0KXN9 |
| Visio Plan 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>De status van AllowSelfServicePurchase weergeven of instellen

Nadat u de lijst met producten hebt weergegeven die beschikbaar zijn voor selfserviceaankopen, kunt u de instelling voor een bepaald product bekijken of wijzigen.

Voer de volgende opdracht uit om de beleidsinstelling voor een bepaald product op te halen:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Voer de volgende opdracht uit als u de beleidsinstelling voor een bepaald product wilt inschakelen:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Voer de volgende opdracht uit om de beleidsinstelling voor een bepaald product uit te schakelen:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Voorbeeldscript om AllowSelfServicePurchase uit te schakelen

In het volgende voorbeeld ziet u hoe u de **MSCommerce-module** importeert, zich met uw account kunt aanmelden, **de ProductId** voor Power Automate kunt krijgen en **vervolgens AllowSelfServicePurchase** voor dat product kunt uitschakelen.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Problemen oplossen

### <a name="problem"></a>Probleem

U ziet het volgende foutbericht:

> HandleError: Kan beleid niet ophalen met PolicyId 'AllowSelfServicePurchase', ErrorMessage - De onderliggende verbinding is gesloten: er is een onverwachte fout opgetreden bij een verzenden.

Dit kan het gevolg zijn van een oudere versie van Transport Layer Security (TLS). Als u deze service wilt verbinden, moet u TLS 1.2 of hoger gebruiken

### <a name="solution"></a>Oplossing

Upgrade naar TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->