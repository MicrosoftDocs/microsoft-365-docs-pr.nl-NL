---
title: Gegevens filteren bij het importeren van PST-bestanden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
ms.custom: seo-marvel-apr2020
description: Meer informatie over het filteren van gegevens met de intelligente importfunctie in Office 365 importservice wanneer u PST-bestanden importeert in Office 365.
ms.openlocfilehash: fb978332f70495044a457147d29d8cdcf1194264
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684051"
---
# <a name="filter-data-when-importing-pst-files"></a>Gegevens filteren bij het importeren van PST-bestanden

Gebruik de nieuwe functie Intelligent importeren in de Office 365 Service Importeren om de items in PST-bestanden te filteren die daadwerkelijk worden geïmporteerd in de doelpostvakken. Dit werkt als volgende:
  
- Nadat u een PST-importklus hebt gedaan en indient, worden PST-bestanden geüpload naar een Azure-opslaggebied in de Microsoft-cloud.
  
- Microsoft 365 analyseert de gegevens in de PST-bestanden op een veilige en veilige manier door de leeftijd van de postvakitems en de verschillende berichtentypen in de PST-bestanden te identificeren.
  
- Wanneer de analyse is voltooid en de gegevens klaar zijn om te importeren, hebt u de optie om alle gegevens in de PST-bestanden te importeren of de geïmporteerde gegevens te knippen door filters in te stellen die bepalen welke gegevens worden geïmporteerd. U kunt bijvoorbeeld kiezen voor:
  
  - Importeer alleen items van een bepaalde leeftijd.
  
  - Geselecteerde berichttypen importeren.
  
  - Sluit berichten uit die door bepaalde personen zijn verzonden of ontvangen.
  
- Nadat u de filterinstellingen hebt geconfigureerd, Microsoft 365 alleen de gegevens die voldoen aan de filtercriteria, geïmporteerd naar de doelpostvakken die zijn opgegeven in de importklus.
  
In de volgende afbeelding ziet u het proces intelligent importeren en worden de taken die u uitvoert en de taken die door de Office 365.
  
