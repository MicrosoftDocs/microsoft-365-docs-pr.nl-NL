---
title: Veilige afzenderlijsten voor bulkmailers beheren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Als u veilige afzenderlijsten wilt gebruiken, moet u weten dat Exchange Online Protection (EOP) en Outlook de verwerking anders verwerken. De service respecteert veilige afzenders en domeinen door het RFC 5321.MailFrom-adres en de RFC 5322.From-adres te inspecteren, terwijl Outlook de RFC 5322 toevoegt.Van adres naar de lijst met veilige afzenders van een gebruiker. (Opmerking: De service inspecteert zowel het 5321.MailFrom-adres als 5322.Van adres voor geblokkeerde afzenders en domeinen.)'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807329"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="39c10-105">Veilige afzenderlijsten voor bulkmailers beheren</span><span class="sxs-lookup"><span data-stu-id="39c10-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="39c10-106">Als u veilige afzenderlijsten wilt gebruiken, moet u weten dat Exchange Online Protection (EOP) en Outlook de verwerking anders verwerken.</span><span class="sxs-lookup"><span data-stu-id="39c10-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="39c10-107">De Office 365-service respecteert veilige afzenders `RFC 5321.MailFrom` en `RFC 5322.From` domeinen door het `RFC 5322.From` adres en het adres te inspecteren, terwijl Outlook het adres toevoegt aan de lijst met veilige afzenders van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="39c10-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="39c10-108">(Opmerking: De service inspecteert zowel het adres als het `5321.MailFrom` `5322.From` adres voor geblokkeerde afzenders en domeinen.)</span><span class="sxs-lookup"><span data-stu-id="39c10-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="39c10-109">Het `SMTP MAIL FROM` adres, ook `RFC 5321.MailFrom address`wel bekend als het , is het e-mailadres dat wordt gebruikt om SPF-controles uit te voeren, en als de e-mail niet kan worden bezorgd, het pad waarop het teruggestuurde bericht wordt bezorgd.</span><span class="sxs-lookup"><span data-stu-id="39c10-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="39c10-110">Het is dit e-mailadres dat `Return-Path` standaard in de berichtenkoppen wordt geplaatst, hoewel het mogelijk `Return-Path` is voor de afzender om een ander adres aan te wijzen.</span><span class="sxs-lookup"><span data-stu-id="39c10-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="39c10-111">Het `From:` adres in de berichtkoppen, `RFC 5322.From` ook wel het adres genoemd, is het e-mailadres dat wordt weergegeven in de e-mailclient zoals Outlook.</span><span class="sxs-lookup"><span data-stu-id="39c10-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="39c10-112">Veel van de `5321.MailFrom` tijd, de en `5322.From` adressen zijn hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="39c10-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="39c10-113">Dit is typisch voor persoonlijke communicatie.</span><span class="sxs-lookup"><span data-stu-id="39c10-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="39c10-114">Wanneer e-mail echter namens iemand anders wordt verzonden, zijn de adressen vaak verschillend.</span><span class="sxs-lookup"><span data-stu-id="39c10-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="39c10-115">Dit gebeurt meestal het vaakst voor bulk e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="39c10-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="39c10-116">Stel bijvoorbeeld dat Blue Yonder Airlines Margie's Travel heeft ingehuurd om haar e-mailreclame te versturen.</span><span class="sxs-lookup"><span data-stu-id="39c10-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="39c10-117">U ontvangt dan een bericht in uw postvak in van afzender blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="39c10-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="39c10-118">In dit voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="39c10-118">In this example:</span></span>

- <span data-ttu-id="39c10-119">Het `5321.MailFrom` adres is blueyonder.airlines@margiestravel.com.</span><span class="sxs-lookup"><span data-stu-id="39c10-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="39c10-120">Het `5322.From` adres is blueyonder@news.blueyonderairlines.com, dat is wat u ziet in Outlook.</span><span class="sxs-lookup"><span data-stu-id="39c10-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="39c10-121">Om te voorkomen dat dit bericht wordt gefilterd, u het:</span><span class="sxs-lookup"><span data-stu-id="39c10-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="39c10-122">**Als gebruiker**: `RFC 5322.From` Voeg het adres toe als veilige afzender in Outlook.</span><span class="sxs-lookup"><span data-stu-id="39c10-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="39c10-123">**Als beheerder**: Stel een [e-mailstroomregel](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) in (ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="39c10-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
