---
title: Apparaatprofiel in Microsoft 365-beveiligingsportal
description: Bekijk de risico's en blootstellingsniveaus voor een apparaat in uw organisatie. Analyseer eerdere en huidige bedreigingen en bescherm het apparaat met de nieuwste updates.
keywords: beveiliging, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, beveiligingscentrum, Microsoft Defender ATP, Office 365 ATP, Azure ATP, apparaatpagina, apparaatprofiel, computerpagina, machineprofiel
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929572"
---
# <a name="device-profile-page"></a>Apparaatprofielpagina

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


De Microsoft 365-beveiligingsportal biedt u apparaatprofielpagina's, zodat u snel de status en status van apparaten in uw netwerk kunt beoordelen.

> [!IMPORTANT]
> De profielpagina van het apparaat kan er iets anders uit zien, afhankelijk van of het apparaat is ingeschreven bij Microsoft Defender for Endpoint, Microsoft Defender for Identity of beide.

Als het apparaat is geregistreerd bij Microsoft Defender for Endpoint, kunt u ook de profielpagina van het apparaat gebruiken om enkele veelvoorkomende beveiligingstaken uit te voeren.

## <a name="navigating-the-device-profile-page"></a>Navigeren op de apparaatprofielpagina

De profielpagina is onderverdeeld in diverse algemene secties.

![Afbeelding van apparaatprofielpagina met (1) Tabbladgebied (2) Zijbalk en (3) Acties gemarkeerd met rood](../../media/mtp-device-profile/hybrid-device-overall.png)

De zijbalk (1) bevat basisgegevens over het apparaat.

Het gebied met de hoofdinhoud (2) bevat tabbladen waar u doorheen kunt schakelen om verschillende soorten informatie over het apparaat te bekijken.

Als het apparaat is geregistreerd bij Microsoft Defender for Endpoint, ziet u ook een lijst met antwoordacties (3). Met antwoordacties kunt u veelvoorkomende beveiligingstaken uitvoeren.

## <a name="sidebar"></a>Zijbalk

Naast het gebied met de hoofdinhoud van de profielpagina van het apparaat, staat de zijbalk.

