---
title: Een verbindingslijn instellen om fysieke foutgegevens te importeren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Beheerders kunnen een gegevensconnector instellen om gegevens uit het fysieke systeem van hun organisatie te importeren in Microsoft 365. Op deze manier kunt u deze gegevens gebruiken in beleidsregels voor insiderrisicobeheer om u te helpen bij het detecteren van toegang tot uw fysieke gebouwen door specifieke gebruikers die een mogelijke interne bedreiging voor uw organisatie kunnen aangeven.
ms.openlocfilehash: a300107af1d3fe07f208f7e3f239f75a9cd6e5af
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/24/2021
ms.locfileid: "52162719"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Een connector instellen om fysieke foutgegevens te importeren (voorbeeld)

U kunt een gegevensconnector instellen in het Microsoft 365 compliancecentrum om fysieke foutgegevens te importeren, zoals de onbewerkte fysieke toegangsgebeurtenissen van werknemers of eventuele fysieke toegangsmeldingen die worden gegenereerd door het systeem voor slechte toegang van uw organisatie. Voorbeelden van fysieke toegangspunten zijn een toegang tot een gebouw of een toegang tot een serverruimte of datacenter. Fysieke foutgegevens kunnen worden gebruikt door de Microsoft 365 [insider risk management-oplossing](insider-risk-management.md) om uw organisatie te beschermen tegen schadelijke activiteiten of gegevensdiefstal binnen uw organisatie.

Het instellen van een fysieke verbindingslijn voor slechten bestaat uit de volgende taken:

- Een app maken in Azure Active Directory (Azure AD) om toegang te krijgen tot een API-eindpunt dat een JSON-payload accepteert die fysieke foutgegevens bevat.

- De JSON-payload maken met een schema dat is gedefinieerd door fysieke gegevensconnector.

- Een fysieke verbindingslijn voor slechtmakende gegevens maken in het Microsoft 365 compliancecentrum.

- Een script uitvoeren om de fysieke foutgegevens naar het API-eindpunt te pushen.

- Desgewenst kunt u plannen dat het script automatisch wordt uitgevoerd om momenteel fysieke foutgegevens te importeren.

## <a name="before-you-set-up-the-connector"></a>Voordat u de verbindingslijn in stelt

- Aan de gebruiker die de fysieke verbindingslijn voor slecht maken in stap 3 moet de rol Postvak importeren exporteren in Exchange Online. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een nieuwe rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

- U moet bepalen hoe u de gegevens op haalt of exporteert uit het fysieke systeem voor slecht werken van uw organisatie (dagelijks) en een JSON-bestand maakt dat wordt beschreven in stap 2. Met het script dat u in stap 4 hebt uitgevoerd, worden de gegevens in het JSON-bestand naar het API-eindpunt geleid.

- Met het voorbeeldscript dat u in stap 4 hebt uitgevoerd, worden de fysieke gegevens van het JSON-bestand naar de connector-API geleid, zodat deze kunnen worden gebruikt door de oplossing voor insiderrisicobeheer. Dit voorbeeldscript wordt niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft. Het voorbeeldscript wordt geleverd als IS zonder enige garantie. Microsoft wijst alle impliciete garanties verder af, inclusief, zonder beperking, impliciete garanties van verkoopbaarheid of geschiktheid voor een bepaald doel. Het volledige risico dat voortvloeit uit het gebruik of de prestaties van het voorbeeldscript en de documentatie blijft bij u. In geen geval zijn Microsoft, de auteurs of anderen die betrokken zijn bij het maken, produceren of leveren van de scripts aansprakelijk voor enige schade (met inbegrip van, zonder beperking, schade voor verlies van bedrijfswinsten, bedrijfsonderbreking, verlies van bedrijfsgegevens of ander geldverlies) als gevolg van het gebruik van of het onvermogen om de voorbeeldscripts of documentatie te gebruiken, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Stap 1: Een app maken in Azure Active Directory

De eerste stap is het maken en registreren van een nieuwe app in Azure Active Directory (Azure AD). De app komt overeen met de fysieke verbindingslijn die u maakt in stap 3. Als u deze app maakt, kan Azure AD de pushaanvraag voor JSON-payload met fysieke gegevens over slechte gegevens verifiëren. Sla tijdens het maken van deze Azure AD-app de volgende informatie op. Deze waarden worden in latere stappen gebruikt.

- Azure AD-toepassings-id (ook wel *de app-id* *of client-id* genoemd)

- Azure AD-toepassingsgeheim (ook wel het *clientgeheim genoemd)*

- Tenant-id (ook wel *adreslijst-id* genoemd)

Zie Een toepassing registreren met de Microsoft identity platform voor stapsgewijs [instructies voor](/azure/active-directory/develop/quickstart-register-app)het maken van een app in Azure AD.

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Stap 2: Een JSON-bestand voorbereiden met fysieke foutgegevens

