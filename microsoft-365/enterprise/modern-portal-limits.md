---
title: Limieten voor moderne portal-sites in SharePoint Online
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
description: Meer informatie over aanbevelingen voor moderne sites in SharePoint Online, zoals oproepen voor SharePoint en externe eindpunten beperken.
ms.openlocfilehash: 2afca20183bef8c8f6dda9bdc35a44e5153ef07c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689402"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>Limieten voor moderne portal-sites in SharePoint Online

Dit artikel biedt prestatie aanbevelingen voor moderne portal-sites in SharePoint Online. Gebruik de richtlijnen in dit artikel om de prestaties van de moderne portal-site te optimaliseren en veelvoorkomende prestatieproblemen te voorkomen.

## <a name="performance-considerations-for-modern-portal-sites"></a>Prestatieoverwegingen voor moderne portalsites

Vanuit het oogpunt van optimaliseren van prestaties zijn er een paar kenmerken die de moderne portal-sites uniek maken. Het belangrijkste verschil tussen samenwerking en portalsites in SharePoint Online is schaal. Portal sites worden meestal niet meer naar een groter aantal gebruikers weergegeven dan Samenwerkingssites, en kunnen waarschijnlijk meer statische inhoud bevatten en minder bewerkbare bronnen. Daarnaast is de architectuur van moderne sites afwijkend van de klassieke sites waarvan de verwerking van pagina's en het uitvoeren van code op de client plaatsvindt, in plaats van de server.

Prestatie optimalisering voor moderne portal-sites is hoofdzakelijk gericht op een paar algemene doelstellingen:

- De totale grootte van de onderdelen van de pagina site verkleinen
- Offloading van gemeenschappelijke statische bestanden, zoals afbeeldingen, opmaakmodellen en scripts, aan CDN
- Oproepen beperken tot SharePoint-en externe eindpunten uitsluitend wat nodig is
- Vermijd dubbele aanvragen voor dezelfde inhoud

Veel van de richtlijnen in dit artikel focus op het minimaliseren en optimaliseren van oproepen naar SharePoint Online. Als u een pagina laadt, worden de prestaties van de gebruikers beïnvloed wanneer de gegevens worden opgehaald van de service, ook als deze niet is gewijzigd. Daarom kunnen aanvragen voor SharePoint worden gecategoriseerd als gesprekken die voor elke afzonderlijke gebruiker gelden. Resultaten van deze twee gespreks categorieën moeten worden opgeslagen in de cache om de gebruikerservaring te optimaliseren.

