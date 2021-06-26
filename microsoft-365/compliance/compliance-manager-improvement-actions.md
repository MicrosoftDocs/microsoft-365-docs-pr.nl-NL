---
title: Verbeteracties toewijzen en voltooien in Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het uitvoeren van implementatie en testen van besturingselementen in Microsoft Compliance Manager. Werk toewijzen, documentatie opslaan en rapporten exporteren.
ms.openlocfilehash: f2674e24ed38362c5c7563a574e0dba9c81f2584
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149032"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Verbeteracties toewijzen en voltooien in Compliance Manager

**In dit artikel:** In dit artikel wordt uitgelegd hoe u **uw compliancewerkstroom kunt beheren** met verbeteracties. Meer informatie over het **toewijzen van verbeteracties** voor implementatie en testen, **het beheren van updates** en het exporteren van **rapporten.**

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Compliancewerkstromen beheren met verbeteracties

Verbeteracties centraliseren uw complianceactiviteiten. Elke verbeteringsactie biedt gedetailleerde implementatie-richtlijnen om u te helpen bij het afstemmen op de regelgeving en standaarden voor gegevensbescherming. Acties kunnen worden toegewezen aan gebruikers in uw organisatie om implementatie- en testwerk uit te voeren. U kunt ook documentatie, notities en statusupdates opnemen in de actie.

