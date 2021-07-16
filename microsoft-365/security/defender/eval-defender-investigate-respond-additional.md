---
title: Probeer Microsoft 365 Defender mogelijkheden voor incidentrespons in een testomgeving te gebruiken, om prioriteit te geven aan incidenten en om incidenten te beheren, geautomatiseerde onderzoeken en antwoorden te configureren en geavanceerd zoeken te gebruiken
description: Probeer mogelijkheden voor incidentrespons in Microsoft 365 Defender om prioriteit te geven aan incidenten en om incidenten te beheren, onderzoeken te automatiseren en geavanceerde zoekactie te gebruiken bij het opsporen van bedreigingen.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457809"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>Probeer Microsoft 365 Defender mogelijkheden voor incidentrespons in een testomgeving

**Van toepassing op:**
- Microsoft 365 Defender

Dit artikel is [stap 2 van 2](eval-defender-investigate-respond.md) in het proces van het uitvoeren van een onderzoek en de reactie van een incident in Microsoft 365 Defender met behulp van een testomgeving. Zie het [overzichtsartikel](eval-defender-investigate-respond.md) voor meer informatie over dit proces.

Nadat u een [incidentreactie voor](eval-defender-investigate-respond-simulate-attack.md)een gesimuleerde aanval hebt uitgevoerd, zijn hier enkele Microsoft 365 Defender mogelijkheden om te verkennen:

