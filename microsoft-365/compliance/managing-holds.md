---
title: Beheert houdt in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Meer informatie over het plaatsen van bewaarnemingen voor bewaarders en hun gegevensbronnen om relevante inhoud voor uw Advanced eDiscovery bewaren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 70390a933de788a6b1190e42b5087b85a175b9a2
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162535"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Beheert houdt in Advanced eDiscovery

U kunt een Advanced eDiscovery gebruiken om bewaar bewaart te maken om inhoud te behouden die mogelijk relevant is voor uw zaak. Met de Advanced eDiscovery bewaarmogelijkheden kunt u bewaarmogelijkheden voor bewaarders en hun gegevensbronnen plaatsen. Bovendien kunt u postvakken en sites die niet worden bewaard, OneDrive voor Bedrijven bewaren. U kunt ook een wacht houden op het groepspostvak, SharePoint site en OneDrive voor Bedrijven voor een Microsoft 365 Groep. U kunt ook een wacht houden op het postvak en de site die zijn gekoppeld aan Microsoft Teams. Wanneer u inhoudslocaties in de wacht zet, wordt inhoud bewaard totdat u de bewaarder los laat, een specifieke gegevenslocatie verwijdert of het bewaarbeleid volledig verwijdert.

## <a name="manage-custodian-based-holds"></a>Bewaar bewaarders beheren

In sommige gevallen hebt u mogelijk een set bewaarders die u hebt geïdentificeerd en die u hebt besloten om hun gegevens tijdens de zaak te bewaren. Wanneer Advanced eDiscovery bewaarders in de wacht worden gezet, worden de gebruiker en de geselecteerde gegevensbronnen automatisch toegevoegd aan een bewaarbeleid.

Het bewaarbeleid weergeven:

1. Klik in Microsoft 365 compliancecentrum op **eDiscovery > Advanced** om de lijst met zaken in uw organisatie weer te geven.

2. Ga naar het **tabblad Bronnen** om beheerders toe te voegen in uw zaak. Zie Bewaarders toevoegen aan een zaak voor meer informatie over het toevoegen en in de wacht zetten van bewaarders in een Advanced eDiscovery [zaak.](add-custodians-to-case.md) Als u al beheerders hebt toegevoegd en deze in de wacht hebt geplaatst, gaat u naar stap 3.

3. Ga naar het **tabblad Houdt** en klik **op Bewaarderhold. \<HoldId>**

4. Op de flyoutpagina ziet u statistieken over het beleid. U kunt ook acties uitvoeren, zoals het toepassen van een query op uw bewaar bewaarfunctie. Zie Trefwoordquery's en zoekvoorwaarden voor Inhoud zoeken voor meer informatie over het maken van een wachtquery en het gebruik van [voorwaarden.](keyword-queries-and-search-conditions.md)

## <a name="manage-non-custodial-holds"></a>Niet-bewaarder-bewaar houdt beheren

Wanneer u een wachtruimte maakt, hebt u de volgende opties voor het bereik van de inhoud die op de opgegeven inhoudslocaties wordt gehouden:

- U maakt een oneindige greep waarin alle inhoud in de wacht wordt geplaatst. U kunt ook een op query's gebaseerde wachtplaats maken waarbij alleen inhoud die overeenkomt met een zoekquery, in de wacht wordt geplaatst.
  
- U kunt een datumbereik opgeven om alleen de inhoud vast te houden die binnen dat datumbereik is verzonden, ontvangen of gemaakt. U kunt ook alle inhoud vasthouden, ongeacht wanneer deze is verzonden, ontvangen of gemaakt.

Als u een niet-bewaarder wilt maken voor een Advanced eDiscovery geval:

1. Klik in Microsoft 365 compliancecentrum op **eDiscovery > Advanced** om de lijst met zaken in uw organisatie weer te geven.
  
2. Klik **op Openen** naast de zaak waarin u de ops houdt.
  
3. Klik op de startpagina voor de zaak op het **tabblad Ingedrukt.**
  
4. Klik op **het** tabblad Houdt op **Maken.**
  
5. Geef op **de pagina** Uw wacht houden een naam op. De naam van de wacht moet uniek zijn in uw organisatie.
 
6. (Optioneel) Voeg in **het** vak Beschrijving een beschrijving van de wacht in.
  
