---
title: In quarantaine geplaatste berichten zoeken en vrijgeven als beheerder
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: In dit onderwerp wordt beschreven hoe EOP-beheerders (Exchange Online and Exchange Online Protection) in quarantaine geplaatste berichten kunnen vinden, vrijgeven en rapporteren in het Exchange-beheercentrum (EAC).
ms.openlocfilehash: 7c46ff11b8d08c46c3000232c836af8148c58511
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805480"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>In quarantaine geplaatste berichten zoeken en vrijgeven als beheerder

In dit onderwerp wordt beschreven hoe EOP-beheerders (Exchange Online and Exchange Online Protection) in quarantaine geplaatste berichten kunnen vinden, vrijgeven en rapporteren in het Exchange-beheercentrum (EAC). Office 365 stuurt berichten naar quarantaine omdat ze zijn geïdentificeerd als spam of omdat ze overeenkomen met een regel voor e-mailstroom (ook wel een transportregel genoemd).

U het Security & Compliance Center gebruiken in plaats van de EAC om ook een van deze taken uit te voeren. de quarantaineportal in het Exchange-beheercentrum (EAC) is ingesteld om te worden gedecommisioned. Zie [E-mailberichten in quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.

In quarantaine geplaatste berichten worden vermeld op de **quarantainepagina** in EAC. Standaard worden berichten gesorteerd van nieuwste naar oudste in het veld **ONTVANGEN.** De waarden **AFZENDER,** **ONDERWERP**en **VERLOOPT** worden ook voor elk bericht weergegeven. U sorteren op een van deze velden door op hun kopteksten te klikken. Als u een tweede keer op een kolomkop klikt, wordt de sorteervolgorde omgekeerd. Op **de quarantainepagina** worden maximaal 500 berichten weergegeven.

U een lijst met alle in quarantaine geplaatste berichten bekijken of u naar specifieke berichten zoeken door filtercriteria op te geven (filteren kan ook helpen uw resultaatset te verminderen als u meer dan 500 berichten hebt). Nadat u een specifiek in quarantaine geplaatst bericht hebt gezocht en gevonden, u details over het bericht bekijken. U ook:

- Geef het bericht vrij aan een of meer ontvangers en rapporteer het optioneel als een vals-positief (niet-junk) bericht aan het Microsoft Spam Analysis Team, dat het bericht evalueert en analyseert. Afhankelijk van de resultaten van de analyse kunnen de filterregels voor spaminhoud voor de hele service worden aangepast om het bericht door te laten gaan.

- Laat het bericht los en sta alle toekomstige berichten van die afzender toe.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie het item 'Quarantaine' in het onderwerp [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) om te zien welke machtigingen u nodig hebt.

- U meerdere berichten tegelijk vrijgeven of rapporteren op de **quarantainepagina.** U ook een extern Windows PowerShell-script maken om deze taak uit te voeren. Gebruik de cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) om berichten te zoeken en de cmdlet [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) om ze vrij te geven.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>Geavanceerd zoeken gebruiken om in quarantaine geplaatste berichten te filteren en te lokaliseren

In het Exchange-beheercentrum (EAC) u in quarantaine geplaatste items filteren op basis van verschillende voorwaarden met behulp van geavanceerd zoeken. U deze voorwaarden afzonderlijk of in combinatie met elkaar gebruiken. De zoekopdracht biedt een lijst met berichten die voldoen aan al uw filtercriteria.

1. Navigeer in EAC naar **Beveiliging** \> **quarantaine**en klik vervolgens op **Geavanceerd zoeken**.

