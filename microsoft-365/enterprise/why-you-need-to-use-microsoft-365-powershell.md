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
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688970"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Waarom u PowerShell voor Microsoft 365 moet gebruiken

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met het Microsoft 365-Beheercentrum kunt u niet alleen uw gebruikersaccounts en licenties van Microsoft 365 beheren, maar u kunt ook uw Microsoft 365-Services beheren, zoals Exchange Online, teams en SharePoint Online. U kunt deze elementen echter ook beheren met PowerShell-opdrachten, waarbij u gebruikmaakt van een omgeving voor de opdrachtprompt en de scripts voor snelheid, automatisering en extra mogelijkheden.
  
In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken voor het beheren van Microsoft 365:
  
- Extra informatie weergeven die u niet kunt vinden in het Microsoft 365-Beheercentrum
    
- Configureer functies en instellingen alleen mogelijk met PowerShell
    
- Bulk activiteiten uitvoeren
    
- Gegevens filteren
    
- Gegevens afdrukken of opslaan
    
- Meerdere services beheren
    
Voordat u begint, begrijpt u dat PowerShell voor Microsoft 365 een set modules voor Windows PowerShell is, een opdrachtregelomgeving voor Windows-Services en platformen. In deze omgeving wordt een taal voor de opdrachtshell gemaakt die kan worden uitgebreid met extra modules en kan een eenvoudige of complexe opdracht of scripts worden uitgevoerd. Wanneer u bijvoorbeeld de modules PowerShell voor Microsoft 365 installeert en verbinding maakt met uw Microsoft 365-abonnement, kunt u deze opdracht uitvoeren om alle gebruikerspostvakken voor Microsoft Exchange Online weer te geven:
  
```powershell
Get-Mailbox
```

U kunt de lijst met postvakken ook eenvoudig uitvoeren met behulp van het Microsoft 365-Beheercentrum, maar u kunt het aantal items in alle lijsten voor alle sites van alle websites niet eenvoudig uitvoeren.
  
Houd er rekening mee dat PowerShell voor Microsoft 365 is ontworpen om het beheren van Microsoft 365 te bevorderen en de mogelijkheid om te zorgen dat u het Microsoft 365-Beheercentrum niet vervangt. Als beheerder dient u minstens vertrouwd te zijn met het gebruik van PowerShell voor Microsoft 365, vanwege enkele configuratieprocedures die alleen kunnen worden uitgevoerd met PowerShell-opdrachten voor Microsoft 365. In deze gevallen moet u weten hoe u dit doet:
  
- Installeer de PowerShell voor Microsoft 365-modules (maar één keer voor elke beheerders computer).
    
- Maak verbinding met uw Microsoft 365-abonnement (eenmaal gedaan voor elke PowerShell-sessie).
    
- Verzamel de gegevens die u nodig hebt om de vereiste PowerShell voor Microsoft 365-opdrachten uit te voeren.
    
- Voer de opdrachten voor PowerShell voor Microsoft 365 uit.
    
Nadat u deze basisvaardigheden hebt leren, bent u niet verplicht de gebruikers van uw postvak in te stellen met de opdracht **Get-Mailbox** , en u bent niet verplicht om te zien hoe u een nieuwe opdracht kunt maken, zoals de vorige, zodat alle items in alle lijsten voor alle websites worden geteld voor alle websites van alle webapps. Microsoft en de community van beheerders kunnen u helpen.
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a>PowerShell voor Microsoft 365 kan aanvullende informatie onthullen die u niet kunt zien in het Microsoft 365-Beheercentrum

Het Microsoft 365-Beheercentrum geeft veel nuttige informatie weer, maar dit betekent niet dat alle mogelijke informatie wordt weergegeven die Microsoft 365 opslaat op gebruikers, licenties, postvakken en sites. Hier ziet u een voorbeeld van **gebruikers en groepen** in het microsoft 365-Beheercentrum:
  
