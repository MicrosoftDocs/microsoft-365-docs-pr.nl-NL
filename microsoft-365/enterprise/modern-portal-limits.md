---
title: SharePoint Online moderne portalsitelimieten
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: Meer informatie over prestatieaanbevelingen voor moderne sites in SharePoint Online, zoals het beperken van oproepen tot Sharepoint en externe eindpunten.
ms.openlocfilehash: 28c32be276f6c27194d164708e268a5cd36ac957
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925318"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint Online moderne portalsitelimieten

Dit artikel bevat prestatieaanbevelingen voor moderne portalsites in SharePoint Online. Gebruik de richtlijnen in dit artikel om de prestaties van moderne portalsite te optimaliseren en veelvoorkomende prestatieproblemen te voorkomen.

## <a name="performance-considerations-for-modern-portal-sites"></a>Prestatieoverwegingen voor moderne portalsites

Vanuit het oogpunt van prestatieoptimalisatie zijn er enkele kenmerken die moderne portalsites uniek maken. Het belangrijkste verschil tussen samenwerking en portalsites in SharePoint Online is schaal. Van portalsites wordt over het algemeen verwacht dat meer paginaweergaven worden weergegeven voor een groter aantal gebruikers dan samenwerkingssites en waarschijnlijk meer statische inhoud en minder bewerkbare bronnen bevatten. Bovendien verschilt de architectuur van moderne sites van klassieke sites omdat de meeste verwerkingen die betrokken zijn bij het weergeven van pagina's en het uitvoeren van code op de client plaatsvinden in plaats van op de server.

Prestatieoptimalisatie voor moderne portalsites is voornamelijk gericht op een paar algemene doelstellingen:

- De totale grootte van de onderdelen van elke sitepagina verkleinen
- Het hosten van veelvoorkomende statische bestanden, zoals afbeeldingen, stijlbladen en scripts, om te CDN
- Oproepen tot SharePoint en externe eindpunten beperken tot alleen wat nodig is
- Dubbele aanvragen voor dezelfde inhoud voorkomen

Veel van de richtlijnen in dit artikel zijn gericht op het minimaliseren en optimaliseren van oproepen SharePoint Online. Terugkerende oproepen telkens wanneer een pagina wordt geladen, zijn van invloed op de prestaties van gebruikers, omdat de informatie telkens uit de service wordt opgehaald, zelfs als deze niet is gewijzigd. Daarom kunnen aanvragen voor SharePoint worden gecategoriseerd als oproepen die gebruikelijk zijn voor alle gebruikers of oproepen die nodig zijn voor elke afzonderlijke gebruiker. De resultaten van deze twee gesprekscategorieën moeten in de cache worden opgeslagen om de gebruikerservaring te optimaliseren.

>[!NOTE]
>Gebruik het [hulpprogramma Paginadiagnose SharePoint als](./page-diagnostics-for-spo.md) uitgangspunt voor het analyseren van specifieke prestatiegegevens op SharePoint onlinesitepagina's.

## <a name="modern-portal-site-limits-and-recommendations"></a>Moderne portalsitelimieten en aanbevelingen

