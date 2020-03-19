---
title: Beheerdersinzendingen in Office 365, O365-inzendingen, Office 365-spamprobleem, O365 vals negatief, phish indienen in Office 365, e-mail indienen voor scannen, verdachte e-mail in Office 365, een e-mail scannen, Microsoft laten scannen op phish, Microsoft laten scannen op spam, verzenden e-mail, e-mail indienen, dodgy e-mail, slechte acteur mail, verdacht, niet-vertrouwde e-mail, phish e-mails melden aan Microsoft, phish e-mails melden aan Microsoft, meld scam e-mail aan Microsoft, meld malware in e-mail naar Microsoft, spam e-mail in inbox office 365, virus in e-mail office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Meer informatie over het verzenden van verdachte e-mails, vermoedelijke phishingmails, spam en andere mogelijk schadelijke berichten, URL's en bestanden van uw Office 365-tenant aan Microsoft voor het scannen.
ms.openlocfilehash: b123aef485628728df9db27875117b47295975ad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808814"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="7b85a-103">Verdachte spam, phish, URL's en bestanden indienen bij Microsoft voor Office 365-scannen</span><span class="sxs-lookup"><span data-stu-id="7b85a-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="7b85a-104">Beheerders kunnen e-mails verzenden met behulp van bestands- of netwerkbericht-id, URL's en bestanden voor het scannen door Microsoft in Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b85a-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span>
<span data-ttu-id="7b85a-105">De bijgewerkte inzendingen sectie bevat nog steeds door de gebruiker gerapporteerde berichten en beschikbaar voor alle klanten met behulp van EOP.</span><span class="sxs-lookup"><span data-stu-id="7b85a-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="7b85a-106">Wanneer u een e-mail indient, krijgt u informatie over alle beleidsregels die de inkomende e-mail mogelijk in uw tenant hebben toegestaan, evenals het onderzoeken van URL's en bijlagen in de e-mail.</span><span class="sxs-lookup"><span data-stu-id="7b85a-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="7b85a-107">Beleid waarmee een e-mail mogelijk is, omvat de lijst met veilige afzenders van een individuele gebruiker en beleid op tenantniveau, zoals exchange-mailstroomregels (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="7b85a-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="7b85a-108">Verdachte inhoud doorsturen naar Microsoft voor Office 365-scannen</span><span class="sxs-lookup"><span data-stu-id="7b85a-108">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="7b85a-109">Als u inhoud wilt verzenden naar Microsoft, klikt u op de knop **Nieuwe indiening** in de linkerbovenhoek van de inzendingenpagina.</span><span class="sxs-lookup"><span data-stu-id="7b85a-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="7b85a-110">Er verschijnt een fly-out aan de rechterkant van de pagina met de optie om een e-mail, URL of bestand in te dienen.</span><span class="sxs-lookup"><span data-stu-id="7b85a-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="7b85a-111">Een twijfelachtige e-mail verzenden naar Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b85a-111">Submit a questionable email to Microsoft</span></span>

![Voorbeeld van e-mailindiening](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="7b85a-113">Als u een e-mail wilt verzenden, selecteert u **e-mail** en geeft u de **e-mailbericht-id** op of uploadt u het e-mailbestand.</span><span class="sxs-lookup"><span data-stu-id="7b85a-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="7b85a-114">Geef de ontvanger(s) op tegen wie u de beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="7b85a-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="7b85a-115">De beleidscontrole bepaalt of de e-mail het scannen heeft omzeild vanwege beleid op gebruikers- of tenantniveau.</span><span class="sxs-lookup"><span data-stu-id="7b85a-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="7b85a-116">Geef op of de e-mail al dan niet geblokkeerd had moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="7b85a-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="7b85a-117">Als de e-mail had moeten worden geblokkeerd, geeft u aan of deze had moeten worden geblokkeerd als spam, phishing of malware.</span><span class="sxs-lookup"><span data-stu-id="7b85a-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="7b85a-118">Als u niet zeker weet welk type het zou kunnen zijn, gebruik dan uw beste oordeel.</span><span class="sxs-lookup"><span data-stu-id="7b85a-118">If you are not sure what type it might be, use your best judgement.</span></span>

   - <span data-ttu-id="7b85a-119">Als het filter is omzeild vanwege beleid bij indiening, ziet u informatie over dat beleid.</span><span class="sxs-lookup"><span data-stu-id="7b85a-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="7b85a-120">Als het filter niet is omzeild vanwege een of meer beleidsregels, wordt de scan binnen enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="7b85a-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="7b85a-121">U ziet aanvullende informatie over de indiening door op de statuskoppeling te klikken.</span><span class="sxs-lookup"><span data-stu-id="7b85a-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="7b85a-122">Dit omvat de resultaten van de beleidscontrole en het herscannen.</span><span class="sxs-lookup"><span data-stu-id="7b85a-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="7b85a-123">Houd er rekening mee dat de e-mail niet opnieuw wordt uitgevoerd via de volledige filterstack van Office 365 ATP, maar een gedeeltelijke herscan uitvoert op basis van bepaalde kenmerken van de e-mail, URL of het bestand.</span><span class="sxs-lookup"><span data-stu-id="7b85a-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="7b85a-124">Klik op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="7b85a-124">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="7b85a-125">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="7b85a-125">Send a suspect URL to Microsoft</span></span>

![Voorbeeld van e-mailindiening](../../media/submission-url-flyout.png)

1. <span data-ttu-id="7b85a-127">Als u een URL wilt indienen, selecteert u **URL** van de flyout.</span><span class="sxs-lookup"><span data-stu-id="7b85a-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="7b85a-128">Typ de volledige URL in inclusief het protocol **(https://).**</span><span class="sxs-lookup"><span data-stu-id="7b85a-128">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="7b85a-129">Als u hebt geselecteerd **Moet zijn gefilterd,** geef dan op of de URL phishing of malware is.</span><span class="sxs-lookup"><span data-stu-id="7b85a-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="7b85a-130">Klik op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="7b85a-130">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="7b85a-131">Een verdacht bestand indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b85a-131">Submit a suspected file to Microsoft</span></span>

![Voorbeeld van e-mailindiening](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="7b85a-133">Als u een bestand wilt indienen, selecteert u **Bestand** uit de flyout en uploadt u het bestand dat u wilt scannen.</span><span class="sxs-lookup"><span data-stu-id="7b85a-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="7b85a-134">Klik op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="7b85a-134">Click the **Submit** button.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b85a-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7b85a-135">Related topics</span></span>

[<span data-ttu-id="7b85a-136">Office 365 Advanced Threat Protection Plan 2</span><span class="sxs-lookup"><span data-stu-id="7b85a-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)

[<span data-ttu-id="7b85a-137">Beschermen tegen bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="7b85a-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="7b85a-138">Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="7b85a-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
