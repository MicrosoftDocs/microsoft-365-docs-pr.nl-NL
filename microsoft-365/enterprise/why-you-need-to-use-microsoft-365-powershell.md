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
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="cb00b-103">Waarom u PowerShell voor Microsoft 365 moet gebruiken</span><span class="sxs-lookup"><span data-stu-id="cb00b-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="cb00b-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cb00b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cb00b-105">Met het Microsoft 365-Beheercentrum kunt u niet alleen uw gebruikersaccounts en licenties van Microsoft 365 beheren, maar u kunt ook uw Microsoft 365-Services beheren, zoals Exchange Online, teams en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cb00b-105">With the Microsoft 365 admin center, you can not only manage your Microsoft 365 user accounts and licenses, but you can also manage your Microsoft 365 services such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="cb00b-106">U kunt deze elementen echter ook beheren met PowerShell-opdrachten, waarbij u gebruikmaakt van een omgeving voor de opdrachtprompt en de scripts voor snelheid, automatisering en extra mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="cb00b-106">However, you can also manage these elements with PowerShell commands, taking advantage of a command-line and scripting language environment for speed, automation, and additional capability.</span></span>
  
<span data-ttu-id="cb00b-107">In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken voor het beheren van Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="cb00b-107">In this article, we'll show you these ways in which you can use PowerShell to manage Microsoft 365:</span></span>
  
- <span data-ttu-id="cb00b-108">Extra informatie weergeven die u niet kunt vinden in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="cb00b-108">Reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="cb00b-109">Configureer functies en instellingen alleen mogelijk met PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb00b-109">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="cb00b-110">Bulk activiteiten uitvoeren</span><span class="sxs-lookup"><span data-stu-id="cb00b-110">Perform bulk operations</span></span>
    
- <span data-ttu-id="cb00b-111">Gegevens filteren</span><span class="sxs-lookup"><span data-stu-id="cb00b-111">Filtering data</span></span>
    
- <span data-ttu-id="cb00b-112">Gegevens afdrukken of opslaan</span><span class="sxs-lookup"><span data-stu-id="cb00b-112">Print or save data</span></span>
    
- <span data-ttu-id="cb00b-113">Meerdere services beheren</span><span class="sxs-lookup"><span data-stu-id="cb00b-113">Manage across services</span></span>
    
<span data-ttu-id="cb00b-114">Voordat u begint, begrijpt u dat PowerShell voor Microsoft 365 een set modules voor Windows PowerShell is, een opdrachtregelomgeving voor Windows-Services en platformen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-114">Before you begin, understand that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="cb00b-115">In deze omgeving wordt een taal voor de opdrachtshell gemaakt die kan worden uitgebreid met extra modules en kan een eenvoudige of complexe opdracht of scripts worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="cb00b-115">This environment creates a command shell language that can be extended with additional modules and provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="cb00b-116">Wanneer u bijvoorbeeld de modules PowerShell voor Microsoft 365 installeert en verbinding maakt met uw Microsoft 365-abonnement, kunt u deze opdracht uitvoeren om alle gebruikerspostvakken voor Microsoft Exchange Online weer te geven:</span><span class="sxs-lookup"><span data-stu-id="cb00b-116">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run this command to list all of the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="cb00b-117">U kunt de lijst met postvakken ook eenvoudig uitvoeren met behulp van het Microsoft 365-Beheercentrum, maar u kunt het aantal items in alle lijsten voor alle sites van alle websites niet eenvoudig uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="cb00b-117">Getting the list of mailboxes can also be easily done using the Microsoft 365 admin center, but counting the number of items in all of the lists for all of the sites for all of your web apps cannot be easily done.</span></span>
  
<span data-ttu-id="cb00b-118">Houd er rekening mee dat PowerShell voor Microsoft 365 is ontworpen om het beheren van Microsoft 365 te bevorderen en de mogelijkheid om te zorgen dat u het Microsoft 365-Beheercentrum niet vervangt.</span><span class="sxs-lookup"><span data-stu-id="cb00b-118">Please note that PowerShell for Microsoft 365 is designed to augment and enhance your ability to manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="cb00b-119">Als beheerder dient u minstens vertrouwd te zijn met het gebruik van PowerShell voor Microsoft 365, vanwege enkele configuratieprocedures die alleen kunnen worden uitgevoerd met PowerShell-opdrachten voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb00b-119">As an administrator, you must become at least comfortable with using PowerShell for Microsoft 365 because there are some configuration procedures that can only be done with PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="cb00b-120">In deze gevallen moet u weten hoe u dit doet:</span><span class="sxs-lookup"><span data-stu-id="cb00b-120">In these cases, you will be required to understand how to:</span></span>
  
- <span data-ttu-id="cb00b-121">Installeer de PowerShell voor Microsoft 365-modules (maar één keer voor elke beheerders computer).</span><span class="sxs-lookup"><span data-stu-id="cb00b-121">Install the PowerShell for Microsoft 365 modules (done only once for each administrator computer).</span></span>
    
- <span data-ttu-id="cb00b-122">Maak verbinding met uw Microsoft 365-abonnement (eenmaal gedaan voor elke PowerShell-sessie).</span><span class="sxs-lookup"><span data-stu-id="cb00b-122">Connect to your Microsoft 365 subscription (done once for each PowerShell session).</span></span>
    
- <span data-ttu-id="cb00b-123">Verzamel de gegevens die u nodig hebt om de vereiste PowerShell voor Microsoft 365-opdrachten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="cb00b-123">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="cb00b-124">Voer de opdrachten voor PowerShell voor Microsoft 365 uit.</span><span class="sxs-lookup"><span data-stu-id="cb00b-124">Run the PowerShell for Microsoft 365 commands successfully.</span></span>
    
