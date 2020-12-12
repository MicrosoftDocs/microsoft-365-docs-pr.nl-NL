---
title: Regels voor e-mail stroom gebruiken voor de SCL in berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Informatie over het maken van een e-mail stroom regels (transportregels) om berichten te identificeren en het betrouwbaarheidsniveau (spam niveau) van berichten in Exchange Online Protection in te stellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 447333eb968ba7d91a1673c57b11afdb16b90469
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659835"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="d35dc-103">De regels voor de e-mail stroom gebruiken voor het instellen van het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) in berichten in EOP</span><span class="sxs-lookup"><span data-stu-id="d35dc-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d35dc-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP-organisaties zonder Exchange Online-postvakken), EOP maakt gebruik van Antispambeleid (ook wel spamfilter beleid of inhouds filter beleid) om inkomende berichten voor spam te scannen.</span><span class="sxs-lookup"><span data-stu-id="d35dc-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="d35dc-105">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d35dc-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d35dc-106">Als u bepaalde berichten wilt markeren als spam voordat ze worden gescand via spam filteren of berichten markeren zodat ze spam filteren, kunt u een e-mail stroom regels (ook wel de zogenaamde transportregels) maken om de berichten te identificeren en het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) in te stellen.</span><span class="sxs-lookup"><span data-stu-id="d35dc-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="d35dc-107">Zie voor meer informatie over het SCL [spam niveau (SCL) in EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d35dc-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d35dc-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d35dc-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d35dc-109">Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor Exchange Online of Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="d35dc-109">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="d35dc-110">Specifiek hebt u de rol van **transport regels** nodig, dat is toegewezen aan **Organisatiebeheer**, **nalevings beheer** (globale beheerders) en rollen groepen voor **recordbeheer** .</span><span class="sxs-lookup"><span data-stu-id="d35dc-110">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="d35dc-111">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="d35dc-111">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="d35dc-112">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d35dc-112">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="d35dc-113">Machtigingen in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="d35dc-113">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="d35dc-114">Werken met de lijst met wijzigingen in de lijst met leden van rollen groepen</span><span class="sxs-lookup"><span data-stu-id="d35dc-114">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="d35dc-115">Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)om het SBV te openen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d35dc-115">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="d35dc-116">Als u het Exchange-Beheercentrum in standalone EOP wilt openen, raadpleegt u [Exchange Admin Center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d35dc-116">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="d35dc-117">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d35dc-117">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d35dc-118">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d35dc-118">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d35dc-119">Zie voor meer informatie over regels voor e-mail stroom in Exchange Online en Exchange Online Protection Zie [regels voor e-mail stroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="d35dc-119">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="d35dc-120">Het Exchange-Beheercentrum gebruiken om een e-mail stroom regel te maken waarmee de SCL van een bericht wordt ingesteld</span><span class="sxs-lookup"><span data-stu-id="d35dc-120">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="d35dc-121">Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> .</span><span class="sxs-lookup"><span data-stu-id="d35dc-121">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d35dc-122">Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer vervolgens **een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="d35dc-122">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="d35dc-123">Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="d35dc-123">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d35dc-124">**Naam**: Typ een unieke, beschrijvende naam voor de regel.</span><span class="sxs-lookup"><span data-stu-id="d35dc-124">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="d35dc-125">Klik op **meer opties**.</span><span class="sxs-lookup"><span data-stu-id="d35dc-125">Click **More Options**.</span></span>

   - <span data-ttu-id="d35dc-126">**Deze regel toepassen als**: Selecteer een of meer voorwaarden voor het identificeren van berichten.</span><span class="sxs-lookup"><span data-stu-id="d35dc-126">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="d35dc-127">Zie voor meer informatie de [voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="d35dc-127">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="d35dc-128">**Ga als volgt** te werk: opties voor het wijzigen van het **bericht** is \> **het betrouwbaarheidsniveau van spam (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="d35dc-128">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="d35dc-129">In het dialoogvenster **SCL opgeven** dat wordt weergegeven, configureert u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d35dc-129">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="d35dc-130">**Spam filteren negeren**: de berichten worden in spam filteren overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d35dc-130">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="d35dc-131">Wees zeer voorzichtig met het toestaan van berichten om spam te filteren.</span><span class="sxs-lookup"><span data-stu-id="d35dc-131">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="d35dc-132">Kwaadwillenden kunnen dit beveiligingslek gebruiken om phishingberichten en andere schadelijke berichten te verzenden naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d35dc-132">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="d35dc-133">Voor de regels voor de e-mail stroom zijn er meer dan alleen het e-mailadres of domein van de afzender vereist.</span><span class="sxs-lookup"><span data-stu-id="d35dc-133">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="d35dc-134">Zie voor meer informatie [lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d35dc-134">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="d35dc-135">**0 t**/m 4: het bericht wordt via spam filteren verzonden voor verdere verwerking.</span><span class="sxs-lookup"><span data-stu-id="d35dc-135">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="d35dc-136">**5 of 6**: het bericht is gemarkeerd als **spam**.</span><span class="sxs-lookup"><span data-stu-id="d35dc-136">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="d35dc-137">De actie die u hebt geconfigureerd voor het filteren van **ongewenste e-mail** Verdicts in uw Antispambeleid op het bericht (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="d35dc-137">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="d35dc-138">**7 en 9**: het bericht is gemarkeerd als **spam van hoge betrouwbaarheid**.</span><span class="sxs-lookup"><span data-stu-id="d35dc-138">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="d35dc-139">De actie die u hebt geconfigureerd voor het filteren van **ongewenste e-mail** in Verdicts in uw antispambeleid wordt toegepast op het bericht (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="d35dc-139">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="d35dc-140">Geef de gewenste extra eigenschappen voor de regel op.</span><span class="sxs-lookup"><span data-stu-id="d35dc-140">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="d35dc-141">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d35dc-141">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d35dc-142">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="d35dc-142">How do you know this worked?</span></span>

<span data-ttu-id="d35dc-143">Ga als volgt te werk om te controleren of deze procedure goed werkt: een e-mailbericht naar iemand binnen uw organisatie verzenden en controleren of de actie die op het bericht is uitgevoerd, is zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="d35dc-143">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="d35dc-144">Als u bijvoorbeeld **het spam niveau (SCL) instelt** om **spam te filteren**, moet het bericht naar het postvak in van de opgegeven ontvanger worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="d35dc-144">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="d35dc-145">Als u echter **het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) instelt** op **9** en de actie **spam hoge betrouwbaarheid** voor uw toepasselijke Antispambeleid is het verplaatsen van het bericht naar de map Ongewenste e-mail, dan moet het bericht worden verzonden naar de map Ongewenste e-mail van de opgegeven geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="d35dc-145">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
