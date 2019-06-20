---
title: Bescherming van de bedreiging voor Microsoft 365 Business verhogen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection instellen en vertrouwelijke gegevens te beschermen.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/31/2019
ms.locfileid: "35086300"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="172c1-103">Naleving van functies instellen</span><span class="sxs-lookup"><span data-stu-id="172c1-103">Set up compliance features</span></span>

<span data-ttu-id="172c1-104">Uw bedrijf Microsoft 365 beschikt u over functies voor uw bedrijf en uw klanten gevoelige informatie beveiligen en beschermen van uw gegevens en apparaten.</span><span class="sxs-lookup"><span data-stu-id="172c1-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="172c1-105">DLP-functies instellen</span><span class="sxs-lookup"><span data-stu-id="172c1-105">Set up DLP features</span></span>

<span data-ttu-id="172c1-106">Zie [een DLP-beleid van een sjabloon maken](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) voor een voorbeeld van het instellen van een beleid ter bescherming tegen persoonlijk identificeerbare informatie (PII).</span><span class="sxs-lookup"><span data-stu-id="172c1-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="172c1-107">DLP wordt geleverd met een groot aantal kant-en-klare sjablonen voor veel verschillende landinstellingen.</span><span class="sxs-lookup"><span data-stu-id="172c1-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="172c1-108">Bijvoorbeeld financiële gegevens van Australië, Canada persoonlijk informatie handelen, Amerikaanse financiële gegevens, enz. Zie [Wat de DLP-beleidssjablonen opnemen](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) voor een volledige lijst.</span><span class="sxs-lookup"><span data-stu-id="172c1-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="172c1-109">Al deze sjablonen kunnen worden ingeschakeld als in het voorbeeld van de sjabloon PII.</span><span class="sxs-lookup"><span data-stu-id="172c1-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="172c1-110">E-mail bewaren met Exchange Online Archiving instellen</span><span class="sxs-lookup"><span data-stu-id="172c1-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="172c1-111">Functies van **Exchange Online Archiving** licentie ten behoeve van conformiteit en wettelijke normen e-mail behouden voor eDiscovery-inhoud.</span><span class="sxs-lookup"><span data-stu-id="172c1-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="172c1-112">Ook vermindert het risico in geval van een rechtsgeding en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging of als u verwijderde items herstellen.</span><span class="sxs-lookup"><span data-stu-id="172c1-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="172c1-113">U kunt de rechtszaak vasthouden gebruiken voor het behoud van de inhoud van een gebruiker of bewaarbeleid gebruiken voor het aanpassen van wat u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="172c1-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="172c1-114">**Rechtszaak geblokkeerd:** U kunt alle inhoud met inbegrip van verwijderde items door het volledige postvak van een gebruiker in de rechtszaak plaatsen houdt behouden.</span><span class="sxs-lookup"><span data-stu-id="172c1-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="172c1-115">Om een postbus Afwachten rechtszaak, in de Admin center:</span><span class="sxs-lookup"><span data-stu-id="172c1-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="172c1-116">Ga naar **gebruikers** in de Linkernavigatie \> **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="172c1-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="172c1-117">Selecteer een gebruiker wiens postvak u wilt plaatsen op de rechtszaak houdt en vouw in het deelvenster gebruiker **e-mailinstellingen** en kies **Eigenschappen bewerken Exchange**naast **meer instellingen** .</span><span class="sxs-lookup"><span data-stu-id="172c1-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="172c1-118">Kies op de pagina postvak voor de gebruiker \*\* postbus functies \*\* op de Linkernavigatie en kies vervolgens de koppeling **inschakelen** onder **rechtszaak houdt**.</span><span class="sxs-lookup"><span data-stu-id="172c1-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="172c1-119">In de **rechtszaak houdt** in het dialoogvenster kunt u opgeven dat de rechtszaak duur in het veld **rechtszaak duur houdt** ingedrukt, laat het veld leeg als u wilt een oneindige wachtruimte te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="172c1-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="172c1-120">U kunt ook notities toevoegen en rechtstreeks van de eigenaar van het vak e-mail naar een website die u wellicht meer informatie over de rechtszaak houdt uitgelegd \> **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="172c1-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="172c1-121">**Bewaren:** U kunt bijvoorbeeld aangepaste bewaarbeleid behouden gedurende een bepaalde tijd of permanent verwijderen van inhoud aan het einde van de bewaarperiode inschakelen.</span><span class="sxs-lookup"><span data-stu-id="172c1-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="172c1-122">Voor meer informatie, Zie [overzicht van het bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="172c1-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="172c1-123">Azure informatie beveiligingsfuncties instellen</span><span class="sxs-lookup"><span data-stu-id="172c1-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="172c1-124">Azure informatie Protection (AIP) helpt u bij het classificeren en bescherming van uw documenten en e-mails, eventueel door labels toe te passen.</span><span class="sxs-lookup"><span data-stu-id="172c1-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="172c1-125">Labels kunnen automatisch worden toegepast die regels en voorwaarden definiëren door beheerders handmatig door gebruikers of door een combinatie waar gebruikers aanbevelingen krijgen.</span><span class="sxs-lookup"><span data-stu-id="172c1-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="172c1-126">U kunt in Outlook op het web de volgende ingebouwde labels en beperkingen toepassen op uw e-mailberichten:</span><span class="sxs-lookup"><span data-stu-id="172c1-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="172c1-127">**Niet doorsturen**: geadresseerden kunnen het bericht lezen, maar ze kunnen doorsturen, afdrukken of kopiëren van inhoud</span><span class="sxs-lookup"><span data-stu-id="172c1-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="172c1-128">**Coderen**: het hele bericht is gecodeerd.</span><span class="sxs-lookup"><span data-stu-id="172c1-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="172c1-129">Ontvangers hun identiteit moeten bevestigen voordat deze toegang krijgen tot gecodeerde inhoud en codering niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="172c1-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="172c1-130">**Vertrouwelijk**: de werknemers in uw organisatie biedt volledige machtigingen voor de inhoud van e-mail en bijlagen, maar niet voor personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="172c1-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="172c1-131">Eigenaars van gegevens kunnen bijhouden en de inhoud op elk moment intrekken.</span><span class="sxs-lookup"><span data-stu-id="172c1-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="172c1-132">**Zeer vertrouwelijke**: deze beperking tot zeer vertrouwelijke gegevens, zodat werknemers kunnen bekijken, bewerken, en beantwoorden, maar niet doorsturen, afdrukken of kopiëren van de gegevens kan worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="172c1-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="172c1-133">Eigenaars van gegevens kunnen bijhouden en de inhoud op elk moment intrekken.</span><span class="sxs-lookup"><span data-stu-id="172c1-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="172c1-134">Zorg ervoor dat informatiebeveiliging Azure is geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="172c1-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="172c1-135">Om te verifiëren dat de AIP is geactiveerd:</span><span class="sxs-lookup"><span data-stu-id="172c1-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="172c1-136">Inloggen op [portal Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="172c1-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="172c1-137">Selecteer **alle services** en typ in *Azure informatiebeveiliging* in het **Vak Zoeken**.</span><span class="sxs-lookup"><span data-stu-id="172c1-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="172c1-138">Zodra de resultaten worden weergegeven, klikt u op het begin volgende **Informatiebescherming Azure** een favoriet maken en later gemakkelijk te vinden.</span><span class="sxs-lookup"><span data-stu-id="172c1-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="172c1-139">**Azure informatie** beveiliging \> **activering bescherming** en zorg ervoor dat de status is ingesteld op actief.</span><span class="sxs-lookup"><span data-stu-id="172c1-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="172c1-140">De Azure informatiebeveiliging en de standaard etiketten weergeven</span><span class="sxs-lookup"><span data-stu-id="172c1-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="172c1-141">Als u wilt weergeven en wijzigen, de bestaande labels:</span><span class="sxs-lookup"><span data-stu-id="172c1-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="172c1-142">Selecteer op het dashboard Azure informatiebescherming **classificaties** \> **etiketten**.</span><span class="sxs-lookup"><span data-stu-id="172c1-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="172c1-143">![Standaard etiketten voor informatiebescherming Azure.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="172c1-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="172c1-144">U kunt een label om opties weer te geven, kunt u de weergavenaam, kleuren, enz.</span><span class="sxs-lookup"><span data-stu-id="172c1-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="172c1-145">Zie [wijzigen en nieuwe labels maken](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) als u wilt uw eigen maken.</span><span class="sxs-lookup"><span data-stu-id="172c1-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="172c1-146">De client Azure informatiebeveiliging handmatig installeren</span><span class="sxs-lookup"><span data-stu-id="172c1-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="172c1-147">De client AIP handmatig installeren:</span><span class="sxs-lookup"><span data-stu-id="172c1-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="172c1-148">**AzInfoProtection.exe** downloaden van het [Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="172c1-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="172c1-149">U kunt controleren of de installatie heeft gewerkt door een Word-document bekijken en ervoor te zorgen dat de optie **Protect** beschikbaar op het tabblad **Start is** .</span><span class="sxs-lookup"><span data-stu-id="172c1-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="172c1-150">![Tabblad Beveiliging vervolgkeuzelijst in een Word-document.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="172c1-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="172c1-151">Zie voor meer informatie [de client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="172c1-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
