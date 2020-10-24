---
title: Waarom u PowerShell voor Microsoft 365 moet gebruiken
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Overzicht: begrijpen waarom u PowerShell moet gebruiken voor het beheren van Microsoft 365, in sommige gevallen efficiënter en in andere gevallen.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754104"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Waarom u PowerShell voor Microsoft 365 moet gebruiken

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met het Microsoft 365-Beheercentrum kunt u uw gebruikersaccounts en licenties voor Microsoft 365 beheren. U kunt ook uw Microsoft 365-Services beheren, zoals Exchange Online, teams en SharePoint Online. Als u in plaats hiervan PowerShell gebruikt voor het beheren van deze services, kunt u gebruikmaken van de taal omgeving voor de opdrachtprompt en de scripts voor snelheid, automatisering en extra mogelijkheden.
  
In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken voor het beheren van Microsoft 365 voor:
  
- Extra informatie weergeven die u niet kunt zien in het Microsoft 365-Beheercentrum
    
- Configureer functies en instellingen alleen mogelijk met PowerShell
    
- Bulk activiteiten uitvoeren
    
- Gegevens filteren
    
- Gegevens afdrukken of opslaan
    
- Meerdere services beheren
    
Houd er rekening mee dat PowerShell voor Microsoft 365 een set modules voor Windows PowerShell is, een opdrachtregelomgeving voor Windows-Services en platformen. In deze omgeving wordt een opdrachtshell taal gemaakt die kan worden uitgebreid met extra modules. U kunt eenvoudige of complexe opdrachten of scripts uitvoeren. Wanneer u bijvoorbeeld de modules PowerShell voor Microsoft 365 installeert en verbinding maakt met uw Microsoft 365-abonnement, kunt u de volgende opdracht uitvoeren om alle gebruikerspostvakken voor Microsoft Exchange Online weer te geven:
  
```powershell
Get-Mailbox
```

U kunt ook de lijst met postvakken downloaden met behulp van het Microsoft 365-Beheercentrum, maar u kunt wel de items in alle lijsten tellen voor alle sites voor al uw web apps.
  
PowerShell voor Microsoft 365 is bedoeld voor hulp bij het beheren van Microsoft 365, het niet vervangen van het Microsoft 365-Beheercentrum. Beheerders moeten PowerShell voor Microsoft 365 kunnen gebruiken, omdat er enkele configuratieprocedures zijn die alleen kunnen worden uitgevoerd via de PowerShell-opdrachten voor Microsoft 365. Voor deze gevallen moet u weten hoe u het volgende kunt doen:
  
- Installeer de PowerShell voor Microsoft 365-modules (slechts één keer uitgevoerd voor elke beheerders computer).
    
- Maak verbinding met uw Microsoft 365-abonnement (één keer voor elke PowerShell-sessie).
    
- Verzamel de gegevens die u nodig hebt om de vereiste PowerShell voor Microsoft 365-opdrachten uit te voeren.
    
- Voer PowerShell voor Microsoft 365-opdrachten uit.
    
Wanneer u deze basisvaardigheden hebt leren, hoeft u uw postvak gebruikers niet te vermelden met de opdracht **Get-postvak** . U hoeft ook niet te leren hoe u een nieuwe opdracht kunt maken, zoals met de opdracht eerder is vermeld voor het tellen van alle items in alle lijsten voor alle sites van alle webapps. Microsoft en de community van beheerders kunnen u helpen bij het uitvoeren van dergelijke taken.
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>PowerShell voor Microsoft 365 kan informatie onthullen die u niet kunt zien in het Microsoft 365-Beheercentrum

In het Microsoft 365-Beheercentrum wordt veel nuttige informatie weergegeven. In deze weergave worden niet alle mogelijke informatie weergegeven die Microsoft 365 biedt over gebruikers, licenties, postvakken en sites. Hier ziet u een voorbeeld van *gebruikers en groepen* in het microsoft 365-Beheercentrum:
  
![Voorbeeld van de weergave van gebruikers en groepen in het Microsoft 365-Beheercentrum.](../media/o365-powershell-users-and-groups.png)
  
Deze weergave bevat de informatie die u nodig hebt in een groot aantal gevallen. Er zijn echter situaties waarin u meer nodig hebt. Microsoft 365 Licensing (en de Microsoft 365-functies die beschikbaar zijn voor een gebruiker), is bijvoorbeeld afhankelijk van de geografische locatie van de gebruiker. De beleidsregels en functies die u kunt verlengen naar een gebruiker die niet in de Verenigde Staten woont, zijn mogelijk niet hetzelfde als de gebruikers die u in India of in België kunt uitbreiden. Voer de volgende stappen uit in het Microsoft 365-Beheercentrum om de geografische locatie van een gebruiker te bepalen:
  
