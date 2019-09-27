---
title: Bedreigingsbeveiliging voor Microsoft 365 Business verhogen
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Stel de geavanceerde Bedreigingsbeveiliging van Office 365 in en beveilig gevoelige gegevens.
ms.openlocfilehash: 8144bcebe8a0cdf28a5e092f592362922ccbdd48
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288740"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="857da-103">Nalevingsfuncties instellen</span><span class="sxs-lookup"><span data-stu-id="857da-103">Set up compliance features</span></span>

<span data-ttu-id="857da-104">Uw Microsoft 365 Business wordt geleverd met functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw klanten veilig te houden.</span><span class="sxs-lookup"><span data-stu-id="857da-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="857da-105">DLP-functies instellen</span><span class="sxs-lookup"><span data-stu-id="857da-105">Set up DLP features</span></span>

<span data-ttu-id="857da-106">Zie [een DLP-beleid maken op basis van een sjabloon](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) voor een voorbeeld over het instellen van een beleid ter bescherming tegen persoonlijk identificeerbare informatie (PII).</span><span class="sxs-lookup"><span data-stu-id="857da-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="857da-107">DLP wordt geleverd met veel gebruiksklare beleidssjablonen voor veel verschillende landinstellingen.</span><span class="sxs-lookup"><span data-stu-id="857da-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="857da-108">Bijvoorbeeld, Australië financiële gegevens, Canada Personal Information Act, Amerikaanse financiële gegevens, enz. Zie [wat de DLP-beleidssjablonen](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) voor een volledige lijst bevatten.</span><span class="sxs-lookup"><span data-stu-id="857da-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="857da-109">Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon.</span><span class="sxs-lookup"><span data-stu-id="857da-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="857da-110">E-mail retentie instellen met Exchange Online-archivering</span><span class="sxs-lookup"><span data-stu-id="857da-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="857da-111">De licentie functies voor het **archiveren van Exchange Online** helpen de nalevings-en regelgevingsnormen te handhaven door e-mail inhoud voor eDiscovery te behouden</span><span class="sxs-lookup"><span data-stu-id="857da-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="857da-112">Het helpt ook verminderen uw risico in het geval van een rechtszaak en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging, of wanneer u nodig hebt om verwijderde items te herstellen.</span><span class="sxs-lookup"><span data-stu-id="857da-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="857da-113">U rechtszaak blokkering gebruiken om alle inhoud van een gebruiker te behouden, of gebruik bewaarbeleid om aan te passen wat u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="857da-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="857da-114">**Rechtszaak Hold:** U alle inhoud van de postbus inclusief verwijderde items behouden door het hele postvak van een gebruiker in de rechtszaak te bewaren.</span><span class="sxs-lookup"><span data-stu-id="857da-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="857da-115">Om een postbus te plaatsen in de rechtszaak Hold, in het Admin Center:</span><span class="sxs-lookup"><span data-stu-id="857da-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="857da-116">Ga in de linkernavigatiebalk naar **gebruikers** \> **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="857da-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="857da-117">Selecteer een gebruiker wiens postvak u wilt plaatsen in de rechtszaak blokkering en in de gebruikers deelvenster Vouw **e-mail instellingen** en naast **meer instellingen** kiest u **Exchange-eigenschappen bewerken**.</span><span class="sxs-lookup"><span data-stu-id="857da-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="857da-118">Op de postbus pagina voor de gebruiker, kiest u \* \* mailbox functies \* \* op de linker NAV, en kies vervolgens de koppeling **inschakelen** onder **rechtszaak vasthouden**.</span><span class="sxs-lookup"><span data-stu-id="857da-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="857da-119">In het dialoogvenster **rechtszaak houden** u de duur van de rechtszaak houden in het veld **rechtszaak Hold duur** , laat veld leeg als u wilt plaatsen een oneindige hold.</span><span class="sxs-lookup"><span data-stu-id="857da-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="857da-120">U ook notities toevoegen en de eigenaar van de brievenbus naar een website sturen die u wellicht meer moet uitleggen over de \> **Bewaar**procedure voor rechtszaken.</span><span class="sxs-lookup"><span data-stu-id="857da-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="857da-121">**Retentie:** U aangepaste bewaarbeleid inschakelen, bijvoorbeeld om te behouden voor een bepaalde hoeveelheid tijd of verwijderen van inhoud permanent aan het einde van de bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="857da-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="857da-122">Zie [overzicht van bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="857da-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="857da-123">Azure Information Protection-functies instellen</span><span class="sxs-lookup"><span data-stu-id="857da-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="857da-124">Azure Information Protection (AIP) helpt u bij het classificeren en optioneel beveiligen van uw documenten en e-mail berichten, door het toepassen van labels.</span><span class="sxs-lookup"><span data-stu-id="857da-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="857da-125">Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden, handmatig door gebruikers definiëren of met behulp van een combinatie waar gebruikers aanbevelingen worden gegeven.</span><span class="sxs-lookup"><span data-stu-id="857da-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="857da-126">In Outlook op het web u de volgende ingebouwde labels en beperkingen toepassen op uw e-mails:</span><span class="sxs-lookup"><span data-stu-id="857da-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="857da-127">**Niet doorsturen**: geadresseerden kunnen het bericht lezen, maar niet doorsturen, afdrukken of inhoud kopiëren</span><span class="sxs-lookup"><span data-stu-id="857da-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="857da-128">**Versleutelen**: het hele bericht is versleuteld.</span><span class="sxs-lookup"><span data-stu-id="857da-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="857da-129">Ontvangers moeten hun identiteit bevestigen voordat ze toegang krijgen tot versleutelde inhoud en kunnen geen versleuteling verwijderen.</span><span class="sxs-lookup"><span data-stu-id="857da-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="857da-130">**Vertrouwelijk**: geeft de werknemers in uw organisatie volledige machtigingen voor de e-mail inhoud en bijlagen, maar niet voor mensen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="857da-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="857da-131">Eigenaren van gegevens kunnen op elk gewenst moment inhoud bijhouden en intrekken.</span><span class="sxs-lookup"><span data-stu-id="857da-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="857da-132">**Zeer vertrouwelijk**: deze beperking kan worden toegepast op zeer vertrouwelijke gegevens, zodat werknemers de gegevens kunnen bekijken, bewerken en beantwoorden, maar niet doorsturen, afdrukken of kopiëren.</span><span class="sxs-lookup"><span data-stu-id="857da-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="857da-133">Eigenaren van gegevens kunnen op elk gewenst moment inhoud bijhouden en intrekken.</span><span class="sxs-lookup"><span data-stu-id="857da-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="857da-134">Zorg ervoor dat Azure Information Protection is geactiveerd</span><span class="sxs-lookup"><span data-stu-id="857da-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="857da-135">Om te controleren of AIP is geactiveerd:</span><span class="sxs-lookup"><span data-stu-id="857da-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="857da-136">Meld u aan bij [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="857da-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="857da-137">Selecteer **alle services** en typ *Azure Information Protection* in het **zoekvak**.</span><span class="sxs-lookup"><span data-stu-id="857da-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="857da-138">Zodra de resultaten weergegeven, klikt u op de start naast **Azure Information Protection** om het een favoriet en gemakkelijk te vinden later.</span><span class="sxs-lookup"><span data-stu-id="857da-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="857da-139">Selecteer **Azure Information Protection** \> - **beveiligingsactivering** en zorg ervoor dat de status is ingesteld op geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="857da-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="857da-140">Het Azure Information Protection-beleid en de standaardlabels weergeven</span><span class="sxs-lookup"><span data-stu-id="857da-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="857da-141">De bestaande labels weergeven en wijzigen:</span><span class="sxs-lookup"><span data-stu-id="857da-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="857da-142">Op de Azure Information Protection-dashboard, selecteer **classificaties** \> **labels**.</span><span class="sxs-lookup"><span data-stu-id="857da-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="857da-143">![Standaard labels voor Azure Information Protection.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="857da-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="857da-144">U elk label kiezen om opties te bekijken, u de weergavenaam, kleuren, etc. wijzigen.</span><span class="sxs-lookup"><span data-stu-id="857da-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="857da-145">Zie [wijzigen en maken van nieuwe labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) als u wilt maken van uw eigen.</span><span class="sxs-lookup"><span data-stu-id="857da-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="857da-146">De Azure Information Protection-client handmatig installeren</span><span class="sxs-lookup"><span data-stu-id="857da-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="857da-147">De AIP-client handmatig installeren:</span><span class="sxs-lookup"><span data-stu-id="857da-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="857da-148">Download **Azinfoprotection. exe** van [het Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="857da-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="857da-149">U controleren of de installatie heeft gewerkt door een Word-document te bekijken en ervoor te zorgen dat de optie **beveiligen** beschikbaar is op het tabblad **Start** .</span><span class="sxs-lookup"><span data-stu-id="857da-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="857da-150">![Drop-down bescherming tabblad in een Word-document.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="857da-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="857da-151">Zie voor meer informatie, [de client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="857da-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
