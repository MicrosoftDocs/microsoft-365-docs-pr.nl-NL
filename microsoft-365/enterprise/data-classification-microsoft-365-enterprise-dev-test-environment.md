---
title: Gegevensclassificatie voor uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab-handleiding voor het maken en gebruiken van Office 365-bewaarlabels in documenten in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 6534eff67e9c91423eb6f81415cb3ef2e965dcc1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812028"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7c690-103">Gegevensclassificatie voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="7c690-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7c690-104">*Deze Test Lab Guide kan worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="7c690-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7c690-105">Met de instructies in dit artikel configureert u gegevensclassificatie met office 365-bewaarlabels in uw Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="7c690-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Lab-handleidingen testen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7c690-107">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="7c690-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7c690-108">Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="7c690-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7c690-109">Als u alleen office 365-bewaarlabels op een lichtgewicht manier wilt configureren met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="7c690-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7c690-110">Als u Office 365-bewaarlabels in een gesimuleerde onderneming wilt configureren, volgt u de instructies in [pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="7c690-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c690-111">Voor het testen van Office 365-bewaarlabels is de gesimuleerde bedrijfstestomgeving niet vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="7c690-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7c690-112">Het wordt hier als optie verstrekt, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="7c690-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="7c690-113">Fase 2: Bewaarlabels voor Office 365 maken</span><span class="sxs-lookup"><span data-stu-id="7c690-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="7c690-114">In deze fase maakt u de bewaarlabels voor de verschillende retentieniveaus voor SharePoint Online-documentenmappen.</span><span class="sxs-lookup"><span data-stu-id="7c690-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="7c690-115">Meld u aan bij het [Microsoft 365-beveiligingscentrum](https://security.microsoft.com/homepage) met uw wereldwijde beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="7c690-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="7c690-116">Klik op het **tabblad Start - Microsoft 365** van uw browser op Labels classificatie > **behouden**.</span><span class="sxs-lookup"><span data-stu-id="7c690-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="7c690-117">Klik **op Een label maken**.</span><span class="sxs-lookup"><span data-stu-id="7c690-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="7c690-118">Typ In het deelvenster **Naam van uw label** de tekst Intern **openbaar** in Naam van **uw label**en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7c690-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="7c690-119">Klik in het deelvenster **Beschrijvingen van bestandsplannen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7c690-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="7c690-120">Stel in het deelvenster **Labelinstellingen** indien nodig **Retentie** in **op Aan**en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7c690-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7c690-121">Klik **in** het deelvenster Instellingen controleren op **Het label maken**.</span><span class="sxs-lookup"><span data-stu-id="7c690-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="7c690-122">Herhaal stap 3-7 voor extra labels met deze namen:</span><span class="sxs-lookup"><span data-stu-id="7c690-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="7c690-123">Privé</span><span class="sxs-lookup"><span data-stu-id="7c690-123">Private</span></span>
    
  - <span data-ttu-id="7c690-124">Gevoelige</span><span class="sxs-lookup"><span data-stu-id="7c690-124">Sensitive</span></span>
    
  - <span data-ttu-id="7c690-125">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="7c690-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="7c690-126">Klik in het deelvenster **Bewaarlabels** op **Labels publiceren**.</span><span class="sxs-lookup"><span data-stu-id="7c690-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="7c690-127">Klik **in** het deelvenster Labels kiezen om te publiceren op Labels kiezen om te **publiceren**.</span><span class="sxs-lookup"><span data-stu-id="7c690-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="7c690-128">Klik **in** het deelvenster Labels kiezen op **Toevoegen** en selecteer alle vier de labels.</span><span class="sxs-lookup"><span data-stu-id="7c690-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="7c690-129">Klik **op Toevoegen**en klik vervolgens op **Gereed.**</span><span class="sxs-lookup"><span data-stu-id="7c690-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="7c690-130">Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7c690-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="7c690-131">Klik in het deelvenster **Locaties kiezen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7c690-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="7c690-132">Typ **Voorbeeldorganisatie** in **Naam**in het **deelvenster Naam en** klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7c690-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="7c690-133">Klik in het deelvenster **Instellingen controleren** op **Labels publiceren**.</span><span class="sxs-lookup"><span data-stu-id="7c690-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="7c690-134">Houd er rekening mee dat het enkele minuten kan duren voordat de bewaarlabels zijn gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="7c690-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="7c690-135">Fase 3: Bewaarlabels van Office 365 toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="7c690-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="7c690-136">In deze fase ontdekt u het standaardlabelgedrag voor bestanden in de map Documenten van een SharePoint Online-site en wijzigt u handmatig het bewaarlabel van een document.</span><span class="sxs-lookup"><span data-stu-id="7c690-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="7c690-137">Maak eerst een SharePoint Online-teamsite op gevoelig niveau:</span><span class="sxs-lookup"><span data-stu-id="7c690-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="7c690-138">Meld u met een privé-exemplaar van uw browser aan bij de [Office 365-portal](https://portal.office.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="7c690-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="7c690-139">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7c690-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="7c690-140">Klik op het nieuwe **tabblad SharePoint** in uw browser op **Site maken**.</span><span class="sxs-lookup"><span data-stu-id="7c690-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="7c690-141">Klik **op de pagina Een site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="7c690-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="7c690-142">Typ **Gevoelige bestanden**in **teamsitenaam**.</span><span class="sxs-lookup"><span data-stu-id="7c690-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="7c690-143">Typ **SharePoint-site voor gevoelige bestanden**in **teamsitebeschrijving**.</span><span class="sxs-lookup"><span data-stu-id="7c690-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="7c690-144">Selecteer **privé-instellingen**en selecteer **deze site**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7c690-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7c690-145">Klik in het deelvenster Wie wilt **Finish** **u toevoegen?**</span><span class="sxs-lookup"><span data-stu-id="7c690-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="7c690-146">Configureer vervolgens de map Documenten van de teamsite SensitiveFiles voor het label Gevoelige bewaaropslag.</span><span class="sxs-lookup"><span data-stu-id="7c690-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="7c690-147">Klik op het tabblad **SensitiveFiles** van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="7c690-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="7c690-148">Klik op het pictogram Instellingen en klik vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="7c690-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="7c690-149">Klik **onder Machtigingen en beheer**op Label toepassen op items in deze lijst of **bibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="7c690-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="7c690-150">Als deze optie niet wordt weergegeven, worden uw bewaarlabels nog niet gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="7c690-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="7c690-151">Probeer deze stap op een later tijdstip.</span><span class="sxs-lookup"><span data-stu-id="7c690-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="7c690-152">Selecteer In **Label Instellingen toepassen**de optie **Gevoelig** in de vervolgkeuzelijst en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7c690-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="7c690-153">Maak vervolgens een nieuw document op de site SensitiveFiles en wijzighet bewaarlabel.</span><span class="sxs-lookup"><span data-stu-id="7c690-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="7c690-154">Klik in de map documenten op **Nieuw > Word-document**.</span><span class="sxs-lookup"><span data-stu-id="7c690-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="7c690-155">Typ tekst in het lege document.</span><span class="sxs-lookup"><span data-stu-id="7c690-155">Type some text in the blank document.</span></span> <span data-ttu-id="7c690-156">Wacht tot de tekst is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="7c690-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="7c690-157">Klik in de menubalk op **Gedeelde documenten**.</span><span class="sxs-lookup"><span data-stu-id="7c690-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="7c690-158">Klik op de verticale ellips naast de bestandsnaam **Document.docx** en klik vervolgens op **Details**.</span><span class="sxs-lookup"><span data-stu-id="7c690-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="7c690-159">Houd er in het rechterdeelvenster in de sectie **Eigenschappen** onder **Bewaarlabel Bewaar toepassing**op op dat het label **Gevoelige** bewaaring automatisch is toegepast.</span><span class="sxs-lookup"><span data-stu-id="7c690-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="7c690-160">Klik **op Alles bewerken**.</span><span class="sxs-lookup"><span data-stu-id="7c690-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="7c690-161">Selecteer in het deelvenster **Document.docx** onder **Bewaarlabel Toepassen**het label **Zeer vertrouwelijk** en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7c690-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="7c690-162">Zie de [stap Classificatie configureren voor uw omgeving](infoprotect-configure-classification.md) in de fase **Informatiebeveiliging** voor informatie en koppelingen voor het implementeren van Office 365-bewaarlabels in productie.</span><span class="sxs-lookup"><span data-stu-id="7c690-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="7c690-163">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="7c690-163">Next step</span></span>

<span data-ttu-id="7c690-164">Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="7c690-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c690-165">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7c690-165">See also</span></span>

[<span data-ttu-id="7c690-166">Microsoft 365 Enterprise Test Lab-handleidingen</span><span class="sxs-lookup"><span data-stu-id="7c690-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7c690-167">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="7c690-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7c690-168">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="7c690-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
