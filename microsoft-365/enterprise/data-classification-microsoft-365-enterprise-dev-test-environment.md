---
title: Gegevensclassificatie voor uw Microsoft 365-testomgeving voor ondernemingen
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
description: Gebruik deze test lab-handleiding voor het maken en gebruiken van labels voor bewaarbeleid voor documenten in uw Microsoft 365 voor Enterprise-test omgeving.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487730"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f37bc-103">Gegevensclassificatie voor uw Microsoft 365-testomgeving voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="f37bc-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f37bc-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="f37bc-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f37bc-105">In dit artikel wordt uitgelegd hoe u gegevensclassificatie kunt configureren met labels voor bewaarbeleid in uw Microsoft 365 voor Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="f37bc-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="f37bc-106">Het classificeren van gegevens in de testomgeving omvat drie fasen:</span><span class="sxs-lookup"><span data-stu-id="f37bc-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="f37bc-107">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="f37bc-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="f37bc-108">Fase 2: Labels voor bewaarbeleid maken</span><span class="sxs-lookup"><span data-stu-id="f37bc-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="f37bc-109">Fase 3: Labels voor bewaarbeleid toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="f37bc-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f37bc-111">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="f37bc-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f37bc-112">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="f37bc-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f37bc-113">Als u alleen Bewaar etiketten op een lichte manier wilt configureren met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f37bc-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f37bc-114">Als u de Bewaar labels van een gesimuleerde Enterprise-organisatie wilt configureren, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f37bc-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f37bc-115">Voor het testen van labels voor bewaarbeleid is de gesimuleerde Enterprise-testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="f37bc-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f37bc-116">Dit wordt hier als optie geboden, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="f37bc-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="f37bc-117">Fase 2: Labels voor bewaarbeleid maken</span><span class="sxs-lookup"><span data-stu-id="f37bc-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="f37bc-118">In deze fase maakt u de etiketten voor bewaarbeleid voor de verschillende niveaus voorbehoud van mappen in SharePoint Online-documenten:</span><span class="sxs-lookup"><span data-stu-id="f37bc-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="f37bc-119">Meld u aan bij het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/homepage) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="f37bc-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="f37bc-120">Selecteer op het tabblad **Start-Microsoft 365-beveiliging** van uw browser de optie **classificatie**  >  **Bewaar labels**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="f37bc-121">Selecteer **een etiket maken**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="f37bc-122">**Voer in** het deelvenster naam van **de naam uw** naam in de **naam van uw etiket**in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="f37bc-123">Selecteer in het deelvenster met **descriptors voor bestandsplan** de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="f37bc-124">Stel in het deelvenster **etiketinstellingen** , indien nodig, **bewaren** in **op**aan en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="f37bc-125">Selecteer in het deelvenster **uw instellingen controleren** **de optie het etiket maken**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="f37bc-126">Herhaal stappen 3-7 voor aanvullende labels met de volgende namen:</span><span class="sxs-lookup"><span data-stu-id="f37bc-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="f37bc-127">Privé</span><span class="sxs-lookup"><span data-stu-id="f37bc-127">Private</span></span>
  - <span data-ttu-id="f37bc-128">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="f37bc-128">Sensitive</span></span>
  - <span data-ttu-id="f37bc-129">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="f37bc-129">Highly Confidential</span></span>
