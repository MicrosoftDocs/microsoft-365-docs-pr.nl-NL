---
title: Bestanden in teams beveiligen met bewaarlabels en DLP
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Samenvatting: bewaarlabel- en DLP-beleid (Data Loss Prevention) toepassen op bestanden in teams met verschillende niveaus van informatiebescherming.'
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806648"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="c5bbf-103">Bestanden in teams beveiligen met bewaarlabels en DLP</span><span class="sxs-lookup"><span data-stu-id="c5bbf-103">Protect files in teams with retention labels and DLP</span></span>

 
<span data-ttu-id="c5bbf-104">Gebruik de stappen in dit artikel om bewaarlabels en DLP-beleid te ontwerpen en te implementeren voor baseline, gevoelige en zeer vertrouwelijke teams en hun onderliggende SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-104">Use the steps in this article to design and deploy retention labels and data loss prevention (DLP) policies for baseline, sensitive, and highly confidential teams and their underlying SharePoint sites.</span></span> <span data-ttu-id="c5bbf-105">Zie [Bestanden beveiligen in Microsoft Teams](secure-files-in-teams.md) voor meer informatie over deze drie beveiligingslagen.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="c5bbf-106">Hoe dit werkt</span><span class="sxs-lookup"><span data-stu-id="c5bbf-106">How this works</span></span>

1. <span data-ttu-id="c5bbf-107">Maak de gewenste bewaarlabels en publiceer deze.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="c5bbf-108">Het kan maximaal 12 uur duren voordat deze worden gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="c5bbf-109">Voor de gewenste onderliggende SharePoint-sites bewerkt u de instellingen van de documentbibliotheek om de gewenste bewaarlabels toe te passen op items in de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-109">For the desired underlying SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="c5bbf-110">Maak DLP-beleid om actie te ondernemen op basis van bewaarlabels.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="c5bbf-111">Wanneer gebruikers een document toevoegen aan de onderliggende SharePoint-sitebibliotheek voor het team, ontvangt het document standaard het toegewezen bewaarlabel.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-111">When users add a document to the underlying SharePoint site library for the team, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="c5bbf-112">Gebruikers kunnen zo nodig het label wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-112">Users can change the label, if needed.</span></span> <span data-ttu-id="c5bbf-113">Wanneer een gebruiker een document buiten de organisatie deelt, wordt met DLP gecontroleerd of een label is toegewezen en wordt actie ondernomen als een DLP-beleid overeenkomt met het label.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="c5bbf-114">DLP zal ook zoeken naar andere beleidsovereenkomsten, zoals het beschermen van bestanden met creditcardnummers als dit type beleid is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="c5bbf-115">Bewaarlabels voor uw onderliggende SharePoint-sites</span><span class="sxs-lookup"><span data-stu-id="c5bbf-115">Retention labels for your underlying SharePoint sites</span></span>

<span data-ttu-id="c5bbf-116">Er zijn drie fasen voor het maken en vervolgens toewijzen van bewaarlabels aan onderliggende SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-116">There are three phases to creating and then assigning retention labels to underlying SharePoint sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="c5bbf-117">Stap 1: de namen van de bewaarlabels bepalen</span><span class="sxs-lookup"><span data-stu-id="c5bbf-117">Step 1: Determine the retention label names</span></span>

<span data-ttu-id="c5bbf-118">In deze fase bepaalt u de namen van de bewaarlabels voor de vier niveaus van informatiebescherming die zijn toegepast op onderliggende SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to underlying SharePoint sites.</span></span> <span data-ttu-id="c5bbf-119">In de volgende tabel vindt u een overzicht van de aanbevolen namen voor elk niveau.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="c5bbf-120">**niveau van bescherming onderliggende SharePoint-sites**</span><span class="sxs-lookup"><span data-stu-id="c5bbf-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="c5bbf-121">**Labelnaam**</span><span class="sxs-lookup"><span data-stu-id="c5bbf-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c5bbf-122">Basislijn-openbaar</span><span class="sxs-lookup"><span data-stu-id="c5bbf-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="c5bbf-123">Intern openbaar</span><span class="sxs-lookup"><span data-stu-id="c5bbf-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="c5bbf-124">Basislijn-persoonlijk</span><span class="sxs-lookup"><span data-stu-id="c5bbf-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="c5bbf-125">Privé</span><span class="sxs-lookup"><span data-stu-id="c5bbf-125">Private</span></span>  <br/> |
|<span data-ttu-id="c5bbf-126">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="c5bbf-126">Sensitive</span></span>  <br/> |<span data-ttu-id="c5bbf-127">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="c5bbf-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="c5bbf-128">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="c5bbf-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="c5bbf-129">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="c5bbf-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="c5bbf-130">Stap 2: de bewaarlabels maken</span><span class="sxs-lookup"><span data-stu-id="c5bbf-130">Step 2: Create the retention labels</span></span>

