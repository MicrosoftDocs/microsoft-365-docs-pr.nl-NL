---
title: Versleutelde e-mail verzenden
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Meer informatie over het verzenden van versleutelde e-mail via Outlook.
ms.openlocfilehash: b9d5d32b61c49dcffaab83fb13e46d32f2166552
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080025"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="35e29-103">Uw gevoelige e-mail versleutelen of labelen</span><span class="sxs-lookup"><span data-stu-id="35e29-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="35e29-104">Uw gegevens en campagne-informatie zijn belangrijk en vaak vertrouwelijk.</span><span class="sxs-lookup"><span data-stu-id="35e29-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="35e29-105">Help deze gevoelige informatie te beschermen door versleutelings- en gevoeligheidslabels te gebruiken, zodat u en uw e-mailontvangers de informatie behandelen met de gevoeligheid die dit vereist.</span><span class="sxs-lookup"><span data-stu-id="35e29-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="35e29-106">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="35e29-106">Best practices</span></span>

<span data-ttu-id="35e29-107">Voordat u e-mail verzendt met vertrouwelijke of gevoelige informatie, u overwegen het inschakelen van:</span><span class="sxs-lookup"><span data-stu-id="35e29-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="35e29-108">**Versleuteling:** U uw e-mail versleutelen om de privacy van de informatie in de e-mail te beschermen.</span><span class="sxs-lookup"><span data-stu-id="35e29-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="35e29-109">Wanneer u een e-mailbericht versleutelt, wordt het omgezet van leesbare platte tekst in vervormde cyphertekst.</span><span class="sxs-lookup"><span data-stu-id="35e29-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="35e29-110">Alleen de ontvanger die de privésleutel heeft die overeenkomt met de openbare sleutel die wordt gebruikt om het bericht te versleutelen, kan het bericht ontcijferen om te lezen.</span><span class="sxs-lookup"><span data-stu-id="35e29-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="35e29-111">Elke ontvanger zonder de bijbehorende privésleutel ziet echter onleesbare tekst.</span><span class="sxs-lookup"><span data-stu-id="35e29-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="35e29-112">Uw beheerder kan regels definiëren om berichten die aan bepaalde criteria voldoen, automatisch te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="35e29-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="35e29-113">Uw beheerder kan bijvoorbeeld een regel maken die alle berichten versleutelt die buiten uw organisatie worden verzonden of alle berichten waarin specifieke woorden of zinnen worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="35e29-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="35e29-114">Alle versleutelingsregels worden automatisch toegepast.</span><span class="sxs-lookup"><span data-stu-id="35e29-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="35e29-115">**Gevoeligheidslabels:** Uw campagne kan ook gevoeligheidslabels instellen die u toepassen op uw bestanden en e-mail om ze te laten voldoen aan het beleid voor informatiebescherming van uw campagne.</span><span class="sxs-lookup"><span data-stu-id="35e29-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="35e29-116">Wanneer u een label instelt, blijft het label bij uw e-mail, zelfs wanneer het wordt verzonden, bijvoorbeeld door als koptekst naar uw bericht te worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="35e29-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagram van een e-mail met bijschriften voor labels en versleuteling](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="35e29-118">Instellen</span><span class="sxs-lookup"><span data-stu-id="35e29-118">Set it up</span></span>

<span data-ttu-id="35e29-119">Als u een bericht wilt versleutelen dat niet aan een vooraf gedefinieerde regel voldoet of als uw beheerder geen regels heeft ingesteld, u verschillende versleutelingsregels toepassen voordat u het bericht verzendt.</span><span class="sxs-lookup"><span data-stu-id="35e29-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="35e29-120">Als u een versleuteld bericht wilt verzenden vanuit Outlook 2013 of 2016 of Outlook 2016 voor Mac, selecteert u **Opties > Machtigingen**en selecteert u de beveiligingsoptie die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="35e29-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="35e29-121">U ook een versleuteld bericht verzenden door de knop **Beveiligen** in de webversie van Outlook te selecteren.</span><span class="sxs-lookup"><span data-stu-id="35e29-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="35e29-122">Zie [Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook voor pc voor](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="35e29-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="35e29-123">Beheerdersinstellingen</span><span class="sxs-lookup"><span data-stu-id="35e29-123">Admin settings</span></span>

<span data-ttu-id="35e29-124">U alles te weten komen over het instellen van e-mailversleuteling bij [e-mailversleuteling in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="35e29-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="35e29-125">E-mailberichten automatisch versleutelen</span><span class="sxs-lookup"><span data-stu-id="35e29-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="35e29-126">Beheerders kunnen regels voor e-mailstromen maken om e-mailberichten die worden verzonden en ontvangen van uw campagne automatisch te beschermen.</span><span class="sxs-lookup"><span data-stu-id="35e29-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="35e29-127">Stel regels in om uitgaande e-mailberichten te versleutelen en versleuteling te verwijderen uit versleutelde berichten die afkomstig zijn van uw organisatie of uit antwoorden op versleutelde berichten die vanuit uw organisatie worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="35e29-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="35e29-128">U maakt regels voor e-mailstroom om e-mailberichten te versleutelen met de nieuwe ome-mogelijkheden (Office 365 Message Encryption).</span><span class="sxs-lookup"><span data-stu-id="35e29-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="35e29-129">Definieer regels voor e-mailstroom voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van het Exchange Admin Center (EAC).</span><span class="sxs-lookup"><span data-stu-id="35e29-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="35e29-130">Meld u in een webbrowser aan met een werk- of schoolaccount dat algemene beheerdersmachtigingen heeft gekregen.</span><span class="sxs-lookup"><span data-stu-id="35e29-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span> 
2. <span data-ttu-id="35e29-131">Kies de tegel Beheerder.</span><span class="sxs-lookup"><span data-stu-id="35e29-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="35e29-132">Kies in het beheercentrum **Beheercentra > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="35e29-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="35e29-133">Zie [Regels voor e-mailstroom definiëren om e-mailberichten te versleutelen voor](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="35e29-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="35e29-134">Uw versleutelingsberichten brandmerken</span><span class="sxs-lookup"><span data-stu-id="35e29-134">Brand your encryption messages</span></span>

<span data-ttu-id="35e29-135">U uw campagnebranding ook toepassen om het uiterlijk en de tekst in de e-mailberichten aan te passen.</span><span class="sxs-lookup"><span data-stu-id="35e29-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="35e29-136">[Zie Het merk van uw organisatie toevoegen aan uw versleutelde berichten voor](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="35e29-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

