---
title: Schadelijke e-mail onderzoeken die is bezorgd in Office 365, schadelijke e-mail zoeken en onderzoeken
keywords: TIMailData-Inline, Security Incident, Incident, ATP PowerShell, email malware, compromised users, email phish, email malware, read email headers, read headers, open email headers,special actions
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Informatie over het gebruik van bedreigingsonderzoek en reactiemogelijkheden om schadelijke e-mail te zoeken en te onderzoeken.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b36e16f5351ab30ac8150fbc3e87feb9ca4a6453
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286631"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Schadelijke e-mail onderzoeken die is bezorgd in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**

- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Met Microsoft Defender voor Office 365](office-365-atp.md) kunt u activiteiten onderzoeken die personen in uw organisatie in gevaar brengen en acties ondernemen om uw organisatie te beschermen. Als u bijvoorbeeld deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u verdachte e-mailberichten zoeken en onderzoeken die zijn bezorgd. U kunt dit doen met behulp van Bedreigingsverkenner [(of realtime detecties).](threat-explorer.md)

> [!NOTE]
> Ga naar het artikel over herstel [hier.](remediate-malicious-email-delivered-office-365.md)

## <a name="before-you-begin"></a>Voordat u begint

Zorg ervoor dat aan de volgende vereisten wordt voldaan:

- Uw organisatie heeft [Microsoft Defender voor Office 365 en](office-365-atp.md) licenties zijn toegewezen aan [gebruikers.](../../admin/manage/assign-licenses-to-users.md)

- [auditlogregistratie](../../compliance/turn-audit-log-search-on-or-off.md) is ingeschakeld voor uw organisatie.

- Uw organisatie heeft beleid gedefinieerd voor antispam, anti-malware, anti-phishing, en meer. Zie [Beveiligen tegen bedreigingen in Office 365.](protect-against-threats.md)

- U bent een globale beheerder of u hebt de beveiligingsbeheerder of de rol Zoeken en & toegewezen. Zie [Machtigingen in het beveiligings- & compliancecentrum.](permissions-in-the-security-and-compliance-center.md) Voor sommige acties moet ook een nieuwe Preview-rol zijn toegewezen.

### <a name="preview-role-permissions"></a>Voorbeeld van rolmachtigingen bekijken

Als u bepaalde acties wilt uitvoeren, zoals het weergeven van berichtkoppen of het downloaden van de inhoud van e-mailberichten, moet u een nieuwe rol met de naam *Voorbeeld* toevoegen aan een andere geschikte rollengroep. In de volgende tabel worden vereiste rollen en machtigingen toegelicht.

****

|Activiteit|Rollengroep|Voorbeeldrol nodig?|
|---|---|---|
|Bedreigingsverkenner (en realtime detecties) gebruiken om bedreigingen te analyseren |Globale beheerder <p> Beveiligingsbeheerder <p> Beveiligingslezer|Nee|
|Bedreigingsverkenner (en realtime detecties) gebruiken om kopteksten voor e-mailberichten weer te geven en om in quarantaine geplaatste e-mailberichten te bekijken en te downloaden|Globale beheerder <p> Beveiligingsbeheerder <p> Beveiligingslezer|Nee|
|Bedreigingsverkenner gebruiken om koppen te bekijken, een voorbeeld van e-mail te bekijken (alleen op de pagina van de e-mailentiteit) en e-mailberichten te downloaden die in postvakken zijn bezorgd|Globale beheerder <p> Beveiligingsbeheerder <p> Beveiligingslezer <p> Voorbeeld|Ja|
|

