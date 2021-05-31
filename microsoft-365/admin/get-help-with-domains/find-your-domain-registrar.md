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
ms.openlocfilehash: af883f53c8c45aee2594b0f5b8b9da57e5717f9e
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706392"
---
# <a name="find-your-domain-registrar"></a>Uw domeinregistrar zoeken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
## <a name="domain-registrar"></a>Domeinregistrar
  
### <a name="find-your-domain-name-registrar"></a>Uw domeinnaamregistrar vinden

>[!NOTE]
> Alleen domeinen die eindigen op *.COM*, *.NET* en *.EDU* werken met dit hulpprogramma.
  
1. Typ uw domein op de [zoekpagina van InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770) in het vak **Whois Search**, bijvoorbeeld *contoso.com*. 
    
2. Selecteer de optie **Domain** en selecteer **Submit**.
    
3. Zoek op de pagina **Whois Search Results** het item **Registrar**. Hier staat de organisatie die fungeert als registrarservice voor uw domein. 
    
## <a name="dns-hosting-provider"></a>DNS-hostingprovider
  
### <a name="find-your-dns-hosting-provider"></a>Uw DNS-hostingprovider vinden

>[!NOTE]
> Alleen domeinen die eindigen op *.COM*, *.NET* en *.EDU* werken met dit hulpprogramma.
  
1. Typ uw domein op de [zoekpagina van InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770) in het vak **Whois Search**, bijvoorbeeld contoso.com. 
    
2. Selecteer de optie **Domain** en selecteer **Submit**.
    
3. Zoek op de pagina **Whois Search Results** het item **Name Server**. 
    
4. Kopieer de gegevens van de naamserver (NS) na de dubbele punt (:) en plak ze in het vak **Search** bovenaan op de pagina. Selecteer **Nameserver** en vervolgens **Submit**.
    
5. Zoek op de pagina **Whois Search Results** het item **Registrar**. Hier staat de DNS-serviceprovider, de DNS-provider die eigenaar is van de naamserver voor uw domein. 
    
---

