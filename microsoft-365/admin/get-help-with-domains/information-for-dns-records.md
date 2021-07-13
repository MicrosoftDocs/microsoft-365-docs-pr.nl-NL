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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Verzamel de waarden/gegevens die u nodig hebt om DNS-records te maken om uw domein te verbinden met uw Microsoft 365 abonnement.
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393881"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>De gegevens verzamelen die u nodig hebt om DNS-records te maken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Stap 1: De TXT-recordwaarde zoeken en controleren

::: moniker range="o365-worldwide"

1. Ga in Microsoft 365-beheercentrum naar de pagina **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen.</a>

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
2. Selecteer op **de pagina** Domeinen uw domein en selecteer vervolgens **Setup starten.** U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.
    
3. Selecteer op **de pagina Domeinverificatie** de optie **Een TXT-record toevoegen** aan de DNS-records van het domein en selecteer vervolgens **Doorgaan.**
    
4. Kopieer de **weergegeven TXT-waarde.** Het ziet er zo uit: **MS=msXXXXXXXX**. 
    
5. Ga naar [DNS-records toevoegen om uw domein te verbinden](create-dns-records-at-any-dns-hosting-provider.md)en volg de stappen om records toe te voegen op de website van uw DNS-host.
    
6. Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en controleer vervolgens het domein weer in Microsoft 365.

7. Verwijder de TXT-record (of MX-record) van uw DNS-host zodra het domein is geverifieerd in Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Stap 2: De MX-recordwaarde voor e-mail zoeken en meer

::: moniker range="o365-worldwide"

1. Ga in Microsoft 365-beheercentrum naar de pagina **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen.</a>

::: moniker-end
    
::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
2. Selecteer uw domein op de pagina **Domeinen**.
    
3. Kies **Manage DNS**, select More Options **Add** your own  >  **DNS** and select **Continue** to see the DNS records to add.
    
    Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.
    
    Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.
    
4. Ga naar [DNS-records toevoegen om uw domein te verbinden](create-dns-records-at-any-dns-hosting-provider.md)en volg de stappen om records toe te voegen op de website van uw DNS-host.

5. Volg de stappen voor het maken van de records bij uw DNS-host.

## <a name="related-content"></a>Verwante inhoud

[Veelgestelde vragen over domeinen](../setup/domains-faq.yml) (artikel)\
[Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](find-and-fix-issues.md) (artikel)\
[Domeinen beheren](index.yml) (koppelingspagina)