---
title: Schadelijke e-mailberichten in Office 365 onderzoeken, kwaadaardige e-mail zoeken en onderzoeken
keywords: TIMailData-inline, beveiliging incident, incident, ATP PowerShell, e-mail malware, gebruikers met risico, gebruikers die in gebruik zijn, e-mail phishing, e-mailberichten, e-mailbericht koppen, gelezen e-mail koppen, speciale acties
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/09/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Meer informatie over het gebruik van de functie voor het onderzoek van bedreigingen en de antwoord mogelijkheden om kwaadaardige e-mail te vinden en te onderzoeken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f16c3aa7ba98467c52fb25e0597f346a810003
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949262"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Schadelijke e-mailberichten onderzoeken die zijn uitgebracht in Office 365

Met [Bebeschermings beveiliging van Office 365](office-365-atp.md) kunt u activiteiten onderzoeken waarmee mensen in uw organisatie worden bedreigd en om actie te ondernemen om uw organisatie te beveiligen. Als u bijvoorbeeld bij het beveiligingsteam van uw organisatie bent, kunt u verdachte e-mailberichten zoeken en onderzoeken die zijn ontvangen. U kunt dit doen met behulp van de [bedreigings Verkenner (of realtime detectie)](threat-explorer.md).

> [!NOTE]
> Ga naar het artikel herstel [hier](remediate-malicious-email-delivered-office-365.md).

## <a name="before-you-begin"></a>Voordat u begint

Controleer of aan de volgende vereisten wordt voldaan:

- Uw organisatie heeft [Office 365 Advanced Threat Protection](office-365-atp.md) en [licenties zijn toegewezen aan gebruikers](../../admin/manage/assign-licenses-to-users.md).

- [controlelogboekregistratie](../../compliance/turn-audit-log-search-on-or-off.md) is ingeschakeld voor uw organisatie.

- Uw organisatie bevat beleidsregels die zijn gedefinieerd voor anti-spam, anti-malware, anti phishing en dergelijke. Zie [beveiliging tegen bedreigingen in Office 365](protect-against-threats.md).

- U bent een globale beheerder of u hebt de rol beveiligingsbeheerder of zoeken en verwijderen toegewezen in het beveiligings &amp; centrum. Zie [machtigingen in het beveiligings &amp; conformiteitscentrum](permissions-in-the-security-and-compliance-center.md). Voor sommige acties moet aan u ook een nieuwe preview-rol zijn toegewezen.

### <a name="preview-role-permissions"></a>Machtigingen voor voorbeeld van rollen

Als u bepaalde acties wilt uitvoeren, zoals het weergeven van berichtkoppen of het downloaden van e-mailberichten, moet u een nieuwe rol genaamd *voorbeeld* toevoegen aan een andere bijbehorende rollen groep. In de volgende tabel worden vereiste rollen en machtigingen duidelijker.

****

|Activiteit|Rollen groep|Is de functie voorbeeld nodig?|
|---|---|---|
|Het gebruik van bedreigings Verkenner (en real-time detecties) om bedreigingen te analyseren |Globale beheerder <br> Beveiligingsbeheerder <br> Beveiligings lezer|Nee|
|De weergave van bedreigings Verkenner (en realtime-detectie) gebruiken om kopteksten voor e-mailberichten weer te geven en voorbeelden van e-mailberichten in quarantaine te downloaden|Globale beheerder <br> Beveiligingsbeheerder <br>Beveiligings lezer|Nee|
|Met behulp van de bedreigings Verkenner kopteksten en e-mailberichten die zijn bezorgd bij postvakken weergeven|Globale beheerder <br>Beveiligingsbeheerder <br> Beveiligings lezer <br> Voorbeeld|Ja|
|

