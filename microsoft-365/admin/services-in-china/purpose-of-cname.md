---
title: Wat is het doel van de CNAME-record MSOID voor Office 365?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Meer informatie over de CNAME-record 'MSOID' in Office 365 die u naar de beste server voor verificatieprocessen leidt, zodat u sneller reageert.
monikerRange: o365-21vianet
ms.openlocfilehash: f5369b8a723c60691da0e73f2bd8cc32233abbcd
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212219"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Wat is het doel van de CNAME-record MSOID voor Office 365?

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
> [!NOTE]
> Het volgende geldt alleen voor **Office 365 dat wordt beheerd door 21Vianet.
  
U vraagt zich misschien af waarom u een CNAME-record voor MSOID moet toevoegen in Office 365. Dit is een record die u moet toevoegen voor alle aangepaste domeinen, ongeacht het abonnement dat u gebruikt. Waarom hebt u deze record nodig? Het is een beetje een technisch verhaal, maar het komt erop neer dat u wordt doorgestuurd naar de beste server voor bepaalde verificatieprocessen, zodat u sneller een reactie krijgt.
  
Technische informatie: wanneer u een clienttoepassing uitvoert die werkt met Office 365, zoals Skype voor Bedrijven Online, Outlook, Windows PowerShell of Microsoft AzureActive Directory-synchronisatie, moeten uw referenties worden geverifieerd. In Office 365 wordt een CNAME-record gebruikt om te verwijzen naar het juiste verificatie-eindpunt voor uw locatie. Op deze manier kan de snelheid van verificaties worden verhoogd.
  
Als deze CNAME-record voor uw domein ontbreekt, wordt door deze toepassingen een standaardeindpunt voor verificatie in de Verenigde Staten gebruikt. Hierdoor verloopt de verificatie mogelijk trager. Als deze CNAME-record niet correct wordt geconfigureerd, bijvoorbeeld wanneer het adres bij **Adres waarnaar wordt verwezen** een typefout bevat, kan er geen verificatie worden uitgevoerd.
  
 **Als Office 365 de DNS-records van uw domein beheert,** Office 365 stelt deze CNAME-record voor u in. 
  
 **Als u DNS-records voor uw domein beheert bij uw DNS-host,** maakt u deze record zelf door [de instructies voor uw DNS-host te volgen.](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx)
  
Als u een Office 365-implementatie plant en meer wilt weten over alle DNS-records die u mogelijk moet toevoegen of bijwerken, leest u deze gegevens in [Referentie: Extern domeinnaamsysteemrecords voor Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).
  

