---
title: Aanvals Simulator in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met behulp van Hack Simulator een aanval uitvoert met phishing en wachtwoorden in hun Microsoft 365 E5-of ATP-abonnement 2-organisaties.
ms.openlocfilehash: 76ba6fb68bbf8dd22f96d2be56136e74b0057619
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414008"
---
# <a name="attack-simulator-in-atp"></a>Aanvals Simulator in ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als uw organisatie Office 365 Advanced Threat Protection (ATP) heeft, waaronder het [onderzoek en de antwoord mogelijkheden](office-365-ti.md)van Office, kunt u met behulp van aanvals functie in het beveiligings & nalevings centrum realistische aanvalsscenario's in uw organisatie uitvoeren. Met de gesimuleerde aanvallen kunt u gebruikers kwetsbaar maken en kwetsbaar maken voor een echte aanval met uw onderste regel. Lees dit artikel voor meer informatie.

> [!NOTE]
> Simulatie van aanval en opleidingen met betrekking tot de training voor Microsoft 365-Services met andere klantgegevens. Zie [Microsoft 365-gegevenslocaties](/microsoft-365/enterprise/o365-data-locations)voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen. Er is een aanvals Simulator beschikbaar op de **bedreigings beheer** \> **aanval Simulator**. Ga rechtstreeks naar aanval Simulator, open <https://protection.office.com/attacksimulator> .

