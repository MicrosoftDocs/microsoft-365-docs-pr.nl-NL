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
description: Meer informatie over de ' MSOID-CNAME-record in Office 365 waarmee u naar de beste server voor verificatieprocessen wordt geleid, zodat u een sneller antwoord krijgt.
monikerRange: o365-21vianet
ms.openlocfilehash: ac9ad3ad9f860722760d59c54570a453146a3a93
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644637"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Wat is het doel van de CNAME-record MSOID voor Office 365?

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
> [!NOTE]
> Het volgende is alleen van toepassing op * * Office 365, beheerd door 21Vianet.
  
U vraagt zich misschien af waarom u een CNAME-record voor MSOID moet toevoegen in Office 365. Dit is een record die u moet toevoegen voor alle aangepaste domeinen, ongeacht het abonnement dat u gebruikt. Waarom hebt u deze record nodig? Het is een beetje een technisch verhaal, maar het komt erop neer dat u wordt doorgestuurd naar de beste server voor bepaalde verificatieprocessen, zodat u sneller een reactie krijgt.
  
Technische informatie: wanneer u een clienttoepassing uitvoert die werkt met Office 365, zoals Skype voor Bedrijven Online, Outlook, Windows PowerShell of Microsoft AzureActive Directory-synchronisatie, moeten uw referenties worden geverifieerd. In Office 365 wordt een CNAME-record gebruikt om te verwijzen naar het juiste verificatie-eindpunt voor uw locatie. Op deze manier kan de snelheid van verificaties worden verhoogd.
  
Als deze CNAME-record voor uw domein ontbreekt, wordt door deze toepassingen een standaardeindpunt voor verificatie in de Verenigde Staten gebruikt. Hierdoor verloopt de verificatie mogelijk trager. Als deze CNAME-record niet correct wordt geconfigureerd, bijvoorbeeld wanneer het adres bij **Adres waarnaar wordt verwezen** een typefout bevat, kan er geen verificatie worden uitgevoerd.
  
 **Als Office 365 de DNS-records van uw domein beheert,** Office 365 stelt deze CNAME-record voor u in. 
  
 **Als u DNS-records voor uw domein bij uw DNS-host beheert,** maakt u deze record zelf door [de instructies te volgen voor uw DNS-host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).
  
Als u een Office 365-implementatie plant en meer wilt weten over alle DNS-records die u mogelijk wilt toevoegen of bijwerken, raadpleegt u de volgende informatie: externe DNS-records ( [Domain Name System) voor Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).
  

