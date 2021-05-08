---
title: Uw portal starten met de planning voor het starten van portals
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In dit artikel wordt beschreven hoe u uw portal kunt starten met de planning voor het starten van portals
ms.openlocfilehash: 1e62446054f91ff5d2c99520ca65c1681d899ac9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272054"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a>Uw portal starten met de SharePoint Portal Launch Scheduler

Een portal is een SharePoint-communicatiesite op uw intranet met veel verkeer: een site met een locatie van 10.000 tot meer dan 100.000 kijkers in de loop van enkele weken. Gebruik de planning voor het starten van portals om uw portal te starten om ervoor te zorgen dat gebruikers een soepele weergaveervaring hebben bij het openen van uw nieuwe SharePoint-portal.
<br>
<br>
De planning voor het starten van portals is ontworpen om u te helpen een gefaseerd implementatieaanpak te volgen door gebruikers in golven te batchen en de URL-omleiding voor de nieuwe portal te beheren. Tijdens de lancering van elke golf kunt u feedback van gebruikers verzamelen, de prestaties van de portal controleren en de start onderbreken om problemen op te lossen voordat u verdergaat met de volgende golf. Meer informatie over het plannen van een [portallancering in SharePoint.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide) 

**Er zijn twee soorten omleiding:**

- **Bidirectioneel:** start een nieuwe moderne SharePoint-portal om een bestaande klassieke of moderne SharePoint-portal te vervangen
- **Omleiden naar een tijdelijke pagina:** start een nieuwe moderne SharePoint-portal zonder bestaande SharePoint-portal

Sitemachtigingen moeten afzonderlijk van golven zijn ingesteld als onderdeel van de start. Als u bijvoorbeeld een portal voor de hele organisatie uitwijst, kunt u machtigingen instellen voor 'Iedereen behalve externe gebruikers'. Scheid vervolgens uw gebruikers in golven met behulp van beveiligingsgroepen. Als u een beveiligingsgroep toevoegt aan een golf, krijgt die beveiligingsgroep geen toegang tot de site. 


