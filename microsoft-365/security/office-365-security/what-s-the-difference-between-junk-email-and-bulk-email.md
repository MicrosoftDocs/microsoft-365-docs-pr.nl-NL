---
title: Wat is &apos; het verschil tussen ongewenste e-mail en bulk-e-mail?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie vinden over de verschillen tussen ongewenste e-mail (spam) en bulk-e-mail (grijze e-mail) in Exchange Online Protection (EOP).
ms.openlocfilehash: 17e6223175013678f389c0d7624cc4e4f4476f98
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826727"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="9f2aa-103">Wat is het verschil tussen ongewenste e-mail en bulk-e-mail in EOP?</span><span class="sxs-lookup"><span data-stu-id="9f2aa-103">What's the difference between junk email and bulk email in EOP?</span></span>

<span data-ttu-id="9f2aa-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken kunnen klanten soms het volgende vragen: ' wat is het verschil tussen ongewenste e-mail en bulk-e-mail? '.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="9f2aa-105">In dit onderwerp wordt het verschil uitgelegd en worden de beschikbare besturingselementen beschreven in EOP.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="9f2aa-106">**Ongewenste e-mail** is spam, ongevraagd en universeel ongewenst berichten (bij een juiste identificatie).</span><span class="sxs-lookup"><span data-stu-id="9f2aa-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="9f2aa-107">In de EOP worden de spam standaard genegeerd op basis van de reputatie van de bron-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="9f2aa-108">Als het bericht wordt gecontroleerd via bron-IP-inspectie, wordt het verzonden naar spam filteren.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="9f2aa-109">Als het bericht is geclassificeerd als spam via spamfilters, wordt het bericht (standaard) bezorgd bij de geadresseerden en verplaatst naar de map Ongewenste E-mail.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="9f2aa-110">U kunt de acties configureren die u moet uitvoeren om spam te filteren Verdicts.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="9f2aa-111">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="9f2aa-112">Als u niet akkoord gaat met de spamfilter Verdict, kunt u op verschillende manieren berichten rapporteren die u beschouwt als spam of niet-spam voor Microsoft, zoals beschreven in [berichten en bestanden aan Microsoft rapporteren](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9f2aa-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="9f2aa-113">**Bulk-e-mail** (ook wel _grijze e-mail_genoemd), is moeilijker te classificeren.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="9f2aa-114">Aangezien spam een voortdurende bedreiging vormt, is bulksgewijs e-mailberichten vaak eenmalige advertenties of marketingberichten.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="9f2aa-115">Sommige gebruikers willen bulksgewijs e-mailberichten (en in werkelijkheid hebben ze aangemeld om ze te ontvangen), terwijl andere gebruikers op de hoogte zijn van ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="9f2aa-116">Sommige gebruikers willen bijvoorbeeld advertenties van de Contoso Corporation of uitnodigingen ontvangen voor een toekomstige conferentie over de Cyber-veiligheid, terwijl andere gebruikers deze berichten als spam beschouwen.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="9f2aa-117">Zie voor meer informatie over de manier waarop bulk-e-mail wordt geïdentificeerd de [bulk klachten niveau (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="9f2aa-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="9f2aa-118">Bulk-e-mail beheren</span><span class="sxs-lookup"><span data-stu-id="9f2aa-118">How to manage bulk email</span></span>

<span data-ttu-id="9f2aa-119">Aangezien de gemengde reacties op bulk e-mail niet, is er geen universele richtlijnen die van toepassing zijn op elke organisatie.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="9f2aa-120">Anti spam policies hebben een standaard BCL-drempel die wordt gebruikt voor het identificeren van bulk e-mail als spam.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="9f2aa-121">Beheerders kunnen de drempelwaarden vergroten of verkleinen.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="9f2aa-122">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="9f2aa-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="9f2aa-123">[Antispambeleid te configureren in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9f2aa-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="9f2aa-124">EOP antispam beleidsinstellingen</span><span class="sxs-lookup"><span data-stu-id="9f2aa-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="9f2aa-125">Een andere optie die gemakkelijk te laat overlopen: als een gebruiker een bericht geeft over het ontvangen van bulk-e-mail, maar de berichten afkomstig zijn van goede afzenders die het filteren op ongewenste e-mail doorgeven in EOP, kunt u de gebruiker controleren op een optie voor het afmelden van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="9f2aa-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
