---
title: Lijsten met afzenders en geblokkeerde afzenders in Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Als Beheerder van Exchange Online of Exchange Online Protection (Exchange Online Protection) u ervoor zorgen dat een e-mailbericht dat via de service reist, niet als spam wordt gemarkeerd. Een manier om dit te doen is door veilige afzender- en geblokkeerde afzenderlijsten te maken voor de mensen in uw organisatie.
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809181"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="c5e77-104">Lijsten met afzenders en geblokkeerde afzenders in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c5e77-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="c5e77-105">Als Beheerder van Exchange Online of Exchange Online Protection (Exchange Online Protection) u ervoor zorgen dat een e-mailbericht dat via de service reist, niet als spam wordt gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="c5e77-105">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam.</span></span> <span data-ttu-id="c5e77-106">Een manier om dit te doen is door veilige afzender- en geblokkeerde afzenderlijsten te maken voor de mensen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c5e77-106">One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="c5e77-107">*Bekijk de bijgewerkte versie van de tips en procedures voor het werken met deze lijsten als beheerder in* Hoe [voorkom je dat goede e-mail wordt gemarkeerd als spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="c5e77-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="c5e77-108">Als u geen beheerder bent en u alleen uw eigen ongewenste e-mail in Outlook wilt beheren met behulp van een lijst met veilige afzenders, bekijkt u de stappen in het[overzicht van het filter ongewenste e-mail](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span><span class="sxs-lookup"><span data-stu-id="c5e77-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="c5e77-109">Wat zijn de veilige en geblokkeerde verzendlimieten in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="c5e77-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="c5e77-110">De limieten voor veilige en geblokkeerde afzenders in Exchange Online verschillen van de limieten voor Active Directory en Outlook.</span><span class="sxs-lookup"><span data-stu-id="c5e77-110">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits.</span></span> <span data-ttu-id="c5e77-111">Ze zijn:</span><span class="sxs-lookup"><span data-stu-id="c5e77-111">They are:</span></span>

- <span data-ttu-id="c5e77-112">Veilige verzendlimiet: 1.024</span><span class="sxs-lookup"><span data-stu-id="c5e77-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="c5e77-113">Geblokkeerde afzenderlimiet: 500</span><span class="sxs-lookup"><span data-stu-id="c5e77-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="c5e77-114">Opmerking:</span><span class="sxs-lookup"><span data-stu-id="c5e77-114">Note:</span></span>

<span data-ttu-id="c5e77-115">U de fout ervaren die wordt beschreven in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span><span class="sxs-lookup"><span data-stu-id="c5e77-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="c5e77-116">Schakel het selectievakje E-mails van mijn contactpersonen in vertrouwen uit om dit probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="c5e77-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="c5e77-117">U ook de hoeveelheid e-mailadressen die zich in uw standaardmap Contactpersonen bevinden, verkleinen om deze binnen de maximaal toegestane limiet van 1024 in Exchange Online te brengen die is ingesteld op het kenmerk 'MaxSafeSenders'.</span><span class="sxs-lookup"><span data-stu-id="c5e77-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="c5e77-118">Zie het volgende onderwerp voor meer informatie over dit kenmerk en de cmdlet Set-Mailbox:</span><span class="sxs-lookup"><span data-stu-id="c5e77-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="c5e77-119">Postvak instellen</span><span class="sxs-lookup"><span data-stu-id="c5e77-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="c5e77-120">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c5e77-120">See also</span></span>

[<span data-ttu-id="c5e77-121">Afzenderfiltering in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c5e77-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
