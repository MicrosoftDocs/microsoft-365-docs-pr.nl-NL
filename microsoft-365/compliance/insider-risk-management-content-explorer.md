---
title: Insider risk management Content explorer
description: Meer informatie over insider risk management Content explorer in Microsoft 365
keywords: Microsoft 365, intern risicobeheer, risicobeheer, naleving
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3ff3c652d5446167ac3c2bf78a2405c21929ea11
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226465"
---
# <a name="insider-risk-management-content-explorer"></a>Insider risk management Content explorer

Met insider risk management **Content explorer** kunnen gebruikers die de rol Insider Risk *Management Investigators* hebben toegewezen, de context en details bekijken van inhoud die is gekoppeld aan activiteit in waarschuwingen. De casegegevens in Inhoudsverkenner worden dagelijks vernieuwd om nieuwe activiteiten op te nemen. Voor alle waarschuwingen die aan een zaak worden bevestigd, worden kopieën van gegevens en berichtbestanden gearchiveerd als momentopname in de tijd van de items, met behoud van de oorspronkelijke bestanden en berichten in de opslagbronnen. Indien nodig kunnen casegegevensbestanden worden geëxporteerd als een draagbaar documentbestand (PDF) of in de oorspronkelijke bestandsindeling.

Het kopiëren van gegevens en berichten is transparant voor de gebruiker die is gekoppeld aan de waarschuwing en aan de eigenaar van de inhoud. Voor nieuwe gevallen duurt het meestal ongeveer een uur voordat inhoud wordt ingevuld in Inhoudsverkenner. Voor gevallen met grote hoeveelheden inhoud kan het langer duren om een momentopname te maken. Als inhoud nog steeds wordt geladen in Inhoudsverkenner, ziet u een voortgangsindicator waarin het voltooiingspercentage wordt weergegeven.

