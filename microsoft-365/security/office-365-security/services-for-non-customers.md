---
title: Services voor niet-klanten die e-mail verzenden naar Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Microsoft heeft verschillende beleidsregels en technologieën ingevoerd om onze gebruikers te helpen beschermen voor het behoud van gebruikers vertrouwen in het gebruik van e-mail.
ms.openlocfilehash: 478f94d2ed1a03253168486d48fb2b2df57a6a5e
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021023"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="b3184-103">Services voor niet-klanten die e-mail verzenden naar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3184-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b3184-104">E-mail misbruik, ongewenste e-mail en frauduleuze e-mailberichten blijven in het hele e-mailbericht doorlopen.</span><span class="sxs-lookup"><span data-stu-id="b3184-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="b3184-105">Om gebruikers vertrouwen in het gebruik van e-mail te houden, heeft Microsoft diverse beleidsregels en technologieën ingevoerd om onze gebruikers te helpen beschermen.</span><span class="sxs-lookup"><span data-stu-id="b3184-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="b3184-106">Microsoft begrijpt echter dat de betrouwbare e-mail niet negatief wordt beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="b3184-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="b3184-107">Daarom hebben we een suite met Services opgezet om afzenders te helpen de mogelijkheid e-mail te leveren aan Microsoft 365-gebruikers door te proactief hun eigen reputatie te beheren.</span><span class="sxs-lookup"><span data-stu-id="b3184-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="b3184-108">Dit overzicht bevat informatie over de voordelen die we voor uw organisatie leveren, ook als u geen klant bent.</span><span class="sxs-lookup"><span data-stu-id="b3184-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="b3184-109">Oplossingen voor afzender</span><span class="sxs-lookup"><span data-stu-id="b3184-109">Sender solutions</span></span>

****

|<span data-ttu-id="b3184-110">Service</span><span class="sxs-lookup"><span data-stu-id="b3184-110">Service</span></span>|<span data-ttu-id="b3184-111">Bene</span><span class="sxs-lookup"><span data-stu-id="b3184-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="b3184-112">Deze inhoud van online-Help</span><span class="sxs-lookup"><span data-stu-id="b3184-112">This online help content</span></span>|<span data-ttu-id="b3184-113">Wordt</span><span class="sxs-lookup"><span data-stu-id="b3184-113">Provides:</span></span> <ul><li><span data-ttu-id="b3184-114">Een beginpunt voor vragen die betrekking hebben op het leveren van communicatie voor EOP-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b3184-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="b3184-115">Inclusief een eenvoudige online handleiding met ons beleid en de vereisten.</span><span class="sxs-lookup"><span data-stu-id="b3184-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="b3184-116">Een overzicht van de filters voor ongewenste e-mail en verificatietechnologieën die door Microsoft worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b3184-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="b3184-117">Microsoft ondersteuning</span><span class="sxs-lookup"><span data-stu-id="b3184-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="b3184-118">Biedt ondersteuning voor Self-Help en escalatie voor bezorgings problemen.</span><span class="sxs-lookup"><span data-stu-id="b3184-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="b3184-119">Portal voor IP-adressen met anti-spam</span><span class="sxs-lookup"><span data-stu-id="b3184-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="b3184-120">Een hulpmiddel voor het verzenden van een aanvraag voor een IP-lijst.</span><span class="sxs-lookup"><span data-stu-id="b3184-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="b3184-121">Voordat u deze aanvraag verzendt, is het de verantwoordelijkheid van de afzender om te controleren of verdere e-mail die afkomstig is van het IP-adres in kwestie, geen beledigend of kwaadief is.</span><span class="sxs-lookup"><span data-stu-id="b3184-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="b3184-122">Misbruik en spam van e-mailberichten die afkomstig zijn van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b3184-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="b3184-123">Zorgt dat ongewenste e-mail en andere ongewenste e-mail worden verzonden via Exchange Online en maak de Internet-en e-mail systemen onoverzichtelijk.</span><span class="sxs-lookup"><span data-stu-id="b3184-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="b3184-124">Microsoft ondersteuning</span><span class="sxs-lookup"><span data-stu-id="b3184-124">Microsoft support</span></span>

<span data-ttu-id="b3184-125">Microsoft biedt diverse ondersteuningsopties voor personen die problemen hebben met het verzenden van e-mail naar Microsoft 365-geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="b3184-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="b3184-126">We raden u aan:</span><span class="sxs-lookup"><span data-stu-id="b3184-126">We recommend that you:</span></span>

- <span data-ttu-id="b3184-127">Volg de instructies in een rapport over niet-uitgevoerde bezorging.</span><span class="sxs-lookup"><span data-stu-id="b3184-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="b3184-128">Bekijk de meest voorkomende problemen die niet-klanten kunnen vinden in het [oplossen van e-mailberichten die zijn verzonden naar Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b3184-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="b3184-129">Gebruik de [Portal van Microsoft 365](https://sender.office.com) om een aanvraag in te dienen om uw IP uit de lijst met geblokkeerde afzenders te laten verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b3184-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="b3184-130">Lees de [Microsoft Community-Forums](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="b3184-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="b3184-131">Neem contact op met de klant die u per e-mail wilt verzenden en vraag contact op te nemen met Microsoft ondersteuning en een ondersteuningsticket namens u te openen.</span><span class="sxs-lookup"><span data-stu-id="b3184-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="b3184-132">In sommige gevallen moet Microsoft Support rechtstreeks met de afzender communiceren die de eigenaar is van de geblokte IP-ruimte.</span><span class="sxs-lookup"><span data-stu-id="b3184-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="b3184-133">Klanten van ondersteunings tickets kunnen echter niet worden geopend.</span><span class="sxs-lookup"><span data-stu-id="b3184-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="b3184-134">Zie [ondersteuning](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)voor meer informatie over Microsoft technische ondersteuning voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3184-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="b3184-135">Portal voor IP-adressen met anti-spam</span><span class="sxs-lookup"><span data-stu-id="b3184-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="b3184-136">Dit is een selfservice portal die u kunt gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3184-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="b3184-137">Gebruik deze portal als u een foutbericht krijgt wanneer u probeert een e-mailbericht te verzenden naar een geadresseerde waarvan het e-mailadres zich in Microsoft 365 bevindt en u niet denkt dat u het zou moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="b3184-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="b3184-138">Voor meer informatie raadpleegt u [de lijst met geblokkeerde afzenders gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="b3184-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="b3184-139">Misbruik en spam van e-mailberichten die afkomstig zijn van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b3184-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="b3184-140">Soms wordt Microsoft365 door derden gebruikt om ongewenste e-mail te verzenden, in schending van onze gebruiksvoorwaarden en beleid.</span><span class="sxs-lookup"><span data-stu-id="b3184-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="b3184-141">Als u ongewenste e-mail ontvangt van Office 365, kunt u deze berichten aan Microsoft rapporteren.</span><span class="sxs-lookup"><span data-stu-id="b3184-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="b3184-142">Zie voor instructies [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b3184-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