2. Selecteer in het **zoekvenster Geavanceerd** een combinatie van de volgende voorwaarden. Schakel het selectievakje Gekoppeld in om elke voorwaarde in te schakelen. Jokertekens worden niet ondersteund.

   1. **Bericht-id:** U deze parameter gebruiken om een gerichte zoekopdracht uit te voeren naar een specifiek bericht. Als een specifiek bericht bijvoorbeeld wordt verzonden door of bedoeld is voor een gebruiker in uw organisatie, maar het nooit zijn bestemming bereikt, u naar het bericht zoeken met de functie berichttracering. Zie Een [berichttracering uitvoeren en resultaten weergeven voor](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/run-a-message-trace-and-view-results)meer informatie. Als u ontdekt dat het bericht naar de quarantaine is verzonden, misschien omdat het overeenkwam met een regel of als spam is geïdentificeerd, u dit bericht vervolgens eenvoudig in de quarantaine vinden door de Berichten-ID op te geven. Zorg ervoor dat u de volledige Bericht-ID-tekenreeks opneemt. Dit kan hoekbeugels\<\>() zijn.

   2. **E-mailadres afzender:** geef het e-mailadres op van de persoon die het bericht heeft verzonden.

   3. **E-mailadres van**de ontvanger: geef het e-mailadres op van de beoogde ontvanger van het bericht.

   4. **Onderwerp:** Geef de onderwerpregeltekst van het bericht op.

   5. **Ontvangen**: U selecteren dat het bericht is ontvangen door quarantaine in de afgelopen 24 uur ( **Vandaag**), binnen de afgelopen 48 uur ( **Laatste 2 dagen**), in de afgelopen week ( Laatste 7 **dagen**), of u een aangepast tijdsinterval selecteren waarin het bericht is ontvangen door de quarantaine.

   6. **Verloopt:** U selecteren dat het bericht wordt verwijderd uit quarantaine binnen de komende 24 uur **(Vandaag),** binnen de komende 48 uur ( **Volgende 2 dagen**), binnen de volgende week ( Volgende 7 **dagen**), of u een aangepast tijdsinterval selecteren waarin het bericht zal worden verwijderd uit quarantaine.

      > [!IMPORTANT]
      > Standaard worden berichten in quarantaine geplaatst voor spam gedurende 30 dagen in quarantaine, terwijl in quarantaine geplaatste berichten die overeenkomen met een e-mailstroomregel tot 30 dagen in quarantaine worden gehouden op basis van de bewaarperiode die is ingesteld in uw standaardinhoudsfilterbeleid. Na deze periode verwijdert Office 365 de berichten en kunnen ze niet meer worden opgehaald. De bewaarperiode voor in quarantaine geplaatste berichten die overeenkomen met een e-mailstroomregel, is niet configureerbaar. De bewaartermijn voor spam-quarantaine berichten kan echter worden verlaagd via de instelling **Spam behouden voor (dagen)** in uw inhoudsfilterbeleid. Zie [Beleid voor spamfilters configureren](configure-your-spam-filter-policies.md)voor meer informatie.

   7. **Tekst** U opgeven of u moet zoeken naar in quarantaine geplaatste berichten die zijn geïdentificeerd als **Spam,** of dat u moet zoeken naar berichten die overeenkomen met een regel voor e-mailstroom **(transportregel).**

3. Klik op **OK** om de geavanceerde zoekopdracht uit te voeren.

   > [!NOTE]
   > Als u uw zoekcriteria wilt wissen en alle berichten in de quarantaine wilt weergeven, schakelt u alle selectievakjes in het **geavanceerde zoekvenster** uit en klikt u op **OK.**

Na het zoeken naar berichten worden de resultaten weergegeven die overeenkomen met de opgegeven criteria in de gebruikersinterface. Er kunnen maximaal 500 berichten worden weergegeven in de EAC.

## <a name="view-details-about-a-specific-quarantined-message"></a>Details weergeven over een specifiek in quarantaine geplaatst bericht

Nadat u een specifiek in quarantaine geplaatst bericht op de **quarantainepagina** hebt gevonden, u details hierover bekijken.