![Voorbeeld van de weergave van gebruikers en groepen in het Microsoft 365-Beheercentrum.](../media/o365-powershell-users-and-groups.png)
  
In veel gevallen wordt hiermee de informatie weergegeven die u moet weten. Er zijn echter situaties waarin u meer nodig hebt. Microsoft 365 Licensing (en de Microsoft 365-functies die beschikbaar zijn voor een gebruiker), zijn bijvoorbeeld afhankelijk van de geografische locatie van die gebruiker. De beleidsregels en functies die u kunt verlengen naar een gebruiker die in de Verenigde Staten woont, kunnen niet hetzelfde zijn als de beleidsregels en functies die u kunt verlengen naar een gebruiker die in India of in België woont. Met het Microsoft 365-Beheercentrum kunt u de geografische locatie van een gebruiker vaststellen aan de hand van de volgende stappen:
  
1. Dubbelklik op de **weergavenaam**van de gebruiker.
    
2. Klik in het deelvenster met eigenschappen van de gebruiker op **Details**.
    
3. Klik in het detail scherm op **extra details**.
    
4. Schuif omlaag totdat u het **land of de regio**van de kop ziet:
    
     ![Voorbeeld van de regiogegevens voor een gebruiker in het Microsoft 365-Beheercentrum.](../media/o365-powershell-usage-location.png)
  
5. Schrijf de weergavenaam en locatie van de gebruiker op een vel papier, of kopieer en plak deze in Kladblok. 
    
Voor elke gebruiker moet u deze procedure herhalen. Voor veel gebruikers kan dit een saaie taak zijn. Met PowerShell voor Microsoft 365 kunt u deze informatie weergeven voor alle gebruikers met de volgende opdracht:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Hier ziet u een voorbeeld van het beeldscherm:
  
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

> [!TIP]
>  De uitleg van deze PowerShell-opdracht is: alle gebruikers in het huidige Microsoft 365-abonnement ( **Get-AzureADUser** ) krijgen, maar alleen de naam en de locatie weergeven voor elke gebruiker ( **Select DisplayName, UsageLocation** ).
  
Aangezien PowerShell voor Microsoft 365 ondersteuning biedt voor een taal in de taal van de opdrachtshell, kunt u de informatie die u hebt verkregen, verder manipuleren met de opdracht **Get-AzureADUser** . Bijvoorbeeld: u wilt deze gebruikers sorteren op hun locatie, met alle Braziliaanse gebruikers samen, alle gebruikers van de Verenigde Staten, enzovoort. Dit is de opdracht:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Hier ziet u een voorbeeld van het beeldscherm:
  
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

> [!TIP]
>  De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement overnemen, maar alleen de naam en de locatie weergeven voor elke gebruiker en ze eerst sorteren op hun locatie en vervolgens de namen ( **Sorteer UsageLocation, DisplayName** ).
  
U kunt ook extra filters gebruiken. Als u bijvoorbeeld alleen informatie wilt weergeven over gebruikers die op basis van Brazilië werken, gebruikt u deze opdracht:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Hier ziet u een voorbeeld van het beeldscherm:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  De uitleg van deze PowerShell-opdracht luidt als volgt: Hiermee krijgt u alle gebruikers in het huidige Microsoft 365-abonnement te zien, waarvan de locatie Brazilië is ( **waarbij {$ \_ . UsageLocation-EQ "BR"}** ) en geef vervolgens de naam en de locatie van de gebruiker op.
  
 **Een korte notitie over grotere domeinen**
  
