---
title: Machineprofiel in Microsoft 365-beveiligingsportal
description: Bekijk risico- en blootstellingsniveaus voor een apparaat in uw organisatie. Analyseer eerdere en huidige bedreigingen en bescherm de machine met de nieuwste updates.
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
ms.openlocfilehash: 7ab3f63008c65fca1a99128cc6f11f83bc86b2b4
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857607"
---
# <a name="machine-profile-page"></a>Pagina machineprofiel

De Microsoft 365-beveiligingsportal biedt u machineprofielpagina's, zodat u de status en status van apparaten in uw netwerk beoordelen. Elke machine profiel pagina bevat een schat aan informatie over het apparaat.

U diepgaande informatie bekijken over welke software het draait, alle beveiligingsgebeurtenissen of waarschuwingen uit het verleden en heden en koppelingen naar relevante softwarepatches vinden.

U het machineprofiel ook gebruiken om veelvoorkomende beveiligingsgerelateerde taken uit te voeren en snel basisdetails over het apparaat te bekijken.

## <a name="navigating-the-machine-profile-page"></a>Navigeren op de pagina Machineprofiel

De pagina Machineprofiel is toegankelijk door direct een apparaatnaam in de lijst Machines te selecteren of door **de pagina Machine openen** in de lijst Machines flyout te kiezen.

Zodra u de pagina hebt geopend, zult u merken dat deze is opgesplitst in drie secties.

