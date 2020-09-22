---
title: Apparaatprofiel in Microsoft 365 Security Portal
description: Risico's en belichtings niveaus voor een apparaat in uw organisatie weergeven. Analyseer oude en presenteer bedreigingen en Beveilig het apparaat met de nieuwste updates.
keywords: beveiliging, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Security Center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, apparaatklasse, apparaat-profiel, computer pagina, computerprofiel
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f6b79d3252084b298f94e01b18ebe3505f83b480
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196855"
---
# <a name="device-profile-page"></a>De pagina apparaat Profiel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Met de Microsoft 365-beveiligings Portal beschikt u over apparaatprofielen, zodat u snel de status en status van apparaten in uw netwerk kunt beoordelen.

> [!IMPORTANT]
> De pagina apparaat-profiel kan enigszins afwijken, afhankelijk van of het apparaat is ingeschreven in Microsoft Defender ATP, Azure ATP of beide.

Als het apparaat is ingeschreven in Microsoft Defender ATP, kunt u ook de profielpagina van het apparaat gebruiken om enkele veelvoorkomende beveiligingstaken uit te voeren.

## <a name="navigating-the-device-profile-page"></a>Navigeren in de profielpagina van het apparaat

De profielpagina is opgesplitst in diverse grote secties.

![Afbeelding van de pagina met het apparaatprofiel met (1) tabblad gebied (2) zijbalk en (3) gemarkeerde acties in rood](../../media/mtp-device-profile/hybrid-device-overall.png)

De zijbalk (1) geeft een overzicht van de algemene Details van het apparaat.

Het gebied met de hoofdinhoud (2) bevat tabbladen waarmee u kunt schakelen om verschillende soorten informatie over het apparaat weer te geven.

Als het apparaat is ingeschreven in Microsoft Defender ATP, ziet u ook een lijst met antwoord acties (3). Met antwoord acties kunt u veelvoorkomende taken uitvoeren met betrekking tot beveiliging.

## <a name="sidebar"></a>Protection

Naast het gebied met de hoofdinhoud van de profielpagina van het apparaat is de zijbalk.