Als u een zeer groot domein hebt met tientallen gebruikers, kunt u een aantal voorbeelden van het gebruik van dit artikel proberen te beperken. Dat betekent dat, op basis van zaken zoals de kracht en de beschikbare bandbreedte van het netwerk, niet te veel tegelijk werkt. In grote gevallen willen grote organisaties sommige van deze PowerShell-opdrachten voor PowerShell voor Microsoft 365 splitsen in twee opdrachten. Met deze optie worden bijvoorbeeld alle gebruikersaccounts opgevraagd en worden de naam en de locatie van de gebruikersaccounts weergegeven:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Dit werkt prima voor kleinere domeinen. In een grote organisatie moet u de gegevens mogelijk in twee opdrachten splitsen: één opdracht voor het opslaan van de informatie over de gebruikersaccount in een variabele en een andere opdracht om de benodigde informatie weer te geven. Hier ziet u een voorbeeld:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

De uitleg van deze reeks PowerShell-opdrachten luidt als volgt:
- Zorg dat alle gebruikers in het huidige Microsoft 365-abonnement komen te staan en sla de gegevens op in een variabele met de naam $x ( **$x = Get-AzureADUser** ).
- De inhoud van de variabele $x weergeven, maar alleen de naam en de locatie opnemen voor elke gebruiker ( **$x | Selecteer DisplayName, UsageLocation** ).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 bevat functies die alleen kunnen worden geconfigureerd met PowerShell voor Microsoft 365

Het Microsoft 365-Beheercentrum is bedoeld om toegang te bieden tot de meest voorkomende of meest voorkomende beheertaken die voor de meeste personen gelden. Met andere woorden: het Microsoft 365-Beheercentrum is zo ontworpen dat de beheerder van het programma de meest voorkomende beheertaken kan uitvoeren met behulp van het hulpprogramma. Met deze definitie betekent dit dat er enkele taken die niet kunnen worden uitgevoerd, worden uitgevoerd met het Microsoft 365-Beheercentrum.
  
Het Skype voor bedrijven online-Beheercentrum biedt bijvoorbeeld een paar opties voor het maken van aangepaste uitnodigingen voor vergaderingen:
  
![Voorbeeld van de weergave van aangepaste uitnodigingen voor vergaderingen in het Skype voor bedrijven online-Beheercentrum.](../media/o365-powershell-meeting-invitation.png)
  
Met deze instellingen kunt u een aanraakscherm voor uitnodigingen voor vergaderingen toevoegen. Er zijn echter meer instellingen voor de configuratie van de vergadering dan alleen voor het maken van aangepaste uitnodigingen voor vergaderingen. In het volgende voorbeeld is het bijvoorbeeld mogelijk dat vergaderingen:
  
- Anonieme gebruikers om automatisch toegang tot elke vergadering te krijgen.
    
- Deelnemers kunnen de vergadering opnemen.
    
- Alle gebruikers in uw organisatie die als presentator worden aangewezen wanneer ze deelnemen aan de vergadering.
    
