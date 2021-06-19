---
title: Schadelijke e-mail onderzoeken die is bezorgd in Microsoft 365, Schadelijke e-mail zoeken en onderzoeken
keywords: TIMailData-Inline, Beveiligingsincident, incident, Microsoft Defender voor Eindpunt PowerShell, e-mail malware, gecompromitteerde gebruikers, e-mail phish, e-mail malware, lees e-mailkoppen, leeskoppen, open e-mailkoppen, speciale acties
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
description: Meer informatie over het gebruik van mogelijkheden voor het onderzoeken en reageren van bedreigingen om schadelijke e-mail te zoeken en te onderzoeken.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e99cda906e97db72a440c3daf509a767181e5342
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029789"
---
# <a name="investigate-malicious-email-that-was-delivered-in-microsoft-365"></a>Schadelijke e-mail onderzoeken die is bezorgd in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op:**

- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Met Microsoft Defender voor Office 365](defender-for-office-365.md) kunt u activiteiten onderzoeken die personen in uw organisatie in gevaar brengen en actie ondernemen om uw organisatie te beschermen. Als u bijvoorbeeld deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u verdachte e-mailberichten vinden en onderzoeken die zijn bezorgd. U kunt dit doen met [Behulp van Threat Explorer (of realtime detecties)](threat-explorer.md).

> [!NOTE]
> Ga naar het artikel over herstel [hier.](remediate-malicious-email-delivered-office-365.md)

## <a name="before-you-begin"></a>Voordat u begint

Zorg ervoor dat aan de volgende vereisten wordt voldaan:

- Uw organisatie heeft [Microsoft Defender voor Office 365](defender-for-office-365.md) en licenties worden toegewezen aan [gebruikers.](../../admin/manage/assign-licenses-to-users.md)

- [Auditregistratie](../../compliance/turn-audit-log-search-on-or-off.md) is ingeschakeld voor uw organisatie.

- Uw organisatie heeft beleidsregels gedefinieerd voor antispam, anti-malware, anti-phishing, en meer. Zie [Beschermen tegen bedreigingen in Office 365.](protect-against-threats.md)

- U bent een globale beheerder of u hebt de beveiligingsbeheerder of de rol Zoeken en zuiveren toegewezen in de Microsoft 365 Defender portal. Zie Machtigingen in de Microsoft 365 Defender [portal voor meer informatie.](permissions-microsoft-365-security-center.md) Voor sommige acties moet ook de voorbeeldrol zijn toegewezen.

### <a name="preview-role-permissions"></a>Voorbeeld van rolmachtigingen

Als u bepaalde acties wilt uitvoeren, zoals het weergeven van berichtkoppen of het downloaden van e-mailberichtinhoud, moet u de voorbeeldrol toevoegen aan een andere geschikte rollengroep.  In de volgende tabel worden vereiste rollen en machtigingen opgehelderd.

<br>

****

|Activiteit|Rollengroep|Voorbeeldrol nodig?|
|---|---|---|
|Threat Explorer (en realtimedetecties) gebruiken om bedreigingen te analyseren |Globale beheerder <p> Beveiligingsbeheerder <p> Beveiligingslezer|Nee|
|Bedreigingsverkenner (en realtimedetecties) gebruiken om kopteksten voor e-mailberichten weer te geven en om in quarantaine geplaatste e-mailberichten te bekijken en te downloaden|Globale beheerder <p> Beveiligingsbeheerder <p> Beveiligingslezer|Nee|
|Threat Explorer gebruiken om kopteksten weer te geven, een voorbeeld van e-mail weer te geven (alleen op de pagina met e-mailentiteit) en e-mailberichten te downloaden die in postvakken zijn bezorgd|Globale beheerder <p> Beveiligingsbeheerder <p> Beveiligingslezer <p> Voorbeeld|Ja|
|

