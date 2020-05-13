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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over de verschillen tussen ongewenste e-mail (spam) en bulke-mail (grijze e-mail) in Exchange Online Protection (EOP).
ms.openlocfilehash: 6936028aa7bda538f0e49429d22f28c7a78cdb36
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208450"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="a5b03-103">Wat is het verschil tussen ongewenste e-mail en bulke-mail in EOP?</span><span class="sxs-lookup"><span data-stu-id="a5b03-103">What's the difference between junk email and bulk email in EOP?</span></span>

<span data-ttu-id="a5b03-104">In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken vragen klanten soms: "wat is het verschil tussen ongewenste e-mail en bulke-mail?"</span><span class="sxs-lookup"><span data-stu-id="a5b03-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="a5b03-105">In dit onderwerp wordt het verschil uitgelegd en worden de besturingselementen beschreven die beschikbaar zijn in EOP.</span><span class="sxs-lookup"><span data-stu-id="a5b03-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="a5b03-106">**Ongewenste e-mail** is spam, die ongevraagde en universeel ongewenste berichten (wanneer correct geïdentificeerd).</span><span class="sxs-lookup"><span data-stu-id="a5b03-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="a5b03-107">Standaard wijst de EOP spam af op basis van de reputatie van de bron-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="a5b03-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="a5b03-108">Als een bericht de IP-inspectie van de bron doorgeeft, wordt het verzonden naar spamfiltering.</span><span class="sxs-lookup"><span data-stu-id="a5b03-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="a5b03-109">Als het bericht wordt geclassificeerd als spam door spamfiltering, wordt het bericht (standaard) geleverd aan de beoogde ontvangers en verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="a5b03-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="a5b03-110">U de acties configureren die u wilt uitvoeren op spamfilteringsvonnissen.</span><span class="sxs-lookup"><span data-stu-id="a5b03-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="a5b03-111">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="a5b03-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="a5b03-112">Als u het niet eens bent met het spamfiltervonnis, u berichten die u als spam of niet-spam beschouwt op verschillende manieren aan Microsoft rapporteren, zoals beschreven in [Berichten en bestanden rapporteren aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="a5b03-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="a5b03-113">**Bulk e-mail** (ook wel bekend als _grijze e-mail),_ is moeilijker te classificeren.</span><span class="sxs-lookup"><span data-stu-id="a5b03-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="a5b03-114">Terwijl spam is een constante bedreiging, bulk e-mail is vaak eenmalige advertenties of marketing berichten.</span><span class="sxs-lookup"><span data-stu-id="a5b03-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="a5b03-115">Sommige gebruikers willen bulk e-mailberichten (en in feite, ze hebben bewust aangemeld om ze te ontvangen), terwijl andere gebruikers overwegen bulk e-mail te zijn spam.</span><span class="sxs-lookup"><span data-stu-id="a5b03-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="a5b03-116">Sommige gebruikers willen bijvoorbeeld advertentieberichten ontvangen van de Contoso Corporation of uitnodigingen voor een komende conferentie over cyberbeveiliging, terwijl andere gebruikers dezelfde berichten als spam beschouwen.</span><span class="sxs-lookup"><span data-stu-id="a5b03-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="a5b03-117">Zie [Bulk klachtenniveau (BCL) in EOP](bulk-complaint-level-values.md)voor meer informatie over hoe bulke-mail wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="a5b03-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="a5b03-118">Bulke-mail beheren</span><span class="sxs-lookup"><span data-stu-id="a5b03-118">How to manage bulk email</span></span>

<span data-ttu-id="a5b03-119">Vanwege de gemengde reactie op bulk e-mail, is er geen universele begeleiding die van toepassing is op elke organisatie.</span><span class="sxs-lookup"><span data-stu-id="a5b03-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="a5b03-120">Anti-spam politie heeft een standaard BCL drempel die wordt gebruikt om bulk e-mail te identificeren als spam.</span><span class="sxs-lookup"><span data-stu-id="a5b03-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="a5b03-121">Beheerders kunnen de drempelwaarde verhogen of verlagen.</span><span class="sxs-lookup"><span data-stu-id="a5b03-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="a5b03-122">Lees de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="a5b03-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="a5b03-123">[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a5b03-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="a5b03-124">EOP-beleidsinstellingen voor spam</span><span class="sxs-lookup"><span data-stu-id="a5b03-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="a5b03-125">Een andere optie die gemakkelijk over het hoofd te zien: als een gebruiker klaagt over het ontvangen van bulk e-mail, maar de berichten zijn van gerenommeerde afzenders die spam filtering passeren in EOP, hebben de gebruiker controleren op een uitschrijven optie in de bulk e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="a5b03-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