De volgende stap is het maken van een JSON-bestand met informatie over de fysieke toegangsgegevens van werknemers. Zoals wordt uitgelegd in de sectie voordat u begint, moet u bepalen hoe u dit JSON-bestand genereert vanuit het fysieke systeem van uw organisatie.

Het JSON-bestand moet voldoen aan de schemadefinitie die door de verbindingslijn is vereist. Hier zijn beschrijvingen van de vereiste schemaeigenschappen voor het JSON-bestand:

|Eigenschap|Beschrijving|Gegevenstype|
|---|---|---|
|UserId|Een werknemer kan meerdere digitale identiteiten hebben in de systemen. De invoer moet de Azure AD-id al zijn opgelost door het bronsysteem.|UPN of e-mailadres|
|AssetId|De verwijzings-id van het fysieke activum of het fysieke toegangspunt.|Alfanumerieke tekenreeks|
|AssetName|De vriendelijke naam van het fysieke activum of het fysieke toegangspunt.|Alfanumerieke tekenreeks|
|EventTime|Het tijdstempel van toegang.|Datum en tijd, in UTC-indeling|
|AccessStatus|Waarde `Success` van of `Failed`|Tekenreeks|
|||

Hier is een voorbeeld van een JSON-bestand dat voldoet aan het vereiste schema:

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",
        "AccessStatus":"Success",
    }
]
```

U kunt ook de volgende schemadefinitie voor het JSON-bestand downloaden vanuit de wizard wanneer u de fysieke verbindingslijn voor slecht maken maakt in stap 3.

```text
{
   "title" : "Physical Badging Signals",
   "description" : "Access signals from physical badging systems",
   "DataType" : {
      "description" : "Identify what is the data type for input signal",
      "type" : "string",
   },
   "type" : "object",
   "properties": {
      "UserId" : {
         "description" : "Unique identifier AAD Id resolved by the source system",
         "type" : "string",
      },
      "AssetId": {
         "description" : "Unique ID of the physical asset/access point",
         "type" : "string",
      },
      "AssetName": {
         "description" : "friendly name of the physical asset/access point",
         "type" : "string",
      },
      "EventTime" : {
         "description" : "timestamp of access",
         "type" : "string",
      },
      "AccessStatus" : {
         "description" : "what was the status of access attempt - Success/Failed",
         "type" : "string",
      },
   }
   "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>Stap 3: de fysieke verbindingslijn maken

De volgende stap is het maken van een verbindingslijn voor fysieke problemen in het Microsoft 365 compliancecentrum. Nadat u het script hebt uitgevoerd in stap 4, wordt het JSON-bestand dat u hebt gemaakt in stap 3 verwerkt en naar het API-eindpunt dat u hebt geconfigureerd in stap 1. Kopieer in deze stap de JobId die wordt gegenereerd wanneer u de verbindingslijn maakt. U gebruikt de functie JobId wanneer u het script uit te voeren.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **Fysieke fout**, op **Weergave.**

3. Klik op **de pagina Fysieke fout** op **Verbindingslijn toevoegen.**

4. Ga op **de pagina Verificatiereferenties** als volgt te werk en klik vervolgens op **Volgende:**

   1. Typ of plak de Azure AD-toepassings-id voor de Azure-app die u in stap 1 hebt gemaakt.

   2. Download het voorbeeldschema voor uw verwijzing om het JSON-bestand te maken.

   3. Typ een unieke naam voor de fysieke verbindingslijn voor slechte eigenschappen.

5. Controleer op **de pagina** Controleren uw instellingen en klik vervolgens **op Voltooien** om de verbindingslijn te maken.

6. Er wordt een statuspagina weergegeven die bevestigt dat de verbindingslijn is gemaakt. Deze pagina bevat ook de taak-id. U kunt taak-id kopiëren vanaf deze pagina of vanaf de flyoutpagina voor de verbindingslijn. U hebt deze taak-id nodig bij het uitvoeren van het script.

   De statuspagina bevat ook een koppeling naar het script. Raadpleeg dit script voor meer informatie over het posten van het JSON-bestand naar het API-eindpunt.

7. Klik op **Gereed**.

   De nieuwe verbindingslijn wordt weergegeven in de lijst op het **tabblad Connectors.**

8. Klik op de fysieke verbindingslijn die u zojuist hebt gemaakt om de flyoutpagina weer te geven, die eigenschappen en andere informatie over de verbindingslijn bevat.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Stap 4: Voer het script uit om uw JSON-bestand met fysieke foutgegevens te posten

De volgende stap bij het instellen van een verbindingslijn voor fysieke problemen is het uitvoeren van een script dat de fysieke foutgegevens in het JSON-bestand (die u in stap 2 hebt gemaakt) naar het API-eindpunt dat u in stap 1 hebt gemaakt, zal pushen. We bieden een voorbeeldscript voor uw verwijzing en u kunt ervoor kiezen om het te gebruiken of uw eigen script te maken om het JSON-bestand te posten op het API-eindpunt.

Nadat u het script hebt uitgevoerd, wordt het JSON-bestand met de fysieke foutgegevens naar uw Microsoft 365 organisatie gebracht, waar het kan worden gebruikt door de insider-oplossing voor risicobeheer. We raden u aan om dagelijks fysieke foutgegevens te posten. U kunt dit doen door het proces te automatiseren om het JSON-bestand elke dag te genereren vanuit uw fysieke systeem met problemen en vervolgens het script te plannen om de gegevens te pushen.

> [!NOTE]
> Het maximum aantal records in het JSON-bestand dat door de API kan worden verwerkt, is 50.000 records.

1. Ga naar [deze GitHub site om](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) het voorbeeldscript te openen.

2. Klik op **de knop Raw** om het script weer te geven in de tekstweergave

3. Kopieer alle regels in het voorbeeldscript en sla ze vervolgens op in een tekstbestand.

4. Wijzig indien nodig het voorbeeldscript voor uw organisatie.

5. Sla het tekstbestand op als een Windows PowerShell scriptbestand met een achtervoegsel van een bestandsnaam van .ps1; bijvoorbeeld PhysicalBadging.ps1.

6. Open een opdrachtprompt op uw lokale computer en ga naar de adreslijst waar u het script hebt opgeslagen.

7. Voer de volgende opdracht uit om de fysieke foutgegevens in het JSON-bestand naar de Microsoft-cloud te pushen. bijvoorbeeld:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   In de volgende tabel worden de parameters beschreven die u wilt gebruiken met dit script en de vereiste waarden. De gegevens die u in de vorige stappen hebt verkregen, worden gebruikt in de waarden voor deze parameters.

   |Parameter|Beschrijving|
   |---|---|
   |tenantId|Dit is de id voor uw Microsoft 365 organisatie die u hebt verkregen in stap 1. U kunt ook de tenantId voor uw organisatie verkrijgen op het **overzichtsblad** in het Azure AD-beheercentrum. Dit wordt gebruikt om uw organisatie te identificeren.|
   |appId|Dit is de Azure AD-toepassing-id voor de app die u hebt gemaakt in Azure AD in stap 1. Dit wordt door Azure AD gebruikt voor verificatie wanneer het script toegang probeert te krijgen tot uw Microsoft 365 organisatie.|
   |appSecret|Dit is het Azure AD-toepassingsgeheim voor de app die u hebt gemaakt in Azure AD in stap 1. Dit wordt ook gebruikt voor verificatie.|
   |jobId|Dit is de taak-id voor de fysieke verbindingslijn die u hebt gemaakt in stap 3. Dit wordt gebruikt om de fysieke foutgegevens die naar de Microsoft-cloud worden geduwd, te koppelen aan de fysieke verbindingslijn voor slechten.|
   |JsonFilePath|Dit is het bestandspad op de lokale computer (het pad dat u gebruikt om het script uit te voeren) voor het JSON-bestand dat u hebt gemaakt in stap 2. Dit bestand moet het voorbeeldschema volgen dat is beschreven in stap 3.|
   |||

   Hier is een voorbeeld van de syntaxis voor het script voor de fysieke verbindingslijn met behulp van werkelijke waarden voor elke parameter:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Als het uploaden is gelukt, wordt in het script het **Upload bericht Geslaagd** weergegeven.

   Als u meerdere JSON-bestanden hebt, moet u het script voor elk bestand uitvoeren.

> [!NOTE]
> U kunt er ook voor kiezen om de fysieke foutgegevens naar het API-eindpunt te pushen met andere methoden dan het vorige script uit te voeren. Hier is bijvoorbeeld een voorbeeld voor het gebruik van Postman om uw gegevens naar het API-eindpunt te pushen.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Stap 5: De fysieke verbindingslijn controleren

Nadat u de fysieke verbindingslijn voor slecht maken en uw fysieke foutgegevens hebt opgeladen, kunt u de verbindingslijn bekijken en de status uploaden in het Microsoft 365 compliancecentrum. Als u het script regelmatig automatisch wilt uitvoeren, kunt u ook de huidige status weergeven nadat het script voor het laatst is uitgevoerd.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de fysieke verbindingslijn voor slechte verbindingen om de flyoutpagina weer te geven. Deze pagina bevat de eigenschappen en informatie over de verbindingslijn.

   ![Flyout-pagina status voor fysieke verbindingslijn](..\media\PhysicalBadgingStatusFlyout.png)

3. Klik **onder Laatst importeren** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat informatie over elke keer dat het script wordt uitgevoerd en uploadt de gegevens uit het CSV-bestand naar de Microsoft-cloud.

   ![Fysiek foutmeldingslogboekbestand van connector toont nummerrijen uit JSON-bestand die zijn geüpload](..\media\PhysicalBadgingConnectorLogFile.png)

   Het **veld RecordsSaved** geeft het aantal rijen aan in het CSV-bestand dat is geüpload. Als het CSV-bestand bijvoorbeeld vier rijen bevat, is de waarde van de **velden RecordsSaved** 4, als het script alle rijen in het CSV-bestand heeft geüpload.

Als u het script niet hebt uitgevoerd in stap 4, wordt een koppeling voor het downloaden van het script weergegeven onder **Laatst importeren.** U kunt het script downloaden en vervolgens de stappen in stap 4 volgen om het uit te voeren.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Optioneel) Stap 6: Het script automatisch laten uitvoeren