|Mogelijkheid |Beschrijving |
|:-------|:-----|
| [Prioriteit geven aan incidenten](#prioritize-incidents) | Gebruik het filteren en sorteren van de incidentenwachtrij om te bepalen welke incidenten u vervolgens moet adresseren. |
| [Incidenten beheren](#manage-incidents) | Wijzig incidenteigenschappen om ervoor te zorgen dat de toewijzing correct is, voeg tags en opmerkingen toe en om een incident op te lossen. |
| [Geautomatiseerd onderzoek en reactie](#examine-automated-investigation-and-response-with-the-action-center) | Geautomatiseerde onderzoeks- en antwoordmogelijkheden (AIR) die uw beveiligingsteam kunnen helpen om bedreigingen efficiënter en effectiever aan te pakken. Het actiecentrum is een 'enkel deelvenster met glas' voor incident- en waarschuwingstaken, zoals het goedkeuren van in behandeling zijnde herstelacties. |
| [Geavanceerd opsporen](#advanced-hunting) | Een op query's gebaseerd hulpprogramma voor het zoeken naar bedreigingen waarmee u gebeurtenissen in uw netwerk proactief kunt controleren en bedreigingsindicatoren en entiteiten kunt vinden. U gebruikt ook geavanceerde jacht tijdens het onderzoeken en herstellen van een incident. |
||||

## <a name="prioritize-incidents"></a>Prioriteit geven aan incidenten

U komt bij de incidentwachtrij van **Incidenten & waarschuwingen > Incidenten** op de snelle start van de Microsoft 365 Defender portal [(security.microsoft.com).](https://security.microsoft.com) Hier is een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Voorbeeld van de incidentwachtrij":::

In **de sectie Meest recente incidenten en waarschuwingen** ziet u een grafiek van het aantal ontvangen waarschuwingen en incidenten die in de afgelopen 24 uur zijn gemaakt.

Als u de lijst met incidenten wilt bekijken en prioriteit wilt geven aan het belang ervan voor toewijzing en onderzoek, kunt u het volgende doen: 

- Configureer aanpasbare kolommen (selecteer **Kolommen kiezen)** om u inzicht te geven in de verschillende kenmerken van het incident of de beïnvloede entiteiten. Op deze manier kunt u een weloverwogen beslissing nemen over de prioriteit van incidenten voor analyse.

- Gebruik filtering om de focus te richten op een specifiek scenario of een bepaalde bedreiging. Door filters toe te passen op de incidentenwachtrij, kunt u bepalen welke incidenten direct aandacht vereisen. 

Selecteer filters in de standaardwachtrij voor incidenten **om** een deelvenster **Filters** te zien, waaruit u een specifieke set incidenten kunt opgeven. Hier volgt een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Voorbeeld van het filtervenster voor de incidentwachtrij":::

Zie Prioriteit geven aan incidenten voor meer [informatie.](incident-queue.md)

## <a name="manage-incidents"></a>Incidenten beheren

U kunt incidenten beheren vanuit het deelvenster **Incident beheren** voor een incident. Hier is een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Voorbeeld van het deelvenster Incident beheren van een incident":::

U kunt dit deelvenster weergeven via de koppeling **Incident beheren** op het volgende:

- Deelvenster Eigenschappen van een incident in de incidentwachtrij.
- **Overzichtspagina** van een incident.

Dit zijn de manieren waarop u uw incidenten kunt beheren:

- De naam van het incident bewerken

  Wijzig de niet-automatisch toegewezen naam op basis van de best practices van uw beveiligingsteam.
  
- Incidentlabels toevoegen

  Voeg tags toe die uw beveiligingsteam gebruikt om incidenten te classificeren, die later kunnen worden gefilterd.
  
- Het incident aan uzelf toewijzen

  Wijs deze toe aan de naam van uw gebruikersaccount, die later kan worden gefilterd.
  
- Een incident oplossen

  Sluit het incident nadat het is gesaneerd.
  
- De classificatie en bepaling ervan instellen

  Classificeer en selecteer het type bedreiging wanneer u een incident hebt opgelost.
  
- Opmerkingen toevoegen

  Gebruik opmerkingen voor voortgang, notities of andere informatie op basis van best practices van uw beveiligingsteam. De volledige opmerkingsgeschiedenis is beschikbaar via de **optie Opmerkingen en geschiedenis** op de detailspagina van een incident.

Zie Incidenten beheren voor meer [informatie.](manage-incidents.md)

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>Geautomatiseerde onderzoeken en antwoorden onderzoeken met het Actiecentrum

Afhankelijk van hoe geautomatiseerde onderzoeks- en antwoordmogelijkheden voor uw organisatie zijn geconfigureerd, worden herstelacties automatisch of alleen uitgevoerd na goedkeuring door uw beveiligingsteam. Alle acties, in behandeling of voltooid, [](m365d-action-center.md)worden weergegeven in het Actiecentrum, waarin in behandeling zijnde en voltooide herstelacties voor uw apparaten, e-mail & samenwerkingsinhoud en identiteiten op één locatie worden vermeld.

Hier is een voorbeeld.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Unified Action center in Microsoft 365 Defender":::

In het actiecentrum kunt u acties in behandeling selecteren en deze vervolgens goedkeuren of weigeren in het deelvenster Flyout. Hier is een voorbeeld.

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Een actie goedkeuren of weigeren":::

Hangende acties zo snel mogelijk goedkeuren (of weigeren), zodat uw geautomatiseerde onderzoeken tijdig kunnen worden uitgevoerd en voltooid.

Zie Geautomatiseerd onderzoek [](m365d-autoir.md) en antwoord en Actiecentrum voor [meer informatie.](m365d-action-center.md)

## <a name="advanced-hunting"></a>Geavanceerd opsporen

> [!NOTE]
> Voordat we u door de geavanceerde jachtsimulatie leiden, bekijkt u de volgende video om geavanceerde zoekconcepten te begrijpen, te zien waar u deze kunt vinden in de portal en hoe deze u kan helpen bij uw beveiligingsbewerkingen.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


Als [](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) de optionele powershell-aanvalssimulatie zonder bestand een echte aanval was die de toegangsfase voor referenties al had bereikt, kunt u op elk moment in het onderzoek geavanceerde zoekactie gebruiken om proactief door gebeurtenissen en records in het netwerk te zoeken met behulp van wat u al weet uit de gegenereerde waarschuwingen en betrokken entiteiten. U kunt bijvoorbeeld zoeken naar eventuele verbindingen met het externe IP-adres in de afgelopen 30 dagen.

### <a name="hunting-environment-requirements"></a>Vereisten voor de jachtomgeving

Er is één intern postvak en één apparaat vereist voor deze simulatie. U hebt ook een extern e-mailaccount nodig om het testbericht te verzenden.

1. Controleer of uw tenant [de](m365d-enable.md#confirm-that-the-service-is-on)Microsoft 365 Defender.
2. Identificeer een doelpostvak dat moet worden gebruikt voor het ontvangen van e-mail.

   - Dit postvak moet worden gecontroleerd door Microsoft Defender voor Office 365

   - Het apparaat van vereiste 3 moet toegang krijgen tot dit postvak

3. Een testapparaat configureren:

    a. Zorg ervoor dat u de Windows 10 versie 1903 of hoger gebruikt.

    b. Ga met het testapparaat naar het testdomein.

    c. [Schakel de Windows Defender Antivirus.](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) Als u problemen hebt met het inschakelen van Windows Defender Antivirus, [bekijkt u dit probleemoplossingsonderwerp.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)

    d. [Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>De simulatie uitvoeren

1. Verzend vanuit een extern e-mailaccount een e-mail naar het postvak dat is geïdentificeerd in stap 2 van de sectie vereisten voor de zoekomgeving. Voeg een bijlage toe die is toegestaan via een bestaand e-mailfilterbeleid. Dit bestand hoeft niet schadelijk of uitvoerbaar te zijn. Voorgestelde <i>bestandstypen.pdf</i>, <i>.exe</i> (indien toegestaan) of een Office zoals een Word-bestand.

2. Open de verzonden e-mail vanaf het apparaat dat is geconfigureerd zoals gedefinieerd in stap 3 van de sectie vereisten voor de zoekomgeving. Open de bijlage of sla het bestand op het apparaat op.

#### <a name="go-hunting"></a>Ga op zoek

1. Open de [Microsoft 365 Defender portal](https://security.microsoft.com/).

2. Selecteer in het navigatiedeelvenster **de optie > Advanced hunting.**

3. Maak een query die begint met het verzamelen van e-mailgebeurtenissen.

   1. Selecteer **Query > Nieuw**.

   1. Dubbelklik in **de e-mailgroepen** onder Geavanceerd **zoeken** op **E-mailEvents.** U ziet dit in het queryvenster.

      ```console
      EmailEvents
      ```

   1. Wijzig het tijdsbestek van de query in de laatste 24 uur. Ervan uitgaande dat de e-mail die u hebt verzonden toen u de bovenstaande simulatie hebt uitgevoerd, de afgelopen 24 uur was, wijzigt u anders de tijd zo nodig.

   1. Selecteer **Query uitvoeren.** U hebt mogelijk verschillende resultaten, afhankelijk van uw testomgeving.

      > [!NOTE]
      > Zie de volgende stap voor filteropties om het retourneren van gegevens te beperken.

      ![Voorbeeld van de resultaten van geavanceerde query's](../../media/mtp/fig19.png)

        > [!NOTE]
        > Geavanceerde selectie geeft queryresultaten weer als tabelgegevens. U kunt er ook voor kiezen om de gegevens weer te geven in andere notatietypen, zoals grafieken.

   1. Bekijk de resultaten en kijk of u de e-mail kunt identificeren die u hebt geopend. Het kan maximaal twee uur duren voordat het bericht wordt weergegeven in de geavanceerde jacht. Als u de resultaten wilt  beperken, kunt u de voorwaarde waar aan uw query toevoegen om alleen te zoeken naar e-mailberichten met 'yahoo.com' als afzenderMailFromDomain. Hier volgt een voorbeeld.

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Klik op de resulterende rijen uit de query, zodat u de record kunt controleren.

      ![Voorbeeld van het zijpaneel inspecteerrecord dat wordt geopend wanneer een geavanceerd selectieresultaat wordt geselecteerd](../../media/mtp/fig21.png)

4. Nu u hebt geverifieerd dat u het e-mailbericht kunt zien, voegt u een filter voor de bijlagen toe. Focus op alle e-mailberichten met bijlagen in de omgeving. Voor deze simulatie richt u zich op binnenkomende e-mailberichten, niet op de e-mailberichten die vanuit uw omgeving worden verzonden. Verwijder alle filters die u hebt toegevoegd om uw bericht te zoeken en voeg '| where **AttachmentCount > 0** and **EmailDirection**  ==  **"Inbound""**

   In de volgende query ziet u het resultaat met een kortere lijst dan de eerste query voor alle e-mailgebeurtenissen:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Voeg vervolgens de informatie over de bijlage (zoals: bestandsnaam, hashes) toe aan uw resultatenset. Neem deel aan de tabel **EmailAttachmentInfo** om dit te doen. De veelgebruikte velden voor deelname zijn in dit geval **NetworkMessageId** **en RecipientObjectId.**

   De volgende query bevat ook een extra regel '| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Gebruik vervolgens de **SHA256-waarde** uit de tabel **EmailAttachmentInfo** om **DeviceFileEvents (bestandsacties** die zijn gebeurd op het eindpunt) te zoeken voor die hash. Het algemene veld hier is de SHA256-hash voor de bijlage.

   De resulterende tabel bevat nu details van het eindpunt (Microsoft Defender voor eindpunt), zoals de naam van het apparaat, welke actie is uitgevoerd (in dit geval gefilterd om alleen Bestandscreated-gebeurtenissen op te nemen) en waar het bestand is opgeslagen. De accountnaam die aan het proces is gekoppeld, wordt ook opgenomen.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   U hebt nu een query gemaakt die alle binnenkomende e-mailberichten identificeert waarin de gebruiker de bijlage heeft geopend of opgeslagen. U kunt deze query ook verfijnen om te filteren op specifieke afzenderdomeinen, bestandsgrootten, bestandstypen, en ga zo maar door.

7. Functies zijn een speciaal type join, waarmee u meer TI-gegevens over een bestand kunt ophalen, zoals de aanwezigheidsgegevens, ondertekenaars en uitgevende e-mail. Gebruik de functie **FileProfile()** voor meer informatie over het bestand:

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>Een detectie maken

Nadat u een query hebt gemaakt die informatie  identificeert die u wilt laten weten als ze in de toekomst worden uitgevoerd, kunt u een aangepaste detectie maken op de query.

Met aangepaste detecties wordt de query uitgevoerd op basis van de frequentie die u hebt ingesteld. De resultaten van de query's maken beveiligingswaarschuwingen, op basis van de beïnvloede assets die u kiest. Deze waarschuwingen worden gecorreleerd aan incidenten en kunnen worden gekoppeld aan een andere beveiligingswaarschuwing die door een van de producten wordt gegenereerd.

1. Verwijder op de querypagina de regels 7 en 8 die zijn toegevoegd in stap 7 van de zoekinstructies gaan en klik op **Detectieregel maken.**

   ![Voorbeeld van waar u op detectieregel maken kunt klikken op de pagina geavanceerd zoeken](../../media/mtp/fig22.png)

   > [!NOTE]
   > Als u op **Detectieregel maken** klikt en u syntaxisfouten in de query hebt, wordt de detectieregel niet opgeslagen. Controleer de query om er zeker van te zijn dat er geen fouten zijn.

2. Vul de vereiste velden in met de gegevens waarmee het beveiligingsteam inzicht krijgt in de waarschuwing, waarom deze is gegenereerd en welke acties u verwacht dat ze uitvoeren.

   ![Voorbeeld van de pagina detectieregel maken waarin u de waarschuwingsdetails kunt definiëren](../../media/mtp/fig23.png)

   Zorg ervoor dat u de velden helder invult om de volgende gebruiker een weloverwogen beslissing te geven over deze detectieregelwaarschuwing

3. Selecteer in deze waarschuwing welke entiteiten van invloed zijn. Selecteer in dit geval **Apparaat** en **Postvak.**

   ![Voorbeeld van de pagina detectieregel maken waarin u de parameters van de beïnvloede entiteiten kunt kiezen](../../media/mtp/fig24.png)

4. Bepaal welke acties moeten plaatsvinden als de waarschuwing wordt geactiveerd. Voer in dit geval een antivirusscan uit, hoewel andere acties kunnen worden uitgevoerd.

   ![Voorbeeld van de pagina detectieregel maken waarin u een antivirusscan kunt uitvoeren wanneer een waarschuwing wordt geactiveerd om bedreigingen te helpen adresseren](../../media/mtp/fig25.png)

5. Selecteer het bereik voor de waarschuwingsregel. Aangezien deze query apparaten omvat, zijn de apparaatgroepen relevant in deze aangepaste detectie volgens microsoft Defender voor eindpuntcontext. Wanneer u een aangepaste detectie maakt die geen apparaten als beïnvloede entiteiten bevat, is het bereik niet van toepassing.

   ![Voorbeeld van de pagina detectieregel maken waarin u het bereik voor de waarschuwingsregel kunt instellen, beheert u uw verwachtingen voor de resultaten die u ziet](../../media/mtp/fig26.png)

   Voor deze pilot kunt u deze regel beperken tot een subset testapparaten in uw productieomgeving.

6. Selecteer **Maken**. Selecteer vervolgens **Aangepaste detectieregels** in het navigatiedeelvenster.

   ![Voorbeeld van de optie Aangepaste detectieregels in het menu](../../media/mtp/fig27a.png)

   ![Voorbeeld van de pagina detectieregels waarin de regel- en uitvoeringsgegevens worden weergegeven](../../media/mtp/fig27b.png)

   Op deze pagina kunt u de detectieregel selecteren, waarmee een detailpagina wordt geopend.

   ![Voorbeeld van de pagina e-mailbijlagen waarin u de status van de uitvoering van de regel, geactiveerde waarschuwingen en acties kunt zien, de detectie kunt bewerken, en ga zo maar door](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a>Deskundige training over geavanceerde jacht

**Het bijhouden van de strijder** is een webcastreeks voor nieuwe beveiligingsanalisten en doorgevinterde bedreigingsjagers. U wordt begeleid door de basisbeginselen van geavanceerd zoeken tot aan het maken van uw eigen geavanceerde query's. 

Zie [Training van experts krijgen over geavanceerde jacht om](advanced-hunting-expert-training.md) aan de slag te gaan.

### <a name="navigation-you-may-need"></a>Navigatie die u mogelijk nodig hebt

[De Microsoft 365 Defender evaluatieomgeving maken](eval-create-eval-environment.md)
