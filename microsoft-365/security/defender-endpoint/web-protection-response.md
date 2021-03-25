---
title: Reageren op webbedreigingen in Microsoft Defender ATP
description: Reageren op waarschuwingen met betrekking tot schadelijke en ongewenste websites. Meer informatie over de manier waarop webbedreigingsbeveiliging eindgebruikers informeert via hun webbrowsers en Windows-meldingen
keywords: webbeveiliging, bescherming tegen webdreigingen, surfen op het web, waarschuwingen, reactie, beveiliging, phishing, malware, exploit, websites, netwerkbeveiliging, Edge, Internet Explorer, Chrome, Firefox, webbrowser, meldingen, eindgebruikers, Windows-meldingen, blokkeringspagina,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9f3873db4f85cec3f5f1a400dcfb7930c6a4faa
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187539"
---
# <a name="respond-to-web-threats"></a>Reageren op webbedreigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Met webbeveiliging in Microsoft Defender voor Eindpunt kunt u waarschuwingen met betrekking tot schadelijke websites en websites in uw aangepaste indicatorlijst efficiënt onderzoeken en beantwoorden.

## <a name="view-web-threat-alerts"></a>Waarschuwingen voor webbedreigingen weergeven
Microsoft Defender voor Eindpunt genereert de volgende [waarschuwingen voor](manage-alerts.md) schadelijke of verdachte webactiviteit:
- **Verdachte verbinding geblokkeerd door netwerkbeveiliging:** deze waarschuwing wordt gegenereerd wanneer een poging om toegang  te krijgen tot een schadelijke website of een website in uw aangepaste indicatorlijst wordt gestopt door netwerkbeveiliging in de *blokmodus*
- **Verdachte verbinding gedetecteerd** door netwerkbeveiliging: deze waarschuwing wordt gegenereerd wanneer een poging om toegang te krijgen tot een schadelijke website of een website in uw aangepaste indicatorlijst wordt gedetecteerd door netwerkbeveiliging *in* de modus Alleen controleren

Elke waarschuwing bevat de volgende informatie: 
- Apparaat dat heeft geprobeerd toegang te krijgen tot de geblokkeerde website
- Toepassing of programma dat wordt gebruikt om de webaanvraag te verzenden
- Schadelijke URL of URL in de lijst met aangepaste indicatoren
- Aanbevolen acties voor responders

![Afbeelding van een waarschuwing met betrekking tot beveiliging tegen webdreigingen](images/wtp-alert.png)

>[!Note]
>Als u het aantal waarschuwingen wilt beperken, worden detecties van webdreigingen voor hetzelfde domein op hetzelfde apparaat elke dag samengevoegd tot één waarschuwing. Er wordt slechts één waarschuwing gegenereerd en geteld in het [webbeveiligingsrapport.](web-protection-monitoring.md)

## <a name="inspect-website-details"></a>Websitedetails controleren
U kunt verder gaan door de URL of het domein van de website in de waarschuwing te selecteren. Hiermee opent u een pagina over die specifieke URL of domein met diverse informatie, waaronder:
- Apparaten die hebben geprobeerd toegang te krijgen tot de website
- Incidenten en waarschuwingen met betrekking tot de website
- Hoe vaak de website is gezien in gebeurtenissen in uw organisatie

    ![Afbeelding van de pagina met domein- of URL-entiteitdetails](images/wtp-website-details.png)

[Meer informatie over url- of domeinentiteitspagina's](investigate-domain.md)

## <a name="inspect-the-device"></a>Het apparaat controleren
U kunt ook het apparaat controleren dat heeft geprobeerd toegang te krijgen tot een geblokkeerde URL. Als u de naam van het apparaat op de waarschuwingspagina selecteert, wordt er een pagina geopend met uitgebreide informatie over het apparaat.

[Meer informatie over pagina's met apparaatentiteit](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>Webbrowser en Windows-meldingen voor eindgebruikers

Met webbeveiliging in Microsoft Defender voor Eindpunt kunnen uw eindgebruikers geen schadelijke of ongewenste websites bezoeken met Microsoft Edge of andere browsers. Omdat blokkeren wordt uitgevoerd door [netwerkbeveiliging,](network-protection.md)zien ze een algemene fout in de webbrowser. Ze zien ook een melding van Windows.

![Afbeelding van Microsoft Edge met een 403-fout en de ](images/wtp-browser-blocking-page.png)
 *Windows-meldingswebdreiging geblokkeerd op Microsoft Edge*

![Afbeelding van de webbrowser Chrome met een waarschuwing voor een beveiligde verbinding en de ](images/wtp-chrome-browser-blocking-page.png)
 *Windows-meldingswebdreiging geblokkeerd in Chrome*

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van webbeveiliging](web-protection-overview.md)
- [Filteren van webinhoud](web-content-filtering.md)
- [Beveiliging tegen bedreigingen op het web](web-threat-protection.md)
- [Webbeveiliging controleren](web-protection-monitoring.md)
