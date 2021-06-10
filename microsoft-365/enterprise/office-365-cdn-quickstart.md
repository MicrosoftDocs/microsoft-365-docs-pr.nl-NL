---
title: Office 365 Content Delivery Network (CDN) Quickstart
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
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network (CDN) Quickstart
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921592"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 Content Delivery Network (CDN) Quickstart

U kunt de ingebouwde **Office 365 Content Delivery Network (CDN)** gebruiken om statische assets (afbeeldingen, JavaScript, Stylesheets, WOFF-bestanden) te hosten om betere prestaties te bieden voor uw SharePoint Online-pagina's. De Office 365 CDN verbetert de prestaties door statische assets dichter bij de browsers te houden waarin ze worden gevraagd, wat helpt om downloads te versnellen en de latentie te verminderen. De Office 365 CDN gebruikt ook het HTTP/2-protocol voor verbeterde compressie en HTTP-pipelineing. De Office 365 CDN service is opgenomen als onderdeel van uw SharePoint Online-abonnement.

Zie De Office 365 Content Delivery Network [(CDN)](use-microsoft-365-cdn-with-spo.md)met SharePoint Online voor meer informatie.

>[!NOTE]
>De Office 365 CDN is alleen beschikbaar voor tenants in de productiecloud (wereldwijd). Tenants in de amerikaanse overheid, China en Duitsland clouds ondersteunen momenteel de Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Gebruik het hulpprogramma Paginadiagnose voor SharePoint om items te identificeren die niet in de CDN

U kunt de browserextensie **Paginadiagnose** voor SharePoint gebruiken om eenvoudig activa in uw SharePoint Online-pagina's weer te geven die kunnen worden toegevoegd aan een CDN origin.

Het **hulpprogramma Paginadiagnose voor SharePoint** is een browserextensie voor de nieuwe Microsoft Edge ( en Chrome-browsers die zowel SharePoint Moderne portal online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's analyseert. Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria. Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken](./page-diagnostics-for-spo.md)voor SharePoint Online.

Wanneer u het hulpprogramma Paginadiagnose voor SharePoint op een pagina SharePoint  Online uit te voeren, kunt u op het tabblad Diagnostische tests klikken om een lijst weer te geven met assets die niet worden gehost door de CDN. Deze activa worden weergegeven onder de kopcontrole **Content Delivery Network (CDN)** zoals wordt weergegeven in de onderstaande schermafbeelding.

![Paginadiagnose](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Het hulpprogramma Paginadiagnose werkt alleen SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.

## <a name="cdn-overview"></a>CDN Overzicht

De Office 365 CDN is ontworpen om de prestaties voor gebruikers te optimaliseren door veelgebruikte objecten, zoals afbeeldingen en javascript-bestanden, te distribueren via een snel globaal netwerk, de laadtijd van pagina's te verkorten en door de gebruiker zo dicht mogelijk toegang te bieden tot gehoste objecten. De CDN haalt uw activa op van een locatie die een origin _wordt genoemd._ Een origin kan een SharePoint site, documentbibliotheek of map zijn die toegankelijk is via een URL.

De Office 365 CDN is gescheiden in twee basistypen:

- **Openbare CDN** is ontworpen voor JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) en niet-eigendomsafbeeldingen, zoals bedrijfslogo's.
- **Persoonlijke CDN** is ontworpen voor afbeeldingen (PNG, JPG, JPEG, enzovoort).

U kunt ervoor kiezen om zowel openbare als persoonlijke origins voor uw organisatie te hebben. De meeste organisaties kiezen ervoor om een combinatie van de twee te implementeren. Openbare en private opties bieden vergelijkbare prestatieverbeteringen, maar elk heeft unieke kenmerken en voordelen. Zie Kiezen of elke origin openbaar of privé [](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)moet zijn voor meer informatie over openbare en CDN origins.

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Openbare en privé-CDN met de standaardconfiguratie inschakelen
Voordat u wijzigingen aan de tenantinstellingen CDN, moet u controleren of deze voldoet aan het compliance-, beveiligings- en privacybeleid van uw organisatie.

Voor meer gedetailleerde configuratie-instellingen of als u CDN al hebt ingeschakeld en extra locaties (origins) wilt toevoegen, raadpleegt u de sectie De Office 365 CDN instellen en configureren met behulp van [de SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Verbinding maken naar uw tenant met behulp van SharePoint Online Management Shell:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Als u wilt dat uw organisatie zowel openbare als persoonlijke origins met de standaardconfiguratie kan gebruiken, typt u de volgende opdracht:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

De uitvoer van deze cmdlets ziet er als volgt uit:

![Uitvoer van Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Zie ook

[Het hulpprogramma Paginadiagnose gebruiken voor SharePoint Online](./page-diagnostics-for-spo.md)

[De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Netwerken voor contentlevering](./content-delivery-networks.md)

[Network planning and performance tuning for Office 365](./network-planning-and-performance.md)

[SharePoint Performance Series - Office 365 CDN videoreeks](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)