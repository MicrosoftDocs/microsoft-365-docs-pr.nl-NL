---
title: Controle door beheerder voor gerapporteerde berichten
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Informatie over het controleren van berichten die worden gerapporteerd en feedback geven aan uw gebruikers.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a9fa6c890f0fa6098a2bb712f79ab82fc1edb68b
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108557"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="8aa64-103">Controle door beheerder voor gerapporteerde berichten</span><span class="sxs-lookup"><span data-stu-id="8aa64-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="8aa64-104">De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="8aa64-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8aa64-105">Dit document is alleen beschikbaar voor evaluatie- en verkenningsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="8aa64-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="8aa64-106">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="8aa64-106">**Applies to**</span></span>
- [<span data-ttu-id="8aa64-107">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8aa64-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8aa64-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8aa64-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8aa64-109">In Microsoft 365 organisaties met Exchange Online postvakken en Microsoft Defender voor Office 365, kunnen beheerders nu sjablonenberichten terugsturen naar eindgebruikers nadat ze gerapporteerde berichten hebben beoordeeld.</span><span class="sxs-lookup"><span data-stu-id="8aa64-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="8aa64-110">Dit kan worden aangepast voor uw organisatie en op basis van de uitspraak van uw beheerder.</span><span class="sxs-lookup"><span data-stu-id="8aa64-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="8aa64-111">Deze functie is ontworpen om feedback te geven aan uw gebruikers, maar wijzigt de uitspraken van berichten in het systeem niet.</span><span class="sxs-lookup"><span data-stu-id="8aa64-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="8aa64-112">Als u Microsoft wilt helpen bij het bijwerken en verbeteren van de filters, moet u berichten verzenden voor analyse met [beheerdersinzending.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="8aa64-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="8aa64-113">U kunt alleen gebruikers van controleresultaten markeren en op de hoogte stellen als het bericht is gerapporteerd als een onwaar positief of [onwaar negatief.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="8aa64-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8aa64-114">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="8aa64-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8aa64-115">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="8aa64-115">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="8aa64-116">Als u rechtstreeks naar de pagina **Inzendingen wilt** gaan, gebruikt u <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="8aa64-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="8aa64-117">Als u de configuratie voor gebruikersinzendingen wilt wijzigen, moet u lid zijn van een van de volgende rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="8aa64-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="8aa64-118">Organisatiebeheer of Beveiligingsbeheerder in de [Microsoft 365 Defender portal.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="8aa64-118">Organization Management or Security Administrator in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="8aa64-119">Organisatiebeheer in [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="8aa64-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="8aa64-120">U hebt ook toegang nodig tot Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8aa64-120">You'll also need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="8aa64-121">Als het account dat u probeert te gebruiken geen toegang heeft tot Exchange Online PowerShell, krijgt u een foutmelding met de vermelding Een e-mailadres *opgeven in uw domein.*</span><span class="sxs-lookup"><span data-stu-id="8aa64-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="8aa64-122">Zie de volgende onderwerpen voor meer informatie over het in- of uitschakelen van toegang tot Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8aa64-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="8aa64-123">Toegang tot powershell in- Exchange Online uitschakelen</span><span class="sxs-lookup"><span data-stu-id="8aa64-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="8aa64-124">Clienttoegangsregels in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8aa64-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="8aa64-125">De berichten configureren die worden gebruikt om gebruikers op de hoogte te stellen</span><span class="sxs-lookup"><span data-stu-id="8aa64-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="8aa64-126">Ga in Microsoft 365 Defender portal naar E-mail & **samenwerkingsbeleid** & pagina Regels bedreigingsbeleid Pagina Overige sectie \>  \>  \>  \> **Gebruiker gerapporteerde berichtinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="8aa64-126">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="8aa64-127">Als  u op de pagina Gebruikersinzendingen de weergavenaam van de afzender wilt opgeven, gaat u  naar Het **Office 365 e-mailadres** opgeven dat u wilt gebruiken als afzender onder de sectie E-mailmeldingen voor beheerdersbeoordelingsresultaten en voert u de naam in die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8aa64-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="8aa64-128">Dit is het e-mailadres dat zichtbaar is in Outlook waar de antwoorden naartoe gaan.</span><span class="sxs-lookup"><span data-stu-id="8aa64-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="8aa64-129">Als u een van de sjablonen wilt aanpassen, klikt u **op E-mailmelding aanpassen.**</span><span class="sxs-lookup"><span data-stu-id="8aa64-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="8aa64-130">In deze flyout kunt u alleen de volgende opties aanpassen:</span><span class="sxs-lookup"><span data-stu-id="8aa64-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="8aa64-131">Phishing</span><span class="sxs-lookup"><span data-stu-id="8aa64-131">Phishing</span></span>
    - <span data-ttu-id="8aa64-132">Ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="8aa64-132">Junk</span></span>
    - <span data-ttu-id="8aa64-133">Geen bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="8aa64-133">No threats found</span></span>
    - <span data-ttu-id="8aa64-134">Bewustmakingstraining</span><span class="sxs-lookup"><span data-stu-id="8aa64-134">Awareness training</span></span>
    - <span data-ttu-id="8aa64-135">Voettekst</span><span class="sxs-lookup"><span data-stu-id="8aa64-135">Footer</span></span>

4. <span data-ttu-id="8aa64-136">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="8aa64-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="8aa64-137">Als u deze waarden wilt verwijderen, klikt **u op Verwijderen** op de pagina Gebruikersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="8aa64-137">To clear these values, click **Discard** on the User submissions page.</span></span>
