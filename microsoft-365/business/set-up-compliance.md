---
title: Bedreigingsbeveiliging voor Microsoft 365 Business Premium verbeteren
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: U kunt nalevings functies instellen om verlies van gegevens te voorkomen en de gevoelige informatie van uw klanten veilig te houden.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841168"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="a7848-103">Compliancefuncties instellen</span><span class="sxs-lookup"><span data-stu-id="a7848-103">Set up compliance features</span></span>

<span data-ttu-id="a7848-104">Uw Microsoft 365 Business Premium biedt functies om uw gegevens en apparaten te beschermen en u te helpen de gevoelige informatie van uw klanten veilig te houden.</span><span class="sxs-lookup"><span data-stu-id="a7848-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="a7848-105">DLP-functies instellen</span><span class="sxs-lookup"><span data-stu-id="a7848-105">Set up DLP features</span></span>

<span data-ttu-id="a7848-106">Zie [een DLP-beleid maken op basis van een sjabloon](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) voor een voorbeeld over het instellen van een beleid ter bescherming tegen het beschermen van persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="a7848-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="a7848-107">DLP biedt een groot aantal kant-en-klare beleidssjablonen voor veel verschillende landinstellingen.</span><span class="sxs-lookup"><span data-stu-id="a7848-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="a7848-108">Bijvoorbeeld financiële gegevens voor Australië, persoonlijke gegevens van Canada, Amerikaanse financiële gegevens, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="a7848-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="a7848-109">Bekijk [wat de DLP-beleidssjablonen zijn](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) voor een volledige lijst.</span><span class="sxs-lookup"><span data-stu-id="a7848-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="a7848-110">Al deze sjablonen kunnen worden ingeschakeld, vergelijkbaar met het voorbeeld van de PII-sjabloon.</span><span class="sxs-lookup"><span data-stu-id="a7848-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="a7848-111">E-mail behoud instellen met Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="a7848-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="a7848-112">**Exchange Online Archiving** -licentie functies helpen bij de naleving van compliance en regelgevings normen door e-mail inhoud voor eDiscovery te behouden.</span><span class="sxs-lookup"><span data-stu-id="a7848-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="a7848-113">Dit levert ook minder Risico's op als er een nakomend en een manier is om gegevens te herstellen na een schending van de beveiliging of wanneer u verwijderde items moet herstellen.</span><span class="sxs-lookup"><span data-stu-id="a7848-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="a7848-114">U kunt met behulp van de procedure voor het bewaren van inhoud de inhoud van een gebruiker behouden of het bewaarbeleid gebruiken om de inhoud van de inhoud aan te passen.</span><span class="sxs-lookup"><span data-stu-id="a7848-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="a7848-115">**Bewaring voor rechtszaken:** U kunt alle inhoud van het postvak met de verwijderde items bewaren door het hele postvak van een gebruiker in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a7848-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="a7848-116">In het Beheercentrum kunt u een postvak op het geschil bewaren.</span><span class="sxs-lookup"><span data-stu-id="a7848-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="a7848-117">Ga in het linkernavigatievenster naar gebruikers van **gebruikers** met de \> **actieve gebruikers** .</span><span class="sxs-lookup"><span data-stu-id="a7848-117">In the left nav, go to **Users** \> **Active users** .</span></span>
    
2. <span data-ttu-id="a7848-118">Selecteer de gebruiker van wie u het postvak wilt plaatsen.</span><span class="sxs-lookup"><span data-stu-id="a7848-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="a7848-119">Vouw in het deelvenster gebruiker **e-mail instellingen** uit en kies naast **meer instellingen** de optie **Exchange-eigenschappen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="a7848-119">In the user pane, expand **Mail settings** , and next to **More settings** , choose **Edit Exchange properties** .</span></span>
    
3. <span data-ttu-id="a7848-120">Ga naar de pagina Postvak voor de gebruiker en kies \* \* Mailbox features \* \* aan de linkerkant en kies vervolgens de koppeling **inschakelen** onder voor de bewaring van de **geschil** .</span><span class="sxs-lookup"><span data-stu-id="a7848-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold** .</span></span>
    
4. <span data-ttu-id="a7848-121">In het dialoogvenster ter ter ter ter plaatse **bekleedt** u de wachtstand van de gewenste aanbieding in het veld duur van de **geschil** .</span><span class="sxs-lookup"><span data-stu-id="a7848-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="a7848-122">Laat het veld leeg als u het oneindig in de wacht wilt plaatsen.</span><span class="sxs-lookup"><span data-stu-id="a7848-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="a7848-123">U kunt ook aantekeningen toevoegen en de eigenaar van het postvak direct naar een website gaan als u meer wilt weten over het bewaren van de geschillen.</span><span class="sxs-lookup"><span data-stu-id="a7848-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="a7848-124">\>**Save** .</span><span class="sxs-lookup"><span data-stu-id="a7848-124">\> **Save** .</span></span>
    
<span data-ttu-id="a7848-125">**Bewaren:** U kunt een aangepast bewaarbeleid inschakelen, bijvoorbeeld om gedurende een bepaalde periode te behouden of om inhoud permanent te verwijderen aan het einde van de bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="a7848-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="a7848-126">Voor meer informatie raadpleegt u [overzicht van bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span><span class="sxs-lookup"><span data-stu-id="a7848-126">To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="a7848-127">Gevoeligheids labels instellen</span><span class="sxs-lookup"><span data-stu-id="a7848-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="a7848-128">Vertrouwelijkheids etiketten komen voor Azure Information Protection (beheerders abonnement 1) en helpen u bij het classificeren van uw documenten en e-mailberichten, door labels toe te passen.</span><span class="sxs-lookup"><span data-stu-id="a7848-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="a7848-129">Labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers of met behulp van een combinatie waarbij gebruikers aanbevelingen doen.</span><span class="sxs-lookup"><span data-stu-id="a7848-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="a7848-130">Voor het instellen van laag tekstlabels, bekijkt u de video voor het [maken en beheren van gevoeligheids labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="a7848-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="a7848-131">De Azure Information Protection-client handmatig installeren</span><span class="sxs-lookup"><span data-stu-id="a7848-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="a7848-132">De beheerders client handmatig installeren:</span><span class="sxs-lookup"><span data-stu-id="a7848-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="a7848-133">Download **AzinfoProtection_UL.exe** van het [Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="a7848-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="a7848-134">U kunt controleren of de installatie heeft gewerkt door een Word-document te bekijken en ervoor te zorgen dat de optie **gevoeligheid** beschikbaar is op het tabblad **Start** .</span><span class="sxs-lookup"><span data-stu-id="a7848-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="a7848-135">![Vervolgkeuzelijst beveiliging in een Word-document.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="a7848-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="a7848-136">Zie voor meer informatie [de client installeren](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="a7848-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