1. Dubbelklik op de **weergavenaam**van de gebruiker.
    
2. Selecteer in het deelvenster weergave van de gebruikerseigenschappen de optie **Details**.
    
3. Selecteer **extra details**in het detail scherm.
    
4. Schuif totdat u het **land of de regio**van de kop vindt:
    
     ![Voorbeeld van de regiogegevens voor een gebruiker in het Microsoft 365-Beheercentrum.](../media/o365-powershell-usage-location.png)
  
5. Schrijf de weergavenaam en locatie van de gebruiker op een vel papier, of kopieer en plak deze in Kladblok.
    
Voor elke gebruiker moet u deze procedure herhalen. Als u veel gebruikers hebt, kan dit een zeer vervelend proces zijn. Met PowerShell voor Microsoft 365 kunt u deze informatie voor al uw gebruikers weergeven met behulp van de volgende opdracht:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam. U dient deze cmdlets uit te voeren vanuit Windows PowerShell.
>

Hier ziet u een voorbeeld van de resultaten:
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

De uitleg van deze PowerShell-opdracht is: alle gebruikers in het huidige Microsoft 365-abonnement (**Get-AzureADUser**) krijgen, maar alleen de naam en de locatie weergeven voor elke gebruiker (**Select DisplayName, UsageLocation**).
  
Aangezien PowerShell voor Microsoft 365 ondersteuning biedt voor een schakeloptie voor de shell, kunt u de gegevens die zijn verkregen met de opdracht **Get-AzureADUser** , verder bewerken. Bijvoorbeeld: u wilt deze gebruikers sorteren op hun locatie, met alle Braziliaanse gebruikers samen, alle gebruikers van de Verenigde Staten, enzovoort. Dit is de opdracht:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Hier ziet u een voorbeeld van de resultaten:
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement krijgen, maar alleen de naam en de locatie weergeven voor elke gebruiker en ze eerst sorteren op hun locatie en vervolgens de naam van een gebruiker (**sorteren UsageLocation, DisplayName**).
  
U kunt ook extra filters gebruiken. Als u bijvoorbeeld alleen informatie wilt weergeven over gebruikers die op basis van Brazilië werken, gebruikt u deze opdracht:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Hier ziet u een voorbeeld van de resultaten:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

De uitleg van deze PowerShell-opdracht luidt als volgt: Hiermee krijgt u alle gebruikers in het huidige Microsoft 365-abonnement te zien, waarvan de locatie Brazilië is (**waarbij {$ \_ . UsageLocation-EQ "BR"}**) en geef vervolgens de naam en de locatie voor elke gebruiker weer.
  
 **Een opmerking over grote domeinen**
  
Als u een groot domein hebt met tientallen gebruikers, kunt u een aantal voorbeelden van de voorbeelden in dit artikel weergeven als u wilt beperken. Op basis van factoren zoals computervermogen en de beschikbare bandbreedte van het netwerk kunt u te veel tegelijk doen. Grote organisaties willen wellicht sommige van deze PowerShell-bewerkingen in twee opdrachten verdelen.

Met de volgende opdracht worden bijvoorbeeld alle gebruikersaccounts weergegeven en worden voor elke gebruiker de naam en de locatie weergegeven:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Dit werkt prima voor kleinere domeinen. Maar in een grote organisatie wilt u de werking mogelijk in twee opdrachten verdelen: één opdracht voor het opslaan van de informatie over de gebruikersaccounts in een variabele en een andere opdracht voor het weergeven van de benodigde informatie. Hier ziet u een voorbeeld:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

De uitleg van deze reeks PowerShell-opdrachten luidt als volgt:
1. Alle gebruikers in het huidige Microsoft 365-abonnement krijgen en de informatie opslaan in een variabele met de naam $x (**$x = Get-AzureADUser**).
1.  De inhoud van de variabele *$x*weergeven, maar alleen de naam en de locatie opnemen voor elke gebruiker (**$x | Selecteer DisplayName, UsageLocation**).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 bevat functies die alleen kunnen worden geconfigureerd met PowerShell voor Microsoft 365