- Zie voor meer informatie over de beschikbaarheid van een aanvals functie in diverse Microsoft 365-abonnementen de [Beschrijving van Office 365 Advanced Threat Protection Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- U moet lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** . Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Uw account moet worden geconfigureerd voor multi-factor Authentication (MFA) voor het maken en beheren van campagnes in aanvals Simulator. Zie [multi-factor Authentication instellen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)voor instructies.

- Phishingberichten verzamelen en verwerken activiteiten gedurende 30 dagen. Actuele campagnegegevens zijn beschikbaar voor 90 dagen nadat u de campagne hebt gestart.

- Er zijn geen bijbehorende PowerShell-cmdlets voor Attack Simulator.

## <a name="spear-phishing-campaigns"></a>Met Spear verphishings campagnes

*Phishing* is een algemene term voor e-mail aanvallen waarbij gevoelige informatie wordt gestolen voor berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. *Spear phishing* is een gerichte malafide aanval waarbij gerichte en aangepaste inhoud worden gebruikt die specifiek is afgestemd op de gerichte geadresseerden (meestal na Reconnaissance op de geadresseerden van de aanvaller).

In het geval van een aanvals Simulator zijn er twee verschillende typen vergelijkende phishingberichten beschikbaar:

- **Spear phishing (credentials oogst)**: de aanval probeert de geadresseerden te overtuigen om op een URL in het bericht te klikken. Als u op de koppeling klikt, wordt u gevraagd hun referenties in te voeren. Als dat het geval is, worden deze in een van de volgende locaties gezet:

  - Een standaardpagina waarmee wordt uitgelegd dat dit een enkele test is en geeft tips voor het herkennen van phishingberichten.

    ![Welke gebruikers zien of ze op de phishing-koppeling klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - Een aangepaste pagina (URL) die u opgeeft.

- **Spear phishing (bijlage)**: de aanval probeert de geadresseerden te overtuigen een. DOCX-of. PDF-bijlage te openen in het bericht. De bijlage bevat dezelfde inhoud van de standaard malafide hyperlink, maar de eerste zin begint met ' \<Display Name\> , dit bericht wordt weergegeven als een onlangs verzonden e-mailbericht dat u hebt geopend... '.

> [!NOTE]
> Op dit moment verloopt het met Spear vermoeden van een aanvals Simulator niet.

### <a name="create-a-spear-phishing-campaign"></a>Een Spear malafide campagne maken

Een belangrijk onderdeel van een spear phishing is het uiterlijk van het e-mailbericht dat naar de specifieke geadresseerden is verzonden. Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:

- **Een ingebouwde e-mail sjabloon gebruiken**: er zijn twee ingebouwde sjablonen beschikbaar: **prijs Giveaway** en **salaris update**. U kunt enkele, alle of geen van de e-mail eigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.

- **Een herbruikbare e-mail sjabloon maken**: nadat u de e-mail sjabloon hebt gemaakt en opgeslagen, kunt u deze opnieuw gebruiken in toekomstige phishingberichten van een malafide programma. U kunt enkele, alle of geen van de e-mail eigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.

- **Het e-mailbericht maken in de wizard**: u kunt het e-mailbericht rechtstreeks in de wizard maken wanneer u de Spear malafide-campagne maakt en start.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Stap 1 (optioneel): een aangepaste e-mail sjabloon maken

Als u een van de ingebouwde sjablonen gaat gebruiken of het e-mailbericht rechtstreeks in de wizard wilt maken, kunt u deze stap overslaan.

1. Ga in het beveiligings & compliance naar aanvals centrum voor **Threat Management** \> **Attack simulator**.

2. Op de pagina **aanvallen simuleren** , in de secties **spear phishing (credentials oogst)** of **spear phishing (bijlage)** , klikt u op **Details van aanval**.

   Het maakt niet uit waar u de sjabloon maakt. De beschikbare opties in de sjabloon zijn hetzelfde voor beide typen phishing-aanvallen.

3. Klik op de pagina met **aanvals gegevens** die wordt geopend, in de sectie **phishingberichten** , in het gebied **sjablonen maken** op **nieuwe sjabloon**.

4. De wizard **phishing configureren** start in een nieuwe flyout. Voer in de stap **begin** een unieke weergavenaam voor de sjabloon in en klik op **volgende**.

5. Configureer de volgende instellingen in de stap **e-mail gegevens configureren** :

   - **From (naam)**: de weergavenaam die wordt gebruikt voor de afzender van het bericht.

   - **From (e-mail)**: het e-mailadres van de afzender.

   - **URL voor phishing-login server**: Klik op de vervolgkeuzelijst en selecteer een van de beschikbare url's in de lijst. Dit is de URL die gebruikers in de neiging krijgen om te klikken. U kunt kiezen uit de volgende opties:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Alle Url's zijn per ongeluk http, niet HTTPS.
     >
     > - Een URL-reputatie service kan een of meer van deze Url's als onveilig identificeren. Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL in een malafide campagne gebruikt.

   - **URL voor aangepaste landingspagina**: Voer een optionele openingspagina in, waar gebruikers worden gehouden als ze op de phishing-koppeling klikken en hun referenties invoeren. Met deze koppeling vervangt u de standaard landingspagina. Als u bijvoorbeeld een interne bewustmakings training hebt, kunt u die URL hier opgeven.

   - **Categorie**: deze instelling wordt op dit moment niet gebruikt (alle ingevoerde tekst wordt genegeerd).

   - **Onderwerp**: het veld **onderwerp** van het e-mailbericht.

   Wanneer u klaar bent, klikt u op **volgende**.

6. Maak in de stap **e-mailbericht opstellen** de berichttekst van het e-mailbericht. U kunt het tabblad **e-mail** (een rijke HTML-editor) of het tabblad **bron** (onbewerkte HTML-code) gebruiken.

   De HTML-opmaak kan zo eenvoudig of ingewikkeld zijn als u deze nodig hebt. U kunt afbeeldingen en tekst invoegen om de beknopte van het bericht in de e-mailclient van de ontvanger te bevorderen.

   - `${username}` voegt de naam van de geadresseerde in.

   - `${loginserverurl}` Hiermee voegt u de URL-naam van de phishingwebsite voor de **phishingwebsite** in met de vorige stap.

   Wanneer u klaar bent, klikt u op **volgende**.

7. Klik in de stap **bevestigen** op **Voltooien**.

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Stap 2: de spear phishing-campagne maken en starten

1. Ga in het beveiligings & compliance naar aanvals centrum voor **Threat Management** \> **Attack simulator**.

2. Maak op de pagina **aanvallen simuleren** een van de volgende opties op basis van het type campagne dat u wilt maken:

   - Klik in de sectie **spear phishing (credentials oogst)** op **Attack activeren** of klik op aanvals **Details** \> **starten**.

   - Klik in de sectie **spear phishing (bijlage)** op **aanval starten** of klik op aanvals **informatie** \> **starten**.

3. De wizard **phishing configureren** begint in een nieuwe flyout. Voer in de stap **begin** een van de volgende stappen uit:

   - Voer in het vak **naam** een unieke weergavenaam voor de campagne in. Klik niet op **sjabloon gebruiken**omdat u het e-mailbericht later in de wizard gaat maken.

   - Klik op **sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mail sjabloon. Wanneer u de sjabloon hebt geselecteerd, wordt het vak **naam** automatisch ingevuld op basis van de sjabloon, maar u kunt de naam wijzigen.

   ![De start pagina van phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Wanneer u klaar bent, klikt u op **volgende**.

4. Voer een van de volgende stappen uit in de stap **doel geadresseerden** :

   - Klik op **Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren. Elke gerichte ontvanger moet een postvak van Exchange Online hebben. Als u op **filter** en **toepassen** klikt zonder de zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en aan de campagne toegevoegd.

   - Klik op **importeren** en vervolgens op **bestand importeren** om een CSV-bestand (door komma's gescheiden waarden) of een bestand met door komma's gescheiden waarden van e-mailadressen te importeren. Elke regel moet het e-mailadres van de geadresseerde bevatten.

   Wanneer u klaar bent, klikt u op **volgende**.

5. Configureer de volgende instellingen in de stap **e-mail gegevens configureren** :

   Als u een sjabloon hebt geselecteerd in de **begin** stap, zijn de meeste van deze waarden al geconfigureerd, maar u kunt ze wijzigen.

   - **From (naam)**: de weergavenaam die wordt gebruikt voor de afzender van het bericht.

   - **From (e-mail)**: het e-mailadres van de afzender. U kunt een echt e-mailadres of e-mailadres invoeren in het e-mail domein van uw organisatie, of u kunt een echt of vervalst extern e-mailadres invoeren. Een geldig e-mailadres van de afzender van uw organisatie wordt daadwerkelijk omgezet in de e-mailclient van de ontvanger.

   - **URL voor phishing-login server**: Klik op de vervolgkeuzelijst en selecteer een van de beschikbare url's in de lijst. Dit is de URL die gebruikers in de neiging krijgen om te klikken. U kunt kiezen uit de volgende opties:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Alle Url's zijn per ongeluk http, niet HTTPS.
     >
     > - Een URL-reputatie service kan een of meer van deze Url's als onveilig identificeren. Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL in een malafide campagne gebruikt.
     >
     > - U moet een URL selecteren. U kunt de koppeling in de hoofdtekst van het bericht in de volgende stap verwijderen (in de volgende stap, anders is het bericht een koppeling **en** een **bijlage).**

   - **Bijlage type**: deze instelling is alleen beschikbaar in een **Spear malafide-campagne (bijlage)** . Klik op de vervolgkeuzelijst en selecteer **. DOCX** of **. PDF** uit de lijst.

   - **Bijlagenaam**: deze instelling is alleen beschikbaar in een **Spear malafide-campagne (bijlage)** . Voer een bestandsnaam in voor de. DOCX-of. PDF-bijlage.

   - **URL voor aangepaste landingspagina**: Voer een optionele openingspagina in, waar gebruikers worden gehouden als ze op de phishing-koppeling klikken en hun referenties invoeren. Met deze koppeling vervangt u de standaard landingspagina. Als u bijvoorbeeld een interne bewustmakings training hebt, kunt u die URL hier opgeven.

   - **Onderwerp**: het veld **onderwerp** van het e-mailbericht.

   Wanneer u klaar bent, klikt u op **volgende**.

6. Maak in de stap **e-mailbericht opstellen** de berichttekst van het e-mailbericht. Als u in de stap **begin** een sjabloon hebt geselecteerd, is de berichttekst al geconfigureerd, maar u kunt deze aanpassen. U kunt het tabblad **e-mail** (een rijke HTML-editor) of het tabblad **bron** (onbewerkte HTML-code) gebruiken.

   De HTML-opmaak kan zo eenvoudig of ingewikkeld zijn als u deze nodig hebt. U kunt afbeeldingen en tekst invoegen om de beknopte van het bericht in de e-mailclient van de ontvanger te bevorderen.

   - `${username}` voegt de naam van de geadresseerde in.

   - `${loginserverurl}` Hiermee voegt u de URL-naam van de phishingwebsite van de **phishingwebsite** in.

   U moet de koppeling in de hoofdtekst van het bericht verwijderen (in de **meeste** gevallen moet het bericht zowel een koppeling **als** een bijlage bevatten, en koppelings klikken worden niet bijgehouden in een bijlage campagne).

   ![Berichttekst opstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Wanneer u klaar bent, klikt u op **volgende**.

7. Klik in de stap **bevestigen** op **Voltooien** om de campagne te starten. Het malafide bericht wordt bezorgd bij de specifieke geadresseerden.

## <a name="password-attack-campaigns"></a>Wachtwoord aanvals campagnes

Een *wachtwoord aanval* probeert wachtwoorden te raden voor gebruikersaccounts in een organisatie, meestal nadat de hacker een of meer geldige gebruikersaccounts heeft vastgesteld.

In het geval van een aanvals Simulator zijn voor u de complexiteit van de wachtwoorden van de gebruikers mogelijk.

- **Wachtwoord voor brute kracht (woordenboekaanval)**: een *Grove* woord of *woordenboek* aanval gebruikt een groot woordenboek met wachtwoorden voor een gebruikersaccount, zodat een van deze wachtwoorden (veel wachtwoorden voor één account) werkt. Onjuiste wachtwoord vergrendelings helpt bij het beschermen van grove aanvals wachtwoorden.

  Voor de woordenboekaanval kunt u een of meer wachtwoorden opgeven voor de invoer (handmatig of in een geüpload bestand) en kunt u een of meer gebruikers opgeven.

- **Aanval**met een wachtwoord: een aanval met een *wachtwoord* gebruikt hetzelfde zorgvuldig als het wachtwoord voor een lijst met gebruikersaccounts (één wachtwoord voor een groot aantal accounts). Aanval met een wachtwoord is moeilijker te detecteren dan aanvallen met een grove kracht (de kans op succes vergroot wanneer een aanvaller één wachtwoord probeert uit te proberen of honderden accounts zonder dat het risico loopt dat de gebruikers onjuiste wachtwoorden voor de gebruiker uitchecken).

  Voor de wachtwoord spray mag u slechts één wachtwoord opgeven om te proberen, en kunt u een of meer gebruikers opgeven.

> [!NOTE]
> Met de wachtwoord aanvallen in aanval Simulator worden gebruikersnamen en basisverificatie aanvragen doorgegeven aan een eindpunt, zodat ze ook met andere verificatiemethoden werken (AD FS, hash-synchronisatie, Pass-Through, PingFederate, enzovoort). Voor gebruikers waarbij MFA is ingeschakeld, wordt het wachtwoord van de aanvaller automatisch geregistreerd als gevolg van een aanval (met andere woorden, MFA-gebruikers worden nooit weergegeven in het aantal **geslaagde pogingen** van de campagne). Dit is het verwachte resultaat. MFA is een primaire methode voor een betere bescherming tegen wachtwoord aanvallen.

### <a name="create-and-launch-a-password-attack-campaign"></a>Een wachtwoord aanvals campagne maken en starten

1. Ga in het beveiligings & compliance naar aanvals centrum voor **Threat Management** \> **Attack simulator**.

2. Maak op de pagina **aanvallen simuleren** een van de volgende opties op basis van het type campagne dat u wilt maken:

   - Klik in de sectie **Grove wachtwoord afdwingen (woordenboekaanval)** op **aanval starten** of klik op aanvals **Details** \> **starten**.

   - Klik in de sectie **wachtwoord spuit aanval** op **aanval starten** of klik op aanvals **Details** \> **starten**.

3. De wizard **wachtwoord configureren** wordt gestart in een nieuwe flyout. Voer in de stap **begin** een unieke weergavenaam voor de campagne in en klik op **volgende**.

4. Voer een van de volgende stappen uit in de stap **doelgebruikers** :

   - Klik op **Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren. Elke gerichte ontvanger moet een postvak van Exchange Online hebben. Als u op **filter** en **toepassen** klikt zonder de zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en aan de campagne toegevoegd.

   - Klik op **importeren** en vervolgens op **bestand importeren** om een CSV-bestand (door komma's gescheiden waarden) of een bestand met door komma's gescheiden waarden van e-mailadressen te importeren. Elke regel moet het e-mailadres van de geadresseerde bevatten.

   Wanneer u klaar bent, klikt u op **volgende**.

5. Kies in de stap **Choose Attack Settings** wat u wilt doen op basis van het type campagne:

   - **Wachtwoord voor brute kracht (woordenboekaanval)**: Voer een van de volgende stappen uit:

     - **Voer uw wachtwoorden handmatig**in: Typ een wachtwoord in het vak **Druk op ENTER om een wachtwoord toe te voegen** en druk op ENTER. Herhaal deze stap zo vaak als nodig is.

     - **Wachtwoorden van een woordenlijstbestand uploaden**: Klik op **uploaden** om een bestaand tekstbestand te importeren dat één wachtwoord bevat op een regel en een lege laatste regel. Het tekstbestand mag niet groter zijn dan 10 MB, en mag niet meer dan 30000 wachtwoorden bevatten.

   - **Aanval**met een wachtwoord: Typ in **het vak voor de aanval** één wachtwoord.

   Wanneer u klaar bent, klikt u op **volgende**.

6. Klik in de stap **bevestigen** op **Voltooien** om de campagne te starten. De wachtwoorden die u hebt opgegeven, worden geprobeerd op door u opgegeven gebruikers.

## <a name="view-campaign-results"></a>Campagne resultaten weergeven

Wanneer u een campagne hebt gestart, kunt u de voortgang en de resultaten controleren op de pagina met **aanvals simulatie** .

Actieve campagnes tonen een statusbalk, een voltooide percentagewaarde en ' (voltooide gebruikers) van (totaal aantal gebruikers) '. Als u op de knop **vernieuwen** klikt, wordt de voortgang van actieve campagnes bijgewerkt. U kunt ook op **beëindigen** klikken om een actieve campagne te beëindigen.

Wanneer de campagne is voltooid, wordt de status gewijzigd in **aanval voltooid**. U kunt de resultaten van de campagne weergeven door een van de volgende handelingen uit te voeren:

- Klik op de pagina Hoofdpagina met **simulaties** op **rapport weergeven** onder de naam van de campagne.

- Op de pagina Main Attack- **aanvallen** klikt u op **Details van aanval** in de sectie voor het type aanval. Selecteer op de pagina **Details van aanval** de optie campagne in de sectie **aanvals geschiedenis** .

Met een van de vorige acties gaat u naar een pagina met de naam **aanvals gegevens**. In de volgende secties wordt beschreven welke informatie op deze pagina beschikbaar is voor elk type campagne.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Resultaten van een spear phishing-campagne (referenties oogst)

U vindt de volgende informatie op de pagina met details van een **aanval** voor elke campagne:

- De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.

- **Totaal aantal gebruikers dat is gericht**

- **Geslaagde pogingen**: het aantal gebruikers dat op de koppeling heeft geklikt **en** hun referenties heeft ingevoerd (*elke* gebruikersnaam en wachtwoord).

- **Algemeen succes tarief**: een percentage dat wordt berekend door de **succesvolle pogingen**voor een  /  **Totaal aantal gebruikers**die zijn gericht.

- **Snelste Klik**: hoe lang het duurt voordat de eerste gebruiker op de koppeling klikt, nadat u de campagne hebt gestart.

- **Gemiddelde Klik**: de som van hoe lang het duurt voordat iedereen op de koppeling klikt, gedeeld door het aantal gebruikers dat op de koppeling heeft geklikt.

- **Klik op succes tarief**: een percentage dat wordt berekend door (aantal gebruikers dat op de koppeling hebt geklikt)/ **totale aantal gebruikers**dat is gericht.

- **Snelste referenties**: hoe lang het duurt voordat de eerste gebruiker de referenties heeft ingevoerd nadat u de campagne hebt gestart.

- **Gemiddelde referenties**: de som van hoe lang het duurt voordat iedereen de referenties heeft ingevoerd, gedeeld door het aantal gebruikers dat hun referenties heeft ingevoerd.

- **Geslaagde referenties**: een percentage dat wordt berekend door (aantal gebruikers dat zijn of haar referenties heeft ingevoerd)/ **totale aantal gebruikers met een targeted**.

- Een staafdiagram met een koppeling waarmee de **koppeling wordt geklikt** en de **ingevoerde** nummers per dag.

- Een cirkeldiagram waarin de koppeling wordt weergegeven waarop de **koppeling**is **gebaseerd**, en **geen** percentages van de campagne.

- De sectie verdeelde **gebruikers** bevat de details van de gebruikers die op de koppeling hebben geklikt:

  - Het e-mailadres van de gebruiker

  - De datum/tijd waarop ze op de koppeling hebben geklikt.

  - Het IP-adres van de client.

  - Details van de versie van Windows en de webbrowser van de gebruiker.

  U kunt op **exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.

### <a name="spear-phishing-attachment-campaign-results"></a>Campagne resultaten van Spear malafide (bijlage)

U vindt de volgende informatie op de pagina met details van een **aanval** voor elke campagne:

- De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.

- **Totaal aantal gebruikers dat is gericht**

- **Geslaagde pogingen**: het aantal gebruikers dat de bijlage heeft geopend of gedownload en geopend (geen aantal).

- **Algemeen succes tarief**: een percentage dat wordt berekend door de **succesvolle pogingen**voor een  /  **Totaal aantal gebruikers**die zijn gericht.

- **Snelste tijd voor bijlage open**: hoelang de eerste gebruiker de bijlage heeft gemaakt om de bijlage te openen na het starten van de campagne.

- **Gemiddelde openingstijd bijlage**: de som van hoe lang het duurt voordat iedereen de bijlage opent, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.

- **Bijlage openen geslaagd**: een percentage dat wordt berekend door (aantal gebruikers dat de bijlage heeft geopend)/ **totale aantal gebruikers**dat is gericht.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>De campagne resultaten van brute kracht (woordenboekaanval)

U vindt de volgende informatie op de pagina met details van een **aanval** voor elke campagne:

- De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.

- **Totaal aantal gebruikers dat is gericht**

- **Geslaagde pogingen**: het aantal gebruikers dat is gevonden met een van de opgegeven wachtwoorden.

- **Algemeen succes tarief**: een percentage dat wordt berekend door de **succesvolle pogingen**voor een  /  **Totaal aantal gebruikers**die zijn gericht.

- In de sectie met verdeelde **gebruikers** worden de e-mailadressen van de betrokken gebruikers weergegeven. U kunt op **exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.

### <a name="password-spray-attack-campaign-results"></a>Resultaten van een aanval via een wachtwoord

U vindt de volgende informatie op de pagina met details van een **aanval** voor elke campagne:

- De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.

- **Totaal aantal gebruikers dat is gericht**

- **Geslaagde pogingen**: het aantal gebruikers dat het opgegeven wachtwoord heeft gevonden.

- **Algemeen succes tarief**: een percentage dat wordt berekend door de **succesvolle pogingen**voor een  /  **Totaal aantal gebruikers**die zijn gericht.