7. Klik op **Volgende**.
  
8. Kies de inhoudslocaties die u in de wacht wilt zetten. U kunt postvakken, sites en openbare mappen in de wacht zetten.

   1. **Exchange** e-mail: klik op **Gebruikers, groepen** of teams kiezen en klik vervolgens nogmaals op **Gebruikers,** groepen of teams kiezen om postvakken op te geven die in de wacht moeten worden gezet. Gebruik het zoekvak om gebruikerspostvakken en distributiegroepen te zoeken (om de postvakken van groepsleden in de wacht te zetten) om deze in de wacht te zetten. U kunt ook het bijbehorende postvak in de wacht zetten voor een Microsoft 365 of een Microsoft-team. Schakel het selectievakje gebruiker, groep, team in, klik **op Kiezen** en klik vervolgens op **Klaar.**
 
      > [!NOTE]
      > Wanneer u op **Gebruikers, groepen** of teams kiezen klikt om postvakken op te geven die in de wacht moeten worden gezet, is de weergegeven postvak picker leeg. Dit is een ontwerp om de prestaties te verbeteren. Als u personen aan deze lijst wilt toevoegen, typt u een naam (minimaal 3 tekens) in het zoekvak.

   1. **SharePoint Sites:** **klik** op Sites kiezen  en klik vervolgens nogmaals op Sites kiezen om SharePoint en OneDrive voor Bedrijven sites in de wacht te zetten. Typ de URL voor elke site die u in de wacht wilt zetten. U kunt ook de URL voor de SharePoint toevoegen voor een Microsoft 365 groep of een Microsoft-team. Klik **op** Kiezen en klik vervolgens op **Klaar.**

      > [!NOTE]
      > De URL voor het OneDrive account van een gebruiker bevat de naam van de gebruikershoofdnaam (UPN) `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` (bijvoorbeeld). In het zeldzame geval dat de UPN van een persoon wordt gewijzigd, wordt OneDrive URL ook gewijzigd om de nieuwe UPN in te nemen. Als het account OneDrive van een gebruiker deel uitmaakt van een niet-bewaarder en de UPN wordt gewijzigd, moet u de wacht houden bijwerken en de nieuwe URL OneDrive aanwijzers. Zie Hoe UPN-wijzigingen van invloed zijn op de [OneDrive URL voor meer informatie.](/onedrive/upn-changes)

   1. **Exchange openbare mappen:** verplaats de wisselknop naar de positie Alles om alle openbare mappen in uw Exchange Online in de wachtstand te zetten. Houd er rekening mee dat u geen specifieke openbare mappen kunt kiezen om in de wacht te zetten. Laat de wisselknop ingesteld op **Geen** als u openbare mappen niet in de wacht wilt zetten.

9. Wanneer u klaar bent met het toevoegen van inhoudslocaties aan de wacht, klikt u op **Volgende.**
  
10. Als u een query met voorwaarden wilt maken, vult u het volgende in. Klik anders op **Volgende.**
    
    - Typ in het vak onder **Trefwoorden** een zoekquery in het vak, zodat alleen de inhoud die aan de zoekcriteria voldoet, in de wacht wordt geplaatst. U kunt trefwoorden, berichteigenschappen of documenteigenschappen opgeven, zoals bestandsnamen. U kunt ook complexere query's gebruiken die een Booleaanse operator gebruiken, zoals EN, OF of NIET. Als u het vak met trefwoorden leeg laat, wordt alle inhoud op de opgegeven inhoudslocaties in de wacht geplaatst.

    - Klik  **op Voorwaarden** toevoegen om een of meer voorwaarden toe te voegen om de zoekquery voor de wacht te beperken. Elke voorwaarde voegt een component toe aan de KQL-zoekquery die wordt gemaakt en uitgevoerd wanneer u de wacht houdt. U kunt bijvoorbeeld een datumbereik opgeven, zodat e-mail- of sitedocumenten die zijn gemaakt binnen het opgegeven datumbereik in de wacht worden geplaatst. Een voorwaarde is logisch verbonden met de trefwoordquery (opgegeven in het trefwoordvak) door de operator AND. Dit betekent dat items moeten voldoen aan zowel de trefwoordquery als de voorwaarde die in de wacht moet worden geplaatst.

     Zie Trefwoordenquery's en zoekvoorwaarden voor Inhoud zoeken voor meer informatie over het maken van een zoekquery en het gebruik van [voorwaarden.](/office365/SecurityCompliance/keyword-queries-and-search-conditions)