Het Microsoft 365-Beheercentrum is bedoeld om toegang te bieden tot veelvoorkomende, nuttige beheertaken die op de meeste omgevingen van toepassing zijn. Met andere woorden: het Microsoft 365-Beheercentrum is zo ontworpen dat de typische beheerder de meest voorkomende beheertaken kan uitvoeren. Er zijn echter wel enkele taken die niet in het Beheercentrum kunnen worden uitgevoerd.
  
Het Skype voor bedrijven online-Beheercentrum biedt bijvoorbeeld een paar opties voor het maken van aangepaste uitnodigingen voor vergaderingen:
  
![Voorbeeld van de weergave van aangepaste uitnodigingen voor vergaderingen in het Skype voor bedrijven online-Beheercentrum.](../media/o365-powershell-meeting-invitation.png)
  
Met deze instellingen kunt u een aanraakscherm voor uitnodigingen voor vergaderingen toevoegen. Er zijn echter meer instellingen voor de configuratie van de vergadering, maar u kunt alleen aangepaste uitnodigingen voor vergaderingen maken. In het volgende voorbeeld is het bijvoorbeeld mogelijk dat vergaderingen:
  
- Anonieme gebruikers om automatisch toegang tot elke vergadering te krijgen.
    
- Deelnemers kunnen de vergadering opnemen.
    
- Alle gebruikers in uw organisatie die als presentator worden aangewezen wanneer ze deelnemen aan de vergadering.
    
Deze instellingen zijn niet beschikbaar in het Skype voor bedrijven online-Beheercentrum. U kunt ze beheren via PowerShell voor Microsoft 365. Dit is een opdracht waarmee u deze drie instellingen uitschakelt:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Om deze opdracht uit te voeren, moet u de [PowerShell-module voor Skype voor bedrijven online ](https://www.microsoft.com/download/details.aspx?id=39366)installeren.
  
De uitleg van deze PowerShell-opdracht luidt als volgt:
 
1. Via de instellingen voor nieuwe vergaderingen in Skype voor bedrijven online (**set-CsMeetingConfiguration**) kunt u instellen dat anonieme gebruikers automatische toegang hebben tot vergaderingen (**-AdmitAnonymousUsersByDefault $False**).
2.  De mogelijkheid voordeel nemers uitschakelen voor het opnemen van vergaderingen (**-AllowConferenceRecording $False**).
3. Wijs niet alle gebruikers in uw organisatie aan als presentatoren (**-DesignateAsPresenter "geen"**).
  
Voer de volgende opdracht uit om deze standaardinstellingen te herstellen (opties in te schakelen):
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Daarnaast zijn er andere soortgelijke scenario's, wat wil zeggen dat beheerders weten dat de PowerShell voor Microsoft 365-opdrachten moet worden uitgevoerd.
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>PowerShell voor Microsoft 365 is ideaal voor bulkbewerkingen

Voorbeeld van een visuele interface, zoals het Microsoft 365-Beheercentrum, zijn zeer waardevol wanneer u één bewerking moet uitvoeren. Als u bijvoorbeeld één gebruikersaccount moet uitschakelen, kunt u het Beheercentrum gebruiken om snel een selectievakje te zoeken en uit te schakelen. Dit kan eenvoudiger zijn dan een soortgelijke bewerking uitvoeren in PowerShell.
  
Als u een groot aantal zaken of bepaalde items binnen een groot aantal andere zaken moet wijzigen, is het mogelijk dat het Microsoft 365-Beheercentrum niet de beste functie is. Stel dat u het voorvoegsel van duizenden telefoonnummers moet wijzigen of dat u de specifieke gebruikers van *Myer* wilt verwijderen van al uw SharePoint Online-sites. Hoe doet u dat in het Microsoft 365-Beheercentrum?
  
Stel dat u in het laatste voorbeeld meerdere honderd SharePoint Online-sites hebt en weet u niet welke Meyer lid is van de SharePoint Online-sites. U moet eerst beginnen bij het Beheercentrum van Microsoft 365 en vervolgens deze procedure uitvoeren voor elke site:
  
1. Selecteer de **URL** van de site.
    
2. Selecteer in het vak Eigenschappen van de **siteverzameling** de koppeling naar het **adres** van de website om de site te openen.
    
3. Selecteer **delen**op de site.
    
4. Selecteer in het dialoogvenster **delen** de koppeling met alle gebruikers die de juiste machtigingen hebben voor de site:
    
     ![Voorbeeld van het weergeven van de leden van een SharePoint Online-site in het SharePoint Online-Beheercentrum.](../media/o365-powershell-view-permissions.png)
  
5. Selecteer in het dialoogvenster **gedeeld met** de optie **Geavanceerd**.
    
6. Blader omlaag in de lijst met gebruikers, zoek en selecteer Ken Myer (ervan uitgaand dat hij of zij machtigingen heeft voor de site), en selecteer **Gebruikersmachtigingen verwijderen**.
    
Dit kan *veel* tijd in beslag nemen voor honderden sites.
  
U kunt ook de volgende opdracht uitvoeren in PowerShell voor Microsoft 365 om ken Myer van al uw sites te verwijderen:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Voor deze opdracht moet u de [PowerShell-module van SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)installeren. 
  
De uitleg van deze PowerShell-opdracht luidt als volgt: alle SharePoint-sites in het huidige Microsoft 365-abonnement (**Get-SPOSite**) krijgen en voor elke site Verwijder ken de Meyer uit de lijst met gebruikers die toegang hebben tot de PowerShell **-site $ \_ . URL-login "kenmyer \@ litwareinc.com"}**).
  