1. <span data-ttu-id="f37bc-130">Selecteer in het deelvenster **Bewaar labels** de optie **etiketten publiceren**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="f37bc-131">Selecteer in het deelvenster **Kies Labels voor publiceren** de optie **etiketten selecteren om te publiceren**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="f37bc-132">Selecteer in het deelvenster **labels kiezen** de optie **toevoegen** en selecteer alle vier de etiketten.</span><span class="sxs-lookup"><span data-stu-id="f37bc-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="f37bc-133">Selecteer **toevoegen**en selecteer **gereed**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="f37bc-134">Selecteer **volgende**in het deelvenster **Kies Labels die u wilt publiceren** .</span><span class="sxs-lookup"><span data-stu-id="f37bc-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="f37bc-135">Selecteer in het deelvenster **kieslocaties** de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="f37bc-136">Voer in het deelvenster **uw beleid een naam** geven in **voorbeeld van organisatie** in **naam**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="f37bc-137">Selecteer in het deelvenster **uw instellingen controleren** de optie **etiketten publiceren**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="f37bc-138">Het kan een paar minuten duren voordat de Bewaar etiketten zijn gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="f37bc-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="f37bc-139">Fase 3: Labels voor bewaarbeleid toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="f37bc-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="f37bc-140">In deze fase ontdekt u het standaardgedrag van het Bewaar label voor bestanden in de map documenten van een SharePoint Online-site en wijzigt u het Bewaar label van een document handmatig.</span><span class="sxs-lookup"><span data-stu-id="f37bc-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="f37bc-141">Maak eerst een SharePoint Online-team site met gevoelige niveaus:</span><span class="sxs-lookup"><span data-stu-id="f37bc-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="f37bc-142">Meld u met een persoonlijk exemplaar van uw browser aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="f37bc-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="f37bc-143">Selecteer in de lijst met tegels de optie **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="f37bc-144">Selecteer **site maken**op het tabblad nieuwe **SharePoint** in de browser.</span><span class="sxs-lookup"><span data-stu-id="f37bc-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="f37bc-145">Selecteer op de pagina **een site maken** de optie **team site**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="f37bc-146">Voer in het vak **naam van team site** **SensitiveFiles**in.</span><span class="sxs-lookup"><span data-stu-id="f37bc-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="f37bc-147">Voer in het vak **Beschrijving van team site** de **SharePoint-site in voor gevoelige bestanden**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="f37bc-148">Selecteer bij **privacyinstellingen**de optie **persoonlijke leden hebben toegang tot deze site**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="f37bc-149">Selecteer in het deelvenster **wie wilt u toevoegen?** de optie **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="f37bc-150">Vervolgens configureert u de map documenten van de team site van SensitiveFiles voor het gevoelige Bewaar label.</span><span class="sxs-lookup"><span data-stu-id="f37bc-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="f37bc-151">Selecteer op het tabblad **SensitiveFiles** van uw browser de optie **documenten**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="f37bc-152">Selecteer het pictogram **instellingen** en selecteer vervolgens **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="f37bc-153">Selecteer onder **machtigingen en beheer**de optie **label toepassen op items in deze lijst of bibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="f37bc-154">Als deze optie niet wordt weergegeven, zijn uw Bewaar etiketten nog niet gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="f37bc-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="f37bc-155">Probeer deze stap later nog eens.</span><span class="sxs-lookup"><span data-stu-id="f37bc-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="f37bc-156">Selecteer in de vervolgkeuzelijst **instellingen-labels toepassen**de optie **gevoelig** en selecteer vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="f37bc-157">Vervolgens maakt u een nieuw document op de site van SensitiveFiles en wijzigt u het Bewaar label.</span><span class="sxs-lookup"><span data-stu-id="f37bc-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="f37bc-158">Selecteer in de map documenten de optie **Nieuw**  >  **Word-document**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="f37bc-159">Typ wat tekst in het lege document.</span><span class="sxs-lookup"><span data-stu-id="f37bc-159">Enter some text in the blank document.</span></span> <span data-ttu-id="f37bc-160">Wacht totdat de tekst is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="f37bc-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="f37bc-161">Selecteer in de menubalk **gedeelde documenten**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="f37bc-162">Selecteer naast de bestandsnaam van de **Document.docx** de drie puntjes en selecteer vervolgens **Details**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="f37bc-163">Selecteer in het rechterdeelvenster, in de sectie **Eigenschappen** , onder **Bewaar label toepassen**, het document met het **gevoelige** Bewaar label automatisch toegepast.</span><span class="sxs-lookup"><span data-stu-id="f37bc-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="f37bc-164">Klik op **Alles bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="f37bc-165">Selecteer in het deelvenster **Document.docx** , onder **Bewaar etiket toepassen**, de optie voor **zeer vertrouwelijke** etiketten en selecteer vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f37bc-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="f37bc-166">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f37bc-166">Next step</span></span>

<span data-ttu-id="f37bc-167">Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="f37bc-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f37bc-168">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f37bc-168">See also</span></span>

[<span data-ttu-id="f37bc-169">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="f37bc-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f37bc-170">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="f37bc-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f37bc-171">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="f37bc-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
