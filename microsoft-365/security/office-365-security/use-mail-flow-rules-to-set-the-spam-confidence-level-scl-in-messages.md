---
title: Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u de SCL van berichten instellen in Exchange Online Protection.
ms.openlocfilehash: 10440d5ac8cd57388f4550f21ca72ce7aa1a2745
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808451"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="d11f3-103">Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen</span><span class="sxs-lookup"><span data-stu-id="d11f3-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="d11f3-104">U een e-mailstroomregel maken (ook wel een transportregel genoemd) waarmee het spamvertrouwen (SCL) van een e-mailbericht wordt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="d11f3-104">You can create a mail flow rule (also known as a transport rule) that sets the spam confidence level (SCL) of an email message.</span></span> <span data-ttu-id="d11f3-105">De SCL is een maat voor hoe waarschijnlijk een bericht is om spam te zijn.</span><span class="sxs-lookup"><span data-stu-id="d11f3-105">The SCL is a measure of how likely a message is to be spam.</span></span> <span data-ttu-id="d11f3-106">Spam is ongevraagde (en meestal ongewenste) e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="d11f3-106">Spam is unsolicited (and typically unwanted) email messages.</span></span> <span data-ttu-id="d11f3-107">De service onderneemt verschillende actie op een bericht, afhankelijk van de SCL-beoordeling.</span><span class="sxs-lookup"><span data-stu-id="d11f3-107">The service takes different action on a message depending on its SCL rating.</span></span> <span data-ttu-id="d11f3-108">U bijvoorbeeld spaminhoud omzeilen die wordt gefilterd op berichten die worden verzonden van mensen binnen uw organisatie, omdat u erop vertrouwt dat een bericht dat intern van een collega wordt verzonden, geen spam is.</span><span class="sxs-lookup"><span data-stu-id="d11f3-108">For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam.</span></span> <span data-ttu-id="d11f3-109">Het gebruik van regels voor de stroom van e-mail om de SCL-waarde van een bericht in te stellen, geeft u meer controle bij het verwerken van spam.</span><span class="sxs-lookup"><span data-stu-id="d11f3-109">Using mail flow rules to set the SCL value of a message gives you increased control in handling spam.</span></span>

 <span data-ttu-id="d11f3-110">**Wat moet je weten voordat je begint?**</span><span class="sxs-lookup"><span data-stu-id="d11f3-110">**What do you need to know before you begin?**</span></span>

- <span data-ttu-id="d11f3-111">Geschatte tijd om deze procedure te voltooien: 10 minuten.</span><span class="sxs-lookup"><span data-stu-id="d11f3-111">Estimated time to complete this procedure: 10 minutes.</span></span>

