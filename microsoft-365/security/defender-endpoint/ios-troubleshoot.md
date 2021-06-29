---
title: Problemen oplossen en antwoorden vinden op veelgestelde vragen over Microsoft Defender voor Eindpunt in iOS
description: Probleemoplossing en veelgestelde vragen - Microsoft Defender voor Eindpunt op iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, troubleshoot, faq, how to
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194971"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>Problemen oplossen en antwoorden vinden op veelgestelde vragen op Microsoft Defender voor eindpunt in iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

In dit onderwerp vindt u informatie over het oplossen van problemen die kunnen optreden wanneer u Microsoft Defender voor Eindpunt in iOS gebruikt.



> [!NOTE]
> Defender voor Eindpunt in iOS zou een VPN gebruiken om de functie Webbeveiliging te bieden. Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>Apps werken niet wanneer VPN is ingeschakeld
Er zijn enkele apps die niet meer werken wanneer er een actieve VPN wordt gedetecteerd. U kunt de VPN uitschakelen tijdens het gebruik van dergelijke apps. 

Defender voor Eindpunt in iOS bevat standaard de functie voor webbeveiliging en schakelt deze in. [Webbeveiliging helpt](web-protection-overview.md) om apparaten te beveiligen tegen webbedreigingen en gebruikers te beschermen tegen phishingaanvallen. Defender voor Endpoint in iOS gebruikt een VPN om deze beveiliging te bieden. Let op: dit is een lokale VPN en in tegenstelling tot traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.

Hoewel deze standaard is ingeschakeld, zijn er mogelijk bepaalde gevallen waarvoor u VPN moet uitschakelen. U wilt bijvoorbeeld bepaalde apps uitvoeren die niet werken wanneer een VPN is geconfigureerd. In dergelijke gevallen kunt u ervoor kiezen om VPN uit te schakelen vanuit de app op het apparaat door de onderstaande stappen uit te voeren:

1. Open op uw iOS-apparaat de **Instellingen** app, klik of tik **op Algemeen** en vervolgens **op VPN.**
1. Klik of tik op de knop 'i' voor Microsoft Defender voor Eindpunt.
1. Schakel de optie **Verbinding maken op aanvraag uit om** VPN uit te schakelen.

    > [!div class="mx-imgBorder"]
    > ![VPN config connect on demand](images/ios-vpn-config.png)

> [!NOTE]
> Webbeveiliging is niet beschikbaar wanneer VPN is uitgeschakeld. Als u Webbeveiliging opnieuw wilt inschakelen, opent u de Microsoft Defender voor Eindpunt-app op het apparaat en klikt of tikt u op **Start VPN**.

## <a name="co-existence-with-multiple-vpn-profiles"></a>Co-existence met meerdere VPN-profielen

Apple iOS biedt geen ondersteuning voor meerdere **VPN's** voor het hele apparaat om tegelijk actief te zijn. Hoewel er meerdere VPN-profielen op het apparaat kunnen bestaan, kan er slechts één VPN tegelijk actief zijn.

Microsoft Defender voor Endpoint VPN kan naast andere VPN's bestaan die zijn geconfigureerd *als per-app* of *'Persoonlijk'.*

## <a name="battery-consumption"></a>Batterijverbruik

In de Instellingen app wordt in iOS alleen het batterijgebruik van apps weergegeven die voor de gebruiker gedurende een bepaalde periode zichtbaar zijn. Het batterijgebruik van apps die op het scherm worden weergegeven, is alleen voor die tijdsduur en wordt berekend door iOS op basis van een groot aantal factoren, waaronder cpu- en netwerkgebruik. Microsoft Defender voor Eindpunt gebruikt een lokale/lus-back VPN op de achtergrond om het webverkeer te controleren op schadelijke websites of verbindingen. Netwerkpakketten van een app worden door deze controle heen en daardoor wordt het batterijgebruik van Microsoft Defender voor Eindpunt onjuist berekend. Het werkelijke batterijverbruik van Microsoft Defender voor Eindpunt is veel lager dan wat wordt weergegeven op de pagina Batterij Instellingen op het apparaat.

Gemiddeld is het batterijgebruik per dag door Microsoft Defender voor eindpunt op de achtergrond ongeveer **8,81%** van de totale batterij die die dag is verbruikt. Deze metrische waarde wordt gerapporteerd door Apple op basis van het werkelijke gebruik van Microsoft Defender voor Eindpunt op apparaten van eindgebruikers en kan om bovenstaande redenen ook worden verantwoord voor andere apps die netwerkactiviteit hebben.

De gebruikte VPN is ook een lokale VPN en in tegenstelling tot een traditioneel VPN wordt netwerkverkeer niet buiten het apparaat verzonden.

## <a name="data-usage"></a>Gegevensgebruik

Microsoft Defender for Endpoint gebruikt een lokale/lusback VPN om het webverkeer te controleren op schadelijke websites of verbindingen. Om deze reden kan het gegevensgebruik van Microsoft Defender voor eindpunten onjuist worden verantwoord. We hebben ook vastgesteld dat als het apparaat alleen op een mobiel netwerk is, het gegevensgebruik dat door de serviceprovider wordt gerapporteerd, zeer dicht bij het werkelijke verbruik ligt, terwijl apple in de Instellingen-app ongeveer 1,5x tot 2x aan werkelijke verbruikte gegevens laat zien.

We hebben vergelijkbare waarnemingen met andere VPN-services en hebben dit gemeld bij Apple.

Daarnaast is het essentieel dat Microsoft Defender voor Eindpunt up-to-date is met onze back-endservices om betere bescherming te bieden. We werken echter aan het optimaliseren van het gegevensgebruik door Microsoft Defender voor Eindpunt.

## <a name="report-unsafe-site"></a>Onveilige site rapporteren

Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen. Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om een website te rapporteren die een phishingsite kan zijn.

## <a name="malicious-site-detected"></a>Schadelijke site gedetecteerd

Microsoft Defender voor Eindpunt beschermt u tegen phishing of andere webaanvallen. Als er een schadelijke site wordt gedetecteerd, wordt de verbinding geblokkeerd en wordt er een waarschuwing verzonden naar de portal van het beveiligingscentrum van de organisatie. De waarschuwing bevat de domeinnaam van de verbinding, het externe IP-adres en de apparaatgegevens.

Daarnaast wordt er een melding weergegeven op het iOS-apparaat. Als u op de melding tikt, wordt het volgende scherm geopend voor de gebruiker om de details te bekijken.

> [!div class="mx-imgBorder"]
> ![Afbeelding van site gerapporteerd als onveilige melding](images/ios-phish-alert.png)

## <a name="data-and-privacy"></a>Gegevens en privacy

Zie Privacygegevens - Microsoft [Defender voor eindpunt in iOS](ios-privacy.md)voor meer informatie over verzamelde gegevens en privacy.