> [!NOTE]
> *Voorbeeld* is een rol en geen rollen groep. de rol van voorbeeld moet worden toegevoegd aan een bestaande rollen groep voor Office 365. De rol van de globale beheerder wordt het Microsoft 365-Beheercentrum toegewezen [https://admin.microsoft.com](https://admin.microsoft.com) , en de rollen Beveiligingsbeheerder en beveiligings lezer worden toegewezen in het beveiligings & nalevings centrum ( [https://protection.office.com](https://protection.office.com) ). Als u meer wilt weten over rollen en machtigingen, raadpleegt u [machtigingen in de sectie beveiliging & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

## <a name="find-suspicious-email-that-was-delivered"></a>Verdachte e-mail vinden die is bezorgd

Bedreigings Verkenner is een krachtig rapport waarmee u kunt zoeken naar meerdere doeleinden, zoals berichten zoeken en verwijderen, het IP-adres van een kwaadwillende e-mail verzender identificeren of een incident voor verder onderzoek starten. In de volgende procedure wordt beschreven hoe u met Verkenner schadelijke e-mail van de postvakken van de ontvanger kunt vinden en verwijderen.

> [!NOTE]
> Standaardzoekopdrachten in Explorer bevatten momenteel geen zapped-items.  Dit geldt voor alle weergaven, bijvoorbeeld malware of phishing. Als u zapped-items wilt opnemen, moet u een actie voor de leverings actie toevoegen zodat de waarde ' verwijderd door ZAP ' wordt vermeld. Als u alle opties opneemt, ziet u alle resultaten van de bezorgings actie, waaronder zapped-items.

1. **Ga naar Threat Explorer**: Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw werk-of schoolaccount voor Office 365. U gaat nu naar het beveiligings &amp; conformiteitscentrum.

2. Kies in de navigatiebalk aan de linkerkant de optie **Threat Management** \> **Explorer**.

    ![Explorer met de velden bezorgings actie en locatie van aflever.](../../media/ThreatExFields.PNG)

    U ziet mogelijk de kolom nieuwe **speciale acties** . Deze functie is bedoeld om beheerders een e-mailbericht te sturen. De kolom **speciale acties** kan worden geopend op dezelfde plaats als de bezorgings **actie** en de **bezorgingslocatie**. Speciale acties kunnen worden bijgewerkt aan het einde van de e-mail tijdlijn van de bedreiging van de bedreiging, een nieuwe functie waarmee u de jacht-ervaring beter kunt benutten.

3. **Weergaven in de bedreigings Verkenner**: Kies in het menu **weergave** de optie **alle e-mail**.

    ![Afbeelding van het menu Beeld van bedreiging, en e-malware, phishing, inzendingen en alle e-mail opties, ook inhoud-malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    De weergave van de *malware* is op dit moment de standaardweergave en de e-mailberichten worden vastgelegd waarbij een schadelijke schadelijke bedreiging wordt gedetecteerd. De weergave *phishing* werkt op dezelfde manier, voor phishing.

    De weergave *e-mail* bevat echter elk e-mailbericht dat door de organisatie is ontvangen, of bedreigingen zijn gedetecteerd. Zoals u kunt zien, is dit een groot aantal gegevens, wat de voorwaarde is: in deze weergave wordt een tijdelijke aanduiding weergegeven om aan te geven dat er een filter wordt toegepast. (Deze weergave is alleen beschikbaar voor ATP P2-klanten.)

    De weergave *ingediende items* toont alle e-mailberichten die zijn verzonden door een beheerder of gebruiker die bij Microsoft werd gerapporteerd.

4. **Zoeken en filteren in de bedreigings Verkenner**: filters worden boven aan de pagina weergegeven in de zoekbalk om beheerders in hun onderzoek te helpen. U kunt op elk gewenst moment meerdere filters toepassen, en meerdere door lijstscheidingstekens gescheiden waarden toevoegen aan een filter om de zoekopdracht te verfijnen. Belang

    - Filters doen nauwkeurig overeen met de meeste filtervoorwaarden.
    - Het onderwerp-filter gebruikt een contain-query.
    - URL-filters werken met of zonder protocollen (bijv. https).
    - URL-domein, URL-pad en URL-domein en-padcomponenten vereisen geen protocol om te filteren.
    - U moet telkens wanneer u de filterwaarden wijzigt, op het pictogram Vernieuwen klikken om relevante resultaten te bereiken.

5. **Geavanceerde filters**: met deze filters kunt u complexe query's maken en de gegevensset filteren. Met klikken op *Geavanceerde filters* wordt een flyout geopend met opties.

   Geavanceerde filtering is een fantastische aanvulling op de mogelijkheden van zoeken. Er is een Booleaanse waarde **niet** filter geïntroduceerd voor de *ontvanger*, het domein van de *afzender* en het domein van de *afzender* , zodat beheerders door geen waarden kunnen onderzoeken. Deze optie wordt weergegeven onder selectie parameter *bevat geen van*. Laat beheerders **geen** waarschuwingen, standaardantwoord boxen van hun onderzoek, en kan handig zijn voor gevallen waarin beheerders zoeken naar een specifiek onderwerp (subject = "aandacht") waarbij de ontvanger kan worden ingesteld op *geen van defaultMail \@ contoso.com*. Dit is een exacte waarde waarnaar wordt gezocht.

   ![De geadresseerden-' bevatten geen van ' Geavanceerde filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Door uren te filteren* wordt het beveiligingsteam van uw organisatie sneller ingezoomd. De kortste toegestane tijdsduur is 30 minuten. Als u de verdachte actie kunt specificeren op basis van tijdskader (bijvoorbeeld 3 uur geleden gebeurd), wordt de context beperkt en wordt het probleem door u gespeld.

   ![De optie filteren op uren om de hoeveelheid gegevensbeveiliging te verfijnen, en waarvan de kortste dag 30 minuten duurt.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Velden in de bedreigings Verkenner: met**bedreigings Verkenner worden veel meer beveiligingsgegevens voor beveiliging weergeven, zoals de *bezorgings actie*, *bezorgingslocatie*, *speciale actie*, *richting*, *overschrijvingen*en de bedreiging van de *URL*. Ook kan het beveiligingsteam van uw organisatie een betere zekerheid krijgen.

    De *bezorgings actie* is de actie die op een e-mail is uitgevoerd vanwege bestaande beleidsregels of detecties. Dit zijn de mogelijke acties waarmee een e-mail kan worden verzonden:

    - **Bezorgd** -e-mail is bezorgd in het postvak in of de map van een gebruiker en de gebruiker kan deze rechtstreeks openen.
    - **Ongewenst** (afgeleverd aan ongewenste e-mail) – e-mail is verzonden naar de map Ongewenste e-mail van de gebruiker of een map die is verwijderd, en de gebruiker heeft toegang tot e-mailberichten in hun ongewenste map.
    - **Geblokkeerde** e-mail: alle e-mailberichten die zijn gequarantined, dat niet is gelukt of zijn verwijderd. (Dit is helemaal niet toegankelijk voor de gebruiker).
    - **Vervangen** : alle e-mailberichten waarin schadelijke bijlagen worden vervangen door txt-bestanden die aangeven dat de bijlage schadelijk is

    **Bezorgingslocatie**: het filter bezorgingslocatie is beschikbaar om beheerders te helpen begrijpen waar kwaadaardige e-mailberichten zijn beëindigd en welke acties hieraan zijn ondergebracht. De gegevens die worden geretourneerd, kunnen worden geëxporteerd naar het werkblad. Mogelijke bezorgingslocaties zijn:

    - **Postvak in of map** : het e-mailbericht bevindt zich in het postvak in of een specifieke map, volgens uw e-mail regels.
    - **On-premises of extern** : het postvak bestaat niet in de Cloud, maar is on-premises.
    - **Map Ongewenste** E-mail: de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.
    - **Map Verwijderde items** : de e-mail bevindt zich in de map Verwijderde items van een gebruiker.
    - **Quarantine** : de e-mail in quarantaine, en niet in het postvak van een gebruiker.
    - **Mislukt** : het e-mailbericht kon het postvak niet bereiken.
    - **Neergezet** -de e-mail is ergens in de e-mail stroom verdwenen.

    **Richting**: met deze optie kan uw bedrijfsactiviteiten team filteren op de ' direction ' waarnaar een e-mailbericht wordt verzonden. Waarden in de richting zijn *Inkomend*, *uitgaand*en *binnenste organisatie* (corresponderend met e-mail van derden, die wordt verstuurd vanuit uw organisatie of intern verzonden naar uw organisatie). Deze informatie biedt bescherming van beveiligingsactiviteiten teams om spoofing en imitatie te voorkomen, omdat de waarde van de richting niet klopt (ex. *Inkomend*), en het domein van de afzender (die *wordt weergegeven* als een intern domein), blijkt duidelijk! De waarde richting is gescheiden en kan variëren van de bericht tracering. Resultaten kunnen worden geëxporteerd naar spreadsheet.

    **Overschrijvingen**: dit filter bevat informatie die wordt weergegeven op het tabblad Details van het e-mailbericht en wordt gebruikt om het weergeven van de organisatie of het gebruikersbeleid, zodat e-mailberichten kunnen worden toegestaan en *geblokkeerd.* Het belangrijkste voor dit filter is dat het beveiligingsteam van uw organisatie het beveiligingsteam van uw organisatie kan bekijken hoeveel verdachte e-mailberichten zijn bezorgd vanwege de configuratie. Zo nodig kunnen ze de verkoopkans wijzigen en blokkeren. Dit filter kan worden geëxporteerd naar spreadsheet.

    ****

    |De bedreiging negeren|Wat ze betekenen|
    |---|---|
    |Toegestaan door het beleid voor de organisatie|E-mail is in het postvak toegestaan volgens de door u ingestelde organisatiebeleid.|
    |Geblokkeerd door organisatiebeleid|E-mail is geblokkeerd voor levering aan het postvak, zoals door het organisatiebeleid werd doorgestuurd.|
    |Bestandsextensie geblokkeerd door organisatiebeleid|Het bestand is geblokkeerd voor levering aan het postvak, zoals door het organisatiebeleid werd doorgestuurd.|
    |Toegestaan door gebruikersbeleid|E-mail werd toegestaan in het postvak, zoals door het gebruikersbeleid is doorgestuurd.|
    |Geblokkeerd door gebruikersbeleid|E-mail is geblokkeerd voor levering aan het postvak, zoals door het gebruikersbeleid werd doorgestuurd.|
    |

    **URL Threat**: het veld URL Threat is opgenomen op het tabblad *Details* van een e-mailbericht om de bedreiging aan te geven die wordt weergegeven door een URL. Bedreigingen die door een URL worden gepresenteerd, kunnen *malware*, *phishing*of *spam*bevatten en een URL zonder *bedreiging* zeg *geen* in de sectie bedreigingen.

7. **Weergave van e-mail tijdlijn**: het team van uw beveiligingsactiviteiten moet mogelijk uitgebreide informatie over de e-mail bekijken om verder te kunnen onderzoeken. Met de e-mail tijdlijn kunnen beheerdersacties weergeven die zijn gemaakt voor een e-mailbericht van aflevering tot na levering. Als u een e-mail tijdlijn wilt weergeven, klikt u op het onderwerp van een e-mailbericht en vervolgens op e-mail tijdlijn. (Het wordt weergegeven onder andere koppen op het deelvenster, zoals Summary or details). U kunt deze resultaten exporteren naar een werkblad.

    De e-mail tijdlijn wordt geopend in een tabel waarin alle gebeurtenissen voor de bezorging van de e-mail en de bezorging van de e-mail worden weergegeven. Als het e-mailbericht geen verdere acties bevat, ziet u één gebeurtenis voor de oorspronkelijke aflevering met een resultaat, zoals *geblokkeerd*, met een verdict zoals *phishing*. Beheerders kunnen de volledige e-mail tijdlijn exporteren, inclusief alle details op het tabblad en e-mailadres (zoals het onderwerp, de afzender, de geadresseerde, het netwerk en de bericht-ID). De e-mail tijdlijn snijdt voor willekeurige berichten omdat er minder tijd is besteed aan het controleren van verschillende locaties om te zien welke gebeurtenissen zijn aangebracht sinds de e-mail is ontvangen. Wanneer meerdere gebeurtenissen plaatsvinden aan of sluiten op een e-mail, worden deze gebeurtenissen weergegeven in een tijdlijnweergave.

8. **Preview/Download**: met de bedreigings Verkenner krijgt u uw beveiligingsactiviteiten team de details die ze nodig hebben om verdachte e-mail te onderzoeken. Het team van uw beveiligingsactiviteiten kan een van de volgende handelingen uitvoeren:

    - [Controleer de bezorgings actie en de locatie](#check-the-delivery-action-and-location).

    - [De tijdlijn van uw E-mail bekijken](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Controleer de bezorgings actie en de locatie

In de fase van de [bedreiging](threat-explorer.md), de realtime-bezorgings **status** en de bezorgingslocatie, hebt u nu de kolommen **leverings actie** en **bezorgingslocatie** . Dit levert een uitgebreide foto van de plaats van uw e-mailberichten. Onderdeel van het doel van deze wijziging is het maken van onderzoek eenvoudiger voor beveiligings werkactiviteiten teams, maar het resultaat van de e-mail is in één oogopslag bekend.

De bezorgings status is nu uitgebroken in twee kolommen:

- **Bezorgings actie** : wat is de status van dit e-mailbericht?

- **Bezorgingslocatie** : waar werd dit e-mailbericht rondgestuurd als resultaat?

De bezorgings actie is de actie die op een e-mail is uitgevoerd vanwege bestaande beleidsregels of detecties. Dit zijn de mogelijke acties waarmee een e-mail kan worden verzonden:

- **Bezorgd** -e-mail is bezorgd in het postvak in of de map van een gebruiker en de gebruiker kan deze rechtstreeks openen.

- **Ongewenst** – e-mail is verzonden naar de map Ongewenste e-mail van de gebruiker of de map die is verwijderd, en de gebruiker heeft toegang tot e-mailberichten in zijn of haar map.

- **Geblokkeerde** e-mail: alle e-mailberichten die zijn gequarantined, dat niet is gelukt of zijn verwijderd. (Dit is helemaal niet toegankelijk voor de gebruiker).

- **Vervangen** : alle e-mailberichten waarin schadelijke bijlagen worden vervangen door txt-bestanden die aangeven dat de bijlage schadelijk is.

Locatie van levering toont de resultaten van beleidsregels en detecties die na levering worden uitgevoerd. Het is gekoppeld aan een bezorgings actie. Dit veld is toegevoegd om inzicht te krijgen in de actie die optreedt wanneer er een probleem met de e-mail is gevonden. Dit zijn de mogelijke waarden van de lever locatie:

- **Postvak in of map** : het e-mailbericht bevindt zich in het postvak in of de map (volgens uw e-mail regels).

- **On-premises of extern** : het postvak bestaat niet in de Cloud, maar is on-premises.

- **Map Ongewenste e-mail** : het e-mailbericht bevindt zich in de map Ongewenste e-mail van een gebruiker.

- **Map Verwijderde items** : de e-mail bevindt zich in de map Verwijderde items van een gebruiker.

- **Quarantine** : de e-mail in quarantaine, en niet in het postvak van een gebruiker.

- **Mislukt** : het e-mailbericht kon het postvak niet bereiken.

- **Neergezet** : de e-mail wordt ergens in de e-mail stroom neergezet.

### <a name="view-the-timeline-of-your-email"></a>De tijdlijn van uw e-mailbericht weergeven

**E-mail tijdlijn** is een veld in de Threat Explorer waarmee u de jacht eenvoudiger kunt maken voor uw beveiligingsactiviteiten. Wanneer meerdere gebeurtenissen plaatsvinden op of dicht bij een e-mailbericht, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. Sommige gebeurtenissen die plaatsvinden na de bezorging van e-mail, worden vastgelegd in de kolom **speciale acties** . Wanneer u de gegevens van de tijdlijn van een e-mailbericht combineert met speciale acties die na de levering zijn uitgevoerd, levert beheerders inzicht in beleidsregels en bedreigings afhandeling op, bijvoorbeeld de manier waarop de e-mail is gerouteerd, en in sommige gevallen, wat de laatste beoordeling was.

> [!IMPORTANT]
> Ga naar [een sectie voor herstel.](remediate-malicious-email-delivered-office-365.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Kwaadwillende e-mailberichten herstellen die worden bezorgd in Office 365](remediate-malicious-email-delivered-office-365.md)

[Office 365 Advanced Threat Protection](office-365-ti.md)

[Beveiliging tegen bedreigingen in Office 365](protect-against-threats.md)

[Rapporten weergeven voor Office 365 Advanced Threat Protection](view-reports-for-atp.md)