- <span data-ttu-id="d11f3-112">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d11f3-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="d11f3-113">Zie de vermelding 'Regels voor de stroomstroom' in [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) of [Functiemachtigingen in EOP](feature-permissions-in-eop.md)om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="d11f3-113">To see what permissions you need, see the "Mail flow rules" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) or [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="d11f3-114">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="d11f3-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="d11f3-115">Een e-mailstroomregel maken waarmee de SCL van een bericht wordt ingesteld</span><span class="sxs-lookup"><span data-stu-id="d11f3-115">To create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="d11f3-116">Kies in het Exchange-beheercentrum (EAC) de optie \> **Regels** **voor de stroom van e-mail** .</span><span class="sxs-lookup"><span data-stu-id="d11f3-116">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d11f3-117">Kies Pictogram](../../media/ITPro-EAC-AddIcon.gif) **Nieuw**![toevoegen en selecteer Vervolgens Een nieuwe regel **maken**.</span><span class="sxs-lookup"><span data-stu-id="d11f3-117">Choose **New**![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="d11f3-118">Geef een naam voor de regel op.</span><span class="sxs-lookup"><span data-stu-id="d11f3-118">Specify a name for the rule.</span></span>

4. <span data-ttu-id="d11f3-119">Kies **Meer opties**en geef vervolgens onder Deze regel toepassen **als**u een voorwaarde opgeeft die de actie activeert die u voor deze regel instelt (namelijk het instellen van de SCL-waarde).</span><span class="sxs-lookup"><span data-stu-id="d11f3-119">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>

   <span data-ttu-id="d11f3-120">U bijvoorbeeld de **afzender** \> **intern/extern**instellen en vervolgens in het dialoogvenster **Afzenderlocatie selecteren** binnen de **organisatie**selecteren en **ok**kiezen.</span><span class="sxs-lookup"><span data-stu-id="d11f3-120">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
   <span data-ttu-id="d11f3-121">![Afzenderlocatie selecteren](../../media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="d11f3-121">![Select sender location](../../media/EOP-ETR-SetSCL-1.jpg)</span></span>

5. <span data-ttu-id="d11f3-122">Selecteer onder **Ga als volgt**de optie De \> eigenschappen van het bericht **wijzigen** **en stel het betrouwbaarheidsniveau voor spam (SCL)** in .</span><span class="sxs-lookup"><span data-stu-id="d11f3-122">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

6. <span data-ttu-id="d11f3-123">Selecteer in het vak **SCL opgeven** een van de volgende waarden en kies **OK:**</span><span class="sxs-lookup"><span data-stu-id="d11f3-123">In the **Specify SCL** box, select one of the following values, and choose **OK**:</span></span>

   - <span data-ttu-id="d11f3-124">**Bypass spam filtering**: Hiermee wordt de SCL ingesteld op -1, wat betekent dat contentfiltering niet wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d11f3-124">**Bypass spam filtering**: This sets the SCL to -1, which means that content filtering won't be performed.</span></span>

   - <span data-ttu-id="d11f3-125">**0-4**: Het bericht wordt doorgegeven aan het inhoudsfilter voor extra verwerking.</span><span class="sxs-lookup"><span data-stu-id="d11f3-125">**0-4**: The message will be passed along to the content filter for additional processing.</span></span>

   - <span data-ttu-id="d11f3-126">**5-6**: De actie die voor **spam** is opgegeven in het toepasselijke beleid voor inhoudsfilter wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="d11f3-126">**5-6**: The action specified for **Spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="d11f3-127">Standaard is de actie om het bericht naar de map Ongewenste e-mail van de ontvanger te verzenden.</span><span class="sxs-lookup"><span data-stu-id="d11f3-127">By default, the action is to send the message to the recipient's Junk Email folder.</span></span>

   - <span data-ttu-id="d11f3-128">**7-9**: De actie die is opgegeven voor **spam met een hoog vertrouwen** in het toepasselijke beleid voor inhoudsfilter, wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="d11f3-128">**7-9**: The action specified for **High confidence spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="d11f3-129">Standaard is de actie om het bericht naar de map Ongewenste e-mail van de ontvanger te verzenden.</span><span class="sxs-lookup"><span data-stu-id="d11f3-129">By default, the action is to send the message to the recipient's Junk Email folder.</span></span>

   <span data-ttu-id="d11f3-130">Zie Uw beleid voor spamfilters configureren voor meer informatie over het configureren van uw beleid voor [inhoudsfilters.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d11f3-130">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="d11f3-131">Zie [Vertrouwensniveaus](spam-confidence-levels.md)voor spam voor meer informatie over SCL-waarden in de service.</span><span class="sxs-lookup"><span data-stu-id="d11f3-131">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

7. <span data-ttu-id="d11f3-132">Geef extra eigenschappen voor de regel op en kies **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d11f3-132">Specify additional properties for the rule, and choose **save**.</span></span>

   > [!TIP]
   > <span data-ttu-id="d11f3-133">Zie De EAC gebruiken om regels voor [e-mailstroom te maken voor](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules)meer informatie over de extra eigenschappen die u voor deze regel selecteren of opgeven.</span><span class="sxs-lookup"><span data-stu-id="d11f3-133">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d11f3-134">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="d11f3-134">How do you know this worked?</span></span>

<span data-ttu-id="d11f3-135">Als u wilt controleren of deze procedure correct werkt, stuurt u een e-mailbericht naar iemand binnen uw organisatie en controleert u of de actie die op het bericht is uitgevoerd, zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="d11f3-135">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="d11f3-136">Als u bijvoorbeeld **het spamvertrouwensniveau (SCL) instelt op** **spamfiltering omzeilen,** moet het bericht naar het postvak in van de opgegeven ontvanger worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="d11f3-136">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="d11f3-137">Als u echter **het spamvertrouwensniveau (SCL) instelt op** **9**, en de **spamactie met veel vertrouwen** voor uw toepasselijke beleid voor inhoudsfilter is om het bericht naar de map Ongewenste e-mail te verplaatsen, moet het bericht worden verzonden naar de map Ongewenste e-mail van de opgegeven ontvanger.</span><span class="sxs-lookup"><span data-stu-id="d11f3-137">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