![Afbeelding van het tabblad zijbalk voor apparaatprofiel](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

De zijbalk bevat de volledige naam en het belichtings niveau van het apparaat. Het biedt ook enkele belangrijke basisinformatie in kleine subsecties die kunnen worden geopend of gesloten.

* **Tags** : Microsoft Defender ATP, Azure ATP of aangepaste labels die zijn gekoppeld aan het apparaat. Tags van Azure ATP kunnen niet worden bewerkt.
* **Beveiligingsgegevens** -open incidenten en actieve meldingen. Op apparaten die zijn geregistreerd in Microsoft Defender ATP worden ook belichtings niveau en risiconiveau weergegeven.

> [!TIP]
> Belichtings niveau is afhankelijk van het aantal beveiligingsaanbevelingen, waarbij risiconiveau wordt berekend op basis van een aantal factoren, waaronder de typen en de ernst van actieve waarschuwingen.

* **Apparaatgegevens** : domein, besturingssysteem, tijdstempel van wanneer het apparaat voor het eerst werd gezien, IP-adressen, bronnen. Op apparaten die zijn geregistreerd in Microsoft Defender ATP wordt ook de status status weergegeven. In azure ATP ingeschreven apparaten wordt de naam van de SAM weergegeven en wordt een tijdstempel weergegeven voor wanneer het apparaat voor het eerst is gemaakt.
* **Netwerkactiviteit** : tijdstempels voor de eerste keer en de laatste keer dat het apparaat is gedetecteerd op het netwerk.
* **Active Directory** [-vlaggen,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [spn's](https://docs.microsoft.com/windows/win32/ad/service-principal-names)en groepslidmaatschappen (*alleen voor apparaten die zijn geregistreerd in azure ATP*).

## <a name="response-actions"></a>Antwoord acties

Antwoord acties bieden een snelle manier om bedreigingen te verdedigen en analyseren.

![Afbeelding van actiebalk voor Profiel van apparaat](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Antwoord acties](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) zijn alleen beschikbaar als het apparaat is ingeschreven in Microsoft Defender ATP.
> * Apparaten die zijn ingeschreven in Microsoft Defender ATP, kunnen verschillende nummers van antwoord acties weergeven, op basis van het OS en het versienummer van het apparaat.

Dit zijn de beschikbare acties op de profielpagina van het apparaat:

* **Tags beheren** : Hiermee worden aangepaste tags bijgewerkt die u hebt toegepast op dit apparaat.
* **Isoleer apparaat** : isoleert het apparaat in het netwerk van uw organisatie en houdt het verbonden met Microsoft Defender Advanced Threat Protection. U kunt ervoor kiezen Outlook, teams en Skype voor bedrijven uit te voeren wanneer het apparaat is geïsoleerd voor communicatiedoeleinden.
* **Onderhoudscentrum** : de status van ingediende acties weergeven. Alleen beschikbaar als er nog een actie is geselecteerd.
* **App-uitvoering beperken** : verhindert toepassingen die niet door Microsoft worden uitgevoerd.
* **Voer antivirus scan uit** : updates voor Windows Defender antivirus en direct een antivirus scan uitvoeren. Kies tussen snelle scan of volledige scan.
* **Onderzoek pakket verzamelen** : informatie over het apparaat verzamelen. Wanneer het onderzoek is voltooid, kunt u het downloaden.
* **Live antwoordsessie starten** : Laad een externe shell op het apparaat voor [uitgebreid beveiligings onderzoek](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).
* Automatisch **onderzoek initiëren** : Hiermee wordt de [bedreiging automatisch onderzocht en hersteld](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Hoewel u automatisch controles handmatig moet uitvoeren op deze pagina, activeren [bepaalde waarschuwings beleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) zichzelf automatisch onderzoek.
* **Onderhoudscentrum** : Hier vindt u informatie over eventuele antwoord acties die op dat moment actief zijn.

## <a name="tabs-section"></a>Sectietabbladen

Op de tabbladen apparaat-profiel kunt u een overzicht van beveiligings Details over het apparaat en de tabellen met een lijst met waarschuwingen wisselen.

Op apparaten die zijn ingeschreven in Microsoft Defender ATP worden ook tabbladen weergegeven die een tijdlijn betreffen, een lijst met beveiligingsaanbevelingen, een inventarisatie van de software, een lijst met ontdekte beveiligingslekken en ontbrekende KBs (beveiligingsupdates).

### <a name="overview-tab"></a>Tabblad Overzicht

Het standaardtabblad is **overzicht**. Dit biedt een kort overzicht van het belangrijkste beveiligings feit van het apparaat.

![Afbeelding van het tabblad Overzicht voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Hier ziet u een beknopt overzicht van de actieve waarschuwingen van het apparaat en van gebruikers die momenteel zijn aangemeld.

Als het apparaat is ingeschreven in Microsoft Defender ATP, wordt ook het risiconiveau van het apparaat en de beschikbare gegevens van beveiligings beoordelingen weergegeven. Met de beveiligings beoordelingen wordt het belichtings niveau van het apparaat beschreven, aanbevelingen van beveiligingsaanbevelingen en betroffen software en ontdekte beveiligingslekken.

### <a name="alerts-tab"></a>Tabblad waarschuwingen

Het tabblad **waarschuwingen** bevat een lijst met waarschuwingen die op het apparaat zijn geactiveerd, in zowel Azure ATP als Microsoft Defender ATP.

![Afbeelding van tabblad Waarschuwingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

U kunt het aantal weer te geven items aanpassen, evenals de kolommen die worden weergegeven voor elk item. Het standaardgedrag is een lijst van dertig items per pagina.

De kolommen op dit tabblad bevatten informatie over de ernst van de bedreiging waarmee de waarschuwing werd geactiveerd, evenals de status, het onderzoek en de persoon aan wie de waarschuwing is toegewezen.

De kolom *beïnvloede entiteiten* verwijst naar het apparaat (de entiteit) waarvan u momenteel kijkt, plus andere apparaten in het netwerk waarop dit van invloed is.

Wanneer u een item in deze lijst selecteert, wordt er een flyout met nog meer informatie over de geselecteerde waarschuwing geopend.

U kunt deze lijst filteren op Ernst, status of de persoon aan wie de waarschuwing is toegewezen.

### <a name="timeline-tab"></a>Het tabblad tijdlijn

Het tabblad **tijdlijn** bevat een interactieve, chronologische grafiek van alle gebeurtenissen die op het apparaat zijn geactiveerd. Als u het gemarkeerde gebied van de grafiek naar links of naar rechts verplaatst, kunt u gebeurtenissen over verschillende tijdsperioden weergeven. U kunt ook een aangepast datumbereik kiezen in de vervolgkeuzelijst tussen de interactieve grafiek en de lijst met gebeurtenissen.

Onder de grafiek bevindt zich een lijst met gebeurtenissen voor het geselecteerde datumbereik.

![Afbeelding van het tabblad tijdlijn voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

Het aantal weergegeven items en de kolommen in de lijst kunnen beide worden aangepast. De lijst standaardkolommen de gebeurtenistijd, actieve gebruiker, actietype, entiteiten (processen) en aanvullende informatie over de gebeurtenis.

Wanneer u een item in deze lijst selecteert, wordt er een flyout geopend met de grafiek gebeurtenis entiteiten, met daarin de bovenliggende en onderliggende processen van de gebeurtenis.

De lijst kan worden gefilterd op het specifieke type gebeurtenis; bijvoorbeeld register gebeurtenissen of slim schermgebeurtenissen.

U kunt de lijst ook exporteren naar een CSV-bestand als u het bestand wilt downloaden. Hoewel het bestand niet beperkt is van een aantal gebeurtenissen, kunt u kiezen uit zeven dagen wanneer u wilt exporteren.

### <a name="security-recommendations-tab"></a>Tabblad beveiligingsaanbevelingen

Het tabblad **beveiligingsaanbevelingen** bevat een lijst met acties die u kunt uitvoeren om het apparaat te beschermen. Wanneer u een item in deze lijst selecteert, wordt een flyout geopend waarin u instructies kunt krijgen voor het toepassen van de aanbeveling.

![Afbeelding van het tabblad beveiligingsaanbevelingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Net als met de vorige tabbladen, het aantal weergegeven items per pagina en de kolommen die zichtbaar zijn, kunnen worden aangepast.

De standaardweergave bevat kolommen die de beantwoorde zwakke punten, de bijbehorende bedreiging, de bijbehorende component of software beïnvloedt door de bedreiging, en nog veel meer. Items kunnen worden gefilterd op de status van de aanbeveling.

### <a name="software-inventory"></a>Software-inventarisatie

Het tabblad **software-inventaris** bevat een overzicht van de software die op het apparaat is geïnstalleerd.

![Afbeelding van het tabblad software-inventarisatie voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

In de standaardweergave wordt de softwareleverancier, het geïnstalleerde versienummer, het aantal bekende software-zwakke punten, bedreigings inzichten, productcode en tags weergegeven. Het aantal weer te geven items en welke kolommen worden weergegeven, kunnen beide worden aangepast.

Wanneer u een item uit deze lijst selecteert, wordt een flyout geopend met meer informatie over de geselecteerde software, en het pad en de tijdstempel voor de laatste keer dat de software is gevonden.

Deze lijst kan worden gefilterd op productcode.

### <a name="discovered-vulnerabilities-tab"></a>Tabblad ontdekte zwakke plekken

Het tabblad **ontdekte beveiligingslekken** bevat veelvoorkomende problemen met CVEs die van invloed kunnen zijn op het apparaat.

![Afbeelding van het tabblad ontdekte zwakke plekken voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

De standaardweergave toont de ernst van de CVE, de gang van de gangbare punten van het beveiligingslek (CVS), de software die is gerelateerd aan de CVE, wanneer de CVE werd gepubliceerd, wanneer de CVE voor het laatst is bijgewerkt en de Risico's die zijn gekoppeld aan de CVE.

Net als met de vorige tabbladen, zijn het aantal weer te geven items en welke kolommen zichtbaar zijn, kunnen worden aangepast.

Wanneer u een item in deze lijst selecteert, wordt een flyout geopend met de beschrijving van de CVE.

### <a name="missing-kbs"></a>Ontbrekende KBs

Het **ontbrekende tabblad KBs** bevat een lijst met alle Microsoft-updates die nog op het apparaat moeten worden toegepast. De vraag ' KBs ' in het [Knowledge Base-artikel bevat Knowledge Base-artikelen](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) die deze updates beschrijven. bijvoorbeeld [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Afbeelding van ontbrekend tabblad KBS voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

De standaardweergave bevat het bulletin dat de updates, de versie van het besturingssysteem, de desbetreffende producten bevat, CVEs verholpen, het KB-nummer en de tags.

Het aantal weergegeven items per pagina en welke kolommen worden weergegeven, kunnen worden aangepast.

Wanneer u een item selecteert, wordt een flyout geopend dat is gekoppeld aan de update.

## <a name="related-topics"></a>Verwante onderwerpen

* [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
* [Microsoft Threat Protection inschakelen](mtp-enable.md)
* [Entiteiten op apparaten onderzoeken met Live antwoord](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Geautomatiseerd onderzoek en antwoord (lucht) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