> [!NOTE]
> *Preview* is een rol en niet een rollengroep; De Preview-rol moet worden toegevoegd aan een bestaande rollengroep voor Office 365 (op [https://protection.office.com](https://protection.office.com) ). Ga naar **Machtigingen** en bewerk vervolgens een bestaande rollengroep of voeg een nieuwe rollengroep toe aan de **preview-rol.**
> De rol globale beheerder wordt toegewezen aan het Microsoft 365-beheercentrum ( ) en de rollen voor beveiligingsbeheerder en beveiligingslezer worden toegewezen in het <https://admin.microsoft.com> beveiligings- & Compliancecentrum ( <https://protection.office.com> ). Zie Machtigingen in het beveiligings- en compliancecentrum voor meer informatie over rollen [& machtigingen.](permissions-in-the-security-and-compliance-center.md)

We begrijpen dat het bekijken en downloaden van e-mail gevoelige activiteiten zijn en daarom is controle ingeschakeld voor deze activiteiten. Wanneer een beheerder deze activiteiten voor e-mailberichten uitvoert, worden er controlelogboeken voor hetzelfde gegenereerd en kunt u deze bekijken in het Office 365-beveiligings- & Compliancecentrum ( [https://protection.office.com](https://protection.office.com) ). Ga naar **Zoeken in**  >  **het auditlogboek** en filter op de naam van de beheerder in de sectie Zoeken. De gefilterde resultaten tonen **adminMailAccess van de activiteit.** Selecteer een rij om details weer te geven in **de sectie Meer informatie** over bekeken of gedownloade e-mailberichten.

## <a name="find-suspicious-email-that-was-delivered"></a>Verdachte e-mailberichten zoeken die zijn bezorgd

Bedreigingsverkenner is een krachtig rapport dat meerdere doeleinden kan dienen, zoals het zoeken en verwijderen van berichten, het IDENTIFICEREN van het IP-adres van een kwaadwillende afzender van e-mail of het starten van een incident voor nader onderzoek. De volgende procedure is gericht op het zoeken en verwijderen van schadelijke e-mail in de postvakken van de geadresseerde.

> [!NOTE]
> Standaard zoekopdrachten in Verkenner bevatten momenteel geen gezapeerde items.  Dit geldt voor alle weergaven, bijvoorbeeld malware- of phish-weergaven. Als u zapped-items wilt opnemen, moet u een set **leveringsactie** toevoegen die **is verwijderd door ZAP.** Als u alle opties opneemt, ziet u alle resultaten van de bezorgingsactie, inclusief Zapped-items.

1. **Ga naar Bedreigingsverkenner:** ga <https://protection.office.com> naar en meld u aan met uw werk- of schoolaccount voor Office 365. U gaat nu naar het & compliancecentrum.

2. Kies Bedreigingsbeheerverkenner in het **linkernavigatievenster** snel \> **starten.**

    ![Verkenner met de velden Bezorgingsactie en Bezorgingslocatie.](../../media/ThreatExFields.PNG)

    Mogelijk ziet u de nieuwe **kolom Speciale** acties. Deze functie is bedoeld om beheerders te laten weten wat het resultaat is van het verwerken van een e-mailbericht. De **kolom Speciale** acties kan worden gebruikt op dezelfde plaats als de bezorgingsactie en de  **bezorgingslocatie.** Speciale acties worden mogelijk bijgewerkt aan het einde van de e-mailtijdlijn van Bedreigingsverkenner. Dit is een nieuwe functie die is gericht op het verbeteren van de zoekervaring voor beheerders.

3. **Weergaven in Bedreigingsverkenner:** kies in **het** menu Beeld de **optie Alle e-mailberichten.**

    ![Het menu Beeld van bedreigingsverkenner en e-mail - Malware, Phish, Inzending en Alle e-mailopties, ook Inhoud - Malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    De *weergave Malware* is momenteel de standaardweergave en legt e-mailberichten vast waar een malware bedreiging wordt gedetecteerd. De *weergave Phish* werkt op dezelfde manier, voor Phish.

    In alle *e-mailweergaven* wordt echter elke e-mail vermeld die door de organisatie is ontvangen, ongeacht of er bedreigingen zijn gedetecteerd. U kunt zich voorstellen dat dit een groot aantal gegevens is en daarom wordt in deze weergave een tijdelijke aanduiding gebruikt waarin u wordt gevraagd om een filter toe te paste. (Deze weergave is alleen beschikbaar voor Defender voor klanten met Office 365 P2.)

    *De weergave Inzendingen* toont alle e-mailberichten die zijn verzonden door een beheerder of gebruiker en die zijn gerapporteerd bij Microsoft.

4. **Zoeken en filteren in Bedreigingsverkenner:** filters worden boven aan de pagina in de zoekbalk weergegeven om beheerders in hun onderzoek te helpen. U ziet dat meerdere filters tegelijkertijd kunnen worden toegepast en dat meerdere door komma's gescheiden waarden aan een filter kunnen worden toegevoegd om de zoekopdracht te beperken. Denk eraan:

    - Filters komen precies overeen voor de meeste filtervoorwaarden.
    - Het onderwerpfilter maakt gebruik van een CONTAINS-query.
    - URL-filters werken met of zonder protocollen (bijvoorbeeld. https).
    - Voor URL-domein, URL-pad en URL-domein- en padfilters is geen protocol vereist om te filteren.
    - Telkens wanneer u de filterwaarden wijzigt, moet u op het pictogram Vernieuwen klikken om relevante resultaten te krijgen.

5. **Geavanceerde filters:** met deze filters kunt u complexe query's maken en uw gegevensset filteren. Als u op Geavanceerde *filters klikt,* wordt een flyout met opties geopend.

   Geavanceerd filteren is een goede aanvulling op de zoekmogelijkheden. Er is een boolean **filter NIET** geïntroduceerd in het domein *Recipient,* *Sender* en *Sender* om beheerders in staat te stellen onderzoek te doen door waarden uit te sluiten. Deze optie wordt weergegeven onder de *selectieparameter Bevat geen van.* Met **NOT** kunnen beheerders waarschuwingspostvakken uitsluiten, postvakken met standaardantwoorden uitsluiten van hun onderzoek en dit is handig in gevallen waarin beheerders zoeken naar een specifiek onderwerp (onderwerp='Aandacht'), waarbij de ontvanger kan worden ingesteld op geen *van de \@ defaultMail-contoso.com.* Dit is een exacte waardezoekactie.

   ![De geadresseerden: 'Bevat geen' geavanceerd filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Door te filteren op uren* kan het beveiligingsteam van uw organisatie snel inzoomen. De kortste toegestane tijdsduur is 30 minuten. Als u de verdachte actie kunt beperken op tijd (bijvoorbeeld het probleem is 3 uur geleden gebeurd), wordt de context beperkt en kan het probleem worden gelokaliseerd.

   ![De optie filteren per uur om de hoeveelheid gegevensbeveiligingsteams te beperken die moet worden verwerkt en waarvan de kortste duur 30 minuten is.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Velden in Bedreigingsverkenner**: Bedreigingsverkenner bevat veel meer beveiligingsgerelateerde e-mailgegevens, zoals bezorgingsactie, bezorgingslocatie, speciale *actie,* *directioneelheid,* overschrijven en *URL-bedreiging.* Hiermee kan het beveiligingsteam van uw organisatie ook nader onderzoek doen.

    *Bezorgingsactie* is de actie die wordt ondernomen op een e-mail vanwege bestaand beleid of detecties. Dit zijn de mogelijke acties die een e-mail kan uitvoeren:

    - **Bezorgd:** e-mail is bezorgd in het Postvak IN of de map van een gebruiker en de gebruiker kan er rechtstreeks toegang toe krijgen.
    - **Ongewenste e-mail** (bezorgd in ongewenste e-mail): e-mail is verzonden naar de map Ongewenste e-mail of verwijderde map van de gebruiker en de gebruiker heeft toegang tot e-mailberichten in de map Ongewenste e-mail of Verwijderd.
    - **Geblokkeerd:** alle e-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of die zijn geplaatst. (Dit is volledig ontoegankelijk voor de gebruiker.)
    - **Vervangen:** alle e-mailberichten waarin schadelijke bijlagen worden vervangen door TXT-bestanden waarin wordt staat dat de bijlage schadelijk is

    **Bezorgingslocatie:** het filter voor de bezorgingslocatie is beschikbaar om beheerders te laten weten waar verdachte schadelijke e-mail is terecht gekomen en welke acties er zijn ondernomen. De resulterende gegevens kunnen worden geëxporteerd naar een spreadsheet. Mogelijke leveringslocaties zijn:

    - **Postvak IN of map:** de e-mail staat in het Postvak IN of in een specifieke map, volgens uw e-mailregels.
    - **On-premises of extern:** het postvak bestaat niet in de cloud, maar is on-premises.
    - **Map Ongewenste** e-mail: de e-mail staat in de map Ongewenste e-mail van een gebruiker.
    - **Map Verwijderde items:** de e-mail staat in de map Verwijderde items van een gebruiker.
    - **Quarantaine:** de e-mail in quarantaine en niet in het postvak van een gebruiker.
    - **Mislukt:** het e-mailbericht kan niet in het postvak worden bereikt.
    - **In plaats:** de e-mail is ergens in de e-mailstroom verloren gegaan.

    **Directionality:** met deze optie kan uw team voor beveiligingsbewerkingen filteren op de 'richting' waar een e-mailbericht vandaan komt of gaat. Directionaliteitswaarden zijn *Inkomende,* *Uitgaande* en Rente-organisatie (wat overeenkomt met *e-mail* die van buiten naar uw organisatie binnenkomt, die u uit uw organisatie stuurt of die intern naar uw organisatie wordt verzonden). Met deze informatie kunnen teams met beveiligingsbewerkingen spoofing en imitatie herkennen, omdat de waarde van Directionality niet overeen komt (bijvoorbeeld. *Inkomende* berichten en het domein van de afzender (dat *een* intern domein lijkt te zijn) wordt zichtbaar. De richtingswaarde staat los van de bericht traceren en kan afwijken van de waarde voor bericht traceren. Resultaten kunnen naar een spreadsheet worden geëxporteerd.

    **Overschrijven:** dit filter haalt informatie op die wordt weergegeven op het tabblad Details van de e-mail en gebruikt dit om aan te geven waar organisatie- of gebruikersbeleid voor het toestaan en blokkeren van e-mailberichten *is overgenomen.* Het belangrijkste aan dit filter is dat het beveiligingsteam van uw organisatie kan zien hoeveel verdachte e-mailberichten zijn bezorgd vanwege configuratie. Hierdoor hebben ze de mogelijkheid om de mogelijkheid toe te passen en te blokken wanneer dat nodig is. Deze resultatenset van dit filter kan worden geëxporteerd naar een spreadsheet.

    ****

    |Bedreigingsverkenner wordt overschrijven|Wat ze betekenen|
    |---|---|
    |Toegestaan volgens organisatiebeleid|E-mail is in het postvak toegestaan volgens het organisatiebeleid.|
    |Geblokkeerd door organisatiebeleid|E-mail is geblokkeerd voor bezorging in het postvak, zoals omgeleid door het organisatiebeleid.|
    |Bestandsextensie geblokkeerd door organisatiebeleid|Bestand is geblokkeerd voor bezorging in het postvak, zoals omgeleid door het organisatiebeleid.|
    |Toegestaan door gebruikersbeleid|E-mail is in het postvak toegestaan volgens het gebruikersbeleid.|
    |Geblokkeerd door gebruikersbeleid|E-mail is geblokkeerd voor bezorging in het postvak, volgens het gebruikersbeleid.|
    |

    **URL-bedreiging:** het veld URL-bedreiging is opgenomen op het *detailtabblad* van een e-mail om de bedreiging aan te geven die door een URL wordt voorgesteld. Bedreigingen die door een URL worden gepresenteerd, kunnen *Malware,* *Phish* of *Spam* zijn, en een URL *zonder* bedreiging staat *Onder* de bedreigingssectie.

7. **E-mailtijdlijnweergave:** Uw team voor beveiligingsbewerkingen moet mogelijk dieper in op de e-maildetails om nader onderzoek te doen. Via de e-mailtijdlijn kunnen beheerders acties bekijken die voor een e-mailbericht zijn gemaakt, van bezorging tot na bezorging. Als u een tijdlijn per e-mail wilt weergeven, klikt u op het onderwerp van een e-mailbericht en klikt u vervolgens op Tijdlijn per e-mail. (Deze wordt weergegeven naast andere koppen in het deelvenster, zoals Overzicht of Details.) Deze resultaten kunnen worden geëxporteerd naar een spreadsheet.

    De e-mailtijdlijn wordt geopend in een tabel met alle bezorgings- en bezorgingsgebeurtenissen voor de e-mail. Als er geen verdere acties op de e-mail zijn, moet u één gebeurtenis zien voor de oorspronkelijke bezorging die een resultaat, zoals *Geblokkeerd,* met een uitspraak zoals *Phish geeft.* Beheerders kunnen de volledige tijdlijn van de e-mail exporteren, inclusief alle details op het tabblad en e-mailberichten (zoals Onderwerp, Afzender, Geadresseerde, Netwerk en Bericht-id). De e-mailtijdlijn bezuinigt minder willekeurigheid omdat er minder tijd wordt besteed aan het controleren van verschillende locaties om te proberen wat er precies is gebeurd sinds de e-mail is ontvangen. Wanneer er meerdere gebeurtenissen tegelijk op of in de buurt van een e-mailbericht plaatsvinden, worden deze gebeurtenissen weergegeven in een tijdlijnweergave.

8. **Preview/download:** Bedreigingsverkenner geeft uw team voor beveiligingsbewerkingen de details die ze nodig hebben om verdachte e-mail te onderzoeken. Uw team voor beveiligingsbewerkingen kan:

    - [Controleer de bezorgingsactie en locatie.](#check-the-delivery-action-and-location)

    - [Bekijk de tijdlijn van uw e-mail.](#view-the-timeline-of-your-email)

### <a name="check-the-delivery-action-and-location"></a>De bezorgingsactie en locatie controleren

In [Bedreigingsverkenner (en realtime detecties)](threat-explorer.md)ziet  u nu kolommen Bezorgingsactie en Bezorgingslocatie in plaats van de voormalige **kolom Bezorgingsstatus.**  Dit levert een vollediger beeld op van waar uw e-mailberichten terecht komen. Het doel van deze wijziging is om onderzoeken gemakkelijker te maken voor teams met beveiligingsbewerkingen, maar het resultaat is de locatie van probleem-e-mailberichten in één oogopslag te weten.

Bezorgingsstatus is nu onderverdeeld in twee kolommen:

- **Bezorgingsactie:** wat is de status van deze e-mail?

- **Bezorgingslocatie:** waar is deze e-mail omgeleid?

Bezorgingsactie is de actie die wordt ondernomen op een e-mail vanwege bestaand beleid of detecties. Dit zijn de mogelijke acties die een e-mail kan uitvoeren:

- **Bezorgd:** e-mail is bezorgd in het Postvak IN of de map van een gebruiker en de gebruiker kan er rechtstreeks toegang toe krijgen.

- **Ongewenste** e-mail: e-mail is verzonden naar de map Ongewenste e-mail of verwijderde map van de gebruiker en de gebruiker heeft toegang tot e-mailberichten in de map Ongewenste e-mail of Verwijderd.

- **Geblokkeerd:** alle e-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of die zijn geplaatst. (Dit is volledig ontoegankelijk voor de gebruiker.)

- **Vervangen:** alle e-mailberichten waarin schadelijke bijlagen worden vervangen door TXT-bestanden waarin wordt staat dat de bijlage schadelijk is.

Bezorgingslocatie bevat de resultaten van beleidsregels en detecties die na de bezorging worden uitgevoerd. De actie is gekoppeld aan een bezorgingsactie. Dit veld is toegevoegd om inzicht te geven in de actie die wordt ondernomen wanneer er een probleem met e-mail wordt gevonden. Hier zijn de mogelijke waarden voor de bezorgingslocatie:

- **Postvak IN of map:** de e-mail staat in het Postvak IN of in een map (volgens uw e-mailregels).

- **On-premises of extern:** het postvak bestaat niet in de cloud, maar is on-premises.

- **Map Ongewenste** e-mail: de e-mail staat in de map Ongewenste e-mail van een gebruiker.

- **Map Verwijderde items:** de e-mail staat in de map Verwijderde items van een gebruiker.

- **Quarantaine:** de e-mail in quarantaine en niet in het postvak van een gebruiker.

- **Mislukt:** het e-mailbericht kan niet in het postvak worden bereikt.

- **Afgekapt:** de e-mail gaat ergens verloren in de e-mailstroom.

### <a name="view-the-timeline-of-your-email"></a>De tijdlijn van uw e-mail weergeven

**E-mailtijdlijn** is een veld in Bedreigingsverkenner dat het zoeken naar beveiligingsacties gemakkelijker maakt. Wanneer er meerdere gebeurtenissen op hetzelfde moment of op hetzelfde moment in een e-mailbericht plaatsvinden, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. Sommige gebeurtenissen na bezorging van e-mail worden vastgelegd in de **kolom** Speciale acties. Door informatie uit de tijdlijn van een e-mailbericht te combineren met speciale acties die na de bezorging zijn uitgevoerd, krijgen beheerders inzicht in beleidsregels en risicoafhandeling (zoals waar de e-mail is doorgestuurd en, in sommige gevallen, wat de uiteindelijke evaluatie was).

> [!IMPORTANT]
> Ga hier naar een [oplossingsonderwerp.](remediate-malicious-email-delivered-office-365.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Herstel schadelijke e-mail die wordt geleverd in Office 365](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender voor Office 365](office-365-ti.md)

[Beveiligen tegen bedreigingen in Office 365](protect-against-threats.md)

[Rapporten voor Defender voor Office 365 weergeven](view-reports-for-atp.md)
