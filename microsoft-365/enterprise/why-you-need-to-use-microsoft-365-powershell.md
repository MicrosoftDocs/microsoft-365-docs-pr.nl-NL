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
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="d16a8-103">Waarom u PowerShell voor Microsoft 365 moet gebruiken</span><span class="sxs-lookup"><span data-stu-id="d16a8-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="d16a8-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d16a8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d16a8-105">Met het Microsoft 365-Beheercentrum kunt u uw gebruikersaccounts en licenties voor Microsoft 365 beheren.</span><span class="sxs-lookup"><span data-stu-id="d16a8-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="d16a8-106">U kunt ook uw Microsoft 365-Services beheren, zoals Exchange Online, teams en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d16a8-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="d16a8-107">Als u in plaats hiervan PowerShell gebruikt voor het beheren van deze services, kunt u gebruikmaken van de taal omgeving voor de opdrachtprompt en de scripts voor snelheid, automatisering en extra mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="d16a8-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="d16a8-108">In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken voor het beheren van Microsoft 365 voor:</span><span class="sxs-lookup"><span data-stu-id="d16a8-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="d16a8-109">Extra informatie weergeven die u niet kunt zien in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d16a8-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="d16a8-110">Configureer functies en instellingen alleen mogelijk met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d16a8-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="d16a8-111">Bulk activiteiten uitvoeren</span><span class="sxs-lookup"><span data-stu-id="d16a8-111">Do bulk operations</span></span>
    
- <span data-ttu-id="d16a8-112">Gegevens filteren</span><span class="sxs-lookup"><span data-stu-id="d16a8-112">Filter data</span></span>
    
- <span data-ttu-id="d16a8-113">Gegevens afdrukken of opslaan</span><span class="sxs-lookup"><span data-stu-id="d16a8-113">Print or save data</span></span>
    
- <span data-ttu-id="d16a8-114">Meerdere services beheren</span><span class="sxs-lookup"><span data-stu-id="d16a8-114">Manage across services</span></span>
    
