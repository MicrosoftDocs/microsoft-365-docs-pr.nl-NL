---
title: De e-mailentiteitspagina van Microsoft Defender voor Office 365 (MDO)
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Klanten met Microsoft Defender voor Office 365 E5 en ATP P1 en ATP P2 krijgen nu een 360-graden weergave van elke e-mail met de pagina van de e-mailentiteit.
ms.openlocfilehash: 0a866b4d635e5c9e26b6fc065503b44ee2063e9f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289483"
---
# <a name="the-email-entity-page"></a>De pagina E-mailentiteit

**In dit artikel:**
- [De pagina van de e-mailentiteit bereiken](#reach-the-email-entity-page)
- [De pagina van de e-mailentiteit lezen](#read-the-email-entity-page)
- [Paginatabbladen van e-mailentiteit gebruiken](#use-email-entity-page-tabs)
- [Nieuw op de pagina van de e-mailentiteit](#new-to-the-email-entity-page)

Beheerders van Microsoft Defender voor Office 365 (of MDO) E5 en MDO P1 en P2 hebben een 360-graden weergave van e-mail via de pagina E-mailentiteit. Deze e-mailpagina is gemaakt om de informatie te verbeteren die wordt weergegeven op de fly out met [e-mailgegevens van Bedreigingsverkenner.](threat-explorer-views.md)

## <a name="reach-the-email-entity-page"></a>De pagina van de e-mailentiteit bereiken

In het bestaande Office-beveiligings- en compliancecentrum (protection.office.com) of het nieuwe Microsoft 365-beveiligingscentrum (security.microsoft.com) kunt u de pagina van de e-mailentiteit bekijken en gebruiken.

|Centreer  |URL  |Navigatie  |
|---------|---------|---------|
|Naleving & beveiliging |protection.office.com | Threat Management > Explorer   |
|Microsoft 365-beveiligingscentrum |security.microsoft.com | E& mail voor samenwerking > Verkenner |

Selecteer in Bedreigingsverkenner het onderwerp van een e-mailbericht dat u aan het onderzoeken bent. Boven aan het uitvliegende e-mailbericht voor die e-mail wordt een gouden balk weergegeven. Deze uitnodiging voor de nieuwe pagina bevat de tekst 'Probeer onze nieuwe e-mailentiteitspagina uit met aanvullende gegevens...'. Selecteer deze optie om de nieuwe pagina weer te geven.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="U ziet een gouden banner met de woorden *Probeer onze nieuwe e-mailentiteitspagina uit met aanvullende gegevens* om naar de nieuwe ervaring te navigeren.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Deze afbeelding van de pagina van de e-mailentiteit is gericht op koppen die u ziet. Let op: de koptekst van het e-mailbericht wordt hier weergegeven.":::

> [!NOTE]
> De machtigingen die u nodig hebt om deze pagina weer te geven en te gebruiken, zijn hetzelfde als voor het weergeven van Bedreigingsverkenner. De beheerder moet lid zijn van een globale beheerder of globale lezer, of beveiligingsbeheerder of beveiligingslezer.

## <a name="read-the-email-entity-page"></a>De pagina van de e-mailentiteit lezen

De structuur is ontworpen om eenvoudig te kunnen worden gelezen en in één oogopslag door de structuur te navigeren. Via de verschillende tabbladen aan de bovenkant van de pagina kunt u meer details onderzoeken. De indeling werkt als volgende:

1. De meest vereiste velden staan aan de linkerkant van de fly-out. Deze details zijn 'plak', wat betekent dat ze aan de linkerkant zijn verankerd, ongeacht het tabblad waar u naartoe navigeert in de rest van de fly-out.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Afbeelding van de pagina van de e-mailentiteit met de linkerkant gemarkeerd. Hier staan de titel en feiten over de bezorging van e-mail.":::

2. In de rechterbovenhoek ziet u de acties die u kunt uitvoeren op een e-mailbericht. Alle acties die via Verkenner kunnen worden ondernomen, zijn ook beschikbaar via de pagina van de e-mailentiteit.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Afbeelding van de pagina van de e-mailentiteit met de *rechter*-kant gemarkeerd, ditmaal. Acties zoals E-mailvoorbeeld en Ga naar quarantaine zijn nu beschikbaar.":::

3. U kunt een grondigere analyse uitvoeren door de rest van de pagina te sorteren. Controleer de details van de e-maildetectie, de status van de e-mailverificatie en de koptekst. Dit gebied moet per geval worden bekeken, maar de informatie in deze tabbladen is beschikbaar voor elk e-mailbericht.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Het hoofdvenster van deze pagina bevat de e-mailkop en de verificatiestatus.":::

### <a name="use-email-entity-page-tabs"></a>Paginatabbladen van e-mailentiteit gebruiken

Via de tabbladen boven aan de entiteitspagina kunt u e-mail efficiënt onderzoeken.

1. **Tijdlijn:** De tijdlijnweergave voor een e-mailbericht (volgens de tijdlijn van Bedreigingsverkenner) toont de oorspronkelijke bezorging bij gebeurtenissen na bezorging die plaatsvinden in een e-mailbericht. Voor e-mailberichten die geen acties na bezorging hebben, wordt in de weergave de oorspronkelijke bezorgingsrij weergegeven in de tijdlijnweergave. Gebeurtenissen zoals: Zero-hour Auto Purge (ZAP), Herstellen, URL-klikken, et balk, van bronnen zoals: systeem, beheerder en gebruiker, worden hier weergegeven, in de volgorde waarin ze hebben plaatsgevonden.
2. **Analyse:** Analyse toont velden die beheerders helpen een e-mail uitgebreid te analyseren. Voor gevallen waarin beheerders meer informatie moeten hebben over detectie, afzender/geadresseerde en gegevens over e-mailverificatie, moeten ze het tabblad Analyse gebruiken. Koppelingen voor bijlagen en URL's vindt u ook op deze pagina, onder Gerelateerde entiteiten. Zowel bijlagen als geïdentificeerde bedreigingen worden hier genummerd, en als u klikt, gaat u rechtstreeks naar de pagina's Bijlagen en URL. Dit tabblad heeft ook de optie Koptekst weergeven om *de koptekst van de e-mail weer te geven.* Beheerders kunnen alle details in e-mailberichtkoppen naast de informatie in het hoofdvenster vergelijken voor duidelijkheid.
3. **Bijlagen:** hiermee worden bijlagen in de e-mail onderzocht, met andere gegevens die zijn gevonden in bijlagen. Het aantal weergegeven bijlagen is momenteel beperkt tot 10. U ziet dat detonatiedetails voor bijlagen die schadelijk zijn, hier ook worden weergegeven.
4. **URL's:** dit tabblad bevat URL's in de e-mail met andere details over de URL's. Het aantal URL's is op dit moment beperkt tot 10, maar deze 10 hebben prioriteit, om schadelijke URL's eerst *weer te geven.* Prioriteit besparen u tijd en raad-werk. De URL's die schadelijk en gedetoneerd zijn gevonden, worden hier ook weergegeven.
5. **Vergelijkbare e-mailberichten:** dit tabblad bevat alle e-mailberichten die lijken op de *netwerkbericht-id en* de combinatie van geadresseerden die specifiek is voor deze e-mail. Overeenkomsten zijn alleen gebaseerd op *de bericht* zelf. Bijlagen worden niet in overweging genomen bij de bepalingen die door e-mailberichten zijn gedaan om ze als 'vergelijkbaar' *te categoriseren.*

## <a name="new-to-the-email-entity-page"></a>Nieuw op de pagina van de e-mailentiteit

Deze e-mailentiteitspagina biedt nieuwe mogelijkheden. Hier is de lijst.

### <a name="email-preview-for-cloud-mailboxes"></a>E-mailvoorbeeld voor cloudpostvakken
Beheerders kunnen een voorbeeld van e-mailberichten in postvakken in de cloud bekijken, ***als*** de e-mailberichten nog steeds aanwezig zijn in de cloud. In geval van een soft delete (door een beheerder of gebruiker) of ZAP (in quarantaine), zijn e-mailberichten niet meer aanwezig in de cloudlocatie. In dat geval kunnen beheerders geen voorbeeld van deze specifieke e-mailberichten bekijken. E-mailberichten die zijn weggelaten of waarbij bezorging mislukte, zijn nooit in het postvak bezorgd. Hierdoor kunnen beheerders ook geen voorbeeld van deze e-mailberichten bekijken.

> [!WARNING]
>Als u een voorbeeld van e-mailberichten wilt bekijken, moet een speciale rol met de naam ***Preview** _ worden toegewezen aan beheerders. U kunt deze rol toevoegen door naar _ Machtigingen & rollen * > **E-mail** &*samenwerkingsrollen* in *security.microsoft.com* of **Machtigingen** in *protection.office.com.* Voeg de ***preview-rol*** toe aan een van de rollengroepen of een kopie van een rollengroep waarmee beheerders in uw organisatie in Bedreigingsverkenner kunnen werken.

### <a name="detonation-details"></a>Detonatiedetails

Deze details zijn specifiek voor e-mailbijlagen en URL's.

Gebruikers zien nu meer informatie over bekende schadelijke bijlagen of hyperlinks die in hun postvakken zijn aangetroffen, zoals Detonation Chain, Detonation Summary, Screenshot en Observed behavior details om klanten te helpen begrijpen waarom de bijlage of URL als schadelijk is beschouwd en is gedetoneerd.
 
- *Detonatieketen:* één bestand of URL-detonatie kan tot meerdere detonaties leiden. De detonatieketen houdt het pad van detonaties bij, inclusief het oorspronkelijke schadelijke bestand of de URL die het resultaat heeft veroorzaakt, en alle andere bestanden of URL's die door de detonatie zijn veroorzaakt. Deze URL's of bijgevoegde bestanden zijn mogelijk niet rechtstreeks in de e-mail aanwezig, maar het is wel belangrijk om te bepalen waarom het bestand of de URL schadelijk is gevonden.
- *Samenvatting van detonatie:* hier vindt u informatie over:
    - Detonatietijdbereik.
    - Een afbeelding van het bijgevoegde bestand of de URL.
    - Gerelateerde informatie (bestandsnummer, URL's, IP's of domeinen), die andere entiteiten zijn die tijdens detonatie worden onderzocht.
- *Schermafbeelding van detonatie:* hier ziet u schermafbeeldingen die zijn gemaakt tijdens detonatie.
- *Detonatiedetails:* dit zijn de exacte details van het gedrag van elk proces dat heeft plaatsgevonden tijdens de detonatie.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Schermafbeelding van het overzicht van detonatie met de ketting, samenvatting, detonatiedetails en schermafbeelding onder de kop *Deep Analysis*.":::

### <a name="other-innovations"></a>Andere innovaties

*Tags:* dit zijn tags die worden toegepast op gebruikers. Als de gebruiker een geadresseerde is, zien beheerders een *tag voor de ontvanger.* En als de gebruiker een afzender is, is dit ook een *tag voor de* afzender. Dit wordt weergegeven aan de linkerkant van de pagina met e-mailentiteiten (in het gedeelte dat wordt beschreven als plakkerig en dus verankerd aan de pagina). 

*Meest recente* bezorgingslocatie: de meest recente bezorgingslocatie is de locatie waar een e-mail wordt bezorgd na systeemacties zoals ZAP, of beheeracties zoals Verplaatsen naar Verwijderde items, voltooien. De meest recente bezorgingslocatie is niet bedoeld om beheerders te informeren over de huidige locatie van *het* bericht. Als een gebruiker bijvoorbeeld een bericht verwijdert of naar een archief verplaatst, wordt de bezorgingslocatie niet bijgewerkt. Als er echter een systeemactie heeft plaatsgevonden en de locatie is bijgewerkt (zoals zap waardoor een e-mailbericht in quarantaine wordt geplaatst), wordt de meest recente bezorgingslocatie in quarantaine bijgewerkt.

*E-maildetails:* details die nodig zijn voor een beter begrip van e-mail op het *tabblad* Analyse.

- *Exchange-transportregels (ETR's of Mailflow-regels)*: Deze regels worden toegepast op een bericht op de transportlaag en hebben prioriteit boven phish- en spamspamingswortels. Deze kunnen alleen worden gemaakt en gewijzigd in het Exchange-beheercentrum, maar als een ETR van toepassing is op een bericht, worden de ETR-naam en GUID hier weergegeven. Waardevolle informatie voor traceringsdoeleinden.
    
- *Overschrijven* systeem: Dit is een manier om uitzonderingen op de bezorgingslocatie voor een bericht aan te brengen door de leveringslocatie te vervangen die door het systeem wordt gegeven (volgens de technologie voor bedreiging en detectie).
    
- *Regel voor ongewenste* e-mail: Ongewenste e-mail is een verborgen regel voor Postvak IN die standaard in elk postvak is ingeschakeld.
    - Wanneer de regel voor ongewenste e-mail is ingeschakeld in het postvak, kan Exchange Online Protection (EOP) berichten naar ongewenste e-mail verplaatsen op basis van bepaalde criteria. De overstap kan zijn gebaseerd op actie van de spamfilteractie Bericht verplaatsen naar map Ongewenste e-mail of op de lijst met geblokkeerde afzenders in het postvak. Het uitschakelen van de regel voor ongewenste e-mail voorkomt dat berichten worden bezorgd in de map Ongewenste e-mail op basis van de lijst *met veilige afzenders* in het postvak.
    - Wanneer de regel voor ongewenste e-mail *is* uitgeschakeld in het postvak, kan EOP geen berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie spamfilter bericht verplaatsen naar map Ongewenste e-mail *of* de veilige lijstverzameling van het postvak.
    
- *Bulksgewijs compatibel niveau (BCL:* het bulksgewijs klachtniveau) van het bericht. Een hogere BCL geeft aan dat de kans groter is dat een bulkmailbericht klachten genereert (het natuurlijke resultaat als het e-mailbericht waarschijnlijk spam is).
    
- *Spam vertrouwelijkheidsniveau :* het betrouwbaarheidsniveau voor spam van het bericht. Hoe hoger de waarde, hoe groter de kans dat het bericht spam is.

- *Domeinnaam:* is de domeinnaam van de afzender.
    
- *Eigenaar van domein:* geeft de eigenaar van het verzendende domein aan.
    
- *Domeinlocatie:* geeft de locatie van het verzendende domein aan.
    
- *Datum van domein gemaakt:* geeft de aanmaakdatum van het verzendende domein aan. Een nieuw gemaakt domein is iets wat u voorzichtig kunt zijn als andere signalen verdacht gedrag aangeven.

*E-mailverificatie:* Methoden voor e-mailverificatie die door Microsoft 365 worden gebruikt, zijn SPF, DKIM en DMARC.

- Sender Policy Framework **(SPF):** beschrijft de resultaten van de SPF-controle voor het bericht. Mogelijke waarden zijn:
    - Pass (IP address): De SPF-controle op het doorgegeven bericht, inclusief het IP-adres van de afzender. De client wordt geautoriseerd e-mail te verzenden of door te sturen namens het domein van de afzender.
    - Fail (IP-adres): De SPF-controle op het bericht is mislukt en bevat het IP-adres van de afzender. Dit wordt ook wel een hard fail genoemd.
    - Softfail (reden): Met de SPF-record is de host aangewezen als niet toegestaan om te verzenden, maar is in overgang.
    - Neutraal: In de SPF-record wordt expliciet vermeld dat niet wordt vastgesteld of het IP-adres is geautoriseerd om te verzenden.
    - Geen: Het domein heeft geen SPF-record of de SPF-record levert geen resultaat op.
    - Temperror: Er is een tijdelijke fout opgetreden. Bijvoorbeeld een DNS-fout. Dezelfde controle kan mogelijk later wel worden uitgevoerd.
    - Permerror: Er is een permanente fout opgetreden. Het domein heeft bijvoorbeeld een foutief ingedeeld SPF-record.

- DomainKeys Identified Mail (**DKIM**):
    - Pass: Geeft aan dat de DKIM-controle op het doorgegeven bericht wordt doorgegeven.
    - Mislukt (reden): Hiermee wordt aangegeven dat de DKIM-controle op het bericht is mislukt en waarom. Bijvoorbeeld als het bericht niet is ondertekend of als de handtekening niet is gecontroleerd.
    - Geen: Hiermee wordt aangegeven dat het bericht niet is ondertekend. Dit kan al of niet betekenen dat het domein een DKIM-record heeft of dat het DKIM-record geen resultaat oplevert. Het betekent in elk geval dat dit bericht niet is ondertekend.

- Domain-based Message Authentication, Reporting and Conformance **(DMARC**):
    - Geslaagd: hiermee wordt de DMARC-controle op het doorgegeven bericht aangegeven.
    - Mislukt: geeft aan dat de DMARC-controle op het bericht is mislukt.
    - Bestguesspass: Hiermee wordt aangegeven dat er geen DMARC TXT-record bestaat voor het domein, maar als er een had bestaan, zou de DMARC-controle voor het bericht zijn doorgegeven.
    - Geen: Hiermee wordt aangegeven dat er geen DMARC TXT-record bestaat voor het verzendende domein in DNS.

*Samengestelde* verificatie: dit is een waarde die door Microsoft 365 wordt gebruikt om e-mailverificatie zoals SPF, DKIM en DMARC te combineren om te bepalen of het bericht echt is. Hierbij wordt het *van:-domein* van de e-mail gebruikt als basis voor evaluatie.
