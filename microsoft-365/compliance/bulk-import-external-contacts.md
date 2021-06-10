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
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="59a32-103">Externe contactpersonen bulksgewijs importeren in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="59a32-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="59a32-104">**Dit artikel is bedoeld voor beheerders. Wilt u contactpersonen importeren in uw eigen postvak? Zie [Contactpersonen importeren in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="59a32-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="59a32-105">Heeft uw bedrijf veel bestaande zakelijke contactpersonen die u wilt opnemen in het gedeelde adresboek (ook wel de algemene adreslijst genoemd) in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="59a32-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="59a32-106">Wilt u externe contactpersonen toevoegen als leden van distributiegroepen, net zoals met gebruikers binnen uw bedrijf?</span><span class="sxs-lookup"><span data-stu-id="59a32-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="59a32-107">Als dat zo is, kunt u Exchange Online PowerShell en een CSV-bestand (door komma's gescheiden waarde) gebruiken om externe contactpersonen bulksgewijs te importeren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="59a32-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="59a32-108">Het is een proces in drie stappen:</span><span class="sxs-lookup"><span data-stu-id="59a32-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="59a32-109">Stap 1: Een CSV-bestand maken met informatie over de externe contactpersonen</span><span class="sxs-lookup"><span data-stu-id="59a32-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="59a32-110">Stap 2: De externe contactpersonen maken met PowerShell</span><span class="sxs-lookup"><span data-stu-id="59a32-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="59a32-111">Stap 3: Gegevens toevoegen aan de eigenschappen van de externe contactpersonen</span><span class="sxs-lookup"><span data-stu-id="59a32-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="59a32-112">Nadat u deze stappen hebt uitgevoerd om contactpersonen te importeren, kunt u deze extra taken uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="59a32-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="59a32-113">Meer externe contactpersonen toevoegen</span><span class="sxs-lookup"><span data-stu-id="59a32-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="59a32-114">Externe contactpersonen verbergen in het gedeelde adresboek</span><span class="sxs-lookup"><span data-stu-id="59a32-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="59a32-115">Stap 1: Een CSV-bestand maken met informatie over de externe contactpersonen</span><span class="sxs-lookup"><span data-stu-id="59a32-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="59a32-116">De eerste stap is het maken van een CSV-bestand met informatie over elke externe contactpersoon die u wilt importeren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="59a32-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="59a32-117">Kopieer de volgende tekst naar een tekstbestand in Kladblok en sla deze op uw bureaublad op als een CSV-bestand met een bestandsnaamachtervoegsel van .csv; bijvoorbeeld ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="59a32-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="59a32-118">Als uw taal speciale tekens bevat (zoals **å**, **ä** en **ö** in het Zweeds), kunt u het CSV-bestand opslaan met UTF-8 of andere Unicode-codering wanneer u het bestand opgeslagen in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="59a32-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="59a32-119">De eerste rij of veldnamenrij van het CSV-bestand bevat de eigenschappen van contactpersonen die kunnen worden gebruikt wanneer u ze importeert naar Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="59a32-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="59a32-120">Elke eigenschapsnaam wordt gescheiden door een komma.</span><span class="sxs-lookup"><span data-stu-id="59a32-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="59a32-121">Elke rij onder de veldnamenrij vertegenwoordigt de eigenschapswaarden voor het importeren van één externe contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="59a32-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="59a32-122">Deze tekst bevat voorbeeldgegevens die u kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="59a32-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="59a32-123">Maar verwijder de eerste rij (koptekst) niet of wijzig deze niet.</span><span class="sxs-lookup"><span data-stu-id="59a32-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="59a32-124">Het bevat alle eigenschappen voor de externe contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="59a32-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="59a32-125">Open het CSV-bestand in Microsoft Excel om het CSV-bestand te bewerken, omdat u het CSV-bestand veel gemakkelijker kunt Excel om het CSV-bestand te bewerken.</span><span class="sxs-lookup"><span data-stu-id="59a32-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="59a32-126">Maak een rij voor elke contactpersoon die u wilt importeren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="59a32-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="59a32-127">Vul zo veel mogelijk cellen in.</span><span class="sxs-lookup"><span data-stu-id="59a32-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="59a32-128">Deze gegevens worden weergegeven in het gedeelde adresboek voor elke contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="59a32-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="59a32-129">De volgende eigenschappen (de eerste vier items in de veldnamenrij) zijn vereist om een externe contactpersoon te maken en moeten worden ingevuld in het CSV-bestand: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span><span class="sxs-lookup"><span data-stu-id="59a32-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="59a32-130">Met de PowerShell-opdracht die u in stap 2 hebt uitgevoerd, worden de waarden voor deze eigenschappen gebruikt om de contactpersonen te maken.</span><span class="sxs-lookup"><span data-stu-id="59a32-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="59a32-131">Stap 2: De externe contactpersonen maken met PowerShell</span><span class="sxs-lookup"><span data-stu-id="59a32-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="59a32-132">De volgende stap is om het CSV-bestand dat u hebt gemaakt in stap 1 en PowerShell te gebruiken om de externe contactpersonen die in het CSV-bestand worden vermeld, bulksgewijs te importeren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="59a32-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="59a32-133">Verbinding maken PowerShell voor uw Exchange Online organisatie.</span><span class="sxs-lookup"><span data-stu-id="59a32-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="59a32-134">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="59a32-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="59a32-135">Gebruik de gebruikersnaam en het wachtwoord voor uw globale beheerdersaccount wanneer u verbinding maakt met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59a32-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="59a32-136">Nadat u PowerShell hebt verbonden met Exchange Online, gaat u naar de bureaubladmap waar u het CSV-bestand hebt opgeslagen in stap 1. bijvoorbeeld `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="59a32-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="59a32-137">Voer de volgende opdracht uit om de externe contactpersonen te maken:</span><span class="sxs-lookup"><span data-stu-id="59a32-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="59a32-138">Het kan even duren voordat u de nieuwe contactpersonen maakt, afhankelijk van het aantal contactpersonen dat u importeert.</span><span class="sxs-lookup"><span data-stu-id="59a32-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="59a32-139">Wanneer de opdracht is voltooid, wordt in PowerShell een lijst weergegeven met de nieuwe contactpersonen die zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="59a32-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="59a32-140">Als u de nieuwe externe contactpersonen wilt weergeven, gaat u naar het Exchange -beheercentrum (EAC) en klikt u vervolgens **op Contactpersonen** \> **geadresseerden.**</span><span class="sxs-lookup"><span data-stu-id="59a32-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="59a32-141">Zie Exchange beheercentrum in Exchange Online voor instructies voor het maken van verbinding met [het](/exchange/exchange-admin-center)EAC.</span><span class="sxs-lookup"><span data-stu-id="59a32-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span> 
  
5. <span data-ttu-id="59a32-142">Klik indien nodig op **Vernieuwen om** de lijst bij te werken en de externe contactpersonen te bekijken die zijn geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="59a32-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="59a32-143">De geïmporteerde contactpersonen worden weergegeven in het gedeelde adresboek in Outlook en Outlook op internet.</span><span class="sxs-lookup"><span data-stu-id="59a32-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="59a32-144">U kunt de contactpersonen ook weergeven in het Microsoft 365 beheercentrum door naar **Gebruikerscontacten** \> **te gaan.**</span><span class="sxs-lookup"><span data-stu-id="59a32-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="59a32-145">Stap 3: Gegevens toevoegen aan de eigenschappen van de externe contactpersonen</span><span class="sxs-lookup"><span data-stu-id="59a32-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="59a32-146">Nadat u de opdracht hebt uitgevoerd in stap 2, worden de externe contactpersonen gemaakt, maar ze bevatten geen van de contactgegevens of organisatiegegevens, wat de gegevens zijn van de meeste cellen in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="59a32-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="59a32-147">Dit komt omdat wanneer u nieuwe externe contactpersonen maakt, alleen de vereiste eigenschappen worden ingevuld.</span><span class="sxs-lookup"><span data-stu-id="59a32-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="59a32-148">Maak u geen zorgen als u niet alle gegevens hebt ingevuld in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="59a32-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="59a32-149">Als deze er niet is, wordt deze niet toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="59a32-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="59a32-150">Verbinding maken PowerShell voor uw Exchange Online organisatie.</span><span class="sxs-lookup"><span data-stu-id="59a32-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="59a32-151">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="59a32-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="59a32-152">Ga naar de bureaubladmap waar u het CSV-bestand hebt opgeslagen in stap 1; `C:\Users\Administrator\desktop`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="59a32-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="59a32-153">Voer de volgende twee opdrachten uit om de andere eigenschappen uit het CSV-bestand toe te voegen aan de externe contactpersonen die u in stap 2 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="59a32-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="59a32-154">De  _parameter Manager_ kan problematisch zijn.</span><span class="sxs-lookup"><span data-stu-id="59a32-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="59a32-155">Als de cel leeg is in het CSV-bestand, krijgt u een foutmelding en wordt geen van de eigenschapsgegevens toegevoegd aan de contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="59a32-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="59a32-156">Als u geen manager hoeft op te geven, verwijdert u de vorige  ` -Manager $_.Manager ` PowerShell-opdracht.</span><span class="sxs-lookup"><span data-stu-id="59a32-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="59a32-157">Het kan ook even duren voordat u de contactpersonen hebt bijgewerkt, afhankelijk van het aantal contactpersonen dat u hebt geïmporteerd in stap 1.</span><span class="sxs-lookup"><span data-stu-id="59a32-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="59a32-158">Als u wilt controleren of de eigenschappen zijn toegevoegd aan de contactpersonen:</span><span class="sxs-lookup"><span data-stu-id="59a32-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="59a32-159">Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden.**</span><span class="sxs-lookup"><span data-stu-id="59a32-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="59a32-160">Klik op een contactpersoon en klik vervolgens **op Pictogram** Bewerken bewerken om de eigenschappen van de contactpersoon weer ![ te ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) geven.</span><span class="sxs-lookup"><span data-stu-id="59a32-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="59a32-161">Dat is alles.</span><span class="sxs-lookup"><span data-stu-id="59a32-161">That's it!</span></span> <span data-ttu-id="59a32-162">Gebruikers kunnen de contactpersonen en de aanvullende informatie in het adresboek zien Outlook en Outlook op internet.</span><span class="sxs-lookup"><span data-stu-id="59a32-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="59a32-163">Meer externe contactpersonen toevoegen</span><span class="sxs-lookup"><span data-stu-id="59a32-163">Add more external contacts</span></span>

<span data-ttu-id="59a32-164">U kunt stap 1 tot en met stap 3 herhalen om nieuwe externe contactpersonen toe te voegen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="59a32-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="59a32-165">U of gebruikers in uw bedrijf kunnen gewoon een nieuwe rij toevoegen aan het CSV-bestand voor de nieuwe contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="59a32-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="59a32-166">Vervolgens kunt u de PowerShell-opdrachten uitvoeren in stap 2 en stap 3 om informatie te maken en toe te voegen aan de nieuwe contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="59a32-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="59a32-167">Wanneer u de opdracht voor het maken van nieuwe contactpersonen uit te voeren, krijgt u mogelijk een foutmelding dat de contactpersonen die eerder zijn gemaakt, al bestaan.</span><span class="sxs-lookup"><span data-stu-id="59a32-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="59a32-168">Maar elke nieuwe contactpersoon die aan het CSV-bestand is toegevoegd, wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="59a32-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="59a32-169">Externe contactpersonen verbergen in het gedeelde adresboek></span><span class="sxs-lookup"><span data-stu-id="59a32-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="59a32-170">Sommige bedrijven gebruiken alleen externe contactpersonen, zodat ze kunnen worden toegevoegd als leden van distributiegroepen.</span><span class="sxs-lookup"><span data-stu-id="59a32-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="59a32-171">In dit scenario willen ze mogelijk externe contactpersonen verbergen in het gedeelde adresboek.</span><span class="sxs-lookup"><span data-stu-id="59a32-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="59a32-172">Hier ziet u hoe dat gaat:</span><span class="sxs-lookup"><span data-stu-id="59a32-172">Here's how:</span></span>
  
1.  <span data-ttu-id="59a32-173">Verbinding maken PowerShell voor uw Exchange Online organisatie.</span><span class="sxs-lookup"><span data-stu-id="59a32-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="59a32-174">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="59a32-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="59a32-175">Als u één externe contactpersoon wilt verbergen, moet u de volgende opdracht uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="59a32-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="59a32-176">Als u Bijvoorbeeld Pilar Pinilla wilt verbergen in het gedeelde adresboek, gaat u als volgende opdracht te werk:</span><span class="sxs-lookup"><span data-stu-id="59a32-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="59a32-177">Voer deze opdracht uit als u alle externe contactpersonen wilt verbergen in het gedeelde adresboek:</span><span class="sxs-lookup"><span data-stu-id="59a32-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="59a32-178">Nadat u deze hebt verborgen, worden externe contactpersonen niet weergegeven in het gedeelde adresboek, maar u kunt ze wel toevoegen als leden van een distributiegroep.</span><span class="sxs-lookup"><span data-stu-id="59a32-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>