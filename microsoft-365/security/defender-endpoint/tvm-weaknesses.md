---
title: 'Beveiligingslekken in mijn organisatie : bedreigings- en kwetsbaarheidsbeheer'
description: Hier vindt u de algemene beveiligingslekken en blootstellings-id (CVE) van zwakke punten in de software die in uw organisatie wordt uitgevoerd. Ontdekt door de ATP-beveiligings- en beveiligingsbeheerfunctie van Microsoft Defender.
keywords: mdatp threat & vulnerability management, threat and vulnerability management, mdatp tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b42e25c409ba19639e77e95fafc3d939514511ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060485"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a>Beveiligingslekken in mijn organisatie : bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Bedreigings- en kwetsbaarheidsbeheer gebruikt dezelfde signalen in de endpointbeveiliging van Defender voor eindpuntbeveiliging om beveiligingsproblemen te scannen en op te sporen.

Op **de pagina Zwakke** punten worden de beveiligingslekken vermeld waar uw apparaten aan worden blootgesteld door de CVE-id (Common Vulnerabilities and Exposures) te noteren. U kunt ook de ernst, cvss-classificatie (Common Vulnerability Scoring System), de prevalentie in uw organisatie, de bijbehorende inbreuk, bedreigingsinzichten en meer bekijken.

>[!NOTE]
>Als er geen officiële CVE-ID is toegewezen aan een beveiligingsprobleem, wordt de naam van de kwetsbaarheid toegewezen door bedreigings- en kwetsbaarheidsbeheer.

