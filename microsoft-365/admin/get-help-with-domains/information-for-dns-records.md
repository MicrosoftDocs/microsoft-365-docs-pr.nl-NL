---
title: De informatie verzamelen die u nodig hebt om DNS-records te maken
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
description: 'Lees hoe u de waarden/informatie vindt die u nodig hebt om DNS-records voor Microsoft 365 te maken. '
ms.openlocfilehash: 45994139b11a2fd5a03b2e979dd6af334bc1f00b
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126369"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>De informatie verzamelen die u nodig hebt om DNS-records te maken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Stap 1: de waarde van de TXT-record zoeken en controleren

::: moniker range="o365-worldwide"

1. Ga in het Microsoft 365-beheercentrum naar **de** pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a> instellen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de **pagina** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a> instellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de **pagina** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a> instellen.

::: moniker-end
    
2. Selecteer uw **domein op de** pagina Domeinen en selecteer Setup **starten.** U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.
    
3. Selecteer op **de pagina Domein** verifiëren in plaats daarvan **TXT-record toevoegen** en selecteer vervolgens **Volgende.**
    
4. Kopieer de **weergegeven TXT-waarde.** Deze ziet er zo uit: **MS=msXXXXXXXX.** 
    
5. Ga naar DNS-records maken bij een [DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registrars voor de stapsgewijse instructies.
    
6. Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en verifieer vervolgens het domein in Microsoft 365.

7. Verwijder de TXT-record (of MX-record) van uw DNS-host nadat het domein is geverifieerd in Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Stap 2: De waarde van de MX-record voor e-mail zoeken en meer

::: moniker range="o365-worldwide"

1. Ga in het Microsoft 365-beheercentrum naar **de** pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a> instellen.

::: moniker-end
    
::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de **pagina** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a> instellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de **pagina** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a> instellen.

::: moniker-end
    
2. Selecteer uw domein op de pagina **Domeinen**. 
    
3. Onder **Vereiste DNS-instellingen** ziet u de DNS-records die u moet toevoegen.
    
    Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.
    
    Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.
    
4. Ga naar DNS-records maken bij een [DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registrars om stapsgewijs instructies te zien voor het toevoegen van records op de website van die DNS-host.
    
5. Volg de stappen voor het maken van de records bij uw DNS-host.