11. Klik na het configureren van een query-hold op **Volgende.**

12. Controleer uw instellingen en klik vervolgens op **Deze wacht houden maken.**

## <a name="view-hold-statistics"></a>Statistieken weergeven

Na enige tijd wordt informatie over de nieuwe wacht in het detailvenster weergegeven op het **tabblad** Houdt voor de geselecteerde wacht. Deze informatie omvat het aantal postvakken en sites dat in de wacht staat en statistieken over de inhoud die in de wacht is geplaatst, zoals het totale aantal en de grootte van items die in de wacht zijn geplaatst en de laatste keer dat de holdstatistieken zijn berekend. Met deze statistieken kunt u bepalen hoeveel inhoud er in verband met de eDiscovery-zaak wordt opgehouden.

Houd rekening met de volgende zaken bij het bewaren van statistieken:

- Het totale aantal items dat in de wacht staat, geeft het aantal items aan van alle inhoudsbronnen die in de wacht zijn geplaatst. Als u een query hold hebt gemaakt, geeft deze statistiek het aantal items aan dat bij de query past.
  
- Het aantal items dat in de wacht staat, bevat ook niet-geïndexeerde items die op de inhoudslocaties worden gevonden. Houd er rekening mee dat als u een op query gebaseerde wachtplaats maakt, alle niet-geïndexeerde items op de inhoudslocaties in de wacht worden geplaatst. Dit geldt ook voor niet-geïndexeerde items die niet overeenkomen met de zoekcriteria van een op query gebaseerde greep en niet-geïndexeerde items die buiten een datumbereikvoorwaarde vallen. Dit is anders dan wat er gebeurt wanneer u een inhoudszoekactie uitvoert, waarbij niet-geïndexeerde items die niet overeenkomen met de zoekquery of die worden uitgesloten door een datumbereik, niet worden opgenomen in de zoekresultaten. Zie Gedeeltelijk geïndexeerde items in Inhoud zoeken in Office 365 voor [meer informatie over niet-geïndexeerde items.](partially-indexed-items-in-content-search.md) 

- U kunt de meest recente holdstatistieken krijgen door op Statistieken bijwerken te klikken om een zoekschatting opnieuw uit te voeren waarmee het huidige aantal items in de wacht wordt berekend.

- Klik indien nodig op Vernieuwen op de werkbalk om de holdstatistieken in het detailvenster bij te werken.

- Het is normaal dat het aantal items dat in de wacht staat in de tijd toeneemt, omdat gebruikers van wie het postvak of de site in de wacht staat, meestal nieuw e-mailbericht verzenden of ontvangen en nieuwe SharePoint en OneDrive voor Bedrijven maken.

- Als een SharePoint-site of OneDrive-account wordt verplaatst naar een andere regio in een multi-geo-omgeving, worden de statistieken voor die site niet opgenomen in de hold-statistieken. De inhoud op de site blijft echter in de wacht staan. Als een site naar een ander gebied wordt verplaatst, wordt de URL die in de wacht wordt weergegeven, niet bijgewerkt. U moet de wacht houden bewerken en de URL bijwerken.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Een wacht houden op Microsoft Teams en Office 365 Groepen

Microsoft Teams zijn gebaseerd op Office 365 Groepen. Daarom lijkt het plaatsen van de Advanced eDiscovery in de wacht.