> [!NOTE]
> *Voorbeeld* is een rol, geen rollengroep. De voorbeeldrol moet worden toegevoegd aan een bestaande rollengroep in de Microsoft 365 Defender portal ( <https://security.microsoft.com> ). Ga naar **Machtigingen** en bewerk vervolgens een bestaande rollengroep of voeg een nieuwe rollengroep toe met de **toegewezen voorbeeldrol.**
>
> De rol Globale beheerder wordt toegewezen aan Microsoft 365-beheercentrum ( ) en de rollen Beveiligingsbeheerder en Beveiligingslezer worden <https://admin.microsoft.com> toegewezen in Microsoft 365 Defender ( <https://security.microsoft.com> ). Zie Machtigingen in de portal Microsoft 365 Defender voor meer informatie over rollen [en machtigingen.](permissions-microsoft-365-security-center.md)

We begrijpen dat het bekijken en downloaden van e-mail gevoelige activiteiten zijn en daarom is auditing ingeschakeld voor deze activiteiten. Wanneer een beheerder deze activiteiten uitvoert op e-mailberichten, worden auditlogboeken voor hetzelfde gegenereerd en kunnen ze worden gezien in het Office 365 Security & Compliance Center ( <https://protection.office.com> ). Ga naar **Zoeken in**  >  **het auditlogboek en** filter op de naam van de beheerder in de sectie Zoeken. In de gefilterde resultaten wordt activiteit **AdminMailAccess weer te geven.** Selecteer een rij om details weer te geven in de sectie **Meer informatie** over voorbeeld van of gedownloade e-mail.

## <a name="find-suspicious-email-that-was-delivered"></a>Verdachte e-mail zoeken die is bezorgd

Threat Explorer is een krachtig rapport dat meerdere doeleinden kan dienen, zoals het vinden en verwijderen van berichten, het identificeren van het IP-adres van een kwaadaardige afzender van e-mail of het starten van een incident voor verder onderzoek. De volgende procedure is gericht op het gebruik van Verkenner om schadelijke e-mail te zoeken en te verwijderen uit de postvakken van de geadresseerde.

> [!NOTE]
> Standaardzoekingen in Explorer bevatten momenteel geen geleverde items die zijn verwijderd uit het cloudpostvak door automatische beveiliging van nul uur (ZAP). Deze beperking is van toepassing op alle weergaven (bijvoorbeeld de weergaven **\> E-mail malware** of **\> E-mail phish).** Als u items wilt opnemen die door ZAP zijn verwijderd, moet u een actieset **Bezorging** toevoegen om **Verwijderd door ZAP op te nemen.** Als u alle opties opneemt, ziet u alle resultaten van de bezorgingsactie, inclusief items die door ZAP zijn verwijderd.

1. Open de Microsoft 365 Defender portal en meld u aan met uw werk- of <https://security.microsoft.com> schoolaccount voor Office 365.

2. Ga naar **Threat Explorer door** e-mail te & **Explorer** voor \> **samenwerking** in de linkernavigatie. Als u rechtstreeks naar **Threat Explorer wilt** gaan, gebruikt u <https://security.microsoft.com/threatexplorer> .

   Op de **pagina Verkenner** worden in de kolom **Aanvullende** acties beheerders het resultaat van het verwerken van een e-mailbericht weergegeven. De **kolom Extra** acties kan worden gebruikt op dezelfde plaats als de actie **Bezorging** en de **bezorgingslocatie.** Speciale acties kunnen worden bijgewerkt aan het einde van de e-mailtijdlijn van Threat Explorer. Dit is een nieuwe functie waarmee beheerders de zoekervaring kunnen verbeteren.

3. Kies in **het** menu Beeld de optie  \> **E-mail alle e-mail** in de vervolgkeuzelijst.

    ![Threat explorer View menu, and Email - Malware, Phish, Submissions and All Email options, also Content - Malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    De *weergave Malware* is momenteel de standaardweergave en legt e-mailberichten vast waarin een malwaredreiging wordt gedetecteerd. De *phish-weergave* werkt op dezelfde manier, voor Phish.

    Alle *e-mailweergave* bevat echter elke e-mail die door de organisatie is ontvangen, ongeacht of er bedreigingen zijn gedetecteerd of niet. Zoals u zich kunt voorstellen, is dit een groot aantal gegevens. Daarom wordt in deze weergave een tijdelijke aanduiding voor het toepassen van een filter voorgesteld. (Deze weergave is alleen beschikbaar voor Defender voor Office 365 P2-klanten.)

    *De weergave* Inzendingen toont alle e-mails die zijn verzonden door een beheerder of gebruiker die zijn gerapporteerd bij Microsoft.

4. **Zoeken en filteren in Threat Explorer:** filters worden boven aan de pagina in de zoekbalk weergegeven om beheerders te helpen bij hun onderzoeken. U ziet dat meerdere filters tegelijk kunnen worden toegepast en dat meerdere door komma's gescheiden waarden aan een filter worden toegevoegd om de zoekopdracht te beperken. Denk eraan:

    - Filters komen exact overeen met de meeste filtervoorwaarden.
    - Onderwerpfilter gebruikt een CONTAINS-query.
    - URL-filters werken met of zonder protocollen (bijvoorbeeld. https).
    - Url-domein, URL-pad en URL-domein- en padfilters vereisen geen protocol om te filteren.
    - U moet telkens op het pictogram Vernieuwen klikken wanneer u de filterwaarden wijzigt om relevante resultaten te krijgen.

5. **Geavanceerde filters:** met deze filters kunt u complexe query's maken en uw gegevensset filteren. Als u op Geavanceerde *filters klikt,* wordt een flyout met opties geopend.

   Geavanceerd filteren is een geweldige aanvulling op zoekmogelijkheden. Met een booleaanse NOT op de domeinfilters **Geadresseerde,** **Afzender** en Afzender kunnen **beheerders** onderzoeken door waarden uit te sluiten. Deze optie is de **optie Is gelijk aan geen selectie.** Met deze optie kunnen beheerders ongewenste postvakken uitsluiten van onderzoeken (bijvoorbeeld waarschuwingspostvakken en standaardantwoordpostvakken) en is dit handig voor gevallen waarin beheerders zoeken naar een specifiek onderwerp (bijvoorbeeld Aandacht), waarbij de geadresseerde kan worden ingesteld op Geen *van: defaultMail@contoso.com.* Dit is een exacte waardezoekactie.

   ![Het filter Geadresseerden - 'Bevat geen van' Geavanceerd.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   Als u een tijdfilter toevoegt aan de begin- en einddatum, kan uw beveiligingsteam snel inzoomen. De kortste toegestane tijdsduur is 30 minuten. Als u de verdachte actie kunt beperken op tijdsframe (bijvoorbeeld 3 uur geleden), wordt de context beperkt en wordt het probleem aan het licht geholpen.

   ![De optie filteren op uren om de hoeveelheid gegevensbeveiligingsteams te beperken die moet worden verwerkt en waarvan de kortste duur 30 minuten is.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Velden in Threat Explorer:** Threat Explorer bevat veel meer beveiligingsgerelateerde e-mailgegevens, zoals Bezorgingsactie, Bezorgingslocatie, Speciale *actie,* *Directionality,* *Overschrijven* en *URL-bedreiging.* Hiermee kan het beveiligingsteam van uw organisatie ook met een hogere zekerheid onderzoek doen.

    *Bezorgingsactie* is de actie die is ondernomen op een e-mail vanwege bestaand beleid of detecties. Hier volgen de mogelijke acties die een e-mail kan uitvoeren:

    - **Bezorgd:** e-mail is bezorgd in het Postvak IN of de map van een gebruiker en de gebruiker heeft rechtstreeks toegang tot de e-mail.
    - **Ongewenste e-mail** (bezorgd bij ongewenste e-mail): e-mail is verzonden naar de map Ongewenste e-mail of verwijderde map van de gebruiker en de gebruiker heeft toegang tot e-mailberichten in de map Ongewenste e-mail of Verwijderd.
    - **Geblokkeerd:** e-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of die zijn gedropt. (Dit is volledig ontoegankelijk voor de gebruiker.)
    - **Vervangen:** e-mailberichten waarin schadelijke bijlagen worden vervangen door .txt waarin staat dat de bijlage schadelijk was

    **Bezorgingslocatie:** het filter Bezorgingslocatie is beschikbaar om beheerders te helpen begrijpen waar verdachte schadelijke e-mail is terecht gekomen en welke acties er zijn ondernomen. De resulterende gegevens kunnen worden geëxporteerd naar een spreadsheet. Mogelijke bezorgingslocaties zijn:

    - **Postvak IN of map:** de e-mail staat in het Postvak IN of in een specifieke map, volgens uw e-mailregels.
    - **On-prem of extern:** het postvak bestaat niet in de cloud, maar is on-premises.
    - **Map Ongewenste** e-mail: de e-mail staat in de map Ongewenste e-mail van een gebruiker.
    - **Map Verwijderde items:** de e-mail staat in de map Verwijderde items van een gebruiker.
    - **Quarantaine:** de e-mail in quarantaine en niet in het postvak van een gebruiker.
    - **Mislukt:** het e-mailbericht kan het postvak niet bereiken.
    - **Gedropt:** de e-mail is ergens in de e-mailstroom verloren gegaan.

    **Richtingsrichting:** met deze optie kan uw beveiligingsbewerkingsteam filteren op de 'richting' waar een e-mailbericht vandaan komt of die wordt verzonden. Directionality values are *Inbound,* Outbound , and *Intra-org* (correspond to mail coming into your org from outside, being sent out of your org, or being *sently* internally to your org, respectively). Met deze informatie kunnen beveiligingsbewerkingen teams spoofing en imitatie herkennen, omdat er een verkeerde match is tussen de richtingswaarde (bijvoorbeeld. *Binnenkomende*), en het domein van de afzender (dat *lijkt op* een intern domein) is duidelijk! De richtingswaarde is gescheiden en kan afwijken van de berichtspoorwaarde. Resultaten kunnen worden geëxporteerd naar spreadsheets.

    **Overschrijven:** Met dit filter wordt informatie overgenomen die wordt weergegeven op het tabblad Details van de e-mail en wordt deze gebruikt om aan te geven waar organisatie- of gebruikersbeleid is overgenomen voor het toestaan en blokkeren van e-mails.  Het belangrijkste aan dit filter is dat het beveiligingsteam van uw organisatie kan zien hoeveel verdachte e-mailberichten zijn bezorgd vanwege de configuratie. Dit biedt hen de mogelijkheid om de mogelijkheid om de mogelijkheden en blokken zo nodig aan te passen. Deze resultatenset van dit filter kan worden geëxporteerd naar een spreadsheet.

    <br>

    ****

    |Bedreigingsverkenner overschrijven|Wat ze betekenen|
    |---|---|
    |Toegestaan door organisatiebeleid|E-mail is toegestaan in het postvak, zoals aangegeven door het organisatiebeleid.|
    |Geblokkeerd door organisatiebeleid|E-mail is geblokkeerd voor bezorging naar het postvak, zoals wordt aangegeven door het organisatiebeleid.|
    |Bestandsextensie geblokkeerd door organisatiebeleid|Bestand is geblokkeerd voor bezorging in het postvak, zoals wordt aangegeven door het organisatiebeleid.|
    |Toegestaan door gebruikersbeleid|E-mail is toegestaan in het postvak volgens het gebruikersbeleid.|
    |Geblokkeerd door gebruikersbeleid|E-mail is geblokkeerd voor bezorging naar het postvak, zoals wordt aangegeven door het gebruikersbeleid.|
    |

    **URL-bedreiging:** het veld URL-bedreiging is opgenomen op het *tabblad Details* van een e-mailbericht om de bedreiging aan te geven die door een URL wordt weergegeven. Bedreigingen die door een URL worden gepresenteerd, kunnen *Malware,* *Phish* of  *Spam* zijn, en een URL zonder bedreiging zegt *Geen* in de sectie bedreigingen.

7. **E-mailtijdlijnweergave:** Uw team voor beveiligingsbewerkingen moet mogelijk diep in de e-maildetails duiken om het verder te onderzoeken. Met de e-mailtijdlijn kunnen beheerders acties bekijken die zijn ondernomen op een e-mail van bezorging tot postbezorging. Als u een e-mailtijdlijn wilt weergeven, klikt u op het onderwerp van een e-mailbericht en klikt u vervolgens op E-mailtijdlijn. (Deze wordt weergegeven tussen andere koppen in het deelvenster, zoals Samenvatting of Details.) Deze resultaten kunnen worden geëxporteerd naar spreadsheets.

    E-mailtijdlijn wordt geopend voor een tabel met alle bezorgings- en postbezorgingsgebeurtenissen voor het e-mailbericht. Als er geen verdere acties op het e-mailbericht staan, ziet u één gebeurtenis voor de oorspronkelijke bezorging met een resultaat, zoals *Geblokkeerd,* met een uitspraak zoals *Phish.* Beheerders kunnen de volledige e-mailtijdlijn exporteren, inclusief alle details op het tabblad en e-mail (zoals Onderwerp, Afzender, Geadresseerde, Netwerk en Bericht-id). De e-mailtijdlijn vermindert randomisatie omdat er minder tijd is besteed aan het controleren van verschillende locaties om te proberen te begrijpen wat er is gebeurd sinds de e-mail is aangekomen. Wanneer er meerdere gebeurtenissen tegelijk plaatsvinden op een e-mail of in de buurt, worden deze gebeurtenissen weergegeven in een tijdlijnweergave.

8. **Preview/download:** Threat Explorer geeft uw beveiligingsteam de details die ze nodig hebben om verdachte e-mail te onderzoeken. Uw beveiligingsteam kan het volgende doen:

    - [Controleer de bezorgingsactie en de locatie.](#check-the-delivery-action-and-location)

    - [Bekijk de tijdlijn van uw e-mail.](#view-the-timeline-of-your-email)

### <a name="check-the-delivery-action-and-location"></a>De bezorgingsactie en locatie controleren

In [Threat Explorer (en realtimedetecties)](threat-explorer.md)hebt  u  nu de kolommen Bezorgingsactie en Bezorgingslocatie in plaats van de voormalige kolom Bezorgingsstatus.  Dit resulteert in een vollediger beeld van waar uw e-mailberichten terecht komen. Een deel van het doel van deze wijziging is om onderzoeken gemakkelijker te maken voor beveiligingsbewerkingsteams, maar het nettoresultaat is de locatie van probleem-e-mailberichten in één oogopslag te kennen.

De bezorgingsstatus is nu onderverdeeld in twee kolommen:

- **Bezorgingsactie:** wat is de status van dit e-mailbericht?
- **Bezorgingslocatie:** waar is dit e-mailbericht als resultaat gerouteerd?

Bezorgingsactie is de actie die is ondernomen op een e-mail vanwege bestaand beleid of detecties. Hier volgen de mogelijke acties die een e-mail kan uitvoeren:

- **Bezorgd:** e-mail is bezorgd in het Postvak IN of de map van een gebruiker en de gebruiker heeft rechtstreeks toegang tot de e-mail.
- **Ongewenste** e-mail: e-mail is verzonden naar de map Ongewenste e-mail of verwijderde map van de gebruiker en de gebruiker heeft toegang tot e-mailberichten in de map Ongewenste e-mail of Verwijderd.
- **Geblokkeerd:** e-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of die zijn gedropt. (Dit is volledig ontoegankelijk voor de gebruiker.)
- **Vervangen:** e-mailberichten waarin schadelijke bijlagen worden vervangen door .txt waarin staat dat de bijlage schadelijk was.

Bezorgingslocatie toont de resultaten van beleidsregels en detecties die na de bezorging worden uitgevoerd. Deze is gekoppeld aan een bezorgactie. Dit veld is toegevoegd om inzicht te geven in de actie die is ondernomen wanneer een probleemmail wordt gevonden. Hier zijn de mogelijke waarden van de bezorgingslocatie:

- **Postvak IN of map:** de e-mail staat in het Postvak IN of in een map (volgens uw e-mailregels).
- **On-prem of extern:** het postvak bestaat niet in de cloud, maar is on-premises.
- **Map Ongewenste** e-mail: de e-mail staat in de map Ongewenste e-mail van een gebruiker.
- **Map Verwijderde items:** de e-mail staat in de map Verwijderde items van een gebruiker.
- **Quarantaine:** de e-mail in quarantaine en niet in het postvak van een gebruiker.
- **Mislukt:** het e-mailbericht kan het postvak niet bereiken.
- **Gedropt:** de e-mail gaat ergens in de e-mailstroom verloren.

### <a name="view-the-timeline-of-your-email"></a>De tijdlijn van uw e-mail weergeven

**E-mailtijdlijn** is een veld in Threat Explorer dat het zoeken gemakkelijker maakt voor uw beveiligingsteam. Wanneer er meerdere gebeurtenissen op hetzelfde moment op een e-mail plaatsvinden of bijna op hetzelfde moment plaatsvinden, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. Sommige gebeurtenissen die plaatsvinden na de bezorging van e-mail, worden vastgelegd in **de kolom Speciale** acties. Als u gegevens uit de tijdlijn van een e-mailbericht combineert met speciale acties die na de bezorging zijn uitgevoerd, krijgen beheerders inzicht in beleid en bedreigingsafhandeling (zoals waar de e-mail is gerouteerd, en in sommige gevallen wat de uiteindelijke beoordeling was).

> [!IMPORTANT]
> Ga hier naar een [herstelonderwerp.](remediate-malicious-email-delivered-office-365.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Herstel schadelijke e-mail die is bezorgd in Office 365](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender voor Office 365](office-365-ti.md)

[Beschermen tegen bedreigingen in Office 365](protect-against-threats.md)

[Rapporten weergeven voor Defender voor Office 365](view-reports-for-mdo.md)
