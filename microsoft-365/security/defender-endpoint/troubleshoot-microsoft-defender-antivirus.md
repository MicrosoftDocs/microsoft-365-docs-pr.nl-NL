---
title: Microsoft Defender AV-gebeurtenis-IDs en foutcodes
description: Zoek de oorzaken en oplossingen voor Microsoft Defender Antivirus gebeurtenis-ID's en fouten
keywords: gebeurtenis, foutcode, siem, logboekregistratie, probleemoplossing, wef, windows event forwarding
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275346"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Gebeurtenislogboeken en foutcodes bekijken voor het oplossen van problemen met Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Als u een probleem ondervindt met Microsoft Defender Antivirus, kunt u in de tabellen in dit onderwerp zoeken naar een overeenkomend probleem en een mogelijke oplossing.

De lijst met tabellen:

- [Microsoft Defender Antivirus gebeurtenis-ID's](#windows-defender-av-ids) (deze zijn van toepassing op zowel Windows 10 als Windows Server 2016)
- [Microsoft Defender Antivirus clientfoutcodes](#error-codes)
- [Interne Microsoft Defender Antivirus clientfoutcodes (gebruikt door Microsoft tijdens ontwikkeling en testen)](#internal-error-codes)

> [!TIP]
> U kunt ook naar de demowebsite [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) van Microsoft Defender voor Eindpunt demo.wd.microsoft.com om te bevestigen dat de volgende functies werken:
> 
> - Cloudbeveiliging
> - Snel leren (inclusief Blok op het eerste gezicht)
> - Mogelijk ongewenste blokkering van toepassingen

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Microsoft Defender Antivirus gebeurtenis-IDs

Microsoft Defender Antivirus records gebeurtenis-ID's in het Windows gebeurtenislogboek.

U kunt het gebeurtenislogboek rechtstreeks bekijken of als u een hulpprogramma voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) van derden hebt, kunt u ook [Microsoft Defender Antivirus clientgebeurtenis-ID's](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) gebruiken om specifieke gebeurtenissen en fouten van uw eindpunten te bekijken.

De tabel in deze sectie bevat de belangrijkste Microsoft Defender Antivirus gebeurtenis-ID's en biedt, indien mogelijk, voorgestelde oplossingen om de fout op te lossen of op te lossen. 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>Een gebeurtenis Microsoft Defender Antivirus weergeven

1.  **Gebeurtenisviewer openen.**
2.  Vouw in de consolestructuur **Toepassingen en Services-logboeken** uit, vervolgens **Microsoft**, Windows **en** **Windows Defender.**
3.  Dubbelklik op **Operationeel.**
4.  Bekijk in het detailvenster de lijst met afzonderlijke gebeurtenissen om uw gebeurtenis te zoeken.
5.  Klik op de gebeurtenis om specifieke details over een gebeurtenis te zien in het onderste deelvenster, onder de **tabbladen** Algemeen **en** Details.

<table> 
<tr>
<th colspan="2" >Gebeurtenis-id: 1000</th>
</tr>
<tr>
<td>
Symbolische naam:
</td>
<td>
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Er is een antimalwarescan gestart. </b>
</td>
</tr>
<tr>
<td >
Beschrijving:
</td>
<td >
<dl>
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:<ul>
<li>Volledige scan</li>
<li>Snelle scan</li>
<li>Klantscan</li>
</ul>
</dt>
<dt>Scanbronnen: &lt; Resources (zoals bestanden/mappen/BHO) die zijn &gt; gescand.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1001</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Een antimalwarescan is voltooid.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
<dl>
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:<ul>
<li>Volledige scan</li>
<li>Snelle scan</li>
<li>Klantscan</li>
</ul>
</dt>
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;Scantijd</dt>
<dt>van gebruiker: de duur van een &lt; scan. &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1002</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Een antimalwarescan is gestopt voordat deze is voltooid. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
<dl>
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:<ul>
<li>Volledige scan</li>
<li>Snelle scan</li>
<li>Klantscan</li>
</ul>
</dt>
<dt>Gebruiker: &lt; Domein &gt; &amp; lt; &gt;Scantijd</dt>
<dt>van gebruiker: de duur van een &lt; scan. &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1003</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Een antimalwarescan is onderbroken. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
<dl>
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:<ul>
<li>Volledige scan</li>
<li>Snelle scan</li>
<li>Klantscan</li>
</ul>
</dt>
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1004</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Er is een antimalwarescan hervat. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
<dl>
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:<ul>
<li>Volledige scan</li>
<li>Snelle scan</li>
<li>Klantscan</li>
</ul>
</dt>
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1005</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Een antimalwarescan is mislukt. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
<dl>
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:<ul>
<li>Volledige scan</li>
<li>Snelle scan</li>
<li>Klantscan</li>
</ul>
</dt>
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Er is een fout opgetreden bij de antivirusclient en de huidige scan is gestopt. De scan kan mislukken vanwege een probleem aan de clientzijde. Deze gebeurtenisrecord bevat de scan-id, het type scan (Microsoft Defender Antivirus, antispyware, antimalware), scanparameters, de gebruiker die de scan heeft gestart, de foutcode en een beschrijving van de fout.
Problemen met deze gebeurtenis oplossen:
<ol>
<li>Voer de scan opnieuw uit.</li>
<li>Als het op dezelfde manier mislukt, gaat u naar de <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-site</a>en voert u het foutnummer in het vak Zoeken in om te zoeken naar de foutcode.</li>
<li>Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1006</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine heeft malware of andere mogelijk ongewenste software gevonden. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:<ul>
<li>Unknown</li>
<li>Lokale computer</li>
<li>Netwerk delen</li>
<li>Internet</li>
<li>Binnenkomend verkeer</li>
<li>Uitgaand verkeer</li>
</ul>
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Beton</li>
<li>Dynamische handtekening</li>
</ul>
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:<ul>
<li>Gebruiker: gebruiker gestart</li>
<li>Systeem: systeem gestart</li>
<li>Realtime: in realtime gestarte component</li>
<li>IOAV: IE Downloads and Outlook Express Attachments initiated</li>
<li>NIS: Netwerkcontrolesysteem</li>
<li>IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</li>
<li>Early Launch Antimalware (ELAM). Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</li>
<li>Externe bevestiging</li>
</ul>Antimalware Scan Interface (AMSI). Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.
</dt>
<dt>UAC-status: &lt; &gt; Statusgebruiker:</dt>
<dt>Domein &lt; &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; pid-handtekeningversie:</dt>
<dt> &lt; engineversie van &gt; </dt>
<dt>definitieversie: Antimalware Engine &lt; versie &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1007</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft een actie uitgevoerd om uw systeem te beschermen tegen malware of andere mogelijk ongewenste software. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus heeft actie ondernomen om deze computer te beschermen tegen malware of andere mogelijk ongewenste software. Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt> &lt; &gt; Bedreigingsnaam-id:</dt>
<dt>Ernst van &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt> Actie: &lt; Actie &gt; , bijvoorbeeld:<ul>
<li>Schoon: De resource is opgeschoond</li>
<li>Quarantaine: De resource is in quarantaine geplaatst</li>
<li>Verwijderen: De resource is verwijderd</li>
<li>Toestaan: De resource is toegestaan om uit te voeren/te bestaan</li>
<li>Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</li>
<li>Geen actie: geen actie</li>
<li>Blokkering: De resource is geblokkeerd voor het uitvoeren van</li>
</ul>
</dt>
<dt>Status: &lt; &gt;</dt>
<dt>Statushandtekeningsversie: &lt; engineversie &gt; van</dt>
<dt>definitieversie: &lt; Antimalware Engine versie &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1008</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft geprobeerd een actie uit te voeren om uw systeem te beschermen tegen malware of andere mogelijk ongewenste software, maar de actie is mislukt.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het ondernemen van actie tegen malware of andere mogelijk ongewenste software. Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt> &lt; &gt; Bedreigingsnaam-id:</dt>
<dt>Ernst van &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; &gt;Bestandspad</dt> 
<dt> actie: &lt; &gt; actie, bijvoorbeeld:<ul>
<li>Schoon: De resource is opgeschoond</li>
<li>Quarantaine: De resource is in quarantaine geplaatst</li>
<li>Verwijderen: De resource is verwijderd</li>
<li>Toestaan: De resource is toegestaan om uit te voeren/te bestaan</li>
<li>Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</li>
<li>Geen actie: geen actie</li>
<li>Blokkering: De resource is geblokkeerd voor het uitvoeren van</li>
</ul>
</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden. </dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Status: &lt; &gt;</dt>
<dt>Statushandtekeningsversie: &lt; engineversie &gt; van</dt>
<dt>definitieversie: &lt; Antimalware Engine versie &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1009</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft een item uit quarantaine hersteld. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus heeft een item uit quarantaine hersteld. Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; Gebruiker &gt; van</dt>
<dt> &lt; bestandspad: Domein &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1010</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform kan een item niet herstellen uit quarantaine. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het herstellen van een item uit quarantaine. Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; Gebruiker &gt; van</dt>
<dt> &lt; bestandspad: Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden. </dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine-versie: &lt; Antimalware Engine &gt; versie</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1011</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft een item uit quarantaine verwijderd. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus heeft een item uit quarantaine verwijderd.<br/>Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; Gebruiker &gt; van</dt>
<dt> &lt; bestandspad: Domein &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1012</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform kan een item niet uit quarantaine verwijderen.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het verwijderen van een item uit quarantaine.
Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; Gebruiker &gt; van</dt>
<dt> &lt; bestandspad: Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden. </dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine-versie: &lt; Antimalware Engine &gt; versie</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1013</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft de geschiedenis van malware en andere mogelijk ongewenste software verwijderd.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus heeft de geschiedenis van malware en andere mogelijk ongewenste software verwijderd.
<dl>
<dt>Tijd: de tijd waarop de gebeurtenis heeft plaatsgevonden, bijvoorbeeld wanneer de geschiedenis wordt verwijderd. Deze parameter wordt niet gebruikt bij bedreigingsgebeurtenissen, zodat er geen verwarring bestaat over de vraag of het hersteltijd of de tijd van de infectie is. Voor deze personen noemen we ze specifiek Actietijd of Detectietijd.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1014</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
Het antimalwareplatform kan de geschiedenis van malware en andere mogelijk ongewenste software niet verwijderen.
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het verwijderen van de geschiedenis van malware en andere mogelijk ongewenste software.
<dl>
<dt>Tijd: de tijd waarop de gebeurtenis heeft plaatsgevonden, bijvoorbeeld wanneer de geschiedenis wordt verwijderd. Deze parameter wordt niet gebruikt bij bedreigingsgebeurtenissen, zodat er geen verwarring bestaat over de vraag of het hersteltijd of de tijd van de infectie is. Voor deze personen noemen we ze specifiek Actietijd of Detectietijd.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden. </dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1015</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft verdacht gedrag gedetecteerd.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus heeft een verdacht gedrag gedetecteerd.<br/>Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:
<ul>
<li>Unknown</li>
<li>Lokale computer</li>
<li>Netwerk delen</li>
<li>Internet</li>
<li>Binnenkomend verkeer</li>
<li>Uitgaand verkeer</li>
</ul>
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Beton</li>
<li>Dynamische handtekening</li>
</ul>
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:<ul>
<li>Gebruiker: gebruiker gestart</li>
<li>Systeem: systeem gestart</li>
<li>Realtime: in realtime gestarte component</li>
<li>IOAV: IE Downloads and Outlook Express Attachments initiated</li>
<li>NIS: Netwerkcontrolesysteem</li>
<li>IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</li>
<li>Early Launch Antimalware (ELAM). Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</li>
<li>Externe bevestiging</li>
</ul>Antimalware Scan Interface (AMSI). Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.
</dt>
<dt>UAC-status: &lt; &gt; Statusgebruiker:</dt>
<dt>Domein &lt; &gt; \& lt; Naam &gt; </dt>
<dt>van gebruikersproces: &lt; proces &gt; in de PID-handtekening-id:</dt>de ernst van de gegevens die
<dt>overeenkomen met de ernst van de gegevens.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine Version: &lt; Antimalware Engine &gt; versie</dt>
<dt>Fidelity Label:</dt>
<dt>Doelbestandsnaam: &lt; &gt; Bestandsnaam van het bestand.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1116</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft malware of andere mogelijk ongewenste software gedetecteerd. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus malware of andere mogelijk ongewenste software heeft gedetecteerd.<br/>Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:
<ul>
<li>Unknown</li>
<li>Lokale computer</li>
<li>Netwerk delen</li>
<li>Internet</li>
<li>Binnenkomend verkeer</li>
<li>Uitgaand verkeer</li>
</ul>
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Beton</li>
<li>Dynamische handtekening</li>
</ul>
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:<ul>
<li>Gebruiker: gebruiker gestart</li>
<li>Systeem: systeem gestart</li>
<li>Realtime: in realtime gestarte component</li>
<li>IOAV: IE Downloads and Outlook Express Attachments initiated</li>
<li>NIS: Netwerkcontrolesysteem</li>
<li>IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</li>
<li>Early Launch Antimalware (ELAM). Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</li>
<li>Externe bevestiging</li>
</ul>Antimalware Scan Interface (AMSI). Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.
</dt>
<dt>UAC-gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; pid-handtekeningversie:</dt>
<dt> &lt; engineversie van &gt; </dt>
<dt>definitieversie: Antimalware Engine &lt; versie &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Er is geen actie vereist. Microsoft Defender Antivirus kan deze bedreiging opschorten en routinematige actie ondernemen. Als u de bedreiging handmatig wilt verwijderen, klikt u in Microsoft Defender Antivirus interface op <b>Computer reinigen.</b>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1117</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft een actie uitgevoerd om uw systeem te beschermen tegen malware of andere mogelijk ongewenste software. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus heeft actie ondernomen om deze computer te beschermen tegen malware of andere mogelijk ongewenste software.<br/>Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:
<ul>
<li>Unknown</li>
<li>Lokale computer</li>
<li>Netwerk delen</li>
<li>Internet</li>
<li>Binnenkomend verkeer</li>
<li>Uitgaand verkeer</li>
</ul>
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Beton</li>
<li>Dynamische handtekening</li>
</ul>
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:<ul>
<li>Gebruiker: gebruiker gestart</li>
<li>Systeem: systeem gestart</li>
<li>Realtime: in realtime gestarte component</li>
<li>IOAV: IE Downloads and Outlook Express Attachments initiated</li>
<li>NIS: Netwerkcontrolesysteem</li>
<li>IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</li>
<li>Early Launch Antimalware (ELAM). Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</li>
<li>Externe bevestiging</li>
</ul>Antimalware Scan Interface (AMSI). Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.
</dt>
<dt>UAC-gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; PID-actie:</dt> 
<dt> &lt; &gt; Actie, bijvoorbeeld:<ul>
<li>Schoon: De resource is opgeschoond</li>
<li>Quarantaine: De resource is in quarantaine geplaatst</li>
<li>Verwijderen: De resource is verwijderd</li>
<li>Toestaan: De resource is toegestaan om uit te voeren/te bestaan</li>
<li>Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</li>
<li>Geen actie: geen actie</li>
<li>Blokkering: De resource is geblokkeerd voor het uitvoeren van</li>
</ul>
</dt>
<dt>Actiestatus: &lt; Beschrijving van &gt; aanvullende acties</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine Version: &lt; Antimalware Engine &gt; version</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:<ul>
<li>Standaardinstelling voor Internet Explorer of Microsoft Edge</li>
<li>Instellingen voor Gebruikerstoegangsbeheer</li>
<li>Chrome-instellingen</li>
<li>Opstartbeheergegevens</li>
<li>Registerinstellingen voor Regedit en Task Manager</li>
<li>Windows Update, Background Intelligent Transfer Service en Remote Procedure Call Service</li>
<li>Windows Besturingssysteembestanden</li></ul>
De bovenstaande context is van toepassing op de volgende client- en serverversies:
<table>
<tr>
<th>Besturingssysteem</th>
<th>Versie van besturingssysteem</th>
</tr>
<tr>
<td>
Clientbesturingssysteem
</td>
<td>
Windows Vista (Service Pack 1 of Service Pack 2), Windows 7 en hoger
</td>
</tr>
<tr>
<td>
Serverbesturingssysteem
</td>
<td>
Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 en Windows Server 2016
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Er is geen actie nodig. Microsoft Defender Antivirus een bedreiging verwijderd of in quarantaine geplaatst. 
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1118</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform heeft geprobeerd een actie uit te voeren om uw systeem te beschermen tegen malware of andere mogelijk ongewenste software, maar de actie is mislukt. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een niet-kritieke fout opgetreden bij het ondernemen van actie tegen malware of andere mogelijk ongewenste software.<br/>Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:
<ul>
<li>Unknown</li>
<li>Lokale computer</li>
<li>Netwerk delen</li>
<li>Internet</li>
<li>Binnenkomend verkeer</li>
<li>Uitgaand verkeer</li>
</ul>
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Beton</li>
<li>Dynamische handtekening</li>
</ul>
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:<ul>
<li>Gebruiker: gebruiker gestart</li>
<li>Systeem: systeem gestart</li>
<li>Realtime: in realtime gestarte component</li>
<li>IOAV: IE Downloads and Outlook Express Attachments initiated</li>
<li>NIS: Netwerkcontrolesysteem</li>
<li>IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</li>
<li>Early Launch Antimalware (ELAM). Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</li>
<li>Externe bevestiging</li>
</ul>Antimalware Scan Interface (AMSI). Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.
</dt>
<dt>UAC-gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; PID-actie:</dt> 
<dt> &lt; &gt; Actie, bijvoorbeeld:<ul>
<li>Schoon: De resource is opgeschoond</li>
<li>Quarantaine: De resource is in quarantaine geplaatst</li>
<li>Verwijderen: De resource is verwijderd</li>
<li>Toestaan: De resource is toegestaan om uit te voeren/te bestaan</li>
<li>Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</li>
<li>Geen actie: geen actie</li>
<li>Blokkering: De resource is geblokkeerd voor het uitvoeren van</li>
</ul>
</dt>
<dt>Actiestatus: &lt; Beschrijving van &gt; aanvullende acties</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine-versie: &lt; Antimalware Engine &gt; versie</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Er is geen actie nodig. Microsoft Defender Antivirus taak met betrekking tot de herstel van malware is niet voltooid. Dit is geen kritieke fout.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1119</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Op het antimalwareplatform is een kritieke fout opgetreden bij het ondernemen van actie tegen malware of andere mogelijk ongewenste software. Er zijn meer details in het gebeurtenisbericht.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een kritieke fout opgetreden bij het ondernemen van actie tegen malware of andere mogelijk ongewenste software.<br/>Zie de volgende onderwerpen voor meer informatie:
<dl>
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:<ul>
<li>Laag</li>
<li>Gemiddeld</li>
<li>Hoog</li>
<li>Ernstig</li>
</ul>
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:
<ul>
<li>Unknown</li>
<li>Lokale computer</li>
<li>Netwerk delen</li>
<li>Internet</li>
<li>Binnenkomend verkeer</li>
<li>Uitgaand verkeer</li>
</ul>
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Beton</li>
<li>Dynamische handtekening</li>
</ul>
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:<ul>
<li>Gebruiker: gebruiker gestart</li>
<li>Systeem: systeem gestart</li>
<li>Realtime: in realtime gestarte component</li>
<li>IOAV: IE Downloads and Outlook Express Attachments initiated</li>
<li>NIS: Netwerkcontrolesysteem</li>
<li>IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</li>
<li>Early Launch Antimalware (ELAM). Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</li>
<li>Externe bevestiging</li>
</ul>Antimalware Scan Interface (AMSI). Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.
</dt>
<dt>UAC-gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; PID-actie:</dt> 
<dt> &lt; &gt; Actie, bijvoorbeeld:<ul>
<li>Schoon: De resource is opgeschoond</li>
<li>Quarantaine: De resource is in quarantaine geplaatst</li>
<li>Verwijderen: De resource is verwijderd</li>
<li>Toestaan: De resource is toegestaan om uit te voeren/te bestaan</li>
<li>Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</li>
<li>Geen actie: geen actie</li>
<li>Blokkering: De resource is geblokkeerd voor het uitvoeren van</li>
</ul>
</dt>
<dt>Actiestatus: &lt; Beschrijving van &gt; aanvullende acties</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine-versie: &lt; Antimalware Engine &gt; versie</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
De Microsoft Defender Antivirus client heeft deze fout ondervonden vanwege kritieke problemen. Het eindpunt is mogelijk niet beveiligd. Bekijk de foutbeschrijving en volg de onderstaande <b>actiestappen</b> voor gebruikers.
<table>
<tr>
<th>Actie</th>
<th>Actie voor gebruikers</th>
</tr>
<tr>
<td>
<b>Verwijderen</b>
</td>
<td>
Werk de definities bij en controleer of de verwijdering is gelukt.
</td>
</tr>
<tr>
<td>
<b>Opruimen</b>
</td>
<td>
Werk de definities bij en controleer of de herstelslag is gelukt.
</td>
</tr>
<tr>
<td>
<b>Quarantaine</b>
</td>
<td>
Werk de definities bij en controleer of de gebruiker toestemming heeft om toegang te krijgen tot de benodigde resources.
</td>
</tr>
<tr>
<td>
<b>Toestaan</b>
</td>
<td>
Controleer of de gebruiker toestemming heeft om toegang te krijgen tot de benodigde resources.
</td>
</tr>
</table>

Als deze gebeurtenis blijft bestaan:<ol>
<li>Voer de scan opnieuw uit.</li>
<li>Als het op dezelfde manier mislukt, gaat u naar de <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-site</a>en voert u het foutnummer in het vak Zoeken in om te zoeken naar de foutcode.</li>
<li>Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1120</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_THREAT_HASH</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Microsoft Defender Antivirus heeft de hashes voor een bedreigingsbron afgeleid.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus client is in een gezonde staat actief.
<dl>
<dt>Huidige platformversie: &lt; Huidige platformversie &gt; </dt>
<dt>Threat Resource Path: &lt; Path &gt; </dt>
<dt>Hashes: &lt; Hashes &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>Opmerking: Deze gebeurtenis wordt alleen geregistreerd als het volgende beleid is ingesteld: <b>ThreatFileHashLogging unsigned</b>.</div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 1150</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Als uw antimalwareplatform de status rapporteert aan een monitoringplatform, geeft deze gebeurtenis aan dat het antimalwareplatform actief is en in een goede staat is. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus client is in een gezonde staat actief.
<dl>
<dt>Platformversie: &lt; Huidige platformversie &gt; </dt>
<dt>Signature Version: Definition &lt; version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Er is geen actie nodig. De Microsoft Defender Antivirus client is in een gezonde staat. Deze gebeurtenis wordt op uurbasis gerapporteerd.
</td>
</tr>

<tr>
<th colspan="2">Gebeurtenis-id: 1151</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Endpoint Protection client health report (time in UTC)</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Rapport over de status van de antivirusclient.
<dl>
<dt>Platformversie: &lt; Huidige platformversie &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine &gt; </dt>version
<dt>Network Realtime Inspection engine &lt; &gt; version: Network Realtime Inspection</dt>engine Antivirus signature
<dt>version: Antivirus &lt; &gt; signature</dt>version
<dt>Antispyware signature version: &lt; &gt; </dt>
<dt> &lt; &gt; </dt>Antispyware signature version Network Realtime Inspection signature version: Network Realtime Inspection signature version
<dt>RTP state: &lt; Realtime protection state &gt; (Enabled of Uitgeschakeld)</dt>OA-status: Status VAN Access (ingeschakeld of
<dt> &lt; &gt; uitgeschakeld)</dt>
<dt>IOAV-status: IE Downloads and Outlook Express Attachments state &lt; &gt; (Enabled</dt>or Disabled) BM
<dt>state: Behavior Monitoring state &lt; &gt; (Enabled</dt>or Disabled) Antivirus signature age: Antivirus signature
<dt>age &lt; &gt; (in days) </dt> 
<dt>Antispyware signature age: &lt; Antispyware signature age &gt; (in days)</dt>Last quick scan age: Last
<dt>quick scan age &lt; &gt; (in days)</dt>
<dt>Last full scan age: Last full scan &lt; age &gt; (in days)</dt>
<dt>Antivirus signature creation time: ? &lt; Tijd voor &gt; het maken van</dt>
<dt>antivirushandtekeningen Antispyware-handtekening: ? &lt; Antispyware signature &gt; creation time Last</dt>
<dt>quick scan start time: ? &lt; Laatste begintijd &gt; snelle scan Laatste</dt>
<dt>eindtijd snelle scan: ? &lt; &gt;</dt>Laatste eindtijd snelle scan Laatste snelle scanbron: Laatste snelle scanbron
<dt> &lt; (0 = scan&#39;niet &gt; uitgevoerd, 1 = gebruiker gestart, 2 =</dt>systeem gestart) Laatste volledige begintijd van de
<dt>scan: ? &lt; Laatste volledige begintijd &gt; van de scan</dt>Laatste volledige
<dt>eindtijd van de scan: ? &lt; &gt;</dt>Laatste volledige eindtijd van de scan Laatste volledige scanbron: Laatste volledige
<dt> &lt; scanbron &gt; (0 = scan&#39;niet uitgevoerd, 1 = gebruiker gestart, 2 =</dt>systeem gestart) Productstatus: Voor interne probleemoplossing 
<dt>
</dl>
</td>
</tr>

<tr>
<th colspan="2">Gebeurtenis-id: 2000</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalwaredefinities zijn bijgewerkt. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Antivirushandtekeningsversie is bijgewerkt.
<dl>
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt>
<dt>Vorige handtekeningversie: Handtekeningtype &lt; &gt; </dt>vorige handtekeningversie: type 
<dt> &lt; &gt; handtekening, bijvoorbeeld: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netwerkcontrolesysteem</li>
</ul>
</dt>
<dt>Type update: &lt; Updatetype &gt; , volledig of Delta.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Er is geen actie nodig. De Microsoft Defender Antivirus client is in een gezonde staat. Deze gebeurtenis wordt gerapporteerd wanneer handtekeningen zijn bijgewerkt.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2001</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De beveiligingsintelligentieupdate is mislukt. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het bijwerken van handtekeningen.
<dl>
<dt>Nieuwe versie van beveiligingsinformatie: &lt; Nieuw versienummer &gt; </dt>
<dt>Vorige versie van beveiligingsinformatie: Vorige &lt; versie &gt; </dt> 
<dt> Updatebron: &lt; &gt; Updatebron, bijvoorbeeld:
<ul>
<li>Updatemap voor beveiligingsinformatie</li>
<li>Interne beveiligingsinformatieupdateserver</li>
<li>Microsoft Update Server</li>
<li>Bestands delen</li>
<li>Microsoft Centrum voor beveiliging tegen schadelijke software (MMPC)</li>
</ul>
</dt>
<dt>Updatefase: &lt; &gt; Updatefase, bijvoorbeeld:
<ul>
<li>Zoeken</li>
<li>Downloaden</li>
<li>Installeren</li>
</ul>
</dt>
<dt>Bronpad: Bestandsaandeelnaam voor Unc (Universal Naming Convention), servernaam voor Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Type handtekening: &lt; type &gt; handtekening, bijvoorbeeld: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netwerkcontrolesysteem</li>
</ul>
</dt>
<dt>Type update: &lt; Updatetype &gt; , volledig of Delta.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Deze fout treedt op wanneer er een probleem is met het bijwerken van definities.
Problemen met deze gebeurtenis oplossen:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Werk definities</a> bij en dwing een rescan rechtstreeks op het eindpunt af.</li>
<li>Bekijk de vermeldingen in het bestand %Windir%\WindowsUpdate.log voor meer informatie over deze fout.</li>
<li>Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2002</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine is bijgewerkt. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus engine-versie is bijgewerkt.
<dl>
<dt>Huidige engine-versie: &lt; Huidige engine &gt; versie</dt>
<dt>Vorige engine versie: Vorige engine &lt; versie &gt; </dt>Engine
<dt>Type: Engine type , ofwel &lt; &gt; antimalware engine of Network Inspection System engine.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Er is geen actie nodig. De Microsoft Defender Antivirus client is in een gezonde staat. Deze gebeurtenis wordt gerapporteerd wanneer de antimalware-engine is bijgewerkt.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2003</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De update van de antimalware-engine is mislukt. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het bijwerken van de engine.
<dl>
<dt>Nieuwe engineversie:</dt>
<dt>vorige engineversie: vorige &lt; &gt; motorversie</dt>
<dt>Motortype: &lt; Motortype , &gt; antimalware-engine of Network Inspection System-engine.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
De Microsoft Defender Antivirus clientupdate is mislukt. Deze gebeurtenis treedt op wanneer de client zichzelf niet kan bijwerken. Deze gebeurtenis is meestal het gevolg van een onderbreking van de netwerkverbinding tijdens een update.
Problemen met deze gebeurtenis oplossen:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Werk definities</a> bij en dwing een rescan rechtstreeks op het eindpunt af.</li>
<li>Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2004</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Er is een probleem met het laden van antimalwaredefinities. De antimalware-engine probeert de laatst bekende goede set definities te laden.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het laden van handtekeningen en wordt geprobeerd terug te keren naar een bekende set handtekeningen.
<dl>
<dt>Handtekeningen Geprobeerd:</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine Version: &lt; Antimalware engine version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
De Microsoft Defender Antivirus client heeft geprobeerd het meest recente definitiebestand te downloaden en te installeren en is mislukt. Deze fout kan optreden wanneer de client een fout ondervindt tijdens het laden van de definities of als het bestand beschadigd is. Microsoft Defender Antivirus probeert terug te keren naar een bekende verzameling definities.
Problemen met deze gebeurtenis oplossen:
<ol>
<li>Start de computer opnieuw en probeer het opnieuw.</li>
<li>Download de meest recente definities van <a href="https://aka.ms/wdsi">de Microsoft-beveiligingsinformatie site.</a>
Opmerking: De grootte van het definitiebestand dat van de site is gedownload, kan groter zijn dan 60 MB en mag niet worden gebruikt als een langetermijnoplossing voor het bijwerken van definities.
</li>
<li>Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2005</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine kan niet worden geladen omdat het antimalwareplatform verouderd is. Het antimalware-platform laadt de laatst bekende goede antimalware-engine en probeert bij te werken.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus kan geen antimalware-engine laden omdat de huidige platformversie niet wordt ondersteund. Microsoft Defender Antivirus terug naar de laatste bekende goede engine en wordt een platformupdate geprobeerd.
<dl>
<dt>Huidige platformversie: &lt; huidige platformversie&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2006</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De platformupdate is mislukt. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het bijwerken van het platform.
<dl>
<dt>Huidige platformversie: &lt; Huidige platformversie &gt; </dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2007</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het platform is binnenkort verouderd. Download het nieuwste platform om de nieuwste beveiliging te behouden.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus binnenkort een nieuwere platformversie nodig om toekomstige versies van de antimalware-engine te ondersteunen. Download het nieuwste Microsoft Defender Antivirus platform om het beste beschermingsniveau te behouden dat beschikbaar is.
<dl>
<dt>Huidige platformversie: &lt; huidige platformversie&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2010</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine heeft de Dynamic Signature Service gebruikt om aanvullende definities te krijgen. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus <i>Dynamic Signature Service gebruikt om</i> extra handtekeningen op te halen om uw computer te beveiligen.
<dl>
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt> 
<dt> Handtekeningtype: &lt; type &gt; handtekening, bijvoorbeeld: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netwerkcontrolesysteem</li>
</ul>
</dt>
<dt>Huidige engine-versie: &lt; Huidige engineversie &gt; </dt> 
<dt> Dynamic Signature Type: Dynamisch &lt; &gt; handtekeningtype, bijvoorbeeld:
<ul>
<li>Versie</li>
<li>Tijdstempel</li>
<li>Geen limiet</li>
<li>Duur</li>
</ul>
</dt>
<dt>Persistentiepad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature
<dt>Compilatie Timestamp: &lt; Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistent limit type , &gt; bijvoorbeeld:
<ul>
<li>VDM-versie</li>
<li>Tijdstempel</li>
<li>Geen limiet</li>
</ul>
</dt>
<dt>Persistentielimiet: persistentielimiet van de fastpath-handtekening.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2011</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De Dynamische handtekeningservice heeft de verouderd dynamische definities verwijderd. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus <i>Dynamic Signature Service gebruikt om</i> verouderde handtekeningen te verwijderen.
<dl>
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt> 
<dt> Handtekeningtype: &lt; type &gt; handtekening, bijvoorbeeld: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netwerkcontrolesysteem</li>
</ul>
</dt>
<dt>Huidige engine-versie: &lt; Huidige engineversie &gt; </dt> 
<dt> Dynamic Signature Type: Dynamisch &lt; &gt; handtekeningtype, bijvoorbeeld:
<ul>
<li>Versie</li>
<li>Tijdstempel</li>
<li>Geen limiet</li>
<li>Duur</li>
</ul>
</dt>
<dt>Persistentiepad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature
<dt>Compilatie Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistent Limit Type: Persistent limit type , &lt; &gt; bijvoorbeeld:
<ul>
<li>VDM-versie</li>
<li>Tijdstempel</li>
<li>Geen limiet</li>
</ul>
</dt>
<dt>Persistentielimiet: persistentielimiet van de fastpath-handtekening.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Er is geen actie nodig. De Microsoft Defender Antivirus client is in een gezonde staat. Deze gebeurtenis wordt gerapporteerd wanneer de dynamische handtekeningservice de actuele dynamische definities verwijdert.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2012</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine heeft een foutmelding ondervonden bij het gebruik van de Dynamic Signature Service. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het gebruik van <i>Dynamic Signature Service.</i>
<dl>
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt> 
<dt> Handtekeningtype: &lt; type &gt; handtekening, bijvoorbeeld: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netwerkcontrolesysteem</li>
</ul>
</dt>
<dt>Huidige engine-versie: &lt; Huidige engine-versie &gt; </dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt> Type dynamische handtekening: &lt; dynamisch &gt; handtekeningtype, bijvoorbeeld:
<ul>
<li>Versie</li>
<li>Tijdstempel</li>
<li>Geen limiet</li>
<li>Duur</li>
</ul>
</dt>
<dt>Persistentiepad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature
<dt>Compilatie Timestamp: &lt; Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistent limit type , &gt; bijvoorbeeld:
<ul>
<li>VDM-versie</li>
<li>Tijdstempel</li>
<li>Geen limiet</li>
</ul>
</dt>
<dt>Persistentielimiet: persistentielimiet van de fastpath-handtekening.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Controleer de instellingen voor uw internetverbinding.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2013</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De Dynamische handtekeningservice heeft alle dynamische definities verwijderd. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus alle <i>dynamische handtekeningservicehandtekeningen</i> verwijderd.
<dl>
<dt>Huidige handtekeningversie: &lt; huidige handtekeningversie&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2020</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine heeft een schoon bestand gedownload. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus een schoon bestand gedownload.
<dl>
<dt>Bestandsnaam: &lt; Bestandsnaam &gt; Van het bestand.</dt> 
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt>
<dt>Current Engine Version: Current engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2021</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine kan geen schoon bestand downloaden. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het downloaden van een schoon bestand.
<dl>
<dt>Bestandsnaam: &lt; Bestandsnaam &gt; Van het bestand.</dt> 
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt>
<dt>Current Engine Version: Current engine &lt; version &gt; </dt>Error
<dt>Code: Error code Result code associated with &lt; threat &gt; status. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Controleer de instellingen voor uw internetverbinding.
De Microsoft Defender Antivirus client heeft een fout ondervonden bij het gebruik van de Dynamic Signature Service om de meest recente definities naar een specifieke bedreiging te downloaden. Deze fout wordt waarschijnlijk veroorzaakt door een probleem met de netwerkverbinding. 
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2030</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine is gedownload en is geconfigureerd om offline te worden uitgevoerd bij de volgende systeemstart.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus offline antivirusprogramma gedownload en geconfigureerd om bij de volgende herstart uit te voeren.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2031</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine kan een offlinescan niet downloaden en configureren.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is een fout opgetreden bij het downloaden en configureren van offline antivirusprogramma's.
<dl>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2040</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Antimalware-ondersteuning voor deze versie van het besturingssysteem eindigt binnenkort. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
De ondersteuning voor uw besturingssysteem verloopt binnenkort. Het Microsoft Defender Antivirus uitvoeren op een niet-ondersteunend besturingssysteem is geen geschikte oplossing om u te beschermen tegen bedreigingen.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2041</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_OS_EOL </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De ondersteuning voor antimalware voor dit besturingssysteem is beëindigd. U moet het besturingssysteem upgraden voor verdere ondersteuning. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
De ondersteuning voor uw besturingssysteem is verlopen. Het Microsoft Defender Antivirus uitvoeren op een niet-ondersteunend besturingssysteem is geen geschikte oplossing om u te beschermen tegen bedreigingen.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 2042</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine ondersteunt dit besturingssysteem niet meer en beschermt uw systeem niet meer tegen malware. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
De ondersteuning voor uw besturingssysteem is verlopen. Microsoft Defender Antivirus wordt niet meer ondersteund op uw besturingssysteem, werkt niet meer en beschermt niet meer tegen malwaredreigingen.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 3002</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Er is een fout opgetreden bij realtimebeveiliging en is mislukt.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus Real-Time Protection-functie is een fout opgetreden en is mislukt.
<dl>
<dt>Functie: &lt; &gt; Functie, bijvoorbeeld:
<ul>
<li>Op Access</li>
<li>Internet Explorer-downloads en Microsoft Outlook Express-bijlagen</li>
<li>Gedragscontrole</li>
<li>Netwerkcontrolesysteem</li>
</ul>
</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Reden: De reden Microsoft Defender Antivirus realtimebeveiliging een functie opnieuw heeft gestart.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Start het systeem opnieuw op en voer een volledige scan uit omdat&#39;mogelijk dat het systeem enige tijd niet is beveiligd.
De Microsoft Defender Antivirus client&#39;in realtime beveiligingsfunctie is een fout opgetreden omdat een van de services niet kon worden begonnen. Als dit wordt gevolgd door een gebeurtenis-id van 3007, is de fout tijdelijk en is de antimalwareclient hersteld van de fout. 
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 3007</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Realtimebeveiliging hersteld van een fout. Het is raadzaam een volledige systeemscan uit te voeren wanneer u deze fout ziet. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus Real-time Protection heeft een functie opnieuw gestart. U wordt aangeraden een volledige systeemscan uit te voeren om items te detecteren die mogelijk zijn gemist terwijl deze agent in de problemen was.
<dl>
<dt>Functie: &lt; &gt; Functie, bijvoorbeeld:
<ul>
<li>Op Access</li>
<li>IE-downloads en Outlook Express-bijlagen</li>
<li>Gedragscontrole</li>
<li>Netwerkcontrolesysteem</li>
</ul>
</dt>
<dt>Reden: De reden Microsoft Defender Antivirus realtimebeveiliging een functie opnieuw heeft gestart.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
De realtimebeveiligingsfunctie is opnieuw gestart. Als deze gebeurtenis zich opnieuw voordeed, neem dan contact op <a href="https://go.microsoft.com/fwlink/?LinkId=215491">met de technische ondersteuning van Microsoft.</a> 
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5000</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Realtime beveiliging is ingeschakeld. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus in realtime beveiligingsscans voor malware en andere mogelijk ongewenste software is ingeschakeld.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5001</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Realtimebeveiliging is uitgeschakeld. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus realtime beveiligingsscan voor malware en andere mogelijk ongewenste software is uitgeschakeld. 
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5004</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De configuratie voor realtimebeveiliging is gewijzigd. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus de configuratie van realtimebeveiligingsfunctie is gewijzigd.
<dl>
<dt>Functie: &lt; &gt; Functie, bijvoorbeeld:
<ul>
<li>Op Access</li>
<li>IE-downloads en Outlook Express-bijlagen</li>
<li>Gedragscontrole</li>
<li>Netwerkcontrolesysteem</li>
</ul>
</dt>
<dt>Configuratie: </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5007</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De configuratie van het antimalwareplatform is gewijzigd.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus configuratie is gewijzigd. Als dit een onverwachte gebeurtenis is, moet u de instellingen controleren, omdat dit het gevolg kan zijn van malware.
<dl>
<dt>Oude waarde: &lt; Oud waardenummer &gt; Oude antivirusconfiguratiewaarde.</dt> 
<dt>Nieuwe waarde: &lt; Nieuw waardenummer &gt; Nieuwe antivirusconfiguratiewaarde.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5008</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>De antimalware-engine heeft een fout ondervonden en is mislukt.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus is beëindigd vanwege een onverwachte fout.
<dl>
<dt>Type fout: &lt; Type fout &gt; , bijvoorbeeld: Crash of Hang</dt>Exception
<dt>Code: &lt; Foutcode &gt; </dt>
<dt>Resource: &lt; Resource: Resource &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
Problemen met deze gebeurtenis oplossen:<ol>
<li>Probeer de service opnieuw te starten.<ul>
<li>Voor antimalware, antivirus en spyware typt u bij een verhoogde opdrachtprompt <b>netstop msmpsvc</b>en typt u <b>msmpsvc netstart</b> om de antimalware-engine opnieuw te starten.</li>
<li>Typ voor het netwerkcontrolesysteem <i>,</i>bij een opdrachtprompt met verhoogde opdracht, <b>netto start nissrv</b>en typ vervolgens <b>net start nissrv</b> om de engine Netwerkcontrolesysteem opnieuw te starten met behulp van het NiSSRV.exe-bestand. <i></i>
</li>
</ul>
</li>
<li>Als de fout op dezelfde manier mislukt, zoekt u de foutcode op door <b></b> toegang te krijgen tot de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-ondersteuningssite</a> en het foutnummer in te voeren in het vak Zoeken en contact op te nemen met de technische ondersteuning <a href="https://go.microsoft.com/fwlink/?LinkId=215491">van Microsoft.</a></li>
</ol>
</td>
</tr>
<tr>
<td>
Gebruikersactie:
</td>
<td >
De Microsoft Defender Antivirus client engine is gestopt vanwege een onverwachte fout.
Problemen met deze gebeurtenis oplossen:
<ol>
<li>Voer de scan opnieuw uit.</li>
<li>Als het op dezelfde manier mislukt, gaat u naar de <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-site</a>en voert u het foutnummer in het vak Zoeken in om te zoeken naar de foutcode.</li>
<li>Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5009</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Scannen op malware en andere mogelijk ongewenste software is ingeschakeld. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus scannen op malware en andere mogelijk ongewenste software is ingeschakeld.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5010</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Scannen op malware en andere mogelijk ongewenste software is uitgeschakeld.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus scannen op malware en andere mogelijk ongewenste software is uitgeschakeld.
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5011</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Scannen naar virussen is ingeschakeld.</b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus scannen op virussen is ingeschakeld. 
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5012</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het scannen van virussen is uitgeschakeld. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus scannen op virussen is uitgeschakeld. 
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5100</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalwareplatform verloopt binnenkort. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus heeft een respijtperiode ingevoerd en verloopt binnenkort. Na verloop van tijd schakelt dit programma de beveiliging tegen virussen, spyware en andere mogelijk ongewenste software uit.
<dl>
<dt>Vervaldatum: De reden waarom Microsoft Defender Antivirus verloopt.</dt> 
<dt>Vervaldatum: De datum waarop Microsoft Defender Antivirus verloopt.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Gebeurtenis-id: 5101</th>
</tr>
<tr><td>
Symbolische naam:
</td>
<td >
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</td>
</tr>
<tr>
<td>
Bericht:
</td>
<td >
<b>Het antimalware-platform is verlopen. </b>
</td>
</tr>
<tr>
<td>
Beschrijving:
</td>
<td >
Microsoft Defender Antivirus respijtperiode is verlopen. Beveiliging tegen virussen, spyware en andere mogelijk ongewenste software is uitgeschakeld.
<dl>
<dt>Vervaldatum: vervaldatum:</dt>
<dt> </dt> 
<dt>foutcode: &lt; foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
##Microsoft Defender Antivirus clientfoutcodes als Microsoft Defender Antivirus problemen krijgt, krijgt u meestal een foutcode om het probleem op te lossen. Meestal betekent een fout dat er een probleem is opgetreden bij het installeren van een update.
In deze sectie vindt u de volgende informatie over Microsoft Defender Antivirus clientfouten.
-   De foutcode -   De mogelijke reden voor de fout Advies over wat u nu moet -   doen

Gebruik de informatie in deze tabellen om problemen met foutcodes Microsoft Defender Antivirus oplossen.


<table> 
<tr>
<th colspan="2">Foutcode: 0x80508007</th>
</tr>
<tr>
<td>Bericht</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
Mogelijke reden
</td>
<td>
Deze fout geeft aan dat u mogelijk geen geheugen meer hebt. 
</td>
</tr>
<tr>
<td>Oplossing</td>
<td>
<ol>
<li>Controleer het beschikbare geheugen op uw apparaat.</li>
<li>Sluit ongebruikte toepassingen die worden uitgevoerd om geheugen vrij te maken op uw apparaat.</li>
<li>Start het apparaat opnieuw op en voer de scan opnieuw uit. 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x8050800C</th>
</tr><tr><td>Bericht</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat er mogelijk een probleem is met uw beveiligingsproduct.
</td>
</tr><tr><td>Oplossing</td><td>
<ol>
<li>Werk de definities bij. Een van de volgende:<ol>
<li>Klik op <b>de knop Definities</b> bijwerken op het <b>tabblad Bijwerken</b> in Microsoft Defender Antivirus. <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>Of:
</li>
<li>Download de meest recente definities van <a href="https://aka.ms/wdsi">de Microsoft-beveiligingsinformatie site.</a>
Opmerking: De grootte van het definitiebestand dat van de site is gedownload, kan groter zijn dan 60 MB en mag niet worden gebruikt als een langetermijnoplossing voor het bijwerken van definities.
</li>
</ol>
</li>
<li>Voer een volledige scan uit.
</li>
<li>Start het apparaat opnieuw en probeer het opnieuw.</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508020</th>
</tr><tr><td>Bericht</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat er mogelijk een motorconfiguratiefout is opgetreden. meestal is dit gerelateerd aan invoergegevens waardoor de engine niet goed kan functioneren. 
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x805080211
</th>
</tr><tr><td>Bericht</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat Microsoft Defender Antivirus bedreiging niet in quarantaine kan plaatsen. 
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508022
</th>
</tr><tr><td>Bericht</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat een herstart vereist is om het verwijderen van bedreigingen te voltooien. 
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>Bericht</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat de bedreiging mogelijk niet meer aanwezig is op de media, of dat malware u kan stoppen met het scannen van uw apparaat. 
</tr><tr><td>Oplossing
</td>
<td>
Voer de <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft-beveiligingsscanner</a> vervolgens uw beveiligingssoftware bij en probeer het opnieuw. 
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508024 </th></tr>
<tr>
<td>Bericht</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat een volledige systeemscan mogelijk is vereist. 
</td></tr>
<tr>
<td>Oplossing</td><td>
Voer een volledige systeemscan uit. 
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508025
</th>
</tr><tr><td>Bericht</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat handmatige stappen nodig zijn om het verwijderen van bedreigingen te voltooien. 
</td></tr><tr><td>Oplossing</td><td>
Volg de handmatige herstelstappen die worden beschreven in de <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>. U kunt een bedreigingsspecifieke koppeling vinden in de gebeurtenisgeschiedenis.<br/></td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508026
</th>
</tr><tr><td>Bericht</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat verwijdering binnen het containertype mogelijk niet wordt ondersteund. 
</td></tr><tr><td>Oplossing</td><td>
Microsoft Defender Antivirus is niet in staat om gedetecteerde bedreigingen in het archief te herstellen. U kunt de gedetecteerde resources handmatig verwijderen. 
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508027
</th>
</tr><tr><td>Bericht</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat het verwijderen van lage en gemiddelde bedreigingen mogelijk is uitgeschakeld. 
</td></tr><tr><td>Oplossing</td><td>
Controleer de gedetecteerde bedreigingen en los ze zo nodig op. 
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508029
</th>
</tr><tr><td>Bericht</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat u de bedreiging opnieuw moet scannen. 
</td></tr><tr><td>Oplossing</td><td>
Voer een volledige systeemscan uit. 
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508030
</th>
</tr><tr><td>Bericht</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat een offlinescan vereist is. 
</td></tr><tr><td>Oplossing</td><td>
Offline uitvoeren Microsoft Defender Antivirus. U kunt lezen hoe u dit doet in het offline Microsoft Defender Antivirus <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">artikel.</a>
</td>
</tr>
<tr>
<th colspan="2">Foutcode: 0x80508031
</th>
</tr><tr><td>Bericht</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>Mogelijke reden</td>
<td>
Deze fout geeft aan dat Microsoft Defender Antivirus de huidige versie van het platform niet ondersteunt en een nieuwe versie van het platform vereist. 
</td></tr><tr><td>Oplossing</td><td>
U kunt alleen Microsoft Defender Antivirus in Windows 10. Voor Windows 8, Windows 7 en Windows Vista kunt u <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection.</a><br/></td>
</tr>
</table>

<a id="internal-error-codes"></a>De volgende foutcodes worden gebruikt tijdens interne tests van Microsoft Defender Antivirus.

Als u deze fouten ziet, kunt u proberen definities [bij te](manage-updates-baselines-microsoft-defender-antivirus.md) werken en een rescan rechtstreeks op het eindpunt af te dwingen.


<table> 
<tr>
<th colspan="3">Interne foutcodes</th>
</tr>
<tr>
<th><b>Foutcode</b></th>
<th>Bericht weergegeven</th>
<th>Mogelijke reden voor fout en oplossing</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
Controleer uw internetverbinding en voer de scan opnieuw uit.
</td>
</tr>
<tr>
<td>
0x80501000
</td>
<td>
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E
</td>
<td rowspan="34">
Dit is een interne fout. De oorzaak is niet duidelijk gedefinieerd.
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
0x80501001
</td>
<td>
<b>ERROR_MP_ACTIONS_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80501002
</td>
<td>
<b>ERROR_MP_NOENGINE</b>
</td>
</tr>
<tr>
<td>
0x80501003
</td>
<td>
<b>ERROR_MP_ACTIVE_THREATS</b>
</td>
</tr>
<tr>
<td>
0x805011011
</td>
<td>
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</td>
</tr>
<tr>
<td>
0x80501101
</td>
<td>
<b>ERROR_LUA_CANCELLATION </b>
</td>
</tr>
<tr>
<td>
0x80501102
</td>
<td>
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</td>
</tr>
<tr>
<td>
0x80501103
</td>
<td>
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</td>
</tr>
<tr>
<td>
0x80501104
</td>
<td>
<b>MP_ERROR_CODE_CANCELLED</b>
</td>
</tr>
<tr>
<td>
0x80501105
</td>
<td>
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</td>
</tr>
<tr>
<td>
0x80501106
</td>
<td>
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</td>
</tr>
<tr>
<td>
0x80501107
</td>
<td>
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</td>
</tr>
<tr>
<td>
0x80501108
</td>
<td>
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</td>
</tr>
<tr>
<td>
0x80508001
</td>
<td>
<b>ERR_MP_BAD_INIT_MODULES</b>
</td>
</tr>
<tr>
<td>
0x80508002
</td>
<td>
<b>ERR_MP_BAD_DATABASE</b>
</td>
</tr>
<tr>
<td>
0x80508004
</td>
<td>
<b>ERR_MP_BAD_UFS </b>
</td>
</tr>
<tr>
<td>
0x8050800C
</td>
<td>
<b>ERR_MP_BAD_INPUT_DATA</b>
</td>
</tr>
<tr>
<td>
0x8050800D
</td>
<td>
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</td>
</tr>
<tr>
<td>
0x8050800E
</td>
<td>
<b>ERR_MP_OBSOLETE</b>
</td>
</tr>
<tr>
<td>
0x8050800F
</td>
<td>
<b>ERR_MP_NOT_SUPPORTED</b>
</td>
</tr>
<tr>
<td>
0x8050800F 0x80508010
</td>
<td>
<b>ERR_MP_NO_MORE_ITEMS </b>
</td>
</tr>
<tr>
<td>
0x80508011
</td>
<td>
<b>ERR_MP_DUPLICATE_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508012
</td>
<td>
<b>ERR_MP_BAD_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508013
</td>
<td>
<b>ERR_MP_BAD_USERDB_VERSION</b>
</td>
</tr>
<tr>
<td>
0x80508014
</td>
<td>
<b>ERR_MP_RESTORE_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80508016
</td>
<td>
<b>ERR_MP_BAD_ACTION</b>
</td>
</tr>
<tr>
<td>
0x80508019
</td>
<td>
<b>ERR_MP_NOT_FOUND</b>
</td>
</tr>
<tr>
<td>
0x80509001
</td>
<td>
<b>ERR_RELO_BAD_EHANDLE</b>
</td>
</tr>
<tr>
<td>
0x80509003
</td>
<td>
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</td>
</tr>
<tr>
<td>
0x8050A001
</td>
<td>
<b>ERR_MP_BADDB_OPEN</b>
</td>
</tr>
<tr>
<td>
0x8050A002
</td>
<td>
<b>ERR_MP_BADDB_HEADER</b>
</td>
</tr>
<tr>
<td>
0x8050A003
</td>
<td>
<b>ERR_MP_BADDB_OLDENGINE</b>
</td>
</tr>
<tr>
<td>
0x8050A004
</td>
<td>
<b>ERR_MP_BADDB_CONTENT </b>
</td>
</tr>
<tr>
<td>
0x8050A005
</td>
<td>
<b>ERR_MP_BADDB_NOTSIGNED</b>
</td>
</tr>
<tr>
<td>
0x8050801
</td>
<td>
<b>ERR_MP_REMOVE_FAILED</b>
</td>
<td>
Dit is een interne fout. Het kan worden geactiveerd wanneer het verwijderen van malware niet is gelukt. 
</td>
</tr>
<tr>
<td>
0x80508018
</td>
<td>
<b>ERR_MP_SCAN_ABORTED </b>
</td>
<td>
Dit is een interne fout. Het kan zijn geactiveerd wanneer een scan niet kan worden voltooid. 
</td>
</tr>
</table>

## <a name="related-topics"></a>Verwante onderwerpen

- [Rapport over Microsoft Defender Antivirus beveiliging](report-monitor-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)