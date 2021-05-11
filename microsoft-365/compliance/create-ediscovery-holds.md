---
title: EDiscovery-ophoudt in een core eDiscovery-zaak maken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: U kunt een hold maken die is gekoppeld aan een Core eDiscovery-zaak in Microsoft 365 om inhoud te behouden die relevant is voor een onderzoek of een juridische zaak.
ms.openlocfilehash: 61bbe2e8d2713c2960105e2ec4eb4beffcd4306e
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311607"
---
# <a name="create-an-ediscovery-hold"></a>Een eDiscovery-greep maken

U kunt een Hoofd-eDiscovery-zaak gebruiken om bewaar bewaart inhoud te maken die mogelijk relevant is voor de zaak. U kunt de postvakken van Exchange en OneDrive voor Bedrijven accounts van personen die u in de zaak onderzoekt, in de wacht zetten. U kunt ook een wacht houden op de postvakken en sites die zijn gekoppeld aan Microsoft Teams, Office 365 Groepen en Yammer Groepen. Wanneer u inhoudslocaties in de wacht zet, blijft inhoud behouden totdat u de inhoudslocatie uit de wacht houdt of totdat u de bewaarplaats verwijdert.

Nadat u een eDiscovery-greep hebt aan maken, kan het tot 24 uur duren voordat de wacht wordt in werking treedt.

Wanneer u een hold maakt, hebt u de volgende opties voor het bereik van de inhoud die is bewaard op de opgegeven inhoudslocaties:
  
- Maak een oneindige greep waarin alle inhoud op de opgegeven locaties in de wacht wordt geplaatst. U kunt ook een op query's gebaseerde wachtplaats maken waarbij alleen de inhoud op de opgegeven locaties die overeenkomt met een zoekquery, in de wacht wordt geplaatst.

- Geef een datumbereik op om alleen de inhoud te behouden die binnen dat datumbereik is verzonden, ontvangen of gemaakt. U kunt ook alle inhoud op opgegeven locaties houden, ongeacht wanneer deze is verzonden, ontvangen of gemaakt.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Een eDiscovery-wacht houden maken

Ga als volgende te werk om een eDiscovery-wacht te maken die is gekoppeld aan een Core eDiscovery-zaak:
  