1. Selecteer op de **quarantainepagina** een specifiek bericht en er wordt een overzicht weergegeven van de eigenschappen van dat bericht in het detailvenster aan de rechterkant van het scherm.

   De waarden **van de status van het bericht** zijn als volgt:

   - **Tekst:** geeft aan of het bericht is geïdentificeerd als **Spam** of overeenkomt met een regel voor e-mailstroom **(transportregel).**

   - **Verloopt:** de datum waarop het bericht uit de quarantaine wordt verwijderd.

   De waarden **van de details van het bericht** zijn als volgt:

   - **Afzender:** het e-mailadres van de persoon die het bericht heeft verzonden.

   - **Onderwerp:** De onderwerpregeltekst van het bericht.

   - **Ontvangen:** de datum waarop het bericht is ontvangen door de quarantaine.

   - **Grootte**: De grootte van het bericht, in kilobytes (KB) of, als de berichtgrootte groter is dan 999 KBs, in megabytes (MB).

   - **Berichtkop weergeven:** klik op deze koppeling om het dialoogvenster **berichtkoptekst** te openen, waarmee u de tekst van de berichtkopkunt weergeven. U de tekst van de berichtkoptekst ook naar het klembord kopiëren en deze in de [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha)plakken. Eenmaal in het gereedschap Message Header Analyzer klikt u op **Kopteksten analyseren** om informatie over de koptekst op te halen.

    > [!TIP]
    > Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)die door de service zijn ingevoegd voor informatie over specifieke kopteksten voor antispamberichten.

   - **Voorbeeld van e-mailbericht** Klik op deze link om de tekst van het bericht te bekijken.

2. Als u dubbelklikt op een in quarantaine geplaatst bericht, wordt het **venster in quarantaine geplaatste berichten** geopend en worden de volgende gegevens weergegeven:

   - **Vrijgegeven aan:** Een lijst van alle e-mailadressen aan wie het bericht is vrijgegeven, indien van toepassing.

   - **Nog niet vrijgegeven aan**: Een lijst van alle e-mailadressen aan wie het bericht niet is vrijgegeven, indien van toepassing. U op **de koppeling Vrijgeven klikken om** het bericht vrij te geven. Zie de volgende sectie voor meer informatie over het vrijgeven van een bericht.

   - **Bericht-id:** de internetberichten-id (ook wel client-id genoemd) die in de koptekst van het bericht wordt gevonden.

   Klik **op Sluiten** om terug te keren naar het hoofdquarantainedeelvenster.

## <a name="release-messages-from-quarantine"></a>Berichten vrijgeven uit quarantaine

Als u berichten wilt vrijgeven aan ontvangers, zijn uw opties:

