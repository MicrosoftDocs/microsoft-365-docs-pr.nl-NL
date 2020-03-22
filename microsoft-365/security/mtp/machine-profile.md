---
title: Machineprofiel in Microsoft 365-beveiligingsportal
description: Bekijk risico- en belichtingsniveaus voor een apparaat in uw organisatie. Analyseer bedreigingen uit het verleden en heden en bescherm de machine met de nieuwste updates.
keywords: beveiliging, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, security center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, machinepagina, machinelijst, machineprofiel
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
ms.openlocfilehash: 1dfb567c8e6b8573397d503ae27c0aceb447c916
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895461"
---
# <a name="machine-profile-page"></a>Pagina machineprofiel

De Microsoft 365-beveiligingsportal biedt u machineprofielpagina's, zodat u de status en status van apparaten in uw netwerk beoordelen. Elke machineprofielpagina bevat een schat aan informatie over het apparaat.

U uitgebreide informatie bekijken over welke software het wordt uitgevoerd, eventuele beveiligingsgebeurtenissen of waarschuwingen uit het verleden en het heden, en links vinden naar relevante softwarepatches.

U het machineprofiel ook gebruiken om veelvoorkomende beveiligingsgerelateerde taken uit te voeren en snel basisgegevens over het apparaat te bekijken.

## <a name="navigating-the-machine-profile-page"></a>Navigeren op de pagina Machineprofiel

De pagina met het machineprofiel is opgesplitst in drie secties.

