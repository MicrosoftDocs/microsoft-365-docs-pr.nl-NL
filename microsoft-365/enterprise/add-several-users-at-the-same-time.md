---
title: Meerdere gebruikers tegelijk toevoegen aan Microsoft 365 - Help voor beheerders
ms.author: kwekua
author: kwekua
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
description: 'Meer informatie over het toevoegen van meerdere gebruikers Microsoft 365 voor bedrijven vanuit een lijst in een spreadsheet of ander CSV-opgemaakt bestand. Bekijk een video op YouTube waarin wordt uitgelegd hoe u accounts toevoegt aan Microsoft 365. Aan het einde van dit proces heeft elke gebruiker met een account een Microsoft 365 postvak. '
ms.openlocfilehash: 6b3e8d885466e44a4aa23427a54cfc98b2eebdf3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905618"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="82347-105">Meerdere gebruikers tegelijk toevoegen aan Microsoft 365 - Help voor beheerders</span><span class="sxs-lookup"><span data-stu-id="82347-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="82347-106">Elke persoon in uw team heeft een gebruikersaccount nodig voordat hij of zij zich kan aanmelden en Microsoft 365 services, zoals e-mail en Office.</span><span class="sxs-lookup"><span data-stu-id="82347-106">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office.</span></span> <span data-ttu-id="82347-107">Als u veel medewerkers hebt, kunt u hun accounts allemaal tegelijk toevoegen vanuit een Excel-spreadsheet of een ander bestand dat is opgeslagen in CSV-indeling.</span><span class="sxs-lookup"><span data-stu-id="82347-107">If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format.</span></span> <span data-ttu-id="82347-108">[Weet u niet zeker wat CSV-indeling is?](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)</span><span class="sxs-lookup"><span data-stu-id="82347-108">[Not sure what CSV format is](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?</span></span>
  
> [!NOTE]
> <span data-ttu-id="82347-109">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="82347-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="82347-110">Meerdere gebruikers toevoegen in het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="82347-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="82347-111">Meld u aan bij Microsoft 365 met uw werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="82347-111">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="82347-112">Kies **Gebruikers** \> **Actieve gebruikers** in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="82347-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="82347-113">Selecteer **Meerdere gebruikers toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="82347-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="82347-114">In het paneel **Meerder gebruikers importeren** kunt u eventueel een voorbeeld van een CSV-bestand met of zonder voorbeeldgegevens downloaden.</span><span class="sxs-lookup"><span data-stu-id="82347-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span>

    <span data-ttu-id="82347-115">Uw spreadsheet moet exact dezelfde **kolomkoppen** bevatten als de voorbeeldkoppen (gebruikersnaam, voornaam, etc.).</span><span class="sxs-lookup"><span data-stu-id="82347-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="82347-116">Als u de sjabloon gebruikt, opent u deze in een hulpmiddel voor tekstbewerking, zoals Kladblok, en overweegt u alle gegevens in rij 1 alleen te laten en alleen gegevens in te voegen in rijen 2 en lager.</span><span class="sxs-lookup"><span data-stu-id="82347-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span>

    <span data-ttu-id="82347-117">De spreadsheet dient voor elke gebruiker ook waarden te bevatten voor de gebruikersnaam (zoals jimmy@contoso.com) en een weergavenaam (zoals Jimmy de Graaf).</span><span class="sxs-lookup"><span data-stu-id="82347-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span>

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="82347-118">Voer een bestandspad in het vak in of kies **Bladeren** om naar de locatie van het CSV-bestand te gaan. Kies vervolgens **Controleren**.</span><span class="sxs-lookup"><span data-stu-id="82347-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="82347-p104">Als er problemen met het bestand zijn, worden deze in het paneel weergegeven. U kunt ook een logboekbestand downloaden.</span><span class="sxs-lookup"><span data-stu-id="82347-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>

6. <span data-ttu-id="82347-121">In het dialoogvenster **Gebruikersopties instellen** kunt u de aanmeldingsstatus instellen en de productlicentie kiezen die aan alle gebruikers wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="82347-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span>

7. <span data-ttu-id="82347-122">In het dialoogvenster **Resultaat weergeven** kunt u de resultaten laten verzenden naar uzelf of naar andere gebruikers (wachtwoorden in platte tekst) en kunt u zien hoeveel gebruikers zijn gemaakt en of u meer licenties dient aan te schaffen voor enkele nieuwe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="82347-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span>

## <a name="next-steps"></a><span data-ttu-id="82347-123">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="82347-123">Next steps</span></span>

- <span data-ttu-id="82347-124">Nu deze personen accounts hebben, moeten ze de Microsoft 365 of Office [2016](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)op een pc of Mac downloaden en installeren of opnieuw installeren.</span><span class="sxs-lookup"><span data-stu-id="82347-124">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="82347-125">Elke persoon in uw team kan Microsoft 365 installeren op maximaal 5 pc's of Macs.</span><span class="sxs-lookup"><span data-stu-id="82347-125">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span>

- <span data-ttu-id="82347-126">Elke persoon kan ook Office [apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) en e-mail instellen op een mobiel apparaat op maximaal 5 tablets en 5 telefoons, zoals iPhones, iPads en Android-telefoons en -tablets.</span><span class="sxs-lookup"><span data-stu-id="82347-126">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="82347-127">Op deze manier kunnen ze Office-bestanden vanaf elke locatie bewerken.</span><span class="sxs-lookup"><span data-stu-id="82347-127">This way they can edit Office files from anywhere.</span></span>

    <span data-ttu-id="82347-128">Zie [Een Microsoft 365 voor bedrijven instellen](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) voor een end-to-end lijst met de installatiestappen.</span><span class="sxs-lookup"><span data-stu-id="82347-128">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span>

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="82347-129">Meer informatie over het toevoegen van gebruikers aan Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82347-129">More information about how to add users to Microsoft 365</span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="82347-130">Weet u niet precies wat een CSV-indeling is?</span><span class="sxs-lookup"><span data-stu-id="82347-130">Not sure what CSV format is?</span></span>

<span data-ttu-id="82347-p107">Een CSV-bestand is een bestand met door komma's gescheiden waarden. U kunt een bestand zoals dit maken of bewerken met elke teksteditor of elk spreadsheetprogramma, zoals Excel.</span><span class="sxs-lookup"><span data-stu-id="82347-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="82347-133">U kunt dit [voorbeeldblad downloaden](https://www.microsoft.com/download/details.aspx?id=45485) als uitgangspunt.</span><span class="sxs-lookup"><span data-stu-id="82347-133">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="82347-134">Houd er Microsoft 365 kolomkoppen in de eerste rij voor nodig zijn, dus vervang ze niet door iets anders.</span><span class="sxs-lookup"><span data-stu-id="82347-134">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="82347-135">Sla het bestand op onder een nieuwe naam en geef de CSV-indeling op.</span><span class="sxs-lookup"><span data-stu-id="82347-135">Save the file with a new name, and specify CSV format.</span></span>
  
![Een afbeelding van hoe u een bestand opslaat in Excel in de CSV-indeling](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="82347-p109">Wanneer u het bestand opslaat, krijgt u waarschijnlijk een melding dat sommige functies in uw werkmap verloren gaan als u het bestand opslaat in een CSV-indeling. Dit is geen probleem. Klik op **Ja** om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="82347-p109">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span>
  
![Een afbeelding van de prompt die mogelijk verschijnt in Excel waarin wordt gevraagd of u het bestand als CSV-bestand wilt opslaan](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="82347-141">Tips voor het opmaken van uw spreadsheet</span><span class="sxs-lookup"><span data-stu-id="82347-141">Tips for formatting your spreadsheet</span></span>

- <span data-ttu-id="82347-142">**Heb ik dezelfde kolomkoppen nodig als in de voorbeeldspreadsheet?**</span><span class="sxs-lookup"><span data-stu-id="82347-142">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="82347-143">Ja.</span><span class="sxs-lookup"><span data-stu-id="82347-143">Yes.</span></span> <span data-ttu-id="82347-144">De voorbeeldspreadsheet bevat kolomkoppen in de eerste rij.</span><span class="sxs-lookup"><span data-stu-id="82347-144">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="82347-145">Deze koppen zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="82347-145">These headings are required.</span></span> <span data-ttu-id="82347-146">Voor elke gebruiker die u wilt toevoegen aan Microsoft 365, maakt u een rij onder de kop.</span><span class="sxs-lookup"><span data-stu-id="82347-146">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="82347-147">Als u een van de kolomkoppen toevoegt, wijzigt of verwijdert, Microsoft 365 mogelijk geen gebruikers maken op de gegevens in het bestand.</span><span class="sxs-lookup"><span data-stu-id="82347-147">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span>

- <span data-ttu-id="82347-p111">**Wat moet ik doen als ik niet alle benodigde gebruikersgegevens heb?** De gebruikersnaam en weergavenaam zijn vereist en u kunt zonder deze gegevens geen nieuwe gebruiker toevoegen. Als u een deel van de andere gegevens niet hebt, zoals een faxnummer, kunt u een spatie plus een komma gebruiken om aan te geven dat het veld leeg moet blijven.</span><span class="sxs-lookup"><span data-stu-id="82347-p111">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span>

- <span data-ttu-id="82347-151">**Hoe klein of groot kan de spreadsheet zijn?**</span><span class="sxs-lookup"><span data-stu-id="82347-151">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="82347-152">Het werkblad moet ten minste twee rijen hebben.</span><span class="sxs-lookup"><span data-stu-id="82347-152">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="82347-153">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="82347-153">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="82347-154">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="82347-154">You cannot have more than 251 rows.</span></span> <span data-ttu-id="82347-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="82347-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span>

- <span data-ttu-id="82347-156">**Welke talen kan ik gebruiken?**</span><span class="sxs-lookup"><span data-stu-id="82347-156">**What languages can I use?**</span></span> <span data-ttu-id="82347-157">Wanneer u uw spreadsheet maakt, kunt u kolomlabels voor gebruikersgegevens invoeren in elke taal of tekens, maar u mag de volgorde van de etiketten niet wijzigen, zoals wordt weergegeven in het voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="82347-157">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="82347-158">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span><span class="sxs-lookup"><span data-stu-id="82347-158">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span>

- <span data-ttu-id="82347-p114">**Wat moet ik doen als ik gebruikers toevoeg uit andere landen of regio's?** Maak een aparte spreadsheet voor elk gebied. U moet de wizard Gebruikers bulksgewijs toevoegen doorlopen voor elke spreadsheet en één locatie opgeven voor alle gebruikers in het bestand waarmee u werkt.</span><span class="sxs-lookup"><span data-stu-id="82347-p114">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span>

- <span data-ttu-id="82347-p115">**Geldt er een beperking voor het aantal tekens dat ik kan gebruiken?** In de volgende tabel staan de kolomlabels voor gebruikersgegevens en het maximum aantal tekens voor elk label in de voorbeeldspreadsheet.</span><span class="sxs-lookup"><span data-stu-id="82347-p115">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span>

|<span data-ttu-id="82347-164">**Kolomlabel met gebruikersgegevens**</span><span class="sxs-lookup"><span data-stu-id="82347-164">**User data column label**</span></span>|<span data-ttu-id="82347-165">**Maximum aantal tekens**</span><span class="sxs-lookup"><span data-stu-id="82347-165">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82347-166">Gebruikersnaam (verplicht)</span><span class="sxs-lookup"><span data-stu-id="82347-166">User Name (Required)</span></span>  <br/> |<span data-ttu-id="82347-167">79 inclusief het bijteken (@), in de name@domain. \<extension\> .</span><span class="sxs-lookup"><span data-stu-id="82347-167">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="82347-168">De alias van de gebruiker mag niet meer dan 50 tekens bevatten en de domeinnaam mag niet groter zijn dan 48 tekens.</span><span class="sxs-lookup"><span data-stu-id="82347-168">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="82347-169">Voornaam</span><span class="sxs-lookup"><span data-stu-id="82347-169">First Name</span></span>  <br/> |<span data-ttu-id="82347-170">64</span><span class="sxs-lookup"><span data-stu-id="82347-170">64</span></span>  <br/> |
|<span data-ttu-id="82347-171">Achternaam</span><span class="sxs-lookup"><span data-stu-id="82347-171">Last Name</span></span>  <br/> |<span data-ttu-id="82347-172">64</span><span class="sxs-lookup"><span data-stu-id="82347-172">64</span></span>  <br/> |
|<span data-ttu-id="82347-173">Weergavenaam (verplicht)</span><span class="sxs-lookup"><span data-stu-id="82347-173">Display Name (required)</span></span>  <br/> |<span data-ttu-id="82347-174">256</span><span class="sxs-lookup"><span data-stu-id="82347-174">256</span></span>  <br/> |
|<span data-ttu-id="82347-175">Functie</span><span class="sxs-lookup"><span data-stu-id="82347-175">Job Title</span></span>  <br/> |<span data-ttu-id="82347-176">64</span><span class="sxs-lookup"><span data-stu-id="82347-176">64</span></span>  <br/> |
|<span data-ttu-id="82347-177">Afdeling</span><span class="sxs-lookup"><span data-stu-id="82347-177">Department</span></span>  <br/> |<span data-ttu-id="82347-178">64</span><span class="sxs-lookup"><span data-stu-id="82347-178">64</span></span>  <br/> |
|<span data-ttu-id="82347-179">Toestelnummer</span><span class="sxs-lookup"><span data-stu-id="82347-179">Office Number</span></span>  <br/> |<span data-ttu-id="82347-180">128</span><span class="sxs-lookup"><span data-stu-id="82347-180">128</span></span>  <br/> |
|<span data-ttu-id="82347-181">Zakelijk nummer</span><span class="sxs-lookup"><span data-stu-id="82347-181">Office Phone</span></span>  <br/> |<span data-ttu-id="82347-182">64</span><span class="sxs-lookup"><span data-stu-id="82347-182">64</span></span>  <br/> |
|<span data-ttu-id="82347-183">Mobiel nummer</span><span class="sxs-lookup"><span data-stu-id="82347-183">Mobile Phone</span></span>  <br/> |<span data-ttu-id="82347-184">64</span><span class="sxs-lookup"><span data-stu-id="82347-184">64</span></span>  <br/> |
|<span data-ttu-id="82347-185">Fax</span><span class="sxs-lookup"><span data-stu-id="82347-185">Fax</span></span>  <br/> |<span data-ttu-id="82347-186">64</span><span class="sxs-lookup"><span data-stu-id="82347-186">64</span></span>  <br/> |
|<span data-ttu-id="82347-187">Adres</span><span class="sxs-lookup"><span data-stu-id="82347-187">Address</span></span>  <br/> |<span data-ttu-id="82347-188">1023</span><span class="sxs-lookup"><span data-stu-id="82347-188">1023</span></span>  <br/> |
|<span data-ttu-id="82347-189">Plaats</span><span class="sxs-lookup"><span data-stu-id="82347-189">City</span></span>  <br/> |<span data-ttu-id="82347-190">128</span><span class="sxs-lookup"><span data-stu-id="82347-190">128</span></span>  <br/> |
|<span data-ttu-id="82347-191">Provincie</span><span class="sxs-lookup"><span data-stu-id="82347-191">State or Province</span></span>  <br/> |<span data-ttu-id="82347-192">128</span><span class="sxs-lookup"><span data-stu-id="82347-192">128</span></span>  <br/> |
|<span data-ttu-id="82347-193">Postcode</span><span class="sxs-lookup"><span data-stu-id="82347-193">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="82347-194">40</span><span class="sxs-lookup"><span data-stu-id="82347-194">40</span></span>  <br/> |
|<span data-ttu-id="82347-195">Land of regio</span><span class="sxs-lookup"><span data-stu-id="82347-195">Country or Region</span></span>  <br/> |<span data-ttu-id="82347-196">128</span><span class="sxs-lookup"><span data-stu-id="82347-196">128</span></span>  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="82347-197">Hebt u nog steeds problemen bij het toevoegen van gebruikers aan Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="82347-197">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="82347-p117">**Controleer goed of de spreadsheet juist is ingedeeld.** Controleer of de kolomkoppen overeenkomen met de koppen in het voorbeeldbestand. Controleer of u de regels volgt voor het aantal tekens en of de velden met komma's zijn gescheiden.</span><span class="sxs-lookup"><span data-stu-id="82347-p117">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span>

- <span data-ttu-id="82347-201">**Als u de nieuwe gebruikers niet direct in Microsoft 365 ziet, wacht u een paar minuten.**</span><span class="sxs-lookup"><span data-stu-id="82347-201">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="82347-202">Het kan even duren voordat wijzigingen worden doorgevoerd in alle services in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82347-202">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="82347-203">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="82347-203">Related articles</span></span>

[<span data-ttu-id="82347-204">Gebruikers afzonderlijk of bulksgewijs toevoegen aan Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82347-204">Add users individually or in bulk to Microsoft 365</span></span>](/office365/admin/add-users/add-users)