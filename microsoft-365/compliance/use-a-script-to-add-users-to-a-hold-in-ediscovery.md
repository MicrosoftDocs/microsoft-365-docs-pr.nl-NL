---
title: Een script gebruiken om gebruikers toe te voegen aan een wacht in een Hoofd-eDiscovery-zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Lees hoe u een script kunt uitvoeren om postvakken & OneDrive voor Bedrijven sites toe te voegen aan een nieuwe wachtplaats die is gekoppeld aan een eDiscovery-zaak in het Microsoft 365 compliancecentrum.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161890"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="fce1c-103">Een script gebruiken om gebruikers toe te voegen aan een wacht in een Hoofd-eDiscovery-zaak</span><span class="sxs-lookup"><span data-stu-id="fce1c-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="fce1c-104">Beveiligings & Compliance center PowerShell biedt cmdlets om tijdrovende taken met betrekking tot het maken en beheren van eDiscovery-zaken te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="fce1c-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="fce1c-105">Het gebruik van de core eDiscovery-zaak in het beveiligings- & compliancecentrum om een groot aantal bewaarlocaties voor inhoud in de wacht te zetten, kost tijd en voorbereiding.</span><span class="sxs-lookup"><span data-stu-id="fce1c-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="fce1c-106">Voordat u bijvoorbeeld een hold maakt, moet u de URL verzamelen voor elke OneDrive voor Bedrijven site die u in de wacht wilt zetten.</span><span class="sxs-lookup"><span data-stu-id="fce1c-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="fce1c-107">Vervolgens moet u voor elke gebruiker die u in de wacht wilt zetten, zijn of haar postvak en OneDrive voor Bedrijven aan de wachtplaats toevoegen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="fce1c-108">U kunt het script in dit artikel gebruiken om dit proces te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="fce1c-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="fce1c-109">In het script wordt u gevraagd om de naam van het domein Mijn site van uw organisatie (bijvoorbeeld in de URL, de naam van een bestaand `contoso` eDiscovery-geval, de naam van de nieuwe wachtplaats die is gekoppeld aan de zaak, een lijst met e-mailadressen van de gebruikers die u wilt in de wacht zetten en een zoekquery die u wilt gebruiken als u een query-hold wilt https://contoso-my.sharepoint.com) maken.</span><span class="sxs-lookup"><span data-stu-id="fce1c-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="fce1c-110">Het script krijgt vervolgens de URL voor de OneDrive voor Bedrijven-site voor elke gebruiker in de lijst, maakt de nieuwe wacht en voegt vervolgens het postvak en de OneDrive voor Bedrijven-site voor elke gebruiker in de lijst toe aan de wacht.</span><span class="sxs-lookup"><span data-stu-id="fce1c-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="fce1c-111">Het script genereert ook logboekbestanden die informatie over de nieuwe wacht houden bevatten.</span><span class="sxs-lookup"><span data-stu-id="fce1c-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="fce1c-112">Hier volgen de stappen om dit te doen:</span><span class="sxs-lookup"><span data-stu-id="fce1c-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="fce1c-113">Stap 1: De SharePoint Online Management Shell installeren</span><span class="sxs-lookup"><span data-stu-id="fce1c-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="fce1c-114">Stap 2: Een lijst met gebruikers genereren</span><span class="sxs-lookup"><span data-stu-id="fce1c-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="fce1c-115">Stap 3: Het script uitvoeren om een wacht te maken en gebruikers toe te voegen</span><span class="sxs-lookup"><span data-stu-id="fce1c-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="fce1c-116">Voordat u gebruikers toevoegt aan een wacht</span><span class="sxs-lookup"><span data-stu-id="fce1c-116">Before you add users to a hold</span></span>

- <span data-ttu-id="fce1c-117">U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum en een SharePoint Online-beheerder om het script uit te voeren in stap 3.</span><span class="sxs-lookup"><span data-stu-id="fce1c-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="fce1c-118">Zie [eDiscovery-machtigingen toewijzen in het Office 365 Beveiligingscentrum & compliancecentrum voor meer informatie.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="fce1c-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="fce1c-119">Er kunnen maximaal 1.000 postvakken en 100 sites worden toegevoegd aan een wachtplaats die is gekoppeld aan een eDiscovery-zaak in het beveiligings- & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="fce1c-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="fce1c-120">Ervan uitgaande dat elke gebruiker die u in de wacht wilt zetten een OneDrive voor Bedrijven site heeft, kunt u maximaal 100 gebruikers aan een wacht houden met behulp van het script in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="fce1c-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="fce1c-121">Zorg ervoor dat u de lijst met gebruikers die u maakt in stap 2 en het script in stap 3 in dezelfde map opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="fce1c-122">Dit maakt het eenvoudiger om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="fce1c-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="fce1c-123">Met het script wordt de lijst met gebruikers toegevoegd aan een nieuwe wacht die is gekoppeld aan een bestaand geval.</span><span class="sxs-lookup"><span data-stu-id="fce1c-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="fce1c-124">Zorg ervoor dat de zaak aan wie u de wacht wilt koppelen, is gemaakt voordat u het script uitwerkt.</span><span class="sxs-lookup"><span data-stu-id="fce1c-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="fce1c-125">Het script in dit artikel ondersteunt moderne verificatie wanneer u verbinding maakt met & Compliance Center PowerShell en SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fce1c-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="fce1c-126">U kunt het script gewoon gebruiken als u een Microsoft 365 of een Microsoft 365 GCC organisatie.</span><span class="sxs-lookup"><span data-stu-id="fce1c-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="fce1c-127">Als u een organisatie Office 365 Duitsland, een Microsoft 365 GCC Hoge organisatie of een Microsoft 365 DoD-organisatie bent, moet u het script bewerken om het uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="fce1c-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="fce1c-128">U moet de regel bewerken en de `Connect-IPPSSession` parameters *ConnectionUri* en *AzureADAuthorizationEndpointUri* (en de juiste waarden voor uw organisatietype) gebruiken om verbinding te maken met Security & Compliance Center PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fce1c-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="fce1c-129">Zie de voorbeelden in Verbinding maken security [& Compliance Center PowerShell voor meer informatie.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)</span><span class="sxs-lookup"><span data-stu-id="fce1c-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="fce1c-130">Het script wordt automatisch losgekoppeld van Security & Compliance Center PowerShell en SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fce1c-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="fce1c-131">Het script bevat minimale foutafhandeling.</span><span class="sxs-lookup"><span data-stu-id="fce1c-131">The script includes minimal error handling.</span></span> <span data-ttu-id="fce1c-132">Het primaire doel is om het postvak en de OneDrive voor Bedrijven van elke gebruiker snel en eenvoudig in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="fce1c-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="fce1c-133">De voorbeeldscripts in dit onderwerp worden niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fce1c-133">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="fce1c-134">De voorbeeldscripts worden zonder enige garantie ONGEWIJZIGD verstrekt.</span><span class="sxs-lookup"><span data-stu-id="fce1c-134">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="fce1c-135">Microsoft wijst alle impliciete garanties met inbegrip van, maar niet beperkt tot, impliciete garanties van verkoopbaarheid en geschiktheid voor een bepaald doel af.</span><span class="sxs-lookup"><span data-stu-id="fce1c-135">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="fce1c-136">Het risico dat ontstaat als gevolg van het gebruik of prestaties van de voorbeeldscripts ligt geheel bij u.</span><span class="sxs-lookup"><span data-stu-id="fce1c-136">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="fce1c-137">In geen geval kan Microsoft, haar auteurs of anderen die bij het maken, produceren of leveren van de scripts zijn betrokken, aansprakelijk worden gehouden voor enige schade om welke reden dan ook (met inbegrip van maar niet beperkt tot schade door verlies van bedrijfswinsten, belemmering van de bedrijfsuitvoering, verlies van bedrijfsinformatie of andere geldelijke verliezen) voortvloeiend uit het gebruik of de onmogelijkheid van het gebruik van de voorbeeldscripts, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.</span><span class="sxs-lookup"><span data-stu-id="fce1c-137">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="fce1c-138">Stap 1: De SharePoint Online Management Shell installeren</span><span class="sxs-lookup"><span data-stu-id="fce1c-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="fce1c-139">De eerste stap is om de SharePoint Online Management Shell te installeren als deze nog niet op uw lokale computer is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="fce1c-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="fce1c-140">U hoeft de shell niet te gebruiken in deze procedure, maar u moet deze installeren omdat deze vereisten bevat die vereist zijn voor het script dat u in stap 3 uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="fce1c-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="fce1c-141">Met deze vereisten kan het script communiceren met SharePoint Online om de URL's voor de OneDrive voor Bedrijven krijgen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="fce1c-142">Ga naar De SharePoint [Online Management Shell Windows PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en voer stap 1 en stap 2 uit om de SharePoint Online Management Shell op uw lokale computer te installeren.</span><span class="sxs-lookup"><span data-stu-id="fce1c-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="fce1c-143">Stap 2: Een lijst met gebruikers genereren</span><span class="sxs-lookup"><span data-stu-id="fce1c-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="fce1c-144">Met het script in stap 3 wordt een wachtlijst gemaakt die is gekoppeld aan een eDiscovery-zaak en worden de postvakken en OneDrive voor Bedrijven sites van een lijst met gebruikers aan de wacht gezet.</span><span class="sxs-lookup"><span data-stu-id="fce1c-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="fce1c-145">U kunt alleen de e-mailadressen in een tekstbestand typen of u kunt een opdracht uitvoeren in Windows PowerShell om een lijst met e-mailadressen op te halen en deze op te slaan in een bestand (in dezelfde map waarin u het script in stap 3 op wilt slaan).</span><span class="sxs-lookup"><span data-stu-id="fce1c-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="fce1c-146">Hier ziet u een PowerShell-opdracht (die u kunt uitvoeren met externe PowerShell die is verbonden met uw Exchange Online-organisatie) om een lijst met e-mailadressen op te halen voor alle gebruikers in uw organisatie en deze op te slaan in een tekstbestand met de naam HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="fce1c-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="fce1c-147">Nadat u deze opdracht hebt uitgevoerd, opent u het tekstbestand en verwijdert u de koptekst met de naam van de  `PrimarySmtpAddress` eigenschap.</span><span class="sxs-lookup"><span data-stu-id="fce1c-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="fce1c-148">Verwijder vervolgens alle e-mailadressen, behalve de e-mailadressen voor de gebruikers die u wilt toevoegen aan de wacht die u in stap 3 maakt.</span><span class="sxs-lookup"><span data-stu-id="fce1c-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="fce1c-149">Zorg ervoor dat er geen lege rijen zijn voor of na de lijst met e-mailadressen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="fce1c-150">Stap 3: Het script uitvoeren om een wacht te maken en gebruikers toe te voegen</span><span class="sxs-lookup"><span data-stu-id="fce1c-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="fce1c-151">Wanneer u het script in deze stap uit te voeren, wordt u gevraagd om de volgende informatie.</span><span class="sxs-lookup"><span data-stu-id="fce1c-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="fce1c-152">Zorg ervoor dat u deze informatie klaar hebt voordat u het script gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="fce1c-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="fce1c-153">**Uw gebruikersreferenties:** Het script gebruikt uw referenties om verbinding te maken met & Compliancecentrum met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fce1c-153">**Your user credentials:** The script will use your credentials to connect to Security & Compliance Center with PowerShell.</span></span> <span data-ttu-id="fce1c-154">Deze referenties worden ook gebruikt om toegang te krijgen tot SharePoint Online om de OneDrive voor Bedrijven url's voor de lijst met gebruikers te krijgen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="fce1c-155">**Naam van uw SharePoint domein:** In het script wordt u gevraagd deze naam in te voeren, zodat deze verbinding kan maken met het SharePoint beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="fce1c-155">**Name of your SharePoint domain:** The script prompts you to enter this name so it can connect to the SharePoint admin center.</span></span> <span data-ttu-id="fce1c-156">De domeinnaam wordt ook gebruikt voor de OneDrive URL's in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fce1c-156">It also uses the domain name for the OneDrive URLs in your organization.</span></span> <span data-ttu-id="fce1c-157">Als bijvoorbeeld de URL voor uw beheercentrum is en de URL voor OneDrive is, voert u deze in wanneer het script u om uw domeinnaam `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` vraagt.</span><span class="sxs-lookup"><span data-stu-id="fce1c-157">For example, if the URL for your admin center is `https://contoso-admin.sharepoint.com` and the URL for OneDrive is `https://contoso-my.sharepoint.com`, then you would enter `contoso` when the script prompts you for your domain name.</span></span>

- <span data-ttu-id="fce1c-158">**Naam van de zaak:** De naam van een bestaand geval.</span><span class="sxs-lookup"><span data-stu-id="fce1c-158">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="fce1c-159">Het script maakt een nieuwe wacht die aan deze zaak is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="fce1c-159">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="fce1c-160">**Naam van de wacht:** De naam van de wacht houden van het script wordt gemaakt en aan het opgegeven geval koppelen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-160">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="fce1c-161">**Zoekquery voor een op query's gebaseerde wachtfunctie:** U kunt een op query's gebaseerde wachtplaats maken, zodat alleen de inhoud die voldoet aan de opgegeven zoekcriteria, in de wacht wordt geplaatst.</span><span class="sxs-lookup"><span data-stu-id="fce1c-161">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="fce1c-162">Als u alle inhoud in de wacht wilt zetten, drukt u **op Enter** wanneer u wordt gevraagd om een zoekquery.</span><span class="sxs-lookup"><span data-stu-id="fce1c-162">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="fce1c-163">**De wacht in- of uitschakelen:** U kunt het script inschakelen nadat het is gemaakt of u kunt het script de wacht laten zetten zonder dit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-163">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="fce1c-164">Als u het script niet in de wacht hebt gezet, kunt u het later in het Beveiligings- & Compliancecentrum in- of door de volgende PowerShell-opdrachten uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="fce1c-164">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="fce1c-165">**Naam van het tekstbestand met** de lijst met gebruikers: de naam van het tekstbestand uit stap 2 met de lijst met gebruikers die u wilt toevoegen aan de wacht.</span><span class="sxs-lookup"><span data-stu-id="fce1c-165">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="fce1c-166">Als dit bestand zich in dezelfde map bevindt als het script, typt u de naam van het bestand (bijvoorbeeld HoldUsers.txt).</span><span class="sxs-lookup"><span data-stu-id="fce1c-166">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="fce1c-167">Als het tekstbestand zich in een andere map, typt u de volledige padnaam van het bestand.</span><span class="sxs-lookup"><span data-stu-id="fce1c-167">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="fce1c-168">Nadat u de informatie hebt verzameld waar u om wordt gevraagd door het script, is de laatste stap het uitvoeren van het script om de nieuwe wachtstand te maken en er gebruikers aan toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-168">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="fce1c-169">Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel van de bestandsnaam `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="fce1c-169">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="fce1c-170">Bijvoorbeeld `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="fce1c-170">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="fce1c-171">Open op uw lokale computer Windows PowerShell en ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="fce1c-171">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="fce1c-172">Voer het script uit; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fce1c-172">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="fce1c-173">Voer de informatie in waar u om wordt gevraagd in het script.</span><span class="sxs-lookup"><span data-stu-id="fce1c-173">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="fce1c-174">Het script maakt verbinding met Security & Compliance Center PowerShell en maakt vervolgens de nieuwe wacht in de eDiscovery-zaak en voegt de postvakken en OneDrive voor Bedrijven toe voor de gebruikers in de lijst.</span><span class="sxs-lookup"><span data-stu-id="fce1c-174">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="fce1c-175">U kunt naar de zaak op de **eDiscovery-pagina** in het beveiligings- & compliancecentrum gaan om de nieuwe wacht te bekijken.</span><span class="sxs-lookup"><span data-stu-id="fce1c-175">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="fce1c-176">Nadat het script is uitgevoerd, worden de volgende logboekbestanden gemaakt en worden deze opgeslagen in de map waar het script zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="fce1c-176">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="fce1c-177">**LocationsOnHold.txt:** Bevat een lijst met postvakken en OneDrive voor Bedrijven sites die het script in de wacht heeft gezet.</span><span class="sxs-lookup"><span data-stu-id="fce1c-177">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="fce1c-178">**LocationsNotOnHold.txt:** Bevat een lijst met postvakken en OneDrive voor Bedrijven sites die het script niet in de wacht heeft geplaatst.</span><span class="sxs-lookup"><span data-stu-id="fce1c-178">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="fce1c-179">Als een gebruiker een postvak heeft, maar geen OneDrive voor Bedrijven site, wordt de gebruiker opgenomen in de lijst met OneDrive voor Bedrijven sites die niet in de wacht zijn geplaatst.</span><span class="sxs-lookup"><span data-stu-id="fce1c-179">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="fce1c-180">**GetCaseHoldPolicy.txt:** Bevat de uitvoer van de **Get-CaseHoldPolicy-cmdlet** voor de nieuwe wacht, die het script heeft uitgevoerd na het maken van de nieuwe hold.</span><span class="sxs-lookup"><span data-stu-id="fce1c-180">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="fce1c-181">De gegevens die door deze cmdlet worden geretourneerd, bevatten een lijst met gebruikers van wie de postvakken en OneDrive voor Bedrijven in de wacht zijn geplaatst en of de wacht in- of uitgeschakeld is.</span><span class="sxs-lookup"><span data-stu-id="fce1c-181">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="fce1c-182">**GetCaseHoldRule.txt:** Bevat de uitvoer van de **Get-CaseHoldRule-cmdlet** voor de nieuwe wacht, die het script heeft uitgevoerd na het maken van de nieuwe wacht.</span><span class="sxs-lookup"><span data-stu-id="fce1c-182">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="fce1c-183">De informatie die door deze cmdlet wordt geretourneerd, bevat de zoekquery als u het script hebt gebruikt om een op query gebaseerde greep te maken.</span><span class="sxs-lookup"><span data-stu-id="fce1c-183">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>