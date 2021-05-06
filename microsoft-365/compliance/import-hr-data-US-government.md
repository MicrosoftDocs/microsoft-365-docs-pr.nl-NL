---
title: Een connector instellen voor het importeren van HR-gegevens in de cloud van de Amerikaanse overheid
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
ROBOTS: NOINDEX, NOFOLLOW
description: Beheerders in de cloud van de Amerikaanse overheid kunnen een gegevensconnector instellen om werknemersgegevens uit het HR-systeem van hun organisatie te importeren in Microsoft 365. Op deze manier kunt u HR-gegevens gebruiken in beleidsregels voor insiderrisicobeheer om activiteiten van specifieke gebruikers te detecteren die een interne bedreiging voor uw organisatie kunnen vormen.
ms.openlocfilehash: 16d6d72d557744e30d41795d5f8c8a17db81c6a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161765"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>Een connector instellen voor het importeren van HR-gegevens in de Amerikaanse overheid

U kunt een gegevensconnector instellen in het Microsoft 365 compliancecentrum om HR-gegevens (HR) te importeren in uw Amerikaanse overheidsorganisatie. HR-gerelateerde gegevens omvatten de datum waarop een werknemer zijn aftreding heeft ingediend en de datum van de laatste dag van de werknemer. Deze HR-gegevens kunnen vervolgens worden gebruikt door Microsoft-oplossingen voor informatiebeveiliging, zoals de oplossing voor [insiderrisicobeheer,](insider-risk-management.md)om uw organisatie te beschermen tegen schadelijke activiteiten of gegevensdiefstal binnen uw organisatie. Het instellen van een HR-connector bestaat uit het maken van een app in Azure Active Directory die wordt gebruikt voor verificatie door connector, het maken van een CSV-toewijzingsbestanden met uw HR-gegevens, het maken van een gegevensconnector in het compliancecentrum en het uitvoeren van een script (op een geplande basis) waarmee de HR-gegevens in het CSV-bestand worden opgenomen in de Microsoft-cloud. Vervolgens wordt de gegevensconnector gebruikt door het insider-hulpprogramma voor risicobeheer om toegang te krijgen tot de HR-gegevens die zijn geïmporteerd in uw Microsoft 365 amerikaanse overheidsorganisatie.

## <a name="before-you-begin"></a>Voordat u begint

- De gebruiker die de HR-connector maakt in stap 3, moet de rol Postvak importeren exporteren in Exchange Online. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een nieuwe rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

- U moet bepalen hoe u de gegevens uit het HR-systeem van uw organisatie (regelmatig) op haalt of exporteert en deze toevoegt aan het CSV-bestand dat wordt beschreven in stap 2. Met het script dat u in stap 4 hebt uitgevoerd, worden de HR-gegevens in het CSV-bestand geüpload naar de Microsoft-cloud.

- Met het voorbeeldscript dat u in stap 4 uitwerkt, worden HR-gegevens geüpload naar de Microsoft-cloud, zodat deze kunnen worden gebruikt door andere Microsoft-hulpprogramma's, zoals de oplossing voor insiderrisicobeheer. Dit voorbeeldscript wordt niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft. Het voorbeeldscript wordt geleverd als IS zonder enige garantie. Microsoft wijst alle impliciete garanties verder af, inclusief, zonder beperking, impliciete garanties van verkoopbaarheid of geschiktheid voor een bepaald doel. Het volledige risico dat voortvloeit uit het gebruik of de prestaties van het voorbeeldscript en de documentatie blijft bij u. In geen geval zijn Microsoft, de auteurs of anderen die betrokken zijn bij het maken, produceren of leveren van de scripts aansprakelijk voor enige schade (met inbegrip van, zonder beperking, schade voor verlies van bedrijfswinsten, bedrijfsonderbreking, verlies van bedrijfsgegevens of ander geldverlies) als gevolg van het gebruik van of het onvermogen om de voorbeeldscripts of documentatie te gebruiken, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Stap 1: Een app maken in Azure Active Directory