Deze instellingen zijn niet beschikbaar in het Skype voor bedrijven online-Beheercentrum. U kunt ze echter wel beheren via PowerShell voor Microsoft 365. Dit is een opdracht waarmee u deze drie instellingen uitschakelt:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Voor deze opdracht moet u de [PowerShell-module voor Skype voor bedrijven online ](https://www.microsoft.com/download/details.aspx?id=39366)installeren. 
  
> [!TIP]
>  De uitleg van deze PowerShell-opdracht is: voor de instellingen voor nieuwe vergaderingen in Skype voor bedrijven online ( **set-CsMeetingConfiguration** ), schakelt u toestaan dat anonieme gebruikers geen toegang hebben tot vergaderingen (- **AdmitAnonymousUsersByDefault $False** ), schakelt u de mogelijkheid voordeel nemers uit om vergaderingen op te nemen ( **-AllowConferenceRecording $False** ) en niet alle gebruikers in uw organisatie als presentatoren ( **-DesignateAsPresenter**
  
Als u van gedachten verandert en deze standaardinstellingen wilt herstellen (al zijn ingeschakeld), voert u deze opdracht uit:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Dit is slechts één voorbeeld. Er zijn andere redenen waarom u, als beheerder, moet worden vertrouwd met het uitvoeren van opdrachten van PowerShell voor Microsoft 365.
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a>PowerShell voor Microsoft 365 is geweldig bij het uitvoeren van bulk activiteiten

Historisch, visuele interfaces zoals het Microsoft 365-Beheercentrum zijn vooral handig wanneer u één bewerking wilt uitvoeren. Als u bijvoorbeeld één gebruikersaccount wilt uitschakelen, kunt u het Microsoft 365-Beheercentrum gebruiken om snel een selectievakje te zoeken en uit te schakelen. Dit kan eenvoudiger zijn dan een soortgelijke bewerking uitvoeren in PowerShell.
  
Als u een groot aantal zaken of bepaalde items binnen een groot aantal andere zaken moet wijzigen, is het mogelijk dat u het Microsoft 365-Beheercentrum niet het beste gebruikt voor uw tijd. Als u bijvoorbeeld het voorvoegsel van duizenden telefoonnummers moet wijzigen of als u een specifieke gebruiker, Ken Myer, wilt verwijderen uit al uw SharePoint Online-sites, hoe wilt u dit doen in het Microsoft 365-Beheercentrum?
  
In het tweede voorbeeld hebt u verschillende honderd SharePoint Online-sites en weet u niet zeker welke namen van Meyer lid zijn. Dat betekent dat u eerst moet beginnen bij het Beheercentrum van Microsoft 365 en vervolgens deze procedure voor elke site moet uitvoeren:
  
1. Klik op de **URL** van de site.
    
2. Klik in het dialoogvenster **Eigenschappen van siteverzameling** op de koppeling naar het **adres** van de website om de site te openen.
    
3. Klik op de site op **delen**.
    
4. Klik in het dialoogvenster **delen** op de koppeling waarmee u alle gebruikers ziet met een machtiging voor de site:
    
     ![Voorbeeld van het weergeven van de leden van een SharePoint Online-site in het SharePoint Online-Beheercentrum.](../media/o365-powershell-view-permissions.png)
  
5. Klik in het dialoogvenster **gedeeld met** op **Geavanceerd**.
    
6. Blader omlaag in de lijst met gebruikers, zoek en selecteer Ken Myer (ervan uitgaand dat hij of zij machtigingen heeft voor de site), en klik vervolgens op **Gebruikersmachtigingen verwijderen**.
    
Dit kan veel tijd in beslag nemen voor meerdere honderden sites.
  
U kunt ook PowerShell voor Microsoft 365 gebruiken en de volgende opdracht om ken Myer van al uw sites te verwijderen:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Voor deze opdracht moet u de [PowerShell-module van SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)installeren. 
  
> [!TIP]
>  De uitleg van deze PowerShell-opdracht luidt als volgt: Zorg dat alle SharePoint-sites in het huidige Microsoft 365-abonnement ( **Get-SPOSite** ) en voor elke site worden verwijderd uit de lijst met gebruikers die toegang hebben tot de PowerShell **-site $ \_ . URL-login "kenmyer@litwareinc.com"}** ).
  
Aangezien we Microsoft 365 vertellen dat ze Ken Meyer van elke site te verwijderen, waaronder de gebruikers die hij niet toegang hebben, wordt in de weergave van deze opdracht fouten weergegeven voor de sites waartoe hij momenteel geen toegang heeft. We kunnen met een extra voorwaarde voor deze opdracht de sleutel Meyer alleen verwijderen van de sites die deze hebben in de aanmeldingslijst, maar de vermelde fouten veroorzaken geen schade voor de sites zelf. Het kan een paar minuten duren voordat de opdracht is uitgevoerd op honderden sites, in plaats van uren via het Microsoft 365-Beheercentrum.
  
