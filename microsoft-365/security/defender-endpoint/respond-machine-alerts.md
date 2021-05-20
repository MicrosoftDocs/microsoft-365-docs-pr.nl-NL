---
title: Antwoordacties uitvoeren op een apparaat in Microsoft Defender voor eindpunt
description: Neem reactieacties op een apparaat, zoals het isoleren van apparaten, het verzamelen van een onderzoekspakket, het beheren van tags, het uitvoeren van av-scan en het beperken van de uitvoering van apps.
keywords: reageren, isoleren, apparaat isoleren, onderzoekspakket verzamelen, actiecentrum, beperken, tags beheren, av-scan, app beperken
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ae8b08ce3d5bcc34e91f031223108fca053348ce
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572391"
---
# <a name="take-response-actions-on-a-device"></a>Acties ondernemen op een apparaat

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wil je Defender for Endpoint ervaren? [Meld je aan voor een gratis proefperiode.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-respondmachine-abovefoldlink) 

Reageer snel op gedetecteerde aanvallen door apparaten te isoleren of een onderzoekspakket te verzamelen. Nadat u actie hebt ondernomen op apparaten, kunt u de activiteitsgegevens controleren in het actiecentrum.

Antwoordacties worden boven aan een specifieke apparaatpagina uitgevoerd en omvatten:

- Tags beheren
- Geautomatiseerd onderzoek starten
- Live responssessie starten
- Onderzoekspakket verzamelen
- Antivirusscan uitvoeren
- Het uitvoeren van apps beperken
- Apparaat isoleren
- Contact opnemen met een risicodeskundige
- Actiecentrum