> [!NOTE]
> - Deze functie is vanaf  mei 2021 toegankelijk via het deelvenster Instellingen op de startpagina van SharePoint-communicatiesites voor klanten met gerichte release en is vanaf juli 2021 beschikbaar voor alle klanten.
> - De PowerShell-versie van dit hulpprogramma is vandaag beschikbaar
> - Deze functie kan alleen worden gebruikt op moderne SharePoint-communicatiesites
> - U moet de machtigingen van de site-eigenaar voor de site hebben om de start van een portal aan te passen en te plannen
> - Lanceringen moeten ten minste zeven dagen van tevoren zijn gepland en elke golf kan één tot zeven dagen duren
> - Het vereiste aantal golven wordt automatisch bepaald door het verwachte aantal gebruikers 
> - Voordat u een portalstart wilt plannen, moet het hulpprogramma Paginadiagnose voor [SharePoint](https://aka.ms/perftool) worden uitgevoerd om te controleren of de startpagina van de site gezond is
> - Aan het einde van de start hebben alle gebruikers met machtigingen voor de site toegang tot de nieuwe site
> - Als uw organisatie [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections)gebruikt, kunnen gebruikers het pictogram van uw organisatie zien op de app-balk van Microsoft Teams, maar wanneer het pictogram is geselecteerd, kunnen gebruikers pas toegang krijgen tot de portal als hun golf is gestart
> - Deze functie is niet beschikbaar voor Office 365 Germany, Office 365 beheerd door 21Vianet (China) of microsoft 365 Amerikaanse overheidsplannen

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a>De verschillen tussen de opties voor het starten van portals begrijpen:

Voorheen konden portallanceringen alleen worden gepland via SharePoint PowerShell. U hebt nu twee opties om u te helpen bij het plannen en beheren van de lancering van uw portal. Meer informatie over de belangrijkste verschillen tussen beide hulpprogramma's:

**SharePoint PowerShell-versie:**

- Beheerdersreferenties zijn vereist voor het gebruik [van SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) 
- Minimumvereiste van één golf 
- Start plannen op basis van de tijdzone Coordinated Universal Time (UTC)

**In-productversie:**

- Referenties van site-eigenaar zijn vereist 
- Minimumvereiste van twee golven
- Start plannen op basis van de lokale tijdzone van de portal, zoals aangegeven in de regionale instellingen



## <a name="get-started-using-the-portal-launch-scheduler"></a>Aan de slag met de planning voor het starten van portals

1.  Voordat u het hulpprogramma Voor het starten van portals gebruikt, voegt u alle gebruikers toe die toegang tot deze [site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) nodig hebben via **sitemachtigingen** als site-eigenaar, sitelid of bezoeker.

2.  Begin vervolgens met het plannen van de lancering van uw portal door op twee manieren toegang te krijgen tot de startschema voor portals:

    **Optie 1:** De eerste paar keer dat u wijzigingen bewerkt en opnieuw uitwerkt op uw startpagina - of tot aan startpagina versie 3.0 - wordt u gevraagd het hulpprogramma Voor het starten van portals te gebruiken. Selecteer **Start plannen om** door te gaan met plannen. Of selecteer **Opnieuw publiceren om** de paginabewerkingen opnieuw te publiceren zonder de start te plannen.
    
    ![Afbeelding van de prompt om de planning voor het starten van de portal te gebruiken bij het opnieuw publiceren van de startpagina](../media/portal-launch-republish-2.png)
    
    **Optie 2:** U kunt op elk moment naar de startpagina van de SharePoint-communicatiesite gaan, Instellingen selecteren en vervolgens de start van de **site** plannen om de lancering van uw portal te plannen. 
    
    ![Afbeelding van het deelvenster Instellingen met Een site starten plannen gemarkeerd](../media/portal-launch-settings-2.png)

3.  Bevestig vervolgens de statusscore van de portal en verbeter de portal indien nodig met behulp van het hulpprogramma Paginadiagnose voor [SharePoint](https://aka.ms/perftool) totdat uw portal een **gezonde** score ontvangt. Selecteer vervolgens **Volgende**.

    ![Afbeelding van het hulpprogramma Voor het starten van portal](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > De naam en beschrijving van de site kunnen niet worden bewerkt vanuit  de planning voor het starten van portals en kunnen in plaats daarvan worden gewijzigd door Instellingen te selecteren en vervolgens **Sitegegevens** op de startpagina.
 
4.  Selecteer het **aantal verwachte gebruikers** in de vervolgkeuzekeuze. Deze afbeelding geeft het aantal gebruikers aan dat waarschijnlijk toegang tot de site nodig heeft. De planning voor het starten van portals bepaalt automatisch het ideale aantal golven, afhankelijk van de verwachte gebruikers zoals deze:
    
    - Minder dan 10.000 gebruikers: twee golven
    - 10.000 tot 30.000 gebruikers: Drie golven 
    - 30.000 tot 100.000 gebruikers: Vijf golven
    - Meer dan 100.000 gebruikers: Vijf golven en neem contact op met uw Microsoft-accountteam

5.  Bepaal vervolgens het **type omleiding dat nodig** is:

    Optie 1: Gebruikers verzenden naar een bestaande **SharePoint-pagina (bidirectioneel)** : gebruik deze optie bij het starten van een nieuwe moderne SharePoint-portal om een bestaande SharePoint-portal te vervangen. Gebruikers in actieve golven worden omgeleid naar de nieuwe site, ongeacht of ze naar de oude of nieuwe site gaan. Gebruikers in een niet-gestarte golf die toegang proberen te krijgen tot de nieuwe site, worden teruggeleid naar de oude site totdat hun golf wordt gestart.
    
    > [!NOTE] 
    > Wanneer u de optie bidirectioneel gebruikt, moet de persoon die de lancering plant, ook machtigingen voor site-eigenaar hebben voor de andere SharePoint-portal.
       
    **Optie 2: Gebruikers** verzenden naar een automatisch gegenereerde tijdelijke pagina (tijdelijke paginaomleiding) : Gebruik een tijdelijke paginaomleiding wanneer er geen bestaande SharePoint-portal bestaat. Gebruikers worden doorgestuurd naar een nieuwe moderne SharePoint-portal en als een gebruiker in een golf zit die niet is gestart, worden ze omgeleid naar een tijdelijke pagina.
    
    **Optie 3: Gebruikers** naar een externe pagina verzenden: geef een externe URL op voor een tijdelijke landingspagina totdat de golf van de gebruiker wordt gestart.
    
6.  Verbreed uw publiek in golven. Voeg maximaal 20 beveiligingsgroepen per golf toe. Golfdetails kunnen tot het begin van elke golf worden bewerkt. Elke golf kan minimaal één dag (24 uur) en ten minste zeven dagen duren. Hierdoor kunnen SharePoint en uw technische omgeving het grote aantal sitegebruikers aanpassen en schalen. Bij het plannen van een start via de gebruikersinterface is de tijdzone gebaseerd op de regionale instellingen van de site. 

    >[!NOTE] 
    > - De planning voor het starten van portals wordt automatisch standaard ingesteld op minimaal 2 golven. De PowerShell-versie van dit hulpprogramma biedt echter 1 golf.
    >  - Microsoft 365-groepen worden niet ondersteund door deze versie van de launch scheduler voor portals.

7. Bepaal wie de site direct moet bekijken en voer de gegevens in in **het veld Gebruikers die zijn vrijgesteld van golven.** Deze gebruikers worden uitgesloten van golven en worden niet omgeleid vóór, tijdens of na de lancering.

8.  Bevestig de details van de portallancering en selecteer **Planning.** Nadat de start is gepland, moeten wijzigingen in de startpagina van de SharePoint-portal een gezond diagnostisch resultaat ontvangen voordat de portal wordt geopend.


## <a name="make-changes-to-a-scheduled-portal-launch"></a>Wijzigingen aanbrengen in een geplande portallancering

Startdetails kunnen worden bewerkt voor elke golf omhoog tot de datum van de lancering van de golf. 

1.  Als u de details van de portallancering wilt bewerken, gaat u naar **Instellingen** en **selecteert u Site starten plannen.**
2.  Selecteer vervolgens **Bewerken.**
3.  Wanneer u klaar bent met het bewerken, selecteert u **Bijwerken.**


## <a name="delete-a-scheduled-portal-launch"></a>Een geplande portallancering verwijderen

Lanceringen die zijn gepland met het hulpprogramma Voor het starten van portals, kunnen op elk moment worden geannuleerd of verwijderd, zelfs als sommige golven al zijn gestart.

1.  Als u de lancering van uw portal wilt annuleren, gaat u naar **Instellingen en** Site **starten plannen.**

2.  Selecteer vervolgens **Verwijderen en** selecteer nogmaals Verwijderen wanneer u het bericht hieronder ziet. 

    ![Afbeelding van het hulpprogramma Voor het starten van portal](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a>De startplanning voor PowerShell Portal gebruiken

De sharePoint Portal launch scheduler tool was oorspronkelijk alleen beschikbaar via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) en wordt nog steeds ondersteund via PowerShell voor klanten die deze methode prefereren. Dezelfde notities aan het begin van dit artikel zijn van toepassing op beide versies van de planning voor het starten van portals. 

>[!NOTE]
> U hebt beheerdersmachtigingen nodig om SharePoint PowerShell te kunnen gebruiken.
> Details voor het starten van portals voor lanceringen die in PowerShell zijn gemaakt, worden weergegeven en kunnen worden beheerd in het nieuwe hulpprogramma Voor het starten van portals in SharePoint.


### <a name="app-setup-and-connecting-to-sharepoint-online"></a>App-installatie en verbinding maken met SharePoint Online
1. [Download de nieuwste SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Als u een eerdere versie van de SharePoint Online Management Shell hebt geïnstalleerd, gaat u naar Programma's toevoegen of verwijderen en verwijdert u 'SharePoint Online Management Shell'. <br>Selecteer op de pagina Downloadcentrum uw taal en klik vervolgens op de knop Downloaden. U wordt gevraagd om te kiezen tussen het downloaden van een x64- en x86-.msi bestand. Download het x64-bestand als u de 64-bits versie van Windows of het x86-bestand gebruikt als u de 32-bits versie gebruikt. Zie Welke versie van windows-besturingssysteem gebruik ik? als u het [niet weet.](https://support.microsoft.com/help/13443/windows-which-operating-system) Voer het bestand na het downloaden uit en volg de stappen in de wizard Instellen.

2. Verbinding maken als SharePoint globale beheerder of beheerder [SharePoint in](/sharepoint/sharepoint-admin-role) Microsoft 365. Zie Aan de slag [met SharePoint Online Management Shell voor meer informatie.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)


### <a name="view-any-existing-portal-launch-setups"></a>Bestaande installatie voor het starten van portals weergeven

Als u wilt zien of er bestaande configuraties voor het starten van portals zijn:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a>Een portallancering op de site plannen

Het aantal benodigde golven is afhankelijk van de verwachte startgrootte. 
- Minder dan 10.000 gebruikers: Één golf
- 10.000 tot 30.000 gebruikers: Drie golven 
- 30.000 tot 100.000 gebruikers: Vijf golven
- Meer dan 100.000 gebruikers: Vijf golven en neem contact op met uw Microsoft-accountteam

#### <a name="steps-for-bidirectional-redirection"></a>Stappen voor bidirectionele omleiding

Bidirectionele omleiding omvat het starten van een nieuwe moderne SharePoint Online-portal om een bestaande SharePoint of moderne portal te vervangen. Gebruikers in actieve golven worden omgeleid naar de nieuwe site, ongeacht of ze naar de oude of nieuwe site gaan. Gebruikers in een niet-gestarte golf die toegang proberen te krijgen tot de nieuwe site, worden teruggeleid naar de oude site totdat hun golf wordt gestart. 

We ondersteunen alleen omleiding tussen de standaard startpagina op de oude site en de standaard startpagina op de nieuwe site. Als u beheerders of eigenaren hebt die toegang nodig hebben tot de oude en nieuwe sites zonder dat deze worden omgeleid, moet u ervoor zorgen dat deze worden weergegeven met de `WaveOverrideUsers` parameter.

Als u gebruikers wilt migreren van een bestaande SharePoint site naar een nieuwe SharePoint site op een gefaseerd manier:

1. Voer de volgende opdracht uit om portallancerings golven aan te wijzen.
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   Voorbeeld:

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Volledige validatie. Het kan 5-10 minuten duren voordat de omleiding de configuratie van de service heeft voltooid. 

#### <a name="steps-for-redirection-to-temporary-page"></a>Stappen voor omleiding naar tijdelijke pagina

Tijdelijke paginaomleiding moet worden gebruikt wanneer er geen bestaande SharePoint portal bestaat. Gebruikers worden op een gefaseerd manier doorgestuurd naar SharePoint nieuwe moderne onlineportal. Als een gebruiker in een golf zit die niet is gestart, wordt deze omgeleid naar een tijdelijke pagina (elke URL). 

1. Voer de volgende opdracht uit om portallancerings golven aan te wijzen.
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   Voorbeeld:

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Volledige validatie. Het kan 5-10 minuten duren voordat de omleiding de configuratie van de service heeft voltooid. 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Een portal starten op de site onderbreken of opnieuw starten

1. Voer de volgende opdracht uit om de voortgang van een portal te onderbreken en tijdelijk te voorkomen dat toekomstige golfprogressie optreedt:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. Valideer dat alle gebruikers worden omgeleid naar de oude site. 

3. Voer de volgende opdracht uit als u een portallancering wilt starten die is onderbroken:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Controleer of de omleiding nu is hersteld. 

### <a name="delete-a-portal-launch-on-the-site"></a>Een portallancering op de site verwijderen

1. Voer de volgende opdracht uit om een portalstart gepland of in uitvoering voor een site te verwijderen.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Valideer dat er geen omleiding voor alle gebruikers gebeurt.

## <a name="learn-more"></a>Meer informatie

[Het plannen van uw portal launch roll-out plan in SharePoint Online](./planportallaunchroll-out.md)

[Uw communicatiesite plannen](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)