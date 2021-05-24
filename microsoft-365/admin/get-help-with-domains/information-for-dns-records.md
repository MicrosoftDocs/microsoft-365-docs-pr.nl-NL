---
title: De gegevens verzamelen die u nodig hebt om DNS-records te maken
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Verzamel de waarden/gegevens die u nodig hebt om DNS-records te maken om uw domein te verbinden met uw Microsoft 365 abonnement.
ms.openlocfilehash: e65d53269f5fb8625b12c4eb22f78516818045be
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635724"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>De gegevens verzamelen die u nodig hebt om DNS-records te maken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Stap 1: De TXT-recordwaarde zoeken en controleren

::: moniker range="o365-worldwide"

1. Ga in Microsoft 365 beheercentrum naar de pagina **Domeinen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> instellen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de **pagina Domeinen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a> instellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de **pagina Domeinen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a> instellen.

::: moniker-end
    
2. Selecteer op **de pagina** Domeinen uw domein en selecteer vervolgens **Setup starten.** U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.
    
3. Selecteer op **de pagina** Domein verifiëren de optie In plaats daarvan **een TXT-record toevoegen** en selecteer vervolgens **Volgende**.
    
4. Kopieer de **weergegeven TXT-waarde.** Het ziet er zo uit: **MS=msXXXXXXXX**. 
    
5. Ga naar DNS-records maken bij een [DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registrars om de stapsgewijs instructies te bekijken.
    
6. Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en controleer vervolgens het domein weer in Microsoft 365.

7. Verwijder de TXT-record (of MX-record) van uw DNS-host zodra het domein is geverifieerd in Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Stap 2: De MX-recordwaarde voor e-mail zoeken en meer

::: moniker range="o365-worldwide"

1. Ga in Microsoft 365 beheercentrum naar de pagina **Domeinen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> instellen.

::: moniker-end
    
::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de **pagina Domeinen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a> instellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de **pagina Domeinen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a> instellen.

::: moniker-end
    
2. Selecteer uw domein op de pagina **Domeinen**. 
    
3. Onder **Vereiste DNS-instellingen** ziet u de DNS-records die u moet toevoegen.
    
    Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.
    
    Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.
    
4. Ga naar DNS-records maken bij een [DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer vervolgens uw DNS-host in de lijst met registrars om stapsgewijs instructies te zien voor het toevoegen van records op de website van die DNS-host.
    
5. Volg de stappen voor het maken van de records bij uw DNS-host.

## <a name="related-content"></a>Verwante onderwerpen

[Veelgestelde vragen over domeinen](../setup/domains-faq.yml) (artikel)\
[Problemen zoeken en oplossen na het toevoegen van uw domein of DNS-records](find-and-fix-issues.md) (artikel)\
[Domeinen beheren](index.yml) (koppelingspagina)