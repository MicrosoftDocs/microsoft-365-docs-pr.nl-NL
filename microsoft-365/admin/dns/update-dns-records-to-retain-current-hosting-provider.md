---
title: DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: Meer informatie over het routeren van verkeer naar een bestaande openbare website die buiten Microsoft wordt gehost, als u Microsoft de DNS-records voor uw aangepaste domein wilt laten beheren.
ms.openlocfilehash: 9a7090eef3ce7d1c67839e7320f31d7bd32aa6a7
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814396"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden

 **Als u de Microsoft-records van uw domein beheert op uw DNS-hosting provider**, hoeft u zich geen zorgen te maken over de stappen in dit onderwerp. De website verandert niet van locatie en blijft gewoon bereikbaar. 
  
 **Als uw DNS-records door Microsoft worden beheerd**om verkeer naar een bestaande openbare website buiten Microsoft te routeren nadat u uw domein aan Microsoft hebt toegevoegd, gaat u als volgt te werk: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>DNS-records bijwerken in het Microsoft 365-Beheercentrum
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

2. Selecteer het domein op de pagina **domeinen** en kies vervolgens **DNS-records**.

3. Selecteer **aangepaste records**onder **DNS-instellingen**.

4. Selecteer **+ Nieuwe aangepaste record** en typ het volgende: 
    
   - Voor **DNS-type** voert u in: **A (adres)**
    
   - Typ het volgende voor **Hostnaam of alias**: **@**
    
   - Voor **IP-adres** typt u het statische IP-adres van uw website waar deze momenteel wordt gehost (bijvoorbeeld: 172.16.140.1). 
    
   Dit moet een  *statisch*  IP-adres van de website zijn, geen  *dynamisch*  IP-adres. Kijk op de site waar uw website wordt gehost om er zeker van te zijn dat u een statisch IP-adres kunt krijgen voor uw openbare website. 
    
5. Selecteer **Opslaan**. 
    
U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.
  
1. Selecteer **+ Nieuwe aangepaste record** en typ het volgende: 
    
   - Voor **DNS-type** voert u in: **CNAME (alias)**
    
   - Voor **Hostnaam of alias** typt u: **www**
    
   - Voor **Adres waarnaar wordt verwezen** typt u de FQDN (Fully Qualified Domain Name) voor uw website (bijvoorbeeld contoso.com). 
    
2. Selecteer **Opslaan**. 
    
Ga ten slotte als volgt te werk:
  
[Werk de DNS-records van uw domein](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) voor zodat ze verwijzen naar Microsoft. 
  
Wanneer de NS-records zijn bijgewerkt zodat ze verwijzen naar Microsoft, is uw domein allemaal ingesteld. E-mail wordt naar Microsoft gerouteerd en verkeer naar uw websiteadres gaat verder naar uw huidige website-host.
 
