---
title: Uw serviceaanbiedingen in Bookings vastleggen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Instructies voor het invoeren van serviceaanbiedingen, waaronder de servicenaam, beschrijving, locatie, duur en prijzen. U kunt ook de werknemers taggen die gekwalificeerd zijn om de service te bieden.
ms.openlocfilehash: 60b77633b9845b3c269f6773c1fb8a26256fbdc5
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419500"
---
# <a name="define-your-service-offerings-in-bookings"></a>Uw serviceaanbiedingen in Bookings vastleggen

Wanneer u uw serviceaanbiedingen opgeeft in Microsoft Bookings, kunt u de naam van een service, beschrijving, locatie opgeven (Kies of u wilt vergaderen of een onlinevergadering wilt hebben), de duur, standaard herinneringen voor klanten en medewerkers, de interne notities over de service en de prijzen. U kunt ook de werknemers taggen die gekwalificeerd zijn om de service te bieden. Wanneer klanten uw zakelijke website gaan raadplegen om een afspraak te boeken, kunnen ze precies zien welke soorten afspraken beschikbaar zijn, de persoon kiezen die de service wil bieden en hoeveel hun servicekosten kost.

U kunt ook aangepaste informatie en Url's toevoegen aan de e-mail bevestiging en de herinneringen die u verzendt wanneer iemand een dienst stuurt via de boekings pagina.

> [!NOTE]
> Bookings is standaard ingeschakeld voor klanten met de Microsoft 365 Business Standard Standard, Microsoft 365 a3 of Microsoft 365 A5-abonnementen. Bookings is ook beschikbaar voor klanten met Office 365 Enterprise E3 en Office 365 Enterprise E5, maar het is standaard uitgeschakeld. Als u aan de slag wilt gaan, raadpleegt [u toegang krijgen tot Microsoft Bookings](get-access.md). Zie [bookings in-of uitschakelen voor uw organisatie](turn-bookings-on-or-off.md)om bookings in of uit te schakelen.

## <a name="create-the-service-details"></a>De servicedetails maken

