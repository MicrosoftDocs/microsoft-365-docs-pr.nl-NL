---
title: Verzamel de informatie die u nodig hebt om DNS-records te maken
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Meer informatie over de waarden/informatie die u nodig hebt om DNS-records voor Microsoft 365 te maken. '
ms.custom: okr_smb
ms.openlocfilehash: 9cfefa2620b6a46b7488a29c22a58d70f53c6ad2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628444"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Verzamel de informatie die u nodig hebt om DNS-records te maken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Stap 1: De TXT-recordwaarde zoeken en verifiëren

::: moniker range="o365-worldwide"

1. Ga in het Microsoft 365-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setup-domeinen.</a> **Setup**

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Setup-domeinen.</a> **Setup**

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Setup-domeinen.</a> **Setup**

::: moniker-end
    
2. Selecteer **op** de pagina Domeinen uw domein en selecteer **Vervolgens Installatie starten**. U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.
    
3. Selecteer **op** de pagina Domein verifiëren in **plaats daarvan Een TXT-record toevoegen**en selecteer **Volgende**.
    
4. Kopieer de **getoonde TXT-waarde.** Het ziet er als volgt uit: **MS=msXXXXXXXX**. 
    
5. Ga naar [DNS-records maken bij elke DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registrars om de stapsgewijze instructies te bekijken.
    
6. Volg de stappen voor het maken van de TXT-record (of MX-record) op uw DNS-host en controleer het domein terug in Microsoft 365.

7. Verwijder de TXT-record (of MX-record) van uw DNS-host zodra het domein is geverifieerd in Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Stap 2: Zoek de MX-recordwaarde voor e-mail en meer

::: moniker range="o365-worldwide"

1. Ga in het Microsoft 365-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setup-domeinen.</a> **Setup**

::: moniker-end
    
::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Setup-domeinen.</a> **Setup**

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Setup-domeinen.</a> **Setup**

::: moniker-end
    
2. Selecteer uw domein op de pagina **Domeinen**. 
    
3. Onder **Vereiste DNS-instellingen** ziet u de DNS-records die u moet toevoegen.
    
    Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.
    
    Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.
    
4. Ga naar [DNS-records maken bij elke DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer vervolgens uw DNS-host in de lijst met registrars om stapsgewijze instructies te zien voor het toevoegen van records op de website van die DNS-host.
    
5. Volg de stappen voor het maken van de records bij uw DNS-host.
