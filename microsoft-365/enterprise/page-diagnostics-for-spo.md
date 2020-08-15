---
title: Het hulpprogramma pagina diagnose voor SharePoint Online gebruiken
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: Met het hulpprogramma pagina diagnose voor SharePoint Online kunt u de moderne portal van SharePoint Online en de klassieke publicatiepagina's analyseren met een vooraf gedefinieerde set prestatiecriteria.
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695735"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Het hulpprogramma pagina diagnose voor SharePoint gebruiken

In dit artikel wordt uitgelegd hoe u het **hulpprogramma pagina diagnose voor SharePoint** online kunt gebruiken voor het analyseren van de modern-en klassieke sitepagina's van SharePoint Online met een vooraf gedefinieerde set prestatiecriteria.

Het hulpprogramma pagina diagnose voor SharePoint kan worden geïnstalleerd voor:

- **Microsoft Edge** [(Edge extension)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(chroom extensie)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>Versie **2.0.0** en hoger biedt ondersteuning voor moderne pagina's, naast de klassieke sitepagina's. Als u niet zeker weet welke versie van het hulpprogramma u gebruikt, kunt u de koppeling **info** of het beletselteken (...) selecteren om uw versie te verifiëren. **Altijd bijwerken naar de meest recente versie** wanneer u de functie gebruikt.

Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren. Dit hulpprogramma werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Met het hulpprogramma wordt een rapport gegenereerd voor elke geanalyseerde pagina op basis van de manier waarop de pagina wordt uitgevoerd met een vooraf gedefinieerde set regels en gedetailleerde informatie wordt weergegeven wanneer resultaten van een test buiten de waarde van de basislijn vallen. Beheerders van SharePoint Online kunnen het hulpprogramma gebruiken voor het oplossen van prestatieproblemen en om ervoor te zorgen dat nieuwe pagina's worden geoptimaliseerd voordat ze worden gepubliceerd.

Het hulpprogramma voor het automatisch toevoegen van pagina's is bedoeld voor het analyseren van alleen SharePoint-sitepagina's, niet over systeem pagina's zoals *AllItems. aspx* of *SharePoint. aspx*. Als u het hulpprogramma probeert uit te voeren op een systeempagina of een andere niet-sitepagina, wordt een foutbericht weergegeven met de mededeling dat het programma niet kan worden uitgevoerd voor dit type pagina.

![Moet worden uitgevoerd op een SharePoint-pagina](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Dit is geen fout in het hulpprogramma omdat er geen waarde is in de beoordeling van bibliotheken of systeem pagina's. Ga naar de pagina van een SharePoint-site om het hulpmiddel te gebruiken. Als deze fout optreedt op een SharePoint-pagina, raadpleegt u de basispagina om ervoor te zorgen dat de metatags van SharePoint niet zijn verwijderd.

Als u feedback wilt geven over het hulpmiddel, selecteert u het beletselteken in de rechterbovenhoek van het hulpmiddel en selecteert u [feedback geven](https://go.microsoft.com/fwlink/?linkid=874109).

![Feedback geven](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Het hulpprogramma pagina diagnose voor SharePoint installeren

De installatieprocedure in deze sectie is geschikt voor de browsers Chrome en Microsoft Edge.

> [!IMPORTANT]
> Microsoft leest geen gegevens of pagina-inhoud die wordt geanalyseerd via het hulpprogramma pagina diagnose voor SharePoint, en we vastleggen geen persoonlijke gegevens, website of downloadinformatie. De enige identificeerbare informatie die bij Microsoft is aangemeld, is de naam van de Tenant, het aantal regels dat mislukt en de datum en tijd waarop het hulpprogramma is uitgevoerd. Deze informatie wordt door Microsoft gebruikt om beter inzicht te krijgen in de moderne Portal en trends van de publicatie van sites en de meest voorkomende prestatieproblemen.

1. Installeer het hulpprogramma voor het maken van diagnostische gegevens voor SharePoint voor **Microsoft Edge** [(Edge extension)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) of **Chrome** [(Chrome)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi). Kijk op de paginabeschrijving van de Store naar het privacybeleid van de gebruiker. Wanneer u het hulpprogramma toevoegt aan uw browser, ziet u de volgende kennisgeving.

    ![Machtigingen voor extensies](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Deze kennisgeving is bedoeld voor omdat een pagina inhoud kan bevatten van locaties buiten SharePoint, afhankelijk van de webonderdelen en aanpassingen op de pagina. Dit houdt in dat het hulpmiddel de verzoeken en antwoorden leest wanneer op de startknop is geklikt en alleen voor het actieve SharePoint-tabblad waarop het hulpprogramma wordt uitgevoerd. Deze informatie wordt lokaal vastgelegd door de webbrowser en is voor u beschikbaar via de knop **exporteren naar JSON** of **exporteren naar har** op het tabblad _netwerktracering_ van het hulp **middel.** (Het programma houdt rekening met het door u [toegankelijke micro](https://go.microsoft.com/fwlink/p/?linkid=857875)Soft-privacybeleid.)

    De machtiging _uw downloads beheren_ betreft de werking van de **export naar JSON** -functionaliteit van het hulpmiddel. Volg de eigen richtlijnen van uw bedrijf voordat u het JSON-bestand deelt buiten uw organisatie, aangezien het resultaat Url's bevat en dat kan worden geclassificeerd als PII (persoonlijk identificeerbare informatie).
1. Als u het hulpprogramma wilt gebruiken in de Incognito of de InPrivate-modus, volgt u de procedure voor uw browser:
    1. Ga in Microsoft Edge naar **extensies** of typ _Edge://Extensions_ in de URL-balk en selecteer **Details** voor de extensie. Selecteer in de instellingen voor toestel het selectievakje **toestaan in InPrivate**.
    1. Ga in Chrome naar **extensies** of typ _Chrome://Extensions_ in de URL-balk en selecteer **Details** voor de extensie. Selecteer in de instellingen voor extensies de schuifregelaar voor **toestaan in incognito**.
1. Ga naar de pagina van de SharePoint-site in SharePoint Online die u wilt beoordelen. Voor het ' uitstellen ' van items op pagina's is toegestaan. dat betekent dat het hulpmiddel niet automatisch wordt gestopt (dit is door ontwerp geschikt voor het laden van de pagina's). Als u wilt stoppen met verzamelen, selecteert u **stoppen**. Zorg ervoor dat de geladen pagina is voltooid voordat u de gegevensverzameling stopt of dat u alleen een gedeeltelijke tracering gaat vastleggen.
1. Klik op de werkbalk van de uitbreiding ![Pagina diagnose voor SharePoint-logo](../media/page-diagnostics-for-spo/pagediag-icon32.png) Als u het hulpprogramma wilt laden, wordt dit weergegeven in de volgende pop-upvenster met extensies:

    ![Pop-upmenu met hulpmiddelen voor pagina's](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Selecteer **starten** om te beginnen met het verzamelen van gegevens voor analyse.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>Wat u ziet in het hulpprogramma pagina diagnose voor SharePoint

1. Klik op de drie puntjes (...) in de rechterbovenhoek van het hulpmiddel om de volgende koppelingen te vinden:
   1. De koppeling **extra resources** bevat algemene richtlijnen en Details over het hulpmiddel, waaronder een koppeling terug naar dit artikel.
   1. De koppeling **feedback geven** biedt een koppeling naar de Voice site van de _SharePoint-sites en-samenwerkings gebruikers_ .
   1. De koppeling **info** bevat de momenteel geïnstalleerde versie van het hulpprogramma en een directe koppeling naar het programma van derden.  
1. De **correlatie-id, SPRequestDuration, SPIISLatency**, **pagina laadtijd**en **URL** -Details zijn informatie en kunnen voor enkele redenen worden gebruikt.

    ![Details over diagnostische gegevens voor pagina's](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID** is een belangrijk element wanneer u werkt met Microsoft-ondersteuning, zodat ze extra diagnostische gegevens voor de specifieke pagina kunnen verzamelen.
   - **SPRequestDuration** is de tijd die voor SharePoint wordt gebruikt om de pagina te verwerken. Met structurele navigatie, grote afbeeldingen en vele API-gesprekken kunnen alle bijdragen langer duren.
   - **SPIISLatency** is de tijd in milliseconden voor SharePoint Online, met het laden van de pagina. Met deze waarde wordt het tijdstip niet opgenomen dat de webtoepassing heeft gereageerd.
   - **Laadtijd voor pagina's** is de totale tijd die door de pagina wordt weergegeven vanaf het moment dat de aanvraag is ontvangen en weergegeven in de browser. Deze waarde is van invloed op diverse factoren, waaronder netwerklatentie, de prestaties van de computer en de tijd die het duurt voor de browser om de pagina te laden.
   - De **pagina-URL** (Uniform Resource Locator) is het webadres van de huidige pagina.

1. Op het tabblad [**diagnostische tests**](#how-to-use-the-diagnostic-tests-tab) worden de resultaten van de analyse in drie categorieën weergegeven. U hebt **geen actie nodig**, verbeteringen van de **verbeteringen** en de **aandacht vereist**. Elk testresultaat wordt weergegeven door een item in een van deze categorieën, zoals beschreven in de volgende tabel:

    |Categorie  |Kleur  |Beschrijving  |
    |---------|---------|---------|
    |**Aandacht vereist** |RGB |Test resultaat valt buiten de waarde van de basislijn en is van invloed op de prestaties van pagina's. Volg de instructies voor herstel.|
    |**Verbeterings mogelijkheden** |Gemarkeerd |Test resultaat valt buiten de waarde van de basislijn en kan bijdragen aan de prestatieproblemen. U kunt criteria van de test toepassen.|
    |**Geen actie vereist** |Groene |Testresultaat valt binnen de waarde van de basislijn van de test.|

    ![Diagnostische gegevens voor pagina's](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. Het tabblad [**netwerktracering**](#how-to-use-the-network-trace-tab) bevat details over het maken van verzoeken en antwoorden voor pagina's.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Het tabblad diagnostische tests gebruiken

Wanneer u een pagina met een moderne SharePoint-Portal pagina of een klassieke publicatiesite controleert met behulp van het hulpprogramma pagina diagnose voor SharePoint, worden de resultaten geanalyseerd met behulp van vooraf gedefinieerde regels waarmee de resultaten worden vergeleken met basislijnwaarden en worden weergegeven op het tabblad **diagnostische tests** . voor regels voor bepaalde tests worden verschillende waarden voor de prestaties gebruikt, afhankelijk van de twee.

Test resultaten die worden weergegeven in de categorie verduidelijkings **mogelijkheden** of aandacht voor de **vereiste** categorieën geven gebieden aan die moeten worden gecontroleerd tegen aanbevolen procedures, en kunnen worden geselecteerd om aanvullende informatie over het resultaat weer te geven. Details voor elk item bevat een koppeling voor meer _informatie_ waarmee u rechtstreeks naar de juiste richtlijnen met betrekking tot de test gaat. Test resultaten die worden weergegeven in de **vereiste categorie geen actie** aangeven de naleving met de relevante regel aangeven en geen extra details weergeven wanneer deze optie is geselecteerd.

Met de gegevens op het tabblad diagnostische tests wordt u niet gewaarschuwd dat u pagina's ontwerpt, maar u kunt ook factoren markeren die van invloed kunnen zijn op de prestaties van pagina's. De werking van bepaalde pagina's en aanpassingen van pagina's hebben een onvermijdbare impact op de pagina-prestaties en moet worden gecontroleerd op mogelijke herstel of afkeuring van de pagina als de invloed hiervan is.

Met rode of gele resultaten kunnen ook webonderdelen worden aangegeven die gegevens te vaak vernieuwen. Bedrijfsnieuws wordt bijvoorbeeld niet elk seconde bijgewerkt, maar aangepaste webonderdelen worden vaak gebouwd om het laatste nieuws van elke seconde te verkrijgen in plaats van de functies voor het opslaan van de algehele gebruikerservaring. Houd er rekening mee wanneer u webonderdelen op een pagina opneemt, wat vaak eenvoudige manieren zijn om de gevolgen van de prestaties te verlagen door de waarde van de beschikbare parameters te beoordelen om te zorgen dat deze correct wordt ingesteld voor het beoogde doel.

>[!NOTE]
>Klassieke team sites waarvan de publicatiefunctie niet is ingeschakeld, kunnen gebruikmaken van Cdn's. Wanneer u het hulpprogramma op deze sites uitvoert, wordt de CDN-test naar verwachting mislukt en kan deze worden genegeerd, maar alle resterende tests zijn van toepassing. De extra functionaliteit van de SharePoint-publicatiefunctie kan het laden van pagina's vergroten, zodat het niet hoeft te worden ingeschakeld om de CDN-functionaliteit toe te staan.

>[!IMPORTANT]
>Test regels worden regelmatig toegevoegd en bijgewerkt, zodat u de nieuwste versie van het hulpmiddel kunt raadplegen voor informatie over de huidige regels en specifieke informatie die in testresultaten wordt opgenomen. U kunt de versie controleren door uw extensies te beheren en de extensie zal u adviseren of er een update beschikbaar is.

## <a name="how-to-use-the-network-trace-tab"></a>Het tabblad netwerktracering gebruiken

Het tabblad **netwerktracering** bevat gedetailleerde informatie over beide aanvragen om de pagina samen te stellen en de antwoorden te ontvangen van SharePoint.

1. **Let op het aantal laadtijden voor items met een rode vlag**. Elke aanvraag en reactie heeft een kleurcode, zodat de invloed op de prestaties van de algemene pagina wordt aangegeven met de volgende latentie gegevens:
    - Groen: \< 500ms
    - Geel: 500-1000ms
    - Rood: \> 1000ms

    ![Netwerk traceren](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    In de afbeelding die hierboven wordt weergegeven, is het rode item betrekking op de standaardpagina. De weergave wordt altijd rood weergegeven, tenzij de pagina wordt geladen in \< 1000ms (minder dan 1 seconde).

2. **Laadtijden van items testen**. In sommige gevallen wordt er geen tijd of kleur indicator weergegeven omdat de items al zijn opgeslagen in de cache van de browser. Als u dit correct wilt testen, opent u de pagina, schakelt u de cache van de browser uit en klikt u vervolgens op **Start** als die een ' koud ' pagina laadt, en moet de eerste pagina wordt geladen. Vervolgens wordt dit vergeleken met de ' warme ' pagina laden, zodat u kunt bepalen welke items in de cache op de pagina worden opgeslagen.

3. **Deel relevante gegevens met anderen die u kunnen helpen om problemen te onderzoeken**. Als u de details of informatie in het hulpprogramma wilt delen met uw ontwikkelaars of een technische ondersteunings persoon, klikt u op **exporteren naar JSON** (zoals weergegeven in de bovenstaande afbeelding). U kunt de resultaten ook downloaden met een JSON-bestands viewer.

    Als u ervoor hebt gekozen om de functie *exporteren in te schakelen naar har* , wordt het export type weergegeven als **export naar har**.

    ![Netwerk traceren](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> Deze resultaten bevatten Url's en deze kunnen worden geclassificeerd als PII (persoonlijk identificeerbare informatie). Zorg ervoor dat u de richtlijnen van de organisatie hebt gevolgd voordat u deze informatie distribueert.

## <a name="engaging-with-microsoft-support"></a>Oefenen met Microsoft ondersteuning

We hebben een **functie voor ondersteuning van Microsoft-ondersteuningsniveau** opgenomen die alleen mag worden gebruikt wanneer ze rechtstreeks aan een ondersteunings zaak werken. Wanneer u deze functie gebruikt, kunt u niet alleen gebruikmaken van de ondersteuning van het team en kunt u de pagina aanzienlijk trager maken. Er is geen extra informatie wanneer u deze functie gebruikt in het hulpmiddel als de aanvullende informatie wordt toegevoegd aan de logboekregistratie in de service.

Er is geen wijziging zichtbaar, behalve dat u een melding krijgt dat u deze hebt ingeschakeld en dat de pagina prestaties aanzienlijk worden verminderd door 2-3 wanneer dit is ingeschakeld. Het is alleen van toepassing op de desbetreffende pagina en de actieve sessie. Daarom dient dit spaarzaam te worden gebruikt, maar alleen wanneer de ondersteuning actief is.

### <a name="to-enable-the-microsoft-support-level-feature"></a>De functie Microsoft-ondersteuningsniveau inschakelen

1. Open het hulpprogramma pagina diagnose voor SharePoint.
2. Druk op het toetsenbord op **ALT + SHIFT + L**. Hiermee wordt het selectievakje **ondersteuning voor logboekregistratie inschakelen** weergegeven.
3. Schakel het selectievakje in en klik op **starten** om de pagina opnieuw te laden en uitgebreide logboekregistratie te genereren.

    ![Ondersteuningsoptie ingeschakeld](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    Let op de CorrelationID (weergegeven aan de bovenkant van de tool) en geef deze aan uw ondersteuningsmedewerker zodat ze aanvullende informatie over de diagnostische sessie kunnen verzamelen.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties van SharePoint Online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Netwerken voor content levering](content-delivery-networks.md)

[Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)
