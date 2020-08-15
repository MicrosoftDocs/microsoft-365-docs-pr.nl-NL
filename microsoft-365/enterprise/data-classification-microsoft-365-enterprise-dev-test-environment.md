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
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686404"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="945ca-103">Gegevensclassificatie voor uw Microsoft 365-testomgeving voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="945ca-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="945ca-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="945ca-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="945ca-105">Met de instructies in dit artikel configureert u de gegevensclassificatie met behulp van labels voor bewaarbeleid in uw Microsoft 365 voor Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="945ca-105">With the instructions in this article, you configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="945ca-107">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="945ca-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="945ca-108">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="945ca-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="945ca-109">Als u alleen Bewaar etiketten op een lichte manier wilt configureren met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="945ca-109">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="945ca-110">Als u de Bewaar labels van een gesimuleerde Enterprise-organisatie wilt configureren, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="945ca-110">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="945ca-111">Voor het testen van labels voor bewaarbeleid is de gesimuleerde Enterprise-testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="945ca-111">Testing retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="945ca-112">U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="945ca-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="945ca-113">Fase 2: Labels voor bewaarbeleid maken</span><span class="sxs-lookup"><span data-stu-id="945ca-113">Phase 2: Create retention labels</span></span>

<span data-ttu-id="945ca-114">In deze fase maakt u de labels voor bewaarbeleid voor de verschillende niveaus voorbehoud van mappen in SharePoint Online-documenten.</span><span class="sxs-lookup"><span data-stu-id="945ca-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="945ca-115">Meld u aan bij het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/homepage) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="945ca-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="945ca-116">Klik op het tabblad **Start-Microsoft 365-beveiliging** van uw browser op **classificatie > Bewaar etiketten**.</span><span class="sxs-lookup"><span data-stu-id="945ca-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="945ca-117">Klik op **een label maken**.</span><span class="sxs-lookup"><span data-stu-id="945ca-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="945ca-118">In het deelvenster **naam van uw etiket** typt u **intern openbaar** in **naam van uw etiket**en klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="945ca-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="945ca-119">Klik in het deelvenster met **descriptors voor bestands planning** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="945ca-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="945ca-120">Stel in het deelvenster **etiketinstellingen** , indien nodig, **bewaren** in **op**aan en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="945ca-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="945ca-121">Klik in het deelvenster **uw instellingen controleren** op **het etiket maken**.</span><span class="sxs-lookup"><span data-stu-id="945ca-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="945ca-122">Herhaal stappen 3-7 voor aanvullende labels met de volgende namen:</span><span class="sxs-lookup"><span data-stu-id="945ca-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="945ca-123">Privé</span><span class="sxs-lookup"><span data-stu-id="945ca-123">Private</span></span>
    
  - <span data-ttu-id="945ca-124">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="945ca-124">Sensitive</span></span>
    
  - <span data-ttu-id="945ca-125">Zeer vertrouwelijk</span><span class="sxs-lookup"><span data-stu-id="945ca-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="945ca-126">Klik in het deelvenster **Bewaar labels** op **etiketten publiceren**.</span><span class="sxs-lookup"><span data-stu-id="945ca-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="945ca-127">Klik in het deelvenster **Kies Labels om te publiceren** op **etiketten selecteren om te publiceren**.</span><span class="sxs-lookup"><span data-stu-id="945ca-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="945ca-128">Klik in het deelvenster **labels kiezen** op **toevoegen** en selecteer alle vier de etiketten.</span><span class="sxs-lookup"><span data-stu-id="945ca-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="945ca-129">Klik op **Toevoegen** en klik op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="945ca-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="945ca-130">Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="945ca-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="945ca-131">Klik in het deelvenster **Locaties kiezen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="945ca-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="945ca-132">Typ in het deelvenster **Uw beleid een naam geven** **Voorbeeldorganisatie** in **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="945ca-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="945ca-133">Klik in het deelvenster **uw instellingen controleren** op **etiketten publiceren**.</span><span class="sxs-lookup"><span data-stu-id="945ca-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="945ca-134">Het kan een paar minuten duren voordat de Bewaar etiketten zijn gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="945ca-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="945ca-135">Fase 3: Labels voor bewaarbeleid toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="945ca-135">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="945ca-136">In deze fase ontdekt u het standaardgedrag van het Bewaar label voor bestanden in de map documenten van een SharePoint Online-site en wijzigt u het Bewaar label van een document handmatig.</span><span class="sxs-lookup"><span data-stu-id="945ca-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="945ca-137">Maak eerst een SharePoint Online-team site met gevoelige niveaus:</span><span class="sxs-lookup"><span data-stu-id="945ca-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="945ca-138">Meld u met een persoonlijk exemplaar van uw browser aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="945ca-138">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="945ca-139">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="945ca-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="945ca-140">Klik op het tabblad nieuwe **SharePoint** in uw browser op **site maken**.</span><span class="sxs-lookup"><span data-stu-id="945ca-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="945ca-141">Klik op de pagina **Site maken** op **Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="945ca-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="945ca-142">Typ **SensitiveFiles**in de naam van de **team site**.</span><span class="sxs-lookup"><span data-stu-id="945ca-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="945ca-143">Typ in een beschrijving van de **team site**de **SharePoint-site voor gevoelige bestanden**.</span><span class="sxs-lookup"><span data-stu-id="945ca-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="945ca-144">Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="945ca-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="945ca-145">Klik in het deelvenster **personen die u wilt toevoegen** op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="945ca-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="945ca-146">Vervolgens configureert u de map documenten van de team site van SensitiveFiles voor het gevoelige Bewaar label.</span><span class="sxs-lookup"><span data-stu-id="945ca-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="945ca-147">Klik op het tabblad **SensitiveFiles** van uw browser op **documenten**.</span><span class="sxs-lookup"><span data-stu-id="945ca-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="945ca-148">Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="945ca-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="945ca-149">Klik onder **machtigingen en beheer**op **label toepassen op items in deze lijst of bibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="945ca-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="945ca-150">Als deze optie niet wordt weergegeven, zijn uw Bewaar etiketten nog niet gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="945ca-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="945ca-151">Probeer deze stap later nog eens.</span><span class="sxs-lookup"><span data-stu-id="945ca-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="945ca-152">Selecteer in de vervolgkeuzelijst **instellingen-labels toepassen**de optie **gevoelig** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="945ca-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="945ca-153">Vervolgens maakt u een nieuw document op de site van SensitiveFiles en wijzigt u het Bewaar label.</span><span class="sxs-lookup"><span data-stu-id="945ca-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="945ca-154">Klik in de map documenten op **nieuw > Word-document**.</span><span class="sxs-lookup"><span data-stu-id="945ca-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="945ca-155">Typ wat tekst in het lege document.</span><span class="sxs-lookup"><span data-stu-id="945ca-155">Type some text in the blank document.</span></span> <span data-ttu-id="945ca-156">Wacht totdat de tekst is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="945ca-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="945ca-157">Klik op de menubalk op **gedeelde documenten**.</span><span class="sxs-lookup"><span data-stu-id="945ca-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="945ca-158">Klik op de drie puntjes naast de naam van het **Document.docx** -bestand en klik vervolgens op **Details**.</span><span class="sxs-lookup"><span data-stu-id="945ca-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="945ca-159">In het deelvenster aan de rechterkant, in de sectie **Eigenschappen** , onder **Bewaar label toepassen**, is het **gevoelige** Bewaar label automatisch toegepast op het document.</span><span class="sxs-lookup"><span data-stu-id="945ca-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="945ca-160">Klik op **Alles bewerken**.</span><span class="sxs-lookup"><span data-stu-id="945ca-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="945ca-161">Selecteer in het deelvenster **Document.docx** , onder **Bewaar etiket toepassen**, de optie voor **zeer vertrouwelijke** etiketten en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="945ca-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="945ca-162">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="945ca-162">Next step</span></span>

<span data-ttu-id="945ca-163">Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="945ca-163">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="945ca-164">Zie ook</span><span class="sxs-lookup"><span data-stu-id="945ca-164">See also</span></span>

[<span data-ttu-id="945ca-165">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="945ca-165">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="945ca-166">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="945ca-166">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="945ca-167">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="945ca-167">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
