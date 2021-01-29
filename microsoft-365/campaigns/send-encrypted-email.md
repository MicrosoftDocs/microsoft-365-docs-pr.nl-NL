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
description: Meer informatie over het verzenden van versleutelde e-mail via Outlook.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044214"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="9267e-103">Uw gevoelige e-mailberichten versleutelen of labelen</span><span class="sxs-lookup"><span data-stu-id="9267e-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="9267e-104">Uw gegevens en campagnegegevens zijn belangrijk en vaak vertrouwelijk.</span><span class="sxs-lookup"><span data-stu-id="9267e-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="9267e-105">Bebeveiligen deze gevoelige informatie met behulp van versleuteling en gevoeligheidslabels, zodat u en uw e-mailontvangers de informatie met de gevoeligheid behandelen die hiervoor is vereist.</span><span class="sxs-lookup"><span data-stu-id="9267e-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="9267e-106">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="9267e-106">Best practices</span></span>

<span data-ttu-id="9267e-107">Voordat u een e-mailbericht met vertrouwelijke of gevoelige informatie verzendt, kunt u het volgende in- of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="9267e-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="9267e-108">**Versleuteling:** U kunt uw e-mail versleutelen om de privacy van de gegevens in de e-mail te beschermen.</span><span class="sxs-lookup"><span data-stu-id="9267e-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="9267e-109">Wanneer u een e-mailbericht versleutelt, wordt dit geconverteerd van leesbare tekst zonder tekst naar gecodeerde cypherische tekst.</span><span class="sxs-lookup"><span data-stu-id="9267e-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="9267e-110">Alleen de ontvanger met de persoonlijke sleutel die overeenkomt met de openbare sleutel waarmee het bericht is versleuteld, kan het bericht ontcijferen om te lezen.</span><span class="sxs-lookup"><span data-stu-id="9267e-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="9267e-111">Iedere ontvanger zonder de bijbehorende persoonlijke sleutel ziet echter ondeci bolvormige tekst.</span><span class="sxs-lookup"><span data-stu-id="9267e-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="9267e-112">Uw beheerder kan regels definiëren om berichten die aan bepaalde criteria voldoen, automatisch te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="9267e-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="9267e-113">Uw beheerder kan bijvoorbeeld een regel maken die alle berichten versleutelt die buiten uw organisatie worden verzonden of alle berichten die specifieke woorden of woordgroepen bevatten.</span><span class="sxs-lookup"><span data-stu-id="9267e-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="9267e-114">Versleutelingsregels worden automatisch toegepast.</span><span class="sxs-lookup"><span data-stu-id="9267e-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="9267e-115">**Gevoeligheidslabels:** Uw campagne kan ook gevoeligheidslabels instellen die u op uw bestanden en e-mailberichten kunt toepassen om ervoor te zorgen dat ze voldoen aan het beleid voor informatiebeveiliging van uw campagne.</span><span class="sxs-lookup"><span data-stu-id="9267e-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="9267e-116">Wanneer u een label in stelt, blijft het label bij uw e-mailbericht staan, zelfs wanneer het wordt verzonden, bijvoorbeeld door deze als een koptekst voor uw bericht weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9267e-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagram van een e-mailbericht met bijroepen voor labels en versleuteling](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="9267e-118">Instellen</span><span class="sxs-lookup"><span data-stu-id="9267e-118">Set it up</span></span>

<span data-ttu-id="9267e-119">Als u een bericht wilt versleutelen dat niet voldoet aan een vooraf gedefinieerde regel of als uw beheerder geen regels heeft ingesteld, kunt u verschillende versleutelingsregels toepassen voordat u het bericht verzendt.</span><span class="sxs-lookup"><span data-stu-id="9267e-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="9267e-120">Als u een versleuteld bericht wilt verzenden vanuit Outlook 2013 of 2016 of Outlook 2016 voor Mac, selecteert u Opties **>-machtigingen** en selecteert u vervolgens de gewenste beveiligingsoptie.</span><span class="sxs-lookup"><span data-stu-id="9267e-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="9267e-121">U kunt ook een versleuteld bericht verzenden door de knop Beveiligen te **selecteren** in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="9267e-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="9267e-122">Zie Versleutelde berichten verzenden, weergeven en [beantwoorden in Outlook voor pc voor meer informatie.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)</span><span class="sxs-lookup"><span data-stu-id="9267e-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="9267e-123">Beheerinstellingen</span><span class="sxs-lookup"><span data-stu-id="9267e-123">Admin settings</span></span>

<span data-ttu-id="9267e-124">Meer informatie over het instellen van e-mailversleuteling bij [E-mailversleuteling in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="9267e-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="9267e-125">E-mailberichten automatisch versleutelen</span><span class="sxs-lookup"><span data-stu-id="9267e-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="9267e-126">Beheerders kunnen regels voor de e-mailstroom maken om e-mailberichten die vanuit uw campagne worden verzonden en ontvangen, automatisch te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="9267e-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="9267e-127">Stel regels in om uitgaande e-mailberichten te versleutelen en versleuteling te verwijderen van versleutelde berichten die afkomstig zijn van binnen uw organisatie of van antwoorden op versleutelde berichten die van uw organisatie worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="9267e-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="9267e-128">U maakt regels voor de e-mailstroom om e-mailberichten te versleutelen met de nieuwe mogelijkheden van Office 365-berichtversleuteling (OME).</span><span class="sxs-lookup"><span data-stu-id="9267e-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="9267e-129">Definieer regels voor de e-mailstroom voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="9267e-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="9267e-130">Meld u in een webbrowser aan met een werk- of schoolaccount dat globale beheerdersmachtigingen heeft gekregen.</span><span class="sxs-lookup"><span data-stu-id="9267e-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="9267e-131">Kies de tegel Beheerder.</span><span class="sxs-lookup"><span data-stu-id="9267e-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="9267e-132">Kies in het beheercentrum **beheercentra > Exchange.**</span><span class="sxs-lookup"><span data-stu-id="9267e-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="9267e-133">Zie Regels voor de [e-mailstroom definiëren om e-mailberichten te versleutelen](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9267e-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="9267e-134">Uw versleutelingsberichten van een huismerk voorzien</span><span class="sxs-lookup"><span data-stu-id="9267e-134">Brand your encryption messages</span></span>

<span data-ttu-id="9267e-135">U kunt ook de huisstijl van uw campagne toepassen om het uiterlijk en de tekst in de e-mailberichten aan te passen.</span><span class="sxs-lookup"><span data-stu-id="9267e-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="9267e-136">Zie Het merk van uw organisatie toevoegen aan [versleutelde berichten voor meer informatie.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="9267e-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>