De eerste stap is het maken en registreren van een nieuwe app in Azure Active Directory (Azure AD). De app komt overeen met de HR-connector die u maakt in stap 3. Als u deze app maakt, kan Azure AD de HR-connector verifiëren wanneer deze wordt uitgevoerd en wordt geprobeerd toegang te krijgen tot uw organisatie. Deze app wordt ook gebruikt om het script te verifiëren dat u in stap 4 gebruikt om uw HR-gegevens te uploaden naar de Microsoft-cloud. Sla tijdens het maken van deze Azure AD-app de volgende informatie op. Deze waarden worden in latere stappen gebruikt.

- Azure AD-toepassings-id (ook wel *de app-id* *of client-id* genoemd)

- Azure AD-toepassingsgeheim (ook wel het *clientgeheim genoemd)*

- Tenant-id (ook wel *adreslijst-id* genoemd)

Zie Een toepassing registreren met de Microsoft identity platform voor stapsgewijs [instructies voor](/azure/active-directory/develop/quickstart-register-app)het maken van een app in Azure AD.

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>Stap 2: Een CSV-bestand voorbereiden met uw HR-gegevens

De volgende stap is het maken van een CSV-bestand met informatie over werknemers die uw organisatie hebben verlaten. Zoals uitgelegd in de sectie Voordat u begint, moet u bepalen hoe u dit CSV-bestand genereert vanuit het HR-systeem van uw organisatie. In het volgende voorbeeld ziet u een voltooid CSV-bestand (geopend in notitieblok) dat de drie vereiste parameters (kolommen) bevat. Het is veel gemakkelijker om het CSV-bestand te bewerken in Microsoft Excel.

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

De eerste rij of veldnamenrij van het CSV-bestand bevat de vereiste kolomnamen. De naam die in elke kolomkop wordt gebruikt, is aan u (de namen in het vorige voorbeeld zijn suggesties). Dezelfde kolomnamen die u in het  CSV-bestand gebruikt, moeten echter worden opgegeven wanneer u de HR-connector maakt in stap 3. Neem geen spaties op in de kolomnamen.

In de volgende tabel wordt elke kolom in het CSV-bestand beschreven:

| Kolomnaam | Beschrijving |
|:-----|:-----|
| **EmailAddress** <br/> |Hiermee geeft u het e-mailadres op van de beëindigde werknemer.|
| **Beëindigingsdatum** <br/> |Hiermee geeft u de datum op waarop het dienstverband van de persoon officieel is beëindigd in uw organisatie. Dit kan bijvoorbeeld de datum zijn waarop de werknemer heeft laten weten uw organisatie te verlaten. Deze datum kan de andere datum zijn dan de datum van de laatste werkdag van de persoon. Gebruik de volgende datumnotatie: de datum- en tijdnotatie `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|**LastWorkingDate**|Hiermee geeft u de laatste dag van het werk voor de beëindigde werknemer op. Gebruik de volgende datumnotatie: de datum- en tijdnotatie `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|||

Nadat u het CSV-bestand met de vereiste HR-gegevens hebt gemaakt, kunt u het opslaan op hetzelfde systeem als het script dat u in stap 4 hebt uitgevoerd. Zorg ervoor dat u een updatestrategie implementeert, zodat het CSV-bestand altijd de meest recente informatie bevat. Als u dit doet, worden de meest recente werknemersbeëindigingsgegevens geüpload naar de Microsoft-cloud.

## <a name="step-3-create-the-hr-connector"></a>Stap 3: De HR-connector maken

De volgende stap is het maken van een HR-connector in het Microsoft 365 compliancecentrum. Nadat u het script hebt uitgevoerd in stap 4, worden de HR-connector die u maakt, de HR-gegevens uit het CSV-bestand opgenomen in uw Microsoft 365 organisatie. Kopieer in deze stap de taak-id die wordt gegenereerd wanneer u de verbindingslijn maakt. U gebruikt de taak-id wanneer u het script uit te voeren.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik vervolgens op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectoren** onder **HR** op **Weergeven.**

3. Klik op **de pagina HR** op **Verbindingslijn toevoegen.**

4. Ga op **de pagina Verificatiereferenties** als volgt te werk en klik vervolgens op **Volgende:**

   1. Typ of plak de Azure AD-toepassings-id voor de Azure-app die u in stap 1 hebt gemaakt.

   1. Typ een naam voor de HR-connector.

