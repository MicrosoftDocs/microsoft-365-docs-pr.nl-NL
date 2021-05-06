---
title: Een verbindingslijn instellen om HR-gegevens te importeren
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
description: Beheerders kunnen een gegevensconnector instellen om werknemersgegevens uit het HR-systeem van hun organisatie te importeren in Microsoft 365. Op deze manier kunt u HR-gegevens gebruiken in beleidsregels voor insiderrisicobeheer om activiteiten van specifieke gebruikers te detecteren die een interne bedreiging voor uw organisatie kunnen vormen.
ms.openlocfilehash: eb11eb5790ca9c585db8bbb95b41747a72e5c8f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161898"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>Een verbindingslijn instellen om HR-gegevens te importeren

U kunt een gegevensconnector instellen in het Microsoft 365 compliancecentrum om HR-gegevens (HR) te importeren die betrekking hebben op gebeurtenissen, zoals het aftreden van een gebruiker of een wijziging in het taakniveau van een gebruiker. De HR-gegevens kunnen vervolgens worden gebruikt door de [insider-oplossing](insider-risk-management.md) voor risicobeheer om risico-indicatoren te genereren die u kunnen helpen bij het identificeren van mogelijke schadelijke activiteiten of gegevensdiefstal door gebruikers binnen uw organisatie.

Het instellen van een connector voor HR-gegevens die door insiderrisicobeheerbeleid kan worden gebruikt om risico-indicatoren te genereren, bestaat uit het maken van een CSV-bestand dat de HR-gegevens bevat, het maken van een app in Azure Active Directory die wordt gebruikt voor verificatie, het maken van een HR-gegevensconnector in het Microsoft 365-compliancecentrum en het uitvoeren van een script (op een geplande basis) dat de HR-gegevens in CSV-bestanden in de Microsoft-cloud opslokt, zodat deze beschikbaar zijn voor de oplossing voor insiderrisicobeheer.

## <a name="before-you-begin"></a>Voordat u begint

- Bepaal welke HR-scenario's en gegevens u wilt importeren in Microsoft 365. Op deze manier kunt u bepalen hoeveel CSV-bestanden en HR-connectors u moet maken en hoe u de CSV-bestanden kunt genereren en structureren. De HR-gegevens die u importeert, worden bepaald door het beleid voor insiderrisicobeheer dat u wilt implementeren. Zie Stap 1 voor meer informatie.

- Bepaal hoe u de gegevens kunt ophalen of exporteren uit het HR-systeem van uw organisatie (en op regelmatige basis) en voeg deze toe aan de CSV-bestanden die u in stap 1 maakt. Het script dat u in stap 4 hebt uitgevoerd, uploadt de HR-gegevens in de CSV-bestanden naar de Microsoft-cloud.

- De gebruiker die de HR-connector maakt in stap 3, moet de rol Postvak importeren exporteren in Exchange Online. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een nieuwe rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

- Met het voorbeeldscript dat u in stap 4 hebt uitgevoerd, worden uw HR-gegevens geüpload naar de Microsoft-cloud, zodat deze kunnen worden gebruikt door de insider-oplossing voor risicobeheer. Dit voorbeeldscript wordt niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft. Het voorbeeldscript wordt geleverd als IS zonder enige garantie. Microsoft wijst alle impliciete garanties verder af, inclusief, zonder beperking, impliciete garanties van verkoopbaarheid of geschiktheid voor een bepaald doel. Het volledige risico dat voortvloeit uit het gebruik of de prestaties van het voorbeeldscript en de documentatie blijft bij u. In geen geval zijn Microsoft, de auteurs of anderen die betrokken zijn bij het maken, produceren of leveren van de scripts aansprakelijk voor enige schade (met inbegrip van, zonder beperking, schade voor verlies van bedrijfswinsten, bedrijfsonderbreking, verlies van bedrijfsgegevens of ander geldverlies) als gevolg van het gebruik van of het onvermogen om de voorbeeldscripts of documentatie te gebruiken, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>Stap 1: Een CSV-bestand voorbereiden met uw HR-gegevens

