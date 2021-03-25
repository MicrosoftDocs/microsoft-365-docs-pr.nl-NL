---
title: MicroFocus ArcSight configureren om Microsoft Defender voor eindpuntdetecties op te halen
description: MicroFocus ArcSight configureren voor het ontvangen en trekken van detecties vanuit het Microsoft Defender-beveiligingscentrum
keywords: MicroFocus ArcSight, beveiligingsinformatie- en evenementenbeheerhulpmiddelen configureren, boogsight
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
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166183"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>MicroFocus ArcSight configureren om Defender voor eindpuntdetecties op te halen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

U moet sommige bestanden en hulpprogramma's installeren en configureren om Micro Focus ArcSight te gebruiken, zodat defender voor eindpuntdetecties kan worden gebruikt.

>[!Note]
>- [Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties
>- [Defender for Endpoint Detection](api-portal-mapping.md) is samengesteld uit de verdachte gebeurtenis die zich heeft voorgedaan op het apparaat en de bijbehorende waarschuwingsgegevens.

## <a name="before-you-begin"></a>Voordat u begint

Voor het configureren van het hulpprogramma Micro Focus ArcSight Connector zijn verschillende configuratiebestanden nodig om detecties uit uw AAD-toepassing (Azure Active Directory) te halen en te parseren.

In deze sectie wordt u begeleid bij het verkrijgen van de benodigde informatie om de vereiste configuratiebestanden correct in te stellen en te gebruiken.

- Zorg ervoor dat u de siem-integratiefunctie hebt ingeschakeld in **het** menu Instellingen. Zie [SiEM-integratie inschakelen in Defender voor eindpunt](enable-siem-integration.md)voor meer informatie.

- Het bestand dat u hebt opgeslagen om de SIEM-integratiefunctie in te stellen, klaar hebben. U moet de volgende waarden krijgen:
  - Url voor vernieuwen van OAuth 2.0 Token
  - OAuth 2.0 Client-id
  - OAuth 2.0 Client secret

- De volgende configuratiebestanden gereed hebben:
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    U zou een ZIP-bestand met deze twee bestanden hebben opgeslagen wanneer u Micro Focus ArcSight hebt gekozen als het SIEM-type dat u in uw organisatie gebruikt.

- Zorg ervoor dat u de volgende tokens genereert en klaar hebt:
  - Access-token
  - Token vernieuwen

  U kunt deze tokens genereren vanuit de **sectie SIEM-integratie-instelling** van de portal.

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>MicroFocus ArcSight FlexConnector installeren en configureren

In de volgende stappen wordt ervan uitgenomen dat u alle vereiste stappen hebt voltooid in [Voordat u begint.](#before-you-begin)

1. Installeer het nieuwste 32-bits Windows FlexConnector-installatieprogramma. U vindt dit in het HPE-softwarecentrum. Het hulpprogramma wordt meestal geïnstalleerd op de volgende standaardlocatie: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</br></br>U kunt kiezen waar u het hulpprogramma wilt opslaan, bijvoorbeeld C: \\ *folder_location*\current\bin waar folder_location de installatielocatie vertegenwoordigt. 

2. Volg de installatiewizard door de volgende taken:
   - Inleiding
   - Map installeren kiezen
   - Installatieset kiezen
   - Snelkoppelingsmap kiezen
   - Overzicht van de installatie vóór de installatie
   - Installeren...

   U kunt de standaardwaarden voor elk van deze taken behouden of de selectie aanpassen aan uw vereisten.

3. Open Verkenner en zoek de twee configuratiebestanden die u hebt opgeslagen toen u de SIEM-integratiefunctie inschakelen. Zet de twee bestanden op de flexconnector-installatielocatie, bijvoorbeeld:

   - WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   - WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   > [!NOTE]
   > 
   > U moet de configuratiebestanden op deze locatie plaatsen, *folder_location* de locatie waar u het hulpprogramma hebt geïnstalleerd.

4. Nadat de installatie van de basisconnector is voltooid, wordt het venster Connector-instelling geopend. Selecteer in het venster Verbindingslijn instellen **de optie Verbindingslijn toevoegen.**

5. Selecteer Type: **ArcSight FlexConnector REST en** klik op **Volgende.**

6. Typ de volgende informatie in het formulier parameterdetails. Alle andere waarden in het formulier zijn optioneel en kunnen leeg worden gelaten.

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th>Veld</th>
    <th>Value</th>
    </tr>
    <tr>
    <td>Configuratiebestand</td>
    <td>Typ de naam van het eigenschapsbestand van de client. De naam moet overeenkomen met het bestand in de ZIP die u hebt gedownload.
Als het configuratiebestand in de flexagentmap bijvoorbeeld de naam &quot; &quot;WDATP-Connector.js&quot; onparser.properties, moet u &quot; &quot; WDATP-Connector typen als de naam van het &quot; clienteigenschappenbestand.</td>
    </tr>
    <td>GEBEURTENIS-URL</td>
    <td>Afhankelijk van de locatie van uw datacenter, selecteert u de URL van de EU of de VS: </br></br> <b>Voor DE EU</b>: https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br>
   </br><b>Voor vs:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br> <br> <b>Voor het</b>Verenigd Koninkrijk : https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</td>
    <tr>
    <td>Verificatietype</td>
    <td>OAuth 2</td>
    </tr>
    <td>OAuth 2 Clienteigenschappenbestand</td>
    <td>Blader naar de locatie van het <em>bestand wdatp-connector.properties.</em> De naam moet overeenkomen met het bestand in de ZIP die u hebt gedownload.</td>
    <tr>
    <td>Token vernieuwen</td>
    <td>U kunt een vernieuwings-token op twee manieren verkrijgen: door een vernieuwings-token te genereren vanaf de <b>pagina SIEM-instellingen</b> of door het hulpprogramma restutil te gebruiken. <br><br> Zie <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">SiEM-integratie in defender</a>voor <b></b> eindpunt inschakelen voor meer informatie over het genereren van een vernieuwingsken van de instelling Voorkeuren. </br> </br><b>Haal uw vernieuwings-token op met behulp van het hulpmiddel Restutil:</b> </br> a. Een opdrachtprompt openen. Ga naar C:\<em>folder_location</em>\current\bin <em>folder_location</em> de locatie waar u het hulpprogramma hebt geïnstalleerd. </br></br> b. Type: <code>arcsight restutil token -config</code> vanuit de adreslijst van de bin. Bijvoorbeeld: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Een webbrowservenster wordt geopend. </br> </br>c. Typ uw referenties en klik op het wachtwoordveld om de pagina om te leiden. Voer in de aanmeldingsprompt uw referenties in. </br> </br>d. In de opdrachtprompt wordt een vernieuwend token weergegeven. </br></br> e. Kopieer en plak het in het <b>veld Token</b> vernieuwen.
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. Er wordt een browservenster geopend door de verbindingslijn. Meld u aan met uw toepassingsreferenties. Nadat u zich hebt aanmelden, wordt u gevraagd toestemming te geven aan uw OAuth2-client. U moet toestemming geven aan uw OAuth 2-client, zodat de configuratie van de verbindingslijn kan worden geverifieerd.

   Als het <code>redirect_uri</code> een HTTPS-URL is, wordt u omgeleid naar een URL op de lokale host. U ziet een pagina met het verzoek om het certificaat te vertrouwen dat wordt geleverd door de connector die op de lokale host wordt uitgevoerd. U moet dit certificaat vertrouwen als de redirect_uri https is.
   
   Als u echter een http-URL opgeeft voor de redirect_uri, hoeft u geen toestemming te geven voor het vertrouwen van het certificaat.

8. Ga verder met de configuratie van de verbindingslijn door terug te keren naar het venster Micro Focus ArcSight Connector Setup.

9. Selecteer **ArcSight Manager (versleuteld)** als de bestemming en klik op **Volgende.**

10. Typ de doel-IP/hostnaam in **Manager Hostname** en uw referenties in het parametersformulier. Alle andere waarden in het formulier moeten worden behouden met de standaardwaarden. Klik op **Volgende**.

11. Typ een naam voor de verbindingslijn in het verbindingslijndetailformulier. Alle andere waarden in het formulier zijn optioneel en kunnen leeg worden gelaten. Klik op **Volgende**.

12. Het importcertificaatvenster van ESM Manager wordt weergegeven. Selecteer **Het certificaat importeren naar verbindingslijn van bestemming** en klik op **Volgende.** Het **venster Overzicht van verbindingslijn** toevoegen wordt weergegeven en het certificaat wordt geïmporteerd.

13. Controleer of de details in het venster Overzicht van **verbindingslijn** toevoegen juist zijn en klik vervolgens op **Volgende.**

14. Selecteer **Installeren als een service** en klik op **Volgende.**

15. Typ een naam in het **veld Interne naam van service.** Alle andere waarden in het formulier kunnen behouden blijven met de standaardwaarden of leeg blijven. Klik op **Volgende**.

16. Typ de serviceparameters en klik op **Volgende.** Er wordt een venster weergegeven **met het overzicht van de installatieservice.** Klik op **Volgende**.

17. U kunt de installatie voltooien door **Afsluiten en** Volgende **te selecteren.**

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>De Micro Focus ArcSight-console installeren en configureren

1. Volg de installatiewizard door de volgende taken:
   - Inleiding
   - Licentieovereenkomst
   - Speciale mededeling
   - ArcSight-installatiemap kiezen
   - Snelkoppelingsmap kiezen
   - Overzicht van de installatie vóór de installatie

2. Klik op **Installeren**. Nadat de installatie is voltooid, wordt de wizard ArcSight-consoleconfiguratie geopend.

3. Typ localhost in **Manager Host Name en** 8443 in Manager **Port** en klik vervolgens op **Volgende.**

4. Selecteer **Directe verbinding gebruiken** en klik vervolgens op **Volgende.**

5. Selecteer **Verificatie op basis van wachtwoord** en klik vervolgens op **Volgende.**

6. Selecteer **Dit is een installatie van één gebruiker. (Aanbevolen)** en klik vervolgens op **Volgende**.

7. Klik **op Klaar** om het installatieprogramma te stoppen.

8. Meld u aan bij de Micro Focus ArcSight-console.

9. **Navigeer naar Active channel set** New  >  **Condition**  >  **Device**  >  **Device Product**.

10. Apparaatproduct **instellen = Microsoft Defender ATP**. Wanneer u hebt geverifieerd dat gebeurtenissen naar het hulpprogramma lopen, stopt u het proces opnieuw en gaat u naar Windows Services en start u de ArcSight FlexConnector REST.

U kunt nu query's uitvoeren in de Micro Focus ArcSight-console.

Defender for Endpoint detections will appear as discrete events, with "Microsoft" as the vendor and "Windows Defender ATP" as the device name.


## <a name="troubleshooting-micro-focus-arcsight-connection"></a>Problemen met Micro Focus ArcSight-verbinding oplossen

**Probleem:** Het token kan niet worden vernieuwd. U vindt het logboek in C: \\ *folder_location*\current\logs waar folder_location de locatie vertegenwoordigt  waar u het hulpprogramma hebt geïnstalleerd. Open _agent.log en_ zoek naar `ERROR/FATAL/WARN` .

**Symptoom:** U krijgt het volgende foutbericht:

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**Oplossing:**

1. Stop het proces door in het venster Verbindingslijn op Ctrl +C te klikken. Klik **op Y** wanneer u wordt gevraagd 'Batch job Y/N beëindigen?'.

2. Ga naar de map waar u het bestand WDATP-connector.properties hebt opgeslagen en bewerk het bestand om de volgende waarde toe te voegen: `reauthenticate=true` .

3. Start de verbindingslijn opnieuw door de volgende opdracht uit te voeren: `arcsight.bat connectors` .

   Er wordt een browservenster weergegeven. Als u de verbindingslijn wilt laten uitvoeren, moet deze verdwijnen en moet de verbindingslijn nu worden uitgevoerd.

> [!NOTE]
> Controleer of de verbindingslijn wordt uitgevoerd door het proces opnieuw te stoppen. Start de verbindingslijn opnieuw en er wordt geen browservenster weergegeven.

## <a name="related-topics"></a>Verwante onderwerpen
- [SIEM-integratie inschakelen in Defender voor Eindpunt](enable-siem-integration.md)
- [Detecties naar uw SIEM-hulpprogramma's trekken](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [Defender voor eindpuntdetecties trekken met BEHULP van REST API](pull-alerts-using-rest-api.md)
- [Problemen met de integratie van SIEM-hulpprogramma's oplossen](troubleshoot-siem.md)
