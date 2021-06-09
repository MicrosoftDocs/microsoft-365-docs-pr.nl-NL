---
title: Uw serviceaanbiedingen definiëren in Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Instructies voor het invoeren van serviceaanbiedingen, waaronder servicenaam, beschrijving, locatie, duur en prijzen. U kunt ook de werknemers taggen die gekwalificeerd zijn om de service te bieden.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962535"
---
# <a name="define-your-service-offerings-in-bookings"></a>Uw serviceaanbiedingen definiëren in Bookings

Wanneer u uw serviceaanbiedingen in Microsoft Bookings definieert, stelt u een servicenaam, beschrijving, locatie in (kies of u persoonlijk wilt vergaderen of een onlinevergadering wilt houden), duur, standaardherinneringen aan klanten en personeel, interne notities over de service en prijzen. U kunt ook de werknemers taggen die gekwalificeerd zijn om de service te bieden. Wanneer klanten vervolgens naar uw zakelijke website komen om een afspraak te boeken, kunnen ze precies zien welke soorten afspraken beschikbaar zijn, de persoon kiezen die ze de service willen leveren en hoeveel hun service kost.

U kunt ook aangepaste informatie en URL's toevoegen aan de e-mailbevestiging en herinneringen die u verzendt wanneer iemand een service boekt via uw boekingspagina.

## <a name="create-the-service-details"></a>De servicedetails maken

