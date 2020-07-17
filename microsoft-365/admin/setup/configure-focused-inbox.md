---
title: Postvak IN met prioriteit configureren voor iedereen in uw organisatie
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: 'Leer hoe u postvak IN met prioriteit configureert voor alle of specifieke gebruikers binnen uw organisatie. '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779927"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="f3e59-103">Postvak IN met prioriteit configureren voor iedereen in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="f3e59-103">Configure Focused Inbox for everyone in your organization</span></span>

  <span data-ttu-id="f3e59-104">Als u voor iedereen in uw bedrijf moet configureren hoe e-mail wordt gebruikt, is dit artikel interessant voor u.</span><span class="sxs-lookup"><span data-stu-id="f3e59-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="f3e59-105">Er wordt uitgelegd hoe u dit kunt aanpassen of kunt uitschakelen voor uw bedrijf, en u krijgt antwoord op [Veelgestelde vragen](#faq-for-focused-inbox).</span><span class="sxs-lookup"><span data-stu-id="f3e59-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>  <br/> <span data-ttu-id="f3e59-106">Zie [Postvak IN met prioriteit uitschakelen](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2) als u Postvak IN met prioriteit alleen voor uzelf wilt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="f3e59-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  
   
<span data-ttu-id="f3e59-p102">Als u er zeker van wilt zijn dat uw gebruikers bepaalde zakelijke e-mailberichten ontvangen, bijvoorbeeld van de afdeling HR of de salarisadministratie, kunt u Postvak IN met prioriteit configureren zodat deze specifieke zakelijke e-mail met prioriteit wordt weergegeven. U kunt ook bepalen of gebruikers in uw organisatie Postvak IN met prioriteit zien in hun postvak.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p102">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="f3e59-109">Postvak IN met prioriteit in- of uitschakelen in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="f3e59-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="f3e59-110">U kunt Windows PowerShell gebruiken om Postvak IN met prioriteit voor iedereen in uw organisatie in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="f3e59-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="f3e59-111">Wilt u dit doen in het Microsoft 365-beheercentrum?</span><span class="sxs-lookup"><span data-stu-id="f3e59-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="f3e59-112">Laat het weten aan ons technische team.</span><span class="sxs-lookup"><span data-stu-id="f3e59-112">Let our Engineering team know.</span></span> <span data-ttu-id="f3e59-113">**[Stem hier!](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="f3e59-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
 <span data-ttu-id="f3e59-114">**Postvak IN met prioriteit uitschakelen:**</span><span class="sxs-lookup"><span data-stu-id="f3e59-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="f3e59-p104">Het volgende PowerShell-voorbeeld schakelt Postvak IN met prioriteit **uit** in uw organisatie. De functie blijft echter wel beschikbaar voor uw gebruikers, wat betekent dat ze Postvak IN met prioriteit desgewenst weer kunnen inschakelen in een e-mailclient.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p104">The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="f3e59-118">[Maak verbinding met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="f3e59-118">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="f3e59-p105">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie voor meer informatie het item Transport rules (Transportregels) in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796) (Machtigingen voor berichtenbeleid en naleving).</span><span class="sxs-lookup"><span data-stu-id="f3e59-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>
    
3. <span data-ttu-id="f3e59-121">Voer de cmdlet **Get-OrganizationConfig** uit.</span><span class="sxs-lookup"><span data-stu-id="f3e59-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. <span data-ttu-id="f3e59-122">Zoek naar **FocusedInboxOn** en bekijk de huidige instelling:</span><span class="sxs-lookup"><span data-stu-id="f3e59-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 
    
    ![Antwoord van PowerShell op de status van het Postvak IN met prioriteit.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="f3e59-124">Voer de volgende cmdlet uit om Postvak IN met prioriteit uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="f3e59-124">Run the following cmdlet to turn Focused Inbox off.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. <span data-ttu-id="f3e59-125">Voer de cmdlet **Get-OrganizationConfig** opnieuw uit. FocusedInboxOn staat nu ingesteld op $false, wat betekent dat het is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f3e59-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 
    
 <span data-ttu-id="f3e59-126">**Postvak IN met prioriteit inschakelen:**</span><span class="sxs-lookup"><span data-stu-id="f3e59-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="f3e59-127">Voer in stap 5 hierboven de volgende cmdlet uit om Postvak IN met prioriteit in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="f3e59-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="f3e59-128">Wat zien gebruikers nadat ik Postvak IN met prioriteit inschakel? </span><span class="sxs-lookup"><span data-stu-id="f3e59-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="f3e59-p106">Gebruikers zien de weergave Prioriteit pas nadat ze Outlook opnieuw hebben gestart. Wanneer ze Outlook opnieuw hebben gestart, zien ze een Tip in de Outlook-gebruikersinterface met de optie om het nieuwe Postvak IN met prioriteit te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p106">Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![Een afbeelding van hoe Postvak IN met prioriteit eruitziet als een gebruiker de webversie van Outlook voor het eerst opent.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="f3e59-p107">Als u van de functie Onbelangrijke e-mail overstapt op Postvak IN met prioriteit, kunnen zij deze inschakelen ('Probeer het') of de functie sluiten. Als de gebruiker meerdere (ondersteunde) clients heeft, kan hij voor elke client Postvak IN met prioriteit afzonderlijk in-of uitschakelen. De tip ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="f3e59-p107">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:</span></span>
  
![Een afbeelding van hoe een Postvak IN met prioriteit eruitziet als deze is uitgerold voor uw gebruikers en Outlook opnieuw wordt geopend.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="f3e59-p108">Wanneer een gebruiker besluit Postvak IN met prioriteit te gaan gebruiken, wordt Onbelangrijke e-mail automatisch uitgeschakeld. De map Onbelangrijke e-mail wordt geconverteerd naar een standaardmap. De gebruiker kan deze map een andere naam geven of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p108">When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="f3e59-138">Postvak IN met prioriteit in- of uitschakelen voor specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="f3e59-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="f3e59-p109">In dit voorbeeld wordt Postvak IN met prioriteit **uitgeschakeld** voor Tim Matthews in de organisatie Contoso. De functie blijft echter wel beschikbaar voor hem. Als hij wil, kan hij Postvak IN met prioriteit weer inschakelen in elk van zijn clients.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p109">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="f3e59-142">[Maak verbinding met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="f3e59-142">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="f3e59-p110">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie voor meer informatie het item Transport rules (Transportregels) in het artikel Messaging policy and compliance permissions (Machtigingen voor berichtenbeleid en naleving).</span><span class="sxs-lookup"><span data-stu-id="f3e59-p110">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>
    
3. <span data-ttu-id="f3e59-145">Voer de cmdlet **Get-FocusedInbox** uit, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="f3e59-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. <span data-ttu-id="f3e59-146">Zoek naar FocusedInboxOn en bekijk de huidige instelling:</span><span class="sxs-lookup"><span data-stu-id="f3e59-146">Look for FocusedInboxOn to view its current setting:</span></span>
    
    ![Antwoord van PowerShell op de status van het Postvak IN met prioriteit.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="f3e59-148">Voer de volgende cmdlet uit om Postvak IN met prioriteit uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="f3e59-148">Run the following cmdlet to turn Focused Inbox off:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. <span data-ttu-id="f3e59-149">Of voer de volgende cmdlet uit om het in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="f3e59-149">OR, run the following cmdlet to turn it on:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="f3e59-150">De gebruikersinterface gebruiken om een transportregel te maken om e-mailberichten voor alle gebruikers met prioriteit weer te geven</span><span class="sxs-lookup"><span data-stu-id="f3e59-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="f3e59-151">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="f3e59-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="f3e59-152">Ga naar **E-mailstroom** \> **Regels**.</span><span class="sxs-lookup"><span data-stu-id="f3e59-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="f3e59-153">Selecteer ![SBV-pictogram toevoegen](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) en selecteer vervolgens **Een nieuwe regel maken...**.</span><span class="sxs-lookup"><span data-stu-id="f3e59-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 
    
3. <span data-ttu-id="f3e59-154">Wanneer u klaar bent met het maken van een nieuwe regel, klikt u op **Opslaan** om de regel toe te passen.</span><span class="sxs-lookup"><span data-stu-id="f3e59-154">After you're done creating the new rule, select **Save** to start the rule.</span></span> 
    
    <span data-ttu-id="f3e59-155">In de volgende afbeelding wordt een voorbeeld weergegeven waarbij alle berichten van 'Salarisadministratie' worden afgeleverd in Postvak IN met prioriteit.</span><span class="sxs-lookup"><span data-stu-id="f3e59-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>
    
    ![postvakinmetprioriteit salarisadministratie](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="f3e59-157">Windows PowerShell gebruiken om een transportregel te maken om e-mailberichten voor alle gebruikers met prioriteit weer te geven</span><span class="sxs-lookup"><span data-stu-id="f3e59-157">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="f3e59-158">[Maak verbinding met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="f3e59-158">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="f3e59-p112">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie voor meer informatie het item Transport rules (Transportregels) in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796) (Machtigingen voor berichtenbeleid en naleving).</span><span class="sxs-lookup"><span data-stu-id="f3e59-p112">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="f3e59-161">Voer de volgende opdracht uit om alle berichten van bijvoorbeeld 'Salarisadministratie' at te leveren in Postvak IN met prioriteit.</span><span class="sxs-lookup"><span data-stu-id="f3e59-161">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> <span data-ttu-id="f3e59-162">In dit voorbeeld zijn zowel 'X-MS-Exchange-Organization-BypassFocusedInbox' als 'true' hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="f3e59-162">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="f3e59-163">De functie Postvak IN met prioriteit ondersteunt X-header die Onbelangrijke e-mail vermijdt. Als u deze instelling gebruikt in Onbelangrijke e-mail, wordt deze ook gebruikt in Postvak IN met prioriteit.</span><span class="sxs-lookup"><span data-stu-id="f3e59-163">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="f3e59-164">Zie [Nieuwe-Transportregel](https://go.microsoft.com/fwlink/p/?LinkId=830194) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="f3e59-164">For detailed syntax and parameter information, see [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f3e59-165">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="f3e59-165">How do you know this worked?</span></span>

<span data-ttu-id="f3e59-166">U kunt de koptekst van e-mailberichten controleren om te kijken of de e-mailberichten door toepassing van een transportregel zijn bezorgd in Postvak IN met prioriteit.</span><span class="sxs-lookup"><span data-stu-id="f3e59-166">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="f3e59-167">Kies een e-mailbericht in een postvak in uw organisatie waarop een transportregel voor Postvak IN met prioriteit is toegepast.</span><span class="sxs-lookup"><span data-stu-id="f3e59-167">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="f3e59-168">Kijk of in de koptekst de tekst **X-MS-Exchange-Organization-BypassFocusedInbox: true** voorkomt.</span><span class="sxs-lookup"><span data-stu-id="f3e59-168">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="f3e59-169">De regel werkt als dit het geval is.</span><span class="sxs-lookup"><span data-stu-id="f3e59-169">This means the bypass is working.</span></span> <span data-ttu-id="f3e59-170">Zie het artikel[Koptekstgegevens weergeven voor een e-mailbericht](https://go.microsoft.com/fwlink/p/?LinkId=822530) voor instructies voor het vinden van de koptekstgegevens van een bericht.</span><span class="sxs-lookup"><span data-stu-id="f3e59-170">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span> 
 
## <a name="turn-onoff-clutter"></a><span data-ttu-id="f3e59-171">Onbelangrijke e-mail in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="f3e59-171">Turn on/off Clutter</span></span>
 
<span data-ttu-id="f3e59-p115">We hebben meldingen ontvangen dat de functie Onbelangrijke e-mail voor sommige gebruikers plotseling niet meer werkt. Als dit gebeurt, kunt u deze functie weer inschakelen voor specifieke gebruikers. Zie [Onbelangrijke e-mail configureren voor uw organisatie](../email/configure-clutter.md).</span><span class="sxs-lookup"><span data-stu-id="f3e59-p115">We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>
 
## <a name="faq-for-focused-inbox"></a><span data-ttu-id="f3e59-175">Veelgestelde vragen over Postvak IN met prioriteit</span><span class="sxs-lookup"><span data-stu-id="f3e59-175">FAQ for Focused Inbox</span></span>

<span data-ttu-id="f3e59-176">Hier vindt u antwoorden op Veelgestelde vragen over Postvak IN met prioriteit.</span><span class="sxs-lookup"><span data-stu-id="f3e59-176">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span> 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="f3e59-177">Kan ik bepalen op welke manier ik de functie Postvak IN met prioriteit implementeer in mijn organisatie?</span><span class="sxs-lookup"><span data-stu-id="f3e59-177">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="f3e59-p116">Ja. U kunt Postvak IN met prioriteit in- of uitschakelen voor de hele organisatie, of voor bepaalde gebruikers. Zie het bovenstaande.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p116">Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="f3e59-181">Is de functie Postvak IN met prioriteit alleen beschikbaar voor clients met Office 2016?</span><span class="sxs-lookup"><span data-stu-id="f3e59-181">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="f3e59-182">Ja, dit geldt alleen voor gebruikers met Office 2016.</span><span class="sxs-lookup"><span data-stu-id="f3e59-182">Yes, only users with Office 2016 are affected.</span></span> <span data-ttu-id="f3e59-183">De functie wordt niet ondersteund voor Outlook 2013 of eerder.</span><span class="sxs-lookup"><span data-stu-id="f3e59-183">The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="f3e59-184">Hoe lang het duurt voordat de gewijzigde instelling van Postvak IN met prioriteit wordt doorgevoerd in Outlook?</span><span class="sxs-lookup"><span data-stu-id="f3e59-184">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="f3e59-185">Nadat u Postvak IN met prioriteit hebt in- of uitgeschakeld, wordt de nieuwe instelling van kracht op het moment dat uw gebruikers hun exemplaar van Outlook sluiten en opnieuw starten.</span><span class="sxs-lookup"><span data-stu-id="f3e59-185">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="f3e59-186">Wat gebeurt er met de functie Onbelangrijke e-mail als ik Postvak IN met prioriteit inschakel?</span><span class="sxs-lookup"><span data-stu-id="f3e59-186">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="f3e59-p118">Nadat u bent overgestapt, ontvangt u de e-mails waarvoor niet direct actie hoeft te worden ondernomen niet meer in de map Onbelangrijke e-mail. In plaats daarvan worden de e-mails geplaatst in de tabbladen Prioriteit of Overige in het postvak. Het algoritme dat items naar de map Onbelangrijke e-mail verplaatste, werkt nu voor Postvak IN met prioriteit, dus alle e-mails die in Onbelangrijke e-mail werden geplaatst, gaan nu naar Overige. Alle berichten die al in de map Onbelangrijke e-mail zitten, blijven daar totdat u besluit ze te verwijderen of te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p118">After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="f3e59-191">Lees dit bericht van [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span><span class="sxs-lookup"><span data-stu-id="f3e59-191">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="f3e59-192">Kan ik Onbelangrijke e-mail ingeschakeld laten voor gebruikers?</span><span class="sxs-lookup"><span data-stu-id="f3e59-192">Can I keep users on Clutter?</span></span> <span data-ttu-id="f3e59-193">Wat adviseert Microsoft als het gaat om de keuze tussen Onbelangrijke e-mail en Postvak IN met prioriteit?</span><span class="sxs-lookup"><span data-stu-id="f3e59-193">What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="f3e59-p120">Ja, u kunt de functie Onbelangrijke e-mail ingeschakeld laten en Postvak IN met prioriteit uitschakelen. Aangezien de functie Onbelangrijke e-mail uiteindelijk echter volledig wordt vervangen door Postvak IN met prioriteit, adviseren wij om nu over te stappen op Postvak IN met prioriteit. Raadpleeg het volgende blogbericht voor meer informatie over wanneer u Onbelangrijke e-mail in Exchange Online gebruikt: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448) (Update over Postvak IN met prioriteit en onze plannen voor Onbelangrijke e-mail).</span><span class="sxs-lookup"><span data-stu-id="f3e59-p120">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="f3e59-196">Moet ik Onbelangrijke e-mail uitschakelen voor mijn eindgebruikers als we iedereen gaan overzetten naar Postvak IN met prioriteit?</span><span class="sxs-lookup"><span data-stu-id="f3e59-196">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="f3e59-p121">Nee. U kunt de cmdlet Set-Clutter gebruiken om de functie Onbelangrijke e-mail expliciet uit te schakelen voor een postvak. Het is dan wel zo dat berichten die eerder werden omgeleid naar de map Onbelangrijke e-mail, in het Postvak IN blijven staan en dat de eigenaar deze berichten handmatig moet verwerken totdat de client is geüpgraded naar een versie die ondersteuning biedt voor Postvak IN met prioriteit. Het is daarom beter om de functie Onbelangrijke e-mail pas uit te schakelen wanneer de geüpgrade clients beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p121">No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="f3e59-201">Waarom zijn er twee verschillende cmdlets voor het beheren van Postvak IN met prioriteit?</span><span class="sxs-lookup"><span data-stu-id="f3e59-201">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="f3e59-202">Postvak IN met prioriteit kan op twee niveaus worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="f3e59-202">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="f3e59-203">**Organisatieniveau**: status van Postvak IN met prioriteit en een bijbehorend tijdstempel van het laatste tijdstip van bijwerken.</span><span class="sxs-lookup"><span data-stu-id="f3e59-203">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span> 
    
- <span data-ttu-id="f3e59-204">**Postvakniveau**: status van Postvak IN met prioriteit en een bijbehorend tijdstempel van het laatste tijdstip van bijwerken</span><span class="sxs-lookup"><span data-stu-id="f3e59-204">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="f3e59-205">Hoe wordt er door Outlook aan de hand van deze twee statuswaarden bepaald of de functie Postvak IN met prioriteit wordt gebruikt?</span><span class="sxs-lookup"><span data-stu-id="f3e59-205">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="f3e59-p122">Dit wordt bepaald aan de hand van de cmdlet met de meest recente tijdstempel. Standaard zijn beide tijdstempels 'null' en in dit geval wordt de functie ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p122">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="f3e59-208">Waarom retourneert de cmdlet Get-FocusedInbox 'true' als ik Postvak IN met prioriteit heb uitgeschakeld in mijn organisatie?</span><span class="sxs-lookup"><span data-stu-id="f3e59-208">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="f3e59-p123">Er zijn twee cmdlets voor het beheren van Postvak IN met prioriteit. Wanneer u Get-FocusedInbox uitvoert voor een postvak, wordt de status van de functie op het niveau van het postvak geretourneerd. De weergave in Outlook wordt gekozen op basis van de cmdlet waarvan de status het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p123">There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="f3e59-212">Kan ik een script uitvoeren om te zien wie Postvak IN met prioriteit heeft ingeschakeld?</span><span class="sxs-lookup"><span data-stu-id="f3e59-212">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="f3e59-p124">Nee, en dat is standaard. Postvak IN met prioriteit kan alleen aan de clientzijde worden ingeschakeld, dus via de cmdlet weet u alleen of het postvak van de gebruiker in aanmerking komt voor deze functie. Het is mogelijk de functie gelijktijdig in sommige clients in te schakelen en in andere uit te schakelen, bijvoorbeeld ingeschakeld in Outlook-app en Outlook Mobile, maar uitgeschakeld in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="f3e59-p124">No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>
