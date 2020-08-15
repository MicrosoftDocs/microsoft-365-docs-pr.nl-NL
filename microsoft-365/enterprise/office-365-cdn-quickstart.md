---
title: Snelstartgids voor Office 365 Content Delivery Network (CDN)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Snelstartgids voor Office 365 Content Delivery Network (CDN)
ms.openlocfilehash: 8a8152c749306ed5247e92d4bc2c6a58e7a1c6cd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695690"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Snelstartgids voor Office 365 Content Delivery Network (CDN)

U kunt het ingebouwde **Office 365 Content Delivery Network (CDN)** gebruiken voor het hosten van statische activa (afbeeldingen, JavaScript, opmaakmodellen en WOFF-bestanden) voor betere prestaties voor de SharePoint Online-pagina's. Het CDN van Office 365 verbetert de prestaties omdat statische activa dichter bij de door u gevraagde browsers worden opgevolgd, zodat downloads sneller kunnen worden en de latentie minder kost. Daarnaast wordt in Office 365 CDN het Protocol HTTP/2 gebruikt voor verbeterde compressie en HTTP-pipeline. De Office 365 CDN-service maakt deel uit van uw SharePoint Online-abonnement.

Zie [het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)voor uitgebreidere informatie.

>[!NOTE]
>Het Office 365 CDN is alleen beschikbaar voor tenants in de productie-Cloud (wereldwijd). Tenants in de Verenigde Staten voor de overheid, China en Duitsland ondersteunen momenteel het Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Het hulpprogramma pagina diagnose voor SharePoint gebruiken om te zoeken naar items die niet in het CDN staan

U kunt de browser extensie voor de browser **van SharePoint voor SharePoint** gebruiken om eenvoudig de assets van de SharePoint Online-pagina's weer te geven die kunnen worden toegevoegd aan een CDN-oorsprong.

Het **hulpprogramma pagina diagnose voor SharePoint** is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren. Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria. Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](https://aka.ms/perftool).

Wanneer u het hulpprogramma pagina diagnose voor SharePoint op een SharePoint Online-pagina uitvoert, kunt u op het tabblad **diagnostische tests** klikken om een lijst weer te geven met assets die niet worden gehost op de CDN. Deze assets worden weergegeven onder het **selectievakje header Content Delivery Network (CDN)** , zoals wordt weergegeven in de onderstaande schermafbeelding.

![Diagnostische gegevens voor pagina's](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

## <a name="cdn-overview"></a>CDN-overzicht

Het Office 365 CDN is ontworpen om de prestaties van gebruikers te optimaliseren door regelmatig toegankelijke objecten zoals afbeeldingen en JavaScript-bestanden te distribueren via een hogesnelheidsnet globaal netwerk, de laadtijd van pagina's te beperken en toegang tot gehoste objecten zo dicht mogelijk te bieden. De CDN haalt de assets op van de locatie die een _oorsprong_wordt genoemd. Een oorsprong kan een SharePoint-site, documentbibliotheek of map zijn die toegankelijk is voor een URL.

Het CDN van Office 365 is onderverdeeld in twee basistypen:

- Het **openbare CDN** is bedoeld voor JS (JavaScript), CSS (Style Sheets), Web lettertypebestand (WOFF, WOFF2) en niet-eigen afbeeldingen zoals bedrijfslogo's.
- **Persoonlijk CDN** is bedoeld voor afbeeldingen (PNG, JPG, JPEG, enzovoort).

U kunt ervoor kiezen om zowel openbare als persoonlijke oorsprong te hebben voor uw organisatie. De meeste organisaties kiezen om een combinatie van beide te implementeren. Zowel de openbare als de persoonlijke opties bieden soortgelijke prestatieverbeteringen, maar elk heeft unieke kenmerken en voordelen. Zie voor meer informatie over openbare en persoonlijke CDN-oorsprong [de optie voor het maken van een openbare of persoonlijke oorsprong](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Public en private CDN inschakelen met de standaardconfiguratie
Voordat u wijzigingen aanbrengt in de CDN-instellingen van de Tenant, dient u te controleren of deze voldoet aan naleving, beveiliging en privacybeleid van uw organisatie.

Zie het gedeelte [Office 365 CDN instellen en configureren met behulp van de SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) voor meer informatie over de configuratie-instellingen of voor het toevoegen van een ander CDN en het toevoegen van extra locaties (oorsprong).

Maak verbinding met de Tenant met behulp van SharePoint Online Management Shell:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Als u wilt dat uw organisatie zowel openbare als persoonlijke Origins gebruikt met de standaardconfiguratie, typt u de volgende opdracht:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

De uitvoer van de volgende cmdlets ziet er als volgt uit:

![Uitvoer van set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Zie ook

[Het hulpprogramma pagina diagnose voor SharePoint Online gebruiken](https://aka.ms/perftool)

[Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Netwerken voor content levering](https://aka.ms/o365cdns)

[Network planning and performance tuning for Office 365](https://aka.ms/tune)

[SharePoint-prestatie serie-Office 365 CDN-VideoReeks](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