De eerste stap is het maken van een CSV-bestand met de HR-gegevens die de verbindingslijn importeert naar Microsoft 365. Deze gegevens worden door de insider-risicooplossing gebruikt om potentiële risico-indicatoren te genereren. Gegevens voor de volgende HR-scenario's kunnen worden geïmporteerd in Microsoft 365:

- Werknemer aftreding. Informatie over gebruikers die uw organisatie hebben verlaten.

- Wijzigingen op taakniveau. Informatie over wijzigingen op taakniveau voor gebruikers, zoals promoties en degradaties.

- Prestatiebeoordelingen. Informatie over de prestaties van gebruikers.

- Prestatieverbeteringsplannen. Informatie over prestatieverbeteringsplannen voor gebruikers.

Het type HR-gegevens dat u wilt importeren, is afhankelijk van het beleid voor insiderrisicobeheer en de bijbehorende beleidssjabloon die u wilt implementeren. In de volgende tabel ziet u welk HR-gegevenstype vereist is voor elke beleidssjabloon:

|  Beleidssjabloon |  HR-gegevenstype |
|:-----------------------------------------------|:---------------------------------------------------------------------|
| Gegevensdiefstal door vertrekkende gebruikers                   | Aftreding van werknemers                                                 |
| Algemene gegevenslekken                              | Niet van toepassing                                                        |
| Gegevenslekken door prioriteitsgebruikers                    | Niet van toepassing                                                        |
| Gegevenslekken door ontevreden gebruikers                 | Wijzigingen op functieniveau, Prestatiebeoordelingen, Prestatieverbeteringsplannen |
| Schendingen van het algemene beveiligingsbeleid              | Niet van toepassing                                                        |
| Schendingen van het beveiligingsbeleid door vertrekkende gebruikers   | Aftreding van werknemers                                                 |
| Schendingen van beveiligingsbeleid door gebruikers met prioriteit    | Niet van toepassing                                                        |
| Schendingen van beveiligingsbeleid door ontevreden gebruikers | Wijzigingen op functieniveau, Prestatiebeoordelingen, Prestatieverbeteringsplannen |
| Aanstootgevende taal in e-mail                     | Niet van toepassing                                                        |