5. Typ op **de pagina** Bestandstoewijzing de namen van de drie kolomkoppen (ook *wel parameters* genoemd) van het CSV-bestand dat u in stap 2 in elk van de juiste vakken hebt gemaakt. De namen zijn niet case-sensitive. Zoals eerder is uitgelegd, moeten de namen die u in deze vakken typt, overeenkomen met de parameternamen in uw CSV-bestand. In de volgende schermafbeelding ziet u bijvoorbeeld de parameternamen uit het voorbeeld in een CSV-voorbeeldbestand dat wordt weergegeven in stap 2.

   ![Kolomkoppen komen overeen met de namen in het CSV-bestand](../media/HRConnectorWizard3.png)

6. Controleer op **de pagina** Controleren uw instellingen en klik vervolgens **op Voltooien** om de verbindingslijn te maken.

   Er wordt een statuspagina weergegeven die bevestigt dat de verbindingslijn is gemaakt. Deze pagina bevat twee belangrijke dingen die u nodig hebt om de volgende stap uit te voeren om het voorbeeldscript uit te voeren om uw HR-gegevens te uploaden.

   ![Pagina controleren met taak-id en koppeling naar github voor voorbeeldscript](../media/HRConnector_Confirmation.png)

   1. **Taak-id.** U hebt deze taak-id nodig om het script in de volgende stap uit te voeren. U kunt deze kopiëren vanaf deze pagina of vanaf de flyoutpagina van de verbindingslijn.
   
   1. **Koppeling maken naar voorbeeldscript.** Klik op **de koppeling** hier om naar de GitHub site te gaan om het voorbeeldscript te openen (met de koppeling wordt een nieuw venster geopend). Houd dit venster open, zodat u het script kunt kopiëren in stap 4. U kunt ook een bladwijzer toevoegen aan de bestemming of de URL kopiëren, zodat u deze opnieuw kunt openen in stap 4. Deze koppeling is ook beschikbaar op de flyoutpagina van de verbindingslijn.

7. Klik op **Gereed**.

   De nieuwe verbindingslijn wordt weergegeven in de lijst op het **tabblad Connectors.** 

8. Klik op de HR-connector die u zojuist hebt gemaakt om de flyoutpagina weer te geven, die eigenschappen en andere informatie over de verbindingslijn bevat.

   ![Flyout-pagina voor nieuwe HR-connector](../media/HRConnectorWizard7.png)

   Als u dit nog niet hebt gedaan, kunt u de waarden voor de **azure-app-id** en **connector-taak-id kopiëren.** U hebt deze nodig om het script in de volgende stap uit te voeren. U kunt het script ook downloaden vanaf de flyoutpagina (of het downloaden via de koppeling in de volgende stap.)

   U kunt ook op **Bewerken klikken om** de Azure App-id of de kolomkopnamen te wijzigen die u hebt gedefinieerd op de pagina **Bestandstoewijzing.**

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Stap 4: Het voorbeeldscript uitvoeren om uw HR-gegevens te uploaden

