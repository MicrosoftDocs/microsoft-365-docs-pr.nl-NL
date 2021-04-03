---
title: Bedreigingsbeveiliging voor Microsoft 365 Business Premium verhogen
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Stel compliancefuncties in om gegevensverlies te voorkomen en om de gevoelige informatie van uw en uw klanten veilig te houden.
ms.openlocfilehash: c0accc37d3dcda9ba75813f01a98a3233c5a8369
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579949"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="9b038-103">Compliancefuncties instellen</span><span class="sxs-lookup"><span data-stu-id="9b038-103">Set up compliance features</span></span>

<span data-ttu-id="9b038-104">Uw Microsoft 365 Business Premium bevat functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw en uw klanten veilig te houden.</span><span class="sxs-lookup"><span data-stu-id="9b038-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="9b038-105">DLP-functies instellen</span><span class="sxs-lookup"><span data-stu-id="9b038-105">Set up DLP features</span></span>

<span data-ttu-id="9b038-106">Zie [Een DLP-beleid maken op basis](../compliance/create-a-dlp-policy-from-a-template.md) van een sjabloon voor een voorbeeld van het instellen van een beleid ter bescherming tegen verlies van persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="9b038-106">See [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="9b038-107">DLP wordt geleverd met veel kant-en-klare beleidssjablonen voor veel verschillende locales.</span><span class="sxs-lookup"><span data-stu-id="9b038-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="9b038-108">Bijvoorbeeld: Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, en meer.</span><span class="sxs-lookup"><span data-stu-id="9b038-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="9b038-109">Zie [Wat de DLP-beleidsjablonen bevatten voor](../compliance/what-the-dlp-policy-templates-include.md) een volledige lijst.</span><span class="sxs-lookup"><span data-stu-id="9b038-109">See [What the DLP policy templates include](../compliance/what-the-dlp-policy-templates-include.md) for a full list.</span></span> <span data-ttu-id="9b038-110">Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon.</span><span class="sxs-lookup"><span data-stu-id="9b038-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="9b038-111">E-mailretentie instellen met Archivering van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9b038-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="9b038-112">**Exchange Online Archiving-licentiefuncties** helpen bij het handhaven van nalevings- en regelgevingsstandaarden door e-mailinhoud voor eDiscovery te behouden.</span><span class="sxs-lookup"><span data-stu-id="9b038-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="9b038-113">Het helpt ook uw risico te beperken als er een proces is en biedt een manier om gegevens te herstellen na een beveiligingsinbreuk of wanneer u verwijderde items moet herstellen.</span><span class="sxs-lookup"><span data-stu-id="9b038-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="9b038-114">U kunt de bewaring van rechtszaken gebruiken om alle inhoud van een gebruiker te behouden of bewaarbeleid gebruiken om aan te passen wat u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="9b038-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="9b038-115">**Procesrecht in de wacht:** U kunt alle postvakinhoud, inclusief verwijderde items, behouden door het hele postvak van een gebruiker in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="9b038-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="9b038-116">Als u een postvak in de wacht wilt zetten voor rechtszaken, gaat u naar het beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="9b038-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="9b038-117">Ga in de linkernavigatiebalk naar **Gebruikers** \> **Actieve gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="9b038-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="9b038-118">Selecteer een gebruiker van wie u het postvak in de wacht wilt zetten.</span><span class="sxs-lookup"><span data-stu-id="9b038-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="9b038-119">Vouw in het gebruikersvenster **E-mailinstellingen** uit en kies naast **Meer instellingen** de optie **Exchange-eigenschappen bewerken.**</span><span class="sxs-lookup"><span data-stu-id="9b038-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="9b038-120">Kies op de postvakpagina voor de gebruiker \*\* postvakfuncties \*\* aan de linkerkant en kies vervolgens de **koppeling** Inschakelen onder **Procesvoering.**</span><span class="sxs-lookup"><span data-stu-id="9b038-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="9b038-121">In het **dialoogvenster Procesrecht** kunt u de duur van de procesduur opgeven in het veld Duur van de duur van **de procesduur.**</span><span class="sxs-lookup"><span data-stu-id="9b038-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="9b038-122">Laat het veld leeg als u een oneindige greep wilt plaatsen.</span><span class="sxs-lookup"><span data-stu-id="9b038-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="9b038-123">U kunt ook notities toevoegen en de eigenaar van het postvak naar een website leiden die u mogelijk meer moet uitleggen over de procedure.</span><span class="sxs-lookup"><span data-stu-id="9b038-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="9b038-124">\>**Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9b038-124">\> **Save**.</span></span>
    
<span data-ttu-id="9b038-125">**Bewaring:** U kunt aangepaste bewaarbeleidsregels inschakelen, bijvoorbeeld om inhoud voor een bepaalde periode te bewaren of inhoud permanent te verwijderen aan het einde van de bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="9b038-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="9b038-126">Zie Overzicht van [bewaarbeleid voor](../compliance/retention.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9b038-126">To learn more, see [Overview of retention policies](../compliance/retention.md).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="9b038-127">Gevoeligheidslabels instellen</span><span class="sxs-lookup"><span data-stu-id="9b038-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="9b038-128">Gevoeligheidslabels worden bij Azure Information Protection (AIP) Plan 1 gebruikt, en u kunt uw documenten en e-mailberichten classificeren en desgewenst beveiligen door etiketten toe te passen.</span><span class="sxs-lookup"><span data-stu-id="9b038-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="9b038-129">Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers, of door een combinatie te gebruiken waarin gebruikers aanbevelingen krijgen.</span><span class="sxs-lookup"><span data-stu-id="9b038-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="9b038-130">Als u Gevoeligheidslabels wilt instellen, bekijkt u video over het maken en beheren [van gevoeligheidslabels.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="9b038-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="9b038-131">De Azure Information Protection-client handmatig installeren</span><span class="sxs-lookup"><span data-stu-id="9b038-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="9b038-132">De AIP-client handmatig installeren:</span><span class="sxs-lookup"><span data-stu-id="9b038-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="9b038-133">Download **AzinfoProtection_UL.exe** downloadcentrum [van Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="9b038-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="9b038-134">U kunt controleren of de installatie heeft gewerkt door  een Word-document weer te geven en ervoor te zorgen dat de optie Gevoeligheid beschikbaar is op het **tabblad** Start.</span><span class="sxs-lookup"><span data-stu-id="9b038-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="9b038-135">![Vervolgkeuzevenster Beveiliging in een Word-document.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="9b038-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="9b038-136">Zie De [client installeren voor meer informatie.](/azure/information-protection/infoprotect-tutorial-step3)</span><span class="sxs-lookup"><span data-stu-id="9b038-136">For more information, see [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span></span>