Hier is nog een voorbeeld van een bulkbewerking. Gebruik deze opdracht om Bonnie Kearney, een nieuwe SharePoint-beheerder, toe te voegen aan alle sites in de organisatie:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  De uitleg van deze PowerShell-opdracht is: alle SharePoint-sites in het huidige Microsoft 365-abonnement en voor elke site gebruiken om de Bonnie Kearney toegang toe te voegen aan de groep leden van de site ( **foreach {add-partner-site $ \_ . URL-login "bkearney@litwareinc.com"-groep "leden"}** ).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell voor Microsoft 365 is geweldig bij het filteren van gegevens

Met het Microsoft 365-Beheercentrum kunt u op verschillende manieren gegevens filteren om snel en eenvoudig een gerichte subset met informatie te vinden. Met Exchange kunt u bijvoorbeeld eenvoudig filteren op vrijwel elke eigenschap van een gebruikerspostvak. Hier ziet u bijvoorbeeld de lijst met postvakken voor alle gebruikers die in de plaats van Bloomington wonen:
  
![Voorbeeld van het gebruik van Geavanceerd zoeken in het Microsoft 365-Beheercentrum voor de lijst met postvakken voor alle gebruikers die in de Bloomington van de stad wonen.](../media/o365-powershell-advanced-search.png)
  
In het Exchange-Beheercentrum kunt u ook filtercriteria combineren. U vindt bijvoorbeeld de postvakken voor alle personen die in Bloomington wonen en die op de afdeling financiën werken. 
  
Er zijn echter beperkingen voor wat u kunt doen in het Exchange-Beheercentrum. U kunt bijvoorbeeld de postvakken vinden van personen die in Bloomington of San Diego, of naar de postvakken van de mensen die niet in Bloomington wonen. 
  
Met PowerShell voor Microsoft 365 kunt u een lijst met postvakken krijgen van alle personen die live in de steden van Bloomington of San Diego met deze opdracht:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Hier ziet u een voorbeeld van het beeldscherm:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  De uitleg van deze PowerShell-opdracht is: alle gebruikers in het huidige abonnement van Microsoft 365 met een postvak in de steden van een San Diego of Bloomington ( **waarbij {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-en ($ \_ . City-EQ "San Diego"-of $ \_ . Plaats-EQ "Bloomington")}** ) en geef vervolgens de naam en de plaats voor elk van de gebruikers ( **Selecteer DisplayName, plaats** ).
  
Als u alle postvakken wilt weergeven voor personen die wonen, met uitzondering van Bloomington, is dit de opdracht:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Hier ziet u een voorbeeld van het beeldscherm:
  
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

> [!TIP]
>  De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement krijgen die een postvak hebben dat zich niet in de plaats van Bloomington bevindt ( **waarbij {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-en $ \_ . Plaats-ne "Bloomington"}** ) en geef vervolgens de naam en plaats op voor elk.
  
U kunt ook jokertekens in uw PowerShell-filters gebruiken om een deel van een naam te vinden. Stel dat u op zoek bent naar een gebruikersaccount en dat u zeker weet dat de achternaam van de persoon is, of misschien Henderson, of misschien de naam Jorgenson.
  
U kunt deze gebruiker in het Microsoft 365-Beheercentrum bijhouden met behulp van het hulpprogramma zoeken en drie verschillende zoekopdrachten uitvoeren:
  
- Eén voor  *Anderson* 
    
- Eén voor  *Henderson* 
    
- Eén voor  *Jorgenson* 
    
Aangezien alle drie deze namen eindigen op ' zoon ', kunt u aangeven dat PowerShell alle gebruikers waarvan de naam eindigt op ' zoon ' weergeven. Dit is de opdracht:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  De uitleg van deze PowerShell-opdracht is: alle gebruikers in het huidige Microsoft 365-abonnement gebruiken, maar u kunt een filter gebruiken dat alleen de gebruikers bevat waarvan de achternaam eindigt op ' zoon ' ( **-filter ' {LastName-like ' \* zoon '} '** ). De \* tekenreeks voor een willekeurige willekeurige tekenreeks, met letters in het geval van de achternaam van de gebruiker.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>Met PowerShell voor Microsoft 365 kunt u eenvoudig gegevens afdrukken of opslaan

