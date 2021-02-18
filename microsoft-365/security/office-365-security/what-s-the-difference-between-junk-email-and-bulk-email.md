---
title: Wat &apos; is het verschil tussen ongewenste e-mail en bulk-e-mail?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen de verschillen tussen ongewenste e-mail (spam) en bulkmail (grijze e-mail) in Exchange Online Protection (EOP) leren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290643"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="ce326-103">Wat is het verschil tussen ongewenste e-mail en bulkmail in EOP?</span><span class="sxs-lookup"><span data-stu-id="ce326-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ce326-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ce326-104">**Applies to**</span></span>
- [<span data-ttu-id="ce326-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ce326-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ce326-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ce326-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ce326-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce326-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ce326-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken vragen klanten soms: 'Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?'</span><span class="sxs-lookup"><span data-stu-id="ce326-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="ce326-109">In dit onderwerp wordt het verschil beschreven en worden de besturingselementen beschreven die beschikbaar zijn in EOP.</span><span class="sxs-lookup"><span data-stu-id="ce326-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="ce326-110">**Ongewenste e-mail** is spam, ongevraagde en universeel ongewenste berichten (indien correct geïdentificeerd).</span><span class="sxs-lookup"><span data-stu-id="ce326-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="ce326-111">Standaard wijst de EOP spam af op basis van de reputatie van de bron-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="ce326-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="ce326-112">Als een bericht de bron-IP-controle doorstaat, wordt het verzonden naar spamfilters.</span><span class="sxs-lookup"><span data-stu-id="ce326-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="ce326-113">Als het bericht door spamfilters als spam wordt geclassificeerd, wordt het bericht (standaard) bezorgd bij de geadresseerden en verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="ce326-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="ce326-114">U kunt de acties zodanig configureren dat ze worden genomen op spamfilters.</span><span class="sxs-lookup"><span data-stu-id="ce326-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="ce326-115">Zie Antispambeleid configureren [in EOP voor instructies.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ce326-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="ce326-116">Als u het niet eens bent met het spamfilter, kunt u berichten die volgens u spam of niet-spam zijn, op verschillende manieren aan Microsoft rapporteren, zoals wordt beschreven in Berichten en bestanden rapporteren [aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ce326-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="ce326-117">**Bulk-e-mail** (ook _wel grijze e-mail genoemd)_ is moeilijker te classificeren.</span><span class="sxs-lookup"><span data-stu-id="ce326-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="ce326-118">Terwijl spam een constante bedreiging is, is bulk-e-mail vaak een eentijdsadvertenties of marketingberichten.</span><span class="sxs-lookup"><span data-stu-id="ce326-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="ce326-119">Sommige gebruikers willen bulk-e-mailberichten (en in feite hebben ze zich opzettelijk aangemeld om ze te ontvangen), terwijl andere gebruikers van mening zijn dat bulk-e-mail spam is.</span><span class="sxs-lookup"><span data-stu-id="ce326-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="ce326-120">Sommige gebruikers willen bijvoorbeeld reclameberichten ontvangen van contoso Corporation of uitnodigingen voor een komende conferentie over cyberbeveiliging, terwijl andere gebruikers deze berichten als spam beschouwen.</span><span class="sxs-lookup"><span data-stu-id="ce326-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="ce326-121">Zie Bulk-klachtniveau [(BCL) in EOP voor](bulk-complaint-level-values.md)meer informatie over hoe bulk-e-mail wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="ce326-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="ce326-122">Bulk-e-mail beheren</span><span class="sxs-lookup"><span data-stu-id="ce326-122">How to manage bulk email</span></span>

<span data-ttu-id="ce326-123">Vanwege een gemengde reactie op bulkmail is er geen universele leidraad die van toepassing is op elke organisatie.</span><span class="sxs-lookup"><span data-stu-id="ce326-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="ce326-124">Antispam beleid heeft een standaard drempelwaarde voor BCL die wordt gebruikt om bulk-e-mail als spam aan te identificeren.</span><span class="sxs-lookup"><span data-stu-id="ce326-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="ce326-125">Beheerders kunnen de drempelwaarde verhogen of verlagen.</span><span class="sxs-lookup"><span data-stu-id="ce326-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="ce326-126">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="ce326-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="ce326-127">[Antispambeleid configureren in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ce326-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="ce326-128">Instellingen voor antispambeleid van EOP</span><span class="sxs-lookup"><span data-stu-id="ce326-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="ce326-129">Een andere optie die u gemakkelijk kunt over het hoofd zien: als een gebruiker over het ontvangen van bulk-e-mail klaagt, maar de berichten afkomstig zijn van betrouwbare afzenders die spamfilters in EOP gebruiken, laat u de gebruiker controleren op een optie voor het afmelden in het bulk-e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="ce326-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