<span data-ttu-id="d16a8-115">Houd er rekening mee dat PowerShell voor Microsoft 365 een set modules voor Windows PowerShell is, een opdrachtregelomgeving voor Windows-Services en platformen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="d16a8-116">In deze omgeving wordt een opdrachtshell taal gemaakt die kan worden uitgebreid met extra modules.</span><span class="sxs-lookup"><span data-stu-id="d16a8-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="d16a8-117">U kunt eenvoudige of complexe opdrachten of scripts uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d16a8-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="d16a8-118">Wanneer u bijvoorbeeld de modules PowerShell voor Microsoft 365 installeert en verbinding maakt met uw Microsoft 365-abonnement, kunt u de volgende opdracht uitvoeren om alle gebruikerspostvakken voor Microsoft Exchange Online weer te geven:</span><span class="sxs-lookup"><span data-stu-id="d16a8-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="d16a8-119">U kunt ook de lijst met postvakken downloaden met behulp van het Microsoft 365-Beheercentrum, maar u kunt wel de items in alle lijsten tellen voor alle sites voor al uw web apps.</span><span class="sxs-lookup"><span data-stu-id="d16a8-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="d16a8-120">PowerShell voor Microsoft 365 is bedoeld voor hulp bij het beheren van Microsoft 365, het niet vervangen van het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d16a8-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="d16a8-121">Beheerders moeten PowerShell voor Microsoft 365 kunnen gebruiken, omdat er enkele configuratieprocedures zijn die alleen kunnen worden uitgevoerd via de PowerShell-opdrachten voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d16a8-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="d16a8-122">Voor deze gevallen moet u weten hoe u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="d16a8-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="d16a8-123">Installeer de PowerShell voor Microsoft 365-modules (slechts één keer uitgevoerd voor elke beheerders computer).</span><span class="sxs-lookup"><span data-stu-id="d16a8-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="d16a8-124">Maak verbinding met uw Microsoft 365-abonnement (één keer voor elke PowerShell-sessie).</span><span class="sxs-lookup"><span data-stu-id="d16a8-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="d16a8-125">Verzamel de gegevens die u nodig hebt om de vereiste PowerShell voor Microsoft 365-opdrachten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d16a8-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="d16a8-126">Voer PowerShell voor Microsoft 365-opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="d16a8-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="d16a8-127">Wanneer u deze basisvaardigheden hebt leren, hoeft u uw postvak gebruikers niet te vermelden met de opdracht **Get-postvak** .</span><span class="sxs-lookup"><span data-stu-id="d16a8-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="d16a8-128">U hoeft ook niet te leren hoe u een nieuwe opdracht kunt maken, zoals met de opdracht eerder is vermeld voor het tellen van alle items in alle lijsten voor alle sites van alle webapps.</span><span class="sxs-lookup"><span data-stu-id="d16a8-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="d16a8-129">Microsoft en de community van beheerders kunnen u helpen bij het uitvoeren van dergelijke taken.</span><span class="sxs-lookup"><span data-stu-id="d16a8-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="d16a8-130">PowerShell voor Microsoft 365 kan informatie onthullen die u niet kunt zien in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d16a8-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="d16a8-131">In het Microsoft 365-Beheercentrum wordt veel nuttige informatie weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d16a8-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="d16a8-132">In deze weergave worden niet alle mogelijke informatie weergegeven die Microsoft 365 biedt over gebruikers, licenties, postvakken en sites.</span><span class="sxs-lookup"><span data-stu-id="d16a8-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="d16a8-133">Hier ziet u een voorbeeld van *gebruikers en groepen* in het microsoft 365-Beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="d16a8-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Voorbeeld van de weergave van gebruikers en groepen in het Microsoft 365-Beheercentrum.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="d16a8-135">Deze weergave bevat de informatie die u nodig hebt in een groot aantal gevallen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="d16a8-136">Er zijn echter situaties waarin u meer nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="d16a8-136">However, there are times when you need more.</span></span> <span data-ttu-id="d16a8-137">Microsoft 365 Licensing (en de Microsoft 365-functies die beschikbaar zijn voor een gebruiker), is bijvoorbeeld afhankelijk van de geografische locatie van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d16a8-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="d16a8-138">De beleidsregels en functies die u kunt verlengen naar een gebruiker die niet in de Verenigde Staten woont, zijn mogelijk niet hetzelfde als de gebruikers die u in India of in België kunt uitbreiden.</span><span class="sxs-lookup"><span data-stu-id="d16a8-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="d16a8-139">Voer de volgende stappen uit in het Microsoft 365-Beheercentrum om de geografische locatie van een gebruiker te bepalen:</span><span class="sxs-lookup"><span data-stu-id="d16a8-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="d16a8-140">Dubbelklik op de **weergavenaam**van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d16a8-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="d16a8-141">Selecteer in het deelvenster weergave van de gebruikerseigenschappen de optie **Details**.</span><span class="sxs-lookup"><span data-stu-id="d16a8-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="d16a8-142">Selecteer **extra details**in het detail scherm.</span><span class="sxs-lookup"><span data-stu-id="d16a8-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="d16a8-143">Schuif totdat u het **land of de regio**van de kop vindt:</span><span class="sxs-lookup"><span data-stu-id="d16a8-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Voorbeeld van de regiogegevens voor een gebruiker in het Microsoft 365-Beheercentrum.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="d16a8-145">Schrijf de weergavenaam en locatie van de gebruiker op een vel papier, of kopieer en plak deze in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="d16a8-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="d16a8-146">Voor elke gebruiker moet u deze procedure herhalen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="d16a8-147">Als u veel gebruikers hebt, kan dit een zeer vervelend proces zijn.</span><span class="sxs-lookup"><span data-stu-id="d16a8-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="d16a8-148">Met PowerShell voor Microsoft 365 kunt u deze informatie voor al uw gebruikers weergeven met behulp van de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="d16a8-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="d16a8-149">PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam.</span><span class="sxs-lookup"><span data-stu-id="d16a8-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="d16a8-150">U dient deze cmdlets uit te voeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d16a8-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="d16a8-151">Hier ziet u een voorbeeld van de resultaten:</span><span class="sxs-lookup"><span data-stu-id="d16a8-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="d16a8-152">De uitleg van deze PowerShell-opdracht is: alle gebruikers in het huidige Microsoft 365-abonnement (**Get-AzureADUser**) krijgen, maar alleen de naam en de locatie weergeven voor elke gebruiker (**Select DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="d16a8-153">Aangezien PowerShell voor Microsoft 365 ondersteuning biedt voor een schakeloptie voor de shell, kunt u de gegevens die zijn verkregen met de opdracht **Get-AzureADUser** , verder bewerken.</span><span class="sxs-lookup"><span data-stu-id="d16a8-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="d16a8-154">Bijvoorbeeld: u wilt deze gebruikers sorteren op hun locatie, met alle Braziliaanse gebruikers samen, alle gebruikers van de Verenigde Staten, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="d16a8-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="d16a8-155">Dit is de opdracht:</span><span class="sxs-lookup"><span data-stu-id="d16a8-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="d16a8-156">Hier ziet u een voorbeeld van de resultaten:</span><span class="sxs-lookup"><span data-stu-id="d16a8-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="d16a8-157">De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement krijgen, maar alleen de naam en de locatie weergeven voor elke gebruiker en ze eerst sorteren op hun locatie en vervolgens de naam van een gebruiker (**sorteren UsageLocation, DisplayName**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="d16a8-158">U kunt ook extra filters gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d16a8-158">You can also use additional filtering.</span></span> <span data-ttu-id="d16a8-159">Als u bijvoorbeeld alleen informatie wilt weergeven over gebruikers die op basis van Brazilië werken, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="d16a8-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="d16a8-160">Hier ziet u een voorbeeld van de resultaten:</span><span class="sxs-lookup"><span data-stu-id="d16a8-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="d16a8-161">De uitleg van deze PowerShell-opdracht luidt als volgt: Hiermee krijgt u alle gebruikers in het huidige Microsoft 365-abonnement te zien, waarvan de locatie Brazilië is (**waarbij {$ \_ . UsageLocation-EQ "BR"}**) en geef vervolgens de naam en de locatie voor elke gebruiker weer.</span><span class="sxs-lookup"><span data-stu-id="d16a8-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="d16a8-162">**Een opmerking over grote domeinen**</span><span class="sxs-lookup"><span data-stu-id="d16a8-162">**A note about large domains**</span></span>
  
<span data-ttu-id="d16a8-163">Als u een groot domein hebt met tientallen gebruikers, kunt u een aantal voorbeelden van de voorbeelden in dit artikel weergeven als u wilt beperken.</span><span class="sxs-lookup"><span data-stu-id="d16a8-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="d16a8-164">Op basis van factoren zoals computervermogen en de beschikbare bandbreedte van het netwerk kunt u te veel tegelijk doen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="d16a8-165">Grote organisaties willen wellicht sommige van deze PowerShell-bewerkingen in twee opdrachten verdelen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="d16a8-166">Met de volgende opdracht worden bijvoorbeeld alle gebruikersaccounts weergegeven en worden voor elke gebruiker de naam en de locatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="d16a8-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="d16a8-167">Dit werkt prima voor kleinere domeinen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-167">That works great for smaller domains.</span></span> <span data-ttu-id="d16a8-168">Maar in een grote organisatie wilt u de werking mogelijk in twee opdrachten verdelen: één opdracht voor het opslaan van de informatie over de gebruikersaccounts in een variabele en een andere opdracht voor het weergeven van de benodigde informatie.</span><span class="sxs-lookup"><span data-stu-id="d16a8-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="d16a8-169">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d16a8-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="d16a8-170">De uitleg van deze reeks PowerShell-opdrachten luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="d16a8-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="d16a8-171">Alle gebruikers in het huidige Microsoft 365-abonnement krijgen en de informatie opslaan in een variabele met de naam $x (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="d16a8-172">De inhoud van de variabele *$x*weergeven, maar alleen de naam en de locatie opnemen voor elke gebruiker (**$x | Selecteer DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="d16a8-173">Microsoft 365 bevat functies die alleen kunnen worden geconfigureerd met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d16a8-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="d16a8-174">Het Microsoft 365-Beheercentrum is bedoeld om toegang te bieden tot veelvoorkomende, nuttige beheertaken die op de meeste omgevingen van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="d16a8-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="d16a8-175">Met andere woorden: het Microsoft 365-Beheercentrum is zo ontworpen dat de typische beheerder de meest voorkomende beheertaken kan uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d16a8-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="d16a8-176">Er zijn echter wel enkele taken die niet in het Beheercentrum kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d16a8-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="d16a8-177">Het Skype voor bedrijven online-Beheercentrum biedt bijvoorbeeld een paar opties voor het maken van aangepaste uitnodigingen voor vergaderingen:</span><span class="sxs-lookup"><span data-stu-id="d16a8-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Voorbeeld van de weergave van aangepaste uitnodigingen voor vergaderingen in het Skype voor bedrijven online-Beheercentrum.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="d16a8-179">Met deze instellingen kunt u een aanraakscherm voor uitnodigingen voor vergaderingen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="d16a8-180">Er zijn echter meer instellingen voor de configuratie van de vergadering, maar u kunt alleen aangepaste uitnodigingen voor vergaderingen maken.</span><span class="sxs-lookup"><span data-stu-id="d16a8-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="d16a8-181">In het volgende voorbeeld is het bijvoorbeeld mogelijk dat vergaderingen:</span><span class="sxs-lookup"><span data-stu-id="d16a8-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="d16a8-182">Anonieme gebruikers om automatisch toegang tot elke vergadering te krijgen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="d16a8-183">Deelnemers kunnen de vergadering opnemen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="d16a8-184">Alle gebruikers in uw organisatie die als presentator worden aangewezen wanneer ze deelnemen aan de vergadering.</span><span class="sxs-lookup"><span data-stu-id="d16a8-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="d16a8-185">Deze instellingen zijn niet beschikbaar in het Skype voor bedrijven online-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d16a8-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="d16a8-186">U kunt ze beheren via PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d16a8-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="d16a8-187">Dit is een opdracht waarmee u deze drie instellingen uitschakelt:</span><span class="sxs-lookup"><span data-stu-id="d16a8-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="d16a8-188">Om deze opdracht uit te voeren, moet u de [PowerShell-module voor Skype voor bedrijven online ](https://www.microsoft.com/download/details.aspx?id=39366)installeren.</span><span class="sxs-lookup"><span data-stu-id="d16a8-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="d16a8-189">De uitleg van deze PowerShell-opdracht luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="d16a8-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="d16a8-190">Via de instellingen voor nieuwe vergaderingen in Skype voor bedrijven online (**set-CsMeetingConfiguration**) kunt u instellen dat anonieme gebruikers automatische toegang hebben tot vergaderingen (**-AdmitAnonymousUsersByDefault $False**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="d16a8-191">De mogelijkheid voordeel nemers uitschakelen voor het opnemen van vergaderingen (**-AllowConferenceRecording $False**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="d16a8-192">Wijs niet alle gebruikers in uw organisatie aan als presentatoren (**-DesignateAsPresenter "geen"**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="d16a8-193">Voer de volgende opdracht uit om deze standaardinstellingen te herstellen (opties in te schakelen):</span><span class="sxs-lookup"><span data-stu-id="d16a8-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="d16a8-194">Daarnaast zijn er andere soortgelijke scenario's, wat wil zeggen dat beheerders weten dat de PowerShell voor Microsoft 365-opdrachten moet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d16a8-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="d16a8-195">PowerShell voor Microsoft 365 is ideaal voor bulkbewerkingen</span><span class="sxs-lookup"><span data-stu-id="d16a8-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="d16a8-196">Voorbeeld van een visuele interface, zoals het Microsoft 365-Beheercentrum, zijn zeer waardevol wanneer u één bewerking moet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d16a8-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="d16a8-197">Als u bijvoorbeeld één gebruikersaccount moet uitschakelen, kunt u het Beheercentrum gebruiken om snel een selectievakje te zoeken en uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="d16a8-198">Dit kan eenvoudiger zijn dan een soortgelijke bewerking uitvoeren in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d16a8-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="d16a8-199">Als u een groot aantal zaken of bepaalde items binnen een groot aantal andere zaken moet wijzigen, is het mogelijk dat het Microsoft 365-Beheercentrum niet de beste functie is.</span><span class="sxs-lookup"><span data-stu-id="d16a8-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="d16a8-200">Stel dat u het voorvoegsel van duizenden telefoonnummers moet wijzigen of dat u de specifieke gebruikers van *Myer* wilt verwijderen van al uw SharePoint Online-sites.</span><span class="sxs-lookup"><span data-stu-id="d16a8-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="d16a8-201">Hoe doet u dat in het Microsoft 365-Beheercentrum?</span><span class="sxs-lookup"><span data-stu-id="d16a8-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="d16a8-202">Stel dat u in het laatste voorbeeld meerdere honderd SharePoint Online-sites hebt en weet u niet welke Meyer lid is van de SharePoint Online-sites.</span><span class="sxs-lookup"><span data-stu-id="d16a8-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="d16a8-203">U moet eerst beginnen bij het Beheercentrum van Microsoft 365 en vervolgens deze procedure uitvoeren voor elke site:</span><span class="sxs-lookup"><span data-stu-id="d16a8-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="d16a8-204">Selecteer de **URL** van de site.</span><span class="sxs-lookup"><span data-stu-id="d16a8-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="d16a8-205">Selecteer in het vak Eigenschappen van de **siteverzameling** de koppeling naar het **adres** van de website om de site te openen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="d16a8-206">Selecteer **delen**op de site.</span><span class="sxs-lookup"><span data-stu-id="d16a8-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="d16a8-207">Selecteer in het dialoogvenster **delen** de koppeling met alle gebruikers die de juiste machtigingen hebben voor de site:</span><span class="sxs-lookup"><span data-stu-id="d16a8-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Voorbeeld van het weergeven van de leden van een SharePoint Online-site in het SharePoint Online-Beheercentrum.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="d16a8-209">Selecteer in het dialoogvenster **gedeeld met** de optie **Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="d16a8-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="d16a8-210">Blader omlaag in de lijst met gebruikers, zoek en selecteer Ken Myer (ervan uitgaand dat hij of zij machtigingen heeft voor de site), en selecteer **Gebruikersmachtigingen verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="d16a8-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="d16a8-211">Dit kan *veel* tijd in beslag nemen voor honderden sites.</span><span class="sxs-lookup"><span data-stu-id="d16a8-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="d16a8-212">U kunt ook de volgende opdracht uitvoeren in PowerShell voor Microsoft 365 om ken Myer van al uw sites te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="d16a8-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="d16a8-213">Voor deze opdracht moet u de [PowerShell-module van SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)installeren.</span><span class="sxs-lookup"><span data-stu-id="d16a8-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="d16a8-214">De uitleg van deze PowerShell-opdracht luidt als volgt: alle SharePoint-sites in het huidige Microsoft 365-abonnement (**Get-SPOSite**) krijgen en voor elke site Verwijder ken de Meyer uit de lijst met gebruikers die toegang hebben tot de PowerShell **-site $ \_ . URL-login "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="d16a8-215">Microsoft 365 vertelt Microsoft het verwijderen van Ken Meyer van elke site, met inbegrip van de personen aan wie hij of zij geen toegang hebben.</span><span class="sxs-lookup"><span data-stu-id="d16a8-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="d16a8-216">Daarom geven de resultaten fouten weer voor de sites waartoe hij geen toegang heeft.</span><span class="sxs-lookup"><span data-stu-id="d16a8-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="d16a8-217">We kunnen op deze opdracht een extra voorwaarde gebruiken om Ken Meyer alleen te verwijderen van de sites die deze persoon hebben op hun aanmeldingslijst.</span><span class="sxs-lookup"><span data-stu-id="d16a8-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="d16a8-218">Maar de fouten die worden geretourneerd, veroorzaken geen schade voor de sites zelf.</span><span class="sxs-lookup"><span data-stu-id="d16a8-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="d16a8-219">Het kan een paar minuten duren voordat de opdracht is uitgevoerd op honderden sites, in plaats van uren via het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d16a8-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="d16a8-220">Hier is nog een voorbeeld van een bulkbewerking.</span><span class="sxs-lookup"><span data-stu-id="d16a8-220">Here's another bulk operation example.</span></span> <span data-ttu-id="d16a8-221">Gebruik deze opdracht om *Bonnie Kearney*, een nieuwe SharePoint-beheerder, toe te voegen aan alle sites in de organisatie:</span><span class="sxs-lookup"><span data-stu-id="d16a8-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="d16a8-222">De uitleg van deze PowerShell-opdracht is: alle SharePoint-sites in het huidige Microsoft 365-abonnement verkrijgen en voor elke site toestaan dat Bonnie Kearney toegang is door de naam van de gebruiker toe te voegen aan de groep leden van de site (**foreach {add-partner-site $ \_ . URL-login "bkearney \@ litwareinc.com"-groep "leden"}**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="d16a8-223">PowerShell voor Microsoft 365 is geweldig bij het filteren van gegevens</span><span class="sxs-lookup"><span data-stu-id="d16a8-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="d16a8-224">Met het Microsoft 365-Beheercentrum kunt u de gegevens op verschillende manieren filteren, zodat u gemakkelijk een gerichte subset met gegevens kunt vinden.</span><span class="sxs-lookup"><span data-stu-id="d16a8-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="d16a8-225">Met Exchange kunt u bijvoorbeeld eenvoudig filteren op vrijwel elke eigenschap van een gebruikerspostvak.</span><span class="sxs-lookup"><span data-stu-id="d16a8-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="d16a8-226">Hier ziet u bijvoorbeeld de lijst met postvakken voor alle gebruikers die in de stad van Bloomington wonen:</span><span class="sxs-lookup"><span data-stu-id="d16a8-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Voorbeeld van het gebruik van Geavanceerd zoeken in het Microsoft 365-Beheercentrum voor de lijst met postvakken voor alle gebruikers die in de Bloomington van de stad wonen.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="d16a8-228">In het Exchange-Beheercentrum kunt u ook filtercriteria combineren.</span><span class="sxs-lookup"><span data-stu-id="d16a8-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="d16a8-229">U vindt bijvoorbeeld de postvakken voor alle personen die in Bloomington wonen en werken op de afdeling Financiën.</span><span class="sxs-lookup"><span data-stu-id="d16a8-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="d16a8-230">Maar er zijn beperkingen voor wat u kunt doen in het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d16a8-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="d16a8-231">U kunt bijvoorbeeld niet snel de postvakken vinden van personen die in Bloomington *of* San Diego, of naar de postvakken van alle personen die niet in Bloomington wonen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="d16a8-232">U kunt de volgende PowerShell voor Microsoft 365-opdracht gebruiken voor het weergeven van een lijst met postvakken voor alle personen die in Bloomington of San Diego wonen:</span><span class="sxs-lookup"><span data-stu-id="d16a8-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="d16a8-233">Hier ziet u een voorbeeld van de resultaten:</span><span class="sxs-lookup"><span data-stu-id="d16a8-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="d16a8-234">De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement met een postvak in de stad van San Diego of Bloomington (**waarbij {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-en ($ \_ . City-EQ "San Diego"-of $ \_ . Plaats-EQ "Bloomington")}**) en geef vervolgens de naam en plaats voor elk (**Selecteer DisplayName, plaats**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="d16a8-235">Dit is de opdracht voor het weergeven van alle postvakken voor personen die overal wonen, met uitzondering van Bloomington:</span><span class="sxs-lookup"><span data-stu-id="d16a8-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="d16a8-236">Hier ziet u een voorbeeld van de resultaten:</span><span class="sxs-lookup"><span data-stu-id="d16a8-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="d16a8-237">De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement krijgen die een postvak hebben dat zich niet in de plaats van Bloomington bevindt (**waarbij {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-en $ \_ . Plaats-ne "Bloomington"}**) en geef vervolgens de naam en plaats op voor elk.</span><span class="sxs-lookup"><span data-stu-id="d16a8-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="d16a8-238">Jokertekens gebruiken</span><span class="sxs-lookup"><span data-stu-id="d16a8-238">Use wildcards</span></span>

<span data-ttu-id="d16a8-239">U kunt ook jokertekens in uw PowerShell-filters gebruiken om een deel van een naam te vinden.</span><span class="sxs-lookup"><span data-stu-id="d16a8-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="d16a8-240">Stel dat u op zoek bent naar een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="d16a8-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="d16a8-241">U kunt ook onthouden dat de achternaam van de gebruiker *Anderson* of misschien *Henderson* of *Jorgenson*.</span><span class="sxs-lookup"><span data-stu-id="d16a8-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="d16a8-242">U kunt deze gebruiker in het Microsoft 365-Beheercentrum bijhouden met behulp van het hulpprogramma zoeken en drie verschillende zoekopdrachten uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="d16a8-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="d16a8-243">Eén voor  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="d16a8-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="d16a8-244">Eén voor  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="d16a8-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="d16a8-245">Eén voor  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="d16a8-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="d16a8-246">Aangezien alle drie deze namen eindigen op ' zoon ', kunt u aangeven dat PowerShell alle gebruikers waarvan de naam eindigt op ' zoon ' weergeven.</span><span class="sxs-lookup"><span data-stu-id="d16a8-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="d16a8-247">Dit is de opdracht:</span><span class="sxs-lookup"><span data-stu-id="d16a8-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="d16a8-248">De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers in het huidige Microsoft 365-abonnement krijgen, maar u kunt een filter alleen weergeven voor de gebruikers van wie de achternaam eindigt op ' zoon ' (**-filter ' {LastName-like ' \* zoon '} '**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="d16a8-249">De \* tekenreeks voor een willekeurige willekeurige tekenreeks, zoals de namen van de achternaam van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d16a8-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="d16a8-250">Met PowerShell voor Microsoft 365 kunt u eenvoudig gegevens afdrukken of opslaan</span><span class="sxs-lookup"><span data-stu-id="d16a8-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="d16a8-251">Met het Microsoft 365-Beheercentrum kunt u lijsten met gegevens weergeven.</span><span class="sxs-lookup"><span data-stu-id="d16a8-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="d16a8-252">Hier is een voorbeeld van het Beheercentrum van Skype voor bedrijven online met een lijst met gebruikers die zijn ingeschakeld voor Skype voor bedrijven online:</span><span class="sxs-lookup"><span data-stu-id="d16a8-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Voorbeeld van het Skype voor bedrijven online-Beheercentrum met een lijst met gebruikers die zijn ingeschakeld voor Skype voor bedrijven online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="d16a8-254">Als u deze gegevens wilt opslaan in een bestand, moet u deze in een document of Microsoft Excel-werkblad plakken.</span><span class="sxs-lookup"><span data-stu-id="d16a8-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="d16a8-255">Voor beide gevallen is extra opmaak nodig.</span><span class="sxs-lookup"><span data-stu-id="d16a8-255">Either case might require additional formatting.</span></span> <span data-ttu-id="d16a8-256">Daarnaast biedt het Microsoft 365-Beheercentrum geen manier om de weergegeven lijst rechtstreeks af te drukken.</span><span class="sxs-lookup"><span data-stu-id="d16a8-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="d16a8-257">Gelukkig kunt u PowerShell gebruiken om de lijst niet alleen weer te geven, maar om deze op te slaan in een bestand dat gemakkelijk kan worden geïmporteerd in Excel.</span><span class="sxs-lookup"><span data-stu-id="d16a8-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="d16a8-258">Hier ziet u een voorbeeld van een knop om Skype voor bedrijven online-gebruikersgegevens op te slaan in een CSV-bestand (door komma's gescheiden waarden), dat vervolgens eenvoudig kan worden geïmporteerd als een tabel in een Excel-werkblad:</span><span class="sxs-lookup"><span data-stu-id="d16a8-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="d16a8-259">Hier ziet u een voorbeeld van de resultaten:</span><span class="sxs-lookup"><span data-stu-id="d16a8-259">Here's an example of the results:</span></span>
  
![Voorbeeld van een tabel die in een Excel-werkblad is geïmporteerd voor gebruikersgegevens van Skype voor bedrijven online die zijn opgeslagen in een bestand met door komma's gescheiden waarden.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="d16a8-261">De uitleg van deze PowerShell-opdracht luidt als volgt: alle gebruikers van Skype voor bedrijven online in het huidige Microsoft 365-abonnement (**Get-CsOnlineUser**); Download alleen de gebruikersnaam, UPN en locatie (**Selecteer DisplayName, userPrincipalName, UsageLocation**). en sla deze informatie op in een CSV-bestand met de naam C: \\ logboeken \\SfBUsers.csv (**export-csv-pad "C: \\ logs \\SfBUsers.csv"-NoTypeInformation**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="d16a8-262">U kunt de lijst met opties ook opslaan als een XML-bestand of een HTML-pagina.</span><span class="sxs-lookup"><span data-stu-id="d16a8-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="d16a8-263">Met extra PowerShell-opdrachten kunt u de functie rechtstreeks opslaan als een Excel-bestand, met de gewenste aangepaste opmaak.</span><span class="sxs-lookup"><span data-stu-id="d16a8-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="d16a8-264">U kunt ook de uitvoer van een PowerShell-opdracht verzenden waarmee een lijst rechtstreeks wordt weergegeven naar de standaardprinter in Windows.</span><span class="sxs-lookup"><span data-stu-id="d16a8-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="d16a8-265">Hier ziet u een voorbeeld van een opdracht:</span><span class="sxs-lookup"><span data-stu-id="d16a8-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="d16a8-266">Het afgedrukte document ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="d16a8-266">Here's what your printed document will look like:</span></span>
  
![Voorbeeld van een afgedrukt document met de uitvoer van een PowerShell-opdracht die rechtstreeks naar de standaardprinter in Windows is verzonden.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="d16a8-268">De uitleg van deze PowerShell-opdracht luidt als volgt: alle Skype voor bedrijven online-gebruikers in het huidige abonnement van Microsoft 365. alleen de gebruikersnaam, UPN en locatie verkrijgen; en deze informatie vervolgens naar de standaardprinter van Windows (**out-printer**) verzenden.</span><span class="sxs-lookup"><span data-stu-id="d16a8-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="d16a8-269">Het afgedrukte document heeft dezelfde eenvoudige opmaak als de weergave in het PowerShell-opdrachtvenster.</span><span class="sxs-lookup"><span data-stu-id="d16a8-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="d16a8-270">Als u een harde kopie wilt toevoegen, hoeft u alleen maar iets toe te voegen \*\* Out-printer\*\* naar het einde van de opdracht.</span><span class="sxs-lookup"><span data-stu-id="d16a8-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="d16a8-271">Met PowerShell voor Microsoft 365 kunt u verschillende server producten beheren</span><span class="sxs-lookup"><span data-stu-id="d16a8-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="d16a8-272">De onderdelen die Microsoft 365 vormen, zijn ontworpen om samen te werken.</span><span class="sxs-lookup"><span data-stu-id="d16a8-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="d16a8-273">U kunt bijvoorbeeld een nieuwe gebruiker toevoegen aan Microsoft 365 en u kunt deze gegevens opgeven als de afdelings-en telefoonnummers van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d16a8-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="d16a8-274">Deze informatie is dan beschikbaar als u de gegevens van de gebruiker opent in een van de 365-services van Microsoft: Skype voor bedrijven online, Exchange of SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d16a8-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="d16a8-275">Dat is voor algemene informatie die de producten Suite beslaat.</span><span class="sxs-lookup"><span data-stu-id="d16a8-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="d16a8-276">Productspecifieke informatie, zoals informatie over het Exchange-postvak van een gebruiker, is doorgaans niet beschikbaar in de hele suite.</span><span class="sxs-lookup"><span data-stu-id="d16a8-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="d16a8-277">Zo is informatie over of het postvak van een gebruiker is ingeschakeld of niet beschikbaar is in het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d16a8-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="d16a8-278">Stel dat u een rapport wilt maken waarin de volgende informatie voor alle gebruikers wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="d16a8-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="d16a8-279">De weergavenaam van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="d16a8-279">The user's display name</span></span>
    
- <span data-ttu-id="d16a8-280">Of de gebruiker een licentie heeft voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d16a8-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="d16a8-281">Of het Exchange-postvak van de gebruiker is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="d16a8-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="d16a8-282">Of de gebruiker is ingeschakeld voor Skype voor bedrijven online</span><span class="sxs-lookup"><span data-stu-id="d16a8-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="d16a8-283">U kunt een dergelijk rapport niet gemakkelijk maken in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d16a8-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d16a8-284">In plaats daarvan moet u een apart document maken om de gegevens op te slaan, zoals een Excel-werkblad.</span><span class="sxs-lookup"><span data-stu-id="d16a8-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="d16a8-285">Ga vervolgens naar alle gebruikersnamen en licentiëringsinformatie via het Microsoft 365-Beheercentrum, ga naar postvakgegevens van het Exchange-Beheercentrum, ga naar informatie over Skype voor bedrijven online via het Skype voor bedrijven online-Beheercentrum en combineer deze informatie.</span><span class="sxs-lookup"><span data-stu-id="d16a8-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="d16a8-286">Het alternatief is een PowerShell-script gebruiken om het rapport voor u samen te stellen.</span><span class="sxs-lookup"><span data-stu-id="d16a8-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="d16a8-287">Het volgende voorbeeldscript is ingewikkelder dan de opdrachten die u tot nu toe hebt gezien in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="d16a8-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="d16a8-288">Maar het is mogelijk dat u PowerShell gebruikt om informatie weergaven te maken die moeilijk te vinden zijn.</span><span class="sxs-lookup"><span data-stu-id="d16a8-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="d16a8-289">Dit is het script voor de compilatie en de lijst weer te geven die u nodig hebt:</span><span class="sxs-lookup"><span data-stu-id="d16a8-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="d16a8-290">Hier ziet u een voorbeeld van de resultaten:</span><span class="sxs-lookup"><span data-stu-id="d16a8-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="d16a8-291">De uitleg van dit PowerShell-script luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="d16a8-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="d16a8-292">Alle gebruikers in het huidige Microsoft 365-abonnement krijgen en de gegevens opslaan in een variabele met de naam *$x* (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="d16a8-293">Een lus starten die wordt uitgevoerd op alle gebruikers in de variabele $x (**foreach ($i in $x)**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="d16a8-294">Definieer een variabele met de naam *$y* en sla de informatie over de Postvak in van de gebruiker op (**$y = Get-Mailbox-Identity $i. userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="d16a8-295">Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam *IsMailBoxEnabled*.</span><span class="sxs-lookup"><span data-stu-id="d16a8-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="d16a8-296">Stel deze in op de waarde van de eigenschap IsMailBoxEnabled van het postvak van de gebruiker (**$i | Add-Member-MemberType NoteProperty-name IsMailBoxEnabled-value $y. IsMailBoxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="d16a8-297">Definieer een variabele met de naam *$y*en sla de informatie over de Skype voor bedrijven online-gegevens van de gebruiker op (**$y = Get-CsOnlineUser-Identity $i. userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="d16a8-298">Voeg een nieuwe eigenschap toe aan de gebruikersgegevens met de naam *EnabledForSfB*.</span><span class="sxs-lookup"><span data-stu-id="d16a8-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="d16a8-299">Stel deze in op de waarde van de eigenschap ingeschakeld van de Skype voor bedrijven online-gegevens van de gebruiker (**$i | Add-Member-MemberType NoteProperty-name EnabledForSfB-value $y. enabled**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="d16a8-300">U kunt de lijst met gebruikers weergeven, maar alleen de naam ervan opnemen, ongeacht of ze een licentie hebben en de twee nieuwe eigenschappen om aan te geven of hun postvak is ingeschakeld en of ze zijn ingeschakeld voor Skype voor bedrijven online (**$x | Selecteer DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span><span class="sxs-lookup"><span data-stu-id="d16a8-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d16a8-301">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d16a8-301">See also</span></span>

[<span data-ttu-id="d16a8-302">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d16a8-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d16a8-303">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d16a8-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d16a8-304">Windows PowerShell gebruiken om rapporten te maken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d16a8-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
