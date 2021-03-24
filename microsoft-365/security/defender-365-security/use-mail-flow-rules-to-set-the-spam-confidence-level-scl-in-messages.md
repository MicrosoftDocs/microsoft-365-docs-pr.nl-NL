---
title: E-mailstroomregels gebruiken voor de SCL in berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Informatie over het maken van regels voor e-mailstroom (transportregels) om berichten te identificeren en het betrouwbaarheidsniveau voor spam (SCL) van berichten in Exchange Online Protection in te stellen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 795347046342ea17870e7758a6327facf51315a4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057209"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="930e4-103">Regels voor e-mailstroom gebruiken om het betrouwbaarheidsniveau voor spam (SCL) in te stellen in berichten in EOP</span><span class="sxs-lookup"><span data-stu-id="930e4-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="930e4-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="930e4-104">**Applies to**</span></span>
- [<span data-ttu-id="930e4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="930e4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="930e4-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="930e4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="930e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="930e4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="930e4-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, gebruikt EOP antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om binnenkomende berichten te scannen op spam.</span><span class="sxs-lookup"><span data-stu-id="930e4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="930e4-109">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="930e4-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="930e4-110">Als u specifieke berichten wilt markeren als spam voordat ze zelfs worden gescand door spamfilters, of berichten markeren zodat ze spamfilters overslaan, kunt u regels voor e-mailstroom (ook wel transportregels genoemd) maken om de berichten te identificeren en het betrouwbaarheidsniveau voor spam (SCL) in te stellen.</span><span class="sxs-lookup"><span data-stu-id="930e4-110">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="930e4-111">Zie Betrouwbaarheidsniveau spam [(SCL) in EOP voor meer informatie over de SCL.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="930e4-111">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="930e4-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="930e4-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="930e4-113">U moet machtigingen krijgen toegewezen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="930e4-113">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="930e4-114">U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="930e4-114">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="930e4-115">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="930e4-115">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="930e4-116">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="930e4-116">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="930e4-117">Machtigingen in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="930e4-117">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="930e4-118">De lijst met leden in rollengroepen wijzigen met het EAC</span><span class="sxs-lookup"><span data-stu-id="930e4-118">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="930e4-119">Zie [Exchange-beheercentrum in Exchange Online](/Exchange/exchange-admin-center)om het EAC in Exchange Online te openen.</span><span class="sxs-lookup"><span data-stu-id="930e4-119">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="930e4-120">Zie [Exchange-beheercentrum in](exchange-admin-center-in-exchange-online-protection-eop.md)zelfstandige EOP om de EAC in zelfstandige EOP te openen.</span><span class="sxs-lookup"><span data-stu-id="930e4-120">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="930e4-121">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="930e4-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="930e4-122">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="930e4-122">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="930e4-123">Zie Regels voor e-mailstroom [(transportregels) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor meer informatie over e-mailstroomregels in Exchange Online en Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="930e4-123">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="930e4-124">De EAC gebruiken om een e-mailstroomregel te maken die de SCL van een bericht in stelt</span><span class="sxs-lookup"><span data-stu-id="930e4-124">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="930e4-125">Ga in het EAC naar **E-mailstroomregels.** \> </span><span class="sxs-lookup"><span data-stu-id="930e4-125">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="930e4-126">Klik **op Pictogram** Toevoegen toevoegen en selecteer vervolgens Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="930e4-126">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="930e4-127">Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="930e4-127">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="930e4-128">**Naam:** Voer een unieke, beschrijvende naam in voor de regel.</span><span class="sxs-lookup"><span data-stu-id="930e4-128">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="930e4-129">Klik **op Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="930e4-129">Click **More Options**.</span></span>

   - <span data-ttu-id="930e4-130">**Pas deze regel toe als**: Selecteer een of meer voorwaarden om berichten te identificeren.</span><span class="sxs-lookup"><span data-stu-id="930e4-130">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="930e4-131">Zie Voorwaarden en uitzonderingen voor [e-mailstroomregelen (predicaten) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="930e4-131">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="930e4-132">**Ga als volgt te** werk: Selecteer **De eigenschappen van het bericht wijzigen** om \> **het betrouwbaarheidsniveau voor spam (SCL) in te stellen.**</span><span class="sxs-lookup"><span data-stu-id="930e4-132">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="930e4-133">Configureer een van de volgende waarden in het dialoogvenster **SCL** opgeven dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="930e4-133">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="930e4-134">**Spamfilters overslaan:** de berichten worden overgeslagen op spamfilters.</span><span class="sxs-lookup"><span data-stu-id="930e4-134">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="930e4-135">Wees erg voorzichtig met het toestaan dat berichten spamfilters overslaan.</span><span class="sxs-lookup"><span data-stu-id="930e4-135">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="930e4-136">Aanvallers kunnen dit beveiligingsprobleem gebruiken om phishing en andere schadelijke berichten naar uw organisatie te verzenden.</span><span class="sxs-lookup"><span data-stu-id="930e4-136">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="930e4-137">Voor de regels voor de e-mailstroom is meer nodig dan alleen het e-mailadres of domein van de afzender.</span><span class="sxs-lookup"><span data-stu-id="930e4-137">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="930e4-138">Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="930e4-138">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="930e4-139">**0 tot en met 4**: Het bericht wordt verzonden via spamfilters voor aanvullende verwerking.</span><span class="sxs-lookup"><span data-stu-id="930e4-139">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="930e4-140">**5 of 6**: Het bericht is gemarkeerd als **Spam.**</span><span class="sxs-lookup"><span data-stu-id="930e4-140">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="930e4-141">De actie die u hebt  geconfigureerd voor spamfilters in uw antispambeleid, wordt toegepast op het bericht (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail).**</span><span class="sxs-lookup"><span data-stu-id="930e4-141">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="930e4-142">**7 tot en met 9**: Het bericht is gemarkeerd als **Spam met hoog vertrouwen.**</span><span class="sxs-lookup"><span data-stu-id="930e4-142">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="930e4-143">De actie die u hebt  geconfigureerd voor het filteren van spam met hoge betrouwbaarheid in uw antispambeleid, wordt toegepast op het bericht (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**</span><span class="sxs-lookup"><span data-stu-id="930e4-143">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="930e4-144">Geef eventuele extra eigenschappen op die u voor de regel wilt hebben.</span><span class="sxs-lookup"><span data-stu-id="930e4-144">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="930e4-145">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="930e4-145">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="930e4-146">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="930e4-146">How do you know this worked?</span></span>

<span data-ttu-id="930e4-147">Als u wilt controleren of deze procedure correct werkt, verzendt u een e-mailbericht naar iemand binnen uw organisatie en controleert u of de actie die op het bericht is uitgevoerd, is zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="930e4-147">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="930e4-148">Als u bijvoorbeeld het **betrouwbaarheidsniveau voor spam (SCL)** in stelt op **Spamfilters** omzeilen, moet het bericht worden verzonden naar het Postvak IN van de opgegeven geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="930e4-148">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="930e4-149">Als u echter het betrouwbaarheidsniveau voor ongewenste e-mail  **(SCL)** in stelt op **9** en u het bericht wilt verplaatsen naar de map Ongewenste e-mail, wordt het bericht naar de map Ongewenste e-mail verzonden naar de map Ongewenste e-mail van de opgegeven geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="930e4-149">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>