De laatste stap bij het instellen van een HR-connector is het uitvoeren van een voorbeeldscript dat de HR-gegevens in het CSV-bestand (die u in stap 2 hebt gemaakt) naar de Microsoft-cloud uploadt. Met het script worden de gegevens geüpload naar de HR-connector. Nadat u het script hebt uitgevoerd, importeert de HR-connector die u hebt gemaakt in stap 3 de HR-gegevens naar uw Microsoft 365-organisatie waar deze toegankelijk zijn via andere compliancehulpmiddelen, zoals de Insider-oplossing voor risicobeheer. Nadat u het script hebt uitgevoerd, kunt u overwegen om een taak te plannen om deze automatisch dagelijks uit te voeren, zodat de meest recente werknemersbeëindigingsgegevens worden geüpload naar de Microsoft-cloud. Zie [Het script automatisch uitvoeren plannen.](#optional-step-6-schedule-the-script-to-run-automatically)

1. Ga naar het venster dat u hebt geopend vanaf de vorige stap om toegang te krijgen tot de GitHub site met het voorbeeldscript. U kunt ook de site met bladwijzers openen of de URL gebruiken die u hebt gekopieerd.

2. Klik op **de knop Raw** om het script weer te geven in de tekstweergave.

3. Kopieer alle regels in het voorbeeldscript en sla ze vervolgens op in een tekstbestand.

4. Wijzig indien nodig het voorbeeldscript voor uw organisatie.

5. Sla het tekstbestand op als Windows PowerShell scriptbestand met een bestandsnaamachtervoegsel van `.ps1` bijvoorbeeld `HRConnector.ps1` .

6. Open een opdrachtprompt op uw lokale computer en ga naar de adreslijst waar u het script hebt opgeslagen.

7. Voer de volgende opdracht uit om de HR-gegevens in het CSV-bestand te uploaden naar de Microsoft-cloud. bijvoorbeeld:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   In de volgende tabel worden de parameters beschreven die u wilt gebruiken met dit script en de vereiste waarden. De gegevens die u in de vorige stappen hebt verkregen, worden gebruikt in de waarden voor deze parameters.

   | Parameter | Beschrijving |
   |:-----|:-----|:-----|
   |`tenantId`|De id voor uw Microsoft 365 organisatie die u hebt verkregen in stap 1. U kunt ook de tenant-id voor uw organisatie verkrijgen op het **overzichtsblad** in het Azure AD-beheercentrum. Dit wordt gebruikt om uw organisatie te identificeren.|
   |`appId` |De Azure AD-toepassing-id voor de app die u hebt gemaakt in Azure AD in stap 1. Dit wordt door Azure AD gebruikt voor verificatie wanneer het script toegang probeert te krijgen tot uw Microsoft 365 organisatie. |
   |`appSecret`|Het geheim van de Azure AD-toepassing voor de app die u hebt gemaakt in Azure AD in stap 1. Dit wordt ook gebruikt voor verificatie.|
   |`jobId`|De taak-id voor de HR-connector die u hebt gemaakt in stap 3. Dit wordt gebruikt om de HR-gegevens die naar de Microsoft-cloud worden geüpload, te koppelen aan de HR-connector.|
   |`csvFilePath`|Het bestandspad voor het CSV-bestand (opgeslagen op hetzelfde systeem als het script) dat u hebt gemaakt in stap 2. Probeer spaties in het bestandspad te vermijden. gebruik anders enkele aanhalingstekens.|
   |||
   
   Hier is een voorbeeld van de syntaxis voor het HR-connectorscript met werkelijke waarden voor elke parameter:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Als het uploaden is gelukt, wordt in het script het **Upload bericht Geslaagd** weergegeven.

   > [!NOTE]
   > Als u problemen hebt met het uitvoeren [](/powershell/module/microsoft.powershell.core/about/about_execution_policies) van de vorige opdracht vanwege uitvoeringsbeleid, zie Over uitvoeringsbeleid en [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) voor informatie over het instellen van uitvoeringsbeleid.

## <a name="step-5-monitor-the-hr-connector"></a>Stap 5: De HR-connector controleren

Nadat u de HR-connector hebt gemaakt en het script hebt uitgevoerd om uw HR-gegevens te uploaden, kunt u de connector bekijken en de status uploaden in het Microsoft 365 compliancecentrum. Als u het script regelmatig automatisch wilt uitvoeren, kunt u ook de huidige status weergeven nadat het script voor het laatst is uitgevoerd.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de HR-verbindingslijn om de flyoutpagina weer te geven. Deze pagina bevat de eigenschappen en informatie over de verbindingslijn.

   ![FLYOUT-pagina HR-connector met eigenschappen en status](../media/HRConnectorFlyout1.png)

3. Klik **onder** Voortgang op de **koppeling Logboek downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat informatie over elke keer dat het script wordt uitgevoerd en uploadt de gegevens uit het CSV-bestand naar de Microsoft-cloud. 

   ![HET LOGBOEKBESTAND VAN HR-connector toont nummerrijen uit CSV-bestand die zijn geüpload](../media/HRConnectorLogFile.png)

   Het veld geeft het aantal rijen aan in het `RecordsSaved` CSV-bestand dat is geüpload. Als het CSV-bestand bijvoorbeeld vier rijen bevat, is de waarde van de velden 4, als het script alle rijen in het `RecordsSaved` CSV-bestand heeft geüpload.

Als u het script niet hebt uitgevoerd in stap 4, wordt een koppeling voor het downloaden van het script weergegeven onder **Laatst importeren.** U kunt het script downloaden en vervolgens de stappen in stap 4 volgen om het uit te voeren.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Optioneel) Stap 6: Het script automatisch laten uitvoeren