<span data-ttu-id="cb00b-125">Nadat u deze basisvaardigheden hebt leren, bent u niet verplicht de gebruikers van uw postvak in te stellen met de opdracht **Get-Mailbox** , en u bent niet verplicht om te zien hoe u een nieuwe opdracht kunt maken, zoals de vorige, zodat alle items in alle lijsten voor alle websites worden geteld voor alle websites van alle webapps.</span><span class="sxs-lookup"><span data-stu-id="cb00b-125">After learning these basic skills, you are not required to list your mailbox users with **Get-Mailbox** command, nor are you required to understand how to create a new command like the previous one to count all the items in all the lists for all of the sites for all of your web apps.</span></span> <span data-ttu-id="cb00b-126">Microsoft en de community van beheerders kunnen u helpen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-126">Microsoft and the community of administrators can help you with that as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="cb00b-127">PowerShell voor Microsoft 365 kan aanvullende informatie onthullen die u niet kunt zien in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="cb00b-127">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="cb00b-128">Het Microsoft 365-Beheercentrum geeft veel nuttige informatie weer, maar dit betekent niet dat alle mogelijke informatie wordt weergegeven die Microsoft 365 opslaat op gebruikers, licenties, postvakken en sites.</span><span class="sxs-lookup"><span data-stu-id="cb00b-128">The Microsoft 365 admin center displays a lot of useful information, but that doesn't mean that it displays all the possible information that Microsoft 365 stores on users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="cb00b-129">Hier ziet u een voorbeeld van **gebruikers en groepen** in het microsoft 365-Beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="cb00b-129">Here is an example for **users and groups** in the Microsoft 365 admin center:</span></span>
  