Met het Microsoft 365-Beheercentrum kunt u lijsten met gegevens weergeven. Hier ziet u een voorbeeld van het Skype voor bedrijven online-Beheercentrum met een lijst met gebruikers die zijn ingeschakeld voor Skype voor bedrijven online:
  
![Voorbeeld van het Skype voor bedrijven online-Beheercentrum met een lijst met gebruikers die zijn ingeschakeld voor Skype voor bedrijven online.](../media/o365-powershell-lync-users.png)
  
Als u deze gegevens wilt opslaan in een bestand, moet u deze kopiëren en plakken in een document of Excel. In beide gevallen is er mogelijk extra opmaak nodig voor de kopie. Daarnaast biedt het Microsoft 365-Beheercentrum geen manier om de weergegeven lijst rechtstreeks af te drukken.
  
Gelukkig kunt u PowerShell gebruiken om de lijst niet alleen weer te geven en deze op te slaan in een bestand dat u eenvoudig kunt importeren in Excel. Hier ziet u een voorbeeld van een knop om Skype voor bedrijven online-gebruikersgegevens op te slaan in een CSV-bestand (door komma's gescheiden waarden), een bestand dat gemakkelijk kan worden geïmporteerd als een tabel in een Excel-werkblad:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Hier ziet u een voorbeeld van het beeldscherm:
  
![Voorbeeld van een tabel die in een Excel-werkblad is geïmporteerd voor gebruikersgegevens van Skype voor bedrijven online die zijn opgeslagen in een CSV-bestand (door komma's gescheiden waarden).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  De uitleg van deze PowerShell-opdracht is: Haal alle gebruikers van Skype voor bedrijven online in het huidige Microsoft 365-abonnement ( **Get-CsOnlineUser** ), vraag alleen de gebruikersnaam, de UPN en de locatie op ( **Selecteer DisplayName, userPrincipalName, UsageLocation** ) en sla deze informatie vervolgens op in het CSV-bestand met de naam C: \\ Logboeken \\SfBUsers.csv ( **export- \\ \\SfBUsers.csv CSV**
  
U kunt ook opties gebruiken om deze lijst op te slaan als een XML-bestand of als een HTML-pagina. Met extra PowerShell-opdrachten kunt u de functie rechtstreeks opslaan als een Excel-bestand, met eventueel aangepaste opmaak. 
  
U kunt ook de uitvoer van een PowerShell-opdracht verzenden waarmee een lijst rechtstreeks wordt weergegeven naar de standaardprinter in Windows. Hier ziet u een voorbeeld van een opdracht:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Het afgedrukte document ziet er als volgt uit:
  
![Voorbeeld van een document dat de uitvoer is van een PowerShell-opdracht die rechtstreeks naar de standaardprinter in Windows werd genoemd.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  De uitleg van deze PowerShell-opdracht is: Download alle gebruikers van Skype voor bedrijven online in het huidige Microsoft 365-abonnement, verkrijg alleen de gebruikersnaam, UPN en locatie, en stuur deze informatie naar de standaardprinter van Windows ( **out-printer** ).
  
Het afgedrukte document heeft dezelfde eenvoudige opmaak als de weergave in het PowerShell-opdrachtvenster, maar nadat u een PowerShell-opdracht hebt gemaakt om een lijst te maken die u nodig hebt, hoeft u alleen maar de tekst toe **te voegen. Uitchecken** naar het einde van de opdracht, zodat u kunt werken met een afdruk.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Met PowerShell voor Microsoft 365 kunt u verschillende server producten beheren

De verschillende onderdelen waaruit Microsoft 365 wordt gebruikt, zijn ontworpen om samen te werken. U kunt bijvoorbeeld een nieuwe gebruiker toevoegen aan Microsoft 365 en wanneer u dit doet, geeft u deze informatie op als de afdeling en het telefoonnummer van de gebruiker. Deze informatie is dan beschikbaar als u de gegevens van de gebruiker opent met behulp van een van de Microsoft 365-Services: Skype voor bedrijven online, Exchange of SharePoint Online.
  
Dat is voor algemene informatie die de producten Suite beslaat. Productspecifieke informatie: voor informatie over het Exchange-postvak van een gebruiker: is doorgaans niet beschikbaar in de hele suite. Als u bijvoorbeeld wilt weten of het postvak van een gebruiker is ingeschakeld of niet, is deze informatie alleen beschikbaar in het Exchange-Beheercentrum. 
  
Stel dat u een rapport wilt maken waarin de volgende informatie voor alle gebruikers wordt weergegeven:
  
- De weergavenaam van de gebruiker
    
- Of de gebruiker een licentie heeft voor Microsoft 365
    
- Of het Exchange-postvak van de gebruiker is ingeschakeld
    
- Of de gebruiker is ingeschakeld voor Skype voor bedrijven online
    
U kunt het Microsoft 365-Beheercentrum momenteel niet gebruiken om eenvoudig een dergelijk rapport te maken. In plaats daarvan moet u een afzonderlijk document maken om de gegevens op te slaan, zoals een Excel-werkblad, en alle gebruikersnamen en licentie-informatie krijgen via het Microsoft 365-Beheercentrum, informatie over de Postvak krijgen via het Exchange-Beheercentrum en vervolgens de gegevens in het Skype voor bedrijven online-Beheercentrum verzamelen en combineren.
  
Het alternatief is een PowerShell-script gebruiken om dit rapport voor u samen te stellen.
  
Het volgende voorbeeldscript is ingewikkelder dan de opdrachten die u tot nu toe hebt gezien in dit artikel. Maar het is mogelijk dat het gebruik van PowerShell voor het maken van weergaven van informatie die zeer moeilijk te doen zijn. Hier is het script waarmee de benodigde lijst kan worden gecompileerd en weergegeven:
  
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

Hier ziet u een voorbeeld van het beeldscherm:
  
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

- Zorg dat alle gebruikers in het huidige Microsoft 365-abonnement komen te staan en sla de gegevens op in een variabele met de naam $x ( **$x = Get-AzureADUser** ).
- Een lussen starten die worden uitgevoerd op alle gebruikers in de variabele met de naam $x ( **foreach ($i in $x)** ).  
- Definieer een variabele met de naam $y en sla de informatie over het postvak van de gebruiker op ( **$y = Get-Mailbox-Identity $i. userPrincipalName** ).
- Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam IsMailBoxEnabled en stel deze in op de waarde van de eigenschap IsMailBoxEnabled van het postvak van de gebruiker ( **$i | Add-member-MemberType NoteProperty-name IsMailboxEnabled-value $y. IsMailboxEnabled** ).
- Definieer een variabele met de naam $y en sla de informatie over de Skype voor bedrijven online-gegevens van de gebruiker op ( **$y = Get-CsOnlineUser-Identity $i. userPrincipalName** ).
- Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam EnabledForSfB en stel deze in op de waarde van de eigenschap ingeschakeld van de Skype voor bedrijven online-informatie van de gebruiker ( **$i | Add-member-MemberType NoteProperty-name EnabledForSfB-value $y. enabled** ).
- U kunt de lijst met gebruikers weergeven, maar alleen de naam ervan opnemen, ongeacht of ze een licentie hebben en de twee nieuwe eigenschappen om aan te geven of hun postvak is ingeschakeld en of ze zijn ingeschakeld voor Skype voor bedrijven online ( **$x | Selecteer DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).
  
## <a name="see-also"></a>Zie ook

[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Windows PowerShell gebruiken om rapporten te maken in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)

