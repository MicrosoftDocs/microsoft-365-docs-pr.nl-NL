---
title: Attack Simulator in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het gebruik van Attack Simulator voor het uitvoeren van gesimuleerde phishing- en wachtwoordaanvallen in uw Microsoft 365 E5- of ATP Plan 2-organisatie.
ms.openlocfilehash: 166a8ab9f6ef08ca089bc8924b686e392e870526
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587566"
---
# <a name="attack-simulator-in-atp"></a>Attack Simulator in ATP

**Samenvatting** Als u een globale beheerder of een beveiligingsbeheerder bent en uw organisatie Office 365 Advanced Threat Protection Plan 2 heeft, dat mogelijkheden voor [bedreigingsonderzoek en -reactie](office-365-ti.md)omvat, u Attack Simulator gebruiken om realistische aanvalsscenario's in uw organisatie uit te voeren. Dit kan u helpen kwetsbare gebruikers te identificeren en te vinden voordat een echte aanval uw bedrijfsresultaat beïnvloedt. Lees dit artikel voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen. Attack simulator is beschikbaar bij **Threat management** \> **Attack simulator**.

  ![Dreigingsbeheer - Attack Simulator](../../media/ThreatMgmt-AttackSimulator.png)

- Zie de servicebeschrijving van [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie over de beschikbaarheid van Attack Simulator voor verschillende Microsoft 365-abonnementen.

- U moet lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Uw account moet zijn geconfigureerd voor multi-factor authenticatie (MFA) om campagnes te maken en te beheren in Attack Simulator. Zie [Meerstapverificatie instellen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)voor instructies.

Zorg ervoor dat het account dat u gebruikt om gesimuleerde aanvallen uit te voeren, gebruik maakt van multi-factor authenticatie om een aanval met succes te starten. Daarnaast moet u een globale beheerder of een beveiligingsbeheerder zijn. (Zie [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen .)

- Phishingcampagnes verzamelen en verwerken gebeurtenissen gedurende 30 dagen. Historische campagnegegevens zijn beschikbaar tot 90 dagen nadat u de campagne hebt gestart.

- Er zijn geen overeenkomstige PowerShell-cmdlets voor Attack Simulator.

## <a name="spear-phishing-campaigns"></a>Spear phishing campagnes

*Phishing* is een algemene term voor e-mailaanvallen die proberen om gevoelige informatie te stelen in berichten die lijken te zijn van legitieme of vertrouwde afzenders. *Spear phishing* is een gerichte phishing-aanval die zeer gerichte en aangepaste inhoud gebruikt die specifiek is afgestemd op de beoogde ontvangers (meestal na verkenning van de ontvangers door de aanvaller).

- U bent een globale beheerder of beveiligingsbeheerder

In Attack Simulator zijn twee verschillende soorten spear phishing-campagnes beschikbaar:

- [Multi-factor authenticatie/Voorwaardelijke toegang](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) is ingeschakeld, voor ten minste het globale beheerdersaccount en beveiligingsbeheerders die Attack Simulator zullen gebruiken. (Idealiter is meervoudige verificatie/voorwaardelijke toegang ingeschakeld voor alle gebruikers in uw organisatie.)

  - Een standaardpagina die uitlegt dat dit slechts een test was en geeft tips voor het herkennen van phishingberichten.

    ![Wat gebruikers zien als ze op de phishing-link klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - Een aangepaste pagina (URL) die u opgeeft.

- **Spear phishing (bijlage)**: De aanval probeert de ontvangers te overtuigen om een .docx of .pdf-bijlage in het bericht te openen. De bijlage bevat dezelfde inhoud van de standaard phishing-link, maar de eerste zin begint met " \<Display Name\> , je ziet dit bericht als een recent e-mailbericht dat je hebt geopend...".

> [!NOTE]
> Op dit moment verlopen spear phishing-campagnes in Attack Simulator niet.

### <a name="create-a-spear-phishing-campaign"></a>Maak een spear phishing campagne

Een belangrijk onderdeel van elke spear phishing campagne is het uiterlijk van het e-mailbericht dat wordt verzonden naar de beoogde ontvangers. Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:

- **Gebruik een ingebouwde e-mailsjabloon:** Er zijn twee ingebouwde sjablonen beschikbaar: **Giveaway en** **Payroll Update**. U sommige, alle of geen e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.

- **Een herbruikbare e-mailsjabloon maken:** Nadat u de e-mailsjabloon hebt gemaakt en opgeslagen, u deze opnieuw gebruiken in toekomstige spear phishing-campagnes. U sommige, alle of geen e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.

- **Het e-mailbericht maken in de wizard**: U het e-mailbericht rechtstreeks in de wizard maken terwijl u de spear phishing-campagne maakt en start.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Stap 1 (optioneel): een aangepaste e-mailsjabloon maken

Als u een van de ingebouwde sjablonen gaat gebruiken of het e-mailbericht rechtstreeks in de wizard gaat maken, u deze stap overslaan.

1. Ga in het Security & Compliance Center naar **Threat management** \> **Attack simulator**.

2. Klik op de pagina **Aanvallen simuleren** in de **secties Spear Phishing (Credentials Harvest)** of **Spear Phishing (Attachment)** op **Aanvalsgegevens.**

   Het maakt niet uit waar u de sjabloon maakt. De beschikbare opties in de sjabloon zijn hetzelfde voor beide soorten phishing-aanvallen.

3. Klik op de pagina **Aanvalsdetails** die wordt geopend in de sectie **Phishingsjablonen** in het gebied **Sjablonen maken** op **Nieuwe sjabloon**.

4. De wizard **Phishingsjabloon configureren** wordt gestart in een nieuwe flyout. Voer in de stap **Start** een unieke weergavenaam voor de sjabloon in en klik op **Volgende**.

5. Configureer in de stap **E-mailgegevens configureren** de volgende instellingen:

   - **Van (Naam)**: de weergavenaam die wordt gebruikt voor de afzender van het bericht.

   - **Van (E-mail)**: het e-mailadres van de afzender.

   - **URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst. Dit is de URL waarop gebruikers geneigd zullen zijn om op te klikken. De keuzes zijn:

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
     > <ul><li>Alle URL's zijn opzettelijk http, niet https.</li><li>Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren. Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.</li></ul>

   - **AANGEPASTE BESTEMMINGSPAGINA-URL:** Voer een optionele bestemmingspagina in waar gebruikers worden meegenomen als ze op de phishingkoppeling klikken en hun referenties invoeren. Deze koppeling vervangt de standaard bestemmingspagina. Als u bijvoorbeeld een interne bewustmakingstraining hebt, u die URL hier opgeven.

   - **Categorie**: Momenteel wordt deze instelling niet gebruikt (alles wat u invoert wordt genegeerd).

   - **Onderwerp**: Het veld **Onderwerp** van het e-mailbericht.

   Klik op **Volgende**als u klaar bent.

6. Maak in de stap **E-mail opstellen** de berichttekst van het e-mailbericht. U het tabblad **E-mail** (een rijke HTML-editor) of het tabblad **Bron** (raw HTML-code) gebruiken.

   De HTML-opmaak kan zo eenvoudig of complex zijn als u nodig hebt. U afbeeldingen en tekst invoegen om de geloofwaardigheid van het bericht in de e-mailclient van de ontvanger te verbeteren.

   - `${username}`hiermee wordt de naam van de ontvanger ingevoegd.

   - `${loginserverurl}`hiermee wordt de **URL-waarde van de phishing-aanmeldingsserver** van de vorige stap ingevoegd.

   Klik op **Volgende**als u klaar bent.

7. Klik **in** de stap Bevestigen op **Voltooien**.

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Stap 2: Maak en start de spear phishing-campagne

1. Ga in het Security & Compliance Center naar **Threat management** \> **Attack simulator**.

2. Maak op de pagina **Aanvallen simuleren** een van de volgende selecties op basis van het type campagne dat u wilt maken:

   - Klik in de sectie **Spear Phishing (Credential Harvest)** op **Aanval starten** of klik op **Aanvalsdetails** \> **startaanval**.

   - Klik in de sectie **Spear Phishing (Attachment)** op **Aanval starten** of klik op **Aanvalsdetails** \> **starten.**

3. De wizard **Phishing-aanval configureren** wordt gestart in een nieuwe flyout. Doe in de stap **Start** een van de volgende stappen:

   - Voer in het vak **Naam** een unieke weergavenaam voor de campagne in. Klik niet op **Sjabloon gebruiken,** omdat u het e-mailbericht later in de wizard maakt.

   - Klik **op Sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mailsjabloon. Nadat u de sjabloon hebt geselecteerd, wordt het vak Naam automatisch gevuld op basis **van** de sjabloon, maar u de naam wijzigen.

   ![Startpagina phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Klik op **Volgende**als u klaar bent.

4. Voert in de stap **Doelontvangers** een van de volgende stappen uit:

   - Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren. Elke beoogde ontvanger moet een Exchange Online-postvak hebben. Als u op **Filter** en **Toepassen klikt** zonder een zoekcriteria in te voeren, worden alle geadresseerden teruggestuurd en aan de campagne toegevoegd.

   - Klik **op Bestand importeren** en bestanden **importeren** om een door komma's gescheiden waarde (CSV) of door regel gescheiden bestand met e-mailadressen te importeren. Elke regel moet het e-mailadres van de ontvanger bevatten.

   Klik op **Volgende**als u klaar bent.

5. Configureer in de stap **E-mailgegevens configureren** de volgende instellingen:

   Als u een sjabloon hebt geselecteerd in de stap **Start,** zijn de meeste van deze waarden al geconfigureerd, maar u deze wijzigen.

   - **Van (Naam)**: de weergavenaam die wordt gebruikt voor de afzender van het bericht.

   - **Van (E-mail)**: het e-mailadres van de afzender. U een echt of nep e-mailadres invoeren vanuit het e-maildomein van uw organisatie, of u een echt of nep extern e-mailadres invoeren. Een geldig e-mailadres van uw organisatie wordt daadwerkelijk opgelost in de e-mailclient van de ontvanger.

   - **URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst. Dit is de URL waarop gebruikers geneigd zullen zijn om op te klikken. De keuzes zijn:

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
     > <ul><li>Alle URL's zijn opzettelijk http, niet https.</li><li>Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren. Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.</li><li>U moet een URL selecteren. Voor <b>Spear Phishing (Attachment)</b> campagnes u de koppeling in de volgende stap verwijderen uit de hoofdtekst van het bericht (anders bevat het bericht zowel een <b>link</b> als een bijlage).</li></ul>

   - **Bijlagetype:** deze instelling is alleen beschikbaar in **Spear Phishing -campagnes (Attachment).** Klik op de vervolgkeuzelijst en selecteer **. DOCX** **of. PDF** uit de lijst.

   - **Bijlagenaam:** deze instelling is alleen beschikbaar in **Spear Phishing -campagnes (Attachment).** Voer een bestandsnaam in voor de bijlage .docx of .pdf.

   - **AANGEPASTE BESTEMMINGSPAGINA-URL:** Voer een optionele bestemmingspagina in waar gebruikers worden meegenomen als ze op de phishingkoppeling klikken en hun referenties invoeren. Deze koppeling vervangt de standaard bestemmingspagina. Als u bijvoorbeeld een interne bewustmakingstraining hebt, u die URL hier opgeven.

   - **Onderwerp**: Het veld **Onderwerp** van het e-mailbericht.

   Klik op **Volgende**als u klaar bent.

6. Maak in de stap **E-mail opstellen** de berichttekst van het e-mailbericht. Als u een sjabloon hebt geselecteerd in de stap **Start,** is de berichttekst al geconfigureerd, maar u deze aanpassen. U het tabblad **E-mail** (een rijke HTML-editor) of het tabblad **Bron** (raw HTML-code) gebruiken.

   De HTML-opmaak kan zo eenvoudig of complex zijn als u nodig hebt. U afbeeldingen en tekst invoegen om de geloofwaardigheid van het bericht in de e-mailclient van de ontvanger te verbeteren.

   - `${username}`hiermee wordt de naam van de ontvanger ingevoegd.

   - `${loginserverurl}`hiermee wordt de **URL-waarde van de phishing-inlogserver** ingevoegd.

   Voor **Spear Phishing (Attachment)** campagnes moet u de koppeling verwijderen uit de hoofdtekst van het bericht (anders bevat het bericht zowel een **koppeling** als een bijlage en worden linkklikken niet bijgehouden in een bijlagecampagne).

   ![E-mailtekst opstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Klik op **Volgende**als u klaar bent.

7. Klik **in** de stap Bevestigen op **Voltooien** om de campagne te starten. Het phishingbericht wordt bezorgd bij de beoogde ontvangers.

## <a name="password-attack-campaigns"></a>Campagnes voor wachtwoordaanvallen

Een *wachtwoordaanval* probeert wachtwoorden voor gebruikersaccounts in een organisatie te raden, meestal nadat de aanvaller een of meer geldige gebruikersaccounts heeft geïdentificeerd.

In Attack Simulator zijn twee verschillende soorten wachtwoordaanvalscampagnes beschikbaar om de complexiteit van de wachtwoorden van uw gebruikers te testen:

- **Brute force wachtwoord (woordenboek aanval)**: Een *brute kracht* of *woordenboek* aanval maakt gebruik van een groot woordenboek bestand van wachtwoorden op een gebruikersaccount in de hoop dat een van hen zal werken (veel wachtwoorden tegen een account). Onjuiste wachtwoord lock-outs helpen af te schrikken brute force wachtwoord aanvallen.

  Voor de woordenboekaanval u een of meerdere wachtwoorden opgeven om te proberen (handmatig ingevoerd of in een geüpload bestand) en u een of meerdere gebruikers opgeven.

- **Wachtwoord spray aanval**: Een *wachtwoord spray* aanval maakt gebruik van hetzelfde zorgvuldig overwogen wachtwoord tegen een lijst van gebruikersaccounts (een wachtwoord tegen veel accounts). Wachtwoord spray aanvallen zijn moeilijker te detecteren dan brute force wachtwoord aanvallen (de kans op succes toeneemt wanneer een aanvaller probeert een wachtwoord over tientallen of honderden accounts zonder het risico van struikelen van de gebruiker onjuiste wachtwoord lock-out).

  Voor de wachtwoordsprayaanval u slechts één wachtwoord opgeven om te proberen en u een of meer gebruikers opgeven.

> [!NOTE]
> De wachtwoordaanvallen in Attack Simulator geven gebruikersnaam en wachtwoord basic auth-verzoeken door naar een eindpunt, zodat ze ook werken met andere verificatiemethoden (AD FS, password hash sync, pass-through, PingFederate, enz.). Voor gebruikers die MFA hebben ingeschakeld, zelfs als de wachtwoordaanval hun werkelijke wachtwoord probeert, wordt de poging altijd geregistreerd als een fout (met andere woorden, MFA-gebruikers zullen nooit worden weergegeven in het aantal **succesvolle pogingen** van de campagne). Dit is het verwachte resultaat. MFA is een primaire methode om te helpen beschermen tegen wachtwoordaanvallen.

### <a name="create-and-launch-a-password-attack-campaign"></a>Een campagne voor wachtwoordaanvallen maken en starten

1. Ga in het Security & Compliance Center naar **Threat management** \> **Attack simulator**.

2. Maak op de pagina **Aanvallen simuleren** een van de volgende selecties op basis van het type campagne dat u wilt maken:

   - Klik in de sectie **Brute Force Password (Dictionary Attack)** op **Aanval starten** of klik op **Aanvalsdetails** \> **startaanval**.

   - Klik in de sectie **Wachtwoordspray-aanval** op **Aanval starten** of klik op **Aanvalsdetails** \> **startaanval**.

3. De wizard **Wachtwoordaanval configureren** wordt gestart in een nieuwe flyout. Voer in de stap **Start** een unieke weergavenaam voor de campagne in en klik op **Volgende**.

4. Voert in de stap **Doelgebruikers** een van de volgende stappen uit:

   - Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren. Elke beoogde ontvanger moet een Exchange Online-postvak hebben. Als u op **Filter** en **Toepassen klikt** zonder een zoekcriteria in te voeren, worden alle geadresseerden teruggestuurd en aan de campagne toegevoegd.

   - Klik **op Bestand importeren** en bestanden **importeren** om een door komma's gescheiden waarde (CSV) of door regel gescheiden bestand met e-mailadressen te importeren. Elke regel moet het e-mailadres van de ontvanger bevatten.

   Klik op **Volgende**als u klaar bent.

5. Kies in de stap **Aanvalsinstellingen kiezen** wat u wilt doen op basis van het campagnetype:

   - **Brute Force Password (Dictionary Attack)**: Doe een van de volgende stappen:

     - **Wachtwoorden handmatig invoeren**: typ in **het vak Druk op Enter om een wachtwoordvak toe te voegen** een wachtwoord en druk op ENTER. Herhaal deze stap zo vaak als nodig is.

     - **Wachtwoorden uploaden uit een woordenboekbestand**: klik op **Uploaden** om een bestaand tekstbestand te importeren dat één wachtwoord op elke regel en een lege laatste regel bevat. Het tekstbestand moet 10 MB of minder groot zijn en mag niet meer dan 30000 wachtwoorden bevatten.

   - **Wachtwoord spray aanval**: Voer in **het wachtwoord(en) te gebruiken in het** aanvalsvak, voer een wachtwoord in.

   Klik op **Volgende**als u klaar bent.

6. Klik **in** de stap Bevestigen op **Voltooien** om de campagne te starten. De wachtwoorden die u hebt opgegeven, worden beproefd op gebruikers die u hebt opgegeven.

## <a name="view-campaign-results"></a>Campagneresultaten weergeven

Nadat u een campagne hebt gestart, u de voortgang en resultaten controleren op de pagina **Hoofdaanvallen simuleren.**

Actieve campagnes tonen een statusbalk, een voltooid percentage waarde en "(voltooide gebruikers) van (totale gebruikers)" tellen. Als u op de knop **Vernieuwen** klikt, wordt de voortgang van actieve campagnes bijgewerkt. U ook op **Beëindigen** klikken om een actieve campagne te stoppen.

Wanneer de campagne is voltooid, wordt de status **gewijzigd in Aanval voltooid**. U de resultaten van de campagne bekijken door een van de volgende acties uit te voeren:

- Klik op de hoofdpagina **van aanvallen simuleren** op **Rapport weergeven** onder de naam van de campagne.

- Klik op de hoofdpagina **aanvallen simuleren** op **Aanvalsdetails** in de sectie voor het type aanval. Selecteer op de pagina **Aanvalsdetails** die wordt geopend de campagne in de sectie **Aanvalsgeschiedenis.**

Een van de vorige acties brengt u naar een pagina met de naam **Attack details**. De informatie die beschikbaar is op deze pagina voor elk type campagne wordt beschreven in de volgende secties.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Spear Phishing (Credentials Harvest) campagne resultaten

De volgende informatie is beschikbaar op de pagina **Aanvalsgegevens** voor elke campagne:

- De duur (begindatum/tijd en einddatum/tijd) van de campagne.

- **Totaal aantal beoogde gebruikers**

- **Geslaagde pogingen**: het aantal gebruikers dat op de link heeft geklikt **en** hun referenties heeft ingevoerd *(elke* gebruikersnaam en wachtwoordwaarde).

- **Algemeen slagingspercentage:** een percentage dat wordt berekend door **succesvolle pogingen**die totale  /  **gebruikers targeten.**

- **Snelste klik:** Hoe lang het duurde voordat de eerste gebruiker op de link klikte nadat u de campagne had gestart.

- **Gemiddelde klik:** de som van hoe lang het duurde iedereen om te klikken op de link gedeeld door het aantal gebruikers die op de link geklikt.

- **Klik op Slagingspercentage:** een percentage dat wordt berekend door (aantal gebruikers dat op de link heeft geklikt) / **Totaal gericht gebruikers**.

- **Snelste referenties:** Hoe lang het duurde voordat de eerste gebruiker zijn referenties invoerde nadat u de campagne had gestart.

- **Gemiddelde referenties:** de som van hoe lang het duurde iedereen om hun referenties gedeeld door het aantal gebruikers die hun referenties ingevoerd in te voeren.

- **Succespercentage referenties:** een percentage dat wordt berekend door (aantal gebruikers die hun referenties hebben ingevoerd) / **Totaal gericht gebruikers.**

- Een staafgrafiek met de **klik op** de koppeling en de opgegeven nummers **per** dag.

- Een cirkelgrafiek met de **link waarop is geklikt,** **Referenties geleverd**en **Geen** percentages voor de campagne.

- In de sectie **Gecompromitteerde gebruikers** worden de gegevens weergegeven van de gebruikers die op de koppeling hebben geklikt:

  - Het e-mailadres van de gebruiker

  - De datum/tijd waarop ze op de link hebben geklikt.

  - Het IP-adres van de client.

  - Details over de versie van Windows en de webbrowser van de gebruiker.

  U op **Exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.

### <a name="spear-phishing-attachment-campaign-results"></a>Campagneresultaten van Spear Phishing (Attachment)

De volgende informatie is beschikbaar op de pagina **Aanvalsgegevens** voor elke campagne:

- De duur (begindatum/tijd en einddatum/tijd) van de campagne.

- **Totaal aantal beoogde gebruikers**

- **Geslaagde pogingen**: het aantal gebruikers dat de bijlage heeft geopend of gedownload en heeft geopend (preview telt niet mee).

- **Algemeen slagingspercentage:** een percentage dat wordt berekend door **succesvolle pogingen**die totale  /  **gebruikers targeten.**

- **Snelste bevestigingsvrije tijd**: Hoe lang het duurde voordat de eerste gebruiker de bijlage opende nadat u de campagne had gestart.

- **Gemiddelde gehechtheidsopentijd**: De som van hoe lang het duurde voordat iedereen de bijlage opende, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.

- **Slagingspercentage voor bijlageopen**: een percentage dat wordt berekend door (aantal gebruikers dat de bijlage heeft geopend) / **Totaal gericht gebruikers**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Brute Force Password (Dictionary Attack) campagne resultaten

De volgende informatie is beschikbaar op de pagina **Aanvalsgegevens** voor elke campagne:

- De duur (begindatum/tijd en einddatum/tijd) van de campagne.

- **Totaal aantal beoogde gebruikers**

- **Geslaagde pogingen**: het aantal gebruikers dat een van de opgegeven wachtwoorden bleek te gebruiken.

- **Algemeen slagingspercentage:** een percentage dat wordt berekend door **succesvolle pogingen**die totale  /  **gebruikers targeten.**

- De sectie **Gecompromitteerde gebruikers** bevat de e-mailadressen van de getroffen gebruikers. U op **Exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.

### <a name="password-spray-attack-campaign-results"></a>Resultaten van de campagne met wachtwoordspray-aanvallen

De volgende informatie is beschikbaar op de pagina **Aanvalsgegevens** voor elke campagne:

- De duur (begindatum/tijd en einddatum/tijd) van de campagne.

- **Totaal aantal beoogde gebruikers**

- **Geslaagde pogingen**: het aantal gebruikers dat het opgegeven wachtwoord bleek te gebruiken.

- **Algemeen slagingspercentage:** een percentage dat wordt berekend door **succesvolle pogingen**die totale  /  **gebruikers targeten.**