1. Ga naar en meld u aan met de referenties voor gebruikersaccount die zijn toegewezen aan de juiste [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-machtigingen.

2. Klik in het linkernavigatiedeelvenster van Microsoft 365 compliancecentrum op Alles weergeven **en** klik vervolgens op **eDiscovery > Core.**

3. Klik op **de pagina Core eDiscovery** op de naam van de zaak waarin u de wacht wilt houden.

4. Klik op **de startpagina** voor de zaak op het **tabblad** Ingedrukt houden.
  
5. Klik op **de pagina** Wacht op **Maken.**

6. Geef op **de pagina Naam van** de wizard Uw wacht ingedrukt houden een naam op en voeg een optionele beschrijving toe en klik op **Volgende.** De naam van de wacht moet uniek zijn in uw organisatie.

7. Kies op **de wizard** Locaties kiezen de inhoudslocaties die u in de wacht wilt zetten. U kunt postvakken, sites en openbare mappen in de wacht zetten.

    ![De inhoudslocaties kiezen die u in de wacht wilt zetten](../media/eDiscoveryHoldLocations.png)
  
   1. **Exchange postvakken:** Stel de schakelknop in op **Aan** en klik vervolgens op **Gebruikers,** groepen of teams kiezen om op te geven welke postvakken in de wacht moeten worden gezet. Gebruik het zoekvak om gebruikerspostvakken en distributiegroepen te zoeken (om de postvakken van groepsleden in de wacht te zetten) om deze in de wacht te zetten. U kunt ook het bijbehorende postvak in de wacht zetten voor een Microsoft-team, Office 365 Groep en Yammer Groep. Zie Inhoud die is opgeslagen in postvakken voor [eDiscovery](what-is-stored-in-exo-mailbox.md)voor meer informatie over de toepassingsgegevens die worden bewaard wanneer een postvak in de wacht wordt geplaatst.

   1. **SharePoint sites:** Stel de schakelknop in op **Aan** en klik vervolgens op Sites **kiezen** om op te geven SharePoint sites en OneDrive accounts in de wacht te zetten. Typ de URL voor elke site die u in de wacht wilt zetten. U kunt ook de URL voor de SharePoint toevoegen voor een Microsoft-team, Office 365 groep of een Yammer Groep.
  
   1. **Exchange openbare mappen:** Stel de schakelknop in op **Aan** om alle openbare mappen in uw Exchange Online in de wacht te zetten. U kunt geen specifieke openbare mappen kiezen om in de wacht te zetten. Schakel de wisselknop uit als u openbare mappen niet in de wacht wilt zetten.

   > [!NOTE]
   > U moet ten minste één inhoudslocatie aan de wacht houden toevoegen. Anders wordt in de eDiscovery-holdstatistieken laten zien dat er geen items in de wacht staan.

8. Wanneer u klaar bent met het toevoegen van locaties aan de wacht, klikt u op **Volgende.**

9. Als u een query wilt maken met behulp van trefwoorden of voorwaarden, moet u de volgende stappen uitvoeren. Als u alle inhoud op de opgegeven inhoudslocaties wilt behouden, klikt u op **Volgende.**

    ![Een op query's gebaseerde wachtfunctie maken met trefwoord en voorwaarden](../media/eDiscoveryHoldQuery.png)
  
    1. Typ in het vak onder **Trefwoorden** een query om alleen de inhoud te behouden die overeenkomt met de querycriteria. U kunt trefwoorden, e-mailberichteigenschappen of site-eigenschappen opgeven, zoals bestandsnamen. U kunt ook complexere query's gebruiken die een Booleaanse operator gebruiken, zoals **EN,** **OF** of **NIET.**

    2. Klik **op Voorwaarde toevoegen** om een of meer voorwaarden toe te voegen om de query voor de wacht te beperken. Elke voorwaarde voegt een component toe aan de KQL-zoekquery die wordt gemaakt en uitgevoerd wanneer u de wacht houdt. U kunt bijvoorbeeld een datumbereik opgeven, zodat e-mail- of sitedocumenten die zijn gemaakt binnen het opgegeven datumbereik, behouden blijven. Een voorwaarde is logisch verbonden met de trefwoordquery (opgegeven in het vak Trefwoorden) en andere voorwaarden door de **operator AND.**  Dit betekent dat items moeten voldoen aan zowel de trefwoordquery als de voorwaarde die moet worden bewaard.

    Zie Trefwoordenquery's en zoekvoorwaarden [voor eDiscovery](keyword-queries-and-search-conditions.md)voor meer informatie over het maken van een zoekquery en het gebruik van voorwaarden.

10. Klik na het configureren van een query-hold op **Volgende.**

11. Controleer uw instellingen (en bewerk ze zo nodig) en klik vervolgens op **Verzenden.**

## <a name="query-based-holds-placed-on-sites"></a>Op query's gebaseerde holds geplaatst op sites

Houd rekening met de volgende zaken wanneer u een eDiscovery-bewaarfunctie op basis van query's op documenten op SharePoint plaatsen:

- In een op query gebaseerde bewaarperiode worden in eerste instantie alle documenten op een site bewaard voor een korte periode nadat ze zijn verwijderd. Dat betekent dat wanneer een document wordt verwijderd, het wordt verplaatst naar de bewaringsbibliotheek, zelfs als het niet voldoet aan de criteria van de query-bewaring. Verwijderde documenten die niet overeenkomen met een bewaring op basis van query's, worden echter verwijderd door een timerfunctie die de bewaringsbibliotheek verwerkt. De timerfunctie wordt regelmatig uitgevoerd en vergelijkt alle documenten in de bewaringsbibliotheek met uw op query's gebaseerde eDiscovery-bewaring (en andere typen bewaar- en bewaarbeleid). Met de timerfunctie worden de documenten verwijderd die niet overeenkomen met een op query gebaseerde bewaarfunctie en worden de documenten behouden die wel worden bewaard.

- Op query's gebaseerde bewaringen mogen niet worden gebruikt om gerichte bewaring uit te voeren, zoals het bewaren van documenten in een specifieke map of site of met behulp van andere bewaarcriteria op basis van locatie. Dit kan onbedoelde resultaten hebben. Het is raadzaam niet-locatiegebaseerde bewaarcriteria, zoals trefwoorden, datumbereiken of andere documenteigenschappen, te gebruiken om sitedocumenten te behouden.

## <a name="ediscovery-hold-statistics"></a>eDiscovery-holdstatistieken

Nadat u een eDiscovery-hold hebt gemaakt, wordt informatie over de nieuwe wacht in de flyoutpagina weergegeven voor de geselecteerde wacht. Deze informatie omvat het aantal postvakken en sites dat in de wacht staat en statistieken over de inhoud die in de wacht is geplaatst, zoals het totale aantal en de grootte van items die in de wacht zijn geplaatst en de laatste keer dat de holdstatistieken zijn berekend. Deze bewaarstatistieken helpen u bij het vaststellen van de hoeveelheid inhoud die aan de zaak is gerelateerd.
  
![Statistieken vast houden](../media/eDiscoveryHoldStatistics.png)
  
Houd rekening met de volgende dingen over de statistieken van eDiscovery-bewaar:
  
- Het totale aantal items dat in de wacht staat, geeft het aantal items aan van alle inhoudsbronnen die in de wacht zijn geplaatst. Als u een query hold hebt gemaakt, geeft deze statistiek het aantal items aan dat bij de query past.

- Het aantal items dat in de wacht staat, bevat ook niet-geïndexeerde items die op de inhoudslocaties worden gevonden. Als u een query in de wacht houdt, worden alle niet-geïndexeerde items op de inhoudslocaties in de wacht geplaatst. Dit geldt ook voor niet-geïndexeerde items die niet overeenkomen met de zoekcriteria van een op query gebaseerde greep en niet-geïndexeerde items die buiten een datumbereikvoorwaarde vallen. Dit is anders dan wat er gebeurt wanneer u een zoekopdracht uitvoert, waarbij niet-geïndexeerde items die niet overeenkomen met de zoekquery of die zijn uitgesloten door een datumbereik, niet worden opgenomen in de zoekresultaten. Zie Gedeeltelijk geïndexeerde items voor meer informatie over niet-geïndexeerde [items.](partially-indexed-items-in-content-search.md)

- U kunt de meest recente holdstatistieken krijgen door op **Statistieken** bijwerken te klikken om een zoekschatting opnieuw uit te werken waarmee het huidige aantal items in de wacht wordt berekend.

- Het is normaal dat het aantal items dat in de wacht staat in de tijd toeneemt, omdat gebruikers van wie het postvak of de site in de wacht staat, gewoonlijk een nieuw e-mailbericht verzenden of ontvangen en nieuwe documenten maken in SharePoint en OneDrive.

- Als een Exchange-, SharePoint-site- of OneDrive-account wordt verplaatst naar een andere regio in een multi-geo-omgeving, worden de statistieken voor die site niet opgenomen in de hold-statistieken. Maar de inhoud op deze locaties blijft behouden. Als een postvak of site naar een ander gebied wordt verplaatst, wordt het SMTP-adres of de URL die in de wacht wordt weergegeven, niet automatisch bijgewerkt. U moet de wacht houden bewerken en de URL of HET SMTP-adres bijwerken, zodat de inhoudslocaties opnieuw worden opgenomen in de hold-statistieken

## <a name="search-locations-on-ediscovery-hold"></a>Zoeklocaties in de eDiscovery-wachtfunctie

Wanneer u [zoekt naar inhoud](search-for-content-in-core-ediscovery.md) in een Hoofd-eDiscovery-zaak, kunt u de zoekopdracht snel configureren om alleen te zoeken op de inhoudslocaties die zijn geplaatst in een wachtplaats die aan de zaak is gekoppeld.

Selecteer de **optie Locaties in de wacht** om te zoeken naar alle inhoudslocaties die in de wacht zijn geplaatst. Als de zaak meerdere eDiscovery-inhoudslocaties bevat, worden de inhoudslocaties uit alle ophoudt doorzocht wanneer u deze optie selecteert. Als een inhoudslocatie in een op query's gebaseerde wachtplaats is geplaatst, worden alleen de items gezocht die overeenkomen met de wachtquery wanneer u de zoekopdracht uitvoert. Met andere woorden: alleen de inhoud die overeenkomt met zowel de criteria voor het vasthouden als het zoekcriterium, wordt geretourneerd met de zoekresultaten. Als een gebruiker bijvoorbeeld is geplaatst op basis van query's met items die vóór een bepaalde datum zijn verzonden of gemaakt, worden alleen die items doorzocht. Dit wordt gedaan door de query voor het vasthouden van de zaak en de zoekquery te verbinden door een **OPERATOR EN.**

Hier zijn enkele andere dingen waar u rekening mee moet houden bij het zoeken naar locaties in de eDiscovery-wacht:

- Als een inhoudslocatie deel uitmaakt van meerdere inhoudsoperatoren  in hetzelfde geval, worden de query's voor het vasthouden door OF-operatoren gecombineerd wanneer u op die inhoudslocatie zoekt met de optie Inhoud van alle gevallen. Als een inhoudslocatie deel uitmaakt van twee verschillende holds, waarbij de ene op query's is gebaseerd en de andere een oneindige greep is (waarbij alle inhoud in de wacht wordt geplaatst), is alle inhoud zoeken vanwege de oneindige greep.

- Als een zoekopdracht is geconfigureerd om locaties in de wacht te zetten en vervolgens een eDiscovery-wacht in de zaak wijzigt (door een locatie toe te voegen of te verwijderen of een wachtquery te wijzigen), wordt de zoekconfiguratie bijgewerkt met deze wijzigingen. U moet de zoekopdracht echter opnieuw doen nadat de wacht is gewijzigd om de zoekresultaten bij te werken.

- Als meerdere eDiscovery-items op één locatie in een eDiscovery-zaak worden geplaatst en u selecteert om locaties in de wacht te zetten, is het maximum aantal trefwoorden voor die zoekquery 500. De zoekactie combineert namelijk alle op query's gebaseerde in- en uitbaters met behulp van de **operator OF.** Als de gecombineerde query's en de zoekquery meer dan 500 trefwoorden bevatten, wordt naar alle inhoud in het postvak gezocht, niet alleen naar de inhoud die overeenkomt met het op query gebaseerde geval.

- Als een eDiscovery-wachtpositie de status **Aan (In behandeling)** heeft, kunt u nog steeds zoeken op de locaties in de wacht terwijl de wachtpositie wordt ingeschakeld.

## <a name="preserve-content-in-microsoft-teams"></a>Inhoud behouden in Microsoft Teams

Gesprekken die deel uitmaken van een Microsoft Teams kanaal, worden opgeslagen in het postvak dat is gekoppeld aan het Microsoft-team. Op dezelfde manier worden bestanden die teamleden delen in een kanaal opgeslagen op de SharePoint teamsite. Daarom moet u het teampostvak en de SharePoint in de eDiscovery-wachtplaats plaatsen om gesprekken en bestanden in een kanaal te behouden.

U kunt ook gesprekken die deel uitmaken van de chatlijst in Teams (chats met de naam *1:1* of *groepschats van 1:N)* opslaan in de postvakken van de gebruikers die deelnemen aan de chat. En bestanden die gebruikers delen in chatgesprekken, worden opgeslagen in OneDrive account van de gebruiker die het bestand deelt. Daarom moet u de afzonderlijke gebruikerspostvakken en -OneDrive toevoegen aan een eDiscovery-wachtruimte om gesprekken en bestanden in de chatlijst te behouden. Het is een goed idee om de postvakken van leden van een Microsoft-team in de wacht te zetten, naast het in de wacht zetten van het teampostvak en de site.

> [!NOTE]
> Als uw organisatie een hybride Exchange-implementatie heeft (of als uw organisatie een on-premises Exchange-organisatie synchroniseert met Office 365) en Microsoft Teams heeft ingeschakeld, kunnen on-premises gebruikers de Teams-chattoepassing gebruiken en deelnemen aan 1:1 chats en 1:N-groepschats. Deze gesprekken worden opgeslagen in cloudopslag die is gekoppeld aan een on-premises gebruiker. Als een on-premises gebruiker in een eDiscovery-bewaring wordt geplaatst, blijft Teams chatinhoud in de cloudopslag behouden. Zie Zoeken naar Teams [chatgegevens voor on-premises gebruikers](search-cloud-based-mailboxes-for-on-premises-users.md)voor meer informatie.

Zie Een gebruiker of [team](/MicrosoftTeams/legal-hold)in Microsoft Teams juridische Microsoft Teams voor meer informatie over het behoud van Teams inhoud.

### <a name="preserve-card-content"></a>Kaartinhoud behouden

Op dezelfde manier wordt kaartinhoud die wordt gegenereerd door apps in Teams-kanalen, 1:1-chats en 1:N-groepschats, opgeslagen in postvakken en behouden wanneer een postvak in een eDiscovery-wachtruimte wordt geplaatst. Een *kaart* is een gebruikersinterfacecontainer voor korte stukken inhoud. Kaarten kunnen meerdere eigenschappen en bijlagen hebben en kunnen knoppen bevatten waarmee kaartacties worden ge triggerd. Zie Kaarten voor meer [informatie.](/microsoftteams/platform/task-modules-and-cards/what-are-cards) Net als Teams inhoud, wordt de kaartinhoud opgeslagen op basis van de plaats waar de kaart is gebruikt. Inhoud voor kaarten die in een Teams kanaal worden gebruikt, wordt opgeslagen in Teams groepspostvak. Kaartinhoud voor 1:1- en 1xN-chats worden opgeslagen in de postvakken van de chatdeelnemers.

### <a name="preserve-meeting-and-call-information"></a>Vergaderings- en gespreksgegevens behouden

Overzichtsgegevens voor vergaderingen en oproepen in een Teams kanaal worden ook opgeslagen in de postvakken van gebruikers die inbelden bij de vergadering of oproep. Deze inhoud blijft ook behouden wanneer een eDiscovery-bewaarplaats in gebruikerspostvakken wordt geplaatst.

### <a name="preserve-content-in-private-channels"></a>Inhoud behouden in privékanalen

Vanaf februari 2020 hebben we ook de mogelijkheid ingeschakeld om inhoud in privékanalen te behouden. Omdat privékanaalchats worden opgeslagen in de postvakken van de chatdeelnemers, blijven privékanaalchats behouden door een gebruikerspostvak in de eDiscovery-wachtruimte te plaatsen. Als een postvak van een gebruiker vóór februari 2020 in een eDiscovery-opslag is geplaatst, wordt de opslag nu automatisch toegepast op berichten van privékanaals die in dat postvak zijn opgeslagen. Het behouden van bestanden die in privékanalen worden gedeeld, wordt ook ondersteund.

### <a name="preserve-wiki-content"></a>Wiki-inhoud behouden

Elk team- of teamkanaal bevat ook een Wiki voor het maken van notitie en samenwerking. De Wiki-inhoud wordt automatisch opgeslagen in een bestand met een MHT-indeling. Dit bestand wordt opgeslagen in de Teams wikigegevens op de teamsite SharePoint wikigegevens. U kunt de wiki-inhoud behouden door de teamsite SharePoint aan een eDiscovery-wachtplaats toe te voegen.

> [!NOTE]
> De mogelijkheid om Wiki-inhoud voor een team- of teamkanaal te behouden (wanneer u de SharePoint-site van het team in de wacht zet) is uitgebracht op 22 juni 2017. Als een teamsite in de wacht staat, blijft de Wiki-inhoud behouden vanaf die datum. Als een teamsite echter in de wacht staat en de Wiki-inhoud vóór 22 juni 2017 is verwijderd, blijft de Wiki-inhoud niet behouden.

### <a name="office-365-groups"></a>Office 365 Groepen

Teams is gebaseerd op Office 365 Groepen. Het plaatsen van Office 365 groepen in de eDiscovery-wacht is daarom vergelijkbaar door de inhoud Teams in de wacht te zetten.

Houd rekening met de volgende dingen wanneer u zowel Teams als Office 365 groepen in een eDiscovery-wacht houdt:

- Als u inhoud in Teams en Office 365 Groepen in de wacht wilt zetten, moet u het postvak en de SharePoint opgeven die is gekoppeld aan een groep of team.

- Voer de **Get-UnifiedGroup-cmdlet** uit in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) om eigenschappen voor Teams en Office 365 groepen. Dit is een goede manier om de URL op te halen voor de site die is gekoppeld aan een team of Office 365 groep. Met de volgende opdracht worden bijvoorbeeld geselecteerde eigenschappen weergegeven voor een Office 365 groep met de naam Senior Leadership Team:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Als u de **cmdlet Get-UnifiedGroup** wilt uitvoeren, moet u de rol View-Only Geadresseerden toegewezen krijgen in Exchange Online of lid zijn van een rollengroep die de rol View-Only Geadresseerden heeft toegewezen. 
  
- Wanneer het postvak van een gebruiker wordt doorzocht, wordt Office 365 team of groep waar de gebruiker lid van is, niet gezocht. Wanneer u een team of groep Office 365 in de eDiscovery-wacht, worden alleen het groepspostvak en de groepssite in de wacht geplaatst. De postvakken en OneDrive voor Bedrijven van groepsleden worden niet in de wacht gezet, tenzij u ze expliciet toevoegt aan de eDiscovery-wachtplaats. Dus als u een Team of Office 365-groep om een juridische reden in de wacht moet zetten, kunt u overwegen om de postvakken en OneDrive accounts van team- of groepsleden in dezelfde wacht te zetten.

- Als u een lijst met de leden van een team of groep  Office 365, kunt u de eigenschappen weergeven op de pagina Groepen in het Microsoft 365 beheercentrum. U kunt ook de volgende opdracht uitvoeren in Exchange Online PowerShell:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Als u de **cmdlet Get-UnifiedGroupLinks** wilt uitvoeren, moet u de rol View-Only Geadresseerden in Exchange Online krijgen of lid zijn van een rollengroep die de rol View-Only Geadresseerden heeft toegewezen.

## <a name="preserve-content-in-onedrive-accounts"></a>Inhoud behouden in OneDrive accounts

Zie Een lijst maken met alle OneDrive-locaties in uw organisatie als u een lijst wilt verzamelen met de URL's voor de [OneDrive voor Bedrijven-sites in](/onedrive/list-onedrive-urls)uw organisatie, zodat u deze kunt toevoegen aan een wacht- of zoekactie die is gekoppeld aan een eDiscovery-zaak. Met het script in dit artikel wordt een tekstbestand gemaakt met een lijst met alle OneDrive sites in uw organisatie. Als u dit script wilt uitvoeren, moet u de SharePoint Online Management Shell installeren en gebruiken. Zorg ervoor dat u de URL voor het MySite-domein van uw organisatie aan elke site OneDrive die u wilt zoeken. Dit is het domein dat al uw OneDrive; `https://contoso-my.sharepoint.com`bijvoorbeeld. Hier is een voorbeeld van een URL voor de OneDrive van een gebruiker: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com` .

> [!IMPORTANT]
> De URL voor het OneDrive account van een gebruiker bevat de naam van de gebruikershoofdnaam (UPN) `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` (bijvoorbeeld). In het zeldzame geval dat de UPN van een persoon wordt gewijzigd, wordt OneDrive URL ook gewijzigd om de nieuwe UPN in te nemen. Als het OneDrive-account van een gebruiker deel uitmaakt van een eDiscovery-wacht, oud en hun UPN wordt gewijzigd, moet u de wacht houden bijwerken en de nieuwe OneDrive-URL van de gebruiker toevoegen en de oude verwijderen. Zie Hoe UPN-wijzigingen van invloed zijn op de [OneDrive URL voor meer informatie.](/onedrive/upn-changes)

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Inhoudslocaties verwijderen uit een eDiscovery-wacht

Nadat een postvak, SharePoint site of OneDrive account is verwijderd uit een eDiscovery-wachtstand, wordt een *vertragingsstop* toegepast. Dit betekent dat de feitelijke verwijdering van de wacht 30 dagen wordt uitgesteld om te voorkomen dat gegevens permanent worden verwijderd (verwijderd) van een inhoudslocatie. Hierdoor kunnen beheerders zoeken naar of inhoud herstellen die wordt verwijderd nadat een eDiscovery-hold is verwijderd. De details van de vertragingsvertraging voor postvakken en sites verschillen.

- **Postvakken:** Een vertragingsstop wordt in een postvak geplaatst wanneer de volgende keer dat de assistent voor beheerde mappen het postvak verwerkt en detecteert dat een eDiscovery-wachtstand is verwijderd. In het bijzonder wordt een vertragingsvertraging toegepast op een postvak wanneer de assistent voor beheerde mappen een van de volgende postvakeigenschappen in stelt op **Waar:**

   - **DelayHoldApplied:** Deze eigenschap is van toepassing op e-mailgerelateerde inhoud (die wordt gegenereerd door personen die gebruikmaken van Outlook en Outlook op het web) die is opgeslagen in het postvak van een gebruiker.

   - **DelayReleaseHoldApplied:** Deze eigenschap is van toepassing op cloudinhoud (gegenereerd door niet-Outlook-apps zoals Microsoft Teams, Microsoft Forms en Microsoft Yammer) die is opgeslagen in het postvak van een gebruiker. Cloudgegevens die door een Microsoft-app worden gegenereerd, worden meestal opgeslagen in een verborgen map in het postvak van een gebruiker.

   Wanneer een vertragingsbehoud in het postvak wordt geplaatst (wanneer een van de vorige eigenschappen is ingesteld op **Waar),** wordt het postvak nog steeds beschouwd als in de wachtstand voor een onbeperkte duur van de wachtstand, alsof het postvak in de wachtstand staat. Na 30 dagen verloopt de vertragingstermijn en Microsoft 365 probeert automatisch de vertragingsbehoud te verwijderen (door de eigenschap DelayHoldApplied of DelayReleaseHoldApplied in te stellen op **Onwaar)** zodat de wachtstand wordt verwijderd. Nadat een van deze eigenschappen is ingesteld op Onwaar, worden de bijbehorende items die zijn gemarkeerd voor verwijdering, verwijderd wanneer het postvak de volgende keer wordt verwerkt door de Assistent voor beheerde mappen.

   Zie Postvakken beheren [bij vertragingsvertraging](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)voor meer informatie.

- **SharePoint en OneDrive sites:** Alle SharePoint of OneDrive inhoud die wordt bewaard in de bewaringsbibliotheek, wordt niet verwijderd tijdens de bewaringsperiode van 30 dagen nadat een site is verwijderd uit een eDiscovery-bewaring. Dit is vergelijkbaar met wat er gebeurt wanneer een site wordt vrijgegeven uit een bewaarbeleid. Bovendien kunt u deze inhoud niet handmatig verwijderen in de bewaringsbibliotheek tijdens de bewaringsperiode van 30 dagen. 

   Zie Een bewaarbeleid vrijgeven voor [meer informatie.](retention.md#releasing-a-policy-for-retention)

Er wordt ook een vertragingsstop toegepast op inhoudslocaties die in de wachtstand staan wanneer u een core eDiscovery-zaak sluit, omdat wachtstanden zijn uitgeschakeld wanneer een zaak wordt gesloten. Zie Een [hoofd-eDiscovery-zaak sluiten,](close-reopen-delete-core-ediscovery-cases.md)opnieuw openen en verwijderen voor meer informatie over het sluiten van een zaak.

## <a name="ediscovery-hold-limits"></a>eDiscovery-limieten voor het vasthouden van eDiscovery

De volgende tabel bevat de limieten voor eDiscovery-zaken en case-holds.

  | Beschrijving van limiet | Limiet |
  |:-----|:-----|
  |Maximum aantal zaken voor een organisatie.  <br/> |Geen limiet  <br/> |
  |Het maximum aantal eDiscovery-bezit voor een organisatie.  <br/> |10,000  <br/> |
  |Maximum aantal postvakken in één eDiscovery-wacht. Deze limiet omvat het gecombineerde totaal van gebruikerspostvakken en de postvakken die zijn gekoppeld aan Microsoft 365 Groepen, Microsoft Teams en Yammer Groepen.  <br/> |1,000  <br/> |
  |Maximum aantal sites in één eDiscovery-wacht. Deze limiet omvat het gecombineerde totaal OneDrive voor Bedrijven sites, SharePoint sites en de sites die zijn gekoppeld aan Microsoft 365 Groepen, Microsoft Teams en Yammer Groepen.  <br/> |100  <br/> |
  |Het maximum aantal zaken dat wordt weergegeven op de startpagina van eDiscovery en het maximum aantal items dat wordt weergegeven op de tabbladen Houdt, Zoekopdrachten en Exporteren in een zaak. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Als u een lijst wilt weergeven met meer dan 1.000 zaken, opgeslagen, gezocht of exporteert, kunt u de bijbehorende powershell-cmdlet Office 365 Security & Compliance PowerShell gebruiken:
   >
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)
