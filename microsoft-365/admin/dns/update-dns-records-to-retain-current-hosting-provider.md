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
ms.openlocfilehash: ceef82345e562e2aa4c291f416c454fb831ee45b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915972"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden

 Als u de Microsoft-records van uw domein beheert bij uw **DNS-hostingprovider,** hoeft u zich geen zorgen te maken over de stappen in dit onderwerp. De website verandert niet van locatie en blijft gewoon bereikbaar. 
  
 Ga als volgt te werk als Microsoft uw **DNS-records** beheert, om verkeer door te laten gaan naar een bestaande openbare website die buiten Microsoft wordt gehost, nadat u uw domein hebt toevoegen aan Microsoft: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>DNS-records bijwerken in het Microsoft 365-beheercentrum
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

2. Selecteer op **de pagina** Domeinen het domein en kies vervolgens **DNS Records.**

3. Selecteer **onder DNS-instellingen** de optie **Aangepaste records.**

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
  
[Werk de NS-records van uw domein bij om](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) naar Microsoft te wijzen. 
  
Wanneer de NS-records zijn bijgewerkt om naar Microsoft te wijzen, is uw domein helemaal ingesteld. E-mail wordt doorgeleid naar Microsoft en het verkeer naar uw websiteadres blijft naar uw huidige websitehost gaan.
