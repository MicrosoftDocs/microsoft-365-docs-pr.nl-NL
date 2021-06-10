---
title: Gegevensclassificatie voor uw Microsoft 365 voor bedrijfstestomgeving
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
description: Gebruik deze Test Lab Guide om bewaarlabels te maken en te gebruiken op documenten in uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919186"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a08d2-103">Gegevensclassificatie voor uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="a08d2-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a08d2-104">*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="a08d2-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a08d2-105">In dit artikel wordt beschreven hoe u gegevensclassificatie configureert met behulp van bewaarlabels in uw Microsoft 365 voor bedrijfstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="a08d2-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="a08d2-106">Het classificeren van gegevens in uw testomgeving bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="a08d2-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="a08d2-107">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="a08d2-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="a08d2-108">Fase 2: Bewaarlabels maken</span><span class="sxs-lookup"><span data-stu-id="a08d2-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="a08d2-109">Fase 3: Bewaarlabels toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="a08d2-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a08d2-111">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="a08d2-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a08d2-112">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="a08d2-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a08d2-113">Als u alleen de bewaarlabels op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="a08d2-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a08d2-114">Als u bewaarlabels wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a08d2-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a08d2-115">Voor het testen van bewaarlabels is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="a08d2-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a08d2-116">Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="a08d2-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="a08d2-117">Fase 2: Bewaarlabels maken</span><span class="sxs-lookup"><span data-stu-id="a08d2-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="a08d2-118">Maak in deze fase de bewaarlabels voor de verschillende bewaarniveaus voor SharePoint onlinedocumentenmappen:</span><span class="sxs-lookup"><span data-stu-id="a08d2-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="a08d2-119">Meld u aan bij [het Microsoft 365 beveiligingscentrum](https://security.microsoft.com/homepage) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="a08d2-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="a08d2-120">Selecteer op **het tabblad Start Microsoft 365 beveiligingstabblad** van uw browser de optie **Classificatiebewaringslabels.**  >  </span><span class="sxs-lookup"><span data-stu-id="a08d2-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="a08d2-121">Selecteer **Een label maken.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="a08d2-122">Voer in **het deelvenster** Naam uw label interne **openbare** naam in naam van uw **label** in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="a08d2-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="a08d2-123">Selecteer volgende in het deelvenster  **Bestandsplandescriptors.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="a08d2-124">Stel in **het deelvenster** Labelinstellingen indien nodig **bewaaring** in op **Aan** en selecteer **vervolgens Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a08d2-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="a08d2-125">Selecteer in **het deelvenster Uw instellingen** controleren de optie Het label **maken.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="a08d2-126">Herhaal stap 3-7 voor extra labels met deze namen:</span><span class="sxs-lookup"><span data-stu-id="a08d2-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="a08d2-127">Privé</span><span class="sxs-lookup"><span data-stu-id="a08d2-127">Private</span></span>
  - <span data-ttu-id="a08d2-128">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="a08d2-128">Sensitive</span></span>
  - <span data-ttu-id="a08d2-129">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="a08d2-129">Highly Confidential</span></span>
1. <span data-ttu-id="a08d2-130">Selecteer in **het deelvenster Bewaarlabels** de optie **Labels publiceren.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="a08d2-131">Selecteer labels **kiezen om te** publiceren in het deelvenster Labels kiezen om te **publiceren.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="a08d2-132">Selecteer in **het deelvenster Labels** kiezen de optie **Toevoegen** en selecteer alle vier labels.</span><span class="sxs-lookup"><span data-stu-id="a08d2-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="a08d2-133">Selecteer **Toevoegen** en selecteer vervolgens **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="a08d2-134">Selecteer volgende **in het deelvenster Labels kiezen** om te **publiceren.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="a08d2-135">Selecteer volgende **in het** deelvenster Locaties **kiezen.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="a08d2-136">Voer in **het deelvenster Naam uw beleid** de optie **Voorbeeldorganisatie** in **Naam** in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="a08d2-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="a08d2-137">Selecteer in **het deelvenster** Uw instellingen controleren de optie **Labels publiceren.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="a08d2-138">Het kan enkele minuten duren voordat de bewaarlabels zijn gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="a08d2-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="a08d2-139">Fase 3: Bewaarlabels toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="a08d2-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="a08d2-140">In deze fase ontdekt u het standaardgedrag van bewaarlabels voor bestanden in de map Documenten van een SharePoint Online-site en wijzigt u handmatig het bewaarlabel van een document.</span><span class="sxs-lookup"><span data-stu-id="a08d2-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="a08d2-141">Maak eerst een teamsite op gevoelig niveau SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a08d2-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="a08d2-142">Als u een privé-exemplaar van uw browser gebruikt, meld u zich aan [bij het Microsoft 365 beheercentrum](https://admin.microsoft.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="a08d2-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="a08d2-143">Selecteer in de lijst met tegels **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="a08d2-144">Selecteer op het **SharePoint** in uw browser de optie **Site maken.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="a08d2-145">Selecteer teamsite **op de pagina** Een **site maken.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="a08d2-146">Voer in **het vak Teamsitenaam** **SensitiveFiles in.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="a08d2-147">Typ in **het vak Teamsitebeschrijving** de **SharePoint voor gevoelige bestanden.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="a08d2-148">Selecteer **in Privacy-instellingen** de optie **Privé- alleen leden** hebben toegang tot deze site en selecteren vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="a08d2-149">Selecteer voltooien Wie het deelvenster Wilt u **toevoegen?** </span><span class="sxs-lookup"><span data-stu-id="a08d2-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="a08d2-150">Configureer vervolgens de map Documenten van de teamsite SensitiveFiles voor het label Gevoelige bewaring.</span><span class="sxs-lookup"><span data-stu-id="a08d2-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="a08d2-151">Selecteer documenten **op het tabblad SensitiveFiles** van **uw** browser.</span><span class="sxs-lookup"><span data-stu-id="a08d2-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="a08d2-152">Selecteer het **Instellingen** pictogram en selecteer vervolgens **Bibliotheekinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="a08d2-153">Selecteer **onder Machtigingen en beheer** de optie Label toepassen op items in deze lijst of **bibliotheek.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="a08d2-154">Als deze optie niet wordt weergegeven, zijn uw bewaarlabels nog niet gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="a08d2-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="a08d2-155">Probeer deze stap op een later tijdstip.</span><span class="sxs-lookup"><span data-stu-id="a08d2-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="a08d2-156">In **Instellingen-Label toepassen,** **selecteert** u Gevoelig in de vervolgkeuzevak en selecteert u **Vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="a08d2-157">Maak vervolgens een nieuw document op de site SensitiveFiles en wijzig het bewaarlabel.</span><span class="sxs-lookup"><span data-stu-id="a08d2-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="a08d2-158">Selecteer nieuw   >  **Word-document** in de map documenten.</span><span class="sxs-lookup"><span data-stu-id="a08d2-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="a08d2-159">Voer tekst in het lege document in.</span><span class="sxs-lookup"><span data-stu-id="a08d2-159">Enter some text in the blank document.</span></span> <span data-ttu-id="a08d2-160">Wacht totdat de tekst is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="a08d2-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="a08d2-161">Selecteer gedeelde documenten op de **menubalk.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="a08d2-162">Selecteer naast **Document.docx** bestandsnaam het verticale beletselteken en selecteer **vervolgens Details**.</span><span class="sxs-lookup"><span data-stu-id="a08d2-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="a08d2-163">In het rechterdeelvenster, in de sectie Eigenschappen, onder **Bewaarlabel** toepassen, wordt het label Gevoelige bewaring automatisch toegepast op het document.  </span><span class="sxs-lookup"><span data-stu-id="a08d2-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="a08d2-164">Klik **op Alles bewerken.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="a08d2-165">Selecteer in **Document.docx** deelvenster Onder **Bewaarlabel toepassen** het label Zeer **vertrouwelijk** en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="a08d2-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="a08d2-166">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="a08d2-166">Next step</span></span>

<span data-ttu-id="a08d2-167">Ontdek extra [functies en](m365-enterprise-test-lab-guides.md#information-protection) mogelijkheden voor informatiebeveiliging in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="a08d2-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a08d2-168">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a08d2-168">See also</span></span>

[<span data-ttu-id="a08d2-169">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="a08d2-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a08d2-170">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="a08d2-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a08d2-171">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="a08d2-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)