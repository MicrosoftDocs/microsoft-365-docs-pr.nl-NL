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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Als u Microsoft hebt ingesteld om DNS-records voor uw aangepaste domein te beheren, vindt u informatie over het routeren van verkeer naar een bestaande openbare website die buiten Microsoft wordt gehost.
ms.openlocfilehash: 08a4e505f4e2a50b3e92cae00b62415e6d02551f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629117"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden

 **Als u de Microsoft-records van uw domein beheert bij uw DNS-hostingprovider,** hoeft u zich geen zorgen te maken over de stappen in dit onderwerp. De website verandert niet van locatie en blijft gewoon bereikbaar. 
  
 **Als Microsoft uw DNS-records beheert**om verkeer te routeren naar een bestaande openbare website die buiten Microsoft wordt gehost, gaat u als volgt te werk nadat u uw domein aan Microsoft hebt toegevoegd: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>DNS-records bijwerken in het Microsoft 365-beheercentrum
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

2. Op de pagina **Domeinen** selecteert u in de lijst met domeinen het domein dat u voor uw website gebruikt en selecteert u vervolgens **DNS-instellingen** in het deelvenster Beheren. 
    
3. Selecteer **+ Nieuwe aangepaste record** en typ het volgende: 
    
  - Voor **DNS-type** voert u in: **A (adres)**
    
  - Typ het volgende voor **Hostnaam of alias**: **@**
    
  - Voor **IP-adres** typt u het statische IP-adres van uw website waar deze momenteel wordt gehost (bijvoorbeeld: 172.16.140.1). 
    
    Dit moet een  *statisch*  IP-adres van de website zijn, geen  *dynamisch*  IP-adres. Kijk op de site waar uw website wordt gehost om er zeker van te zijn dat u een statisch IP-adres kunt krijgen voor uw openbare website. 
    
3. Selecteer **Opslaan**. 
    
U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.
  
1. Selecteer **+ Nieuwe aangepaste record** en typ het volgende: 
    
  - Voor **DNS-type** voert u in: **CNAME (alias)**
    
  - Voor **Hostnaam of alias** typt u: **www**
    
  - Voor **Adres waarnaar wordt verwezen** typt u de FQDN (Fully Qualified Domain Name) voor uw website (bijvoorbeeld contoso.com). 
    
2. Selecteer **Opslaan**. 
    
Ga ten slotte als volgt te werk:
  
[Werk de NS-records van uw domein bij](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) om naar Microsoft te wijzen. 
  
Wanneer de NS-records zijn bijgewerkt om naar Microsoft te wijzen, is uw domein helemaal ingesteld. E-mail wordt doorgestuurd naar Microsoft en het verkeer naar uw websiteadres blijft naar uw huidige websitehost gaan.
 