![Afbeelding van de pagina met het machineprofiel met (1) Tabgebied (2) Zijbalk en (3) Acties gemarkeerd in rood](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

Het hoofdinhoudsgebied (1) bevat zeven tabbladen die u inschakelen om verschillende soorten informatie over de machine te bekijken.

De zijbalk (2) bevat basisdetails over de machine.

Er zijn ook responsacties beschikbaar in een koptekst (3) voor de zijbalk en hoofdinhoudssecties. U de acties in deze koptekst gebruiken om veelvoorkomende beveiligingsgerelateerde taken uit te voeren.

## <a name="tabs-section"></a>Tabbladen, sectie

Met de tabbladen Machine-profiel u een overzicht van beveiligingsgegevens over de machine en tabellen met een lijst met waarschuwingen, een tijdlijn, een lijst met beveiligingsaanbevelingen, een softwarevoorraad, een lijst met ontdekte kwetsbaarheden en ontbrekende KBs (beveiligingsupdates).

### <a name="overview-tab"></a>Tabblad Overzicht

Het standaardtabblad is **Overzicht**. Het biedt een snelle blik op het belangrijkste beveiligingsfeit over het apparaat.

![Afbeelding van het tabblad Overzicht voor Machineprofiel](../../media/mtp-machine-profile/overview.png)

Hier vindt u een grafiek van het risiconiveau van het apparaat en actieve waarschuwingen, alle momenteel aangemelde gebruikers, een korte lijst van de meeste en minst frequente gebruikers en beveiligingsbeoordelingen die het belichtingsniveau van het apparaat, beveiligingsaanbevelingen, beïnvloede software en ontdekte kwetsbaarheden.

### <a name="alerts-tab"></a>Tabblad Waarschuwingen

Het tabblad **Waarschuwingen** bevat een lijst met waarschuwingen die op het apparaat zijn gerapporteerd.

![Afbeelding van het tabblad Waarschuwingen voor Machineprofiel](../../media/mtp-machine-profile/alerts.png)

U het aantal weergegeven items aanpassen en welke kolommen voor elk item worden weergegeven. Het standaardgedrag is om 30 items per pagina weer te geven en 11 kolommen aan te laten zetten om weer te geven.

De kolommen in dit tabblad bevatten informatie over de ernst van de bedreiging die de waarschuwing heeft geactiveerd, evenals de status, de onderzoeksstatus en aan wie de waarschuwing is toegewezen.

De kolom *Beïnvloede entiteiten* verwijst naar de machine (entiteit) waarvan u momenteel het profiel bekijkt, plus alle andere machines in uw netwerk die worden beïnvloed.

Als u een item uit deze lijst selecteert, wordt een koppeling naar de geselecteerde waarschuwing geopend.

Deze lijst kan worden gefilterd op ernst, status of toewijzing.

### <a name="timeline-tab"></a>Tabblad Tijdlijn

Het tabblad **Tijdlijn** bevat een interactieve, chronologische grafiek met gebeurtenissen die op het apparaat worden weergegeven. Door het gemarkeerde gebied van de grafiek te verplaatsen, u gebeurtenissen over verschillende tijdsbereiken bekijken. U ook een aangepast aantal datums intypen.

Onder de grafiek staat een lijst met gebeurtenissen voor het geselecteerde bereik van datums.

![Afbeelding van het tijdlijntabblad voor Machineprofiel](../../media/mtp-machine-profile/timeline.png)

Het aantal weergegeven items en de kolommen in de lijst kunnen beide worden aangepast. In de standaardkolommen worden de gebeurtenistijd, actieve gebruiker, actietype, entiteiten (processen) en aanvullende informatie over de gebeurtenis weergegeven.

Als u een item uit de lijst selecteert, wordt een flyout geopend met een grafiek met entiteiten van gebeurtenissen, waarin de bovenliggende en onderliggende processen worden weergegeven die de gebeurtenis hebben geactiveerd.

Deze lijst kan worden gefilterd op het specifieke type gebeurtenis; bijvoorbeeld registergebeurtenissen of gebeurtenissen op het slimme scherm.

### <a name="security-recommendations-tab"></a>Tabblad Beveiligingsaanbevelingen

Op het tabblad **Beveiligingsaanbevelingen** worden acties weergegeven die u ondernemen om het apparaat te beschermen. Als u een item in deze lijst selecteert, opent u een flyout waar u instructies krijgen over het toepassen van de aanbeveling.

![Afbeelding van het tabblad Beveiligingsaanbevelingen voor Machineprofiel](../../media/mtp-machine-profile/security-recs.png)

Net als bij de vorige tabbladen kan het aantal items dat per pagina wordt weergegeven en welke kolommen zichtbaar zijn, worden aangepast.

De standaardweergave bevat kolommen waarin de beveiligingstekortkomingen worden beschreven die zijn aangepakt, de bijbehorende bedreiging, de bijbehorende component of software die door de bedreiging wordt beïnvloed, en meer. Items kunnen worden gefilterd op de status van de aanbeveling.

### <a name="software-inventory"></a>Softwareinventaris

Op het tabblad **Softwareinventaris** worden software vermeld die op het apparaat is geïnstalleerd.

![Afbeelding van het tabblad Softwarevoorraad voor Machineprofiel](../../media/mtp-machine-profile/software-inventory.png)

In de standaardweergave wordt de softwareleverancier, het geïnstalleerde versienummer, het aantal bekende softwarezwakke punten, bedreigingsinzichten, productcode en tags weergegeven. Het aantal weergegeven items en de weergegeven kolommen kunnen beide worden aangepast.

Als u een item uit deze lijst selecteert, wordt een flyout geopend met meer details over de geselecteerde software, evenals het pad en de tijdstempel voor de laatste keer dat de software is gevonden.

Deze lijst kan worden gefilterd op productcode.

### <a name="discovered-vulnerabilities-tab"></a>Tabblad Ontdekte kwetsbaarheden

Het tabblad **Ontdekte kwetsbaarheden** bevat een lijst van algemene kwetsbaarheden en exploits (CVE's) die van invloed kunnen zijn op het apparaat.

![Afbeelding van het tabblad Ontdekte kwetsbaarheden voor machineprofiel](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

De standaardweergave geeft de ernst van de CVE, de Common Vulnerability Score (CVS), de software met betrekking tot het CVE, toen het CVE werd gepubliceerd, toen het CVE voor het laatst werd bijgewerkt en bedreigingen die zijn gekoppeld aan het CVE.

Net als bij de vorige tabbladen kan het aantal weergegeven items en welke kolommen zichtbaar zijn, worden aangepast.

Als u een item uit deze lijst selecteert, wordt een flyout geopend waarin de CVE wordt beschreven.

### <a name="missing-kbs"></a>Ontbrekende KB's

Op het tabblad **Ontbrekende KBs** worden alle Microsoft-updates weergegeven die nog op de machine moeten worden toegepast. De "KBs" in kwestie zijn [Knowledge Base artikelen](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) die deze updates beschrijven; bijvoorbeeld [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Afbeelding van ontbrekende kbs-tabblad voor Machineprofiel](../../media/mtp-machine-profile/missing-kbs.PNG)

De standaardweergave bevat het bulletin met de updates, OS-versie, de betrokken producten, cve's die zijn geadresseerd, het KB-nummer en tags.

Het aantal items dat per pagina wordt weergegeven en welke kolommen worden weergegeven, kan worden aangepast.

Als u een item selecteert, wordt een flyout geopend die naar de update wordt gekoppeld.

## <a name="sidebar"></a>Zijbalk

Naast het hoofdinhoudsgebied van de pagina Machineprofiel bevindt zich de zijbalk.

![Afbeelding van het tabblad zijbalk voor Machineprofiel](../../media/mtp-machine-profile/sidebar.png)

De zijbalk biedt een aantal belangrijke basisinformatie in kleine ondersecties die kunnen worden ingeschakeld open of gesloten:

* **Tags** - Tags die aan het apparaat zijn gekoppeld
* **Beveiligingsinformatie** - Open incidenten, actieve waarschuwingen, blootstellingsniveau en risiconiveau
* **Apparaatgegevens** - Domein, BE, Activagroep, statusstatus, gegevensgevoeligheid en IP-adressen
* **Netwerkactiviteit** - Tijdstempels voor het eerst en de laatste keer dat het apparaat op het netwerk werd gezien

Deze sectie bevat ook de naam en het belichtingsniveau van het apparaat en een pictogram om aan te geven of het momenteel actief is in het netwerk.

## <a name="response-actions"></a>Reactieacties

Responsacties bieden een snelle manier om bedreigingen te verdedigen en te analyseren.

![Afbeelding van het tabblad zijbalk voor Machineprofiel](../../media/mtp-machine-profile/actions.PNG)

De reactieacties die hier voor u beschikbaar zijn, zijn onder andere:

* **Tags beheren** - Updates aangepaste tags die u hebt toegepast op dit apparaat.
* **Machine isoleren** - Hiermee isoleert u de machine van het netwerk van uw organisatie terwijl deze verbonden blijft met Microsoft Defender Advanced Threat Protection. U ervoor kiezen outlook, teams en Skype voor Bedrijven te laten draaien terwijl de machine is geïsoleerd, voor communicatiedoeleinden.
* **App-uitvoering beperken** - Voorkomt dat toepassingen die niet door Microsoft zijn ondertekend, worden uitgevoerd
* **Antivirusscan uitvoeren** - Updates Windows Defender Antivirus definities en voert onmiddellijk een antivirusscan uit. Kies tussen Quick scan of Volledige scan.
* **Verzamel onderzoekspakket** - Verzamelt informatie over de machine. Wanneer het onderzoek is voltooid, u het downloaden.
* **Live Response-sessie starten** - Laadt een externe shell op de machine voor [diepgaande beveiligingsonderzoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* **Start geautomatiseerd onderzoek** - Onderzoekt en herstelt automatisch [bedreigingen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Hoewel u handmatig geautomatiseerde onderzoeken activeren om vanaf deze pagina uit te voeren, leiden [bepaalde waarschuwingsbeleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) automatisch onderzoek op zichzelf uit.
* **Actiecentrum** - Bekijk de status van ingediende acties. Alleen beschikbaar als er al een andere actie is geselecteerd.

## <a name="related-topics"></a>Verwante onderwerpen

* [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
* [Microsoft-bedreigingsbeveiliging inschakelen](mtp-enable.md)
* [Entiteiten op machines onderzoeken met behulp van live respons](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Geautomatiseerd onderzoek en respons (AIR) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