Microsoft 365 vertelt Microsoft het verwijderen van Ken Meyer van elke site, met inbegrip van de personen aan wie hij of zij geen toegang hebben. Daarom geven de resultaten fouten weer voor de sites waartoe hij geen toegang heeft. We kunnen op deze opdracht een extra voorwaarde gebruiken om Ken Meyer alleen te verwijderen van de sites die deze persoon hebben op hun aanmeldingslijst. Maar de fouten die worden geretourneerd, veroorzaken geen schade voor de sites zelf. Het kan een paar minuten duren voordat de opdracht is uitgevoerd op honderden sites, in plaats van uren via het Microsoft 365-Beheercentrum.
  
Hier is nog een voorbeeld van een bulkbewerking. Gebruik deze opdracht om *Bonnie Kearney*, een nieuwe SharePoint-beheerder, toe te voegen aan alle sites in de organisatie:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

De uitleg van deze PowerShell-opdracht is: alle SharePoint-sites in het huidige Microsoft 365-abonnement verkrijgen en voor elke site toestaan dat Bonnie Kearney toegang is door de naam van de gebruiker toe te voegen aan de groep leden van de site (**foreach {add-partner-site $ \_ . URL-login "bkearney \@ litwareinc.com"-groep "leden"}**).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell voor Microsoft 365 is geweldig bij het filteren van gegevens

Met het Microsoft 365-Beheercentrum kunt u de gegevens op verschillende manieren filteren, zodat u gemakkelijk een gerichte subset met gegevens kunt vinden. Met Exchange kunt u bijvoorbeeld eenvoudig filteren op vrijwel elke eigenschap van een gebruikerspostvak. Hier ziet u bijvoorbeeld de lijst met postvakken voor alle gebruikers die in de stad van Bloomington wonen:
  
![Voorbeeld van het gebruik van Geavanceerd zoeken in het Microsoft 365-Beheercentrum voor de lijst met postvakken voor alle gebruikers die in de Bloomington van de stad wonen.](../media/o365-powershell-advanced-search.png)
  
In het Exchange-Beheercentrum kunt u ook filtercriteria combineren. U vindt bijvoorbeeld de postvakken voor alle personen die in Bloomington wonen en werken op de afdeling Financiën.
  
Maar er zijn beperkingen voor wat u kunt doen in het Exchange-Beheercentrum. U kunt bijvoorbeeld niet snel de postvakken vinden van personen die in Bloomington *of* San Diego, of naar de postvakken van alle personen die niet in Bloomington wonen.
  
U kunt de volgende PowerShell voor Microsoft 365-opdracht gebruiken voor het weergeven van een lijst met postvakken voor alle personen die in Bloomington of San Diego wonen:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Hier ziet u een voorbeeld van de resultaten:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement met een postvak in de stad van San Diego of Bloomington (**waarbij {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-en ($ \_ . City-EQ "San Diego"-of $ \_ . Plaats-EQ "Bloomington")}**) en geef vervolgens de naam en plaats voor elk (**Selecteer DisplayName, plaats**).
  
Dit is de opdracht voor het weergeven van alle postvakken voor personen die overal wonen, met uitzondering van Bloomington:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Hier ziet u een voorbeeld van de resultaten:
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement krijgen die een postvak hebben dat zich niet in de plaats van Bloomington bevindt (**waarbij {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-en $ \_ . Plaats-ne "Bloomington"}**) en geef vervolgens de naam en plaats op voor elk.
  
