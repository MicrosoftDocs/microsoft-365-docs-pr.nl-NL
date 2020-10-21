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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Leer de waarden/informatie vinden die u nodig hebt om DNS-records voor Microsoft 365 te maken. '
ms.openlocfilehash: eca9dbe4e40193f76538b639624b827177ff7772
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645309"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>De gegevens verzamelen die u nodig hebt om DNS-records te maken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Stap 1: Zoek de TXT-recordwaarde en controleer of

::: moniker range="o365-worldwide"

1. Ga in het Microsoft 365-Beheercentrum naar **Setup** de \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen</a> instellen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het Beheercentrum naar de pagina **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domeinen</a> instellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het Beheercentrum naar de pagina **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domeinen</a> instellen.

::: moniker-end
    
2. Selecteer uw domein op de pagina **domeinen** en selecteer vervolgens **Setup starten**. U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.
    
3. Selecteer op de pagina **domein verifiëren** de optie hier **TXT-record toevoegen**en selecteer **volgende**.
    
4. Kopieer de getoonde **txt-waarde** . Dit ziet er als volgt uit: **MS = msXXXXXXXX**. 
    
5. Ga naar [DNS-records maken bij een DNS-hosting provider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registraties om de stapsgewijze instructies weer te geven.
    
6. Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en Verifieer het domein weer in Microsoft 365.

7. Verwijder de TXT-record (of MX-record) van uw DNS-host wanneer het domein is geverifieerd in Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Stap 2: zoeken naar de MX-recordwaarde voor e-mail en meer

::: moniker range="o365-worldwide"

1. Ga in het Microsoft 365-Beheercentrum naar **Setup** de \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen</a> instellen.

::: moniker-end
    
::: moniker range="o365-germany"

1. Ga in het Beheercentrum naar de pagina **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domeinen</a> instellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het Beheercentrum naar de pagina **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domeinen</a> instellen.

::: moniker-end
    
2. Selecteer uw domein op de pagina **Domeinen**. 
    
3. Onder **Vereiste DNS-instellingen** ziet u de DNS-records die u moet toevoegen.
    
    Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.
    
    Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.
    
4. Ga naar [DNS-records maken bij een DNS-hosting provider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer vervolgens uw DNS-host in de lijst met bronvermeldingen voor stapsgewijze instructies voor het toevoegen van records aan de website van de DNS-host.
    
5. Volg de stappen voor het maken van de records bij uw DNS-host.
