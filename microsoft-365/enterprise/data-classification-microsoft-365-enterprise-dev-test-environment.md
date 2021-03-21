---
title: Gegevensclassificatie voor uw Microsoft 365 voor ondernemingstestomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Gebruik deze testlaboratoriumhandleiding om bewaarlabels voor documenten te maken en te gebruiken in uw Microsoft 365 voor ondernemingstestomgeving.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919186"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2027a-103">Gegevensclassificatie voor uw Microsoft 365 voor ondernemingstestomgeving</span><span class="sxs-lookup"><span data-stu-id="2027a-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2027a-104">*Deze testlaborator kan worden gebruikt voor testomgevingen van Microsoft 365 voor bedrijven en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2027a-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2027a-105">In dit artikel wordt beschreven hoe u gegevensclassificatie configureert met bewaarlabels in uw Microsoft 365 voor ondernemingstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="2027a-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="2027a-106">Het classificeren van gegevens in uw testomgeving bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="2027a-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="2027a-107">Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen</span><span class="sxs-lookup"><span data-stu-id="2027a-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="2027a-108">Fase 2: Bewaarlabels maken</span><span class="sxs-lookup"><span data-stu-id="2027a-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="2027a-109">Fase 3: Bewaarlabels toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="2027a-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="2027a-111">Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.</span><span class="sxs-lookup"><span data-stu-id="2027a-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2027a-112">Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen</span><span class="sxs-lookup"><span data-stu-id="2027a-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2027a-113">Als u alleen de bewaarlabels op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="2027a-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2027a-114">Als u bewaarlabels wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="2027a-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2027a-115">Voor het testen van bewaarlabels is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="2027a-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="2027a-116">Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="2027a-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="2027a-117">Fase 2: Bewaarlabels maken</span><span class="sxs-lookup"><span data-stu-id="2027a-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="2027a-118">Maak in deze fase de bewaarlabels voor de verschillende bewaarniveaus voor SharePoint Online-documentenmappen:</span><span class="sxs-lookup"><span data-stu-id="2027a-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="2027a-119">Meld u aan bij [het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/homepage) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="2027a-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="2027a-120">Selecteer classificatiebewaringslabels op het **tabblad Start - Microsoft 365-beveiliging** van   >  **uw** browser.</span><span class="sxs-lookup"><span data-stu-id="2027a-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="2027a-121">Selecteer **Een label maken.**</span><span class="sxs-lookup"><span data-stu-id="2027a-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="2027a-122">Voer in **het deelvenster** Naam uw label interne **openbare** naam in naam van uw **label** in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2027a-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="2027a-123">Selecteer volgende in het deelvenster  **Bestandsplandescriptors.**</span><span class="sxs-lookup"><span data-stu-id="2027a-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="2027a-124">Stel in **het deelvenster** Labelinstellingen indien nodig **bewaaring** in op **Aan** en selecteer **vervolgens Volgende**.</span><span class="sxs-lookup"><span data-stu-id="2027a-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="2027a-125">Selecteer in **het deelvenster Uw instellingen** controleren de optie Het label **maken.**</span><span class="sxs-lookup"><span data-stu-id="2027a-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="2027a-126">Herhaal stap 3-7 voor extra labels met deze namen:</span><span class="sxs-lookup"><span data-stu-id="2027a-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="2027a-127">Privé</span><span class="sxs-lookup"><span data-stu-id="2027a-127">Private</span></span>
  - <span data-ttu-id="2027a-128">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="2027a-128">Sensitive</span></span>
  - <span data-ttu-id="2027a-129">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="2027a-129">Highly Confidential</span></span>
