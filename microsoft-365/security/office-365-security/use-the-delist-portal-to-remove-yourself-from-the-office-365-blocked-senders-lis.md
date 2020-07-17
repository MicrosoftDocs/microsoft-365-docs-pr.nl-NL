---
title: Verwijder jezelf uit de lijst met geblokkeerde afzenders
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u de verwijderingsportal gebruiken om uzelf uit de lijst met geblokkeerde afzenders van Microsoft 365 te verwijderen.
ms.openlocfilehash: 2d9dbba12740e62305e1bcfd193175659be34026
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739241"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="7f332-103">De delist-portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen</span><span class="sxs-lookup"><span data-stu-id="7f332-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

<span data-ttu-id="7f332-104">Krijgt u een foutmelding wanneer u een e-mail probeert te sturen naar een ontvanger wiens e-mailadres in Microsoft 365 staat?</span><span class="sxs-lookup"><span data-stu-id="7f332-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="7f332-105">Als u denkt dat u het foutbericht niet moet ontvangen, u de pagina verwijderen om uzelf uit de lijst met geblokkeerde afzenders te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7f332-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="7f332-106">Wat is de lijst met geblokkeerde afzenders?</span><span class="sxs-lookup"><span data-stu-id="7f332-106">What is the blocked senders list?</span></span>

<span data-ttu-id="7f332-107">Microsoft gebruikt de lijst met geblokkeerde afzenders om zijn klanten te beschermen tegen spam-, spoofing- en phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="7f332-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="7f332-108">Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat uw e-mailserver gebruikt om zich op internet te identificeren, is om verschillende redenen getagd als een potentiële bedreiging voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f332-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="7f332-109">Wanneer Microsoft 365 het IP-adres aan de lijst toevoegt, voorkomt dit alle verdere communicatie tussen het IP-adres en een van onze klanten via onze datacenters.</span><span class="sxs-lookup"><span data-stu-id="7f332-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="7f332-110">U weet dat u aan de lijst bent toegevoegd wanneer u een antwoord op een e-mailbericht ontvangt met een fout die er ongeveer als volgt uitziet:</span><span class="sxs-lookup"><span data-stu-id="7f332-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="7f332-111">550 5.7.606-649 Access geweigerd, verboden verzenden van IP [_IP-adres_]; Om verwijdering van deze lijst aan te vragen, u https://sender.office.com/ terecht op de aanwijzingen en de aanwijzingen volgen.</span><span class="sxs-lookup"><span data-stu-id="7f332-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="7f332-112">Zie Rapporten [over niet-levering e-mailen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7f332-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="7f332-113">waarbij _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="7f332-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="7f332-114">Delist-portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen</span><span class="sxs-lookup"><span data-stu-id="7f332-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="7f332-115">Ga in een webbrowser naar [https://sender.office.com](https://sender.office.com) .</span><span class="sxs-lookup"><span data-stu-id="7f332-115">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="7f332-116">Volg de instructies op de pagina.</span><span class="sxs-lookup"><span data-stu-id="7f332-116">Follow the instructions on the page.</span></span> <span data-ttu-id="7f332-117">Zorg ervoor dat u het e-mailadres gebruikt waarop het foutbericht is verzonden en het IP-adres dat is opgegeven in het foutbericht.</span><span class="sxs-lookup"><span data-stu-id="7f332-117">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="7f332-118">U slechts één e-mailadres en één IP-adres per bezoek invoeren.</span><span class="sxs-lookup"><span data-stu-id="7f332-118">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="7f332-119">Klik **op Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="7f332-119">Click **Submit**.</span></span>

    <span data-ttu-id="7f332-120">De portal stuurt een e-mail naar het e-mailadres dat u aangeeft.</span><span class="sxs-lookup"><span data-stu-id="7f332-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="7f332-121">De e-mail ziet er ongeveer als volgt uit: ![ Schermafbeelding van ontvangen e-mail wanneer u een verzoek indient via de schrappingsportaal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="7f332-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="7f332-122">Klik op de bevestigingslink in de e-mail die u door de schrappingsportal is verzonden.</span><span class="sxs-lookup"><span data-stu-id="7f332-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="7f332-123">Dit brengt je terug naar de schrappingsportaal.</span><span class="sxs-lookup"><span data-stu-id="7f332-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="7f332-124">Klik in de schrappingsportal op **IP schrappen**.</span><span class="sxs-lookup"><span data-stu-id="7f332-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="7f332-125">Nadat het IP-adres uit de lijst met geblokkeerde afzenders is verwijderd, worden e-mailberichten van dat IP-adres bezorgd aan ontvangers die Microsoft 365 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7f332-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="7f332-126">Zorg er dus voor dat je er zeker van bent dat e-mail die vanaf dat IP-adres wordt verzonden, niet beledigend of kwaadaardig is; anders kan het IP-adres opnieuw worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="7f332-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f332-127">Het kan tot 24 uur duren of de resultaten kunnen sterk variëren voordat beperkingen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7f332-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="7f332-128">[Zie Veilige afzenderlijsten maken in EOP-](create-safe-sender-lists-in-office-365.md) en [Uitgaande spambeveiliging in EOP](outbound-spam-controls.md) om te voorkomen dat een IP-adres wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="7f332-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