>[!NOTE]
>Het [hulpprogramma pagina diagnose voor SharePoint](https://aka.ms/perftool) gebruiken als uitgangspunt voor het analyseren van bepaalde prestatiegegevens op SharePoint Online-sitepagina's.

## <a name="modern-portal-site-limits-and-recommendations"></a>Limieten en aanbevelingen voor moderne portalsites

|**Limiet**|**Maximale aanbevolen waarde**|**Opmerkingen**|
|:-----|:-----|:-----|:-----|
|Pagina's en nieuwsitems  <br/> |5.000 per site  <br/> |U wordt aangeraden het aantal pagina's en nieuwsitems op een moderne portalsite te beperken tot onder 5.000.  <br/> |
|Webonderdelen op een pagina  <br/> |20 per pagina  <br/> |We raden u aan gebruik te maken van 20 of minder totale webonderdelen per pagina, waaronder zowel kant-en-klare Microsoft-webonderdelen en aangepaste webonderdelen. <br/> Voor meer informatie raadpleegt u de [prestaties van het webonderdeel in SharePoint Online-sitepagina's optimaliseren](modern-web-part-optimization.md).  <br/> |
|Dynamische webonderdelen op een pagina  <br/> |4 per pagina  <br/> |Dynamische webonderdelen waarmee een of meer query's van SharePoint worden uitgevoerd voor het ophalen van de nieuwste gegevens, moeten worden beperkt tot 4 per pagina. Het webonderdeel _Nieuws_ is een voorbeeld van een dynamisch webonderdeel. <br/> Voor meer informatie raadpleegt u de [prestaties van het webonderdeel in SharePoint Online-sitepagina's optimaliseren](modern-web-part-optimization.md).    <br/> |
|Beveiligingsgroepen  <br/> |20 per site  <br/> |Het aantal beveiligingsgroepen is van invloed op de schaal van veel query's in moderne portal-sites. U wordt aangeraden het aantal beveiligingsgroepen zo klein mogelijk te beperken, met niet meer dan 20 per site.  <br/> |
|Items in sitenavigatie  <br/> |100 per site  <br/> |Het is raadzaam minder dan 100 items toe te voegen aan sitenavigatie en dat u de besturingselementen die u niet gebruikt voor het navigeren gebruiken.  <br/> Zie [pagina gewicht in moderne SharePoint Online-sitepagina's optimaliseren](modern-page-weight-optimization.md)voor meer informatie. <br/> |
|Maximale grootte van afbeeldingen  <br/> |300 kB per afbeelding  <br/> |We raden u aan de grootte van afbeeldingen te beperken tot 300kb of kleiner, en het gebruik van een CDN voor de host van afbeeldingen, opmaakmodellen en scripts. <br/>Zie voor meer informatie [afbeeldingen optimaliseren in moderne sitepagina's voor SharePoint Online](modern-image-optimization.md) en [gebruik het Office 365 Content Delivery Network (CDN) met SharePoint Online](use-microsoft-365-cdn-with-spo.md).  <br/> |
|Gebruikers met bewerkingsrechten  <br/> |200 gebruikers per site  <br/> |SharePoint Portal-sites zijn geoptimaliseerd voor het weergeven en gebruiken van inhoud. Het bewerken van machtigingen op een portal moet beperkt zijn tot een beperkte groep gebruikers omdat machtigingen bewerken extra besturingselementen downloaden en hierdoor sneller worden uitgevoerd voor deze gebruikers. Een buitensporig aantal gebruikers met bewerkingsmachtigingen is dus van invloed op de algemene ervaring. <br/> |
|IFrames van derden  <br/> |2 per pagina  <br/> |iFrames zijn slecht traag omdat ze een afzonderlijke externe pagina laden, waaronder alle bijbehorende inhoud, zoals JavaScript, CSS en Framework elementen. Als u iFrames moet gebruiken, moet u het nummer van de tabel beperken tot 2 of minder per pagina.<br/> Zie [iframes in SharePoint Online-pagina's met de publicerende sites optimaliseren](modern-iframe-optimization.md)voor meer informatie. <br/> |
|Oproepen naar de UPA-service  <br/> |1 per gebruiker per uur  <br/> |U wordt aangeraden geen _aanvragen per aanvraag_ te bellen naar de service UPA (gebruikersprofieltoepassing). De [Microsoft Graph API](https://docs.microsoft.com/graph/call-api) en [PageContext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) kunnen worden gebruikt voor het opvragen van gebruikersgegevens.  <br/> Als u een UPA-serviceoproep nodig hebt, voert u indien nodig één gesprek uit en slaat u de gegevens op voor hergebruik in dezelfde sessie. |
|Oproepen naar de Taxonomieservice  <br/> |5 per gebruiker per uur  <br/> |U wordt aangeraden geen _per aanvraag_ oproepen te doen naar de taxonomieservice. Als de Taxonomieservice oproepen noodzakelijk zijn, slaat u de gegevens op in de cache voor hergebruik in dezelfde sessie. <br/> Zie voor meer informatie [pagina oproepen optimaliseren in de pagina's modern van SharePoint Online en de klassieke publicatiesite](modern-page-call-optimization.md). <br/> |

## <a name="related-topics"></a>Verwante onderwerpen

[Een gezonde SharePoint-Portal maken](https://docs.microsoft.com/sharepoint/portal-health)

[Prestaties van SharePoint Online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)

[Limieten voor SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Richtlijnen voor de prestaties van SharePoint Online-portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance)
