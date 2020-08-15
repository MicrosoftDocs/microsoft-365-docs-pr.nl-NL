---
title: Gegevens van de Tenant rapporten van klanten ophalen met Windows PowerShell voor DAP partners
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
description: 'Overzicht: gebruik externe Windows PowerShell voor Microsoft Exchange Online om rapporten van afzonderlijke tenants van klanten op te halen.'
ms.openlocfilehash: 24d56fffa60232c4ea39f4fe7769131cab23be2f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689013"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Gegevens van de Tenant met informatie van klanten ophalen met Windows PowerShell voor partners met een gedelegeerde toegangsrechten (DAP)

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Gebruik externe Windows PowerShell voor Microsoft Exchange Online om rapporten op te halen uit afzonderlijke tenants van klanten.
  
Service providers voor de syndicatie en Cloud solution provider hebben toegang tot de gegevens die via externe Windows PowerShell voor Exchange Online PowerShell rechtstreeks met de Tenant rapporten van klanten worden gemaakt. Hierdoor kunnen partners de rapportagegegevens verzamelen en opslaan en daarna andere bewerkingen uitvoeren. Wanneer u een externe verbinding hebt geopend, wordt het verkrijgen van rapportagegegevens over een klant pacht identiek aan de uitvoering van een cmdlet voor een klant van pacht.
  
In dit artikel moet u extern Windows PowerShell voor Exchange Online gebruiken om verbinding te maken met één klant pacht en een rapport op te halen. Standaard biedt Windows PowerShell geen ondersteuning voor het samenvoegen van rapportagegegevens van meerdere klant tenancies. De rapporten die u met deze procedure ophaalt, gelden alleen voor de  _DelegatedOrg_ waarmee u verbinding maakt.
  
 
## <a name="before-you-begin"></a>Voordat u begint

- U moet verbinding maken met uw Exchange Online-Tenant via externe Windows PowerShell. Zie [verbinding maken met Exchange Online-tenants met externe Windows PowerShell voor instructies voor gedelegeerde toegangsmachtigingen (DAP)](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md) voor instructies.
    
## <a name="run-the-get-stalemailboxreport-sample"></a>Het voorbeeld voor Get-StaleMailboxReport uitvoeren

Wanneer u een externe sessie voor Exchange Online hebt geopend, voert u deze opdracht uit om de **Get-StaleMailboxReport** voor het datumbereik van 03/25/2015 tot en met 03/31/2015 op te halen.
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Er zijn veel andere rapportage-cmdlets beschikbaar voor Exchange Online, Lync online en SharePoint Online en andere voor de tracering van berichten die u kunt gebruiken. Zie de onderwerpen in de volgende sectie voor meer informatie over de beschikbare rapportage-cmdlets en de Office 365 Reporting-webservice.
  
## <a name="see-also"></a>Zie ook

#### 

[Service Office 365 Reporting voor de webservice](https://go.microsoft.com/fwlink/p/?LinkId=532777)
  
[Cmdlets voor rapporten in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=526430)
  
[Help voor partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)

