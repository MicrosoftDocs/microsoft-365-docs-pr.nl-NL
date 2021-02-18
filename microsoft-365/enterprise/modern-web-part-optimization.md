---
title: Prestaties van webonderdeel optimaliseren op moderne SharePoint Online-sitepagina's
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Informatie over het gebruik van Page Diagnostics om de prestaties van webonderdelen in moderne SharePoint Online-sitepagina's te optimaliseren.
ms.openlocfilehash: ca1b9328ad71fdd4a3f3c6c6be47eaa3993d4fc7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287147"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a>Prestaties van webonderdeel optimaliseren op moderne SharePoint Online-sitepagina's

Moderne SharePoint Online-sitepagina's bevatten webonderdelen die kunnen bijdragen aan de totale laadtijden van pagina's. In dit artikel wordt beschreven hoe u kunt bepalen hoe webonderdelen op uw pagina's van invloed zijn op de door de gebruiker waargenomen latentie en hoe u veelvoorkomende problemen kunt oplossen.

>[!NOTE]
>Zie Prestaties in de moderne SharePoint-ervaring voor meer informatie over de prestaties in moderne [SharePoint Online-portals.](https://docs.microsoft.com/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a>Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om webonderdelen te analyseren

Het hulpprogramma Paginadiagnose voor SharePoint is een browseruitbreiding voor de nieuwe versie van Microsoft Edge (en Chrome-browsers die zowel moderne Portal- als klassieke publicerende sitepagina's van https://www.microsoft.com/edge) SharePoint Online analyseren. Het hulpmiddel bevat een rapport voor elke geanalyseerde pagina, waarin u kunt zien hoe de pagina presteert ten opzichte van een gedefinieerde set prestatiecriteria. Ga naar Het hulpprogramma Paginadiagnose voor SharePoint Online gebruiken voor meer informatie over het hulpprogramma [Paginadiagnose voor SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Het hulpprogramma Paginadiagnose werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een SharePoint-sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, kunt u in het deelvenster Diagnostische tests informatie zien over webonderdelen die de basislijnmeting overschrijden in de **webonderdelen.** 

Mogelijke resultaten zijn:

- **Aandacht vereist** (rood): Elk aangepast _webonderdeel_ dat wordt weergegeven in de viewport (het zichtbare  gedeelte van de pagina dat als eerste wordt geladen) duurt langer dan twee seconden. Aangepaste _webonderdelen_ buiten de viewport die langer dan **vier** seconden in beslag nemen. De totale laadtijd wordt weergegeven in de testresultaten en wordt onderverdeeld per modulebelasting, één voor één laden, init en weergeven.
- **Verkoopkansen voor** kwaliteitsverbetering (geel): Items die van invloed kunnen zijn op de laadtijd van pagina's worden in deze sectie weergegeven en moeten worden gecontroleerd en gecontroleerd. Dit kunnen 'out of the box' (OOTB) Microsoft-webonderdelen zijn. De resultaten voor Microsoft-webonderdelen die in deze sectie worden weergegeven, worden automatisch aan Microsoft gerapporteerd, **dus u hoeft niets te doen.** Meld alleen een ondersteuningsticket aan voor onderzoek als de pagina erg traag **werkt** en alle **Microsoft-webonderdelen** op de pagina worden weergegeven in de resultaten in de sectie Verkoopkansen voor kwaliteitsverbetering. Houd er rekening mee dat de resultaten na een toekomstige update van het hulpprogramma Page Diagnostics voor SharePoint verder worden opgedeeld op basis van de specifieke configuratie van het Microsoft-webonderdeel.
- **Geen actie vereist** (groen): Het duurt  langer dan twee seconden voordat gegevens worden retourneren door een webonderdeel.

Als de **webonderdelen** van invloed zijn op de  laadtijd  van een pagina, wordt het resultaat weergegeven in de sectie Aandacht vereist of Verkoopkansen voor verbetering van de resultaten, klikt u op het resultaat om te zien welke webonderdelen langzaam worden geladen. Toekomstige updates van het hulpprogramma Paginadiagnose voor SharePoint kunnen updates van analyseregels bevatten, dus zorg ervoor dat u altijd de meest recente versie van het hulpprogramma hebt.

![Resultaten van hulpprogramma Paginadiagnose](../media/modern-portal-optimization/pagediag-web-part.png)

De beschikbare informatie in de resultaten omvat:

- **Gemaakt door** laat zien of het webonderdeel aangepast is of Microsoft OOTB.
- **Met de naam en** id worden identificerende gegevens weergegeven die u kunnen helpen het webonderdeel op de pagina te vinden.
- **Totaal** van de totale tijd die het webonderdeel nodig heeft om een module te laden, te initialiseren en weer te geven. Het is de totale relatieve tijd die door het webonderdeel wordt genomen om weer te geven op de pagina, van begin tot einde.
- **Bij het laden** van een module ziet u de tijd die nodig is om de javaScript- en CSS-bestanden te downloaden, te evalueren en te laden. Vervolgens wordt het Init-proces begonnen.
- **In dit artikel** wordt de tijd weergegeven voor het uitgesteld laden van webonderdelen die niet zichtbaar zijn in het hoofdgedeelte van de pagina. Er zijn bepaalde voorwaarden waarbij er te veel webonderdelen zijn om weer te geven en ze worden in de wachtrij geplaatst om weer te geven om de laadtijd van de pagina te minimaliseren.
- **Init** laat de tijd zien die het webonderdeel nodig heeft om de gegevens te initialiseren.
    Het is een asynchrone oproep en tijdin voeren de berekening van de tijd voor de on-Init-functie uit wanneer de geretourneerde belofte wordt opgelost.
- **In het** weergeven ziet u de tijd die nodig is om de gebruikersinterface (gebruikersinterface) weer te geven nadat de module is geladen en Init is voltooid.
    Het is de JavaScript-uitvoeringstijd om de DOM in het document (pagina) te plaatsen.
    Het weergeven van asynchrone resources, zoals afbeeldingen, kan extra tijd in beslag nemen.

Deze informatie wordt verstrekt om ontwerpers en ontwikkelaars te helpen bij het oplossen van problemen. Deze informatie moet u verstrekken aan uw ontwerp- en ontwikkelteam.

## <a name="remediate-web-part-performance-issues"></a>Problemen met de prestaties van webonderdeel herstellen

Volg de richtlijnen in deze sectie om prestatieproblemen te identificeren  en te verhelpen die van invloed zijn op de laadtijd van pagina's als webonderdelen in de webonderdelen.

Er zijn drie categorieën mogelijke oorzaken voor slechte prestaties van webonderdeel. Gebruik de onderstaande informatie om te bepalen welke problemen van toepassing zijn op uw scenario en deze te verhelpen.

- Scriptgrootte en afhankelijkheden van webonderdeel
  - Optimaliseer het initiële script om het hoofdlijnscenario alleen voor de _weergavemodus weer te geven._
  - Verplaats de minder frequente scenario's en bewerk moduscode (zoals het eigenschappenvenster) om segmenten te scheiden met behulp van de _instructie import()._
  - Controleer afhankelijkheden van de _package.jsin_ het bestand om alle doodscodes volledig te verwijderen. Verplaats alleen test-/buildafhankelijkheden naar devDependencies.
  - Het Office 365-CDN is vereist voor het optimaal statisch downloaden van statische bronnen. Openbare CDN-origins hebben de voorkeur boven _js-/css-bestanden._ Zie Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online voor meer informatie over het gebruik van het [Office 365-CDN.](use-microsoft-365-cdn-with-spo.md)
  - Gebruik frameworks zoals _React_ en _Fabric-importen_ die deel uitmaken van het SharePoint Framework (SPFX). Zie Overzicht van SharePoint Framework voor [meer informatie.](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview)
  - Zorg ervoor dat u de nieuwste versie van SharePoint Framework gebruikt en upgrade naar nieuwe versies zodra deze beschikbaar zijn.
- Gegevens ophalen/caching
  - Als het webonderdeel afhankelijk is van extra serveroproepen om gegevens op te halen voor weergave, zorgt u ervoor dat deze server-API's snel zijn en/of client caching (zoals het gebruik van _localStorage_ of _IndexedDB_ voor grotere sets) implementeren.
  - Als er meerdere oproepen nodig zijn om kritieke gegevens weer te geven, kunt u overwegen om een batch te maken op de server of op andere manieren om aanvragen samen tevoegen tot één oproep.
  - Als voor sommige gegevenselementen een tragere API is vereist, maar die niet essentieel zijn voor de eerste weergave, ontkoppelt u deze tot een afzonderlijke oproep die wordt uitgevoerd nadat essentiële gegevens zijn weergegeven.
  - Als meerdere onderdelen dezelfde gegevens gebruiken, gebruik dan een algemene gegevenslaag om dubbele aanroepen te voorkomen.
- Weergavetijd
  - Mediabronnen zoals afbeeldingen en video's moeten worden beperkt tot de limieten van de container, het apparaat en/of het netwerk om te voorkomen dat onnodige grote assets worden gedownload. Zie Het [Office 365 Content Delivery Network (CDN)](use-microsoft-365-cdn-with-spo.md)gebruiken met SharePoint Online voor meer informatie over inhoudsafhankelijkheden.
  - Voorkom API-aanroepen die zorgen voor nieuwe stroom, complexe CSS-regels of ingewikkelde animaties. Zie Het minimaliseren van de [browserreflow voor meer informatie.](https://developers.google.com/speed/docs/insights/browser-reflow)
  - Vermijd het gebruik van geketende, langlopende taken. Verbreed taken daarom in afzonderlijke wachtrijen. Zie [JavaScript-uitvoering optimaliseren voor meer informatie.](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)
  - Reserveer overeenkomstige ruimte voor asynchrone weergave van media of visuele elementen om te voorkomen dat frames worden overgeslagen en rug ruggoot (ook wel _jank genoemd)._
  - Als een bepaalde browser geen ondersteuning biedt voor een functie die wordt gebruikt in weergave, laadt u een polyfillfunctie of sluit u het uitvoeren van afhankelijke code uit. Als de functie niet kritiek is, moet u resources verwijderen, zoals gebeurtenis-handlers, om geheugenlekken te voorkomen.

Voordat u paginarevisies maakt om prestatieproblemen te verhelpen, noteert u de laadtijd van de pagina in de analyseresultaten. Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de nieuwe laadtijd van de pagina om te zien of er een verbetering is.

![Resultaten van laadtijd van pagina](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>De laadtijd van pagina's kan variëren afhankelijk van een aantal factoren, zoals de laadtijd van het netwerk, de tijd van de dag en andere tijdelijke voorwaarden. Test het laden van pagina's een paar keer voor en na het aanbrengen van wijzigingen om het gemiddelde van de resultaten te kunnen bekijken.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties van SharePoint Online afstemmen](tune-sharepoint-online-performance.md)

[De prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Netwerken voor contentlevering](content-delivery-networks.md)

[Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)