[![Afbeelding van responsacties ](images/response-actions.png)](images/response-actions.png#lightbox)

 U kunt apparaatpagina's vinden in een van de volgende weergaven:

- **Dashboard beveiligingsbewerkingen** : selecteer een apparaatnaam op de kaart Apparaten met risico.
- **Waarschuwingswachtrij** : selecteer de apparaatnaam naast het apparaatpictogram in de waarschuwingswachtrij.
- **Lijst met apparaten** : selecteer de kop van de apparaatnaam in de lijst met apparaten.
- **Zoekvak** - Selecteer Apparaat in het vervolgkeuzemenu en voer de apparaatnaam in.

>[!IMPORTANT]
> - Deze antwoordacties zijn alleen beschikbaar voor apparaten op Windows 10, versie 1703 of hoger. 
> - Voor niet-Windows platforms zijn de responsmogelijkheden (zoals apparaatisolatie) afhankelijk van de mogelijkheden van derden.

## <a name="manage-tags"></a>Tags beheren

Tags toevoegen of beheren om een logische groepsaffiliatie te maken. Apparaattags ondersteunen de juiste toewijzing van het netwerk, zodat u verschillende tags kunt koppelen om de context vast te leggen en dynamische lijstcreatie in te schakelen als onderdeel van een incident.

Zie Apparaattags maken en beheren voor meer informatie over [apparaattags.](machine-tags.md)

## <a name="initiate-automated-investigation"></a>Geautomatiseerd onderzoek starten

U kunt indien nodig een nieuw geautomatiseerd onderzoek voor algemeen gebruik op het apparaat starten. Terwijl een onderzoek wordt uitgevoerd, wordt elke andere waarschuwing die van het apparaat wordt gegenereerd, toegevoegd aan een lopend geautomatiseerd onderzoek totdat dat onderzoek is voltooid. Bovendien, als dezelfde dreiging wordt gezien op andere apparaten, die apparaten worden toegevoegd aan het onderzoek.

Zie [Overzicht van geautomatiseerde onderzoeken](automated-investigations.md)voor meer informatie over geautomatiseerde onderzoeken .

## <a name="initiate-live-response-session"></a>Live responssessie starten

Live response is een mogelijkheid die u onmiddellijk toegang geeft tot een apparaat met behulp van een externe shell-verbinding. Dit geeft u de bevoegdheid om diepgaand onderzoekswerk te doen en onmiddellijk actie te ondernemen om geïdentificeerde bedreigingen onmiddellijk in te dammen - realtime.

Live respons is ontworpen om onderzoeken te verbeteren door u in staat te stellen forensische gegevens te verzamelen, scripts uit te voeren, verdachte entiteiten te verzenden voor analyse, bedreigingen te verhelpen en proactief te jagen op opkomende bedreigingen.

Zie Entiteiten onderzoeken op [apparaten die liverespons gebruiken voor](live-response.md)meer informatie over liverespons.

## <a name="collect-investigation-package-from-devices"></a>Onderzoekspakket van apparaten verzamelen

Als onderdeel van het onderzoek- of reactieproces kunt u een onderzoekspakket ophalen van een apparaat. Door het onderzoekspakket te verzamelen, kunt u de huidige status van het apparaat identificeren en de tools en technieken die door de aanvaller worden gebruikt verder begrijpen.

Om het pakket (Zip-bestand) te downloaden en de gebeurtenissen op een apparaat te onderzoeken

1. Selecteer **Onderzoekspakket verzamelen** in de rij met antwoordacties boven aan de apparaatpagina.
2. Geef in het tekstvak op waarom u deze actie wilt uitvoeren. Selecteer **Bevestigen**.
3. Het zip-bestand wordt gedownload

Alternatieve manier:

1. Selecteer **Actiecentrum** in het gedeelte reactieacties van de apparaatpagina.

    ![Afbeelding van actiecentrumknop](images/action-center-package-collection.png)

3. Selecteer **pakketverzamelingspakket dat beschikbaar is** om het zip-bestand te downloaden in het actiecentrum fly-out.
  
    ![Afbeelding van downloadpakketknop](images/collect-package.png)

Het pakket bevat de volgende mappen:

| map | Omschrijving |
|:---|:---------|
|Autoruns | Bevat een set bestanden die elk de inhoud van het register van een bekend automatisch startpunt (ASEP) vertegenwoordigen om de persistentie van de aanvaller op het apparaat te identificeren. </br></br> <div class="alert"><b>OPMERKING:</b> Als de registersleutel niet wordt gevonden, bevat het bestand het volgende bericht: "FOUT: het systeem kon de opgegeven registersleutel of -waarde niet vinden."</div>                                                                                                                                |
|Geïnstalleerde programma's | Dit .CSV bestand bevat de lijst met geïnstalleerde programma's die kunnen helpen identificeren wat er momenteel op het apparaat is geïnstalleerd. Zie [Win32_Product class](https://go.microsoft.com/fwlink/?linkid=841509)voor meer informatie.                                                                                  |
|Netwerkverbindingen | Deze map bevat een set gegevenspunten met betrekking tot de verbindingsinformatie die kunnen helpen bij het identificeren van connectiviteit met verdachte URL's, de C-infrastructuur (Command and Control) van aanvallers (C&C), eventuele zijdelingse verplaatsing of externe verbindingen.</br></br> - ActiveNetConnections.txt : geeft protocolstatistieken en huidige TCP/IP-netwerkverbindingen weer. Biedt de mogelijkheid om te zoeken naar verdachte connectiviteit die door een proces is gemaakt. </br></br> - Arp.txt : geeft de huidige ARP-cachetabellen (Address Resolution Protocol) weer voor alle interfaces. </br></br> ARP-cache kan extra hosts op een netwerk onthullen die zijn gecompromitteerd of verdachte systemen op het netwerk die mogelijk zijn gebruikt om een interne aanval uit te voeren.</br></br> - DnsCache.txt - Geeft de inhoud weer van de DNS-client resolver-cache, die zowel vermeldingen bevat die vooraf zijn geladen uit het lokale Hosts-bestand als alle recent verkregen bronrecords voor naamquery's die door de computer zijn opgelost. Dit kan helpen bij het identificeren van verdachte verbindingen. </br></br> - IpConfig.txt : geeft de volledige TCP/IP-configuratie voor alle adapters weer. Adapters kunnen fysieke interfaces vertegenwoordigen, zoals geïnstalleerde netwerkadapters of logische interfaces, zoals inbelverbindingen. </br></br> - FirewallExecutionLog.txt en pfirewall.log                                                                                  |
| Prefetch-bestanden| Windows Prefetch-bestanden zijn ontworpen om het opstartproces van de toepassing te versnellen. Het kan worden gebruikt om alle bestanden te volgen die onlangs in het systeem zijn gebruikt en sporen te vinden voor toepassingen die mogelijk zijn verwijderd, maar nog steeds te vinden zijn in de prefetch-bestandslijst. </br></br> - Prefetch map – Bevat een kopie van de prefetch bestanden van `%SystemRoot%\Prefetch` . OPMERKING: Het wordt aanbevolen om een prefetch-bestandsviewer te downloaden om de prefetch-bestanden te bekijken. </br></br> - PrefetchFilesList.txt - Bevat de lijst met alle gekopieerde bestanden die kunnen worden gebruikt om bij te houden of er kopieerfouten zijn opgetreden in de prefetch-map.                                                                                                      |
| Processen| Bevat een .CSV bestand met de actieve processen, dat de mogelijkheid biedt om de huidige processen te identificeren die op het apparaat worden uitgevoerd. Dit kan handig zijn bij het identificeren van een verdacht proces en de status ervan.                                                                                                                                                                                                       |
| Geplande taken| Bevat een .CSV bestand met de geplande taken, dat kan worden gebruikt om routines te identificeren die automatisch worden uitgevoerd op een gekozen apparaat om te zoeken naar verdachte code die is ingesteld om automatisch te worden uitgevoerd.                                                                                                                                                                                                      |
| Logboek van beveiligingsgebeurtenissen| Bevat het logboek met beveiligingsgebeurtenissen, dat records bevat van aanmeldings- of afmeldactiviteiten of andere beveiligingsgerelateerde gebeurtenissen die zijn opgegeven in het controlebeleid van het systeem. </br></br><div class="alert"><b>OPMERKING:</b> Open het gebeurtenislogboekbestand met logboek.</div>                                                                                    |
| Services| Bevat een .CSV bestand met services en hun statussen.                                                                                      |
| Windows SMB-sessies (Server Message Block) | Hier worden gedeelde toegang tot bestanden, printers en seriële poorten en diverse communicatie tussen knooppunten in een netwerk weergegeven. Dit kan helpen bij het identificeren van gegevensexfiltratie of zijdelingse beweging. </br></br> Bevat bestanden voor SMBInboundSessions en SMBOutboundSession. </br></br> <div class="alert"><b>OPMERKING:</b> Als er geen sessies zijn (inkomend of uitgaand), krijgt u een tekstbestand waarin staat dat er geen SMB-sessies zijn gevonden.</div>                                                                                                                          |
| Systeeminformatie| Bevat een SystemInformation.txt bestand met systeeminformatie zoals de versie van het besturingssysteem en netwerkkaarten.                                                                                     |
| Tijdelijke mappen| Bevat een set tekstbestanden met de bestanden in %Temp% voor elke gebruiker in het systeem. </br></br> Dit kan helpen om verdachte bestanden bij te houden die een aanvaller mogelijk op het systeem heeft laten vallen. </br></br> <div class="alert"><b>OPMERKING:</b> Als het bestand het volgende bericht bevat: "Het systeem kan het opgegeven pad niet vinden", betekent dit dat er geen tijdelijke map voor deze gebruiker is en mogelijk omdat de gebruiker zich niet heeft aanmelden bij het systeem.</div>                                                                                                                                         |
| Gebruikers en groepen| Hier vindt u een lijst met bestanden die elk een groep en de leden vertegenwoordigen.                                                                                                                   |
|WdSupportLogs| Biedt de MpCmdRunLog.txt en MPSupportFiles.cab  </br></br> <div class="alert"><b>OPMERKING:</b> Deze map wordt alleen gemaakt op Windows 10, versie 1709 of hoger met updatepakket van februari 2020 of recenter geïnstalleerd:</br> Win10 1709 (RS3) Bouw 16299.1717 : [KB4537816](https://support.microsoft.com/en-us/help/4537816/windows-10-update-kb4537816) </br> Win10 1803 (RS4) Bouw 17134.1345 : [KB4537795](https://support.microsoft.com/en-us/help/4537795/windows-10-update-kb4537795) </br> Win10 1809 (RS5) Bouw 17763.1075 : [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818) </br> Win10 1903/1909 (19u1/19u2) Bouwt 18362.693 en 18363.693 : [KB4535996](https://support.microsoft.com/en-us/help/4535996/windows-10-update-kb4535996) </div>                                                                                                                    |
| CollectionSummaryReport.xls| Dit bestand is een samenvatting van de verzameling onderzoekspakketten, het bevat de lijst met gegevenspunten, de opdracht die wordt gebruikt om de gegevens te extraheren, de uitvoeringsstatus en de foutcode in geval van een fout. U kunt dit rapport gebruiken om bij te houden of het pakket alle verwachte gegevens bevat en om te bepalen of er fouten zijn opgetreden. |

## <a name="run-microsoft-defender-antivirus-scan-on-devices"></a>Microsoft Defender Antivirus scannen uitvoeren op apparaten

Als onderdeel van het onderzoek- of reactieproces kunt u op afstand een antivirusscan starten om malware te identificeren en te verhelpen die mogelijk aanwezig is op een gecompromitteerd apparaat.

>[!IMPORTANT]
>- Deze actie is beschikbaar voor apparaten op Windows 10, versie 1709 of hoger.
>- Een Microsoft Defender Antivirus (Microsoft Defender AV) scan kan naast andere antivirusoplossingen worden uitgevoerd, of Microsoft Defender AV nu de actieve antivirusoplossing is of niet. Microsoft Defender AV kan zich in de passieve modus bevinden. Zie [compatibiliteit Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md)voor meer informatie.

Selecteer **het** scantype dat u wilt uitvoeren (snel of vol) en voeg een opmerking toe voordat u de scan bevestigt.

![Afbeelding van melding om snelscan of volledige scan te selecteren en commentaar toe te voegen](images/run-antivirus.png)

Het actiecentrum toont de scaninformatie en de tijdlijn van het apparaat bevat een nieuwe gebeurtenis, die aangeeft dat er een scanactie op het apparaat is ingediend. Microsoft Defender AV-waarschuwingen geven alle detecties weer die tijdens de scan zijn opgedoken.

>[!NOTE]
>Bij het activeren van een scan met behulp van Defender for Endpoint response action is de Microsoft Defender antivirus 'ScanAvgCPULoadFactor'-waarde nog steeds van toepassing en beperkt de CPU-impact van de scan.<br> Als ScanAvgCPULoadFactor niet is geconfigureerd, is de standaardwaarde een limiet van 50% maximale CPU-belasting tijdens een scan.<br>
>Zie [configure-advanced-scan-types-microsoft-defender-antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-advanced-scan-types-microsoft-defender-antivirus)voor meer informatie.

## <a name="restrict-app-execution"></a>Het uitvoeren van apps beperken

Naast het bevatten van een aanval door het stoppen van schadelijke processen, kunt u ook een apparaat vergrendelen en voorkomen dat latere pogingen van mogelijk schadelijke programma's worden uitgevoerd.

>[!IMPORTANT]
> - Deze actie is beschikbaar voor apparaten op Windows 10, versie 1709 of hoger.
> - Deze functie is beschikbaar als uw organisatie Microsoft Defender Antivirus gebruikt.
> - Deze actie moet voldoen aan de Windows Defender integriteitsbeleidsindelingen en ondertekeningsvereisten voor toepassingsbeheercode. Zie [Code-integriteitsbeleidsindelingen en ondertekening](https://docs.microsoft.com/windows/device-security/device-guard/requirements-and-deployment-planning-guidelines-for-device-guard#code-integrity-policy-formats-and-signing)voor meer informatie.

Als u wilt voorkomen dat een toepassing wordt uitgevoerd, wordt een code-integriteitsbeleid toegepast waarmee bestanden alleen kunnen worden uitgevoerd als ze zijn ondertekend door een door Microsoft uitgegeven certificaat. Deze methode van beperking kan helpen voorkomen dat een aanvaller gecompromitteerde apparaten bestuurt en verdere kwaadaardige activiteiten uitvoert.

>[!NOTE]
>U kunt de beperking van toepassingen op elk gewenst moment omkeren. De knop op de apparaatpagina wordt gewijzigd in **App-beperkingen verwijderen** en vervolgens neemt u dezelfde stappen als het beperken van de uitvoering van apps.

Zodra u **De uitvoering van de app beperken** op de apparaatpagina hebt geselecteerd, typt u een opmerking en selecteert u **Bevestigen**. Het actiecentrum toont de scaninformatie en de tijdlijn van het apparaat bevat een nieuwe gebeurtenis.

![Afbeelding van melding van app-beperking](images/restrict-app-execution.png)

**Melding over apparaatgebruiker**:</br>
Wanneer een app is beperkt, wordt de volgende melding weergegeven om de gebruiker te informeren dat een app wordt beperkt tot uitvoeren:

![Afbeelding van app-beperking](images/atp-app-restriction.png)

## <a name="isolate-devices-from-the-network"></a>Apparaten isoleren van het netwerk

Afhankelijk van de ernst van de aanval en de gevoeligheid van het apparaat, kunt u het apparaat isoleren van het netwerk. Deze actie kan helpen voorkomen dat de aanvaller het gecompromitteerde apparaat bestuurt en verdere activiteiten uitvoert, zoals gegevensexfiltratie en zijdelingse beweging.

>[!IMPORTANT]
>- Volledige isolatie is beschikbaar voor apparaten op Windows 10, versie 1703.
>- Selectieve isolatie is beschikbaar voor apparaten op Windows 10, versie 1709 of hoger.
>- Bij het isoleren van een apparaat zijn alleen bepaalde processen en bestemmingen toegestaan. Daarom kunnen apparaten die zich achter een volledige VPN-tunnel bevinden, de Microsoft Defender for Endpoint-cloudservice niet bereiken nadat het apparaat is geïsoleerd. We raden u aan een VPN voor split-tunneling te gebruiken voor Microsoft Defender voor endpoint- en Microsoft Defender Antivirus cloudgebaseerd beveiligingsverkeer.

Met deze functie voor apparaatisolatie wordt het gecompromitteerde apparaat losgekoppeld van het netwerk met behoud van de verbinding met de Defender for Endpoint-service, die het apparaat blijft bewaken.

Op Windows 10, versie 1709 of hoger hebt u extra controle over het netwerkisolatieniveau. U kunt er ook voor kiezen om Outlook-, Microsoft Teams- en Skype voor Bedrijven-connectiviteit in te schakelen (ook wel 'Selectieve isolatie' genoemd).

>[!NOTE]
>U kunt het apparaat op elk gewenst moment opnieuw verbinden met het netwerk. De knop op de apparaatpagina verandert om te zeggen **Loslaten uit isolatie** en vervolgens neemt u dezelfde stappen als het isoleren van het apparaat.

Zodra u **Apparaat isoleren** op de apparaatpagina hebt geselecteerd, typt u een opmerking en selecteert u **Bevestigen**. Het actiecentrum toont de scaninformatie en de tijdlijn van het apparaat bevat een nieuwe gebeurtenis.

![Afbeelding van isolaatapparaat](images/isolate-device.png)

>[!NOTE]
>Het apparaat blijft verbonden met de Defender for Endpoint-service, zelfs als het is geïsoleerd van het netwerk. Als u ervoor hebt gekozen om Outlook en Skype voor Bedrijven communicatie in te schakelen, kunt u met de gebruiker communiceren terwijl het apparaat geïsoleerd is.

**Melding over apparaatgebruiker**:</br>
Wanneer een apparaat wordt geïsoleerd, wordt de volgende melding weergegeven om de gebruiker te informeren dat het apparaat wordt geïsoleerd van het netwerk:

![Afbeelding van geen netwerkverbinding](images/atp-notification-isolate.png)

## <a name="consult-a-threat-expert"></a>Contact opnemen met een risicodeskundige

U kunt een Microsoft-bedreigingsexpert raadplegen voor meer inzichten over een mogelijk gecompromitteerd apparaat of reeds gecompromitteerde apparaten. Microsoft Threat Experts kunnen direct vanuit de Microsoft Defender-beveiligingscentrum worden ingeschakeld voor een tijdige en nauwkeurige reactie. Experts bieden niet alleen inzichten over een mogelijk gecompromitteerd apparaat, maar ook om complexe bedreigingen, gerichte aanvalsmeldingen die u ontvangt of als u meer informatie nodig hebt over de waarschuwingen of een context met bedreigingsinformatie die u op uw portaldashboard ziet, beter te begrijpen.

Zie [Een Microsoft Threat Expert raadplegen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) voor meer informatie.


## <a name="check-activity-details-in-action-center"></a>Activiteitsdetails controleren in Actiecentrum

Het **actiecentrum** biedt informatie over acties die zijn uitgevoerd op een apparaat of bestand. U kunt de volgende details bekijken:

- Collectie onderzoekspakket
- Antivirusscan
- App-beperking
- Isolatie van het apparaat

Alle andere gerelateerde details worden ook weergegeven, bijvoorbeeld indieningsdatum/-tijd, verzendende gebruiker en of de actie is geslaagd of mislukt.

![Afbeelding van actiecentrum met informatie](images/action-center-details.png)

## <a name="related-topic"></a>Verwant onderwerp
- [Acties ondernemen op een bestand](respond-file-alerts.md)
- [Onnauwkeurigheid melden](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation#report-inaccuracy)
