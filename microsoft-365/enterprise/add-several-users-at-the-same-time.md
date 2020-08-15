---
title: Meerdere gebruikers tegelijk toevoegen aan Microsoft 365-Help voor beheerders
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: 'Meer informatie over het toevoegen van meerdere gebruikers aan Microsoft 365 voor bedrijven vanuit een lijst in een spreadsheet of een ander bestand met een CSV-indeling. Bekijk een video op YouTube waarin wordt uitgelegd hoe u accounts toevoegt aan Microsoft 365. Aan het einde van dit proces is elke gebruiker met een account een Microsoft 365-postvak. '
ms.openlocfilehash: c75f16233a85f48be44082ba3ec9ffb82ef18ff9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689568"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>Meerdere gebruikers tegelijk toevoegen aan Microsoft 365-Help voor beheerders

Elke medewerker van uw team moet een gebruikersaccount hebben voordat ze zich kunnen aanmelden en toegang krijgen tot Microsoft 365-Services, zoals e-mail en Office. Als u veel medewerkers hebt, kunt u hun accounts allemaal tegelijk toevoegen vanuit een Excel-spreadsheet of een ander bestand dat is opgeslagen in CSV-indeling. [Weet u niet precies wat een CSV-indeling is?](add-several-users-at-the-same-time.md#__toc316652088)
  
> [!NOTE] 
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>Meerdere gebruikers toevoegen in het Microsoft 365-Beheercentrum

1. Meld u aan bij Microsoft 365 met uw werk- of schoolaccount. 
    
2. Kies **Gebruikers** \> **Actieve gebruikers** in het beheercentrum.

3. Selecteer **meerdere gebruikers toevoegen**.

4. In het paneel **Meerder gebruikers importeren** kunt u eventueel een voorbeeld van een CSV-bestand met of zonder voorbeeldgegevens downloaden. 
    
    De spreadsheet dient **exact dezelfde kolomkoppen** als het voorbeeld te bevatten (Gebruikersnaam, Voornaam, enzovoort). Als u de sjabloon gebruikt, opent u deze in een teksteditor, zoals Kladblok. U kunt alle gegevens in rij 1 behouden en alleen gegevens invoeren in de rijen 2 en verder. 
    
    De spreadsheet dient voor elke gebruiker ook waarden te bevatten voor de gebruikersnaam (zoals jimmy@contoso.com) en een weergavenaam (zoals Jimmy de Graaf). 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-9821,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-9822,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-9823,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-9824,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-9825,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. Voer een bestandspad in het vak in of kies **Bladeren** om naar de locatie van het CSV-bestand te gaan. Kies vervolgens **Controleren**.
  
    Als er problemen met het bestand zijn, worden deze in het paneel weergegeven. U kunt ook een logboekbestand downloaden.
    
5. In het dialoogvenster **Gebruikersopties instellen** kunt u de aanmeldingsstatus instellen en de productlicentie kiezen die aan alle gebruikers wordt toegewezen. 
    
6. In het dialoogvenster **Resultaat weergeven** kunt u de resultaten laten verzenden naar uzelf of naar andere gebruikers (wachtwoorden in platte tekst) en kunt u zien hoeveel gebruikers zijn gemaakt en of u meer licenties dient aan te schaffen voor enkele nieuwe gebruikers. 

## <a name="next-steps"></a>Volgende stappen
<a name="bk_preview"> </a>

- Nu deze personen accounts hebben, moeten ze [Microsoft 365 of Office 2016 op een PC of Mac downloaden en installeren of opnieuw installeren](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658). Elke medewerker van uw team kan Microsoft 365 installeren op maximaal 5 Pc's of Macs. 
    
- Iedereen kan ook [Office-apps en E-mail instellen op een mobiel apparaat met een](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) maximum van 5 Tablets en 5 telefoons, zoals iPhones, IPads en Android-telefoons en-tablets. Op deze manier kunnen ze Office-bestanden vanaf elke locatie bewerken. 
    
    Zie [Microsoft 365 voor bedrijven instellen](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) voor een end-to-end-lijst van de instellingsstappen. 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>Meer informatie over het toevoegen van gebruikers aan Microsoft 365
<a name="bk_preview"> </a>

### <a name="not-sure-what-csv-format-is"></a>Weet u niet precies wat een CSV-indeling is?
<a name="__toc316652088"> </a>

Een CSV-bestand is een bestand met door komma's gescheiden waarden. U kunt een bestand zoals dit maken of bewerken met elke teksteditor of elk spreadsheetprogramma, zoals Excel.
  
U kunt [Dit voorbeeldwerkblad](https://www.microsoft.com/download/details.aspx?id=45485) als uitgangspunt downloaden. Houd er rekening mee dat in Microsoft 365 kolomkoppen in de eerste rij zijn vereist, dus vervang deze niet door iets anders. 
  
Sla het bestand op onder een nieuwe naam en geef de CSV-indeling op.
  
![Een afbeelding van hoe u een bestand opslaat in Excel in de CSV-indeling](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
Wanneer u het bestand opslaat, krijgt u waarschijnlijk een melding dat sommige functies in uw werkmap verloren gaan als u het bestand opslaat in een CSV-indeling. Dit is geen probleem. Klik op **Ja** om door te gaan. 
  
![Een afbeelding van de prompt die mogelijk verschijnt in Excel waarin wordt gevraagd of u het bestand als CSV-bestand wilt opslaan](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>Tips voor het opmaken van uw spreadsheet
<a name="__toc314595848"> </a>

- **Heb ik dezelfde kolomkoppen nodig als in de voorbeeldspreadsheet?** Ja. De voorbeeldspreadsheet bevat kolomkoppen in de eerste rij. Deze koppen zijn vereist. Voor elke gebruiker die u wilt toevoegen aan Microsoft 365, maakt u een rij onder de kop. Als u een kolomkoppen toevoegt, wijzigt of verwijdert, is het mogelijk dat Microsoft 365 geen gebruikers kan maken van de gegevens in het bestand. 
    
- **Wat moet ik doen als ik niet alle benodigde gebruikersgegevens heb?** De gebruikersnaam en weergavenaam zijn vereist en u kunt zonder deze gegevens geen nieuwe gebruiker toevoegen. Als u een deel van de andere gegevens niet hebt, zoals een faxnummer, kunt u een spatie plus een komma gebruiken om aan te geven dat het veld leeg moet blijven. 
    
- **Hoe klein of groot kan het spreadsheet zijn?** De spreadsheet moet minimaal twee rijen hebben. One is for the column headings (the user data column label) and one for the user. You cannot have more than 251 rows. If you need to import more than 250 users, you can create more than one spreadsheet. 
    
- **Welke talen kan ik gebruiken?** Wanneer u een spreadsheet maakt, kunt u kolomlabels van gebruikersgegevens in elke taal of tekens invoeren, maar u moet de volgorde van de etiketten niet wijzigen, zoals in het voorbeeld wordt weergegeven. You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format. 
    
- **Wat moet ik doen als ik gebruikers toevoeg uit andere landen of regio's?** Maak een aparte spreadsheet voor elk gebied. U moet de wizard Gebruikers bulksgewijs toevoegen doorlopen voor elke spreadsheet en één locatie opgeven voor alle gebruikers in het bestand waarmee u werkt. 
    
- **Geldt er een beperking voor het aantal tekens dat ik kan gebruiken?** In de volgende tabel staan de kolomlabels voor gebruikersgegevens en het maximum aantal tekens voor elk label in de voorbeeldspreadsheet. 
    
|**Kolomlabel met gebruikersgegevens**|**Maximum aantal tekens**|
|:-----|:-----|
|Gebruikersnaam (verplicht)  <br/> |79, inclusief het apenstaartje (@), in de name@domain opmaken. \<extension\> .. De alias van de gebruiker mag niet langer zijn dan 50 tekens, en de domeinnaam mag niet langer zijn dan 48 tekens.  <br/> |
|Voornaam  <br/> |64  <br/> |
|Achternaam  <br/> |64  <br/> |
|Weergavenaam (verplicht)  <br/> |256  <br/> |
|Functie  <br/> |64  <br/> |
|Afdeling  <br/> |64  <br/> |
|Toestelnummer  <br/> |128  <br/> |
|Zakelijk nummer  <br/> |64  <br/> |
|Mobiel nummer  <br/> |64  <br/> |
|Fax  <br/> |64  <br/> |
|Adres  <br/> |1023  <br/> |
|Plaats  <br/> |128  <br/> |
|Provincie  <br/> |128  <br/> |
|Postcode  <br/> |40  <br/> |
|Land of regio  <br/> |128  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>Nog steeds problemen bij het toevoegen van gebruikers aan Microsoft 365?

- **Controleer goed of de spreadsheet juist is ingedeeld.** Controleer of de kolomkoppen overeenkomen met de koppen in het voorbeeldbestand. Controleer of u de regels volgt voor het aantal tekens en of de velden met komma's zijn gescheiden. 
    
- **Als u de nieuwe gebruikers niet meteen ziet in Microsoft 365, wacht u enkele minuten.** Het kan even duren voordat wijzigingen worden doorgevoerd in alle services in Microsoft 365. 
    
## <a name="related-articles"></a>Verwante artikelen

[Gebruikers afzonderlijk of bulksgewijs toevoegen aan Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users)