### <a name="use-wildcards"></a>Jokertekens gebruiken

U kunt ook jokertekens in uw PowerShell-filters gebruiken om een deel van een naam te vinden. Stel dat u op zoek bent naar een gebruikersaccount. U kunt ook onthouden dat de achternaam van de gebruiker *Anderson* of misschien *Henderson* of *Jorgenson*.
  
U kunt deze gebruiker in het Microsoft 365-Beheercentrum bijhouden met behulp van het hulpprogramma zoeken en drie verschillende zoekopdrachten uitvoeren:
  
- Eén voor  *Anderson* 
    
- Eén voor  *Henderson* 
    
- Eén voor  *Jorgenson* 
    
Aangezien alle drie deze namen eindigen op ' zoon ', kunt u aangeven dat PowerShell alle gebruikers waarvan de naam eindigt op ' zoon ' weergeven. Dit is de opdracht:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement krijgen, maar u kunt een filter alleen weergeven voor de gebruikers van wie de achternaam eindigt op ' zoon ' (**-filter ' {LastName-like ' \* zoon '} '**). De \* tekenreeks voor een willekeurige willekeurige tekenreeks, zoals de namen van de achternaam van de gebruiker.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>Met PowerShell voor Microsoft 365 kunt u eenvoudig gegevens afdrukken of opslaan

Met het Microsoft 365-Beheercentrum kunt u lijsten met gegevens weergeven. Hier is een voorbeeld van het Beheercentrum van Skype voor bedrijven online met een lijst met gebruikers die zijn ingeschakeld voor Skype voor bedrijven online:
  
![Voorbeeld van het Skype voor bedrijven online-Beheercentrum met een lijst met gebruikers die zijn ingeschakeld voor Skype voor bedrijven online.](../media/o365-powershell-lync-users.png)
  
Als u deze gegevens wilt opslaan in een bestand, moet u deze in een document of Microsoft Excel-werkblad plakken. Voor beide gevallen is extra opmaak nodig. Daarnaast biedt het Microsoft 365-Beheercentrum geen manier om de weergegeven lijst rechtstreeks af te drukken.
  
