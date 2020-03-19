---
title: De lijstmetnaamportal gebruiken om uzelf uit de lijst met geblokkeerde afzenders van Office 365 te verwijderen
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
description: Krijgt u een foutbericht wanneer u een e-mail probeert te verzenden naar een ontvanger wiens e-mailadres zich in Office 365 bevindt? Als u denkt dat u het foutbericht niet moet ontvangen, u de lijst met verwijderde portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders van Office 365 te verwijderen.
ms.openlocfilehash: 3e131addb391ecbf90d74ad4fdfa65b802c5e1ac
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808794"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a><span data-ttu-id="53e44-104">De lijstmetnaamportal gebruiken om uzelf uit de lijst met geblokkeerde afzenders van Office 365 te verwijderen</span><span class="sxs-lookup"><span data-stu-id="53e44-104">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>

<span data-ttu-id="53e44-105">Krijgt u een foutbericht wanneer u een e-mail probeert te verzenden naar een ontvanger wiens e-mailadres zich in Office 365 bevindt?</span><span class="sxs-lookup"><span data-stu-id="53e44-105">Are you getting an error message when you try to send an email to a recipient whose email address is in Office 365?</span></span> <span data-ttu-id="53e44-106">Als u denkt dat u het foutbericht niet moet ontvangen, u de lijst met verwijderde portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders van Office 365 te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="53e44-106">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the Office 365 blocked senders list.</span></span>

## <a name="what-is-the-office-365-blocked-senders-list"></a><span data-ttu-id="53e44-107">Wat is de lijst met geblokkeerde afzenders van Office 365?</span><span class="sxs-lookup"><span data-stu-id="53e44-107">What is the Office 365 blocked senders list?</span></span>

<span data-ttu-id="53e44-108">Microsoft gebruikt de lijst met geblokkeerde afzenders om zijn klanten te beschermen tegen spam, spoofing en phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="53e44-108">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="53e44-109">Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat uw mailserver gebruikt om zich op internet te identificeren, is om verschillende redenen gelabeld als een potentiële bedreiging voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="53e44-109">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Office 365 for one of a variety of reasons.</span></span> <span data-ttu-id="53e44-110">Wanneer Office 365 het IP-adres aan de lijst toevoegt, voorkomt het dat alle verdere communicatie tussen het IP-adres en een van onze klanten via onze datacenters wordt voorkomen.</span><span class="sxs-lookup"><span data-stu-id="53e44-110">When Office 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="53e44-111">U weet dat u aan de lijst bent toegevoegd wanneer u een antwoord ontvangt op een e-mailbericht met een foutmelding die een fout bevat die er ongeveer als volgt uitziet:</span><span class="sxs-lookup"><span data-stu-id="53e44-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="53e44-112">550 5.7.606-649 Toegang geweigerd, verboden verzenden IP [_IP-adres_]; Om verwijdering uit deze https://sender.office.com/ lijst aan te vragen, u de aanwijzingen bezoeken en volgen.</span><span class="sxs-lookup"><span data-stu-id="53e44-112">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="53e44-113">Zie Rapporten [voor niet-bezorging e-mailen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="53e44-113">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="53e44-114">waar _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="53e44-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="53e44-115">De portal voor de lijst met geblokkeerde afzenders gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen</span><span class="sxs-lookup"><span data-stu-id="53e44-115">To use the Office 365 delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="53e44-116">Ga in een webbrowser [https://sender.office.com](https://sender.office.com)naar .</span><span class="sxs-lookup"><span data-stu-id="53e44-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="53e44-117">Volg de instructies op de pagina.</span><span class="sxs-lookup"><span data-stu-id="53e44-117">Follow the instructions on the page.</span></span> <span data-ttu-id="53e44-118">Controleer of u het e-mailadres gebruikt waarnaar het foutbericht is verzonden en het IP-adres dat is opgegeven in het foutbericht.</span><span class="sxs-lookup"><span data-stu-id="53e44-118">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="53e44-119">U slechts één e-mailadres en één IP-adres per bezoek invoeren.</span><span class="sxs-lookup"><span data-stu-id="53e44-119">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="53e44-120">Klik **op Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="53e44-120">Click **Submit**.</span></span>

    <span data-ttu-id="53e44-121">De portal stuurt een e-mail naar het e-mailadres dat u verstrekt.</span><span class="sxs-lookup"><span data-stu-id="53e44-121">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="53e44-122">De e-mail ziet er ![ongeveer als volgt uit: Screenshot van e-mail ontvangen wanneer u een verzoek indient via de lijst portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="53e44-122">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="53e44-123">Klik op de bevestigingskoppeling in de e-mail die u door de niet-vermeldende portal is verzonden.</span><span class="sxs-lookup"><span data-stu-id="53e44-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="53e44-124">Dit brengt je terug naar de lijst portaal.</span><span class="sxs-lookup"><span data-stu-id="53e44-124">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="53e44-125">Klik in de lijstportal op **Ip van de lijst schrappen**.</span><span class="sxs-lookup"><span data-stu-id="53e44-125">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="53e44-126">Nadat het IP-adres uit de lijst met geblokkeerde afzenders is verwijderd, worden e-mailberichten van dat IP-adres bezorgd aan ontvangers die Office 365 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="53e44-126">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Office 365.</span></span> <span data-ttu-id="53e44-127">Zorg er dus voor dat e-mail die vanaf dat IP-adres wordt verzonden, niet beledigend of kwaadaardig is. anders kan het IP-adres opnieuw worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="53e44-127">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53e44-128">Het kan tot 24 uur duren of de resultaten kunnen sterk variëren voordat beperkingen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="53e44-128">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="53e44-129">Lees [meer Over Hoe voorkom je dat echte e-mail wordt gemarkeerd als spam in Office 365](prevent-email-from-being-marked-as-spam.md ) en [Controle op uitgaande spam in Office 365](outbound-spam-controls.md) om te voorkomen dat IP op de zwarte lijst komt te staan.</span><span class="sxs-lookup"><span data-stu-id="53e44-129">Read about [How to prevent real email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md ) and [Controlling outbound spam in Office 365](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>
