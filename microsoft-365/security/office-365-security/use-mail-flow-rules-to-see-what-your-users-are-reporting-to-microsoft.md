---
title: Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: U een Exchange-e-mailstroomregel maken om te voorkomen dat uw gebruikers e-mailberichten naar Microsoft verzenden voor analyse en deze gebruiken in uw eigen beveiligingsprocessen
ms.openlocfilehash: ae8655416840dc326344e2c2aea7c67486389492
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805890"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="35300-103">Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren</span><span class="sxs-lookup"><span data-stu-id="35300-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="35300-104">Er zijn meerdere manieren waarop u fout-positieve en fout-negatieve berichten naar Microsoft verzenden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="35300-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="35300-105">Als beheerder u regels voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren als spam, niet-spam en phishing.As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span><span class="sxs-lookup"><span data-stu-id="35300-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="35300-106">Zie [Spam, niet-spam en phishing-scamberichten verzenden voor analyse voor](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="35300-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="35300-107">Omgekeerd u een Exchange-mailstroomregel maken (ook wel een transportregel genoemd) om te voorkomen dat uw gebruikers e-mailberichten naar Microsoft verzenden voor analyse en deze gebruiken in uw eigen beveiligingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="35300-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="35300-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="35300-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="35300-109">Geschatte tijd om te voltooien: 5 minuten</span><span class="sxs-lookup"><span data-stu-id="35300-109">Estimated time to complete: 5 minutes</span></span>

<span data-ttu-id="35300-110">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="35300-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="35300-111">Zie de vermeldingen 'E-mailstroom' en 'Outlook op het webpostvakbeleid' in [Exchange Online-machtigingen](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="35300-111">To see what permissions you need, see the "Mail flow"  and "Outlook on the web mailbox policies" entries in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

<span data-ttu-id="35300-112">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="35300-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="35300-113">Gebruik de EAC om een e-mailstroomregel te maken om handmatige ongewenste e-mail-, phishing- en niet-ongewenste rapporten van gebruikers weer te geven</span><span class="sxs-lookup"><span data-stu-id="35300-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="35300-114">Navigeer in de EAC naar **E-mailstroomregels** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="35300-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="35300-115">Klik ![op](../../media/ITPro-EAC-AddIcon.gif) Pictogram toevoegen en selecteer **Vervolgens Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="35300-115">Click ![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="35300-116">Geef de regel een naam en klik op **Meer opties**.</span><span class="sxs-lookup"><span data-stu-id="35300-116">Give the rule a name and then click **More options**.</span></span>

4. <span data-ttu-id="35300-117">Selecteer **onder Deze regel toepassen als**u De **ontvanger** selecteert en vervolgens adres selecteert dat een van deze **woorden bevat**.</span><span class="sxs-lookup"><span data-stu-id="35300-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>

5. <span data-ttu-id="35300-118">Ga in het vak **Woorden of zinnen opgeven** de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="35300-118">In the **specify words or phrases** box, do the following steps:</span></span>

   - <span data-ttu-id="35300-119">Typ, `abuse@messaging.microsoft.com` **klik** ![op](../../media/ITPro-EAC-AddIcon.gif)Pictogram `junk@office365.microsoft.com` Toevoegen, typ](../../media/ITPro-EAC-AddIcon.gif)en klik vervolgens op Pictogram Toevoegen **toevoegen** ![.</span><span class="sxs-lookup"><span data-stu-id="35300-119">Type `abuse@messaging.microsoft.com`, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), type `junk@office365.microsoft.com` and then click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="35300-120">Deze e-mailadressen worden gebruikt om valse negatieve berichten naar Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="35300-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>

   - <span data-ttu-id="35300-121">Typ `phish@office365.microsoft.com` en klik op](../../media/ITPro-EAC-AddIcon.gif)Pictogram Toevoegen **toevoegen** ![.</span><span class="sxs-lookup"><span data-stu-id="35300-121">Type `phish@office365.microsoft.com` and then click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="35300-122">Dit e-mailadres wordt gebruikt om gemiste phishingberichten naar Microsoft te sturen.</span><span class="sxs-lookup"><span data-stu-id="35300-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>

   - <span data-ttu-id="35300-123">Typ, `false_positive@messaging.microsoft.com` **klik** ![op](../../media/ITPro-EAC-AddIcon.gif)Pictogram `not_junk@office365.microsoft.com`toevoegen, typ en](../../media/ITPro-EAC-AddIcon.gif) **klik** ![vervolgens op Pictogram toevoegen toevoegen .</span><span class="sxs-lookup"><span data-stu-id="35300-123">Type `false_positive@messaging.microsoft.com`, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), type `not_junk@office365.microsoft.com`, and then click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="35300-124">Deze e-mailadressen worden gebruikt om fout-positieve berichten naar Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="35300-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>

   - <span data-ttu-id="35300-125">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="35300-125">Click **OK**.</span></span>

6. <span data-ttu-id="35300-126">Selecteer **onder Doe het volgende**bcc het bericht **naar...** en selecteer vervolgens de postvakken waar u de berichten wilt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="35300-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span>

7. <span data-ttu-id="35300-127">Als u wilt, u selecties maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een bepaalde periode en andere selecties.</span><span class="sxs-lookup"><span data-stu-id="35300-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="35300-128">We raden u aan de regel te testen voor een periode voordat u deze afdwingt.</span><span class="sxs-lookup"><span data-stu-id="35300-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="35300-129">Zie [Procedures voor regels voor e-mailstromen](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="35300-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span>

8. <span data-ttu-id="35300-130">Klik **op** de knop Opslaan om de regel op te slaan.</span><span class="sxs-lookup"><span data-stu-id="35300-130">Click the **save** button to save the rule.</span></span> <span data-ttu-id="35300-131">Het staat in je lijst met regels.</span><span class="sxs-lookup"><span data-stu-id="35300-131">It appears in your list of rules.</span></span>

<span data-ttu-id="35300-132">Nadat u de regel hebt gemaakt en afgedwongen, worden alle berichten die vanuit uw organisatie naar opgegeven e-mailadressen worden verzonden, gekopieerd naar het opgegeven postvak.</span><span class="sxs-lookup"><span data-stu-id="35300-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
