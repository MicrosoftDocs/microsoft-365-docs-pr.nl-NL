---
title: E-mailstroomregels gebruiken voor de SCL in berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u de SCL van berichten in Exchange Online Protection instellen.
ms.openlocfilehash: b7ea9a0f046e5a48f0de8d4ac9ae6d53821f03c0
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895093"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="1b9ff-103">Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in te stellen in berichten</span><span class="sxs-lookup"><span data-stu-id="1b9ff-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="1b9ff-104">Als u een Office 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection-klant (EOP) zonder Exchange Online-postvakken, gebruikt EOP antispambeleid (ook wel beleid voor spamfilters of inhoudsfilterbeleid genoemd) om te scannen binnenkomende berichten voor spam.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="1b9ff-105">Zie [Beleid voor antispam configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="1b9ff-106">Als u specifieke berichten als spam wilt markeren voordat ze worden gescand door spamfiltering, of berichten markeren zodat ze spamfilters overslaan, u regels voor e-mailstroom (ook wel transportregels genoemd) maken om de berichten te identificeren en het spamvertrouwensniveau (SCL) in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="1b9ff-107">Zie [Spam vertrouwensniveau (SCL) in Office 365 voor](spam-confidence-levels.md)meer informatie over de SCL.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-107">For more information about the SCL, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1b9ff-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="1b9ff-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1b9ff-109">U moet machtigingen in Exchange Online krijgen toegewezen voordat u deze procedures uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="1b9ff-110">U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer**en **Records Management.**</span><span class="sxs-lookup"><span data-stu-id="1b9ff-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="1b9ff-111">Zie [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="1b9ff-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="1b9ff-112">Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)als u de EAC in Exchange Online wilt openen.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="1b9ff-113">Zie [Regels voor e-mailstroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor meer informatie over regels voor e-mailstromen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1b9ff-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="1b9ff-114">De EAC gebruiken om een e-mailstroomregel te maken die de SCL van een bericht instelt</span><span class="sxs-lookup"><span data-stu-id="1b9ff-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="1b9ff-115">Ga in de EAC naar **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="1b9ff-116">Klik **op** ![](../../media/ITPro-EAC-AddIcon.png) Pictogram Toevoegen toevoegen en selecteer **vervolgens Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="1b9ff-117">Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="1b9ff-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="1b9ff-118">**Naam:** Voer een unieke, beschrijvende naam voor de regel in.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="1b9ff-119">Klik **op Meer opties**.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-119">Click **More Options**.</span></span>

   - <span data-ttu-id="1b9ff-120">**Pas deze regel toe als**: Selecteer een of meer voorwaarden om berichten te identificeren.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="1b9ff-121">Zie [Voorwaarden en uitzonderingen (predicaten) e-mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="1b9ff-122">**Ga als volgt**te werk: Selecteer **De eigenschappen** \> van het bericht **wijzigen stel het spamvertrouwensniveau (SCL) in.**</span><span class="sxs-lookup"><span data-stu-id="1b9ff-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="1b9ff-123">Configureer in het dialoogvenster **SCL opgeven** dat wordt weergegeven een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="1b9ff-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="1b9ff-124">**Spamfiltering omzeilen:** Hiermee stelt u de SCL in op -1, wat betekent dat de berichten spamfilters overslaan.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-124">**Bypass spam filtering**: This sets the SCL to -1, which means the messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="1b9ff-125">Wees zeer voorzichtig met het toestaan van berichten om spam filtering overslaan.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="1b9ff-126">Aanvallers kunnen dit beveiligingslek gebruiken om phishing en andere schadelijke berichten naar uw organisatie te verzenden.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="1b9ff-127">De regels voor e-mailstroom vereisen meer dan alleen het e-mailadres of domein van de afzender.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="1b9ff-128">Zie [Lijsten met veilige afzenders maken in Office 365](create-safe-sender-lists-in-office-365.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-128">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="1b9ff-129">**0 tot 4**: Het bericht wordt verzonden via spamfiltering voor extra verwerking.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="1b9ff-130">**5 of 6**: Het bericht is gemarkeerd als **Spam**.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="1b9ff-131">De actie die u hebt **Spam** ingesteld voor spamfiltervonnissen in uw antispambeleid, wordt toegepast op het bericht (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).**</span><span class="sxs-lookup"><span data-stu-id="1b9ff-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="1b9ff-132">**7 tot 9**: Het bericht is gemarkeerd als **High confidence spam**.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="1b9ff-133">De actie die u hebt geconfigureerd voor spamfiltervonnissen met **een hoog vertrouwen** in uw antispambeleid, wordt toegepast op het bericht (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**</span><span class="sxs-lookup"><span data-stu-id="1b9ff-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="1b9ff-134">Geef eventuele extra eigenschappen op die u voor de regel wilt hebben.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="1b9ff-135">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1b9ff-136">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="1b9ff-136">How do you know this worked?</span></span>

<span data-ttu-id="1b9ff-137">Als u wilt controleren of deze procedure correct werkt, stuurt u een e-mailbericht naar iemand binnen uw organisatie en controleert u of de actie die op het bericht is uitgevoerd, zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="1b9ff-138">Als u bijvoorbeeld **het spamvertrouwensniveau (SCL) instelt** op **Het filteren van spam omzeilen,** moet het bericht naar het postvak IN van de opgegeven ontvanger worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="1b9ff-139">Als u **echter het spamvertrouwensniveau (SCL) instelt** op **9**en de **spamactie met veel vertrouwen** voor uw toepasselijke inhoudsfilterbeleid is om het bericht naar de map Ongewenste e-mail te verplaatsen, moet het bericht naar de map Ongewenste e-mail van de opgegeven ontvanger worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="1b9ff-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