Zie Insider-beleid voor risicobeheer voor meer informatie over beleidssjablonen voor [insiderrisicobeheer.](insider-risk-management-policies.md#policy-templates)

Voor elk HR-scenario moet u de bijbehorende HR-gegevens in een of meer CSV-bestanden verstrekken. Het aantal CSV-bestanden dat moet worden gebruikt voor de implementatie van uw insiderrisicobeheer, wordt later besproken in deze sectie.

Nadat u het CSV-bestand met de vereiste HR-gegevens hebt gemaakt, kunt u het opslaan op de lokale computer waarin u het script in stap 4 hebt uitgevoerd. U moet ook een updatestrategie implementeren om ervoor te zorgen dat het CSV-bestand altijd de meest recente informatie bevat, zodat de meest recente HR-gegevens worden geüpload naar de Microsoft-cloud en toegankelijk zijn voor de oplossing voor insiderrisicobeheer.

> [!IMPORTANT]
> De kolomnamen die in de volgende secties worden beschreven, zijn geen vereiste parameters, maar alleen voorbeelden. U kunt elke kolomnaam in uw CSV-bestanden gebruiken. De kolomnamen die u in een  CSV-bestand gebruikt, moeten echter worden toegesneden op het gegevenstype wanneer u de HR-connector maakt in stap 3. Houd er ook rekening mee dat de voorbeeld-CSV-bestanden in de volgende secties worden weergeven in de weergave Kladblok. Het is veel gemakkelijker om CSV-bestanden te bekijken en te bewerken in Microsoft Excel.

In de volgende secties worden de vereiste CSV-gegevens voor elk HR-scenario beschreven.

### <a name="csv-file-for-employee-resignation-data"></a>CSV-bestand voor gegevens over werknemersbetreding

Hier is een voorbeeld van een CSV-bestand voor werknemersgegevens.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

In de volgende tabel wordt elke kolom in het CSV-bestand beschreven voor gegevens over werknemersbezuiling.

|  Kolom   |   Beschrijving |
|:------------|:----------------|
|**EmailAddress**| Hiermee geeft u het e-mailadres (UPN) op van de beëindigde gebruiker.|
| **Aftredingsdatum** | Hiermee geeft u de datum op waarop de dienstverbanden van de gebruiker officieel zijn beëindigd in uw organisatie. Dit kan bijvoorbeeld de datum zijn waarop de gebruiker heeft laten weten uw organisatie te verlaten. Deze datum kan de andere datum zijn dan de datum van de laatste werkdag van de persoon. Gebruik de volgende datumnotatie: de datum- en tijdnotatie `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **LastWorkingDate** | Hiermee geeft u de laatste werkdag voor de beëindigde gebruiker op. Gebruik de volgende datumnotatie: de datum- en tijdnotatie `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|||

### <a name="csv-file-for-job-level-changes-data"></a>CSV-bestand voor taakniveau wijzigt gegevens

Hier is een voorbeeld van een CSV-bestand voor het wijzigen van gegevens op taakniveau.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

In de volgende tabel wordt elke kolom in het CSV-bestand beschreven voor wijzigingen in gegevens op taakniveau.

|  Kolom | Beschrijving |
|:--------- |:------------- |
| **EmailAddress**  | Hiermee geeft u het e-mailadres (UPN) van de gebruiker op.|
| **Effectieve datum** | Hiermee geeft u de datum op waarop het taakniveau van de gebruiker officieel is gewijzigd. Gebruik de volgende datumnotatie: de datum- en tijdnotatie `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Opmerkingen**| Hiermee geeft u de opmerkingen op die de beoordelaar heeft gegeven over de wijziging van het taakniveau. U kunt een limiet van 200 tekens invoeren. Deze parameter is optioneel. U hoeft het bestand niet op te nemen in het CSV-bestand.|
| **OldLevel**| Hiermee geeft u het taakniveau van de gebruiker op voordat deze is gewijzigd. Dit is een vrije-tekstparameter en kan hiërarchische taxonomie voor uw organisatie bevatten. Deze parameter is optioneel. U hoeft het bestand niet op te nemen in het CSV-bestand.|
| **NewLevel**| Hiermee geeft u het taakniveau van de gebruiker op nadat deze is gewijzigd. Dit is een vrije-tekstparameter en kan hiërarchische taxonomie voor uw organisatie bevatten. Deze parameter is optioneel. U hoeft het bestand niet op te nemen in het CSV-bestand.|
|||

### <a name="csv-file-for-performance-review-data"></a>CSV-bestand voor prestatiebeoordelingsgegevens

Hier is een voorbeeld van een CSV-bestand voor prestatiegegevens.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

In de volgende tabel wordt elke kolom in het CSV-bestand beschreven voor prestatiebeoordelingsgegevens.

|  Kolom | Beschrijving |
|:----------|:--------------|
| **EmailAddress**  | Hiermee geeft u het e-mailadres (UPN) van de gebruiker op.|
| **Effectieve datum** | Hiermee geeft u de datum op waarop de gebruiker officieel op de hoogte is gesteld van het resultaat van de prestatiebeoordeling. Dit kan de datum zijn waarop de cyclus voor prestatiebeoordeling is beëindigd. Gebruik de volgende datumnotatie: de datum- en tijdnotatie `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Opmerkingen**| Hiermee geeft u eventuele opmerkingen op die de beoordelaar aan de gebruiker heeft gegeven voor de prestatiebeoordeling. Dit is een tekstparameter met een limiet van 200 tekens. Deze parameter is optioneel. U hoeft het bestand niet op te nemen in het CSV-bestand.|
| **Beoordeling**| Hiermee geeft u de beoordeling op die is opgegeven voor de prestatiebeoordeling. Dit is een tekstparameter en kan vrije tekst bevatten die door uw organisatie wordt gebruikt om de evaluatie te herkennen. Bijvoorbeeld '3 Aan verwachtingen' of '2 onder het gemiddelde'. Dit is een tekstparameter met een limiet van 25 tekens. Deze parameter is optioneel. U hoeft het bestand niet op te nemen in het CSV-bestand.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>CSV-bestand voor prestatieverbeteringsplangegevens

Hier is een voorbeeld van een CSV-bestand voor de gegevens voor de gegevens van het prestatieverbeteringsplan.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

In de volgende tabel wordt elke kolom in het CSV-bestand beschreven voor prestatiebeoordelingsgegevens.

|  Kolom |  Beschrijving |
|:----------|:---------------|
| **EmailAddress**  | Hiermee geeft u het e-mailadres (UPN) van de gebruiker op.|
| **Effectieve datum** | Hiermee geeft u de datum op waarop de gebruiker officieel op de hoogte is gesteld van het prestatieverbeteringsplan. U moet de volgende datumnotatie gebruiken: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` de [iso 8601-datum- en tijdnotatie.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Opmerkingen**| Hiermee geeft u eventuele opmerkingen op die de beoordelaar heeft gegeven over het prestatieverbeteringsplan. Dit is een tekstparameter met een limiet van 200 tekens. Dit is een optionele parameter. U hoeft het bestand niet op te nemen in het CSV-bestand. |
| **Beoordeling**| Hiermee geeft u een beoordeling of andere informatie op die betrekking heeft op de prestatiebeoordeling. prestatieverbeteringsplan. Dit is een tekstparameter en kan vrije formuliertekst bevatten die door uw organisatie wordt gebruikt om de evaluatie te herkennen. Bijvoorbeeld '3 Aan verwachtingen' of '2 onder het gemiddelde'. Dit is een tekstparameter met een limiet van 25 tekens. Dit is een optionele parameter. U hoeft het bestand niet op te nemen in het CSV-bestand.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>Bepalen hoeveel CSV-bestanden moeten worden gebruikt voor HR-gegevens

In stap 3 kunt u ervoor kiezen om afzonderlijke connectors te maken voor elk HR-gegevenstype of u kunt ervoor kiezen om één verbindingslijn te maken voor alle gegevenstypen. U kunt afzonderlijke CSV-bestanden gebruiken die gegevens bevatten voor één HR-scenario (zoals de voorbeelden van de CSV-bestanden die in de vorige secties worden beschreven). U kunt ook één CSV-bestand gebruiken dat gegevens bevat voor twee of meer HR-scenario's. Hier volgen enkele richtlijnen om te bepalen hoeveel CSV-bestanden u moet gebruiken voor HR-gegevens.

- Als voor het insiderrisicobeheerbeleid dat u wilt implementeren meerdere HR-gegevenstypen nodig zijn, kunt u overwegen één CSV-bestand te gebruiken dat alle vereiste gegevenstypen bevat.

- De methode voor het genereren of verzamelen van de HR-gegevens kan het aantal CSV-bestanden bepalen. Als de verschillende typen HR-gegevens die worden gebruikt voor het configureren van een HR-connector zich bijvoorbeeld in één HR-systeem in uw organisatie bevinden, kunt u de gegevens mogelijk exporteren naar één CSV-bestand. Maar als gegevens over verschillende HR-systemen zijn verdeeld, is het mogelijk gemakkelijker om gegevens te exporteren naar verschillende CSV-bestanden. Werknemers kunnen zich bijvoorbeeld in een ander HR-systeem bevinden dan gegevens over functieniveau of Prestatiebeoordeling. In dit geval is het mogelijk gemakkelijker om afzonderlijke CSV-bestanden te hebben in plaats van de gegevens handmatig te combineren in één CSV-bestand. De manier waarop u gegevens uit uw HR-systemen op haalt of exporteert, kan dus bepalen hoe het aantal CSV-bestanden dat u nodig hebt.

- Over het algemeen wordt het aantal HR-connectors dat u moet maken bepaald door de gegevenstypen in een CSV-bestand. Als een CSV-bestand bijvoorbeeld alle gegevenstypen bevat die nodig zijn om uw implementatie van insiderrisicobeheer te ondersteunen, hebt u slechts één HR-connector nodig. Maar als u twee afzonderlijke CSV-bestanden hebt die elk één gegevenstype bevatten, moet u twee HR-connectors maken. Een uitzondering hierop is dat als u een **HRScenario-kolom** toevoegt aan een CSV-bestand (zie de volgende sectie), u één HR-connector kunt configureren die verschillende CSV-bestanden kan verwerken.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>Eén CSV-bestand configureren voor meerdere HR-gegevenstypen

U kunt meerdere HR-gegevenstypen toevoegen aan één CSV-bestand. Dit is handig als voor de insider-oplossing voor risicobeheer die u implementeert, meerdere HR-gegevenstypen zijn vereist of als de gegevenstypen zich in één HR-systeem in uw organisatie bevinden. Als u altijd minder CSV-bestanden hebt, kunt u minder HR-connectors maken en beheren.

Hier zijn vereisten voor het configureren van een CSV-bestand met meerdere gegevenstypen:

- U moet de vereiste kolommen toevoegen (en optioneel als u deze gebruikt) voor elk gegevenstype en de bijbehorende kolomnaam in de veldnamenrij. Als een gegevenstype niet overeenkomt met een kolom, kunt u de waarde leeg laten.

- Als u een CSV-bestand met meerdere typen HR-gegevens wilt gebruiken, moet de HR-connector weten welke rijen in het CSV-bestand hr-gegevens bevatten. Dit wordt gedaan door een extra **HRScenario-kolom** toe te voegen aan het CSV-bestand. De waarden in deze kolom bepalen het type HR-gegevens in elke rij. Waarden die overeenkomen met de vier HR-scenario's kunnen bijvoorbeeld \` \` Berusting, \` \` Functieniveauwijziging, \` Prestatiebeoordeling \` en \` Prestatieverbeteringsplan \` zijn.

- Als u meerdere CSV-bestanden hebt die een KOLOM HRScenario** bevatten, moet u ervoor zorgen dat elk bestand dezelfde kolomnaam en dezelfde waarden gebruikt die de specifieke HR-scenario's identificeren.

In het volgende voorbeeld ziet u een CSV-bestand dat de **kolom HRScenario** bevat. Met de waarden in de kolom HRScenario wordt het type gegevens in de bijbehorende rij bepaald.

```text
HRScenario,EmailAddress,ResignationDate,LastWorkingDate,EffectiveDate,Remarks,Rating,OldLevel,NewLevel
Resignation,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30,,,,
Resignation,pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540,,,,
Job level change,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 61 Sr. Manager, Level 60 Manager
Job level change,pillarp@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 62 Director,Level 60 Sr Manager
Performance review,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2 Below expectations,,
Performance review,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team,,
Performance improvement plan,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2 Below expectations,,
Performance improvement plan,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Multiple conflicts with the team,,
```

> [!NOTE]
> U kunt elke naam gebruiken voor de kolom die hr-gegevenstype identificeert, omdat u de naam van de kolom in het CSV-bestand in kaart brengt als de kolom die het gegevenstype HR identificeert wanneer u de verbindingslijn in stap 3 in stelt. U geeft ook de waarden toe die worden gebruikt voor de kolom gegevenstype wanneer u de verbindingslijn in stelt.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>De kolom HRScenario toevoegen aan een CSV-bestand dat één gegevenstype bevat

Op basis van de HR-systemen van uw organisatie en de manier waarop u HR-gegevens exporteert naar CSV-bestand, moet u mogelijk meerdere CSV-bestanden maken die één HR-gegevenstype bevatten. In dit geval kunt u nog steeds één HR-connector maken om gegevens uit verschillende CSV-bestanden te importeren. Hiervoor hoeft u alleen een KOLOM HRScenario toe te voegen aan het CSV-bestand en het gegevenstype HR op te geven. Vervolgens kunt u het script voor elk CSV-bestand uitvoeren, maar dezelfde taak-id gebruiken voor de verbindingslijn. Zie [Stap 4](#step-4-run-the-sample-script-to-upload-your-hr-data).

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Stap 2: Een app maken in Azure Active Directory

De volgende stap is het maken en registreren van een nieuwe app in Azure Active Directory (Azure AD). De app komt overeen met de HR-connector die u maakt in stap 3. Als u deze app maakt, kan Azure AD de HR-connector verifiëren wanneer deze wordt uitgevoerd en wordt geprobeerd toegang te krijgen tot uw organisatie. Deze app wordt ook gebruikt om het script te verifiëren dat u in stap 4 gebruikt om uw HR-gegevens te uploaden naar de Microsoft-cloud. Sla tijdens het maken van deze Azure AD-app de volgende informatie op. Deze waarden worden gebruikt in stap 3 en stap 4.

- Azure AD-toepassings-id (ook wel *de app-id* *of client-id* genoemd)

- Azure AD-toepassingsgeheim (ook wel het *clientgeheim genoemd)*

- Tenant-id (ook wel *adreslijst-id* genoemd)

Zie Een toepassing registreren met de Microsoft identity platform voor stapsgewijs [instructies voor](/azure/active-directory/develop/quickstart-register-app)het maken van een app in Azure AD.

## <a name="step-3-create-the-hr-connector"></a>Stap 3: De HR-connector maken

De volgende stap is het maken van een HR-connector in het Microsoft 365 compliancecentrum. Nadat u het script hebt uitgevoerd in stap 4, worden de HR-connector die u maakt, de HR-gegevens uit het CSV-bestand opgenomen in uw Microsoft 365 organisatie. Voordat u een verbindingslijn maakt, moet u ervoor zorgen dat u een lijst hebt met de HR-scenario's en de bijbehorende CSV-kolomnamen voor elke connector. U moet de gegevens die voor elk scenario zijn vereist, in kaart brengen aan de werkelijke kolomnamen in het CSV-bestand bij het configureren van de verbindingslijn. U kunt ook een voorbeeld-CSV-bestand uploaden bij het configureren van de verbindingslijn en met de wizard kunt u de naam van de kolommen aan de vereiste gegevenstypen toevoegen.

Nadat u deze stap hebt voltooid, moet u de taak-id kopiëren die wordt gegenereerd wanneer u de verbindingslijn maakt. U gebruikt de taak-id wanneer u het script uit te voeren.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectoren** onder **HR** op **Weergeven.**

3. Klik op **de pagina AANGEPAST** HR op **Verbindingslijn toevoegen.**

4. Ga op **de pagina Verbinding** instellen als volgt te werk en klik vervolgens op **Volgende:**

   1. Typ of plak de Azure AD-toepassings-id voor de Azure-app die u in stap 2 hebt gemaakt.

   1. Typ een naam voor de HR-connector.

5. Selecteer op de pagina HR-scenario's een of meer HR-scenario's waar u gegevens voor wilt importeren en klik vervolgens op **Volgende.**

6. Selecteer op de pagina bestandstoewijzingsmethode een van de volgende opties en klik vervolgens op **Volgende.**

   - **Upload een voorbeeldbestand**. Als u deze optie selecteert, klikt **u Upload voorbeeldbestand** om het CSV-bestand te uploaden dat u hebt voorbereid in stap 1. Met deze optie kunt u snel kolomnamen in uw CSV-bestand selecteren in een vervolgkeuzelijst om deze toe te wijden aan de gegevenstypen voor de HR-scenario's die u eerder hebt geselecteerd.

   OF

   - **Geef de toewijzingsgegevens handmatig op.** Als u deze optie selecteert, moet u de naam van de kolommen in het CSV-bestand typen om deze toe te wijden aan de gegevenstypen voor de HR-scenario's die u eerder hebt geselecteerd.

7. Ga op de pagina Bestandstoewijzingsgegevens op een van de volgende manieren te werk, afhankelijk van of u een voorbeeld-CSV-bestand hebt geüpload en of u de connector configureert voor één HR-scenario of voor meerdere scenario's. Als u een voorbeeldbestand hebt geüpload, hoeft u de kolomnamen niet te typen. U kiest ze in een vervolgkeuzelijst.

    - Als u in de vorige stap één HR-scenario hebt geselecteerd, typt u de kolomkopnamen (ook *wel parameters* genoemd) uit het CSV-bestand dat u in stap 1 in elk van de juiste vakken hebt gemaakt. De kolomnamen die u typt, zijn niet hoofdbestandsgevoelig, maar zorg ervoor dat u spaties op neemt als de kolomnamen in het CSV-bestand spaties bevatten. Zoals eerder is uitgelegd, moeten de namen die u in deze vakken typt, overeenkomen met de parameternamen in het CSV-bestand. In de volgende schermafbeelding ziet u bijvoorbeeld de parameternamen uit het voorbeeld-CSV-bestand voor het HR-scenario voor personeelsaftreding dat wordt weergegeven in stap 1.

    - Als u in stap hierboven meerdere gegevenstypen hebt geselecteerd, moet u de naam van de id-kolom invoeren om het gegevenstype HR in uw CSV-bestand te identificeren. Typ na het invoeren van de naam van de id-kolom de waarde die dit HR-gegevenstype identificeert en typ de kolomkopnamen voor geselecteerde gegevenstypen uit het CSV-bestand(en) dat u in stap 1 hebt gemaakt in elk van de juiste vakken voor elk geselecteerd gegevenstype. Zoals eerder is uitgelegd, moeten de namen die u in deze vakken typt, overeenkomen met de kolomnamen in het CSV-bestand.

8. Controleer op **de pagina** Controleren uw instellingen en klik vervolgens **op Voltooien** om de verbindingslijn te maken.

   Er wordt een statuspagina weergegeven die bevestigt dat de verbindingslijn is gemaakt. Deze pagina bevat twee belangrijke dingen die u nodig hebt om de volgende stap uit te voeren om het voorbeeldscript uit te voeren om uw HR-gegevens te uploaden.

   ![Pagina controleren met taak-id en koppeling naar github voor voorbeeldscript](../media/HRConnector_Confirmation.png)

   1. **Taak-id.** U hebt deze taak-id nodig om het script in de volgende stap uit te voeren. U kunt deze kopiëren vanaf deze pagina of vanaf de flyoutpagina van de verbindingslijn.

   1. **Koppeling maken naar voorbeeldscript.** Klik op **de koppeling** hier om naar de GitHub site te gaan om het voorbeeldscript te openen (met de koppeling wordt een nieuw venster geopend). Houd dit venster open, zodat u het script kunt kopiëren in stap 4. U kunt ook een bladwijzer toevoegen aan de bestemming of de URL kopiëren, zodat u deze opnieuw kunt openen wanneer u het script uit te voeren. Deze koppeling is ook beschikbaar op de flyoutpagina van de verbindingslijn.

9. Klik op **Gereed**.

   De nieuwe verbindingslijn wordt weergegeven in de lijst op het **tabblad Connectors.**

10. Klik op de HR-connector die u zojuist hebt gemaakt om de flyoutpagina weer te geven, die eigenschappen en andere informatie over de verbindingslijn bevat.

   ![Flyout-pagina voor nieuwe HR-connector](../media/HRConnectorWizard7.png)

Als u dit nog niet hebt gedaan, kunt u de waarden voor de **azure-app-id** en **connector-taak-id kopiëren.** U hebt deze nodig om het script in de volgende stap uit te voeren. U kunt het script ook downloaden vanaf de flyoutpagina (of het downloaden via de koppeling in de volgende stap.)

U kunt ook op **Bewerken klikken om** de Azure App-id of de kolomkopnamen te wijzigen die u hebt gedefinieerd op de pagina **Bestandstoewijzing.**

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Stap 4: Het voorbeeldscript uitvoeren om uw HR-gegevens te uploaden

De laatste stap bij het instellen van een HR-connector is het uitvoeren van een voorbeeldscript dat de HR-gegevens in het CSV-bestand (dat u in stap 1 hebt gemaakt) uploadt naar de Microsoft-cloud. Met het script worden de gegevens geüpload naar de HR-connector. Nadat u het script hebt uitgevoerd, importeert de HR-connector die u hebt gemaakt in stap 3 de HR-gegevens naar uw Microsoft 365-organisatie waar deze toegankelijk zijn via andere compliancehulpmiddelen, zoals de Insider-oplossing voor risicobeheer. Nadat u het script hebt uitgevoerd, kunt u overwegen om een taak te plannen om deze automatisch dagelijks uit te voeren, zodat de meest recente werknemersbeëindigingsgegevens worden geüpload naar de Microsoft-cloud. Zie [Het script automatisch uitvoeren plannen.](#optional-step-6-schedule-the-script-to-run-automatically)

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
   |`tenantId`|Dit is de id voor uw Microsoft 365 organisatie die u hebt verkregen in stap 2. U kunt ook de tenant-id voor uw organisatie verkrijgen op het **overzichtsblad** in het Azure AD-beheercentrum. Dit wordt gebruikt om uw organisatie te identificeren.|
   |`appId` |Dit is de Azure AD-toepassing-id voor de app die u hebt gemaakt in Azure AD in stap 2. Dit wordt door Azure AD gebruikt voor verificatie wanneer het script toegang probeert te krijgen tot uw Microsoft 365 organisatie. | 
   |`appSecret`|Dit is het Azure AD-toepassingsgeheim voor de app die u hebt gemaakt in Azure AD in stap 2. Dit wordt ook gebruikt voor verificatie.|
   |`jobId`|Dit is de taak-id voor de HR-connector die u hebt gemaakt in stap 3. Dit wordt gebruikt om de HR-gegevens die naar de Microsoft-cloud worden geüpload, te koppelen aan de HR-connector.|
   |`csvFilePath`|Dit is het bestandspad voor het CSV-bestand (opgeslagen op hetzelfde systeem als het script) dat u hebt gemaakt in stap 1. Probeer spaties in het bestandspad te vermijden. gebruik anders enkele aanhalingstekens.|
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

Als u het script niet hebt uitgevoerd in stap 4, wordt een koppeling voor het downloaden van het script weergegeven onder **Laatst importeren.** U kunt het script downloaden en vervolgens de stappen volgen om het script uit te voeren.

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

## <a name="existing-hr-connectors"></a>Bestaande HR-connectors

Op 20 juli 2020 hebben we extra scenario's uitgebracht die worden ondersteund door HR-connectors. Dit zijn de HR-scenario's die eerder in dit artikel zijn beschreven. Een HR-connector die vóór deze datum is gemaakt, biedt alleen ondersteuning voor het scenario Werknemer aftreding. Als u vóór 20 juli 2020 een HR-connector hebt gemaakt, hebben we deze gemigreerd, zodat deze uw HR-gegevens blijft migreren naar de Microsoft-cloud. U hoeft niets te doen om deze functionaliteit te behouden. U kunt de verbindingslijn zonder onderbrekingen blijven gebruiken.

Als u extra HR-scenario's wilt implementeren, maakt u een nieuwe HR-connector en configureert u deze voor de extra HR-scenario's die zijn uitgebracht. U moet ook een of meer nieuwe CSV-bestanden maken die de gegevens bevatten ter ondersteuning van de extra HR-scenario's. Nadat u een nieuwe HR-connector hebt gemaakt, kunt u het script uitvoeren met de taak-id van de nieuwe verbindingslijn en CSV-bestand(s) met de gegevens voor uw extra HR-scenario's.