>[!TIP]
>Zie E-mailmeldingen voor kwetsbaarheid configureren in Microsoft Defender voor Eindpunt voor e-mailberichten over [nieuwe beveiligingsprobleemgebeurtenissen](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-weaknesses-page"></a>Naar de pagina Zwakke punten gaan

Toegang tot de pagina Zwakheden op een aantal verschillende manieren:

- Zwakke **punten selecteren** in het navigatiemenu bedreigings- en kwetsbaarheidsbeheer in het Microsoft [Defender-beveiligingscentrum](portal-overview.md)
- Algemene zoekactie

### <a name="navigation-menu"></a>Navigatiemenu

Ga naar het navigatiemenu bedreigings- en beveiligingsprobleembeheer en selecteer **Zwakke punten om** de lijst met CVE's te openen.

### <a name="vulnerabilities-in-global-search"></a>Beveiligingslekken in globale zoekopdrachten

1. Ga naar de vervolgkeuzelijst Voor algemene zoekopdrachten.
2. Selecteer **Kwetsbaarheid** en selecteer de CVE-id (Common Vulnerabilities and Exposures) die u zoekt en selecteer vervolgens het zoekpictogram. De **pagina Zwakheden** wordt geopend met de CVE-informatie die u zoekt.
![Algemeen zoekvak met de vervolgkeuzeoptie 'kwetsbaarheid' geselecteerd en een voorbeeld CVE.](images/tvm-vuln-globalsearch.png)
3. Selecteer de CVE om een flyout-paneel te openen met meer informatie, zoals de beschrijving van de kwetsbaarheid, details, bedreigingsinzichten en blootgestelde apparaten.

Als u de rest van de beveiligingslekken op de pagina **Zwakke** punten wilt zien, typt u CVE en selecteert u zoeken.

## <a name="weaknesses-overview"></a>Overzicht van zwakke punten

Herstel de beveiligingslekken in blootgestelde apparaten om het risico voor uw activa en organisatie te beperken. Als in **de kolom Blootgestelde** apparaten 0 wordt getoond, betekent dit dat u geen risico loopt.

![Zwakke landingspagina.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a>Inzichten in inbreuken en bedreigingen

Bekijk eventuele gerelateerde inbreuk- en bedreigingsinzichten in de kolom **Bedreiging** wanneer de pictogrammen rood zijn gekleurd.

 >[!NOTE]
 > Geef altijd prioriteit aan aanbevelingen die zijn gekoppeld aan lopende bedreigingen. Deze aanbevelingen zijn gemarkeerd met het pictogram Bedreigingsinzicht ![ Eenvoudige tekening van een rode bug.](images/tvm_bug_icon.png) en inzichtspictogram inbreuk ![ maken Eenvoudige tekening van een pijl die een doel ](images/tvm_alert_icon.png) raakt. .  

Het pictogram Inbreukinzichten wordt gemarkeerd als er een beveiligingsprobleem is gevonden in uw organisatie.
![Voorbeeld van een inbreukinzichten in tekst die kan worden weergegeven wanneer u de muisaanwijzer op het pictogram plaats. Deze geeft aan dat 'mogelijke actieve waarschuwing is gekoppeld aan deze aanbeveling.](images/tvm-breach-insights.png)

Het pictogram Bedreigingsinzichten wordt gemarkeerd als er gekoppelde exploits zijn in de kwetsbaarheid die in uw organisatie wordt gevonden. Wanneer u de muisaanwijzer boven het pictogram houdt, wordt weergegeven of de bedreiging deel uitmaakt van een exploitkit of verbonden is met specifieke geavanceerde permanente campagnes of activiteitsgroepen. Wanneer deze beschikbaar zijn, is er een koppeling naar een Threat Analytics-rapport met zero-day misbruiknieuws, openbaarmakingen of gerelateerde beveiligingsadviseurs.  

![Threat insights text that that could show up when hovering over icon. Deze bevat meerdere opsommingstekens en gekoppelde tekst.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a>Inzicht krijgen in kwetsbaarheid

Als u een CVE selecteert, wordt er een flyoutvenster geopend met meer informatie, zoals de beschrijving van de kwetsbaarheid, details, bedreigingsinzichten en blootgestelde apparaten.

- De categorie 'OS-functie' wordt weergegeven in relevante scenario's
- U kunt naar de bijbehorende beveiligingsaanbeveling voor elke CVE met een blootgesteld apparaat gaan

 ![Voorbeeld van een zwakke flyout.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a>Software die niet wordt ondersteund

CVE's voor software die momenteel niet wordt ondersteund door & kwetsbaarheidsbeheer is nog steeds aanwezig op de pagina Zwakke punten. Omdat de software niet wordt ondersteund, zijn er slechts beperkte gegevens beschikbaar.

Blootgestelde apparaatgegevens zijn niet beschikbaar voor CVE's met niet-ondersteunde software. Filter op niet-ondersteunde software door de optie 'Niet beschikbaar' te selecteren in de sectie 'Blootgestelde apparaten'.

 ![Blootgestelde apparaten filteren.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a>CvE-vermeldingen (Common Vulnerabilities and Exposures) weergeven op andere plaatsen

### <a name="top-vulnerable-software-in-the-dashboard"></a>Meest kwetsbare software in het dashboard

1. Ga naar het [dashboard bedreigings- en kwetsbaarheidsbeheer](tvm-dashboard-insights.md) en schuif omlaag naar de widget Top vulnerable **software.** U ziet het aantal beveiligingsproblemen in elke software, samen met bedreigingsgegevens en een weergave op hoog niveau van blootstelling aan apparaten in de tijd.

    ![Top kwetsbaar softwarekaart met vier kolommen: software, zwakke punten, bedreigingen, blootgestelde apparaten.](images/tvm-top-vulnerable-software500.png)

2. Selecteer de software die u wilt onderzoeken om naar een inzoompagina te gaan.
3. Selecteer het **tabblad Gevonden beveiligingslekken.**
4. Selecteer het beveiligingsprobleem dat u wilt onderzoeken voor meer informatie over beveiligingsdetails

    ![Overzicht van Windows Server 2019 inzoomen.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a>Beveiligingslekken ontdekken op de apparaatpagina

Informatie over gerelateerde zwakke punten weergeven op de apparaatpagina.

1. Ga naar de navigatiemenubalk van het Microsoft Defender-beveiligingscentrum en selecteer vervolgens het apparaatpictogram. De **lijstpagina Apparaten** wordt geopend.
2. Selecteer op **de pagina Apparatenlijst** de apparaatnaam die u wilt onderzoeken.

    ![Apparaatlijst met geselecteerd apparaat om te onderzoeken.](images/tvm_machinetoinvestigate.png)

3. De apparaatpagina wordt geopend met details en antwoordopties voor het apparaat dat u wilt onderzoeken.
4. Selecteer **Gevonden beveiligingslekken.**

    ![Apparaatpagina met details en antwoordopties.](images/tvm-discovered-vulnerabilities.png)

5. Selecteer het beveiligingsprobleem dat u wilt onderzoeken om een flyoutvenster te openen met de CVE-details, zoals: beschrijving van kwetsbaarheid, bedreigingsinzichten en detectielogica.

#### <a name="cve-detection-logic"></a>CVE-detectielogica

Net als bij de software wordt nu de detectielogica we toegepast op een apparaat om aan te geven dat het kwetsbaar is. De nieuwe sectie heet 'Detectielogica' (in een gedetecteerd beveiligingsprobleem op de apparaatpagina) en toont de detectielogica en -bron.

De categorie 'OS-functie' wordt ook weergegeven in relevante scenario's. Een CVE is alleen van invloed op apparaten met een kwetsbaar besturingssysteem als een specifiek besturingssysteemonderdeel is ingeschakeld. Stel dat Windows Server 2019 een kwetsbaarheid heeft in het DNS-onderdeel. Met deze nieuwe mogelijkheid voegen we deze CVE alleen toe aan de Windows Server 2019-apparaten met de DNS-mogelijkheid die is ingeschakeld in het besturingssysteem.

![Voorbeeld van detectielogica waarin de software wordt vermeld die is gedetecteerd op het apparaat en de KBs.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a>Onnauwkeurigheid van rapport

Meld een onwaar positief wanneer u vage, onnauwkeurige of onvolledige informatie ziet. U kunt ook rapporteren over beveiligingsaanbevelingen die al zijn gesaneerd.

1. Open de CVE op de pagina Zwakke punten.
2. Selecteer **Onnauwkeurigheid melden en** er wordt een flyoutvenster geopend.
3. Selecteer de onnauwkeurigheidscategorie in de vervolgkeuzelijst en vul uw e-mailadres en onnauwkeurigheidsdetails in.
4. Selecteer **Verzenden**. Uw feedback wordt onmiddellijk verzonden naar de experts voor bedreigings- en kwetsbaarheidsbeheer.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Beveiligingsaanbevelingen](tvm-security-recommendation.md)
- [Softwarevoorraad](tvm-software-inventory.md)
- [Dashboardinzichten](tvm-dashboard-insights.md)
- [De lijst Met Microsoft Defender voor eindpuntapparaten weergeven en organiseren](machines-view-overview.md)
