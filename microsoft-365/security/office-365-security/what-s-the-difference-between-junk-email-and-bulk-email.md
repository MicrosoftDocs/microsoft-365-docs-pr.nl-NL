---
title: Wat is het verschil tussen ongewenste e-mail en bulkmail?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: In dit onderwerp wordt het verschil uitgelegd tussen ongewenste e-mail (spam) en bulke-mail en de bijbehorende besturingselementen in Office 365.
ms.openlocfilehash: 15ca00b007ef0b8470e1b30608a695a90bd638b2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630831"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="cff90-103">Wat is het verschil tussen ongewenste e-mail en bulkmail?</span><span class="sxs-lookup"><span data-stu-id="cff90-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="cff90-104">Microsoft 365-klanten met postvakken in Exchange Online- of zelfstandige Exchange Online Protection (EOP)-klanten zonder Exchange Online-postvakken vragen soms: "wat is het verschil tussen ongewenste e-mail en bulke-mail?"</span><span class="sxs-lookup"><span data-stu-id="cff90-104">Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="cff90-105">In dit onderwerp wordt het verschil uitgelegd en worden de besturingselementen beschreven die beschikbaar zijn in EOP.</span><span class="sxs-lookup"><span data-stu-id="cff90-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="cff90-106">**Ongewenste e-mail** is spam, die ongevraagde en universeel ongewenste berichten (wanneer correct geïdentificeerd).</span><span class="sxs-lookup"><span data-stu-id="cff90-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="cff90-107">Standaard wijst de EOP spam af op basis van de reputatie van de bron-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="cff90-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="cff90-108">Als een bericht de IP-inspectie van de bron doorgeeft, wordt het verzonden naar spamfiltering.</span><span class="sxs-lookup"><span data-stu-id="cff90-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="cff90-109">Als het bericht wordt geclassificeerd als spam door spamfiltering, wordt het bericht (standaard) geleverd aan de beoogde ontvangers en verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="cff90-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="cff90-110">U de acties configureren die u wilt uitvoeren op spamfilteringsvonnissen.</span><span class="sxs-lookup"><span data-stu-id="cff90-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="cff90-111">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="cff90-111">For instructions, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="cff90-112">Als u het niet eens bent met het spamfiltervonnis, u berichten die u als spam of niet-spam beschouwt op verschillende manieren aan Microsoft rapporteren, zoals beschreven in [Berichten en bestanden rapporteren aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="cff90-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="cff90-113">**Bulk e-mail** (ook wel bekend als _grijze e-mail),_ is moeilijker te classificeren.</span><span class="sxs-lookup"><span data-stu-id="cff90-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="cff90-114">Terwijl spam is een constante bedreiging, bulk e-mail is vaak eenmalige advertenties of marketing berichten.</span><span class="sxs-lookup"><span data-stu-id="cff90-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="cff90-115">Sommige gebruikers willen bulk e-mailberichten (en in feite, ze hebben bewust aangemeld om ze te ontvangen), terwijl andere gebruikers overwegen bulk e-mail te zijn spam.</span><span class="sxs-lookup"><span data-stu-id="cff90-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="cff90-116">Sommige gebruikers willen bijvoorbeeld advertentieberichten ontvangen van de Contoso Corporation of uitnodigingen voor een komende conferentie over cyberbeveiliging, terwijl andere gebruikers dezelfde berichten als spam beschouwen.</span><span class="sxs-lookup"><span data-stu-id="cff90-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="cff90-117">Zie [Bulkklachtenniveau (BCL) in Office 365 voor](bulk-complaint-level-values.md)meer informatie over de manier waarop bulke-mail wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="cff90-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="cff90-118">Bulke-mail beheren</span><span class="sxs-lookup"><span data-stu-id="cff90-118">How to manage bulk email</span></span>

<span data-ttu-id="cff90-119">Vanwege de gemengde reactie op bulk e-mail, is er geen universele begeleiding die van toepassing is op elke organisatie.</span><span class="sxs-lookup"><span data-stu-id="cff90-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="cff90-120">Anti-spam politie heeft een standaard BCL drempel die wordt gebruikt om bulk e-mail te identificeren als spam.</span><span class="sxs-lookup"><span data-stu-id="cff90-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="cff90-121">Beheerders kunnen de drempelwaarde verhogen of verlagen.</span><span class="sxs-lookup"><span data-stu-id="cff90-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="cff90-122">Lees de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="cff90-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="cff90-123">[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cff90-123">[Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="cff90-124">EOP-beleidsinstellingen voor spam</span><span class="sxs-lookup"><span data-stu-id="cff90-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="cff90-125">Een andere optie die gemakkelijk over het hoofd te zien: als een gebruiker klaagt over het ontvangen van bulk e-mail, maar de berichten zijn van gerenommeerde afzenders die spam filtering passeren in EOP, hebben de gebruiker controleren op een uitschrijven optie in de bulk e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="cff90-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