Om ervoor te zorgen dat de meest recente fysieke foutgegevens van uw organisatie beschikbaar zijn voor hulpprogramma's zoals de insider-oplossing voor risicobeheer, raden we u aan het script automatisch op terugkerende basis uit te voeren, bijvoorbeeld eenmaal per dag. Hiervoor moet u ook de fysieke foutgegevens bijwerken naar het JSON-bestand volgens een vergelijkbaar (zo niet hetzelfde) schema, zodat deze de meest recente informatie bevat over werknemers die uw organisatie verlaten. Het doel is om de meest recente fysieke foutgegevens te uploaden, zodat de fysieke verbindingslijn deze beschikbaar kan maken voor de insider-oplossing voor risicobeheer.

U kunt de app Taakplanning gebruiken in Windows om het script elke dag automatisch uit te voeren.

1. Klik op uw lokale computer op de Windows **startknop** en typ **vervolgens Taakplanning.**

2. Klik op **de app Taakplanning om** deze te openen.

3. Klik in **de sectie** Acties op **Taak maken.**

4. Typ op **het** tabblad Algemeen een beschrijvende naam voor de geplande taak. bijvoorbeeld het **script van fysieke verbindingslijn voor slechten**. U kunt ook een optionele beschrijving toevoegen.

5. Ga **onder Beveiligingsopties** als volgt te werk:

   1. Bepaal of u het script alleen wilt uitvoeren wanneer u bent aangemeld bij de computer of wanneer u bent aangemeld of niet.

   2. Controleer of het selectievakje **Uitvoeren met de hoogste bevoegdheden** is ingeschakeld.