- [Een in quarantaine geplaatst bericht vrijgeven en toekomstige berichten van de afzender toestaan](#release-a-quarantined-message-and-allow-future-messages-from-the-sender)

- [Een in quarantaine geplaatst bericht vrijgeven aan specifieke ontvangers zonder het als vals-positief te melden](#release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive)

- [Een of meer in quarantaine geplaatste berichten vrijgeven aan alle ontvangers](#release-one-or-more-quarantined-messages-to-all-recipients)

- [Een of meer in quarantaine geplaatste berichten vrijgeven aan alle ontvangers en valse positieven melden](#release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives)

### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>Een in quarantaine geplaatst bericht vrijgeven en toekomstige berichten van de afzender toestaan

1. Navigeer in EAC naar **Beveiliging** \> **quarantaine.**

2. Klik op een bericht om het te selecteren en klik vervolgens op het pictogram **Bericht vrijgeven** zoals weergegeven in de volgende schermafbeelding.

   ![Toont de quarantainepagina waarop het pictogram voor het releasebericht is gemarkeerd en de releaseopties worden weergegeven](../../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)

   Klik **op Geselecteerde bericht vrijgeven en afzender toestaan** in de vervolgkeuzelijst.

3. Het **releasebericht en het** dialoogvenster Afzender toestaan wordt geopend. Optioneel u ervoor kiezen om het bericht aan Microsoft te rapporteren, vervolgens op vrijgeven te klikken **en toestaan**. Het bericht wordt vrijgegeven aan alle ontvangers waarnaar het is gericht en alle toekomstige berichten van deze afzender zijn toegestaan. Als dit bericht echter in quarantaine is geplaatst vanwege een regel voor e-mailstroom of geblokkeerde afzender, blijft de afzender geblokkeerd voor toekomstige berichten.

### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>Een in quarantaine geplaatst bericht vrijgeven aan specifieke ontvangers zonder het als vals-positief te melden

1. Navigeer in EAC naar **Beveiliging** \> **quarantaine.**

2. Selecteer een bericht, klik op het pictogram **Bericht vrijgeven** en klik vervolgens in de vervolgkeuzelijst op Bericht vrijgeven aan **specifieke ontvangers.**

3. Selecteer in het dialoogvenster **Releasebericht** een van de volgende opties:

   - **Bericht vrijgeven aan alle ontvangers** Wanneer u deze optie selecteert, moet u er rekening mee houden dat een bericht niet meer dan één keer aan dezelfde ontvanger kan worden vrijgegeven. Als een ontvanger het bericht eerder heeft ontvangen, wordt het bericht niet opnieuw vrijgegeven aan die ontvanger.

   - **Bericht vrijgeven aan opgegeven ontvangers** Selecteer de ontvanger(s) aan wie het bericht kan worden vrijgegeven. Omdat een bericht slechts één keer kan worden vrijgegeven aan elke ontvanger, worden alleen ontvangers aan wie het kan worden vrijgegeven in deze lijst weergegeven. Multi-selectie wordt ondersteund. Nadat u de selecties van de ontvanger hebt gemaakt, klikt u op **Toevoegen**.

4. Klik **op release**.

Als u **op** ![](../../media/ITPro-EAC-RefreshIcon.gif) Pictogram Vernieuwen vernieuwen klikt om uw gegevens te vernieuwen en dubbelklikt u op het bericht, moet u zien dat het is vrijgegeven aan de beoogde ontvangers.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>Een of meer in quarantaine geplaatste berichten vrijgeven aan alle ontvangers

1. Navigeer in EAC naar **Beveiliging** \> **quarantaine.**

2. Klik op een bericht om het te selecteren of gebruik de shift-toets om meerdere berichten te selecteren. Klik vervolgens op het pictogram **Bericht vrijgeven.**

3. Klik in de vervolgkeuzelijst **op Geselecteerde berichten vrijgeven voor ALLE geadresseerden.**

4. Het waarschuwingsdialoogvenster wordt geopend. Lees de waarschuwing en selecteer **Ja** als u verder wilt gaan. Wanneer u deze optie selecteert, moet u er rekening mee houden dat een bericht niet meer dan één keer aan dezelfde ontvanger kan worden vrijgegeven. Als een ontvanger het bericht eerder heeft ontvangen, wordt het bericht niet opnieuw vrijgegeven aan die ontvanger.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>Een of meer in quarantaine geplaatste berichten vrijgeven aan alle ontvangers en valse positieven melden

1. Navigeer in EAC naar **Beveiliging** \> **quarantaine.**

2. Klik op een bericht om het te selecteren of gebruik de shift-toets om meerdere berichten te selecteren. Klik vervolgens op het pictogram **Bericht vrijgeven.**

3. Klik **op Geselecteerde berichten vrijgeven(en) vrijgeven en meld als fout-positief** in de vervolgkeuzelijst.

4. Het waarschuwingsdialoogvenster wordt geopend. Lees de waarschuwing en selecteer **Ja** als u verder wilt gaan. Wanneer u deze optie selecteert, moet u er rekening mee houden dat een bericht niet meer dan één keer aan dezelfde ontvanger kan worden vrijgegeven. Als een ontvanger het bericht eerder heeft ontvangen, wordt het bericht niet opnieuw vrijgegeven aan die ontvanger.

   Wanneer u deze optie kiest, wordt het bericht vrijgegeven aan alle ontvangers die het bericht nog niet hebben ontvangen. Als het een bericht in quarantaine wordt geplaatst, wordt het ook gerapporteerd aan het Microsoft Spam Analysis Team, dat het bericht evalueert en analyseert. Afhankelijk van de resultaten van de analyse kunnen de filterregels voor spaminhoud voor de hele service worden aangepast om het bericht door te laten gaan.

> [!TIP]
> Help ervoor te zorgen dat een bericht niet is gemarkeerd als spam door de stappen te volgen in [Hoe u ervoor wilt zorgen dat een bericht niet is gemarkeerd als spam.](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)

Als u op **het**![pictogram Vernieuwen klikken](../../media/ITPro-EAC-RefreshIcon.gif) om uw gegevens te vernieuwen en dubbelklikt u op het bericht, moet u zien dat het is vrijgegeven aan de beoogde ontvangers.

## <a name="for-more-information"></a>Voor meer informatie

[Veelgestelde vragen over quarantaine](quarantine-faq.md)