<span data-ttu-id="c5bbf-131">In deze fase maakt en publiceert u uw vastgestelde labels voor de verschillende niveaus van informatiebescherming.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="c5bbf-132">Meld u aan bij de [Microsoft 365-compliancecentrum](https://compliance.microsoft.com) met een account met de rol van Beveiligingsbeheerder of Bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="c5bbf-133">Klik op het tabblad **Start: Microsoft 365-compliancecentrum** van uw browser op **Classificaties > Labels**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="c5bbf-134">Klik op **Bewaarlabels > Een label maken**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="c5bbf-135">Typ in het deelvenster **Naam van uw label** de naam van het label en een beschrijving voor beheerders en gebruikers en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="c5bbf-136">Vul het deelvenster **Beschrijvende elementen van het bestandsplan** in zoals gewenst en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c5bbf-137">Indien nodig kunt u in het deelvenster **Labelinstellingen** de **Retentie** instellen op **Aan** en de bewaarinstellingen configureren.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="c5bbf-138">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="c5bbf-139">Klik in het deelvenster **Uw instellingen controleren** op **Label maken**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="c5bbf-140">Voor extra labels klikt u op **een label maken** en herhaalt u de stappen 3-7 in deze procedure.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 in this procedure as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="c5bbf-141">De nieuwe etiketten publiceren</span><span class="sxs-lookup"><span data-stu-id="c5bbf-141">Publish your new labels</span></span>

<span data-ttu-id="c5bbf-142">Vervolgens gebruikt u deze stappen om de nieuwe bewaarlabels te publiceren.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="c5bbf-143">Klik in het deelvenster **labels** op het tabblad **bewaarlabels** en klik vervolgens op **labels publiceren**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="c5bbf-144">Klik in het deelvenster **Labels kiezen om te publiceren** op de optie **Labels kiezen om te publiceren**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="c5bbf-145">Klik op het deelvenster **Labels kiezen** op **Toevoegen**, selecteer alle vier de labels en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="c5bbf-146">Klik op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="c5bbf-147">Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="c5bbf-148">Klik in het deelvenster **Locaties kiezen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="c5bbf-149">Typ in het deelvenster **uw beleid een naam geven** een naam voor uw set labels in **naam** en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="c5bbf-150">Klik in het deelvenster **Uw instellingen controleren** op **Labels publiceren** en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="c5bbf-151">Stap 3: de bewaarlabels toepassen op uw onderliggende SharePoint-sites</span><span class="sxs-lookup"><span data-stu-id="c5bbf-151">Step 3: Apply the retention labels to your underlying SharePoint sites</span></span>

<span data-ttu-id="c5bbf-152">Gebruik de volgende stappen om de bewaarlabels toe te passen op de mappen documenten van uw onderliggende SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-152">Use these steps to apply the retention labels to the documents folders of your underlying SharePoint sites.</span></span>
  
1.  <span data-ttu-id="c5bbf-153">Klik in het team op **bestanden**en klik vervolgens op **openen in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="c5bbf-154">Klik op het nieuwe SharePoint-tabblad van uw browser op **documenten**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="c5bbf-155">Klik op het pictogram Instellingen en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="c5bbf-156">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="c5bbf-157">Selecteer in **Instellingen-Label toepassen** het juiste bewaarlabel en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="c5bbf-158">Sluit het tabblad voor de SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-158">Close the tab for the SharePoint site.</span></span>
    
7. <span data-ttu-id="c5bbf-159">Herhaal stap 1-6 om bewaarlabels toe te wijzen aan uw extra onderliggende SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-159">Repeat steps 1-6 to assign retention labels to your additional underlying SharePoint sites.</span></span>
    
<span data-ttu-id="c5bbf-160">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-160">Here is your resulting configuration.</span></span>
  
![Bewaarlabels voor de vier typen onderliggende SharePoint-sites.](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="c5bbf-162">DLP-beleid voor uw onderliggende SharePoint-sites</span><span class="sxs-lookup"><span data-stu-id="c5bbf-162">DLP policies for your underlying SharePoint sites</span></span>

<span data-ttu-id="c5bbf-163">Volg deze stappen om een DLP-beleid te configureren waarmee gebruikers op de hoogte worden gesteld wanneer ze een document delen op een onderliggende SharePoint-site buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-163">Use these steps to configure a DLP policy that notifies users when they share a document on an underlying SharePoint site outside the organization.</span></span>

1. <span data-ttu-id="c5bbf-164">Meld u aan bij de [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/) met een account met de rol van Beveiligingsbeheerder of Bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="c5bbf-165">Klik op het nieuwe tabblad **Microsoft 365-compliance** in uw browser op **Beleid > Preventie van gegevensverlies**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="c5bbf-166">Klik in het deelvenster **Start > Preventie van gegevensverlies** op **Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="c5bbf-167">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="c5bbf-168">Typ in het deelvenster **Naam van uw beleid** de naam voor het DLP-beleid op gevoelig niveau in **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c5bbf-169">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="c5bbf-170">Schakel in de lijst met locaties de locaties **Exchange-e-mail**, **OneDrive-accounts** en **chat- en kanaalberichten in Teams** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="c5bbf-171">Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="c5bbf-172">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Retentielabels**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="c5bbf-173">Klik in het deelvenster **Retentielabels** op **Toevoegen**, selecteer het label **Gevoelig**, klik op **Toevoegen**en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="c5bbf-174">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="c5bbf-175">Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="c5bbf-176">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="c5bbf-177">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="c5bbf-178">Typ of plak in het tekstvak een van de volgende tips:</span><span class="sxs-lookup"><span data-stu-id="c5bbf-178">In the text box, type or paste in one of the following tips:</span></span>
    
  - <span data-ttu-id="c5bbf-179">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-179">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="c5bbf-180">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-180">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="c5bbf-181">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-181">Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="c5bbf-182">Zeer vertrouwelijke bestanden worden beveiligd met versleuteling.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-182">Highly confidential files are protected with encryption.</span></span> <span data-ttu-id="c5bbf-183">Alleen externe gebruikers die toegang hebben tot deze bestanden door de IT-afdeling, kunnen ze lezen.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-183">Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="c5bbf-184">U kunt ook uw eigen beleidstip typen of plakken waarmee gebruikers worden geïnstrueerd hoe ze een bestand kunnen delen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="c5bbf-185">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="c5bbf-186">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="c5bbf-187">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="c5bbf-188">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="c5bbf-189">Hier vindt u de configuratie voor gevoelige teams.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-189">Here is your resulting configuration for sensitive teams.</span></span>
  
![DLP-beleid voor gevoelig team dat het gevoelige bewaarlabel gebruikt](../../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="c5bbf-191">Gebruik vervolgens deze stappen om een DLP-beleid te configureren dat gebruikers blokkeert wanneer ze een document delen op een onderliggende SharePoint-site buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on an underlying SharePoint site outside the organization.</span></span>
  
1. <span data-ttu-id="c5bbf-192">Klik op het nieuwe tabblad **Microsoft 365-compliance** in uw browser op **Beleid > Preventie van gegevensverlies**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="c5bbf-193">Klik in het deelvenster **Preventie van gegevensverlies** op **Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="c5bbf-194">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="c5bbf-195">Typ in het deelvenster **Naam van uw beleid** de naam voor het DLP-beleid op zeer gevoelig niveau in **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="c5bbf-196">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c5bbf-197">Schakel in de lijst met locaties de locaties **Exchange-e-mail**, **OneDrive-accounts** en **chat- en kanaalberichten in Teams** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="c5bbf-198">Klik in het deelvenster **Het type gevoelige inhoud aanpassen dat u wilt beveiligen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="c5bbf-199">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Bewaarlabels**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="c5bbf-200">Klik in het deelvenster **Retentielabels** op **Toevoegen**, selecteer het label **Zeer Vertrouwelijk**, klik op **Toevoegen**en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="c5bbf-201">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="c5bbf-202">Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="c5bbf-203">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="c5bbf-204">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="c5bbf-205">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="c5bbf-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="c5bbf-206">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-206">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="c5bbf-207">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-207">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="c5bbf-208">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-208">Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="c5bbf-209">U kunt ook uw eigen beleidstip typen of plakken waarmee gebruikers worden geïnstrueerd hoe ze een bestand kunnen delen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="c5bbf-210">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="c5bbf-211">In het deelvenster **Wat wilt u doen als we gevoelige informatie detecteren?**, onder **Detecteren wanneer een bepaalde hoeveelheid gevoelige informatie in een keer wordt gedeeld**, klikt u op **Toegang beperken of de inhoud versleutelen** en klikt u vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="c5bbf-212">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="c5bbf-213">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="c5bbf-214">Hier vindt u de configuratie voor een team met een hoge vertrouwelijkheid.</span><span class="sxs-lookup"><span data-stu-id="c5bbf-214">Here is your resulting configuration for high confidentiality team.</span></span>
  
![DLP-beleid voor een team met een hoge vertrouwelijkheid met het label Zeer vertrouwelijke inhoud](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="c5bbf-216">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c5bbf-216">Next step</span></span>

[<span data-ttu-id="c5bbf-217">Bestanden in teams beveiligen met gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="c5bbf-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="c5bbf-218">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c5bbf-218">See Also</span></span>

[<span data-ttu-id="c5bbf-219">Bestanden beveiligen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c5bbf-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
<span data-ttu-id="c5bbf-220">[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)</span><span class="sxs-lookup"><span data-stu-id="c5bbf-220">[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)</span></span>