1. <span data-ttu-id="2027a-130">Selecteer in **het deelvenster Bewaarlabels** de optie **Labels publiceren.**</span><span class="sxs-lookup"><span data-stu-id="2027a-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="2027a-131">Selecteer labels **kiezen om te** publiceren in het deelvenster Labels kiezen om te **publiceren.**</span><span class="sxs-lookup"><span data-stu-id="2027a-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="2027a-132">Selecteer in **het deelvenster Labels** kiezen de optie **Toevoegen** en selecteer alle vier labels.</span><span class="sxs-lookup"><span data-stu-id="2027a-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="2027a-133">Selecteer **Toevoegen** en selecteer vervolgens **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="2027a-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="2027a-134">Selecteer volgende **in het deelvenster Labels kiezen** om te **publiceren.**</span><span class="sxs-lookup"><span data-stu-id="2027a-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="2027a-135">Selecteer volgende **in het** deelvenster Locaties **kiezen.**</span><span class="sxs-lookup"><span data-stu-id="2027a-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="2027a-136">Voer in **het deelvenster Naam uw beleid** de optie **Voorbeeldorganisatie** in **Naam** in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2027a-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="2027a-137">Selecteer in **het deelvenster** Uw instellingen controleren de optie **Labels publiceren.**</span><span class="sxs-lookup"><span data-stu-id="2027a-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="2027a-138">Het kan enkele minuten duren voordat de bewaarlabels zijn gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="2027a-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="2027a-139">Fase 3: Bewaarlabels toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="2027a-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="2027a-140">In deze fase ontdekt u het standaardgedrag van bewaarlabels voor bestanden in de map Documenten van een SharePoint Online-site en wijzigt u handmatig het bewaarlabel van een document.</span><span class="sxs-lookup"><span data-stu-id="2027a-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="2027a-141">Maak eerst een SharePoint Online-teamsite op gevoelig niveau:</span><span class="sxs-lookup"><span data-stu-id="2027a-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="2027a-142">Meld u met een privé-exemplaar van uw browser aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="2027a-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="2027a-143">Selecteer SharePoint in de lijst met **tegels.**</span><span class="sxs-lookup"><span data-stu-id="2027a-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="2027a-144">Selecteer site maken op het **nieuwe tabblad SharePoint** in **uw browser.**</span><span class="sxs-lookup"><span data-stu-id="2027a-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="2027a-145">Selecteer teamsite **op de pagina** Een **site maken.**</span><span class="sxs-lookup"><span data-stu-id="2027a-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="2027a-146">Voer in **het vak Teamsitenaam** **SensitiveFiles in.**</span><span class="sxs-lookup"><span data-stu-id="2027a-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="2027a-147">Voer in **het vak Teamsitebeschrijving** **SharePoint-site voor gevoelige bestanden in.**</span><span class="sxs-lookup"><span data-stu-id="2027a-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="2027a-148">Selecteer **in Privacy-instellingen** de optie **Privé- alleen leden** hebben toegang tot deze site en selecteren vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="2027a-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="2027a-149">Selecteer voltooien in het deelvenster Wie wilt **u toevoegen?** **.**</span><span class="sxs-lookup"><span data-stu-id="2027a-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="2027a-150">Configureer vervolgens de map Documenten van de teamsite SensitiveFiles voor het label Gevoelige bewaring.</span><span class="sxs-lookup"><span data-stu-id="2027a-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="2027a-151">Selecteer documenten **op het tabblad SensitiveFiles** van **uw** browser.</span><span class="sxs-lookup"><span data-stu-id="2027a-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="2027a-152">Selecteer het **pictogram** Instellingen en selecteer vervolgens **Bibliotheekinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="2027a-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="2027a-153">Selecteer **onder Machtigingen en beheer** de optie Label toepassen op items in deze lijst of **bibliotheek.**</span><span class="sxs-lookup"><span data-stu-id="2027a-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="2027a-154">Als deze optie niet wordt weergegeven, zijn uw bewaarlabels nog niet gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="2027a-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="2027a-155">Probeer deze stap op een later tijdstip.</span><span class="sxs-lookup"><span data-stu-id="2027a-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="2027a-156">Selecteer **in Instellingen-label** toepassen de optie **Gevoelig** in de vervolgkeuzekeuzemenu en selecteer **vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="2027a-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="2027a-157">Maak vervolgens een nieuw document op de site SensitiveFiles en wijzig het bewaarlabel.</span><span class="sxs-lookup"><span data-stu-id="2027a-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="2027a-158">Selecteer nieuw   >  **Word-document** in de map documenten.</span><span class="sxs-lookup"><span data-stu-id="2027a-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="2027a-159">Voer tekst in het lege document in.</span><span class="sxs-lookup"><span data-stu-id="2027a-159">Enter some text in the blank document.</span></span> <span data-ttu-id="2027a-160">Wacht totdat de tekst is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2027a-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="2027a-161">Selecteer gedeelde documenten op de **menubalk.**</span><span class="sxs-lookup"><span data-stu-id="2027a-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="2027a-162">Selecteer naast **Document.docx** bestandsnaam het verticale beletselteken en selecteer **vervolgens Details**.</span><span class="sxs-lookup"><span data-stu-id="2027a-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="2027a-163">In het rechterdeelvenster, in de sectie Eigenschappen, onder **Bewaarlabel** toepassen, wordt het label Gevoelige bewaring automatisch toegepast op het document.  </span><span class="sxs-lookup"><span data-stu-id="2027a-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="2027a-164">Klik **op Alles bewerken.**</span><span class="sxs-lookup"><span data-stu-id="2027a-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="2027a-165">Selecteer in **Document.docx** deelvenster Onder **Bewaarlabel toepassen** het label Zeer **vertrouwelijk** en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="2027a-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="2027a-166">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="2027a-166">Next step</span></span>

<span data-ttu-id="2027a-167">Ontdek extra [functies en](m365-enterprise-test-lab-guides.md#information-protection) mogelijkheden voor informatiebeveiliging in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="2027a-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2027a-168">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2027a-168">See also</span></span>

[<span data-ttu-id="2027a-169">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="2027a-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2027a-170">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="2027a-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2027a-171">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="2027a-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)