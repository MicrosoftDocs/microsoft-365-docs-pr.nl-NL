---
title: Waarom u PowerShell moet gebruiken voor Microsoft 365
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
description: 'Samenvatting: Begrijp waarom u PowerShell moet gebruiken om Microsoft 365 te beheren, in sommige gevallen efficiënter en in andere gevallen uit noodzaak.'
ms.openlocfilehash: cbbceddc98bebaed030f4cff2f183d473d716df6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288465"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Waarom u PowerShell moet gebruiken voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met de Microsoft 365-beheercentrum kunt u uw Microsoft 365 gebruikersaccounts en -licenties beheren. U kunt ook uw Microsoft 365 beheren, zoals Exchange Online, Teams en SharePoint Online. Als u in plaats daarvan PowerShell gebruikt om deze services te beheren, kunt u gebruikmaken van de taalomgeving voor opdrachtregel en scripting voor snelheid, automatisering en extra mogelijkheden.

In dit artikel wordt beschreven hoe u PowerShell kunt gebruiken om Microsoft 365 beheren:

- Extra informatie die u niet kunt zien in de Microsoft 365-beheercentrum

- Functies en instellingen configureren alleen mogelijk met PowerShell

- Bulkbewerkingen uitvoeren

- Gegevens filteren

- Gegevens afdrukken of opslaan

- Beheren in verschillende services

Houd er rekening mee dat PowerShell voor Microsoft 365 een set modules is voor Windows PowerShell, een opdrachtregelomgeving voor Windows services en platforms. In deze omgeving wordt een opdrachtshelltaal gemaakt die kan worden uitgebreid met extra modules. Het biedt een manier om eenvoudige of complexe opdrachten of scripts uit te voeren. Nadat u bijvoorbeeld de PowerShell voor Microsoft 365-modules hebt geïnstalleerd en verbinding hebt gemaakt met uw Microsoft 365-abonnement, kunt u de volgende opdracht uitvoeren om alle gebruikerspostvakken voor Microsoft Exchange Online:

```powershell
Get-Mailbox
```

U kunt ook de lijst met postvakken krijgen met behulp van de Microsoft 365-beheercentrum, maar het tellen van de items in alle lijsten voor alle sites voor al uw web-apps is niet eenvoudig.

PowerShell voor Microsoft 365 is ontworpen om u te helpen uw Microsoft 365 te beheren, niet om de Microsoft 365-beheercentrum. Beheerders moeten PowerShell kunnen gebruiken voor Microsoft 365 omdat er enkele configuratieprocedures zijn die alleen via PowerShell kunnen worden uitgevoerd voor Microsoft 365 opdrachten. Voor deze gevallen moet u weten hoe u:

- Installeer de PowerShell voor Microsoft 365 modules (slechts één keer uitgevoerd voor elke beheerderscomputer).

- Verbinding maken uw Microsoft 365 abonnement (één keer voor elke PowerShell-sessie).

- Verzamel de gegevens die nodig zijn om de vereiste PowerShell voor Microsoft 365 uitvoeren.

- PowerShell uitvoeren voor Microsoft 365 opdrachten.

Nadat u deze basisvaardigheden hebt geleerd, hoeft u uw postvakgebruikers niet op te geven met behulp van de **opdracht Postvak** krijgen. U hoeft ook niet te begrijpen hoe u een nieuwe opdracht maakt, zoals de opdracht die eerder is geciteerd om alle items in alle lijsten voor alle sites voor al uw web-apps te tellen. Microsoft en de community van beheerders kunnen u zo nodig helpen met dergelijke taken.

## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>PowerShell voor Microsoft 365 kan informatie onthullen die u niet kunt zien met de Microsoft 365-beheercentrum

De Microsoft 365-beheercentrum bevat veel nuttige informatie. Er worden echter niet alle mogelijke gegevens weergegeven die Microsoft 365 over gebruikers, licenties, postvakken en sites. Hier volgen een voorbeeld voor *gebruikers en groepen* in de Microsoft 365-beheercentrum:

![Voorbeeld van de weergave van gebruikers en groepen in de Microsoft 365-beheercentrum.](../media/o365-powershell-users-and-groups.png)