![Afbeelding van tabblad Zijbalk voor apparaatprofiel](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

De zijbalk bevat de volledige naam en het blootstellingsniveau van het apparaat. Daarnaast vindt u hier belangrijke basisinformatie in kleine subsecties die u kunt openen of sluiten, zoals:

* **Tags:** Alle Microsoft Defender voor eindpunten, Microsoft Defender voor identiteiten of aangepaste tags die aan het apparaat zijn gekoppeld. Labels van Microsoft Defender voor identiteit kunnen niet worden bewerkt.
* **Beveiligingsgegevens:** open incidenten en actieve waarschuwingen. Apparaten die zijn ingeschreven in Microsoft Defender for Endpoint, geven ook het blootstellingsniveau en het risiconiveau weer.

> [!TIP]
> Blootstellingsniveau heeft betrekking op hoeveel het apparaat voldoet aan beveiligingsaanbevelingen, terwijl het risiconiveau wordt berekend op basis van een aantal factoren, waaronder de typen en ernst van actieve waarschuwingen.

* **Apparaatgegevens:** domein, besturingssysteem, tijdstempel voor wanneer het apparaat voor het eerst werd gezien, IP-adressen, bronnen. Apparaten die zijn ingeschreven in Microsoft Defender voor eindpunten geven ook de status van de status weer. Apparaten die zijn geregistreerd met Microsoft Defender for Identity, geven de SAM-naam en een tijdstempel weer voor wanneer het apparaat voor het eerst werd gemaakt.
* **Netwerkactiviteit:** tijdstempels voor de eerste keer en de laatste keer dat het apparaat in het netwerk is gezien.
* **Adreslijstgegevens** (alleen voor apparaten die zijn geregistreerd *voor Microsoft Defender voor identiteit)*- [UAC-vlaggen,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN's](https://docs.microsoft.com/windows/win32/ad/service-principal-names)en groepslidmaatschap.

## <a name="response-actions"></a>Antwoordacties

Reactieacties bieden een snelle manier om je te beschermen tegen bedreigingen en om bedreigingen te analyseren.

![Afbeelding van actiebalk voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Antwoordacties](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) zijn alleen beschikbaar als het apparaat is ingeschreven bij Microsoft Defender voor Eindpunt.
> * Apparaten die zijn ingeschreven in Microsoft Defender for Endpoint kunnen verschillende aantallen antwoordacties weergeven, op basis van het besturingssysteem en versienummer van het apparaat.

Acties die beschikbaar zijn op de profielpagina van het apparaat zijn:

* **Tags beheren:** updates van aangepaste tags die u op dit apparaat hebt toegepast.
* **Isoleert apparaat:** isoleert het apparaat van het netwerk van uw organisatie terwijl het verbonden blijft met Microsoft Defender voor eindpunt. U kunt Outlook, Teams en Skype voor Bedrijven laten uitvoeren terwijl het apparaat geïsoleerd is, voor communicatiedoeleinden.
* **Actiecentrum** - Bekijk de status van verzonden acties. Alleen beschikbaar als er al een andere actie is geselecteerd.
* **Het uitvoeren van apps** beperken: voorkomt dat toepassingen die niet door Microsoft zijn ondertekend, worden uitgevoerd.
* **Voer antivirusscan uit** - Windows Defender Antivirus-definities worden bijgewerkt en er wordt meteen een antivirusscan uitgevoerd. Kiezen tussen Snelle scan of Volledige scan.
* **Pakket voor onderzoek verzamelen:** verzamelt informatie over het apparaat. Wanneer het onderzoek is voltooid, kunt u het downloaden.
* **Live Response-sessie starten:** er wordt een externe shell op het apparaat geladen voor uitgebreide [beveiligingsonderzoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* **Automatisch onderzoek starten:** automatisch [bedreigingen onderzoeken en herstellen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Hoewel u vanaf deze pagina handmatig kunt activeren dat geautomatiseerde onderzoeken worden [uitgevoerd,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) worden met bepaalde waarschuwingsbeleidsregels automatische onderzoeken automatisch uitgevoerd.
* **Actiecentrum:** hier wordt informatie weergegeven over alle antwoordacties die momenteel worden uitgevoerd.

## <a name="tabs-section"></a>Sectie Tabbladen

Met de profieltabbladen van het apparaat kunt u door een overzicht van beveiligingsdetails over het apparaat schakelen en door tabellen met een lijst met waarschuwingen schakelen.

Apparaten die zijn geregistreerd in Microsoft Defender for Endpoint, bevatten ook tabbladen met een tijdlijn, een lijst met beveiligingsaanbevelingen, een softwarevoorraad, een lijst met gevonden beveiligingsproblemen en ontbrekende KB's (beveiligingsupdates).

### <a name="overview-tab"></a>Tabblad Overzicht

Het standaardtabblad is **Overzicht.** In dit artikel vindt u een beknopt overzicht van de belangrijkste beveiligingsrisico's van het apparaat.

![Afbeelding van tabblad Overzicht voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Hier kunt u een kort overzicht krijgen van de actieve waarschuwingen op het apparaat en eventuele gebruikers die op dat moment zijn aangemeld.

Als het apparaat is geregistreerd bij Microsoft Defender for Endpoint, ziet u ook het risiconiveau van het apparaat en alle beschikbare gegevens over beveiligingsbeoordelingen. In de beveiligingsbeoordelingen wordt het blootstellingsniveau van het apparaat beschreven, worden beveiligingsaanbevelingen gegeven, wordt de betrokken software vermeld en worden beveiligingsproblemen ontdekt.

### <a name="alerts-tab"></a>Tabblad Waarschuwingen

Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn verhoogd op het apparaat, van zowel Microsoft Defender for Identity als Microsoft Defender for Endpoint.

![Afbeelding van tabblad Waarschuwingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

U kunt het aantal weergegeven items aanpassen en voor elk item welke kolommen worden weergegeven. Het standaardgedrag is om dertig items per pagina weer te geven.

De kolommen op dit tabblad bevatten informatie over de ernst van de bedreiging die de waarschuwing heeft geactiveerd, evenals de status, de onderzoeksstatus en aan wie de waarschuwing is toegewezen.

De *kolom met beïnvloede entiteiten* verwijst naar het apparaat (de entiteit) waarvan u het profiel momenteel bekijkt, plus alle andere apparaten in uw netwerk die worden beïnvloed.

Als u een item in deze lijst selecteert, wordt een flyout geopend met nog meer informatie over de geselecteerde waarschuwing.

Deze lijst kan worden gefilterd op ernst, status of aan wie de waarschuwing is toegewezen.

### <a name="timeline-tab"></a>Tabblad Tijdlijn

Het **tabblad** Tijdlijn bevat een interactief chronologisch diagram van alle gebeurtenissen die op het apparaat zijn geplaatst. Door het gemarkeerde gebied van de grafiek naar links of rechts te verplaatsen, kunt u gebeurtenissen over verschillende perioden weergeven. U kunt ook een aangepast datumbereik kiezen in de vervolgkeuzelijst tussen de interactieve grafiek en de lijst met gebeurtenissen.

Onder de grafiek staat een lijst met gebeurtenissen voor het geselecteerde datumbereik.

![Afbeelding van tijdlijntabblad voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

Het aantal weergegeven items en de kolommen in de lijst kunnen beide worden aangepast. De standaardkolommen bevatten de gebeurtenistijd, de actieve gebruiker, het actietype, entiteiten (processen) en aanvullende informatie over de gebeurtenis.

Als u een item in deze lijst selecteert, wordt er een flyout geopend waarin een grafiek met gebeurtenis-entiteiten wordt weergegeven, waarin de bovenliggende en onderliggende processen voor de gebeurtenis worden weergegeven.

De lijst kan worden gefilterd op het specifieke type gebeurtenis; Bijvoorbeeld registergebeurtenissen of slimme schermgebeurtenissen.

De lijst kan ook worden geëxporteerd naar een CSV-bestand om te downloaden. Hoewel het bestand niet wordt beperkt door het aantal gebeurtenissen, is de maximumtijd die u kunt kiezen om te exporteren zeven dagen.

### <a name="security-recommendations-tab"></a>Tabblad Beveiligingsaanbevelingen

Op **het tabblad Beveiligingsaanbevelingen** worden de acties weergegeven die u kunt uitvoeren om het apparaat te beveiligen. Als u een item in deze lijst selecteert, wordt een flyout geopend waarin u instructies kunt krijgen voor het toepassen van de aanbeveling.

![Afbeelding van tabblad Met beveiligingsaanbevelingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Net als bij de vorige tabbladen, kan het aantal items dat per pagina wordt weergegeven en welke kolommen zichtbaar zijn, worden aangepast.

De standaardweergave bevat kolommen met een overzicht van de beveiligingsrisico's die worden aangepakt, de bijbehorende bedreiging, het gerelateerde onderdeel of de software die door de bedreiging wordt beïnvloed, en meer. Items kunnen worden gefilterd op de status van de aanbeveling.

### <a name="software-inventory"></a>Softwarevoorraad

Op **het tabblad Softwarevoorraad** wordt software vermeld die op het apparaat is geïnstalleerd.

![Afbeelding van tabblad Softwarevoorraad voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

In de standaardweergave ziet u de softwareleverancier, het geïnstalleerde versienummer, het aantal bekende software zwakke punten, bedreigingsinzichten, productcode en labels. Het aantal weergegeven items en welke kolommen kunnen beide worden aangepast.

Als u een item in deze lijst selecteert, wordt een flyout geopend met meer informatie over de geselecteerde software en het pad en de tijdstempel voor de laatste keer dat de software is gevonden.

Deze lijst kan worden gefilterd op productcode.

### <a name="discovered-vulnerabilities-tab"></a>Tabblad Voor ontdekte beveiligingsproblemen

Op **het tabblad Gevonden** beveiligingsproblemen worden veelvoorkomende beveiligingslekken en misbruiken (CVEs) vermeld die van invloed kunnen zijn op het apparaat.

![Afbeelding van het tabblad Met beveiligingsproblemen ontdekt voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

In de standaardweergave worden de ernst van het CVE, de CVS (Common Vulnerability Score), de software die is gerelateerd aan het CVE, vermeld wanneer de CVE is gepubliceerd, wanneer de CVE voor het laatst werd bijgewerkt, en de bedreigingen die aan het CVE zijn gekoppeld.

Net als bij de vorige tabbladen, kan het aantal weergegeven items en welke kolommen worden weergegeven, worden aangepast.

Als u een item in deze lijst selecteert, wordt een flyout geopend met een beschrijving van het CVE.

### <a name="missing-kbs"></a>Ontbrekende KB's

Op **het tabblad Ontbrekende KB's** worden alle Microsoft-updates vermeld die nog niet op het apparaat zijn toegepast. De KB's in kwestie zijn [Knowledge Base-artikelen](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) waarin deze updates worden beschreven. bijvoorbeeld [KB4551762.](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)

![Afbeelding van het ontbrekende tabblad Kbs voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

In de standaardweergave wordt het bulletin weergegeven met updates, versie van het besturingssysteem, betrokken producten, geadresseerde CV's, het KB-nummer en labels.

Het aantal weergegeven items per pagina en welke kolommen kunnen worden aangepast.

Als u een item selecteert, wordt een flyout geopend die is koppelingen naar de update.

## <a name="related-topics"></a>Verwante onderwerpen

* [Overzicht van Microsoft 365 Defender](microsoft-threat-protection.md)
* [Microsoft 365 Defender in te zetten](mtp-enable.md)
* [Entiteiten op apparaten onderzoeken met behulp van live-antwoorden](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Automatisch onderzoek en automatisch onderzoek (AIR) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
