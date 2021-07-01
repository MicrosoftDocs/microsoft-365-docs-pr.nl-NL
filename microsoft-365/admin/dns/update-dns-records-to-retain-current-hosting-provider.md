---
title: DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Informatie over het door routen van verkeer naar een bestaande openbare website die buiten Microsoft wordt gehost, als u Microsoft hebt ingesteld voor het beheren van DNS-records voor uw aangepaste domein.
ms.openlocfilehash: d54aa4583862ce19907a3b8494a333bbb925e436
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228121"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden

 Als u de Microsoft-records van uw domein beheert bij uw **DNS-hostingprovider,** hoeft u zich geen zorgen te maken over de stappen in dit onderwerp. De website verandert niet van locatie en blijft gewoon bereikbaar. 
  
 Ga als volgt te werk als Microsoft uw **DNS-records** beheert, om verkeer door te laten gaan naar een bestaande openbare website die buiten Microsoft wordt gehost, nadat u uw domein hebt toevoegen aan Microsoft: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>DNS-records bijwerken in de Microsoft 365-beheercentrum
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

1. Selecteer op **de pagina** Domeinen het domein en kies vervolgens **DNS Records.**

1. Selecteer **+ Record toevoegen** en voer het volgende in: 
    
   - Voor **type** enter: **A (Adres)**
    
   - Typ het volgende voor **Hostnaam of alias**: **@**
    
   - Voor **IP-adres** typt u het statische IP-adres van uw website waar deze momenteel wordt gehost (bijvoorbeeld: 172.16.140.1). 
    
   Dit moet een  *statisch*  IP-adres van de website zijn, geen  *dynamisch*  IP-adres. Kijk op de site waar uw website wordt gehost om er zeker van te zijn dat u een statisch IP-adres kunt krijgen voor uw openbare website. 
    
1. Selecteer **Opslaan**. 
    
U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.
  
1. Selecteer **+ Record toevoegen** en voer het volgende in: 
    
   - Voor **type** enter: **CNAME (Alias)**
    
   - Voor **Hostnaam of alias** typt u: **www**
    
   - Voor **Adres waarnaar wordt verwezen** typt u de FQDN (Fully Qualified Domain Name) voor uw website (bijvoorbeeld contoso.com). 
    
2. Selecteer **Opslaan**. 
    
Ga ten slotte als volgt te werk:
  
[Werk de NS-records van uw domein bij om](../setup/add-domain.md) naar Microsoft te wijzen. 
  
Wanneer de NS-records zijn bijgewerkt om naar Microsoft te wijzen, is uw domein helemaal ingesteld. E-mail wordt doorgeleid naar Microsoft en het verkeer naar uw websiteadres blijft naar uw huidige websitehost gaan.
