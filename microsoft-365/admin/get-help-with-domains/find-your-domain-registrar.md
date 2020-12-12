---
title: Uw domeinregistrar zoeken
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Lees hier hoe u uw domeinregistrar en DNS-hostingprovider kunt vinden met behulp van de zoekpagina van InterNIC.
ms.openlocfilehash: 434e30709b112cf591159a1692540b8ef2b6bb65
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655540"
---
# <a name="find-your-domain-registrar"></a>Uw domeinregistrar zoeken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
## <a name="domain-registrar"></a>Domeinregistrar
  
### <a name="find-your-domain-name-registrar"></a>Uw domeinnaamregistrar vinden

>[!NOTE]
> Alleen domeinen die eindigen op *.COM*, *.NET* en *.EDU* werken met dit hulpprogramma.
  
1. Typ op de [zoekpagina van InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770) uw domein in het vak **Whois Search**. Bijvoorbeeld *contoso.com.* 
    
2. Selecteer de optie **Domain** en selecteer **Submit**.
    
3. Zoek op de pagina **Whois Search Results** het item **Registrar**. Hier staat de organisatie die fungeert als registrar voor uw domein. 
    
## <a name="dns-hosting-provider"></a>DNS-hostingprovider
  
### <a name="find-your-dns-hosting-provider"></a>Uw DNS-hostingprovider vinden

>[!NOTE]
> Alleen domeinen die eindigen op *.COM*, *.NET* en *.EDU* werken met dit hulpprogramma.
  
1. Typ op de [zoekpagina van InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770) uw domein in het vak **Whois Search**. Bijvoorbeeld contoso.com. 
    
2. Selecteer de optie **Domain** en selecteer **Submit**.
    
3. Zoek op de pagina **Whois Search Results** het item **Name Server**. 
    
4. Kopieer de gegevens over de naamserver (NS) na de dubbele punt (:) en plak ze in het vak **Search** bovenaan op de pagina. Selecteer **Nameserver** en selecteer **Submit**.
    
5. Zoek op de pagina **Whois Search Results** het item **Registrar**. Hier staat de DNS-serviceprovider, de DNS-provider die eigenaar is van de naamserver voor uw domein. 
    
---

