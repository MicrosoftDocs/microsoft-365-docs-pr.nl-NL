---
title: Uzelf verwijderen uit de lijst met geblokkeerde afzenders
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
description: In dit artikel leert u hoe u de lijst Portal kunt gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders in Microsoft 365.
ms.openlocfilehash: 2256cde6a3ca3a8ddd728cb2464adff702fa94c8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195829"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="73156-103">De delist-portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen</span><span class="sxs-lookup"><span data-stu-id="73156-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="73156-104">Wordt er een foutbericht weergegeven wanneer u probeert een e-mailbericht te verzenden naar een geadresseerde waarvan het e-mailadres zich in Microsoft 365 bevindt?</span><span class="sxs-lookup"><span data-stu-id="73156-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="73156-105">Als u denkt dat het foutbericht moet worden weergegeven, kunt u de lijst met geblokkeerde afzenders gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="73156-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="73156-106">Wat is de lijst met geblokkeerde afzenders?</span><span class="sxs-lookup"><span data-stu-id="73156-106">What is the blocked senders list?</span></span>

<span data-ttu-id="73156-107">Microsoft gebruikt de lijst met geblokkeerde afzenders om klanten tegen spam, spoofing en phishing-aanvallen te beschermen.</span><span class="sxs-lookup"><span data-stu-id="73156-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="73156-108">Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat door uw e-mailserver wordt gebruikt om zichzelf te identificeren op internet, is als mogelijke bedreiging voor Microsoft 365 in een van de verschillende redenen.</span><span class="sxs-lookup"><span data-stu-id="73156-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="73156-109">Wanneer Microsoft 365 het IP-adres aan de lijst toevoegt, voorkomt u dat alle verdere communicatie tussen het IP-adres en een van onze klanten via onze datacenters wordt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="73156-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="73156-110">U weet dat u bent toegevoegd aan de lijst wanneer u een antwoord ontvangt voor een e-mailbericht met een foutmelding die er ongeveer als volgt uitziet:</span><span class="sxs-lookup"><span data-stu-id="73156-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="73156-111">550 5.7.606-649 toegang geweigerd, weigering IP [_IP Address_]; Als u het verwijderen van deze lijst wilt aanvragen, gaat u https://sender.office.com/ verder met de instructies.</span><span class="sxs-lookup"><span data-stu-id="73156-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="73156-112">Zie [rapporten over niet-uitgevoerde bezorging van e-mail in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="73156-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="73156-113">waarbij  _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="73156-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="73156-114">U kunt als volgt de lijst met geblokkeerde afzenders gebruiken om de portal te verwijderen</span><span class="sxs-lookup"><span data-stu-id="73156-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="73156-115">Ga in een webbrowser naar [https://sender.office.com](https://sender.office.com) .</span><span class="sxs-lookup"><span data-stu-id="73156-115">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="73156-116">Volg de instructies op de pagina.</span><span class="sxs-lookup"><span data-stu-id="73156-116">Follow the instructions on the page.</span></span> <span data-ttu-id="73156-117">Zorg ervoor dat u het e-mailadres gebruikt waarnaar het foutbericht is verzonden en het IP-adres dat is opgegeven in het foutbericht.</span><span class="sxs-lookup"><span data-stu-id="73156-117">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="73156-118">U kunt slechts één e-mailadres en één IP-adres per bezoek invoeren.</span><span class="sxs-lookup"><span data-stu-id="73156-118">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="73156-119">Klik op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="73156-119">Click **Submit**.</span></span>

    <span data-ttu-id="73156-120">De portal verzendt een e-mailadres naar het e-mailadres dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="73156-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="73156-121">Het e-mailbericht ziet er ongeveer als volgt ![ uit: schermafbeelding van een e-mailbericht dat u ontvangt wanneer u een aanvraag indient via de portal voor delistren](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="73156-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="73156-122">Klik op de bevestigings koppeling in het e-mailbericht dat naar u is verzonden, via de portal voor het opzeggen van de portal.</span><span class="sxs-lookup"><span data-stu-id="73156-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="73156-123">U gaat terug naar de lijst Portal.</span><span class="sxs-lookup"><span data-stu-id="73156-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="73156-124">Klik in het vak Portal delijstte op **IP-adres weergeven**.</span><span class="sxs-lookup"><span data-stu-id="73156-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="73156-125">Nadat het IP-adres is verwijderd uit de lijst met geblokkeerde afzenders, worden e-mailberichten van dat IP-adres afgeleverd bij geadresseerden die gebruikmaken van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73156-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="73156-126">Zorg ervoor dat het e-mailadres dat via dat IP-adres is verzonden, niet beledigend of schadelijk kan zijn. anders wordt het IP-adres mogelijk opnieuw geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="73156-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="73156-127">Het kan tot 24 uur duren voordat de beperkingen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="73156-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="73156-128">Zie [voor meer informatie over het maken van lijsten met veilige afzenders in EOP](create-safe-sender-lists-in-office-365.md) en [uitgaande spam bescherming in EOP](outbound-spam-controls.md) om te voorkomen dat een IP wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="73156-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