![Het proces intelligent importeren in Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a>Een PST-importklus maken

- In de stappen in dit onderwerp wordt ervan uit gegaan dat u een PST-import taak hebt gemaakt in de Office 365 Service importeren met behulp van netwerk uploaden of verzenden. Zie een van de volgende onderwerpen voor stapsgewijse instructies:
    
  - [PST-bestanden importeren in Office 365 via het netwerk](use-network-upload-to-import-pst-files.md)
    
  - [Verzendstation gebruiken om PST-bestanden te importeren in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Nadat u een importklus hebt gemaakt met behulp van netwerk uploaden, is de status voor de importklus op de pagina Importeren in het Beveiligings- & Compliancecentrum ingesteld op Analyse **in uitvoering,** wat betekent dat Microsoft 365 de gegevens analyseert in de PST-bestanden die u hebt geüpload. Klik **op Vernieuwen** vernieuwen om de status voor de ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) importklus bij te werken. 
    
- Voor importtaken voor schijfzending worden de gegevens geanalyseerd door Microsoft 365 nadat medewerkers van het Microsoft-datacenter uw harde schijf hebben ontvangen en de PST-bestanden naar het Azure-opslaggebied voor uw organisatie hebben geüpload.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Gegevens filteren die worden geïmporteerd in postvakken

Nadat u een PST-importklus hebt gemaakt, volgt u deze stappen om de gegevens te filteren voordat u deze importeert in Office 365.
  
1. Ga naar <https://compliance.microsoft.com> en meld u aan met de referenties van een beheerdersaccount in uw organisatie.
    
2. Klik in het linkerdeelvenster van Microsoft 365 compliancecentrum op **Informatiebeheer** \> **importeren.**
    
    De importtaken voor uw organisatie worden weergegeven op het **tabblad** Importeren. De **waarde Analyse voltooid** in de kolom **Status** geeft de importtaken aan die door de Microsoft 365 zijn geanalyseerd en die u kunt importeren.
    
    ![Volledige analysestatus geeft aan Microsoft 365 gegevens in PST-bestanden heeft geanalyseerd](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Selecteer de importklus die u wilt voltooien en klik **op Importeren in Office 365.**
  
    Er wordt een flyoutpagina weergegeven met informatie over de PST-bestanden en overige informatie over de importtaak.

4. Klik **op Importeren om Office 365.**
    
    De pagina **Gegevens filteren** wordt weergegeven. Het bevat gegevensinzichten over de gegevens in de PST-bestanden voor de importklus, inclusief informatie over de leeftijd van de gegevens. 
    
    ![De pagina Uw gegevens filteren toont gegevensinzichten van de PST-bestanden voor de importklus](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. Ga op een van de volgende opties te werk op basis van het feit of u de gegevens die in Microsoft 365 worden geïmporteerd, wilt knippen onder Wilt u uw gegevens **filteren?**?
  
    a. Klik **op Ja, ik wil deze filteren voordat u importeert** om de gegevens die u importeert te knippen en klik vervolgens op **Volgende.**
  
    De **pagina Gegevens importeren Office 365 pagina** wordt weergegeven met gedetailleerde gegevensinzichten uit de analyse die Microsoft 365 uitgevoerd. 
  
    ![Microsoft 365 gedetailleerde gegevensinzichten van de analyse van de PST-bestanden](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    In de grafiek op deze pagina ziet u de hoeveelheid gegevens die worden geïmporteerd. Informatie over elk berichttype dat in de PST-bestanden wordt gevonden, wordt weergegeven in de grafiek. U kunt de cursor op elke balk plaatsen om specifieke informatie over dat berichttype weer te geven. Er is ook een vervolgkeuzelijst met verschillende leeftijdswaarden op basis van de analyse van de PST-bestanden. Wanneer u een leeftijd selecteert in de vervolgkeuzelijst, wordt de grafiek bijgewerkt om aan te geven hoeveel gegevens voor de geselecteerde leeftijd worden geïmporteerd. 
  
    b. Als u aanvullingsfilters wilt configureren om de hoeveelheid geïmporteerde gegevens te beperken, klikt u op **Meer filteropties.**
  
    ![De filters configureren op de pagina Meer opties om de geïmporteerde gegevens bij te knippen](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    U kunt deze filters configureren:
  
      - **Leeftijd:** selecteer een leeftijd, zodat alleen items die hoger zijn dan de opgegeven leeftijd, worden geïmporteerd. Zie de [sectie Meer informatie](#more-information) voor een beschrijving over hoe Microsoft 365 leeftijdsemmers voor het leeftijdsfilter bepaalt.  
  
      - **Type:** in deze sectie worden alle berichttypen weergegeven die zijn gevonden in de PST-bestanden voor de importklus. U kunt een vakje naast een berichttype dat u wilt uitsluiten, uit- of uit- U kunt het type Ander bericht niet uitsluiten. Zie de [sectie Meer informatie](#more-information) voor een lijst met postvakitems die zijn opgenomen in de categorie Overige.
  
      - **Gebruikers:** u kunt berichten uitsluiten die door bepaalde personen worden verzonden of ontvangen. Als u personen wilt uitsluiten die worden weergegeven in het veld Van:, het veld Aan: of het veld CC: met berichten, klikt u op Gebruikers **uitsluiten** naast dat type geadresseerde. Typ het e-mailadres (SMTP-adres) van de persoon, klik op Pictogram Nieuw toevoegen om deze toe te voegen aan de lijst met uitgesloten gebruikers voor dat type geadresseerde en klik vervolgens op Opslaan om de lijst met uitgesloten gebruikers op te ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) slaan.  
  
        > [!NOTE]
        > Microsoft 365 geeft geen gegevensinzichten weer die het resultaat zijn van het instellen van **het** filter Personen. Als u dit filter echter in stelt om berichten uit te sluiten die door bepaalde personen zijn verzonden of ontvangen, worden deze berichten uitgesloten tijdens het werkelijke importproces. 
  
    c. Klik **op Toepassen** op de pagina Meer **filteropties** om de filterinstellingen op te slaan. 
  
    De gegevensinzichten op de pagina Gegevens importeren **Office 365** pagina worden bijgewerkt op basis van uw filterinstellingen, inclusief de totale hoeveelheid gegevens die worden geïmporteerd op basis van de filterinstellingen. Er wordt ook een overzicht van de filterinstellingen weergegeven. U kunt klikken **op Bewerken** naast een filter om de instelling zo nodig te wijzigen. 
  
    ![De gegevensinzichten worden bijgewerkt op basis van uw filterinstellingen](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Klik op **Volgende**.
  
    Er wordt een statuspagina weergegeven met de filterinstellingen. Nogmaals, u kunt een van de filterinstellingen bewerken.
  
    e. Klik **op Gegevens importeren** om de import te starten. De totale hoeveelheid gegevens die wordt geïmporteerd, wordt weergegeven. 
  
    Of
  
    a. Klik **op Nee, ik wil alles importeren** om alle gegevens in de PST-bestanden te importeren in Office 365 en klik vervolgens op **Volgende.**
  
    b. Klik op **de pagina Gegevens Office 365** importeren op Gegevens importeren **om** de import te starten. De totale hoeveelheid gegevens die wordt geïmporteerd, wordt weergegeven. 
  
6. Klik op **het tabblad** Importeren op  ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) Vernieuwen. De status van de importklus wordt weergegeven in de **kolom Status.**
  
7. Klik op de taak importeren om meer gedetailleerde informatie weer te geven, zoals de status van elk PST-bestand en de filterinstellingen die u hebt geconfigureerd.

## <a name="more-information"></a>Meer informatie

- Hoe bepaalt Microsoft 365 de stappen voor het leeftijdsfilter? Wanneer Microsoft 365 een PST-bestand analyseert, wordt het verzonden of ontvangen tijdstempel van elk item bekeken (als een item zowel een verzonden als ontvangen tijdstempel heeft, is de oudste datum geselecteerd). Vervolgens Microsoft 365 de jaarwaarde voor die tijdstempel en vergelijkt u deze met de huidige datum om de leeftijd van het item te bepalen. Deze leeftijden worden vervolgens gebruikt als de waarden in de vervolgkeuzelijst voor het **filter** Leeftijd. Als een PST-bestand bijvoorbeeld berichten bevat uit 2016, 2015 en 2014, zijn de waarden in het **filter** Leeftijd **1** jaar, **2** jaar en **3 jaar**.
  
- De volgende tabel bevat de berichtentypen  die zijn opgenomen in  de categorie Overige in het **filter** Type op de pagina Meer opties (zie Stap 5b in de vorige procedure). Momenteel kunt u items in de categorie 'Overige' niet uitsluiten wanneer u PST's importeert in Office 365. 
  
    |**Berichtklasse-id**|**Postvakitems die deze berichtenklasse gebruiken**|
    |:-----|:-----|
    |IPM. Activiteit  <br/> |Logboekgegevens  <br/> |
    |IPM.Document  <br/> |Documenten en bestanden (niet gekoppeld aan een e-mailbericht)  <br/> |
    |IPM. Bestand  <br/> |(hetzelfde als IPM.Document)  <br/> |
    |IPM. Opmerking.IMC.Melding  <br/> |Rapporten die zijn verzonden door Internet Mail Verbinding maken, de Exchange Server gateway naar internet  <br/> |
    |IPM. Note.Microsoft.Fax  <br/> |Faxberichten  <br/> |
    |IPM. Note.Rules.Oof.Template.Microsoft  <br/> |Out-of-office autoreply-berichten  <br/> |
    |IPM. Note.Rules.ReplyTemplate.Microsoft  <br/> |Antwoorden die zijn verzonden met een regel voor Postvak IN  <br/> |
    |IPM. OLE. Klas  <br/> |Uitzonderingen voor een terugkerende reeks  <br/> |
    |IPM. Recall.Report  <br/> |Berichten inroepen  <br/> |
    |IPM. Extern  <br/> |Externe e-mailberichten  <br/> |
    |IPM. Rapport  <br/> |Itemstatusrapporten  <br/> |
