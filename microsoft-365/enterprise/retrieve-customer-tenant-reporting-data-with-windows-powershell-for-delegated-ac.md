---
title: Klantten tenantrapportagegegevens ophalen met Windows PowerShell voor DAP-partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Overzicht: Gebruik externe Windows PowerShell voor Microsoft Exchange Online om rapporten op te halen van afzonderlijke klantten tenants.'
ms.openlocfilehash: 8a244e1178e64d27d5e0f061d094dccd39bb8275
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290073"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Rapportagegegevens van klantten tenants ophalen met Windows PowerShell voor DAP-partners (Gedelegeerde toegangsmachtigingen)

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Gebruik externe Windows PowerShell voor Microsoft Exchange Online om rapporten op te halen bij afzonderlijke klantten tenants.

Syndication- en Cloud Solution Provider (CSP)-partners hebben rechtstreeks via externe Windows PowerShell voor Exchange Online PowerShell toegang tot de gegevens die klant tenantrapporten maken. Op deze manier kunnen partners de rapportagegegevens verzamelen en opslaan en vervolgens andere bewerkingen uitvoeren. Nadat u een externe verbinding hebt geopend, is het ophalen van rapportagegegevens over een klanthuur identiek aan het uitvoeren van een cmdlet tegen een klanthuur.

In dit artikel gebruikt u externe Windows PowerShell voor Exchange Online verbinding te maken met één klant tenancy en een rapport op te halen. Standaard biedt Windows PowerShell geen ondersteuning voor het aggregeren van rapportagegegevens van meerdere klantentenancies. De rapporten die u met deze procedure op haalt, zijn alleen voor  _de GedelegeerdeOrg_ met wie u verbinding maakt.

## <a name="before-you-begin"></a>Voordat u begint

- U moet verbinding maken met uw Exchange Online tenant met behulp van externe Windows PowerShell. Zie voor instructies Verbinding maken tenants Exchange Online met externe Windows PowerShell [voor DAP-partners (Gedelegeerde toegangsmachtigingen)](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="run-the-get-stalemailboxreport-sample"></a>Het voorbeeld Get-StaleMailboxReport uitvoeren

Nadat u een externe sessie voor Exchange Online hebt geopend, kunt u deze opdracht uitvoeren om het **Get-StaleMailboxReport** op te halen voor het datumbereik 03-25-2015 tot en met 31-03-2015.

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Er zijn veel andere rapportage-cmdlets beschikbaar voor Exchange Online, Lync Online en SharePoint Online, evenals andere voor het traceren van berichten die u kunt gebruiken. Zie de onderwerpen in de volgende sectie voor meer informatie over de beschikbare rapportage-cmdlets en de Office 365 Reporting web service.

## <a name="see-also"></a>Zie ook

[Office 365 Rapportagewebservice](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Cmdlets rapporteren in Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)

[Help voor partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)
