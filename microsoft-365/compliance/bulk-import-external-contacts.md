---
title: Externe contactpersonen bulksgewijs importeren in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Meer informatie over hoe beheerders Exchange Online PowerShell en een CSV-bestand kunnen gebruiken om externe contactpersonen bulksgewijs te importeren in de algemene adreslijst.
ms.openlocfilehash: 178e3676f8dc5fb59cdad9cc46d7ecbd9dddb90e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161921"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Externe contactpersonen bulksgewijs importeren in Exchange Online

**Dit artikel is bedoeld voor beheerders. Wilt u contactpersonen importeren in uw eigen postvak? Zie [Contactpersonen importeren in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
Heeft uw bedrijf veel bestaande zakelijke contactpersonen die u wilt opnemen in het gedeelde adresboek (ook wel de algemene adreslijst genoemd) in Exchange Online? Wilt u externe contactpersonen toevoegen als leden van distributiegroepen, net zoals met gebruikers binnen uw bedrijf? Als dat zo is, kunt u Exchange Online PowerShell en een CSV-bestand (door komma's gescheiden waarde) gebruiken om externe contactpersonen bulksgewijs te importeren in Exchange Online. Het is een proces in drie stappen:
  
[Stap 1: Een CSV-bestand maken met informatie over de externe contactpersonen](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Stap 2: De externe contactpersonen maken met PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Stap 3: Gegevens toevoegen aan de eigenschappen van de externe contactpersonen](#step-3-add-information-to-the-properties-of-the-external-contacts)

Nadat u deze stappen hebt uitgevoerd om contactpersonen te importeren, kunt u deze extra taken uitvoeren:
  
- [Meer externe contactpersonen toevoegen](#add-more-external-contacts)
  
- [Externe contactpersonen verbergen in het gedeelde adresboek](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Stap 1: Een CSV-bestand maken met informatie over de externe contactpersonen

De eerste stap is het maken van een CSV-bestand met informatie over elke externe contactpersoon die u wilt importeren in Exchange Online. 
  
1. Kopieer de volgende tekst naar een tekstbestand in Kladblok en sla deze op uw bureaublad op als een CSV-bestand met een bestandsnaamachtervoegsel van .csv; bijvoorbeeld ExternalContacts.csv.
    
    > [!TIP]
    > Als uw taal speciale tekens bevat (zoals **å**, **ä** en **ö** in het Zweeds), kunt u het CSV-bestand opslaan met UTF-8 of andere Unicode-codering wanneer u het bestand opgeslagen in Kladblok. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    De eerste rij of veldnamenrij van het CSV-bestand bevat de eigenschappen van contactpersonen die kunnen worden gebruikt wanneer u ze importeert naar Exchange Online. Elke eigenschapsnaam wordt gescheiden door een komma. Elke rij onder de veldnamenrij vertegenwoordigt de eigenschapswaarden voor het importeren van één externe contactpersoon. 
    
    > [!NOTE]
    > Deze tekst bevat voorbeeldgegevens die u kunt verwijderen. Maar verwijder de eerste rij (koptekst) niet of wijzig deze niet. Het bevat alle eigenschappen voor de externe contactpersonen. 
  
2. Open het CSV-bestand in Microsoft Excel om het CSV-bestand te bewerken, omdat u het CSV-bestand veel gemakkelijker kunt Excel om het CSV-bestand te bewerken.
    
3. Maak een rij voor elke contactpersoon die u wilt importeren in Exchange Online. Vul zo veel mogelijk cellen in. Deze gegevens worden weergegeven in het gedeelde adresboek voor elke contactpersoon. 
    
    > [!IMPORTANT]
    >  De volgende eigenschappen (de eerste vier items in de veldnamenrij) zijn vereist om een externe contactpersoon te maken en moeten worden ingevuld in het CSV-bestand: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. Met de PowerShell-opdracht die u in stap 2 hebt uitgevoerd, worden de waarden voor deze eigenschappen gebruikt om de contactpersonen te maken. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Stap 2: De externe contactpersonen maken met PowerShell

De volgende stap is om het CSV-bestand dat u hebt gemaakt in stap 1 en PowerShell te gebruiken om de externe contactpersonen die in het CSV-bestand worden vermeld, bulksgewijs te importeren in Exchange Online. 
  
1.  Verbinding maken PowerShell voor uw Exchange Online organisatie. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies. Gebruik de gebruikersnaam en het wachtwoord voor uw globale beheerdersaccount wanneer u verbinding maakt met Exchange Online PowerShell. 
    
2. Nadat u PowerShell hebt verbonden met Exchange Online, gaat u naar de bureaubladmap waar u het CSV-bestand hebt opgeslagen in stap 1. bijvoorbeeld `C:\Users\Administrator\desktop` .
    
3. Voer de volgende opdracht uit om de externe contactpersonen te maken:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Het kan even duren voordat u de nieuwe contactpersonen maakt, afhankelijk van het aantal contactpersonen dat u importeert. Wanneer de opdracht is voltooid, wordt in PowerShell een lijst weergegeven met de nieuwe contactpersonen die zijn gemaakt. 
    
4. Als u de nieuwe externe contactpersonen wilt weergeven, gaat u naar het Exchange -beheercentrum (EAC) en klikt u vervolgens **op Contactpersonen** \> **geadresseerden.** 
    
    > [!TIP]
    > Zie Exchange beheercentrum in Exchange Online voor instructies voor het maken van verbinding met [het](/exchange/exchange-admin-center)EAC. 
  
5. Klik indien nodig op **Vernieuwen om** de lijst bij te werken en de externe contactpersonen te bekijken die zijn geïmporteerd. 
    
    De geïmporteerde contactpersonen worden weergegeven in het gedeelde adresboek in Outlook en Outlook op internet.
    
    > [!NOTE]
    > U kunt de contactpersonen ook weergeven in het Microsoft 365 beheercentrum door naar **Gebruikerscontacten** \> **te gaan.** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Stap 3: Gegevens toevoegen aan de eigenschappen van de externe contactpersonen

Nadat u de opdracht hebt uitgevoerd in stap 2, worden de externe contactpersonen gemaakt, maar ze bevatten geen van de contactgegevens of organisatiegegevens, wat de gegevens zijn van de meeste cellen in het CSV-bestand. Dit komt omdat wanneer u nieuwe externe contactpersonen maakt, alleen de vereiste eigenschappen worden ingevuld. Maak u geen zorgen als u niet alle gegevens hebt ingevuld in het CSV-bestand. Als deze er niet is, wordt deze niet toegevoegd.
  
1.  Verbinding maken PowerShell voor uw Exchange Online organisatie. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.
    
2. Ga naar de bureaubladmap waar u het CSV-bestand hebt opgeslagen in stap 1; `C:\Users\Administrator\desktop`bijvoorbeeld.
    
3. Voer de volgende twee opdrachten uit om de andere eigenschappen uit het CSV-bestand toe te voegen aan de externe contactpersonen die u in stap 2 hebt gemaakt.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > De  _parameter Manager_ kan problematisch zijn. Als de cel leeg is in het CSV-bestand, krijgt u een foutmelding en wordt geen van de eigenschapsgegevens toegevoegd aan de contactpersoon. Als u geen manager hoeft op te geven, verwijdert u de vorige  ` -Manager $_.Manager ` PowerShell-opdracht. 
  
    Het kan ook even duren voordat u de contactpersonen hebt bijgewerkt, afhankelijk van het aantal contactpersonen dat u hebt geïmporteerd in stap 1. 
    
4. Als u wilt controleren of de eigenschappen zijn toegevoegd aan de contactpersonen: 
    
1. Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden.**
    
2. Klik op een contactpersoon en klik vervolgens **op Pictogram** Bewerken bewerken om de eigenschappen van de contactpersoon weer ![ te ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) geven. 
    
Dat is alles. Gebruikers kunnen de contactpersonen en de aanvullende informatie in het adresboek zien Outlook en Outlook op internet.
  
## <a name="add-more-external-contacts"></a>Meer externe contactpersonen toevoegen

U kunt stap 1 tot en met stap 3 herhalen om nieuwe externe contactpersonen toe te voegen in Exchange Online. U of gebruikers in uw bedrijf kunnen gewoon een nieuwe rij toevoegen aan het CSV-bestand voor de nieuwe contactpersoon. Vervolgens kunt u de PowerShell-opdrachten uitvoeren in stap 2 en stap 3 om informatie te maken en toe te voegen aan de nieuwe contactpersonen.
  
> [!NOTE]
> Wanneer u de opdracht voor het maken van nieuwe contactpersonen uit te voeren, krijgt u mogelijk een foutmelding dat de contactpersonen die eerder zijn gemaakt, al bestaan. Maar elke nieuwe contactpersoon die aan het CSV-bestand is toegevoegd, wordt gemaakt. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Externe contactpersonen verbergen in het gedeelde adresboek>

Sommige bedrijven gebruiken alleen externe contactpersonen, zodat ze kunnen worden toegevoegd als leden van distributiegroepen. In dit scenario willen ze mogelijk externe contactpersonen verbergen in het gedeelde adresboek. Hier ziet u hoe dat gaat:
  
1.  Verbinding maken PowerShell voor uw Exchange Online organisatie. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.
    
2. Als u één externe contactpersoon wilt verbergen, moet u de volgende opdracht uitvoeren.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Als u Bijvoorbeeld Pilar Pinilla wilt verbergen in het gedeelde adresboek, gaat u als volgende opdracht te werk:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Voer deze opdracht uit als u alle externe contactpersonen wilt verbergen in het gedeelde adresboek:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Nadat u deze hebt verborgen, worden externe contactpersonen niet weergegeven in het gedeelde adresboek, maar u kunt ze wel toevoegen als leden van een distributiegroep.