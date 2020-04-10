---
title: Uw domeinregistrar voor Office 365 zoeken
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Lees hier hoe u uw domeinregistrar en DNS-hostingprovider kunt vinden met behulp van de zoekpagina van InterNIC.
ms.openlocfilehash: 71af74a0f94f2cdc251dab78fd59e9bdd90da5ce
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210390"
---
# <a name="find-your-domain-registrar-for-office-365"></a>Uw domeinregistrar voor Office 365 zoeken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
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