1. Ga naar de [pagina Services beheren](https://outlook.office.com/bookings/services) en selecteer **een service toevoegen**.

2. **Servicenaam**: Voer de naam van uw service in. Dit is de naam die wordt weergegeven in het vervolgkeuzemenu op de pagina agenda. Deze naam wordt ook weergegeven wanneer iedereen handmatig een afspraak op de pagina agenda plaatst, en deze wordt weergegeven als een tegel op de pagina selfservice.

3. **Beschrijving**: de beschrijving die u invoert, wordt weergegeven wanneer een gebruiker op het informatiepictogram op de pagina selfservice klikt.

4. **Standaardlocatie**: deze locatie wordt weergegeven in e-mailberichten voor de bevestiging en de herinneringen voor zowel personeel als klanten, en de agenda wordt weergegeven in de agendagebeurtenis die voor de reservering is gemaakt.

5. **Onlinevergadering toevoegen**: met deze instelling kunt u onlinevergaderingen voor elke afspraak, via teams of Skype, in-of uitschakelen, afhankelijk van welke optie u configureert als standaard-client voor het personeelslid.

    - Enabled

        - Een koppeling naar een team of Skype-vergadering, die uniek is voor de reservering, wordt toegevoegd aan de agendagebeurtenis op zowel de agenda's van de afdeling als de agenda van klanten, samen met inbel informatie.
        - De koppeling om deel te nemen aan de vergadering wordt toegevoegd aan alle e-mailberichten met bevestiging en herinneringen, zoals wordt weergegeven in het volgende voorbeeld:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Voorbeeld van koppeling om deel te nemen aan teams-vergadering in Bookings":::

        > [!NOTE]
        > Teams-vergaderingen kunnen deelnemen via de mobiele app teams, de bureaublad-app van teams, in een webbrowser of via de telefoon inbellen. U wordt ten zeerste aangeraden teams als de standaard onlinevergadering in te schakelen voor de Tenant, voor de beste manier om virtuele afspraken te reserveren.

    - Uitgeschakeld
        - Afspraken bevatten geen optie voor vergaderingen en alle velden die worden weergegeven wanneer u **onlinevergadering toevoegen** wordt ingeschakeld, worden niet weergegeven.

6. **Standaardduur**: Hiermee wordt aangegeven hoe lang alle vergaderingen worden geboekt. De tijd wordt geblokkeerd vanaf de begintijd, geselecteerd tijdens de reservering. De fulltime van de afspraak wordt geblokkeerd in de agenda's van het personeel.

7. **Buffer tijd voor uw klant kan niet boeken**: als u deze instelling inschakelt, wordt het toevoegen van extra tijd aan de agenda van het personeel telkens wanneer een afspraak wordt vastgelegd, toegestaan.

    De tijd wordt geblokkeerd in de agenda van het personeel en impact op de beschikbare beschikbaarheidsinfo. Dit betekent dat als een afspraak eindigt op 3:00 pm en de buffertijd van 10 minuten aan het einde van de vergadering is toegevoegd, de agenda van het personeel wordt weergegeven als bezet en niet-bookable tot 3:10pm. Dit kan handig zijn als uw staf tijd nodig heeft voordat een vergadering kan voorbereiden, zoals een dokter die de grafiek van een patiënten reviseert, of een financiële adviseur waarmee de informatie over de accounts wordt voorbereid. Het kan ook handig zijn na een vergadering, bijvoorbeeld wanneer iemand tijd nodig heeft om naar een andere locatie te reizen.

8. **Laat de klant de reserverings functie laten beheren**: met deze instelling wordt bepaald of de klant de reservering kan wijzigen of annuleren, mits deze via het tabblad Agenda op de web-app Bookings is opgenomen.

    - Enabled

        De knop **reservering beheren** wordt weergegeven op het bevestigingsbericht van de klant. Wanneer deze knop is geselecteerd voor de klant, worden drie opties weergegeven:
        - **Opnieuw plannen** Wanneer u deze optie inschakelt, wordt de gebruiker een service-specifieke selfservice pagina, waar ze een nieuwe tijd en/of datum voor dezelfde service kunnen selecteren en van de oorspronkelijke boeking. Houd er rekening mee dat er in de gebruikers ook wel een wijziging van het personeelslid moet worden gemaakt, ook al is het oorspronkelijke personeelslid bijgevoegd aan de opnieuw geplande reservering.
        - **Reservering annuleren** Hiermee annuleert u de boeking en verwijdert u deze uit de agenda van het personeel.
        - **Nieuwe reservering** Met deze optie wordt de gebruiker gecommuniceerd met alle services en medewerkers die worden weergegeven voor het plannen van een nieuwe boeking.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="De knop Bookings beheren in Bookings":::

        U wordt aangeraden deze instelling in te schakelen als u vertrouwd bent met klanten die toegang hebben tot de selfservice pagina.

    - Uitgeschakeld

        De gebruiker kan zijn of haar boeking niet opnieuw plannen of annuleren wanneer ze het tabblad agenda van de web-app Bookings opnemen. Wanneer u via de selfservice-pagina naar de volgende pagina gaat, hebben klanten echter nog steeds de knop **reserve functie beheren** en alle bijbehorende opties, zelfs als deze instelling is uitgeschakeld.

        U wordt aangeraden deze instelling uit te schakelen als u de toegang tot de selfservice pagina wilt beperken. Daarnaast wordt u aangeraden om tekst toe te voegen aan uw e-mailberichten voor bevestiging en herinneringen, zodat uw klanten u op een andere manier kunnen wijzigen, zoals door het bellen van de Office of het e-mailen van de helpdesk.

9. **Maximum aantal deelnemers per gebeurtenis** Met deze instelling kunt u services maken waarmee meerdere personen dezelfde afspraak tijd en dezelfde medewerkers kunnen boeken (zoals een fitness klasse). De tijdsduur van de afspraak voor de geselecteerde service, medewerkers en tijdstippen zijn beschikbaar voor de boekingsperiode, en de door u opgegeven maximum aantal deelnemers is bereikt. De capaciteit van de huidige afspraak en de deelnemers kunnen worden weergegeven op het tabblad agenda van de web-app bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Voorbeeld van het instellen van het maximum aantal deelnemers aan Bookings":::

10. **Standaardprijs**  Dit is de prijs die op de selfservice pagina wordt weergegeven. Als **prijs niet is ingesteld** , wordt er geen prijs of een verwijzing naar de kosten of prijzen weergegeven.

11. **Info** Dit veld wordt weergegeven in de boekings gebeurtenis voor vastgelegde medewerkers en de gebeurtenis die wordt weergegeven op het tabblad agenda van de Bookings-web-app.

12. **Aangepaste velden** In deze sectie kunnen vragen worden toegevoegd of verwijderd als de klant moet reageren op de juiste volgorde.

    - Klant-e-mail, telefoonnummer, adres en notities zijn niet-verwisselbare velden, maar u kunt ze optioneel maken door het selectievakje **vereist** naast elk veld te deselecteren.

    - U kunt een vraag voor meerdere keuze of tekst antwoorden toevoegen door **een vraag toevoegen**te selecteren.

        Aangepaste velden zijn handig voor het verzamelen van informatie die nodig is telkens wanneer een bepaalde afspraak wordt gereserveerd. Voorbeelden hiervan zijn verzekerings leveranciers voor een fraude bezoek, leningtype voor het aanbrengen van leningen, het belangrijkste onderzoek voor het adviseren van universiteiten of de kandidaat-ID voor functioneringsgesprekken.

13. **Herinneringen en bevestigingen** Beide soorten e-mails worden verzonden naar klanten, medewerkers of beide, op een bepaalde periode vóór de afspraak. U kunt voor elke afspraak meerdere berichten maken op basis van uw voorkeur.

    - Het standaard e-mailbericht met een bevestiging en een herinnering bevat basisinformatie over de afspraak, zoals de naam van de klant/klant, de naam van het personeelslid, de service of afspraak die is geboekt, en de tijd van de afspraak. Voor onlinevergaderingen wordt ook een koppeling naar deelnemen opgenomen. De mogelijkheid om de reservering te beheren, kan ook worden opgenomen als deze instelling is ingeschakeld (zoals hierboven is beschreven in stap 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Een bevestiging van reserve berichten via Bookings":::

    - U kunt eventueel ook eventuele extra tekst die u wilt gebruiken, zoals informatie over Herplannen of de klanten voor de afspraak opnemen. Hieronder ziet u een voorbeeld van de aangepaste tekst die is toegevoegd aan de oorspronkelijke bevestigings-e-mail, die wordt weergegeven in het veld **aanvullende informatie voor e-mail bevestiging** :

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Aanvullende informatie in de e-mail van een Bookings":::

14. **SMS-meldingen voor uw klant inschakelen** Als deze optie is geselecteerd, worden er SMS-berichten naar de klant verzonden, maar alleen als ze zich aanmelden.

    - Opt-in box op de paginahand matig reserveren en self-service:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Het vak opt-in voor bookings":::

    - SMS-meldingen ziet er als volgt uit (Houd er rekening mee dat SMS-meldingen momenteel alleen beschikbaar zijn in Noord-Amerika):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Een tekst melding van Bookings":::

15. **Opties voor publiceren** Kies of u deze service wilt weergeven als bookable op de pagina selfservice, of als u de service bookable alleen wilt maken op het tabblad agenda van de Bookings-web-app.

16. **Planningsbeleid** Met deze instelling wordt bepaald hoe tijden van afspraken worden weergegeven en met welke periode de afspraken kunnen worden gemaakt of geannuleerd.

17. **E-mail meldingen** Sets voor het verzenden van e-mailberichten naar organisatie medewerkers en voor klanten of klanten.

18. **Medewerkers** Als u dit selectievakje inschakelt, kunnen klanten of klanten een specifiek personeelslid voor hun afspraak kiezen.

    - Enabled

        Klanten kunnen kiezen uit alle medewerkers die zijn toegewezen aan de afspraak wanneer ze worden gereserveerd op de pagina selfservice. Als u de optie voor **iedereen** selecteert, kiest u in willekeurige volgorde een beschikbare personeels lid om de afspraak toe te wijzen.

    - Uitgeschakeld

        Klanten die via de selfservice pagina worden herboeken, kunnen een service en een tijd en datum selecteren. De beschikbare medewerkers worden op willekeurige wijze geboekt. Houd er rekening mee dat bepaalde medewerkers nog steeds kunnen worden geselecteerd wanneer ze worden geboekt via het tabblad Agenda in de web-app bookings.

19. **Beschikbaarheid** Met de volgende opties kunt u bepalen wanneer u de service kunt maken:

    - **Bookable wanneer personeel gratis zijn** Met de service wordt de beschikbaarheid bijgehouden op basis van het moment dat de medewerkers binnen kantooruren gratis zijn, zonder enige tijdsbeperkingen.

    - **Aangepaste uren (periodiek wekelijks)** De service heeft een extra beschikbaarheid die verder kan worden beperkt (naast de beperking van kantooruren of met personeels uren). Gebruik deze optie wanneer u de service alleen op een bepaald moment kunt op een bepaald moment aangeleverd of uitvoeren.

    - **Verschillende beschikbaarheid voor een datumbereik instellen** Met deze instelling wordt de beschikbaarheid beïnvloed op een bepaald moment, in plaats van periodieke basis. Dit kan bijvoorbeeld worden gebruikt wanneer een computer die nodig is voor de service tijdelijk wordt afgehandeld en niet beschikbaar is, of als een organisatie voor de feestdagen wordt afgesloten.

20. **Personeel toewijzen** Selecteer de medewerkers (mits u medewerkers hebt toegevoegd aan het tabblad medewerkers) die bookable voor die specifieke service. Als u het selectievakje inschakelt, worden alle medewerkers die aan de service zijn toegewezen, als resultaat gegeven.