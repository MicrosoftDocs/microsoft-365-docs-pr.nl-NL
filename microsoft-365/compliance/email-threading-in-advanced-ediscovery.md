---
title: E-mailthreading in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Bij het uitvoeren Advanced eDiscovery een e-mailthreading een e-mailgesprek parseert en elk bericht in verschillende categorieën scheidt.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161533"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="4ba8c-103">E-mailthreading in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4ba8c-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="4ba8c-104">Overweeg een e-mailgesprek dat al een tijdje gaande is.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="4ba8c-105">In de meeste gevallen bevat de laatste e-mail in de thread de inhoud van alle voorgaande e-mailberichten. Als u de laatste e-mail bekijkt, krijgt u een volledige context van het gesprek dat in de thread is gebeurd.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="4ba8c-106">E-mailthreading identificeert dergelijke e-mailberichten, zodat revisoren een deel van de verzamelde documenten kunnen bekijken zonder context te verliezen.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="4ba8c-107">Wat doet e-mailthreading?</span><span class="sxs-lookup"><span data-stu-id="4ba8c-107">What does email threading do?</span></span>

<span data-ttu-id="4ba8c-108">E-mailthreading parseert elke e-mail en deconstrueert deze naar afzonderlijke berichten; elke e-mail is een keten van afzonderlijke berichten.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="4ba8c-109">Vervolgens worden alle e-mailberichten in de revisieset geanalyseerd om te bepalen of een e-mail unieke inhoud heeft of dat de keten volledig in een andere e-mail is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="4ba8c-110">Uiteindelijk zijn e-mailberichten onderverdeeld in vier categorieën:</span><span class="sxs-lookup"><span data-stu-id="4ba8c-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="4ba8c-111">**Inclusief:** het laatste bericht in de e-mail bevat unieke inhoud en de e-mail bevat alle bijlagen die zijn opgenomen in andere e-mailberichten waarvan de inhoud volledig in deze e-mail is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="4ba8c-112">**Inclusief min:** het laatste bericht in de e-mail bevat unieke inhoud, maar de e-mail bevat geen enkele van de bijlagen die zijn opgenomen in andere e-mailberichten waarvan de inhoud volledig in deze e-mail is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="4ba8c-113">**Inclusief exemplaar:** een exacte kopie van een inclusief/inclusief min-e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="4ba8c-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="4ba8c-114">**Geen:** De inhoud van dit e-mailbericht bevat ten minste één e-mailbericht dat is gemarkeerd als inclusief/inclusief min.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="4ba8c-115">Hoe verschilt dit van gesprekken in Outlook?</span><span class="sxs-lookup"><span data-stu-id="4ba8c-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="4ba8c-116">In één oogopslag klinkt dit vergelijkbaar met gespreksgroeperingen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="4ba8c-117">Er zijn echter enkele belangrijke verschillen.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-117">However, there are some important distinctions.</span></span> <span data-ttu-id="4ba8c-118">Overweeg een e-mailgesprek dat in twee gesprekken is gevorkt; Iemand heeft bijvoorbeeld gereageerd op een e-mailbericht dat niet de laatste is in het gesprek, zodat de laatste twee e-mailberichten in het gesprek unieke inhoud hebben.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="4ba8c-119">Outlook zou de e-mailberichten nog steeds in één gesprek groeperen. als u alleen de laatste e-mail leest, ontbreekt de context van het een-na-laatste e-mailbericht, dat ook unieke inhoud bevat.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="4ba8c-120">Omdat e-mailthreading elke e-mail in afzonderlijke onderdelen parseert en vergelijkt, worden beide laatste twee e-mailberichten door e-mailthreading gemarkeerd als inclusief, zodat u geen context mist zolang u alle e-mailberichten leest die als inclusief zijn gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="4ba8c-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