![Afbeelding van de pagina met machineprofiel met (1) Tabgebied (2) Zijbalk en (3) Acties gemarkeerd in rood](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

Het hoofdinhoudsgebied (1) bevat zeven tabbladen die u inschakelen om verschillende soorten informatie over de machine weer te geven.

De zijbalk (2) bevat basisgegevens over de machine.

Er zijn ook responsacties beschikbaar in een koptekst (3) vóór de zijbalk en de hoofdinhoudssecties. U de acties in deze koptekst gebruiken om algemene beveiligingstaken uit te voeren.

## <a name="tabs-section"></a>Sectie Tabbladen

Met de tabbladen Machine-profiel u schakelen via een overzicht van beveiligingsgegevens over de machine en tabellen met een lijst met waarschuwingen, een tijdlijn, een lijst met beveiligingsaanbevelingen, een software-inventaris, een lijst met ontdekte kwetsbaarheden en ontbrekende KBs (beveiligingsupdates).

### <a name="overview-tab"></a>Tabblad Overzicht

Het standaardtabblad is **Overzicht**. Het biedt een snelle blik op het belangrijkste beveiligingsfeit over het apparaat.

![Afbeelding van het tabblad Overzicht voor Machineprofiel](../../media/mtp-machine-profile/overview.png)

Hier vindt u een grafiek van het risiconiveau en de actieve waarschuwingen van het apparaat, alle momenteel aangemelde gebruikers, een korte lijst met de meeste en minst frequente gebruikers en beveiligingsbeoordelingen die het blootstellingsniveau van het apparaat, beveiligingsaanbevelingen, beïnvloede software en ontdekte kwetsbaarheden.

### <a name="alerts-tab"></a>Tabblad Waarschuwingen

Het tabblad **Waarschuwingen** bevat een lijst met waarschuwingen die op het apparaat zijn gerapporteerd.

![Afbeelding van het tabblad Waarschuwingen voor Machineprofiel](../../media/mtp-machine-profile/alerts.png)

U het aantal weergegeven items aanpassen en welke kolommen voor elk item worden weergegeven. Het standaardgedrag is om 30 items per pagina weer te geven en 11 kolommen te hebben ingeschakeld om weer te geven.

De kolommen op dit tabblad bevatten informatie over de ernst van de bedreiging die de waarschuwing heeft geactiveerd, evenals de status, de onderzoeksstatus en aan wie iemand de waarschuwing is toegewezen.

De *kolom van de getroffen entiteiten* verwijst naar de machine (entiteit) wiens profiel u momenteel bekijkt, plus alle andere machines in uw netwerk die worden beïnvloed.

Als u een item uit deze lijst selecteert, wordt een koppeling naar de geselecteerde waarschuwing geopend.

Deze lijst kan worden gefilterd op ernst, status of cessionaris.

### <a name="timeline-tab"></a>Tabblad Tijdlijn

Het tabblad **Tijdlijn** bevat een interactieve, chronologische grafiek met gebeurtenissen die op het apparaat worden weergegeven. Door het gemarkeerde gebied van de grafiek te verplaatsen, u gebeurtenissen over verschillende tijdsperioden bekijken. U ook een aangepast bereik van datums intypen.

Onder de grafiek vindt u een lijst met gebeurtenissen voor het geselecteerde bereik van datums.

![Afbeelding van het tabblad tijdlijn voor Machineprofiel](../../media/mtp-machine-profile/timeline.png)

Het aantal weergegeven items en de kolommen in de lijst kunnen beide worden aangepast. De standaardkolommen bevatten de gebeurtenistijd, actieve gebruiker, actietype, entiteiten (processen) en aanvullende informatie over de gebeurtenis.

Als u een item in de lijst selecteert, wordt een flyout geopend met een grafiek met gebeurtenisentiteiten, met de bovenliggende en onderliggende processen die de gebeurtenis hebben geactiveerd.

Deze lijst kan worden gefilterd op het specifieke soort gebeurtenis; bijvoorbeeld Registergebeurtenissen of Smart Screen-gebeurtenissen.

### <a name="security-recommendations-tab"></a>Tabblad Beveiligingsaanbevelingen

Op het tabblad **Beveiligingsaanbevelingen** staan acties die u uitvoeren om het apparaat te beschermen. Als u een item in deze lijst selecteert, opent u een flyout waar u instructies krijgen over het toepassen van de aanbeveling.

![Afbeelding van het tabblad Beveiligingsaanbevelingen voor Machineprofiel](../../media/mtp-machine-profile/security-recs.png)

Net als bij de vorige tabbladen kan het aantal items dat per pagina wordt weergegeven en welke kolommen zichtbaar zijn, worden aangepast.

De standaardweergave bevat kolommen waarin de beveiligingszwakke punten worden beschreven die zijn verholpen, de bijbehorende bedreiging, de bijbehorende component of software die door de bedreiging wordt beïnvloed, en meer. Items kunnen worden gefilterd op de status van de aanbeveling.

### <a name="software-inventory"></a>Software-inventaris

Op het tabblad **Softwareinventaris** vindt u software die op het apparaat is geïnstalleerd.

![Afbeelding van het tabblad softwareinventaris voor Machineprofiel](../../media/mtp-machine-profile/software-inventory.png)

De standaardweergave toont de softwareleverancier, het geïnstalleerde versienummer, het aantal bekende softwarezwakke punten, bedreigingsinzichten, productcode en tags. Het aantal weergegeven items en welke kolommen worden weergegeven, kan beide worden aangepast.

Als u een item uit deze lijst selecteert, wordt een flyout geopend met meer details over de geselecteerde software, evenals het pad en de tijdstempel voor de laatste keer dat de software is gevonden.

Deze lijst kan worden gefilterd op productcode.

### <a name="discovered-vulnerabilities-tab"></a>Tabblad Ontdekte kwetsbaarheden

Op het tabblad **Ontdekte kwetsbaarheden** worden alle algemene kwetsbaarheden en exploits (CvEs) weergegeven die van invloed kunnen zijn op het apparaat.

![Afbeelding van het tabblad ontdekte kwetsbaarheden voor machineprofiel](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

De standaardweergave geeft een overzicht van de ernst van de CVE, de Common Vulnerability Score (CVS), de software met betrekking tot de CVE, toen de CVE werd gepubliceerd, toen de CVE voor het laatst werd bijgewerkt, en bedreigingen in verband met de CVE.

Net als bij de vorige tabbladen kan het aantal weergegeven items en welke kolommen zichtbaar zijn, worden aangepast.

Als u een item uit deze lijst selecteert, wordt een flyout geopend waarin de CVE wordt beschreven.

### <a name="missing-kbs"></a>Ontbrekende KBs

Op het tabblad **Ontbrekende KBs** worden alle Microsoft-updates weergegeven die nog niet op de machine moeten worden toegepast. De "KBs" in kwestie zijn [Knowledge Base artikelen](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) die deze updates beschrijven; [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Afbeelding van ontbrekend kbs-tabblad voor Machineprofiel](../../media/mtp-machine-profile/missing-kbs.PNG)

In de standaardweergave wordt het bulletin weergegeven met de updates, de os-versie, de betrokken producten, aco's, het KB-nummer en de tags.

Het aantal items dat per pagina wordt weergegeven en welke kolommen worden weergegeven, kan worden aangepast.

Als u een item selecteert, wordt een flyout geopend die naar de update verwijst.

## <a name="sidebar"></a>Zijbalk

Naast het hoofdinhoudsgebied van de profielpagina machine is de zijbalk.

![Afbeelding van het tabblad zijbalk voor Machineprofiel](../../media/mtp-machine-profile/sidebar.png)

De zijbalk biedt een aantal belangrijke basisinformatie in kleine onderafdelingen die open of gesloten kunnen worden geschakeld:

* **Tags** - Tags die aan het apparaat zijn gekoppeld
* **Beveiligingsinformatie** - Open incidenten, actieve waarschuwingen, blootstellingsniveau en risiconiveau
* **Apparaatgegevens** - Domein, BE, Asset-groep, statusstatus, gegevensgevoeligheid en IP-adressen
* **Netwerkactiviteit** - Tijdstempels voor de eerste en laatste keer dat het apparaat op het netwerk werd gezien

Deze sectie bevat ook de naam en het belichtingsniveau van het apparaat en een pictogram om aan te geven of het momenteel actief is in het netwerk.

## <a name="response-actions"></a>Responsacties

Responsacties bieden een snelle manier om bedreigingen te verdedigen en te analyseren.

![Afbeelding van het tabblad zijbalk voor Machineprofiel](../../media/mtp-machine-profile/actions.PNG)

De responsacties die hier voor u beschikbaar zijn, zijn:

* **Tags beheren** - Werkt aangepaste tags bij die u op dit apparaat hebt toegepast.
* **Machine isoleren** - Isoleer de machine uit het netwerk van uw organisatie en houdt deze verbonden met Microsoft Defender Advanced Threat Protection. U ervoor kiezen om Outlook, Teams en Skype voor Bedrijven te laten draaien terwijl de machine geïsoleerd is, voor communicatiedoeleinden.
* **App-uitvoering beperken** : voorkomt dat toepassingen die niet door Microsoft zijn ondertekend, worden uitgevoerd
* **Antivirusscan uitvoeren** - Werkt Windows Defender Antivirus-definities bij en voert onmiddellijk een antivirusscan uit. Kies tussen Quick scan of Volledige scan.
* **Onderzoekspakket verzamelen** - Verzamelt informatie over de machine. Wanneer het onderzoek is voltooid, u het downloaden.
* **Start de live responssessie** - Laadt een externe shell op de machine voor [diepgaande beveiligingsonderzoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* **Start geautomatiseerd onderzoek** - [onderzoekt en verherstelt automatisch bedreigingen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Hoewel u handmatig geautomatiseerde onderzoeken activeren om vanaf deze pagina uit te voeren, leiden [bepaalde waarschuwingsbeleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) zelf tot automatische onderzoeken.
* **Actiecentrum** - Bekijk de status van ingediende acties. Alleen beschikbaar als er al een andere actie is geselecteerd.

## <a name="related-topics"></a>Verwante onderwerpen

* [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
* [Microsoft-bedreigingsbeveiliging inschakelen](mtp-enable.md)
* [Entiteiten op machines onderzoeken met live respons](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Geautomatiseerd onderzoek en antwoord (AIR) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