Om ervoor te zorgen dat de meest recente HR-gegevens van uw organisatie beschikbaar zijn voor hulpprogramma's zoals de oplossing voor insiderrisicobeheer, raden we u aan het script automatisch te plannen op terugkerende basis, zoals eenmaal per dag. Hiervoor moet u ook de HR-gegevens in het CSV-bestand bijwerken volgens een vergelijkbaar (zo niet hetzelfde) schema, zodat deze de meest recente informatie bevatten over werknemers die uw organisatie verlaten. Het doel is om de meest recente HR-gegevens te uploaden, zodat de HR-connector deze beschikbaar kan maken voor de insider-oplossing voor risicobeheer.

U kunt de app Taakplanning gebruiken in Windows om het script elke dag automatisch uit te voeren.

1. Klik op uw lokale computer op de Windows **startknop** en typ **vervolgens Taakplanning.**

2. Klik op **de app Taakplanning om** deze te openen.

3. Klik in **de sectie** Acties op **Taak maken.**

4. Typ op **het** tabblad Algemeen een beschrijvende naam voor de geplande taak. bijvoorbeeld HR **Connector Script**. U kunt ook een optionele beschrijving toevoegen.

5. Ga **als volgt te** werk onder Beveiligingsopties:

   1. Bepaal of u het script alleen wilt uitvoeren wanneer u bent aangemeld bij de computer of wanneer u bent aangemeld of niet.
   
   1. Controleer of het selectievakje **Uitvoeren met de hoogste bevoegdheden** is ingeschakeld.

6. Selecteer het **tabblad Triggers,** klik **op Nieuw** en ga vervolgens als volgt te werk:

   1. Selecteer **Instellingen** de optie  Dagelijks en kies een datum en tijd om het script voor het eerst uit te voeren. Het script wordt elke dag op dezelfde opgegeven tijd gebruikt.
   
   1. Controleer **onder Geavanceerde** instellingen of **het** selectievakje Ingeschakeld is ingeschakeld.
   
   1. Klik **op Ok**.

7. Selecteer het **tabblad** Acties, klik **op Nieuw** en ga als volgt te werk:

   ![Actie-instellingen voor het maken van een nieuwe geplande taak voor het hr-connectorscript](../media/HRConnectorScheduleTask1.png)

   1. Zorg ervoor **dat een** programma  starten is geselecteerd in de vervolgkeuzelijst Actie.

   1. Klik in **het vak Programma/script** op **Bladeren** en ga naar de volgende locatie en selecteer het pad zodat het pad wordt weergegeven in het vak: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   1. Plak in **het vak Argumenten toevoegen (optioneel)** dezelfde scriptopdracht die u hebt gebruikt in stap 4. Bijvoorbeeld: `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. Plak in **het vak Start in (optioneel)** de maplocatie van het script dat u hebt gebruikt in stap 4. Bijvoorbeeld `C:\Users\contosoadmin\Desktop\Scripts`.

   1. Klik **op Ok** om de instellingen voor de nieuwe actie op te slaan.

8. Klik in **het venster Taak** maken op Ok **om** de geplande taak op te slaan. Mogelijk wordt u gevraagd uw referenties voor uw gebruikersaccount in te voeren.

   De nieuwe taak wordt weergegeven in de bibliotheek Taakplanning.

   ![De nieuwe taak wordt weergegeven in de bibliotheek Taakplanning](../media/HRConnectorTaskSchedulerLibrary.png)

   De laatste keer dat het script is uitgevoerd en de volgende keer dat het wordt uitgevoerd, wordt weergegeven. U kunt dubbelklikken op de taak om deze te bewerken.

   U kunt ook controleren wanneer het script voor het laatst is gebruikt op de flyoutpagina van de bijbehorende HR-connector in het compliancecentrum.