![Voorbeeld van de weergave van gebruikers en groepen in het Microsoft 365-Beheercentrum.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="cb00b-131">In veel gevallen wordt hiermee de informatie weergegeven die u moet weten.</span><span class="sxs-lookup"><span data-stu-id="cb00b-131">For many purposes, this displays the information you need to know.</span></span> <span data-ttu-id="cb00b-132">Er zijn echter situaties waarin u meer nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="cb00b-132">However, there are times when you need more.</span></span> <span data-ttu-id="cb00b-133">Microsoft 365 Licensing (en de Microsoft 365-functies die beschikbaar zijn voor een gebruiker), zijn bijvoorbeeld afhankelijk van de geografische locatie van die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cb00b-133">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depend in part on that user's geographic location.</span></span> <span data-ttu-id="cb00b-134">De beleidsregels en functies die u kunt verlengen naar een gebruiker die in de Verenigde Staten woont, kunnen niet hetzelfde zijn als de beleidsregels en functies die u kunt verlengen naar een gebruiker die in India of in België woont.</span><span class="sxs-lookup"><span data-stu-id="cb00b-134">The policies and features you can extend to a user who lives in the United States might not be the same as the policies and features you can extend to a user who lives in India or in Belgium.</span></span> <span data-ttu-id="cb00b-135">Met het Microsoft 365-Beheercentrum kunt u de geografische locatie van een gebruiker vaststellen aan de hand van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="cb00b-135">You can use the Microsoft 365 admin center to determine a user's geographic location with these steps:</span></span>
  
1. <span data-ttu-id="cb00b-136">Dubbelklik op de **weergavenaam**van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cb00b-136">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="cb00b-137">Klik in het deelvenster met eigenschappen van de gebruiker op **Details**.</span><span class="sxs-lookup"><span data-stu-id="cb00b-137">In the user properties display pane, click **details**.</span></span>
    
3. <span data-ttu-id="cb00b-138">Klik in het detail scherm op **extra details**.</span><span class="sxs-lookup"><span data-stu-id="cb00b-138">In the details display, click **additional details**.</span></span>
    
4. <span data-ttu-id="cb00b-139">Schuif omlaag totdat u het **land of de regio**van de kop ziet:</span><span class="sxs-lookup"><span data-stu-id="cb00b-139">Scroll down until you see the heading **Country or region**:</span></span>
    
     ![Voorbeeld van de regiogegevens voor een gebruiker in het Microsoft 365-Beheercentrum.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="cb00b-141">Schrijf de weergavenaam en locatie van de gebruiker op een vel papier, of kopieer en plak deze in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="cb00b-141">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span> 
    
<span data-ttu-id="cb00b-142">Voor elke gebruiker moet u deze procedure herhalen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-142">You must repeat this procedure for each user.</span></span> <span data-ttu-id="cb00b-143">Voor veel gebruikers kan dit een saaie taak zijn.</span><span class="sxs-lookup"><span data-stu-id="cb00b-143">For many users, this can be a tedious task.</span></span> <span data-ttu-id="cb00b-144">Met PowerShell voor Microsoft 365 kunt u deze informatie weergeven voor alle gebruikers met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="cb00b-144">With PowerShell for Microsoft 365, you can display this information for all of your users with the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="cb00b-145">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="cb00b-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="cb00b-146">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb00b-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="cb00b-147">Hier ziet u een voorbeeld van het beeldscherm:</span><span class="sxs-lookup"><span data-stu-id="cb00b-147">Here is an example of the display:</span></span>
  
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
>  <span data-ttu-id="cb00b-148">De uitleg van deze PowerShell-opdracht is: alle gebruikers in het huidige Microsoft 365-abonnement ( **Get-AzureADUser** ) krijgen, maar alleen de naam en de locatie weergeven voor elke gebruiker ( **Select DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-148">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription ( **Get-AzureADUser** ), but only display the name and location for each user ( **Select DisplayName, UsageLocation** ).</span></span>
  
<span data-ttu-id="cb00b-149">Aangezien PowerShell voor Microsoft 365 ondersteuning biedt voor een taal in de taal van de opdrachtshell, kunt u de informatie die u hebt verkregen, verder manipuleren met de opdracht **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="cb00b-149">Because PowerShell for Microsoft 365 supports a command shell language, you can further manipulate the information obtained from the **Get-AzureADUser** command.</span></span> <span data-ttu-id="cb00b-150">Bijvoorbeeld: u wilt deze gebruikers sorteren op hun locatie, met alle Braziliaanse gebruikers samen, alle gebruikers van de Verenigde Staten, enzovoort. Dit is de opdracht:</span><span class="sxs-lookup"><span data-stu-id="cb00b-150">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, etc. Here is the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="cb00b-151">Hier ziet u een voorbeeld van het beeldscherm:</span><span class="sxs-lookup"><span data-stu-id="cb00b-151">Here is an example of the display:</span></span>
  
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
>  <span data-ttu-id="cb00b-152">De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement overnemen, maar alleen de naam en de locatie weergeven voor elke gebruiker en ze eerst sorteren op hun locatie en vervolgens de namen ( **Sorteer UsageLocation, DisplayName** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location, and then their names ( **Sort UsageLocation, DisplayName** ).</span></span>
  
<span data-ttu-id="cb00b-153">U kunt ook extra filters gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cb00b-153">You can also employ additional filtering.</span></span> <span data-ttu-id="cb00b-154">Als u bijvoorbeeld alleen informatie wilt weergeven over gebruikers die op basis van Brazilië werken, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="cb00b-154">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="cb00b-155">Hier ziet u een voorbeeld van het beeldscherm:</span><span class="sxs-lookup"><span data-stu-id="cb00b-155">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  <span data-ttu-id="cb00b-156">De uitleg van deze PowerShell-opdracht luidt als volgt: Hiermee krijgt u alle gebruikers in het huidige Microsoft 365-abonnement te zien, waarvan de locatie Brazilië is ( **waarbij {$ \_ . UsageLocation-EQ "BR"}** ) en geef vervolgens de naam en de locatie van de gebruiker op.</span><span class="sxs-lookup"><span data-stu-id="cb00b-156">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription whose location is Brazil ( **Where {$\_.UsageLocation -eq "BR"}** ), then display the name and location for each user.</span></span>
  
 <span data-ttu-id="cb00b-157">**Een korte notitie over grotere domeinen**</span><span class="sxs-lookup"><span data-stu-id="cb00b-157">**A Quick Note Regarding Larger Domains**</span></span>
  
<span data-ttu-id="cb00b-158">Als u een zeer groot domein hebt met tientallen gebruikers, kunt u een aantal voorbeelden van het gebruik van dit artikel proberen te beperken.</span><span class="sxs-lookup"><span data-stu-id="cb00b-158">If you have a very large domain with tens of thousands of users, trying some of the examples we show in this article could lead to "throttling."</span></span> <span data-ttu-id="cb00b-159">Dat betekent dat, op basis van zaken zoals de kracht en de beschikbare bandbreedte van het netwerk, niet te veel tegelijk werkt.</span><span class="sxs-lookup"><span data-stu-id="cb00b-159">That means that, based on things like computing power and available network bandwidth, you're trying to do a little too much at one time.</span></span> <span data-ttu-id="cb00b-160">In grote gevallen willen grote organisaties sommige van deze PowerShell-opdrachten voor PowerShell voor Microsoft 365 splitsen in twee opdrachten.</span><span class="sxs-lookup"><span data-stu-id="cb00b-160">Because of that, larger organizations might want to split some of these PowerShell for Microsoft 365 commands into two commands.</span></span> <span data-ttu-id="cb00b-161">Met deze optie worden bijvoorbeeld alle gebruikersaccounts opgevraagd en worden de naam en de locatie van de gebruikersaccounts weergegeven:</span><span class="sxs-lookup"><span data-stu-id="cb00b-161">For example, this one command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="cb00b-162">Dit werkt prima voor kleinere domeinen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-162">That works great for smaller domains.</span></span> <span data-ttu-id="cb00b-163">In een grote organisatie moet u de gegevens mogelijk in twee opdrachten splitsen: één opdracht voor het opslaan van de informatie over de gebruikersaccount in een variabele en een andere opdracht om de benodigde informatie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="cb00b-163">In a large organization, however, you might need to split that into two commands: one command to store the user account information in a variable and another command to display the needed information.</span></span> <span data-ttu-id="cb00b-164">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="cb00b-164">Here is an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="cb00b-165">De uitleg van deze reeks PowerShell-opdrachten luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="cb00b-165">The interpretation of this set of PowerShell commands is:</span></span>
- <span data-ttu-id="cb00b-166">Zorg dat alle gebruikers in het huidige Microsoft 365-abonnement komen te staan en sla de gegevens op in een variabele met de naam $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-166">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="cb00b-167">De inhoud van de variabele $x weergeven, maar alleen de naam en de locatie opnemen voor elke gebruiker ( **$x | Selecteer DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-167">Display the contents of the variable $x, but only include the name and location for each user ( **$x | Select DisplayName, UsageLocation** ).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="cb00b-168">Microsoft 365 bevat functies die alleen kunnen worden geconfigureerd met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb00b-168">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="cb00b-169">Het Microsoft 365-Beheercentrum is bedoeld om toegang te bieden tot de meest voorkomende of meest voorkomende beheertaken die voor de meeste personen gelden.</span><span class="sxs-lookup"><span data-stu-id="cb00b-169">The Microsoft 365 admin center is intended to provide access to the most common or meaningful administrative tasks that apply to most people.</span></span> <span data-ttu-id="cb00b-170">Met andere woorden: het Microsoft 365-Beheercentrum is zo ontworpen dat de beheerder van het programma de meest voorkomende beheertaken kan uitvoeren met behulp van het hulpprogramma.</span><span class="sxs-lookup"><span data-stu-id="cb00b-170">In other words, the Microsoft 365 admin center was designed so that the typical administrator could use the tool to carry out the most common management tasks.</span></span> <span data-ttu-id="cb00b-171">Met deze definitie betekent dit dat er enkele taken die niet kunnen worden uitgevoerd, worden uitgevoerd met het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cb00b-171">By this definition, that means that there are some tasks that can't be completed by using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="cb00b-172">Het Skype voor bedrijven online-Beheercentrum biedt bijvoorbeeld een paar opties voor het maken van aangepaste uitnodigingen voor vergaderingen:</span><span class="sxs-lookup"><span data-stu-id="cb00b-172">For example, the Skype for Business Online Admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Voorbeeld van de weergave van aangepaste uitnodigingen voor vergaderingen in het Skype voor bedrijven online-Beheercentrum.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="cb00b-174">Met deze instellingen kunt u een aanraakscherm voor uitnodigingen voor vergaderingen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-174">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="cb00b-175">Er zijn echter meer instellingen voor de configuratie van de vergadering dan alleen voor het maken van aangepaste uitnodigingen voor vergaderingen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-175">However, there's more to meeting configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="cb00b-176">In het volgende voorbeeld is het bijvoorbeeld mogelijk dat vergaderingen:</span><span class="sxs-lookup"><span data-stu-id="cb00b-176">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="cb00b-177">Anonieme gebruikers om automatisch toegang tot elke vergadering te krijgen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-177">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="cb00b-178">Deelnemers kunnen de vergadering opnemen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-178">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="cb00b-179">Alle gebruikers in uw organisatie die als presentator worden aangewezen wanneer ze deelnemen aan de vergadering.</span><span class="sxs-lookup"><span data-stu-id="cb00b-179">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="cb00b-180">Deze instellingen zijn niet beschikbaar in het Skype voor bedrijven online-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cb00b-180">These settings are not available from the Skype for Business Online Admin center.</span></span> <span data-ttu-id="cb00b-181">U kunt ze echter wel beheren via PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb00b-181">However, you can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="cb00b-182">Dit is een opdracht waarmee u deze drie instellingen uitschakelt:</span><span class="sxs-lookup"><span data-stu-id="cb00b-182">Here is a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="cb00b-183">Voor deze opdracht moet u de [PowerShell-module voor Skype voor bedrijven online ](https://www.microsoft.com/download/details.aspx?id=39366)installeren.</span><span class="sxs-lookup"><span data-stu-id="cb00b-183">This command requires that you install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="cb00b-184">De uitleg van deze PowerShell-opdracht is: voor de instellingen voor nieuwe vergaderingen in Skype voor bedrijven online ( **set-CsMeetingConfiguration** ), schakelt u toestaan dat anonieme gebruikers geen toegang hebben tot vergaderingen (- **AdmitAnonymousUsersByDefault $False** ), schakelt u de mogelijkheid voordeel nemers uit om vergaderingen op te nemen ( **-AllowConferenceRecording $False** ) en niet alle gebruikers in uw organisatie als presentatoren ( **-DesignateAsPresenter**</span><span class="sxs-lookup"><span data-stu-id="cb00b-184">The interpretation of this PowerShell command is: For the settings for new Skype for Business Online meetings ( **Set-CsMeetingConfiguration** ), disable allowing anonymous users to gain automatic entrance to meetings ( **-AdmitAnonymousUsersByDefault $False** ), disable the ability for attendees to record meetings ( **-AllowConferenceRecording $False** ), and do not designate all users from your organization as presenters ( **-DesignateAsPresenter "None"** ).</span></span>
  
<span data-ttu-id="cb00b-185">Als u van gedachten verandert en deze standaardinstellingen wilt herstellen (al zijn ingeschakeld), voert u deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="cb00b-185">If you change your mind and want to restore these default settings (all of them enabled), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="cb00b-186">Dit is slechts één voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="cb00b-186">This is just one example.</span></span> <span data-ttu-id="cb00b-187">Er zijn andere redenen waarom u, als beheerder, moet worden vertrouwd met het uitvoeren van opdrachten van PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb00b-187">There are others, which is why you, as an administrator, need to be comfortable with running PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a><span data-ttu-id="cb00b-188">PowerShell voor Microsoft 365 is geweldig bij het uitvoeren van bulk activiteiten</span><span class="sxs-lookup"><span data-stu-id="cb00b-188">PowerShell for Microsoft 365 is great at carrying out bulk operations</span></span>

<span data-ttu-id="cb00b-189">Historisch, visuele interfaces zoals het Microsoft 365-Beheercentrum zijn vooral handig wanneer u één bewerking wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="cb00b-189">Historically, visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to perform.</span></span> <span data-ttu-id="cb00b-190">Als u bijvoorbeeld één gebruikersaccount wilt uitschakelen, kunt u het Microsoft 365-Beheercentrum gebruiken om snel een selectievakje te zoeken en uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-190">For example, if you need to disable one user account, you can use the Microsoft 365 admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="cb00b-191">Dit kan eenvoudiger zijn dan een soortgelijke bewerking uitvoeren in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb00b-191">This can be simpler than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="cb00b-192">Als u een groot aantal zaken of bepaalde items binnen een groot aantal andere zaken moet wijzigen, is het mogelijk dat u het Microsoft 365-Beheercentrum niet het beste gebruikt voor uw tijd.</span><span class="sxs-lookup"><span data-stu-id="cb00b-192">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best use of your time.</span></span> <span data-ttu-id="cb00b-193">Als u bijvoorbeeld het voorvoegsel van duizenden telefoonnummers moet wijzigen of als u een specifieke gebruiker, Ken Myer, wilt verwijderen uit al uw SharePoint Online-sites, hoe wilt u dit doen in het Microsoft 365-Beheercentrum?</span><span class="sxs-lookup"><span data-stu-id="cb00b-193">For example, if you had to change the prefix on thousands of phone numbers or you needed to remove a specific user, Ken Myer, from all of your SharePoint Online sites, how would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="cb00b-194">In het tweede voorbeeld hebt u verschillende honderd SharePoint Online-sites en weet u niet zeker welke namen van Meyer lid zijn.</span><span class="sxs-lookup"><span data-stu-id="cb00b-194">For the latter example, you have several hundred SharePoint Online sites and you don't know even know which ones of which Ken Meyer is a member.</span></span> <span data-ttu-id="cb00b-195">Dat betekent dat u eerst moet beginnen bij het Beheercentrum van Microsoft 365 en vervolgens deze procedure voor elke site moet uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="cb00b-195">That means you'll have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="cb00b-196">Klik op de **URL** van de site.</span><span class="sxs-lookup"><span data-stu-id="cb00b-196">Click the **URL** of the site.</span></span>
    
2. <span data-ttu-id="cb00b-197">Klik in het dialoogvenster **Eigenschappen van siteverzameling** op de koppeling naar het **adres** van de website om de site te openen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-197">In the **site collection properties** box, click the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="cb00b-198">Klik op de site op **delen**.</span><span class="sxs-lookup"><span data-stu-id="cb00b-198">On the site, click **Share**.</span></span>
    
4. <span data-ttu-id="cb00b-199">Klik in het dialoogvenster **delen** op de koppeling waarmee u alle gebruikers ziet met een machtiging voor de site:</span><span class="sxs-lookup"><span data-stu-id="cb00b-199">In the **Share** dialog box click the link that shows you all the users who have permissions to the site:</span></span>
    
     ![Voorbeeld van het weergeven van de leden van een SharePoint Online-site in het SharePoint Online-Beheercentrum.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="cb00b-201">Klik in het dialoogvenster **gedeeld met** op **Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="cb00b-201">In the **Shared With** dialog box, click **Advanced**.</span></span>
    
6. <span data-ttu-id="cb00b-202">Blader omlaag in de lijst met gebruikers, zoek en selecteer Ken Myer (ervan uitgaand dat hij of zij machtigingen heeft voor de site), en klik vervolgens op **Gebruikersmachtigingen verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="cb00b-202">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then click **Remove User Permissions**.</span></span>
    
<span data-ttu-id="cb00b-203">Dit kan veel tijd in beslag nemen voor meerdere honderden sites.</span><span class="sxs-lookup"><span data-stu-id="cb00b-203">This can take a long time for several hundred sites.</span></span>
  
<span data-ttu-id="cb00b-204">U kunt ook PowerShell voor Microsoft 365 gebruiken en de volgende opdracht om ken Myer van al uw sites te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="cb00b-204">The alternative is to use PowerShell for Microsoft 365 and the following command to remove Ken Myer from all of your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="cb00b-205">Voor deze opdracht moet u de [PowerShell-module van SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)installeren.</span><span class="sxs-lookup"><span data-stu-id="cb00b-205">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="cb00b-206">De uitleg van deze PowerShell-opdracht luidt als volgt: Zorg dat alle SharePoint-sites in het huidige Microsoft 365-abonnement ( **Get-SPOSite** ) en voor elke site worden verwijderd uit de lijst met gebruikers die toegang hebben tot de PowerShell **-site $ \_ . URL-login "kenmyer@litwareinc.com"}** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-206">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription ( **Get-SPOSite** ) and for each site, remove Ken Meyer from the list of users who can access it ( **ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer@litwareinc.com"}** ).</span></span>
  
<span data-ttu-id="cb00b-207">Aangezien we Microsoft 365 vertellen dat ze Ken Meyer van elke site te verwijderen, waaronder de gebruikers die hij niet toegang hebben, wordt in de weergave van deze opdracht fouten weergegeven voor de sites waartoe hij momenteel geen toegang heeft.</span><span class="sxs-lookup"><span data-stu-id="cb00b-207">Because we are telling Microsoft 365 to remove Ken Meyer from every site, including those in which he does not have access, the display of this command will show errors for those sites in which he does not currently have access.</span></span> <span data-ttu-id="cb00b-208">We kunnen met een extra voorwaarde voor deze opdracht de sleutel Meyer alleen verwijderen van de sites die deze hebben in de aanmeldingslijst, maar de vermelde fouten veroorzaken geen schade voor de sites zelf.</span><span class="sxs-lookup"><span data-stu-id="cb00b-208">We can use an additional condition on this command to remove Key Meyer only from the sites that have him in their login list, but the listed errors cause no harm to the sites themselves.</span></span> <span data-ttu-id="cb00b-209">Het kan een paar minuten duren voordat de opdracht is uitgevoerd op honderden sites, in plaats van uren via het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cb00b-209">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="cb00b-210">Hier is nog een voorbeeld van een bulkbewerking.</span><span class="sxs-lookup"><span data-stu-id="cb00b-210">Here is another bulk operation example.</span></span> <span data-ttu-id="cb00b-211">Gebruik deze opdracht om Bonnie Kearney, een nieuwe SharePoint-beheerder, toe te voegen aan alle sites in de organisatie:</span><span class="sxs-lookup"><span data-stu-id="cb00b-211">Use this command to add Bonnie Kearney, a new SharePoint administrator, to all of the sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  <span data-ttu-id="cb00b-212">De uitleg van deze PowerShell-opdracht is: alle SharePoint-sites in het huidige Microsoft 365-abonnement en voor elke site gebruiken om de Bonnie Kearney toegang toe te voegen aan de groep leden van de site ( **foreach {add-partner-site $ \_ . URL-login "bkearney@litwareinc.com"-groep "leden"}** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-212">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription and for each site, allow Bonnie Kearney access by adding her login name to the Members group of the site ( **ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}** ).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="cb00b-213">PowerShell voor Microsoft 365 is geweldig bij het filteren van gegevens</span><span class="sxs-lookup"><span data-stu-id="cb00b-213">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="cb00b-214">Met het Microsoft 365-Beheercentrum kunt u op verschillende manieren gegevens filteren om snel en eenvoudig een gerichte subset met informatie te vinden.</span><span class="sxs-lookup"><span data-stu-id="cb00b-214">The Microsoft 365 admin center provides several different ways to filter your data to quickly and easily locate a targeted subset of information.</span></span> <span data-ttu-id="cb00b-215">Met Exchange kunt u bijvoorbeeld eenvoudig filteren op vrijwel elke eigenschap van een gebruikerspostvak.</span><span class="sxs-lookup"><span data-stu-id="cb00b-215">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="cb00b-216">Hier ziet u bijvoorbeeld de lijst met postvakken voor alle gebruikers die in de plaats van Bloomington wonen:</span><span class="sxs-lookup"><span data-stu-id="cb00b-216">For example, here is the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Voorbeeld van het gebruik van Geavanceerd zoeken in het Microsoft 365-Beheercentrum voor de lijst met postvakken voor alle gebruikers die in de Bloomington van de stad wonen.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="cb00b-218">In het Exchange-Beheercentrum kunt u ook filtercriteria combineren.</span><span class="sxs-lookup"><span data-stu-id="cb00b-218">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="cb00b-219">U vindt bijvoorbeeld de postvakken voor alle personen die in Bloomington wonen en die op de afdeling financiën werken.</span><span class="sxs-lookup"><span data-stu-id="cb00b-219">For example, you can find the mailboxes for all the people who live in Bloomington and who work in the Finance department.</span></span> 
  
<span data-ttu-id="cb00b-220">Er zijn echter beperkingen voor wat u kunt doen in het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cb00b-220">However, there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="cb00b-221">U kunt bijvoorbeeld de postvakken vinden van personen die in Bloomington of San Diego, of naar de postvakken van de mensen die niet in Bloomington wonen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-221">For example, maybe you'd like to find the mailboxes of people who live in Bloomington or San Diego, or the mailboxes for all the people who don't live in Bloomington.</span></span> 
  
<span data-ttu-id="cb00b-222">Met PowerShell voor Microsoft 365 kunt u een lijst met postvakken krijgen van alle personen die live in de steden van Bloomington of San Diego met deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="cb00b-222">With PowerShell for Microsoft 365, you can get a list of mailboxes for all the people who live in the cities of Bloomington or San Diego with this command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="cb00b-223">Hier ziet u een voorbeeld van het beeldscherm:</span><span class="sxs-lookup"><span data-stu-id="cb00b-223">Here is an example of the display:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  <span data-ttu-id="cb00b-224">De uitleg van deze PowerShell-opdracht is: alle gebruikers in het huidige abonnement van Microsoft 365 met een postvak in de steden van een San Diego of Bloomington ( **waarbij {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-en ($ \_ . City-EQ "San Diego"-of $ \_ . Plaats-EQ "Bloomington")}** ) en geef vervolgens de naam en de plaats voor elk van de gebruikers ( **Selecteer DisplayName, plaats** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-224">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox in the cities of either San Diego or Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}** ), then display the name and city for each ( **Select DisplayName, City** ).</span></span>
  
<span data-ttu-id="cb00b-225">Als u alle postvakken wilt weergeven voor personen die wonen, met uitzondering van Bloomington, is dit de opdracht:</span><span class="sxs-lookup"><span data-stu-id="cb00b-225">To list all the mailboxes for people who live anywhere except Bloomington, here is the command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="cb00b-226">Hier ziet u een voorbeeld van het beeldscherm:</span><span class="sxs-lookup"><span data-stu-id="cb00b-226">Here is an example of the display:</span></span>
  
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
>  <span data-ttu-id="cb00b-227">De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement krijgen die een postvak hebben dat zich niet in de plaats van Bloomington bevindt ( **waarbij {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-en $ \_ . Plaats-ne "Bloomington"}** ) en geef vervolgens de naam en plaats op voor elk.</span><span class="sxs-lookup"><span data-stu-id="cb00b-227">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}** ), then display the name and city for each.</span></span>
  
<span data-ttu-id="cb00b-228">U kunt ook jokertekens in uw PowerShell-filters gebruiken om een deel van een naam te vinden.</span><span class="sxs-lookup"><span data-stu-id="cb00b-228">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="cb00b-229">Stel dat u op zoek bent naar een gebruikersaccount en dat u zeker weet dat de achternaam van de persoon is, of misschien Henderson, of misschien de naam Jorgenson.</span><span class="sxs-lookup"><span data-stu-id="cb00b-229">For example, suppose you're looking for a user account, and all you can remember is that their last name was Anderson, or maybe Henderson, or maybe it was Jorgenson.</span></span>
  
<span data-ttu-id="cb00b-230">U kunt deze gebruiker in het Microsoft 365-Beheercentrum bijhouden met behulp van het hulpprogramma zoeken en drie verschillende zoekopdrachten uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="cb00b-230">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="cb00b-231">Eén voor  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="cb00b-231">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="cb00b-232">Eén voor  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="cb00b-232">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="cb00b-233">Eén voor  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="cb00b-233">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="cb00b-234">Aangezien alle drie deze namen eindigen op ' zoon ', kunt u aangeven dat PowerShell alle gebruikers waarvan de naam eindigt op ' zoon ' weergeven.</span><span class="sxs-lookup"><span data-stu-id="cb00b-234">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="cb00b-235">Dit is de opdracht:</span><span class="sxs-lookup"><span data-stu-id="cb00b-235">Here is the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  <span data-ttu-id="cb00b-236">De uitleg van deze PowerShell-opdracht is: alle gebruikers in het huidige Microsoft 365-abonnement gebruiken, maar u kunt een filter gebruiken dat alleen de gebruikers bevat waarvan de achternaam eindigt op ' zoon ' ( **-filter ' {LastName-like ' \* zoon '} '** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-236">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" ( **-Filter '{LastName -like "\*son"}'** ).</span></span> <span data-ttu-id="cb00b-237">De \* tekenreeks voor een willekeurige willekeurige tekenreeks, met letters in het geval van de achternaam van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cb00b-237">The \* stands for any set of characters, which are letters in the case of the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="cb00b-238">Met PowerShell voor Microsoft 365 kunt u eenvoudig gegevens afdrukken of opslaan</span><span class="sxs-lookup"><span data-stu-id="cb00b-238">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="cb00b-239">Met het Microsoft 365-Beheercentrum kunt u lijsten met gegevens weergeven.</span><span class="sxs-lookup"><span data-stu-id="cb00b-239">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="cb00b-240">Hier ziet u een voorbeeld van het Skype voor bedrijven online-Beheercentrum met een lijst met gebruikers die zijn ingeschakeld voor Skype voor bedrijven online:</span><span class="sxs-lookup"><span data-stu-id="cb00b-240">Here is an example of the Skype for Business Online Admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Voorbeeld van het Skype voor bedrijven online-Beheercentrum met een lijst met gebruikers die zijn ingeschakeld voor Skype voor bedrijven online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="cb00b-242">Als u deze gegevens wilt opslaan in een bestand, moet u deze kopiëren en plakken in een document of Excel.</span><span class="sxs-lookup"><span data-stu-id="cb00b-242">To save that information to a file, you must copy and paste it into a document or Excel.</span></span> <span data-ttu-id="cb00b-243">In beide gevallen is er mogelijk extra opmaak nodig voor de kopie.</span><span class="sxs-lookup"><span data-stu-id="cb00b-243">In either case, the copy might require additional formatting.</span></span> <span data-ttu-id="cb00b-244">Daarnaast biedt het Microsoft 365-Beheercentrum geen manier om de weergegeven lijst rechtstreeks af te drukken.</span><span class="sxs-lookup"><span data-stu-id="cb00b-244">Additionally, the Microsoft 365 admin center does not provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="cb00b-245">Gelukkig kunt u PowerShell gebruiken om de lijst niet alleen weer te geven en deze op te slaan in een bestand dat u eenvoudig kunt importeren in Excel.</span><span class="sxs-lookup"><span data-stu-id="cb00b-245">Fortunately, you can use PowerShell to not only display the list, but save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="cb00b-246">Hier ziet u een voorbeeld van een knop om Skype voor bedrijven online-gebruikersgegevens op te slaan in een CSV-bestand (door komma's gescheiden waarden), een bestand dat gemakkelijk kan worden geïmporteerd als een tabel in een Excel-werkblad:</span><span class="sxs-lookup"><span data-stu-id="cb00b-246">Here is an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, a file that can be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="cb00b-247">Hier ziet u een voorbeeld van het beeldscherm:</span><span class="sxs-lookup"><span data-stu-id="cb00b-247">Here is an example of the display:</span></span>
  
![Voorbeeld van een tabel die in een Excel-werkblad is geïmporteerd voor gebruikersgegevens van Skype voor bedrijven online die zijn opgeslagen in een CSV-bestand (door komma's gescheiden waarden).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  <span data-ttu-id="cb00b-249">De uitleg van deze PowerShell-opdracht is: Haal alle gebruikers van Skype voor bedrijven online in het huidige Microsoft 365-abonnement ( **Get-CsOnlineUser** ), vraag alleen de gebruikersnaam, de UPN en de locatie op ( **Selecteer DisplayName, userPrincipalName, UsageLocation** ) en sla deze informatie vervolgens op in het CSV-bestand met de naam C: \\ Logboeken \\SfBUsers.csv ( **export- \\ \\SfBUsers.csv CSV**</span><span class="sxs-lookup"><span data-stu-id="cb00b-249">The interpretation of this PowerShell command is: Get all of the Skype for Business Online users in the current Microsoft 365 subscription ( **Get-CsOnlineUser** ), obtain only the user name, UPN, and location ( **Select DisplayName, UserPrincipalName, UsageLocation** ), and then save that information in CSV file named C:\\Logs\\SfBUsers.csv ( **Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation** ).</span></span>
  
<span data-ttu-id="cb00b-250">U kunt ook opties gebruiken om deze lijst op te slaan als een XML-bestand of als een HTML-pagina.</span><span class="sxs-lookup"><span data-stu-id="cb00b-250">You can also use options to save this list as an XML file or as an HTML page.</span></span> <span data-ttu-id="cb00b-251">Met extra PowerShell-opdrachten kunt u de functie rechtstreeks opslaan als een Excel-bestand, met eventueel aangepaste opmaak.</span><span class="sxs-lookup"><span data-stu-id="cb00b-251">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you desire.</span></span> 
  
<span data-ttu-id="cb00b-252">U kunt ook de uitvoer van een PowerShell-opdracht verzenden waarmee een lijst rechtstreeks wordt weergegeven naar de standaardprinter in Windows.</span><span class="sxs-lookup"><span data-stu-id="cb00b-252">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="cb00b-253">Hier ziet u een voorbeeld van een opdracht:</span><span class="sxs-lookup"><span data-stu-id="cb00b-253">Here is an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="cb00b-254">Het afgedrukte document ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="cb00b-254">Here's what your printed document will look like:</span></span>
  
![Voorbeeld van een document dat de uitvoer is van een PowerShell-opdracht die rechtstreeks naar de standaardprinter in Windows werd genoemd.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  <span data-ttu-id="cb00b-256">De uitleg van deze PowerShell-opdracht is: Download alle gebruikers van Skype voor bedrijven online in het huidige Microsoft 365-abonnement, verkrijg alleen de gebruikersnaam, UPN en locatie, en stuur deze informatie naar de standaardprinter van Windows ( **out-printer** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-256">The interpretation of this PowerShell command is:  Get all of the Skype for Business Online users in the current Microsoft 365 subscription, obtain only the user name, UPN, and location, and then send that information to the default Windows printer ( **Out-Printer** ).</span></span>
  
<span data-ttu-id="cb00b-257">Het afgedrukte document heeft dezelfde eenvoudige opmaak als de weergave in het PowerShell-opdrachtvenster, maar nadat u een PowerShell-opdracht hebt gemaakt om een lijst te maken die u nodig hebt, hoeft u alleen maar de tekst toe **te voegen. Uitchecken** naar het einde van de opdracht, zodat u kunt werken met een afdruk.</span><span class="sxs-lookup"><span data-stu-id="cb00b-257">The printed document has the same simple formatting as the display within the PowerShell command window, but once you have created a PowerShell command to list what you need, you just add **| Out-Printer** to the end of the command to get a hard copy to work from.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="cb00b-258">Met PowerShell voor Microsoft 365 kunt u verschillende server producten beheren</span><span class="sxs-lookup"><span data-stu-id="cb00b-258">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="cb00b-259">De verschillende onderdelen waaruit Microsoft 365 wordt gebruikt, zijn ontworpen om samen te werken.</span><span class="sxs-lookup"><span data-stu-id="cb00b-259">The different components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="cb00b-260">U kunt bijvoorbeeld een nieuwe gebruiker toevoegen aan Microsoft 365 en wanneer u dit doet, geeft u deze informatie op als de afdeling en het telefoonnummer van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cb00b-260">For example, suppose you add a new user to Microsoft 365 and, when you do, you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="cb00b-261">Deze informatie is dan beschikbaar als u de gegevens van de gebruiker opent met behulp van een van de Microsoft 365-Services: Skype voor bedrijven online, Exchange of SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cb00b-261">That information will then be available if you access the user's information using any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint Online.</span></span>
  
<span data-ttu-id="cb00b-262">Dat is voor algemene informatie die de producten Suite beslaat.</span><span class="sxs-lookup"><span data-stu-id="cb00b-262">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="cb00b-263">Productspecifieke informatie: voor informatie over het Exchange-postvak van een gebruiker: is doorgaans niet beschikbaar in de hele suite.</span><span class="sxs-lookup"><span data-stu-id="cb00b-263">Product-specific information-for example, information about a user's Exchange mailbox-is typically not available across the suite.</span></span> <span data-ttu-id="cb00b-264">Als u bijvoorbeeld wilt weten of het postvak van een gebruiker is ingeschakeld of niet, is deze informatie alleen beschikbaar in het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cb00b-264">For example, if you want to know if a user's mailbox is enabled or not, that information is available only in the Exchange Admin center.</span></span> 
  
<span data-ttu-id="cb00b-265">Stel dat u een rapport wilt maken waarin de volgende informatie voor alle gebruikers wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="cb00b-265">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="cb00b-266">De weergavenaam van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="cb00b-266">The user's display name</span></span>
    
- <span data-ttu-id="cb00b-267">Of de gebruiker een licentie heeft voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb00b-267">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="cb00b-268">Of het Exchange-postvak van de gebruiker is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="cb00b-268">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="cb00b-269">Of de gebruiker is ingeschakeld voor Skype voor bedrijven online</span><span class="sxs-lookup"><span data-stu-id="cb00b-269">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="cb00b-270">U kunt het Microsoft 365-Beheercentrum momenteel niet gebruiken om eenvoudig een dergelijk rapport te maken.</span><span class="sxs-lookup"><span data-stu-id="cb00b-270">You currently cannot use the Microsoft 365 admin center to easily produce such a report.</span></span> <span data-ttu-id="cb00b-271">In plaats daarvan moet u een afzonderlijk document maken om de gegevens op te slaan, zoals een Excel-werkblad, en alle gebruikersnamen en licentie-informatie krijgen via het Microsoft 365-Beheercentrum, informatie over de Postvak krijgen via het Exchange-Beheercentrum en vervolgens de gegevens in het Skype voor bedrijven online-Beheercentrum verzamelen en combineren.</span><span class="sxs-lookup"><span data-stu-id="cb00b-271">Instead, you'll have to create a separate document to store the information, like an Excel worksheet, and get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then collate and combine that information.</span></span>
  
<span data-ttu-id="cb00b-272">Het alternatief is een PowerShell-script gebruiken om dit rapport voor u samen te stellen.</span><span class="sxs-lookup"><span data-stu-id="cb00b-272">The alternative is to use a PowerShell script to compile that report for you.</span></span>
  
<span data-ttu-id="cb00b-273">Het volgende voorbeeldscript is ingewikkelder dan de opdrachten die u tot nu toe hebt gezien in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="cb00b-273">The following example script is more complicated than the commands you have seen so far in this article.</span></span> <span data-ttu-id="cb00b-274">Maar het is mogelijk dat het gebruik van PowerShell voor het maken van weergaven van informatie die zeer moeilijk te doen zijn.</span><span class="sxs-lookup"><span data-stu-id="cb00b-274">But, it shows the potential of using PowerShell to create views of information that are very difficult to do otherwise.</span></span> <span data-ttu-id="cb00b-275">Hier is het script waarmee de benodigde lijst kan worden gecompileerd en weergegeven:</span><span class="sxs-lookup"><span data-stu-id="cb00b-275">Here is the script that can compile and display the needed list:</span></span>
  
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

<span data-ttu-id="cb00b-276">Hier ziet u een voorbeeld van het beeldscherm:</span><span class="sxs-lookup"><span data-stu-id="cb00b-276">Here is an example of the display:</span></span>
  
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

<span data-ttu-id="cb00b-277">De uitleg van dit PowerShell-script luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="cb00b-277">The interpretation of this PowerShell script is:</span></span>  

- <span data-ttu-id="cb00b-278">Zorg dat alle gebruikers in het huidige Microsoft 365-abonnement komen te staan en sla de gegevens op in een variabele met de naam $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-278">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="cb00b-279">Een lussen starten die worden uitgevoerd op alle gebruikers in de variabele met de naam $x ( **foreach ($i in $x)** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-279">Start a loop that runs over all the users in the variable named $x ( **foreach ($i in $x)** ).</span></span>  
- <span data-ttu-id="cb00b-280">Definieer een variabele met de naam $y en sla de informatie over het postvak van de gebruiker op ( **$y = Get-Mailbox-Identity $i. userPrincipalName** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-280">Define a variable named $y and store the user's mailbox information in it ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="cb00b-281">Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam IsMailBoxEnabled en stel deze in op de waarde van de eigenschap IsMailBoxEnabled van het postvak van de gebruiker ( **$i | Add-member-MemberType NoteProperty-name IsMailboxEnabled-value $y. IsMailboxEnabled** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-281">Add a new property to the user information named IsMailBoxEnabled and set it to the value of the IsMailBoxEnabled property of the user's mailbox ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).</span></span>
- <span data-ttu-id="cb00b-282">Definieer een variabele met de naam $y en sla de informatie over de Skype voor bedrijven online-gegevens van de gebruiker op ( **$y = Get-CsOnlineUser-Identity $i. userPrincipalName** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-282">Define a variable named $y and store the user's Skype for Business Online information in it ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="cb00b-283">Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam EnabledForSfB en stel deze in op de waarde van de eigenschap ingeschakeld van de Skype voor bedrijven online-informatie van de gebruiker ( **$i | Add-member-MemberType NoteProperty-name EnabledForSfB-value $y. enabled** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-283">Add a new property to the user information named EnabledForSfB and set it to the value of the Enabled property of the user's Skype for Business Online information ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).</span></span>
- <span data-ttu-id="cb00b-284">U kunt de lijst met gebruikers weergeven, maar alleen de naam ervan opnemen, ongeacht of ze een licentie hebben en de twee nieuwe eigenschappen om aan te geven of hun postvak is ingeschakeld en of ze zijn ingeschakeld voor Skype voor bedrijven online ( **$x | Selecteer DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span><span class="sxs-lookup"><span data-stu-id="cb00b-284">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb00b-285">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cb00b-285">See also</span></span>

[<span data-ttu-id="cb00b-286">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb00b-286">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cb00b-287">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb00b-287">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cb00b-288">Windows PowerShell gebruiken om rapporten te maken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb00b-288">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