6. Selecteer het **tabblad Triggers,** klik **op Nieuw** en ga vervolgens als volgt te werk:

   1. Selecteer **Instellingen** de optie  Dagelijks en kies een datum en tijd om het script voor het eerst uit te voeren. Het script wordt elke dag op dezelfde opgegeven tijd gebruikt.

   2. Controleer **onder Geavanceerde** instellingen of **het** selectievakje Ingeschakeld is ingeschakeld.

   3. Klik **op Ok**.

7. Selecteer het **tabblad** Acties, klik **op Nieuw** en ga als volgt te werk:

   ![Actie-instellingen voor het maken van een nieuwe geplande taak voor het script van de fysieke verbindingslijn](..\media\SchedulePhysicalBadgingScript1.png)

   1. Zorg ervoor **dat een** programma  starten is geselecteerd in de vervolgkeuzelijst Actie.

   2. Klik in **het vak Programma/script** op **Bladeren** en ga naar de volgende locatie en selecteer het pad zodat het pad wordt weergegeven in het vak: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. Plak in **het vak Argumenten toevoegen (optioneel)** dezelfde scriptopdracht die u hebt gebruikt in stap 4. Bijvoorbeeld: .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. Plak in **het vak Start in (optioneel)** de maplocatie van het script dat u hebt gebruikt in stap 4. Bijvoorbeeld: C:\Users\contosoadmin\Desktop\Scripts.

   5. Klik **op Ok** om de instellingen voor de nieuwe actie op te slaan.

8. Klik in **het venster Taak** maken op Ok **om** de geplande taak op te slaan. Mogelijk wordt u gevraagd uw referenties voor uw gebruikersaccount in te voeren.

   De nieuwe taak wordt weergegeven in de bibliotheek Taakplanning.

   ![De nieuwe taak wordt weergegeven in de bibliotheek Taakplanning](..\media\SchedulePhysicalBadgingScript2.png)

De laatste keer dat het script is uitgevoerd en de volgende keer dat het wordt uitgevoerd, wordt weergegeven. U kunt dubbelklikken op de taak om deze te bewerken.

U kunt ook controleren wanneer het script voor het laatst is gebruikt op de flyoutpagina van de bijbehorende fysieke verbindingslijn voor slechten in het compliancecentrum.
