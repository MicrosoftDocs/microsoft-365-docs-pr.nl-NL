---
title: Attack Simulator in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze Attack Simulator kunnen gebruiken om gesimuleerde phishing- en wachtwoordaanvallen uit te voeren in hun Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2-organisaties.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 105ca66cdfacaab3b73d8bf89c3a05207b673a3c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921358"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Attack Simulator in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op** [Microsoft Defender voor Office 365-abonnement 2](office-365-atp.md)

Als uw organisatie Microsoft Defender voor Office 365 Plan 2 heeft, met mogelijkheden voor bedreigingsonderzoek en [antwoord,](office-365-ti.md)kunt u Attack Simulator gebruiken in het Beveiligings- & Compliancecentrum om realistische aanvalsscenario's in uw organisatie uit te voeren. Deze gesimuleerde aanvallen kunnen u helpen bij het identificeren en vinden van kwetsbare gebruikers voordat een echte aanval van invloed is op uw bottom line. Lees dit artikel voor meer informatie.

> [!NOTE]
>
> Attack Simulator, zoals beschreven in dit artikel, is nu alleen-lezen en is vervangen door **attack-simulatietraining** in het e-mail-&-samenwerkings knooppunt in het [Microsoft 365-beveiligingscentrum.](https://security.microsoft.com)  Zie Aan de slag [met de trainingstraining Aanvalssimulatie voor meer informatie.](attack-simulation-training-get-started.md)
>
> De mogelijkheid om nieuwe simulaties te starten vanuit deze versie van Attack Simulator is uitgeschakeld. Vanaf 24 januari 2021 hebt u echter nog steeds toegang tot rapporten voor maximaal 90 dagen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen. Attack simulator is beschikbaar op **Threat management** \> **Attack simulator**. Ga rechtstreeks naar de aanvalssimulator, open <https://protection.office.com/attacksimulator> .

- Zie Microsoft [Defender voor Office 365-servicebeschrijving](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie over de beschikbaarheid van Attack Simulator in verschillende Microsoft 365-abonnementen.

- U moet lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Uw account moet zijn geconfigureerd voor meervoudige verificatie (MFA) om campagnes te maken en te beheren in Attack Simulator. Zie Meervoudige verificatie instellen voor [instructies.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Attack Simulator werkt alleen in postvakken in de cloud.

- Phishingcampagnes verzamelen en verwerken gebeurtenissen voor 30 dagen. Historische campagnegegevens zijn beschikbaar tot 90 dagen nadat u de campagne hebt gestart.

- Aanvalssimulatie en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365-services. Zie Microsoft [365-gegevenslocaties](../../enterprise/o365-data-locations.md)voor meer informatie.

- Er zijn geen bijbehorende PowerShell-cmdlets voor Attack Simulator.

## <a name="spear-phishing-campaigns"></a>Phishingcampagnes voor speer

*Phishing* is een algemene term voor e-mailaanvallen die gevoelige informatie proberen te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. *Phishing via phishing* is een gerichte phishing-aanval die gerichte en aangepaste inhoud gebruikt die specifiek is afgestemd op de geadresseerden (meestal na verkenning van de geadresseerden door de aanvaller).

In Attack Simulator zijn twee verschillende typen phishingcampagnes beschikbaar:

- **Phishing van de speer (referenties oogst)**: De aanval probeert de geadresseerden te overtuigen om op een URL in het bericht te klikken. Als ze op de koppeling klikken, wordt hen gevraagd hun referenties in te voeren. Als ze dat doen, worden ze naar een van de volgende locaties overgebracht:

  - Een standaardpagina waarin wordt uitgelegd dat dit slechts een test was en tips geeft voor het herkennen van phishingberichten.

    ![Wat gebruikers zien als ze op de phishingkoppeling klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - Een aangepaste pagina (URL) die u opgeeft.

- **Phishing van de speer (bijlage)**: De aanval probeert de geadresseerden te overtuigen om een .docx- of .pdf-bijlage in het bericht te openen. De bijlage bevat dezelfde inhoud van de standaardkoppeling phishing, maar de eerste zin begint met " , u ziet dit bericht als een recent e-mailbericht \<Display Name\> dat u hebt geopend...".

> [!NOTE]
> Momenteel verlopen phishingcampagnes in Attack Simulator niet.

### <a name="create-a-spear-phishing-campaign"></a>Een phishingcampagne voor een speer maken

Een belangrijk onderdeel van een phishingcampagne is het uiterlijk van het e-mailbericht dat naar de geadresseerden wordt verzonden. Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:

- **Gebruik een ingebouwde e-mailsjabloon:** Er zijn twee ingebouwde sjablonen beschikbaar: **Prijs giveaway** en **Salarisupdate.** U kunt sommige, alle of geen e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.

- **Een herbruikbare e-mailsjabloon** maken: nadat u de e-mailsjabloon hebt gemaakt en opgeslagen, kunt u deze opnieuw gebruiken in toekomstige phishingcampagnes. U kunt sommige, alle of geen e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.

- **Maak het e-mailbericht in de wizard:** U kunt het e-mailbericht rechtstreeks in de wizard maken terwijl u de phishingcampagne voor de speer maakt en start.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Stap 1 (optioneel): een aangepaste e-mailsjabloon maken

Als u een van de ingebouwde sjablonen gaat gebruiken of het e-mailbericht rechtstreeks in de wizard wilt maken, kunt u deze stap overslaan.

1. Ga in het & Compliance center naar **Threat management** \> **Attack simulator**.

2. Klik op **de pagina** Aanvallen simuleren in de secties Phishing van **de speer (Referenties oogst)** of **In** bijlage op Details van aanvallen **.**

   Het maakt niet uit waar u de sjabloon maakt. De beschikbare opties in de sjabloon zijn hetzelfde voor beide typen phishing-aanvallen.

3. Klik op de pagina Aanvalsdetails die wordt geopend in de sectie **Phishingsjablonen** in het gebied **Sjablonen** maken op **Nieuwe sjabloon.** 

4. De **wizard Phishingsjabloon** configureren wordt gestart in een nieuwe flyout. Voer in **de stap** Start een unieke weergavenaam voor de sjabloon in en klik vervolgens op **Volgende.**

5. Configureer **in de stap E-maildetails** configureren de volgende instellingen:

   - **Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.

   - **Van (e-mail)**: het e-mailadres van de afzender.

   - **URL van de phishing-aanmeldingsserver:** Klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst. Dit is de URL waar gebruikers op zullen klikken. De keuzen zijn:

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
     > Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren. Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.

   - **Aangepaste landingspagina-URL:** Voer een optionele landingspagina in waarin gebruikers worden meegenomen als ze op de phishingkoppeling klikken en hun referenties invoeren. Deze koppeling vervangt de standaard landingspagina. Als u bijvoorbeeld training voor interne bewustmaking hebt, kunt u deze URL hier opgeven.

   - **Categorie:** Deze instelling wordt momenteel niet gebruikt (alles wat u in typt, wordt genegeerd).

   - **Onderwerp:** Het **veld Onderwerp** van het e-mailbericht.

   Wanneer u klaar bent, klikt u op **Volgende.**

6. Maak in **de stap E-mail** opstellen de berichtin body van het e-mailbericht. U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad Bron** (onbewerkte HTML-code) gebruiken.

   De HTML-opmaak kan zo eenvoudig of complex zijn als u dat nodig hebt. U kunt afbeeldingen en tekst invoegen om de geloofwaardigheid van het bericht in de e-mailclient van de geadresseerde te verbeteren.

   - `${username}` hiermee voegt u de naam van de geadresseerde in.

   - `${loginserverurl}` hiermee voegt u de **URL-waarde phishing-aanmeldingsserver** in van de vorige stap.

   Wanneer u klaar bent, klikt u op **Volgende.**

7. Klik in **de stap** Bevestigen op **Voltooien.**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Stap 2: De phishingcampagne voor de speer maken en starten

1. Ga in het & Compliance center naar **Threat management** \> **Attack simulator**.

2. Maak op **de** pagina Aanvallen simuleren een van de volgende selecties op basis van het type campagne dat u wilt maken:

   - Klik in de sectie Speer phishing **(referenties oogst)** op **Aanval starten** of klik **op Aanvalsdetails** \> **starten aanval.**

   - Klik in de sectie Phishing van de speer **(bijlage)** op **Aanval starten of** klik op **Aanvalsdetails** \> **starten.**

3. De **wizard Phishing-aanval** configureren begint in een nieuwe flyout. Ga in **de stap** Start op een van de volgende stappen te werk:

   - Voer in **het** vak Naam een unieke weergavenaam voor de campagne in. Klik niet op Sjabloon **gebruiken,** omdat u het e-mailbericht later in de wizard maakt.

   - Klik **op Sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mailsjabloon. Nadat u de sjabloon hebt geselecteerd, wordt het vak **Naam** automatisch opgevuld op basis van de sjabloon, maar u kunt de naam wijzigen.

   > [!div class="mx-imgBorder"]
   > ![Startpagina phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Wanneer u klaar bent, klikt u op **Volgende.**

4. Ga in **de stap Doel geadresseerden** op een van de volgende stappen te werk:

   - Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren. Elke geadresseerde moet een Exchange Online-postvak hebben. Als u op **Filteren en** **Toepassen klikt** zonder een zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.

   - Klik **op Importeren** en vervolgens **bestand** importeren om een door komma's gescheiden waarde (CSV) of een door regel gescheiden bestand met e-mailadressen te importeren. Elke regel moet het e-mailadres van de geadresseerde bevatten.

   Wanneer u klaar bent, klikt u op **Volgende.**

5. Configureer **in de stap E-maildetails** configureren de volgende instellingen:

   Als u een sjabloon hebt geselecteerd in de **stap Start,** zijn de meeste van deze waarden al geconfigureerd, maar u kunt deze wijzigen.

   - **Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.

   - **Van (e-mail)**: het e-mailadres van de afzender. U kunt een echt of nep-e-mailadres invoeren vanuit het e-maildomein van uw organisatie, of u kunt een echt of nep extern e-mailadres invoeren. Een geldig e-mailadres van de afzender van uw organisatie wordt daadwerkelijk opgelost in de e-mailclient van de geadresseerde.

   - **URL van de phishing-aanmeldingsserver:** Klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst. Dit is de URL waar gebruikers op zullen klikken. De keuzen zijn:

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
     > - Alle URL's zijn opzettelijk http, niet https.
     >
     > - Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren. Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.
     >
     > - U moet een URL selecteren. Voor **phishingcampagnes (bijlage)** kunt u de koppeling in de volgende stap uit de hoofdbeslag van het bericht verwijderen (anders bevat het bericht zowel een **koppeling** als een bijlage).

   - **Type bijlage:** deze instelling is alleen beschikbaar in **campagnes met Phishing-e-mail (Bijlage).** Klik op de vervolgkeuzekeuze en selecteer **. DOCX** of **. PDF** uit de lijst.

   - **Naam van bijlage:** deze instelling is alleen beschikbaar in **Campagnes voor Phishing van de e-mail (Bijlage).** Voer een bestandsnaam in voor de .docx- of PDF-bijlage.

   - **Aangepaste landingspagina-URL:** Voer een optionele landingspagina in waarin gebruikers worden meegenomen als ze op de phishingkoppeling klikken en hun referenties invoeren. Deze koppeling vervangt de standaard landingspagina. Als u bijvoorbeeld training voor interne bewustmaking hebt, kunt u deze URL hier opgeven.

   - **Onderwerp:** Het **veld Onderwerp** van het e-mailbericht.

   Wanneer u klaar bent, klikt u op **Volgende.**

6. Maak in **de stap E-mail** opstellen de berichtin body van het e-mailbericht. Als u een sjabloon hebt geselecteerd in de **stap Start,** is de berichtinstelling al geconfigureerd, maar u kunt deze aanpassen. U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad Bron** (onbewerkte HTML-code) gebruiken.

   De HTML-opmaak kan zo eenvoudig of complex zijn als u dat nodig hebt. U kunt afbeeldingen en tekst invoegen om de geloofwaardigheid van het bericht in de e-mailclient van de geadresseerde te verbeteren.

   - `${username}` hiermee voegt u de naam van de geadresseerde in.

   - `${loginserverurl}` hiermee voegt u de **URL-waarde phishing-aanmeldingsserver** in.

   Voor **Phishing-campagnes (Bijlage)** moet u de koppeling verwijderen uit de hoofdbeslag van het bericht (anders bevat het bericht zowel een **koppeling** als een bijlage, en worden klikken op koppeling niet bijgeplagd in een bijlagecampagne).

   > [!div class="mx-imgBorder"]
   > ![E-mail op te stellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Wanneer u klaar bent, klikt u op **Volgende.**

7. Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten. Het phishingbericht wordt bezorgd bij de beoogde geadresseerden.

## <a name="password-attack-campaigns"></a>Wachtwoord aanvalscampagnes

Met *een wachtwoordaanval* wordt geprobeerd wachtwoorden te raden voor gebruikersaccounts in een organisatie, meestal nadat de aanvaller een of meer geldige gebruikersaccounts heeft geïdentificeerd.

In Attack Simulator zijn er twee verschillende typen wachtwoord aanvalscampagnes beschikbaar om de complexiteit van de wachtwoorden van uw gebruikers te testen:

- **Brute force password (dictionary attack)**  : Bij een aanval met een brute kracht of woordenlijst wordt een groot woordenlijstbestand met wachtwoorden op een gebruikersaccount gebruikt in de hoop dat een van deze wachtwoorden werkt (veel wachtwoorden voor één account).  Onjuiste wachtwoordvergrendelingen helpen bij het voorkomen van brute force wachtwoordaanvallen.

  Voor de woordenlijst-aanval kunt u een of meer wachtwoorden opgeven om te proberen (handmatig ingevoerd of in een geüpload bestand) en kunt u een of meer gebruikers opgeven.

- **Wachtwoordinfarct**: Bij een *wachtwoordinfarct* wordt hetzelfde zorgvuldig overwogen wachtwoord gebruikt voor een lijst met gebruikersaccounts (één wachtwoord voor veel accounts). Wachtwoordsproeiaanvallen zijn moeilijker te detecteren dan brute force wachtwoordaanvallen (de kans op succes neemt toe wanneer een aanvaller één wachtwoord probeert op tientallen of honderden accounts zonder dat het risico bestaat dat de gebruiker het onjuiste wachtwoord wordt vergrendeld).

  Voor de wachtwoordinfarct kunt u slechts één wachtwoord opgeven om te proberen en kunt u een of meer gebruikers opgeven.

> [!NOTE]
> De wachtwoordaanvallen in Attack Simulator geven gebruikersnaam en wachtwoord eenvoudige auth-aanvragen door aan een eindpunt, zodat ze ook werken met andere verificatiemethoden (AD FS, wachtwoordhashsynchronisatie, pass-through, PingFederate, enzovoort). Voor gebruikers die MFA hebben ingeschakeld, zelfs als met de wachtwoordaanval het werkelijke wachtwoord wordt geprobeerd, wordt de  poging altijd geregistreerd als een fout (met andere woorden: MFA-gebruikers worden nooit weergegeven in het aantal geslaagde pogingen van de campagne). Dit is het verwachte resultaat. MFA is een primaire methode om u te beschermen tegen wachtwoordaanvallen.

### <a name="create-and-launch-a-password-attack-campaign"></a>Een wachtwoord aanvalscampagne maken en starten

1. Ga in het & Compliance center naar **Threat management** \> **Attack simulator**.

2. Maak op **de** pagina Aanvallen simuleren een van de volgende selecties op basis van het type campagne dat u wilt maken:

   - Klik in **de sectie Brute Force Password (Dictionary Attack)** op Aanval **starten** of klik op **Aanvalsdetails** \> **starten**.

   - klik in **de sectie Password spray attack** op Aanval starten **of** klik **op Aanvalsdetails** \> **starten.**

3. De **wizard Wachtwoordinfarct** configureren wordt gestart in een nieuw flyout. Voer in **de stap** Start een unieke weergavenaam voor de campagne in en klik vervolgens op **Volgende.**

4. Ga in **de stap Doelgebruikers** op een van de volgende stappen te werk:

   - Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren. Elke geadresseerde moet een Exchange Online-postvak hebben. Als u op **Filteren en** **Toepassen klikt** zonder een zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.

   - Klik **op Importeren** en vervolgens **bestand** importeren om een door komma's gescheiden waarde (CSV) of een door regel gescheiden bestand met e-mailadressen te importeren. Elke regel moet het e-mailadres van de geadresseerde bevatten.

   Wanneer u klaar bent, klikt u op **Volgende.**

5. Kies in **de stap Aanvalsinstellingen** kiezen wat u moet doen op basis van het campagnetype:

   - **Brute Force Password (Dictionary Attack)**: Ga op een van de volgende stappen te werk:

     - **Wachtwoorden handmatig invoeren:** Typ in het vak Druk op **Enter** om een wachtwoord toe te voegen een wachtwoord en druk vervolgens op Enter. Herhaal deze stap zo vaak als nodig is.

     - **Wachtwoorden uploaden uit een woordenlijstbestand:** Klik op **Uploaden** om een bestaand tekstbestand te importeren dat één wachtwoord op elke regel en een lege laatste regel bevat. Het tekstbestand moet 10 MB of kleiner zijn en mag niet meer dan 30000 wachtwoorden bevatten.

   - **Wachtwoordinfarct**: Voer in **Het wachtwoord(en)** dat u wilt gebruiken in het aanvalsvak één wachtwoord in.

   Wanneer u klaar bent, klikt u op **Volgende.**

6. Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten. De wachtwoorden die u hebt opgegeven, worden beproefd voor gebruikers die u hebt opgegeven.

## <a name="view-campaign-results"></a>Campagneresultaten weergeven

Nadat u een campagne hebt gestart, kunt u de voortgang en resultaten controleren op de **hoofdpagina Aanvallen simuleren.**

In actieve campagnes worden een statusbalk, een voltooid percentage en '(voltooide gebruikers) van (totaal aantal gebruikers)' geteld. Als u op **de knop** Vernieuwen klikt, wordt de voortgang van actieve campagnes bijgewerkt. U kunt ook op **Beëindigen klikken om** een actieve campagne te stoppen.

Wanneer de campagne is voltooid, wordt de status gewijzigd in **Aanval voltooid.** U kunt de resultaten van de campagne bekijken door een van de volgende acties uit te voeren:

- Klik op de **hoofdpagina Aanvallen simuleren** op **Rapport weergeven** onder de naam van de campagne.

- Klik op de **hoofdpagina Aanvallen simuleren** op **Details van** aanvallen in de sectie voor het type aanval. Selecteer op de pagina Aanvalsdetails die wordt geopend de campagne in **de sectie Aanvalsgeschiedenis.** 

Met een van de vorige acties gaat u naar een pagina met de naam **Details van de aanval.** De informatie die beschikbaar is op deze pagina voor elk type campagne, wordt beschreven in de volgende secties.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Campagneresultaten van De phishing van de speer (Referenties oogst)

De volgende informatie is beschikbaar op de **pagina Details van de aanval** voor elke campagne:

- De duur (begindatum/tijd en einddatum/tijd) van de campagne.

- **Totaal aantal gebruikers dat is gericht**

- **Geslaagde pogingen:** het aantal gebruikers dat op de koppeling heeft geklikt **en** hun referenties heeft ingevoerd *(elke* gebruikersnaam en wachtwoordwaarde).

- **Algehele slagingspercentage:** een percentage dat wordt berekend door **Succesvolle pogingen** Totaal aantal  /  **beoogde gebruikers.**

- **Snelste klik:** hoe lang het duurde voordat de eerste gebruiker op de koppeling klikt nadat u de campagne hebt gestart.

- **Gemiddelde klik:** de som van hoe lang het duurde voordat iedereen op de koppeling klikt, gedeeld door het aantal gebruikers dat op de koppeling heeft geklikt.

- **Klik op Slagingspercentage:** een percentage dat wordt berekend op basis van (het aantal gebruikers dat op de koppeling heeft geklikt) / **Totaal aantal gebruikers dat is getarget.**

- **Snelste referenties:** Hoe lang het duurde voordat de eerste gebruiker zijn of haar referenties invoerde nadat u de campagne hebt gestart.

- **Gemiddelde referenties:** de som van de tijd die iedereen nodig heeft om zijn of haar referenties in te voeren, gedeeld door het aantal gebruikers dat zijn of haar referenties heeft ingevoerd.

- **Succespercentage referenties:** een percentage dat wordt berekend op basis van (het aantal gebruikers dat hun referenties heeft ingevoerd) / **Totaal aantal gebruikers dat is getarget.**

- Een staafdiagram met de **door koppeling geklikte** en **opgegeven** referenties per dag.

- Een cirkeldiagram met de **gekoppelde** klik , **opgegeven** referenties en **Geen** percentages voor de campagne.

- De **sectie Gecompromitteerde** gebruikers bevat de details van de gebruikers die op de koppeling hebben geklikt:

  - Het e-mailadres van de gebruiker

  - De datum/tijd waarop ze op de koppeling hebben geklikt.

  - Het IP-adres van de client.

  - Details over de versie van Windows en de webbrowser van de gebruiker.

  U kunt op **Exporteren klikken** om de resultaten naar een CSV-bestand te exporteren.

### <a name="spear-phishing-attachment-campaign-results"></a>Campagneresultaten van De phishing-campagne (Bijlage) van De speer

De volgende informatie is beschikbaar op de **pagina Details van de aanval** voor elke campagne:

- De duur (begindatum/tijd en einddatum/tijd) van de campagne.

- **Totaal aantal gebruikers dat is gericht**

- **Geslaagde pogingen:** het aantal gebruikers dat de bijlage heeft geopend of gedownload en geopend (voorbeeld telt niet).

- **Algehele slagingspercentage:** een percentage dat wordt berekend door **Succesvolle pogingen** Totaal aantal  /  **beoogde gebruikers.**

- **Snelste geopende bijlage:** Hoe lang het duurde voordat de eerste gebruiker de bijlage heeft geopend nadat u de campagne hebt gestart.

- **Gemiddelde opentijd van bijlage:** de som van de tijd die iedereen nodig had om de bijlage te openen, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.

- **Aantal geopende bijlagen:** een percentage dat wordt berekend op basis van (het aantal gebruikers dat de bijlage heeft geopend) / **Het totale aantal gebruikers dat is getarget.**

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Campagneresultaten van Brute Force Password (Dictionary Attack)

De volgende informatie is beschikbaar op de **pagina Details van de aanval** voor elke campagne:

- De duur (begindatum/tijd en einddatum/tijd) van de campagne.

- **Totaal aantal gebruikers dat is gericht**

- **Geslaagde pogingen:** het aantal gebruikers dat een van de opgegeven wachtwoorden heeft gebruikt.

- **Algehele slagingspercentage:** een percentage dat wordt berekend door **Succesvolle pogingen** Totaal aantal  /  **beoogde gebruikers.**

- De **sectie Gecompromitteerde** gebruikers bevat de e-mailadressen van de getroffen gebruikers. U kunt op **Exporteren klikken** om de resultaten naar een CSV-bestand te exporteren.

### <a name="password-spray-attack-campaign-results"></a>Campagneresultaten met wachtwoordsproeiactie

De volgende informatie is beschikbaar op de **pagina Details van de aanval** voor elke campagne:

- De duur (begindatum/tijd en einddatum/tijd) van de campagne.

- **Totaal aantal gebruikers dat is gericht**

- **Geslaagde pogingen:** het aantal gebruikers dat het opgegeven wachtwoord heeft gebruikt.

- **Algehele slagingspercentage:** een percentage dat wordt berekend door **Succesvolle pogingen** Totaal aantal  /  **beoogde gebruikers.**