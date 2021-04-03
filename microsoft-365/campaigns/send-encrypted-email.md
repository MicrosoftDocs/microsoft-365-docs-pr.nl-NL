---
title: Versleutelde e-mail verzenden
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Meer informatie over het verzenden van versleutelde e-mail met Outlook.
ms.openlocfilehash: 209734bd52d1d97278d5632f035723758fe2e016
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576971"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="319e0-103">Uw gevoelige e-mailberichten versleutelen of labelen</span><span class="sxs-lookup"><span data-stu-id="319e0-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="319e0-104">Uw gegevens en campagnegegevens zijn belangrijk en vaak vertrouwelijk.</span><span class="sxs-lookup"><span data-stu-id="319e0-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="319e0-105">Bescherm deze gevoelige informatie met behulp van versleutelings- en gevoeligheidslabels, zodat u en uw e-mailontvangers de informatie met de gevoeligheid behandelen die hiervoor nodig is.</span><span class="sxs-lookup"><span data-stu-id="319e0-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="319e0-106">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="319e0-106">Best practices</span></span>

<span data-ttu-id="319e0-107">Voordat u e-mail verzendt met vertrouwelijke of gevoelige informatie, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="319e0-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="319e0-108">**Versleuteling:** U kunt uw e-mail versleutelen om de privacy van de gegevens in de e-mail te beschermen.</span><span class="sxs-lookup"><span data-stu-id="319e0-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="319e0-109">Wanneer u een e-mailbericht versleutelt, wordt het geconverteerd van leesbare tekst zonder tekst naar vervormde cyphertekst.</span><span class="sxs-lookup"><span data-stu-id="319e0-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="319e0-110">Alleen de geadresseerde met de persoonlijke sleutel die overeenkomt met de openbare sleutel die wordt gebruikt om het bericht te versleutelen, kan het bericht ontcijferen om te lezen.</span><span class="sxs-lookup"><span data-stu-id="319e0-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="319e0-111">Elke geadresseerde zonder de bijbehorende persoonlijke sleutel ziet echter niet-versleutelbare tekst.</span><span class="sxs-lookup"><span data-stu-id="319e0-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="319e0-112">Uw beheerder kan regels definiëren om berichten die aan bepaalde criteria voldoen, automatisch te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="319e0-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="319e0-113">Uw beheerder kan bijvoorbeeld een regel maken die alle berichten versleutelt die buiten uw organisatie worden verzonden of alle berichten met specifieke woorden of woordgroepen.</span><span class="sxs-lookup"><span data-stu-id="319e0-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="319e0-114">Versleutelingsregels worden automatisch toegepast.</span><span class="sxs-lookup"><span data-stu-id="319e0-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="319e0-115">**Gevoeligheidslabels:** Uw campagne kan ook gevoeligheidslabels instellen die u op uw bestanden en e-mail kunt toepassen, zodat ze voldoen aan het beleid voor informatiebeveiliging van uw campagne.</span><span class="sxs-lookup"><span data-stu-id="319e0-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="319e0-116">Wanneer u een label in stelt, blijft het label bij uw e-mail, zelfs wanneer het wordt verzonden, bijvoorbeeld door als koptekst naar uw bericht te worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="319e0-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagram van een e-mailbericht met bijroepen voor etiketten en versleuteling](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="319e0-118">Instellen</span><span class="sxs-lookup"><span data-stu-id="319e0-118">Set it up</span></span>

<span data-ttu-id="319e0-119">Als u een bericht wilt versleutelen dat niet voldoet aan een vooraf gedefinieerde regel of als uw beheerder geen regels heeft ingesteld, kunt u verschillende versleutelingsregels toepassen voordat u het bericht verzendt.</span><span class="sxs-lookup"><span data-stu-id="319e0-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="319e0-120">Als u een versleuteld bericht wilt verzenden vanuit Outlook 2013 of 2016 of Outlook 2016 voor Mac, selecteert u **Opties > Machtigingen** en selecteert u vervolgens de gewenste beveiligingsoptie.</span><span class="sxs-lookup"><span data-stu-id="319e0-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="319e0-121">U kunt ook een versleuteld bericht verzenden door de **knop** Beveiligen te selecteren in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="319e0-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="319e0-122">Zie Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook voor pc voor [meer informatie.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)</span><span class="sxs-lookup"><span data-stu-id="319e0-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="319e0-123">Beheerinstellingen</span><span class="sxs-lookup"><span data-stu-id="319e0-123">Admin settings</span></span>

<span data-ttu-id="319e0-124">U vindt alles over het instellen van e-mailversleuteling bij [E-mailversleuteling in Microsoft 365.](../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="319e0-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](../compliance/email-encryption.md).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="319e0-125">E-mailberichten automatisch versleutelen</span><span class="sxs-lookup"><span data-stu-id="319e0-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="319e0-126">Beheerders kunnen regels voor e-mailstroom maken om e-mailberichten die vanuit uw campagne worden verzonden en ontvangen, automatisch te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="319e0-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="319e0-127">Stel regels in om uitgaande e-mailberichten te versleutelen en versleuteling te verwijderen uit versleutelde berichten die afkomstig zijn van uw organisatie of van antwoorden naar versleutelde berichten die vanuit uw organisatie worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="319e0-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="319e0-128">U maakt regels voor de e-mailstroom om e-mailberichten te versleutelen met de nieuwe mogelijkheden van Office 365 Message Encryption (OME).</span><span class="sxs-lookup"><span data-stu-id="319e0-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="319e0-129">Definieer e-mailstroomregels voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van het Exchange Admin Center (EAC).</span><span class="sxs-lookup"><span data-stu-id="319e0-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="319e0-130">Meld u aan in een webbrowser met een werk- of schoolaccount dat globale beheerdersmachtigingen heeft gekregen.</span><span class="sxs-lookup"><span data-stu-id="319e0-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="319e0-131">Kies de tegel Beheerder.</span><span class="sxs-lookup"><span data-stu-id="319e0-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="319e0-132">Kies beheercentra in het beheercentrum **> Exchange.**</span><span class="sxs-lookup"><span data-stu-id="319e0-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="319e0-133">Zie Regels voor e-mailstroom definiëren [om e-mailberichten te versleutelen voor meer informatie.](../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="319e0-133">For more information, see [Define mail flow rules to encrypt email messages](../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="319e0-134">Uw versleutelingsberichten brand</span><span class="sxs-lookup"><span data-stu-id="319e0-134">Brand your encryption messages</span></span>

<span data-ttu-id="319e0-135">U kunt ook uw campagnestijl toepassen om het uiterlijk en de tekst in de e-mailberichten aan te passen.</span><span class="sxs-lookup"><span data-stu-id="319e0-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="319e0-136">Zie Het merk van uw organisatie toevoegen aan uw versleutelde berichten voor [meer informatie.](../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="319e0-136">For more information, see [Add your organization's brand to your encrypted messages](../compliance/email-encryption.md).</span></span>