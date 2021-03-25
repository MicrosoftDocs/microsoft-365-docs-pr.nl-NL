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
description: Beheerders kunnen meer informatie krijgen over de verschillen tussen ongewenste e-mail (spam) en bulk-e-mail (grijze e-mail) in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204937"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="2aa7b-103">Wat is het verschil tussen ongewenste e-mail en bulk-e-mail in EOP?</span><span class="sxs-lookup"><span data-stu-id="2aa7b-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2aa7b-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2aa7b-104">**Applies to**</span></span>
- [<span data-ttu-id="2aa7b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2aa7b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2aa7b-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2aa7b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2aa7b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2aa7b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2aa7b-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, vragen klanten soms: 'Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?'</span><span class="sxs-lookup"><span data-stu-id="2aa7b-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="2aa7b-109">In dit onderwerp wordt het verschil uitgelegd en worden de besturingselementen beschreven die beschikbaar zijn in EOP.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="2aa7b-110">**Ongewenste e-mail** is spam, wat ongevraagde en universeel ongewenste berichten zijn (indien correct geïdentificeerd).</span><span class="sxs-lookup"><span data-stu-id="2aa7b-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="2aa7b-111">Standaard wordt spam door de EOP afgewezen op basis van de reputatie van de bron-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="2aa7b-112">Als een bericht de bron-IP-inspectie doorstaat, wordt het verzonden naar spamfilters.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="2aa7b-113">Als het bericht is geclassificeerd als spam door spamfilters, wordt het bericht (standaard) bezorgd bij de beoogde geadresseerden en verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="2aa7b-114">U kunt de acties configureren voor het filteren van spam.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="2aa7b-115">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="2aa7b-116">Als u het niet eens bent met de uitspraak over spamfilters, kunt u berichten die u als spam of niet-spam beschouwt op verschillende manieren aan Microsoft rapporteren, zoals beschreven in Berichten en bestanden rapporteren aan [Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="2aa7b-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="2aa7b-117">**Bulk-e-mail** (ook _wel grijze e-mail genoemd)_ is moeilijker te classificeren.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="2aa7b-118">Terwijl spam een constante bedreiging is, is bulk-e-mail vaak een een-tijdsadvertenties of marketingberichten.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="2aa7b-119">Sommige gebruikers willen bulk-e-mailberichten (en in feite hebben ze zich bewust aangemeld om ze te ontvangen), terwijl andere gebruikers bulk-e-mail beschouwen als spam.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="2aa7b-120">Sommige gebruikers willen bijvoorbeeld reclameberichten ontvangen van de Contoso Corporation of uitnodigingen voor een aanstaande conferentie over cyberbeveiliging, terwijl andere gebruikers deze berichten beschouwen als spam.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="2aa7b-121">Zie Bulk [complaint level (BCL) in EOP voor](bulk-complaint-level-values.md)meer informatie over de manier waarop bulk-e-mail wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="2aa7b-122">Bulk-e-mail beheren</span><span class="sxs-lookup"><span data-stu-id="2aa7b-122">How to manage bulk email</span></span>

<span data-ttu-id="2aa7b-123">Vanwege de gemengde reactie op bulk-e-mail is er geen universele richtlijn die van toepassing is op elke organisatie.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="2aa7b-124">Antispam polices hebben een standaard BCL-drempel die wordt gebruikt om bulk-e-mail te identificeren als spam.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="2aa7b-125">Beheerders kunnen de drempel verhogen of verlagen.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="2aa7b-126">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="2aa7b-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="2aa7b-127">[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2aa7b-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="2aa7b-128">EOP-antispambeleidsinstellingen</span><span class="sxs-lookup"><span data-stu-id="2aa7b-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

<span data-ttu-id="2aa7b-129">Een andere optie die u gemakkelijk kunt over het hoofd zien: als een gebruiker klaagt over het ontvangen van bulk-e-mail, maar de berichten afkomstig zijn van betrouwbare afzenders die spamfilters in EOP doorgeven, laat u de gebruiker controleren op een optie voor afmelden in het bulksgewijs e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="2aa7b-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