Gelukkig kunt u PowerShell gebruiken om de lijst niet alleen weer te geven, maar om deze op te slaan in een bestand dat gemakkelijk kan worden geïmporteerd in Excel. Hier ziet u een voorbeeld van een knop om Skype voor bedrijven online-gebruikersgegevens op te slaan in een CSV-bestand (door komma's gescheiden waarden), dat vervolgens eenvoudig kan worden geïmporteerd als een tabel in een Excel-werkblad:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Hier ziet u een voorbeeld van de resultaten:
  
![Voorbeeld van een tabel die in een Excel-werkblad is geïmporteerd voor gebruikersgegevens van Skype voor bedrijven online die zijn opgeslagen in een bestand met door komma's gescheiden waarden.](../media/o365-powershell-data-in-excel.png)
  
De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers van Skype voor bedrijven online in het huidige Microsoft 365-abonnement (**Get-CsOnlineUser**); Download alleen de gebruikersnaam, UPN en locatie (**Selecteer DisplayName, userPrincipalName, UsageLocation**). en sla deze informatie op in een CSV-bestand met de naam C: \\ logboeken \\SfBUsers.csv (**export-csv-pad "C: \\ logs \\SfBUsers.csv"-NoTypeInformation**).
  
U kunt de lijst met opties ook opslaan als een XML-bestand of een HTML-pagina. Met extra PowerShell-opdrachten kunt u de functie rechtstreeks opslaan als een Excel-bestand, met de gewenste aangepaste opmaak.
  
U kunt ook de uitvoer van een PowerShell-opdracht verzenden waarmee een lijst rechtstreeks wordt weergegeven naar de standaardprinter in Windows. Hier ziet u een voorbeeld van een opdracht:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Het afgedrukte document ziet er als volgt uit:
  
![Voorbeeld van een afgedrukt document met de uitvoer van een PowerShell-opdracht die rechtstreeks naar de standaardprinter in Windows is verzonden.](../media/o365-powershell-printed-data.png)
  
De uitleg van deze PowerShell-opdracht luidt als volgt: alle Skype voor bedrijven online-gebruikers in het huidige abonnement van Microsoft 365. alleen de gebruikersnaam, UPN en locatie verkrijgen; en deze informatie vervolgens naar de standaardprinter van Windows (**out-printer**) verzenden.
  
Het afgedrukte document heeft dezelfde eenvoudige opmaak als de weergave in het PowerShell-opdrachtvenster. Als u een harde kopie wilt toevoegen, hoeft u alleen maar iets toe te voegen ** Out-printer** naar het einde van de opdracht.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Met PowerShell voor Microsoft 365 kunt u verschillende server producten beheren

De onderdelen die Microsoft 365 vormen, zijn ontworpen om samen te werken. U kunt bijvoorbeeld een nieuwe gebruiker toevoegen aan Microsoft 365 en u kunt deze gegevens opgeven als de afdelings-en telefoonnummers van de gebruiker. Deze informatie is dan beschikbaar als u de gegevens van de gebruiker opent in een van de 365-services van Microsoft: Skype voor bedrijven online, Exchange of SharePoint.
  
Dat is voor algemene informatie die de producten Suite beslaat. Productspecifieke informatie, zoals informatie over het Exchange-postvak van een gebruiker, is doorgaans niet beschikbaar in de hele suite. Zo is informatie over of het postvak van een gebruiker is ingeschakeld of niet beschikbaar is in het Exchange-Beheercentrum.
  
Stel dat u een rapport wilt maken waarin de volgende informatie voor alle gebruikers wordt weergegeven:
  
- De weergavenaam van de gebruiker
    
- Of de gebruiker een licentie heeft voor Microsoft 365
    
- Of het Exchange-postvak van de gebruiker is ingeschakeld
    
- Of de gebruiker is ingeschakeld voor Skype voor bedrijven online
    
U kunt een dergelijk rapport niet gemakkelijk maken in het Microsoft 365-Beheercentrum. In plaats daarvan moet u een apart document maken om de gegevens op te slaan, zoals een Excel-werkblad. Ga vervolgens naar alle gebruikersnamen en licentiëringsinformatie via het Microsoft 365-Beheercentrum, ga naar postvakgegevens van het Exchange-Beheercentrum, ga naar informatie over Skype voor bedrijven online via het Skype voor bedrijven online-Beheercentrum en combineer deze informatie.
  
Het alternatief is een PowerShell-script gebruiken om het rapport voor u samen te stellen.
  
Het volgende voorbeeldscript is ingewikkelder dan de opdrachten die u tot nu toe hebt gezien in dit artikel. Maar het is mogelijk dat u PowerShell gebruikt om informatie weergaven te maken die moeilijk te vinden zijn. Dit is het script voor de compilatie en de lijst weer te geven die u nodig hebt:
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

Hier ziet u een voorbeeld van de resultaten:
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

De uitleg van dit PowerShell-script luidt als volgt:  

1. Alle gebruikers in het huidige Microsoft 365-abonnement krijgen en de gegevens opslaan in een variabele met de naam *$x* (**$x = Get-AzureADUser**).
1. Een lus starten die wordt uitgevoerd op alle gebruikers in de variabele $x (**foreach ($i in $x)**).  
1. Definieer een variabele met de naam *$y* en sla de informatie over de Postvak in van de gebruiker op (**$y = Get-Mailbox-Identity $i. userPrincipalName**).
1. Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam *IsMailBoxEnabled*. Stel deze in op de waarde van de eigenschap IsMailBoxEnabled van het postvak van de gebruiker (**$i | Add-Member-MemberType NoteProperty-name IsMailBoxEnabled-value $y. IsMailBoxEnabled**).
1. Definieer een variabele met de naam *$y*en sla de informatie over de Skype voor bedrijven online-gegevens van de gebruiker op (**$y = Get-CsOnlineUser-Identity $i. userPrincipalName**).
1. Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam *EnabledForSfB*. Stel deze in op de waarde van de eigenschap ingeschakeld van de Skype voor bedrijven online-gegevens van de gebruiker (**$i | Add-Member-MemberType NoteProperty-name EnabledForSfB-value $y. enabled**).
1. U kunt de lijst met gebruikers weergeven, maar alleen de naam ervan opnemen, ongeacht of ze een licentie hebben en de twee nieuwe eigenschappen om aan te geven of hun postvak is ingeschakeld en of ze zijn ingeschakeld voor Skype voor bedrijven online (**$x | Selecteer DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).
  
## <a name="see-also"></a>Zie ook

[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Windows PowerShell gebruiken om rapporten te maken in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