1. Ga naar de [pagina Services beheren](https://outlook.office.com/bookings/services) en selecteer Een service **toevoegen.**

2. **Servicenaam:** voer de naam van uw service in. Dit is de naam die wordt weergegeven in de vervolgkeuzelijst op de pagina Agenda. Deze naam wordt ook weergegeven wanneer iemand handmatig een afspraak toevoegt op de pagina Agenda en deze wordt weergegeven als een tegel op de pagina Selfservice.

3. **Beschrijving:** De beschrijving die u op geeft, wordt weergegeven wanneer een gebruiker op het informatiepictogram op de pagina Selfservice klikt.

4. **Standaardlocatie:** Deze locatie wordt weergegeven op bevestigings- en herinneringsberichten voor zowel personeel als klanten en deze wordt weergegeven in de agendagebeurtenis die voor de reservering is gemaakt.

5. **Onlinevergadering** toevoegen: met deze instelling kunt u onlinevergaderingen in- of uitschakelen voor elke afspraak, via Teams of Skype, afhankelijk van welke u configureert als de standaardclient voor het personeelslid.

    - Ingeschakeld:

        - Een koppeling naar een Teams- of Skype-vergadering, uniek voor de reservering, wordt toegevoegd aan de agendagebeurtenis in zowel de agenda's van het personeel als de agenda's van de klanten, samen met inbelgegevens.
        - De koppeling om deel te nemen aan de vergadering wordt toegevoegd aan alle bevestigings- en herinnerings-e-mailberichten, zoals wordt weergegeven in het volgende voorbeeld:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Voorbeeld van koppeling om deel te nemen Teams vergadering in Bookings":::

        > [!NOTE]
        > Teams vergaderingen kunnen worden samengevoegd via de Teams mobiele app, de Teams desktop-app, in een webbrowser of via de telefoon inbeltoepassing. We raden u ten zeerste aan Teams als de standaard onlinevergaderingsservice voor uw tenant in te stellen voor de beste ervaring bij het maken van virtuele afspraken.

    - Uitgeschakeld:
        - Afspraken bevatten geen optie voor een vergadering en alle vergadervelden die worden weergegeven wanneer **Onlinevergadering** toevoegen is ingeschakeld, worden niet weergegeven.

6. **Standaardduur:** dit is hoe lang alle vergaderingen worden geboekt. De tijd wordt geblokkeerd vanaf de begintijd, die tijdens de reservering is geselecteerd. De volledige afspraaktijd wordt geblokkeerd in de agenda's van het personeel.

7. **Buffertijd die uw klant** niet kan boeken: Als u deze instelling inschakelen, kunt u extra tijd toevoegen aan de agenda van het personeel telkens als er een afspraak wordt geboekt.

    De tijd wordt geblokkeerd in de agenda van het personeel en de vrije/drukke informatie beïnvloeden. Dit betekent dat als een afspraak eindigt om 15:00 uur en 10 minuten buffertijd is toegevoegd aan het einde van de vergadering, de agenda van het personeel wordt als bezet en niet-boekbaar tot 15:10 uur. Dit kan handig zijn als uw personeel tijd nodig heeft voor de voorbereiding van een vergadering, zoals een arts die de grafiek van een patiënt bekijkt of een financieel adviseur die relevante accountgegevens voorbereidt. Het kan ook handig zijn na een vergadering, bijvoorbeeld wanneer iemand tijd nodig heeft om naar een andere locatie te reizen.

8. **De klant de** reservering laten beheren: deze instelling bepaalt of de klant zijn of haar reservering kan wijzigen of annuleren, mits deze is geboekt via het tabblad Agenda in de Bookings Web-app.

    - Ingeschakeld:

        De **knop Reservering beheren** wordt weergegeven in het bevestigingsbericht van de klant. Wanneer deze knop is geselecteerd door de klant, worden drie opties weergegeven:
        - **Opnieuw plannen** Als u deze optie selecteert, gaat de gebruiker naar een servicespecifieke Self-Service-pagina, waar hij/zij een nieuwe tijd en/of datum voor dezelfde service en hetzelfde personeelslid uit de oorspronkelijke reservering kan selecteren. Hoewel het oorspronkelijke personeelslid standaard is gekoppeld aan de nieuwe reservering, kan de gebruiker het personeelslid ook wijzigen.
        - **Reservering annuleren** Hiermee wordt de reservering geannuleerd en uit de agenda van het personeel verwijderd.
        - **Nieuwe reservering** Deze optie brengt de gebruiker naar de Self-Service pagina met alle services en personeelsleden die worden vermeld, voor het plannen van een nieuwe reservering.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="De knop Boekingen beheren in Bookings":::

        We raden u alleen aan deze instelling ingeschakeld te laten als u tevreden bent met klanten die toegang hebben tot de Self-Service pagina.

    - Uitgeschakeld:

        De gebruiker kan zijn reservering niet opnieuw plannen of annuleren wanneer hij of zij via het tabblad Agenda in de Bookings Web-app boekt. Bij het boeken via Self-Service pagina hebben klanten echter  nog steeds de knop Reservering beheren en alle opties, zelfs wanneer deze instelling is uitgeschakeld.

        U wordt aangeraden deze instelling uit te zetten als u de toegang tot de Self-Service wilt beperken. Daarnaast raden we aan om tekst toe te voegen aan uw bevestigings- en herinnerings-e-mailberichten waarin uw klanten worden verteld hoe ze hun reservering op een andere manier kunnen wijzigen, bijvoorbeeld door het kantoor te bellen of een e-mail te sturen naar de helpdesk.

9. **Maximum aantal deelnemers per gebeurtenis** Met deze instelling kunt u services maken waarvoor meerdere personen dezelfde afspraaktijd en hetzelfde personeel (zoals een fitnessklasse) moeten kunnen boeken. De tijdsleuf voor de geselecteerde service, personeel en tijd is beschikbaar om te boeken totdat het maximum aantal deelnemers, dat door u is opgegeven, is bereikt. De huidige afspraakcapaciteit en deelnemers kunnen worden weergegeven op het tabblad Agenda in de Bookings Web-app.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Voorbeeld van het instellen van maximale deelnemers in Bookings":::

10. **Standaardprijs**  Dit is de prijs die wordt weergegeven op de Self-Service pagina. Als **Prijs niet is** ingesteld, wordt er geen prijs of verwijzing naar kosten of prijzen weergegeven.

11. **Notities** Dit veld wordt weergegeven in de reserveringsgebeurtenis voor geboekt personeel, evenals op de gebeurtenis die wordt weergegeven op het tabblad Agenda in de web-app Bookings.

12. **Aangepaste velden** In deze sectie kunnen vragen worden toegevoegd of verwijderd als de klant een vraag moet beantwoorden om te kunnen boeken.

    - E-mail, telefoonnummer, adres en notities van klanten zijn niet-verwisselbare velden, maar u kunt ze optioneel maken door **Vereist** naast elk veld te deselecteren.

    - U kunt een vraag met meerdere keuze of tekst beantwoorden toevoegen door **Een vraag toevoegen te selecteren.**

        Aangepaste velden kunnen handig zijn bij het verzamelen van gegevens die nodig zijn telkens wanneer de specifieke afspraak wordt geboekt. Voorbeelden hiervan zijn verzekeringsprovider vóór een bezoek aan de kliniek, leningstype voor leningsoverleg, hoofdstudie voor academische advisering of sollicitant-id voor sollicitatiegesprekken.

13. **Herinneringen en bevestigingen** Beide typen e-mailberichten worden verzonden naar klanten, personeelsleden of beide, binnen een bepaalde periode vóór de afspraak. Er kunnen meerdere berichten worden gemaakt voor elke afspraak, afhankelijk van uw voorkeur.

    - De standaardbevestigings- en herinneringsberichten bevatten basisinformatie over de afspraak, zoals de naam van de klant/klant, de naam van het personeelslid, de service of afspraak die is geboekt en het tijdstip van de afspraak. Voor onlinevergaderingen wordt ook een koppeling opgenomen om deel te nemen. De mogelijkheid om de reservering te beheren kan ook worden opgenomen, als deze instelling is ingeschakeld (zoals hierboven beschreven in stap 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Een bevestigingsmail van Bookings":::

    - Desgewenst kunt u hier eventuele aanvullende tekst opnemen die u wilt gebruiken, zoals informatie over het opnieuw plannen of wat klanten moeten meenemen voor de afspraak. Hieronder ziet u een voorbeeld van aangepaste tekst die is toegevoegd aan de oorspronkelijke bevestigings-e-mail, te zien in het veld **Aanvullende informatie voor e-mailbevestiging:**

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Aanvullende informatie in een e-mail van Bookings":::

14. **Sms-meldingen voor uw klant inschakelen** Als geselecteerd, Sms berichten naar de klant worden verzonden, maar alleen als ze zich hebben aanmeld.

    - Opt-in box on the manual booking and Self-Service Page:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Het opt-in vak in Bookings":::

    - Sms-meldingen zien er als volgt uit (houd er rekening mee dat Sms zijn momenteel alleen beschikbaar in Noord-Amerika):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Een tekstmelding van Bookings":::

15. **Publicatieopties** Kies of deze service moet worden weergegeven als boekbaar op de pagina Self-Service of dat de service alleen kan worden geboekt op het tabblad Agenda in de Bookings Web-app.

16. **Planningsbeleid** Deze instelling bepaalt hoe afspraaktijden worden bekeken en de periode waarin boekingen kunnen worden gemaakt of geannuleerd.

17. **E-mailmeldingen** Hiermee stelt u in wanneer e-mailberichten worden verzonden naar medewerkers van de organisatie en naar klanten of klanten.

18. **Personeel** Als u dit selectievakje incheckt, kunnen klanten of klanten een specifiek personeelslid kiezen voor hun afspraak.

    - Ingeschakeld:

        Klanten kunnen kiezen uit alle personeelsleden die aan de afspraak zijn toegewezen bij het boeken op de Self-Service pagina. Als u de optie **Iedereen selecteert,** kiest Bookings willekeurig een beschikbaar personeelslid om aan de afspraak toe te wijzen.

    - Uitgeschakeld:

        Klanten die via de pagina Self-Service kunnen een service en een tijd en datum selecteren. Het beschikbare personeel wordt willekeurig geboekt. Houd er rekening mee dat specifieke personeelsleden nog steeds kunnen worden geselecteerd wanneer ze zijn geboekt via het tabblad Agenda in de Bookings Web-app.

19. **Beschikbaarheid** De volgende opties bepalen wanneer de service kan worden geboekt:

    - **Boekbaar wanneer het personeel vrij is** De service behoudt de beschikbaarheid op basis van het tijdstip waarop het personeel binnen werkdagen vrij is, zonder extra tijdsbeperkingen.

    - **Aangepaste uren (wekelijks terugkerende uren)** De service heeft een extra laag beschikbaarheid die verder kan worden beperkt (naast het beperken van de werkuren of de personeelsuren). Gebruik deze optie wanneer uw service alleen op een bepaald moment kan worden geleverd of uitgevoerd.

    - **Verschillende beschikbaarheid voor een datumbereik instellen** Deze instelling is van invloed op de beschikbaarheid op een bepaald tijdstip, in plaats van op een terugkerende basis. Dit kan bijvoorbeeld worden gebruikt wanneer een machine die nodig is voor de service tijdelijk wordt gebruikt en niet beschikbaar is, of wanneer een organisatie is gesloten voor een feestdag.

20. **Personeel toewijzen** Selecteer het personeel (mits u personeelsleden hebt toegevoegd aan het tabblad Personeel) die voor die specifieke service kunnen worden geboekt. Als u geen individueel personeel selecteert, worden alle personeelsleden toegewezen aan de service.