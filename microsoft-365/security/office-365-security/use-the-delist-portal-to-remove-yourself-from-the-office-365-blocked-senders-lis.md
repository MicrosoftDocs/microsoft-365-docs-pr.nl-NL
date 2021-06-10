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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u de portal voor het verwijderen van de lijst kunt gebruiken om uzelf te verwijderen uit de lijst Microsoft 365 geblokkeerde afzenders.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204445"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="ff0b6-103">De delist-portal gebruiken om jezelf uit de lijst met geblokkeerde afzenders te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ff0b6-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff0b6-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ff0b6-104">**Applies to**</span></span>
- [<span data-ttu-id="ff0b6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ff0b6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ff0b6-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ff0b6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ff0b6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff0b6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ff0b6-108">Krijgt u een foutbericht wanneer u een e-mailbericht probeert te verzenden naar een geadresseerde van wie het e-mailadres zich in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="ff0b6-108">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="ff0b6-109">Als u denkt dat u het foutbericht niet moet ontvangen, kunt u de portal voor het verwijderen van de lijst met geblokkeerde afzenders gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-109">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="ff0b6-110">Wat is de lijst met geblokkeerde afzenders?</span><span class="sxs-lookup"><span data-stu-id="ff0b6-110">What is the blocked senders list?</span></span>

<span data-ttu-id="ff0b6-111">Microsoft gebruikt de lijst met geblokkeerde afzenders om haar klanten te beschermen tegen spam-, spoofing- en phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-111">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="ff0b6-112">Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat uw e-mailserver gebruikt om zich op internet te identificeren, is om verschillende redenen gelabeld als een mogelijke bedreiging voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-112">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="ff0b6-113">Wanneer Microsoft 365 ip-adres aan de lijst toevoegt, voorkomt dit alle verdere communicatie tussen het IP-adres en een van onze klanten via onze datacenters.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-113">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="ff0b6-114">U weet dat u aan de lijst bent toegevoegd wanneer u een antwoord ontvangt op een e-mailbericht met een fout die er zo uitziet:</span><span class="sxs-lookup"><span data-stu-id="ff0b6-114">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="ff0b6-115">550 5.7.606-649 Access geweigerd, ip-adres verzenden verboden [_IP-adres_]; Als u verwijdering uit deze lijst wilt aanvragen, gaat u naar <https://sender.office.com/> de routebeschrijving en volgt u deze.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="ff0b6-116">Zie [E-mailrapporten voor niet-bezorging in](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-116">For more information see [Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="ff0b6-117">waarbij  _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-117">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="ff0b6-118">Delist portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ff0b6-118">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="ff0b6-119">Ga in een webbrowser naar <https://sender.office.com> .</span><span class="sxs-lookup"><span data-stu-id="ff0b6-119">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="ff0b6-120">Volg de instructies op de pagina.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-120">Follow the instructions on the page.</span></span> <span data-ttu-id="ff0b6-121">Zorg ervoor dat u het e-mailadres gebruikt waarop het foutbericht is verzonden en het IP-adres dat is opgegeven in het foutbericht.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-121">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="ff0b6-122">U kunt slechts één e-mailadres en één IP-adres per bezoek invoeren.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-122">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="ff0b6-123">Klik **op Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="ff0b6-123">Click **Submit**.</span></span>

    <span data-ttu-id="ff0b6-124">De portal stuurt een e-mail naar het e-mailadres dat u oplevert.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-124">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="ff0b6-125">De e-mail ziet er als volgt uit: Schermafbeelding van e-mail die is ontvangen wanneer u een aanvraag indient ![ via de delistportal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="ff0b6-125">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="ff0b6-126">Klik op de bevestigingskoppeling in de e-mail die naar u is verzonden via de portal voor het op de lijst zetten.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-126">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="ff0b6-127">Hiermee gaat u terug naar de portal voor het op de lijst zetten.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-127">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="ff0b6-128">Klik in de lijstportal op **IP-lijst delisten.**</span><span class="sxs-lookup"><span data-stu-id="ff0b6-128">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="ff0b6-129">Nadat het IP-adres is verwijderd uit de lijst met geblokkeerde afzenders, worden e-mailberichten van dat IP-adres bezorgd bij geadresseerden die Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-129">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="ff0b6-130">Zorg er dus voor dat u er zeker van bent dat e-mail die vanaf dat IP-adres wordt verzonden, niet aanstootgevend of schadelijk is. anders wordt het IP-adres mogelijk opnieuw geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-130">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff0b6-131">Het kan tot 24 uur duren of de resultaten kunnen sterk variëren voordat beperkingen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-131">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="ff0b6-132">Zie [Lijsten met veilige afzenders maken in EOP-](create-safe-sender-lists-in-office-365.md) en Uitgaande [spambeveiliging in EOP](outbound-spam-controls.md) om te voorkomen dat een IP-adres wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="ff0b6-132">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>