Al uw verbeteracties worden weergegeven op de pagina verbeteracties. Meer informatie over het [bekijken van uw verbeteracties.](compliance-manager-setup.md#improvement-actions-page)

## <a name="improvement-actions-details-page"></a>Pagina Met details van verbeteracties

Elke verbeteringsactie heeft een detailpagina met de huidige status, de bijbehorende standaarden en wettelijke vereisten en aanbevolen implementatie-richtlijnen. [Technische acties](compliance-score-calculation.md#technical-and-non-technical-actions) omvatten een **koppeling Nu starten** die u naar de juiste oplossing voor implementatie brengt. U kunt implementatie- en testdocumentatie rechtstreeks toevoegen aan de detailspagina van een verbeteractie.

De detailspagina van een verbeteringsactie weergeven:

1. Ga naar de pagina verbeteracties.
2. Selecteer de rij van de beoogde verbeteringsactie, waarmee de detailspagina wordt geopend.

U kunt de volgende of vorige verbeteringsactie in de lijst eenvoudig bekijken door de pijl-omhoog of pijl-omlaag in de rechterbovenhoek van het scherm te selecteren. Als u de lijst hebt gefilterd op de pagina verbeteracties, gaat u met omhoog of omlaag naar het volgende item in die gefilterde lijst.

## <a name="assign-improvement-actions"></a>Verbeteracties toewijzen

Als u wilt beginnen met de implementatie van een verbeteringsactie, kunt u het werk zelf uitvoeren of aan een andere gebruiker toewijzen. De toegewezen persoon kan het volgende zijn:

- Een eigenaar van bedrijfsbeleid
- Een IT-medewerker die verantwoordelijk is voor implementaties
- Een andere werknemer die verantwoordelijk is voor het uitvoeren van de taak

Nadat u de juiste toegewezene hebt aangewezen, moet u ervoor zorgen dat deze een voldoende [compliancemanagerrol](compliance-manager-setup.md#set-user-permissions-and-assign-roles) heeft om het werk uit te voeren. Volg vervolgens de onderstaande stappen om de verbeteringsactie toe te wijzen:

1. Selecteer op de pagina Details van verbeteracties **de optie Status bewerken** in de linkerbovenhoek van het scherm.

2. Schakel in het flyoutvenster Status bewerken het vak **Toegewezen aan** in om een **lijst** met voorgestelde personen met gebruikers weer te geven. U kunt de gebruiker selecteren in de lijst of het e-mailadres typen van de persoon aan wie u deze wilt toewijzen.

3. Selecteer **Opslaan en sluiten.** De toegewezen gebruiker ontvangt een e-mail waarin wordt uitgelegd dat de verbeteringsactie aan de gebruiker is toegewezen, met een directe koppeling naar de verbeteringsactie. 
> [!NOTE]
> Klanten van de Amerikaanse overheidsgemeenschap (GCC) High and Department of Defense (DoD) ontvangen geen e-mail wanneer er verbeteringsacties aan hen zijn toegewezen.

De toegewezen gebruiker kan vervolgens de aanbevolen acties uitvoeren.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Meerdere verbeteracties aan één gebruiker toewijzen

U kunt meerdere verbeteracties aan één gebruiker toewijzen door de volgende stappen uit te voeren:

1. Ga naar de pagina Acties voor verbetering.
2. Selecteer het gebied links van de naam van de verbeteringsactie. Er wordt een pictogram voor ronde controle weergegeven dat aangeeft dat u die actie hebt geselecteerd. Controleer alle acties die u wilt toewijzen.
3. Selecteer de **koppeling Toewijzen aan gebruiker** boven aan de tabel verbeteracties.
4. Er wordt een pop-upvenster weergegeven. Typ in het veld **Toewijzen** aan de naam van de persoon aan wie u de acties wilt toewijzen. U kunt ook selecteren in de lijst met voorgestelde personen.
5. Nadat u het veld **Toewijzen** aan hebt ingevuld met de naam van de toegewezene, selecteert u **Toewijzen**.
6. Vervolgens ziet u de pagina Verbeteracties met de nieuwe toegewezene voor de acties die u zojuist hebt toegewezen.

## <a name="perform-work-and-store-documentation"></a>Werk en opslagdocumentatie uitvoeren

U kunt bestanden en notities met betrekking tot implementatie- en testwerk rechtstreeks uploaden naar de **sectie Notities en documentatie.** Deze omgeving is een veilige, gecentraliseerde opslagplaats om u te helpen aantonen dat u tevreden bent over besturingselementen om te voldoen aan nalevingsstandaarden en -voorschriften. Elke gebruiker met alleen-lezen toegang kan inhoud lezen in deze sectie. Alleen gebruikers met bewerkingsrechten kunnen bestanden uploaden en downloaden en notities invoeren of bewerken.

De **sectie Notities en documentatie** bevat velden voor geüploade documenten, implementatienotities, testnotities en aanvullende notities.

#### <a name="uploaded-documents"></a>Geüploade documenten

- Selecteer **Documenten beheren om** relevante bestanden te uploaden.
- Wanneer het flyoutvenster Documenten beheren wordt geopend, **selecteert** u Document toevoegen en selecteert u het bestand in uw systeem. Geaccepteerde bestandstypen:
    - Documenten (.doc, .xls, .ppt, .txt, .pdf)
    - Afbeeldingen (.jpg, .png)
    - Video (.mkv)
    - Gecomprimeerde bestanden (.zip, .rar)
- Wanneer het bestand is opgelost in het deelvenster, selecteert u **Sluiten,** waardoor de bestandsbijlage automatisch wordt opgeslagen. Vervolgens ziet u het bestand onder Geüploade **documenten.**
- Als u het document wilt downloaden of verwijderen, **selecteert** u Documenten beheren onder de lijst met documenten. Selecteer in het deelvenster Flyout de documentrij om deze te markeren en selecteer **vervolgens Downloaden** of **Verwijderen.**

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Implementatienotities, testnotities en aanvullende notities

- Als u notities wilt toevoegen in een van deze drie velden, selecteert u **Implementatienotities bewerken** onder een van deze velden.
- Wanneer het flyoutvenster wordt geopend, voert u notities in het tekstveld in en selecteert u **Opslaan en sluiten.**
- Als u notities wilt bewerken, selecteert u **Implementatienotities bewerken,** maakt u uw bewerkingen en selecteert u **Opslaan en sluiten.**

Er is geen tekenlimiet in de notitievelden. We raden u aan notities kort te houden, zodat u ze eenvoudig kunt bekijken en bewerken vanaf de pagina details van de verbeteracties.

## <a name="change-improvement-action-status"></a>Actiestatus voor verbetering wijzigen

U kunt voor elke verbeteringsactie de implementatiestatus en -datum en de teststatus en -datum registreren. De **implementatie-** **en teststatusvelden** kunnen worden bewerkt door elke gebruiker met bewerkingsmachtigingen, niet alleen door de toegewezen persoon.

Als u de status van een verbeteringsactie wilt bewerken, **selecteert** u Status bewerken in de linkerbovenhoek van de detailspagina. Hieronder vindt u de beschikbare velden en statusopties:

- **Implementatiestatus**
    - **Niet geïmplementeerd** - actie nog niet geïmplementeerd
    - **Geïmplementeerd -** actie geïmplementeerd
    - **Alternatieve implementatie:** selecteer deze optie als u andere hulpprogramma's van derden hebt gebruikt of andere acties hebt uitgevoerd die niet zijn opgenomen in Microsoft-aanbevelingen
    - **Gepland-** actie is gepland voor implementatie
    - **Buiten bereik:** actie is niet relevant voor uw organisatie en draagt niet bij aan uw score
- **Implementatiedatum:** beschikbaar om te selecteren wanneer de implementatiestatus is 'geïmplementeerd' of 'alternatieve implementatie'.
- **Teststatus:** beschikbaar om te selecteren wanneer de implementatiestatus wordt 'geïmplementeerd' of 'alternatieve implementatie':
    - **Niet beoordeeld:** de actie is nog niet getest
    - **Geslaagd** : de implementatie is geverifieerd door een beoordelaar
    - **Mislukt laag risico-** testen mislukt, laag risico
    - **Mislukt gemiddeld risico:** testen mislukt, gemiddeld risico
    - **Mislukt hoog risico:** testen mislukt, hoog risico
    - **Buiten bereik:** de actie valt buiten het bereik van de beoordeling en draagt niet bij aan uw score
- **Testdatum:** door de pop-up van de agenda schakelen om de datum te selecteren

Veelvoorkomende acties worden in groepen gesynchroniseerd. Wanneer twee verschillende beoordelingen in dezelfde groep verbeteracties delen die door u worden beheerd, worden eventuele updates die u aan de implementatiedetails of status van een actie aanneemt, automatisch gesynchroniseerd met dezelfde actie in een andere beoordeling in de groep. Met deze synchronisatie kunt u één verbeteringsactie implementeren en aan verschillende vereisten in meerdere voorschriften voldoen.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Verbeteractie toewijzen aan beoordelaar voor voltooiing

Nadat u het werk hebt voltooid, tests hebt uitgevoerd en bewijs hebt geüpload, is de volgende stap het toewijzen van de verbeteringsactie aan een beoordelaar voor validatie. De beoordelaar valideert het werk en bekijkt de documentatie en selecteert de juiste teststatus.

**Als de teststatus is ingesteld op 'Geslaagd':** de actie is voltooid en de behaalde punten geven de maximale punten weer die zijn bereikt. De punten worden vervolgens meegetelde voor de algehele nalevingsscore.

**Als de teststatus is** ingesteld op 'Mislukt': de actie voldoet niet aan de vereisten en de beoordelaar kan deze terug toewijzen aan de juiste gebruiker voor extra werk.

## <a name="accepting-updates-to-improvement-actions"></a>Updates voor verbeteracties accepteren

Wanneer een update beschikbaar is voor een verbeteringsactie, ziet u een melding naast de naam. U kunt de update accepteren of deze later uitstellen.

#### <a name="what-causes-an-update"></a>Wat is de oorzaak van een update

Er vindt een update plaats wanneer er wijzigingen zijn met betrekking tot score, automatisering of bereik. Wijzigingen kunnen leiden tot nieuwe richtlijnen voor verbeteringsacties op basis van wijzigingen in de regelgeving of kunnen het gevolg zijn van productwijzigingen. Alleen de verbeteracties die door uw organisaties worden beheerd, ontvangen updatemeldingen.

#### <a name="where-youll-see-assessment-update-notifications"></a>Waar u meldingen voor evaluatieupdates ziet

Wanneer een verbeteringsactie wordt bijgewerkt,  ziet u een updatelabel in behandeling naast de naam ervan op de pagina verbeteracties en op de detailspagina van de bijbehorende evaluaties.

Ga naar de detailspagina van de verbeteringsactie en selecteer de knop **Update** controleren in de bovenste banner om details over de wijzigingen te bekijken en de update te accepteren of uit te stellen.

#### <a name="review-update-to-accept-or-defer"></a>Update controleren om te accepteren of uit te stellen

Nadat u **Update controleren hebt** geselecteerd op de pagina Met de details van de actie voor de verbetering, wordt aan de rechterkant van het scherm een flyoutvenster weergegeven. Het deelvenster Flyout bevat belangrijke details over de update, zoals de beoordelingen die van invloed zijn en wijzigingen in de score en het bereik.

Selecteer **Update accepteren** om alle wijzigingen in de verbeteringsactie te accepteren. **Geaccepteerde wijzigingen zijn permanent.**

> [!NOTE]
> Wanneer u een update voor een actie accepteert, accepteert u ook updates voor andere versies of exemplaren van deze actie. Updates worden verspreid over de hele tenant voor technische acties en de groep wordt verspreid voor niet-technische acties.

Als u **Annuleren selecteert,** wordt de update niet toegepast op de verbeteringsactie. U blijft echter de melding In behandeling bij **de update** zien totdat u de update accepteert.

**Waarom wordt u aangeraden updates te accepteren**

Als u updates accepteert, hebt u de meest bijgewerkte richtlijnen voor het gebruik van oplossingen en kunt u passende verbeteracties uitvoeren om te voldoen aan de vereisten van de certificering.

**Waarom u een update mogelijk wilt uitstellen**

Als u bezig bent met het voltooien van een evaluatie die de verbeteringsactie bevat, kunt u ervoor zorgen dat u klaar bent met het werk voordat u de update accepteert. U kunt de update voor een later tijdstip uitstellen door Annuleren **te selecteren** in het flyoutvenster revisieupdate.

#### <a name="accept-all-updates-at-once"></a>Alle updates tegelijk accepteren

Als u meerdere updates hebt en ze allemaal tegelijk wilt accepteren, selecteert u de koppeling Alle **updates** accepteren boven aan de tabel verbeteracties. Er wordt een flyoutvenster weergegeven met het aantal acties dat moet worden bijgewerkt. Selecteer de **knop Updates accepteren** om alle updates toe te passen.

Wanneer u terugkeert naar de pagina met verbeteracties, ziet u mogelijk een bericht boven aan de pagina waarin u wordt gevraagd de pagina te vernieuwen om de updates te kunnen uitvoeren.

## <a name="export-a-report"></a>Een rapport exporteren

Selecteer **Exporteren** in de linkerbovenhoek van het scherm om een Excel te downloaden met al uw verbeteracties en de filtercategorieën die worden weergegeven op de pagina verbeteracties.