- **Hoe wijs ik een extra Microsoft 365 groepen of Microsoft Teams aan een beheerder? En hoe zit het met het plaatsen van een niet-bewaarder in Microsoft 365 groepen en Microsoft Teams?** Microsoft Teams zijn gebaseerd op Microsoft 365 Groepen. Daarom is het zeer vergelijkbaar om ze in de wacht te zetten in een eDiscovery-zaak. Houd rekening met de volgende zaken wanneer u Microsoft 365 Groepen Microsoft Teams in de wacht houdt.
  - Als u inhoud wilt plaatsen in Microsoft 365 Groepen en Microsoft Teams in de wacht wilt zetten, moet u het postvak en de SharePoint opgeven die zijn gekoppeld aan een groep of team.
  
  - Voer de **cmdlet Get-UnifiedGroup** uit in Exchange Online om eigenschappen voor een groep Microsoft 365 Microsoft-team weer te geven. Dit is een goede manier om de URL op te halen voor de site die is gekoppeld aan een Microsoft 365 of een Microsoft-team. Met de volgende opdracht worden bijvoorbeeld geselecteerde eigenschappen weergegeven voor een Microsoft 365 groep met de naam Senior Leadership Team:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Als u de Get-UnifiedGroup-cmdlet wilt uitvoeren, moet u de rol View-Only Geadresseerden toegewezen krijgen in Exchange Online of lid zijn van een rollengroep die de rol View-Only Geadresseerden heeft toegewezen.

 - Wanneer het postvak van een gebruiker wordt doorzocht, wordt Microsoft 365 groep of Microsoft-team waar de gebruiker lid van is, niet doorzocht. Wanneer u een groeps- Microsoft 365 Microsoft-team in de wacht houdt, worden alleen het groepspostvak en de groepssite in de wacht gezet. de postvakken en OneDrive voor Bedrijven sites van groepsleden worden niet in de wacht gezet, tenzij u ze expliciet toevoegt als bewaarders of hun gegevensbronnen in de wacht houdt. Als u daarom een Microsoft 365-groep of Microsoft-team in de wacht moet zetten voor een specifieke voogd, kunt u overwegen om de groepssite en het groepspostvak toe tewijsen aan de beheerder (zie Beheerders beheren in Advanced eDiscovery). Als de Microsoft 365 groep of Microsoft-team niet kan worden toegeschreven aan één bewaarder, kunt u overwegen de bron toe te voegen aan een niet-bewaarder. 
 
 - Als u een lijst wilt bekijken met de leden van een Microsoft 365-groep of Microsoft-team, kunt u de eigenschappen weergeven op de pagina Start > Groepen in het Microsoft 365 beheercentrum. U kunt ook de volgende opdracht uitvoeren in Exchange Online PowerShell:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Als u de **cmdlet Get-UnifiedGroupLinks** wilt uitvoeren, moet u de rol View-Only Geadresseerden in Exchange Online krijgen of lid zijn van een rollengroep die de rol View-Only Geadresseerden heeft toegewezen.

- Kanaalgesprekken die deel uitmaken van een Microsoft Teams kanaal, worden opgeslagen in het postvak dat is gekoppeld aan het team. Op dezelfde manier worden bestanden die teamleden delen in een kanaal opgeslagen op de SharePoint teamsite. Daarom moet u het Microsoft Team-postvak en de SharePoint in de wacht zetten om gesprekken en bestanden in een kanaal te behouden.
  
- U kunt ook gesprekken die deel uitmaken van de chatlijst in Microsoft Teams worden opgeslagen in het postvak van de gebruiker die deelneemt aan de chat.  Bestanden die een gebruiker in Chatgesprekken deelt, worden opgeslagen op OneDrive voor Bedrijven site van de gebruiker die het bestand deelt. Daarom moet u de afzonderlijke gebruikerspostvakken en -OneDrive voor Bedrijven in de wacht zetten om gesprekken en bestanden in de chatlijst te behouden. 
  
- Elk Microsoft-team- of teamkanaal bevat een Wiki voor het maken van notitie en samenwerking. De Wiki-inhoud wordt automatisch opgeslagen in een bestand met een MHT-indeling. Dit bestand wordt opgeslagen in de Teams wikigegevens op de teamsite SharePoint wikigegevens. U kunt de inhoud in de Wiki in de wacht zetten door de site van het team SharePoint in de wacht te zetten.

  > [!NOTE]
  > De mogelijkheid om Wiki-inhoud te behouden voor een Microsoft-team- of teamkanaal (wanneer u de SharePoint-site van het team in de wacht zet) is uitgebracht op 22 juni 2017. Als een teamsite in de wacht staat, blijft de Wiki-inhoud behouden vanaf die datum. Als een teamsite echter in de wacht staat en de Wiki-inhoud vóór 22 juni 2017 is verwijderd, blijft de Wiki-inhoud niet behouden.
