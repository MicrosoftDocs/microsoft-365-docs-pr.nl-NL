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
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Stel nalevingsfuncties in om gegevensverlies te voorkomen en gevoelige gegevens te labelen.
ms.openlocfilehash: 5213c55f4a8ce0e223896f1b960847714d6d06cb
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031410"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="742f6-103">Nalevingsfuncties instellen</span><span class="sxs-lookup"><span data-stu-id="742f6-103">Set up compliance features</span></span>

<span data-ttu-id="742f6-104">Uw Microsoft 365 Business wordt geleverd met functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw klanten veilig te houden.</span><span class="sxs-lookup"><span data-stu-id="742f6-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="742f6-105">DLP-functies instellen</span><span class="sxs-lookup"><span data-stu-id="742f6-105">Set up DLP features</span></span>

<span data-ttu-id="742f6-106">Zie [een DLP-beleid maken op basis van een sjabloon](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) voor een voorbeeld over het instellen van een beleid ter bescherming tegen persoonlijk identificeerbare informatie (PII).</span><span class="sxs-lookup"><span data-stu-id="742f6-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="742f6-107">DLP wordt geleverd met veel gebruiksklare beleidssjablonen voor veel verschillende landinstellingen.</span><span class="sxs-lookup"><span data-stu-id="742f6-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="742f6-108">Bijvoorbeeld, Australië financiële gegevens, Canada Personal Information Act, Amerikaanse financiële gegevens, enz. Zie [wat de DLP-beleidssjablonen](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) voor een volledige lijst bevatten.</span><span class="sxs-lookup"><span data-stu-id="742f6-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="742f6-109">Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon.</span><span class="sxs-lookup"><span data-stu-id="742f6-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="742f6-110">E-mail retentie instellen met Exchange Online-archivering</span><span class="sxs-lookup"><span data-stu-id="742f6-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="742f6-111">De licentie functies voor het **archiveren van Exchange Online** helpen de nalevings-en regelgevingsnormen te handhaven door e-mail inhoud voor eDiscovery te behouden</span><span class="sxs-lookup"><span data-stu-id="742f6-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="742f6-112">Het helpt ook verminderen uw risico in het geval van een rechtszaak en biedt een manier om gegevens te herstellen na een inbreuk op de beveiliging, of wanneer u nodig hebt om verwijderde items te herstellen.</span><span class="sxs-lookup"><span data-stu-id="742f6-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="742f6-113">U rechtszaak blokkering gebruiken om alle inhoud van een gebruiker te behouden, of gebruik bewaarbeleid om aan te passen wat u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="742f6-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="742f6-114">**Rechtszaak Hold:** U alle inhoud van de postbus inclusief verwijderde items behouden door het hele postvak van een gebruiker in de rechtszaak te bewaren.</span><span class="sxs-lookup"><span data-stu-id="742f6-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="742f6-115">Om een postbus te plaatsen in de rechtszaak Hold, in het Admin Center:</span><span class="sxs-lookup"><span data-stu-id="742f6-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="742f6-116">Ga in de linkernavigatiebalk naar **gebruikers** \> **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="742f6-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="742f6-117">Selecteer een gebruiker wiens postvak u wilt plaatsen in de rechtszaak blokkering en in de gebruikers deelvenster Vouw **e-mail instellingen** en naast **meer instellingen** kiest u **Exchange-eigenschappen bewerken**.</span><span class="sxs-lookup"><span data-stu-id="742f6-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="742f6-118">Op de postbus pagina voor de gebruiker, kiest u \* \* mailbox functies \* \* op de linker NAV, en kies vervolgens de koppeling **inschakelen** onder **rechtszaak vasthouden**.</span><span class="sxs-lookup"><span data-stu-id="742f6-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="742f6-119">In het dialoogvenster **rechtszaak houden** u de duur van de rechtszaak houden in het veld **rechtszaak Hold duur** , laat veld leeg als u wilt plaatsen een oneindige hold.</span><span class="sxs-lookup"><span data-stu-id="742f6-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="742f6-120">U ook notities toevoegen en de eigenaar van de brievenbus naar een website sturen die u wellicht meer moet uitleggen over de \> **Bewaar**procedure voor rechtszaken.</span><span class="sxs-lookup"><span data-stu-id="742f6-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="742f6-121">**Retentie:** U aangepaste bewaarbeleid inschakelen, bijvoorbeeld om te behouden voor een bepaalde hoeveelheid tijd of verwijderen van inhoud permanent aan het einde van de bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="742f6-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="742f6-122">Zie [overzicht van bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="742f6-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="742f6-123">Gevoeligheids etiketten instellen</span><span class="sxs-lookup"><span data-stu-id="742f6-123">Set up Sensitivity labels</span></span>

<span data-ttu-id="742f6-124">Gevoeligheidslabels worden geleverd met Azure Information Protection (AIP) plan 1 en helpen u bij het classificeren en optioneel beveiligen van uw documenten en e-mail berichten, door het toepassen van labels.</span><span class="sxs-lookup"><span data-stu-id="742f6-124">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="742f6-125">Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden, handmatig door gebruikers definiëren of met behulp van een combinatie waar gebruikers aanbevelingen worden gegeven.</span><span class="sxs-lookup"><span data-stu-id="742f6-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="742f6-126">Als u gevoeligheids labels wilt instellen, u video met [gevoeligheids etiketten maken en beheren](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="742f6-126">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="742f6-127">De Azure Information Protection-client handmatig installeren</span><span class="sxs-lookup"><span data-stu-id="742f6-127">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="742f6-128">De AIP-client handmatig installeren:</span><span class="sxs-lookup"><span data-stu-id="742f6-128">To manually install the AIP client:</span></span>

1. <span data-ttu-id="742f6-129">Download **AzinfoProtection_UL. exe** van [het Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="742f6-129">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="742f6-130">U controleren of de installatie heeft gewerkt door een Word-document te bekijken en ervoor te zorgen dat de optie **gevoeligheid** beschikbaar is op het tabblad **Start** .</span><span class="sxs-lookup"><span data-stu-id="742f6-130">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="742f6-131">![Drop-down bescherming tabblad in een Word-document.](media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="742f6-131">![Protection tab drop-down in a Word document.](media/word-sensitivity.png)</span></span>

<span data-ttu-id="742f6-132">Zie voor meer informatie, [de client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="742f6-132">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