Deze weergave bevat de informatie die u in veel gevallen nodig hebt. Er zijn echter momenten waarop u meer nodig hebt. De Microsoft 365 licenties (en de Microsoft 365 functies die beschikbaar zijn voor een gebruiker) zijn bijvoorbeeld deels afhankelijk van de geografische locatie van de gebruiker. Het beleid en de functies die u kunt uitbreiden naar een gebruiker die in de Verenigde Staten woont, zijn mogelijk niet hetzelfde als het beleid dat u kunt uitbreiden naar een gebruiker in India of België. Volg deze stappen in het Microsoft 365-beheercentrum om de geografische locatie van een gebruiker te bepalen:

1. Dubbelklik op de weergavenaam **van de gebruiker.**

2. Selecteer details in het weergavevenster **gebruikerseigenschappen.**

3. Selecteer in de detailweergave **aanvullende details.**

4. Scroll totdat u de kop **Land of regio hebt gevonden:**

     ![Voorbeeld van de regiogegevens voor een gebruiker in de Microsoft 365-beheercentrum.](../media/o365-powershell-usage-location.png)

5. Schrijf de weergavenaam en locatie van de gebruiker op een stuk papier of kopieer en plak deze in Kladblok.

U moet deze procedure voor elke gebruiker herhalen. Als u veel gebruikers hebt, kan dit proces vervelend zijn. Met PowerShell voor Microsoft 365 kunt u deze informatie voor al uw gebruikers weergeven met de volgende opdracht:

```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory module voor Windows PowerShell module en cmdlets met *Msol* in hun naam. U moet deze cmdlets uitvoeren vanaf Windows PowerShell.
>

Hier volgen een voorbeeld van de resultaten:

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

De interpretatie van deze PowerShell-opdracht is: Alle gebruikers in het huidige **Microsoft 365-abonnement (Get-AzureADUser)** krijgen, maar alleen de naam en locatie voor elke gebruiker weergeven **(Selecteer DisplayName, UsageLocation).**

Omdat PowerShell voor Microsoft 365 een opdrachtshelltaal ondersteunt, kunt u de gegevens die zijn verkregen met de **opdracht Get-AzureADUser verder** bewerken. Misschien wilt u deze gebruikers bijvoorbeeld sorteren op hun locatie, alle Braziliaanse gebruikers groeperen, alle Amerikaanse gebruikers bij elkaar, en ga zo maar door. Hier is de opdracht:

```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Hier volgen een voorbeeld van de resultaten:

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

De interpretatie van deze PowerShell-opdracht is: Alle gebruikers in het huidige Microsoft 365-abonnement krijgen, maar alleen de naam en locatie voor elke gebruiker weergeven en ze eerst sorteren op hun locatie en vervolgens op hun naam **(Sort UsageLocation, DisplayName).**

U kunt ook extra filteren gebruiken. Als u bijvoorbeeld alleen informatie wilt zien over gebruikers die in Brazilië zijn gevestigd, gebruikt u deze opdracht:

```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation
```

Hier volgen een voorbeeld van de resultaten:

```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

De interpretatie van deze PowerShell-opdracht is: Alle gebruikers in het huidige abonnement Microsoft 365 waarvan de locatie Brazilië is (**Where {$ \_ . UsageLocation -eq "BR"}**) en geef vervolgens de naam en locatie weer voor elke gebruiker.

 **Een notitie over grote domeinen**

Als u een groot domein met tienduizenden gebruikers hebt, kan het proberen van enkele voorbeelden in dit artikel leiden tot beperking. Op basis van factoren zoals rekenkracht en beschikbare netwerkbandbreedte probeert u mogelijk te veel tegelijk te doen. Grote organisaties willen sommige van deze PowerShell-bewerkingen mogelijk splitsen in twee opdrachten.

De volgende opdracht retourneert bijvoorbeeld alle gebruikersaccounts en geeft de naam en locatie voor elk account weer:

```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Dat werkt prima voor kleinere domeinen. Maar in een grote organisatie kunt u deze bewerking opsplitsen in twee opdrachten: één opdracht om de gebruikersaccountgegevens op te slaan in een variabele en een andere opdracht om de benodigde informatie weer te geven. Hier volgt een voorbeeld:

