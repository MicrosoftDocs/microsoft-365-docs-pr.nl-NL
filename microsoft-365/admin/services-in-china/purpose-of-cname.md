---
title: Wat is het doel van de CNAME-record MSOID voor Office 365?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Meer informatie over de CNAME-record 'MSOID' in Office 365 die u naar de beste server voor verificatieprocessen leidt, zodat u sneller antwoord krijgt.
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914304"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Wat is het doel van de CNAME-record MSOID voor Office 365?

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
> [!NOTE]
> Het volgende geldt alleen voor **Office 365 beheerd door 21Vianet.
  
U vraagt zich misschien af waarom u een CNAME-record voor MSOID moet toevoegen in Office 365. Dit is een record die u moet toevoegen voor alle aangepaste domeinen, ongeacht het abonnement dat u gebruikt. Waarom hebt u deze record nodig? Het is een beetje een technisch verhaal, maar het komt erop neer dat u wordt doorgestuurd naar de beste server voor bepaalde verificatieprocessen, zodat u sneller een reactie krijgt.
  
Technische informatie: wanneer u een clienttoepassing uitvoert die werkt met Office 365, zoals Skype voor Bedrijven Online, Outlook, Windows PowerShell of Microsoft AzureActive Directory-synchronisatie, moeten uw referenties worden geverifieerd. In Office 365 wordt een CNAME-record gebruikt om te verwijzen naar het juiste verificatie-eindpunt voor uw locatie. Op deze manier kan de snelheid van verificaties worden verhoogd.
  
Als deze CNAME-record voor uw domein ontbreekt, wordt door deze toepassingen een standaardeindpunt voor verificatie in de Verenigde Staten gebruikt. Hierdoor verloopt de verificatie mogelijk trager. Als deze CNAME-record niet correct wordt geconfigureerd, bijvoorbeeld wanneer het adres bij **Adres waarnaar wordt verwezen** een typefout bevat, kan er geen verificatie worden uitgevoerd.
  
 **Als Office 365 dns-records** van uw domein beheert, Office 365 deze CNAME-record voor u in. 
  
 **Als u DNS-records voor uw domein** bij uw DNS-host beheert, maakt u deze record zelf door de instructies voor uw [DNS-host te volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
  
Als u een Office 365-implementatie plant en meer wilt weten over alle DNS-records die u mogelijk moet toevoegen of bijwerken, leest u deze in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).