|**Limiet**|**Maximum aanbevolen waarde**|**Opmerkingen**|
|:-----|:-----|:-----|:-----|
|Pagina's en nieuwsitems  <br/> |5.000 per site  <br/> |We raden u aan het aantal pagina's en nieuwsitems in een moderne portalsite te beperken tot minder dan 5.000.  <br/> |
|Webonderdelen op een pagina  <br/> |20 per pagina  <br/> |Het is raadzaam om 20 of minder totale webonderdelen per pagina te gebruiken, inclusief zowel de out-of-the-box Microsoft-webonderdelen als aangepaste webonderdelen. <br/> Zie Prestaties van webonderdeel optimaliseren in [SharePoint moderne onlinesitepagina's](modern-web-part-optimization.md)voor meer informatie.  <br/> |
|Dynamische webonderdelen op een pagina  <br/> |4 per pagina  <br/> |Dynamische webonderdelen die een of meer query's maken om SharePoint om de meest recente gegevens op te halen, moeten worden beperkt tot 4 per pagina. Het _webonderdeel_ Nieuws is een voorbeeld van een dynamisch webonderdeel. <br/> Zie Prestaties van webonderdeel optimaliseren in [SharePoint moderne onlinesitepagina's](modern-web-part-optimization.md)voor meer informatie.    <br/> |
|Beveiligingsgroepen  <br/> |20 per site  <br/> |Het aantal beveiligingsgroepen is van invloed op de schaal van veel query's op moderne portalsites. U wordt aangeraden het aantal beveiligingsgroepen te beperken tot een zo klein mogelijke set, met maximaal 20 per site.  <br/> |
|Items in sitenavigatie  <br/> |100 per site  <br/> |We raden u aan minder dan 100 items toe te voegen aan sitenavigatie en gebruik te maken van niet-gebruiksnavigatiebesturingselementen.  <br/> Zie Paginagewicht optimaliseren [in SharePoint moderne onlinesitepagina's voor meer informatie.](modern-page-weight-optimization.md) <br/> |
|Maximale afbeeldingsgrootte  <br/> |300 Kb per afbeelding  <br/> |We raden u aan de grootte van afbeeldingen te beperken tot 300 kb of kleiner en een CDN gebruiken om afbeeldingen, stylesheets en scripts te hosten. <br/>Zie Afbeeldingen optimaliseren op moderne [sitepagina's SharePoint Online](modern-image-optimization.md) en De Office 365 Content Delivery Network [(CDN)](use-microsoft-365-cdn-with-spo.md)gebruiken met SharePoint Online voor meer informatie.  <br/> |
|Gebruikers met bewerkingsrechten  <br/> |200 gebruikers per site  <br/> |SharePoint portalsites zijn geoptimaliseerd voor het weergeven en consumeren van inhoud. Machtigingen voor bewerken op een portal moeten worden beperkt tot een beperkte groep gebruikers, omdat machtigingen voor bewerken extra besturingselementen downloaden en daarom trager voor deze gebruikers zullen presteren. Een te groot aantal gebruikers met bewerkingsmachtigingen is daarom van invloed op de algehele ervaring. <br/> |
|iFrames van derden  <br/> |2 per pagina  <br/> |iFrames zijn onvoorspelbaar traag omdat ze een afzonderlijke externe pagina laden, inclusief alle bijbehorende inhoud, zoals javascript, CSS en framework-elementen. Als u iFrames moet gebruiken, beperkt u het aantal tot 2 of minder per pagina.<br/> Zie IFrames optimaliseren in SharePoint moderne en klassieke [publicerende sitepagina's voor meer informatie.](modern-iframe-optimization.md) <br/> |
|Oproepen naar de UPA-service  <br/> |1 per gebruiker per uur  <br/> |Het is raadzaam om geen _oproepen per aanvraag_ uit te voeren naar de UPA-service (User Profile Application). De [Microsoft Graph API](/graph/call-api) en [PageContext](/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) kunnen worden gebruikt om te zoeken naar gebruikersgegevens.  <br/> Als een UPA-servicegesprek nodig is, belt u één keer wanneer dat nodig is en cachet u de gegevens voor hergebruik in dezelfde sessie. |
|Oproepen naar de Taxonomie-service  <br/> |5 per gebruiker per uur  <br/> |U wordt aangeraden om _niet per aanvraag te_ bellen naar de Taxonomie-service. Als taxonomie-serviceoproepen nodig zijn, cachet u de gegevens voor hergebruik in dezelfde sessie. <br/> Zie Paginagesprekken optimaliseren in SharePoint moderne en [klassieke publicerende sitepagina's online](modern-page-call-optimization.md)voor meer informatie. <br/> |

## <a name="related-topics"></a>Verwante onderwerpen

[Een gezonde portal SharePoint maken](/sharepoint/portal-health)

[Prestaties SharePoint online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties Office 365 afstemmen](tune-microsoft-365-performance.md)

[SharePoint Onlinelimieten](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Prestaties in de moderne SharePoint ervaring](/sharepoint/modern-experience-performance)

[Prestatie-richtlijnen SharePoint onlineportalen](/sharepoint/dev/solution-guidance/portal-performance)