```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

De interpretatie van deze set PowerShell-opdrachten is:
1. Alle gebruikers in het huidige abonnement Microsoft 365 en sla de gegevens op in een variabele met de naam $x (**$x = Get-AzureADUser**).
1.  De inhoud van de variabele $x *weergeven,* maar alleen de naam en locatie voor elke gebruiker (**$x | Selecteer DisplayName, UsageLocation**).

## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 functies die u alleen met PowerShell kunt configureren voor Microsoft 365

De Microsoft 365-beheercentrum is bedoeld om toegang te bieden tot algemene, nuttige beheertaken die van toepassing zijn op de meeste omgevingen. Met andere woorden, de Microsoft 365-beheercentrum zo ontworpen dat de gewone beheerder de meest voorkomende beheertaken kan uitvoeren. Er zijn echter enkele taken die niet kunnen worden uitgevoerd in het beheercentrum.

Het online-beheercentrum Skype voor Bedrijven biedt bijvoorbeeld een aantal opties voor het maken van aangepaste uitnodigingen voor een vergadering:

![Voorbeeld van de weergave van aangepaste uitnodigingen voor een vergadering in het Skype voor Bedrijven Online-beheercentrum.](../media/o365-powershell-meeting-invitation.png)

Met deze instellingen kunt u een vleugje persoonlijke instellingen en professionaliteit toevoegen aan uitnodigingen voor een vergadering. Maar er is meer aan instellingen voor vergaderingsconfiguraties dan alleen het maken van aangepaste uitnodigingen voor een vergadering. Vergaderingen staan bijvoorbeeld standaard het volgende toe:

- Anonieme gebruikers om automatisch toegang te krijgen tot elke vergadering.

- Deelnemers om de vergadering op te nemen.

- Alle gebruikers van uw organisatie die als presentator moeten worden aangewezen wanneer ze deelnemen aan de vergadering.

Deze instellingen zijn niet beschikbaar in het Skype voor Bedrijven Online-beheercentrum. U kunt ze vanuit PowerShell voor Microsoft 365. Hier is een opdracht die deze drie instellingen uit schakelt:

```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Als u deze opdracht wilt uitvoeren, moet u de Skype voor Bedrijven [Online PowerShell-module installeren.](https://www.microsoft.com/download/details.aspx?id=39366)

De interpretatie van deze PowerShell-opdracht is:

1. Schakel in de instellingen voor nieuwe Skype voor Bedrijven **Online-vergaderingen (Set-CsMeetingConfiguration)** uit dat anonieme gebruikers automatisch toegang krijgen tot vergaderingen (**-AdmitAnonymousUsersByDefault $False).**
2.  De mogelijkheid uitschakelen voor deelnemers om vergaderingen op te nemen (**-AllowConferenceRecording $False).**
3. Wijs niet alle gebruikers uit uw organisatie aan als presentatoren (**-DesignateAsPresenter "None"**).

Als u deze standaardinstellingen wilt herstellen (de opties inschakelen), gaat u als volgende opdracht te werk:

```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Er zijn ook andere vergelijkbare scenario's. Daarom moeten beheerders weten hoe ze PowerShell moeten uitvoeren voor Microsoft 365 opdrachten.

## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>PowerShell voor Microsoft 365 is zeer goed voor bulkbewerkingen

Visuele interfaces zoals de Microsoft 365-beheercentrum zijn het meest waardevol wanneer u één bewerking moet uitvoeren. Als u bijvoorbeeld één gebruikersaccount wilt uitschakelen, kunt u het beheercentrum gebruiken om snel een selectievakje te zoeken en uit te schakelen. Dit kan eenvoudiger zijn dan het uitvoeren van een soortgelijke bewerking in PowerShell.

Maar als u veel dingen of bepaalde geselecteerde dingen binnen een grote reeks andere dingen moet wijzigen, is Microsoft 365-beheercentrum mogelijk niet het beste hulpmiddel. Stel dat u het voorvoegsel voor duizenden telefoonnummers moet wijzigen of de specifieke gebruiker *Ken Myer* van al uw onlinesites SharePoint verwijderen. Hoe zou u dat doen in de Microsoft 365-beheercentrum?

In het laatste voorbeeld zegt u dat u enkele honderden SharePoint onlinesites hebt en u niet weet welke Ken Meyer lid is van. U moet beginnen bij de Microsoft 365-beheercentrum en vervolgens deze procedure voor elke site uitvoeren:

1. Selecteer de **URL** van de site.

2. Selecteer in **het vak Eigenschappen van** de siteverzameling de koppeling Adres van **website** om de site te openen.

3. Selecteer delen op **de** site.

4. Selecteer in **het** dialoogvenster Delen de koppeling met alle gebruikers met machtigingen voor de site:

     ![Voorbeeld van het weergeven van de leden van een SharePoint Online-site in het SharePoint Online-beheercentrum.](../media/o365-powershell-view-permissions.png)

5. Selecteer geavanceerd **in het** dialoogvenster Gedeeld **met.**

6. Schuif omlaag in de lijst met gebruikers, zoek en selecteer Ken Myer (ervan uitgaande dat hij machtigingen voor de site heeft) en selecteer **gebruikersmachtigingen verwijderen.**

Dit duurt lang *voor* enkele honderden sites.

Het alternatief is om de volgende opdracht uit te voeren in PowerShell Microsoft 365 Ken Myer van al uw sites te verwijderen:

```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Voor deze opdracht moet u de SharePoint [Online PowerShell-module installeren.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

De interpretatie van deze PowerShell-opdracht is: Alle SharePoint-sites in het huidige **Microsoft 365-abonnement (Get-SPOSite)** en voor elke site verwijderen Ken Meyer uit de lijst met gebruikers die er toegang toe hebben (**ForEach {Remove-SPOUser -Site $ \_ . Url -LoginName "kenmyer \@ litwareinc.com"}**).

We vertellen Microsoft 365 Ken Meyer van elke site te verwijderen, inclusief de site waar hij geen toegang toe heeft. In de resultaten worden dus fouten voor die sites weer te geven die hij niet kan gebruiken. We kunnen een aanvullende voorwaarde voor deze opdracht gebruiken om Ken Meyer alleen te verwijderen van de sites met hem in hun aanmeldingslijst. Maar de fouten die worden geretourneerd, veroorzaken geen schade aan de sites zelf. Het kan enkele minuten duren voordat deze opdracht wordt uitgevoerd op honderden sites, in plaats van uren te werken via de Microsoft 365-beheercentrum.

Hier is nog een voorbeeld van bulkbewerking. Gebruik deze opdracht om *Bonnie Kearney*, een nieuwe beheerder SharePoint, toe te voegen aan alle sites in de organisatie:

```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

De interpretatie van deze PowerShell-opdracht is: Haal alle SharePoint-sites in het huidige Microsoft 365-abonnement op en sta bonnie Kearney voor elke site toegang toe door haar aanmeldingsnaam toe te voegen aan de groep Leden van de site (**ForEach {Add-SPOUser -Site $ \_ . Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).

## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell voor Microsoft 365 is zeer goed in het filteren van gegevens

De Microsoft 365-beheercentrum biedt verschillende manieren om uw gegevens te filteren om eenvoudig een gerichte subset met informatie te vinden. Met Exchange kunt u bijvoorbeeld eenvoudig filteren op vrijwel elke eigenschap van een gebruikerspostvak. Hier is bijvoorbeeld de lijst met postvakken voor alle gebruikers die in de stad Bloomington wonen:

![Voorbeeld van een geavanceerde zoekopdracht in de Microsoft 365-beheercentrum naar de lijst met postvakken voor alle gebruikers die in de stad Bloomington wonen.](../media/o365-powershell-advanced-search.png)

In Exchange beheercentrum kunt u ook filtercriteria combineren. U kunt bijvoorbeeld de postvakken vinden voor alle personen die in Bloomington wonen en op de afdeling Financiën werken.

Maar er zijn beperkingen voor wat u kunt doen in het Exchange beheercentrum. U kunt bijvoorbeeld niet zo gemakkelijk de postvakken vinden van personen die in *Bloomington* of San Diego wonen, of de postvakken voor alle personen die niet in Bloomington wonen.

U kunt de volgende PowerShell voor Microsoft 365 opdracht gebruiken om een lijst met postvakken te krijgen voor alle personen die in Bloomington of San Diego wonen:

```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox&quot; -and ($_.City -eq &quot;San Diego&quot; -or $_.City -eq &quot;Bloomington")} | Select DisplayName, City
```

Hier volgen een voorbeeld van de resultaten:

```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

De interpretatie van deze PowerShell-opdracht is: Alle gebruikers in het huidige Microsoft 365-abonnement krijgen die een postvak hebben in de stad San Diego of Bloomington (**Where {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and ($ \_ ). City -eq "San Diego" -of $ \_ . Plaats -eq "Bloomington")} )** en geef vervolgens de naam en de plaats weer voor elk **(Selecteer DisplayName, Plaats).**

En hier is de opdracht om alle postvakken weer te geven voor mensen die ergens wonen, behalve Bloomington:

```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Hier volgen een voorbeeld van de resultaten:

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

De interpretatie van deze PowerShell-opdracht is: Alle gebruikers in het huidige Microsoft 365-abonnement krijgen die een postvak hebben dat zich niet in de stad Bloomington bevindt (**Where {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and $ \_ . Plaats -ne "Bloomington"} )** en geef vervolgens de naam en de plaats weer voor elk.

### <a name="use-wildcards"></a>Jokertekens gebruiken

U kunt ook jokertekens in uw PowerShell-filters gebruiken om een deel van een naam aan te passen. Stel dat u een gebruikersaccount zoekt. Alles wat u zich kunt herinneren is dat de achternaam van de gebruiker *Was Anderson* of misschien *Henderson* of *Jorgenson.*

U kunt deze gebruiker in de Microsoft 365-beheercentrum met behulp van het zoekprogramma en drie verschillende zoekopdrachten uitvoeren:

- Een voor  *Anderson*

- Een voor  *Henderson*

- Een voor  *Jorgenson*

Omdat alle drie deze namen eindigen op 'zoon', kunt u PowerShell vertellen dat alle gebruikers van wie de naam eindigt op 'zoon' moeten weergeven. Hier is de opdracht:

```powershell
Get-User -Filter '{LastName -like "*son"}'
```

De interpretatie van deze PowerShell-opdracht is: Alle gebruikers in het huidige Microsoft 365-abonnement krijgen, maar gebruik een filter waarin alleen de gebruikers worden vermeld waarvan de achternamen eindigen op 'zoon' (**-Filter '{LastName -like " \* son"}'**). De \* staat voor elke set tekens, die letters zijn in de achternaam van de gebruiker.

## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>PowerShell voor Microsoft 365 maakt het eenvoudig om gegevens af te drukken of op te slaan

Met Microsoft 365-beheercentrum kunt u lijsten met gegevens weergeven. Hier is een voorbeeld van het Skype voor Bedrijven Online-beheercentrum met een lijst met gebruikers die zijn ingeschakeld voor Skype voor Bedrijven Online:

![Voorbeeld van het Skype voor Bedrijven Online-beheercentrum met een lijst met gebruikers die zijn ingeschakeld voor Skype voor Bedrijven Online.](../media/o365-powershell-lync-users.png)

Als u deze gegevens wilt opslaan in een bestand, moet u deze in een document of werkblad Microsoft Excel plakken. Voor beide gevallen is mogelijk extra opmaak vereist. Bovendien biedt de Microsoft 365-beheercentrum geen manier om de weergegeven lijst rechtstreeks af te drukken.

Gelukkig kunt u PowerShell gebruiken om niet alleen de lijst weer te geven, maar ook om deze op te slaan in een bestand dat eenvoudig kan worden geïmporteerd in Excel. Hier ziet u een voorbeeldopdracht om Skype voor Bedrijven Online-gebruikersgegevens op te slaan in een CSV-bestand (door komma's gescheiden waarden), dat vervolgens eenvoudig kan worden geïmporteerd als een tabel in een Excel werkblad:

```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Hier volgen een voorbeeld van de resultaten:

![Voorbeeld van een tabel die is geïmporteerd in een Excel werkblad voor Skype voor Bedrijven onlinegebruikersgegevens die zijn opgeslagen in een door komma's gescheiden waardenbestand.](../media/o365-powershell-data-in-excel.png)

De interpretatie van deze PowerShell-opdracht is: Alle Skype voor Bedrijven Online-gebruikers in het huidige Microsoft 365 **(Get-CsOnlineUser);** alleen de gebruikersnaam, UPN en locatie verkrijgen (**Selecteer DisplayName, UserPrincipalName, UsageLocation**); en sla deze informatie vervolgens op in een CSV-bestand met de naam C: \\ Logs \\SfBUsers.csv (**Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation).**

U kunt ook opties gebruiken om deze lijst op te slaan als een XML-bestand of een HTML-pagina. Met extra PowerShell-opdrachten kunt u deze zelfs rechtstreeks opslaan als een Excel bestand, met elke gewenste aangepaste opmaak.

U kunt ook de uitvoer van een PowerShell-opdracht verzenden waarin een lijst rechtstreeks wordt weergegeven naar de standaardprinter in Windows. Hier is een voorbeeldopdracht:

```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Het afgedrukte document ziet er als volgende uit:

![Voorbeeld van een afgedrukt document dat de uitvoer was van een PowerShell-opdracht die rechtstreeks naar de standaardprinter in Windows.](../media/o365-powershell-printed-data.png)

De interpretatie van deze PowerShell-opdracht is: Alle Skype voor Bedrijven Online-gebruikers in het huidige Microsoft 365 krijgen; alleen de gebruikersnaam, UPN en locatie verkrijgen; en verzendt u deze gegevens naar de standaardprinter Windows printer **(Out-Printer).**

Het afgedrukte document heeft dezelfde eenvoudige opmaak als de weergave in het PowerShell-opdrachtvenster. Als u een kopie wilt downloaden, voegt u een | **Out-Printer** tot het einde van de opdracht.

## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Met PowerShell voor Microsoft 365 kunt u alle serverproducten beheren

De onderdelen die samen Microsoft 365 zijn ontworpen om samen te werken. Stel dat u een nieuwe gebruiker toevoegt aan Microsoft 365 en u dergelijke gegevens opgeeft, zoals de afdeling van de gebruiker en het telefoonnummer. Deze informatie is dan beschikbaar als u toegang hebt tot de gegevens van de gebruiker in een van de Microsoft 365-services: Skype voor Bedrijven Online, Exchange of SharePoint.

Maar dat is voor algemene informatie over de suite met producten. Productspecifieke informatie, zoals informatie over het postvak van een gebruiker Exchange, is meestal niet beschikbaar in de suite. Informatie over het al dan niet inschakelen van het postvak van een gebruiker is bijvoorbeeld alleen beschikbaar in het Exchange beheercentrum.

Stel dat u een rapport wilt maken met de volgende informatie voor al uw gebruikers:

- De weergavenaam van de gebruiker

- Of de gebruiker een licentie voor Microsoft 365

- Of het postvak van Exchange gebruiker is ingeschakeld

- Of de gebruiker is ingeschakeld voor Skype voor Bedrijven Online

U kunt een dergelijk rapport niet eenvoudig in de Microsoft 365-beheercentrum. In plaats daarvan moet u een afzonderlijk document maken om de gegevens op te slaan, zoals een Excel werkblad. Haal vervolgens alle gebruikersnamen en licentiegegevens op van het Microsoft 365-beheercentrum, ontvang postvakgegevens van het Exchange-beheercentrum, haal Skype voor Bedrijven Online-informatie op in het Skype voor Bedrijven Online-beheercentrum en combineer deze gegevens.

Het alternatief is om een PowerShell-script te gebruiken om het rapport voor u samen te stellen.

Het volgende voorbeeldscript is ingewikkelder dan de opdrachten die u tot nu toe in dit artikel hebt gezien. Maar het toont het potentieel van het gebruik van PowerShell om informatieweergaven te maken die anders moeilijk te verkrijgen zijn. Hier ziet u het script om de lijst te compileren en weer te geven die u nodig hebt:

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

Hier volgen een voorbeeld van de resultaten:

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

De interpretatie van dit PowerShell-script is:

1. Alle gebruikers in het huidige abonnement Microsoft 365 en sla de gegevens op in een variabele met de naam *$x* (**$x = Get-AzureADUser**).
1. Start een lus die wordt uitgevoerd over alle gebruikers in de variabele $x (**foreach ($i in $x)**).
1. Definieer een *variabele $y* en sla de postvakgegevens van de gebruiker in op ( $y =**Get-Mailbox -Identity $i.UserPrincipalName).**
1. Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam *IsMailBoxEnabled.* Stel deze in op de waarde van de eigenschap IsMailBoxEnabled van het postvak van de gebruiker **($i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).
1. Definieer een *variabele met* de naam $y en sla de Skype voor Bedrijven Online-gegevens van de gebruiker in op ( $y =**Get-CsOnlineUser -Identity $i.UserPrincipalName).**
1. Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam *EnabledForSfB.* Stel deze in op de waarde van de eigenschap Enabled van de Skype voor Bedrijven Online-gegevens van de gebruiker (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).
1. De lijst met gebruikers weergeven, maar alleen de naam, of ze een licentie hebben, en de twee nieuwe eigenschappen die aangeven of hun postvak is ingeschakeld en of ze zijn ingeschakeld voor Skype voor Bedrijven Online **($x | Selecteer DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).

## <a name="see-also"></a>Zie ook

[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Windows PowerShell gebruiken om rapporten te maken in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)