In sommige gevallen zijn gegevens die aan een zaak zijn gekoppeld, mogelijk niet beschikbaar als momentopname voor controle in Inhoudsverkenner. Deze situatie kan optreden wanneer casegegevens zijn verwijderd of verplaatst of wanneer er een tijdelijke fout optreedt bij het verwerken van casegegevens. Als deze situatie zich voordoet, **selecteert** u Bestanden weergeven op de waarschuwingsbalk om de bestandsnamen, het bestandspad en de reden voor de fout voor elk bestand weer te geven. Indien nodig kan deze informatie worden geëxporteerd naar een .csv bestand (door komma's gescheiden waarden).

Als de inhoud machtigingen voor Information Rights Management bevat, worden deze machtigingen behouden voor de gekopieerde inhoud en hebben gebruikers die de rol Insider *Risk Management Investigators* hebben toegewezen deze machtigingen en rechten nodig als ze de bestanden moeten openen en bekijken. Aan elk bestand en bericht wordt automatisch een unieke bestands-id toegewezen in de insider risk management case voor beheerdoeleinden. Documenten die zijn gekoppeld aan apparaatindicatoractiviteiten, worden niet opgenomen in Inhoudsverkenner.

> [!NOTE]
> Inhoudsverkenner bevat activiteiten met betrekking tot Microsoft Office bestanden. Activiteiten op siteniveau, zoals wanneer een SharePoint site wordt verwijderd of als sitemachtigingen worden gewijzigd, worden niet opgenomen in Inhoudsverkenner.

## <a name="column-options"></a>Kolomopties

Om het voor risicoanalisten en onderzoekers gemakkelijker te maken om vastgelegde gegevens en berichten te bekijken en de context van de zaak te bekijken, worden verschillende filter- en sorteerhulpmiddelen opgenomen in de Inhoudsverkenner. Voor eenvoudige sortering ondersteunen de kolommen **Datum** **en** Bestandsklasse het sorteren met behulp van de kolomtitels in het inhoudswachtrijvenster. Andere wachtrijkolommen zijn beschikbaar om toe te voegen aan de weergave om verschillende draaitarijen op de bestanden en berichten te geven.

Als u kolomkoppen voor de inhoudswachtrij wilt toevoegen of verwijderen, gebruikt u **het** besturingselement Kolommen bewerken en selecteert u een van de volgende kolomopties. In deze kolommen worden de algemene voorwaarden voor de eigenschappen voor e-mail en document die in de Verkenner voor inhoud worden ondersteund en die later in dit artikel worden weergegeven, in kaart gebracht.

| **Kolomoptie** | **Beschrijving** |
|:------------------|:----------------|
| **Auteur** | Het auteursveld van Office documenten, dat blijft bestaan als een document wordt gekopieerd. Als een gebruiker bijvoorbeeld een document maakt en de e-mailberichten naar iemand anders die het vervolgens uploadt naar SharePoint, blijft de oorspronkelijke auteur behouden. |
| **BCC** | Beschikbaar voor e-mailberichten, de gebruikers in het BCC-berichtenveld. |
| **CC** | Beschikbaar voor e-mailberichten, de gebruikers in het berichtveld CC. |
| **Samengesteld pad** | Human readable path that describes the source of the item. |
| **Gespreks-id** | Gespreks-id van het bericht. |
| **Gespreksindex** | Gespreksindex uit het bericht. |
| **Aangemaakte tijd** | De tijd dat het bestand of het e-mailbericht is gemaakt. |
| **Datum (UTC)** | Voor e-mail is de datum waarop een bericht is ontvangen door een geadresseerde of verzonden door de afzender. Voor documenten is de datum waarop een document voor het laatst is gewijzigd. Date is in Coordinated Universal Time (UTC).|
| **Dominant thema** | Dominant thema zoals berekend voor analyse. |
| **E-mailset-id** | Groeps-id voor alle berichten in dezelfde e-mailset. |
| **Gezins-id** | Familie-id groeperen alle items; voor e-mail bevat deze kolom het bericht en alle bijlagen; voor documenten bevat deze kolom het document en eventuele ingesloten items. |
| **Bestandsklasse** | Voor inhoud van SharePoint en OneDrive: **Document**; voor inhoud van Exchange: **E-mail** of **Bijlage.** |
| **Bestands-id** | Documentaanduiding die uniek is in de zaak. |
| **Pictogram Bestandstype** | De uitbreiding van een bestand; bijvoorbeeld docx, one, pptx of xlsx. Dit veld is dezelfde eigenschap als de eigenschap FileExtension-site. |
| **ID** | De GUID-id voor het bestand. |
| **Onveranderlijke id** | Onveranderlijke id zoals opgeslagen in Office 365. |
| **Inclusief type** | Inclusief type berekend voor analyse: **0** - niet inclusief; **1** - inclusief; **2** - inclusief min; **3** - inclusief exemplaar. |
| **Laatst gewijzigd** | De datum waarop een document voor het laatst is gewijzigd. |
| **Gemarkeerd als representatief** | Eén document uit elke set exacte duplicaten wordt gemarkeerd als vertegenwoordigers. |
| **Type bericht** | Het type e-mailbericht dat u wilt zoeken. Mogelijke waarden: contactpersonen, documenten, e-mail, externe gegevens, faxen, chatberichten, logboeken, vergaderingen, microsoft-teams (retourneert items uit chats, vergaderingen en oproepen in Microsoft Teams), notities, berichten, RSS-feeds, taken, voicemail |
| **Deelnemers** | Lijst met alle deelnemers van een bericht; bijvoorbeeld Afzender, Aan, CC, BCC. |
| **Draaitabel-id** | De id van een draaipunt. |
| **Ontvangen** | De datum waarop een e-mailbericht is ontvangen door een geadresseerde. Dit veld is dezelfde eigenschap als de eigenschap Ontvangen e-mail. |
| **Geadresseerden** | Alle geadresseerdevelden in een e-mailbericht. Deze velden zijn Aan, CC en BCC. |
| **Representatieve id** | Numerieke id van elke set exacte duplicaten. |
| **Afzender** | De afzender van een e-mailbericht. |
| **Afzender/auteur** | Voor e-mail, de persoon die een bericht heeft verzonden. Voor documenten, de persoon die in het auteursveld wordt geciteerd uit Office documenten. U kunt meerdere namen typen, gescheiden door komma's. Twee of meer waarden zijn logisch verbonden door de operator OF. |
| **Gevoelige informatietypen** | De gevoelige informatietypen die zijn geïdentificeerd in inhoud. |
| **Gevoeligheidslabels** | De gevoeligheidslabels die op de inhoud zijn toegepast. |
| **Verzonden** | De datum waarop een e-mailbericht is verzonden door de afzender. Dit veld is dezelfde eigenschap als de eigenschap Verzonden e-mail. |
| **Grootte** | Voor zowel e-mail als documenten, de grootte van het item (in bytes). |
| **Onderwerp** | De tekst in de onderwerpregel van een e-mailbericht. |
| **Onderwerp/titel** | Voor e-mail wordt de tekst in de onderwerpregel van een bericht weergegeven. Voor documenten, de titel van het document. Zoals eerder uitgelegd, is de eigenschap Titel metagegevens die zijn opgegeven in Microsoft Office documenten. U kunt de naam van meer dan één onderwerp/titel typen, gescheiden door komma's. Twee of meer waarden zijn logisch verbonden door de operator OF. |
| **Lijst met thema's** | Lijst met thema's zoals berekend voor analyse. |
| **Title** | De titel van het document. De eigenschap Titel is metagegevens die zijn opgegeven in Office documenten. Deze is anders dan de bestandsnaam van het document. |
| **Naar** | De ontvanger van een e-mailbericht in het veld Aan. |

## <a name="filtering"></a>Filteren

U kunt een of meer filters gebruiken om het bereik van een zoekopdracht te beperken en een meer verfijnde set resultaten te retourneren. Als u een filter wilt instellen, **selecteert** u Filters boven aan de inhoudswachtrij. Veel filters bevatten extra filteropties om de resultaten van het filter te beperken. Het filter Datum *bevat bijvoorbeeld* besturingselementen voor het configureren van een *Begindatum* en *Einddatum* voor het **datumfilter.** Selecteer een of meer filteritems in de volgende categorieën:

### <a name="common-filters"></a>Veelgebruikte filters

| **Filteren** | **Beschrijving** |
|:---------------------|:----------------|
| **Datum (UTC)** | Voor e-mail is de datum waarop een bericht is ontvangen door een geadresseerde of verzonden door de afzender. Voor documenten is de datum waarop een document voor het laatst is gewijzigd. |
| **Afzender/auteur** | Voor e-mail, de persoon die een bericht heeft verzonden. Voor documenten, de persoon  die in het veld Auteur wordt geciteerd uit Office documenten. U kunt meerdere namen typen, gescheiden door komma's. |
| **Source** | De locatie van het document in uw organisatie. Bijvoorbeeld een specifieke locatie SharePoint site. |
| **Onderwerp/titel** | Voor e-mail wordt de tekst in de onderwerpregel van een bericht weergegeven. Voor documenten, de titel van het document. De eigenschap Titel in documenten is metagegevens die zijn opgegeven in Microsoft Office documenten. U kunt de naam van meer dan één onderwerp/titel typen, gescheiden door komma's. Twee of meer waarden zijn logisch verbonden door de operator OF. |

### <a name="email-filters"></a>E-mailfilters

| **Filteren** | **Beschrijving** |
|:---------------------|:----------------|
| **BCC** | Het veld BCC van een e-mailbericht. |
| **CC** | Het veld CC van een e-mailbericht. |
| **Heeft bijlage** | Geeft aan of een bericht een bijlage heeft. Waarden worden weergegeven als **waar** of **onwaar.** |
| **Is e-mailbijlage** | Als het document een bijlage is, wordt de waarde weergegeven als **Ja.** |
| **Is ingesloten document** | Als het document is ingesloten in het e-mailbericht, wordt de waarde weergegeven als **Ja.** |
| **Is inlinebijlage** | Als het document een inlinebijlage is in het e-mailbericht, wordt de waarde weergegeven als **Ja.** |
| **Deelnemers** | Alle personenvelden in een e-mailbericht. Deze velden zijn Van, Aan, CC en BCC. |
| **Ontvangen** | De datum waarop een e-mailbericht is ontvangen door een geadresseerde. |
| **Geadresseerdedomeinen** | Lijst met alle domeinen van geadresseerden van een bericht. |
| **Geadresseerden** | De geadresseerden van het e-mailbericht. |
| **Afzender** | Het veld Afzender (Van) voor berichttypen.  Notatie is **DisplayName. \<SmtpAddress>** |
| **Afzenderdomein** | Domein van de afzender. |
| **Naar** | Het veld Aan van een e-mailbericht. |
| **Uniek in e-mailset** | Onwaar als er een duplicaat van de bijlage in de e-mailset staat. |

## <a name="document-filters"></a>Documentfilters

| **Filters** | **Beschrijving** |
|:---------------------|:----------------|
| **Compliancelabels** | Nalevingslabels die in Office 365. |
| **Aangemaakte tijd (UTC)** | De datum en tijd waarop het bestand of het e-mailbericht is gemaakt. De datum en tijd zijn in Coordinated Universal Time (UTC). |
| **Laatst gewijzigde datum (UTC)** | De datum waarop een document voor het laatst is gewijzigd. De datum en tijd zijn in Coordinated Universal Time (UTC). |
| **Bestandsextensie** | Het extensietype van het bestand. |
| **Gebeurtenissen in gebruikersactiviteit** | Activiteit voor items die betrekking hebben op specifieke gebruikersactiviteit in een zaak.  Als u bijvoorbeeld een koppeling naar 'Inhoud verkennen'  selecteert voor een activiteit op de pagina Gebruikersactiviteit van een zaak, wordt dit filter gebruikt om items weer te geven die betrekking hebben op die activiteit. |
| **Werkproduct** | Het type werkproduct voor het document. Bijvoorbeeld aantekeningen of tags in het document. |
