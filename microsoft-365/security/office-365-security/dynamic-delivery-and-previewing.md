---
title: Dynamische bezorgings-en voorbeeldweergave met veilige bijlagen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Wanneer u uw ATP-beleid voor veilige bijlagen instelt, kiest u Dynamische bezorging om berichtvertragingen te voorkomen en personen in staat te stellen een voorbeeld van bijlagen te bekijken die worden gescand.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0b19317babbd433ba0914ca2385cf6c9b40d89b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203033"
---
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a><span data-ttu-id="a1f52-103">Dynamische bezorgings-en voorbeeldweergave met veilige bijlagen</span><span class="sxs-lookup"><span data-stu-id="a1f52-103">Dynamic Delivery and previewing with ATP Safe Attachments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-dynamic-delivery"></a><span data-ttu-id="a1f52-104">Basisfuncties van dynamische bezorging</span><span class="sxs-lookup"><span data-stu-id="a1f52-104">Basic features of Dynamic Delivery</span></span>

<span data-ttu-id="a1f52-105">Dynamische bezorging is een optie die kan worden geselecteerd voor de [veilige bijlagen van ATP.</span><span class="sxs-lookup"><span data-stu-id="a1f52-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="a1f52-106">Lees dit artikel om meer te weten te komen over de mogelijkheden van Dynamische bezorging en bijlagenvoorbeeld in [veilige bijlagen van ATP in Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="a1f52-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="a1f52-107">Wanneer [ATP-beleid voor veilige bijlagen wordt ingesteld](set-up-atp-safe-attachments-policies.md) voor uw organisatie, zijn er verschillende opties voor het verwerken van e-mailbijlagen.</span><span class="sxs-lookup"><span data-stu-id="a1f52-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="a1f52-108">Deze omvatten **blokkeren**, **vervangen** en **dynamische bezorging**.</span><span class="sxs-lookup"><span data-stu-id="a1f52-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="a1f52-109">Afhankelijk van hoe het ATP-beleid voor veilige bijlagen is geconfigureerd, kunnen geadresseerden van e-mailberichten een kleine vertraging in de bezorging van e-mail ondervinden terwijl hun bijlagen worden gescand.</span><span class="sxs-lookup"><span data-stu-id="a1f52-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="a1f52-110">Als u vertragingen bij berichten wilt voorkomen, kiest u **dynamische bezorging**.</span><span class="sxs-lookup"><span data-stu-id="a1f52-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>

## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="a1f52-111">Hoe dynamische bezorging werkt</span><span class="sxs-lookup"><span data-stu-id="a1f52-111">How Dynamic Delivery works</span></span>

<span data-ttu-id="a1f52-112">Dynamische bezorging elimineert e-mailvertragingen door de hoofdtekst van een e-mailbericht door te sturen naar de ontvanger met een tijdelijke aanduiding voor e-mailbijlage(n).</span><span class="sxs-lookup"><span data-stu-id="a1f52-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="a1f52-113">De tijdelijke aanduiding blijft staan totdat een kopie van de bijlage is gescand en door [ATP veilige bijlagen](atp-safe-attachments.md) als veilig is beoordeeld.</span><span class="sxs-lookup"><span data-stu-id="a1f52-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

- <span data-ttu-id="a1f52-114">Nadat een bijlage is gescand, is deze beschikbaar om te openen of te downloaden.</span><span class="sxs-lookup"><span data-stu-id="a1f52-114">As each attachment is cleared, it is available to open or download.</span></span>

- <span data-ttu-id="a1f52-115">Als een bijlage is vastgesteld om schadelijk te zijn, wordt deze naar Quarantine verzonden, waar iemand in het beveiligingsteam van uw organisatie (zoals een globale beheerder of beveiligingsbeheerder) [berichten in quarantaine kan beheren in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="a1f52-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as a global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="a1f52-116">De meeste PDF-bestanden en Office-documenten kunnen worden weergegeven in de veilige modus terwijl er met ATP wordt gescand.</span><span class="sxs-lookup"><span data-stu-id="a1f52-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="a1f52-117">Als een bijlage niet compatibel is met de voorbeeldweergave voor dynamische bezorging, zien geadresseerden van e-mailberichten een tijdelijke aanduiding voor bijlagen, totdat het scannen van de veilige bijlagen is voltooid.</span><span class="sxs-lookup"><span data-stu-id="a1f52-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="a1f52-118">Als u een mobiel apparaat gebruikt en PDF-bestanden niet worden weergegeven in de weergave voor dynamische aflevering, meldt u zich eerst aan met uw mobiele browser.</span><span class="sxs-lookup"><span data-stu-id="a1f52-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing in using your mobile browser.</span></span>

<span data-ttu-id="a1f52-119">Met dynamische bezorging kunnen personen hun e-mailberichten meteen lezen en beantwoorden, terwijl hun bijlagen worden geanalyseerd.</span><span class="sxs-lookup"><span data-stu-id="a1f52-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span>

<span data-ttu-id="a1f52-120">Met de functie voor het scannen van ATP-virussen wordt gebruikgemaakt van de regio waarin uw Microsoft 365-gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="a1f52-120">ATP Safe Attachments scanning takes place in the same region where your Microsoft 365 data resides.</span></span> <span data-ttu-id="a1f52-121">Voor meer informatie over de geografie in datacenters raadpleegt u [waar bevinden uw gegevens zich?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="a1f52-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span>

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="a1f52-122">Wat gebeurt er als iemand een e-mailbericht met een bijlage doorstuurt?</span><span class="sxs-lookup"><span data-stu-id="a1f52-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="a1f52-123">Stel dat een organisatie dynamische bezorging gebruikt voor hun [ATP-beleid voor veilige bijlagen](set-up-atp-safe-attachments-policies.md) en iemand ontvangt een e-mailbericht met een bijlage.</span><span class="sxs-lookup"><span data-stu-id="a1f52-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="a1f52-124">Stel nu dat die persoon het e-mailbericht doorstuurt naar iemand anders.</span><span class="sxs-lookup"><span data-stu-id="a1f52-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="a1f52-125">Wat gebeurt er?</span><span class="sxs-lookup"><span data-stu-id="a1f52-125">What happens?</span></span> <span data-ttu-id="a1f52-126">Het hangt af van het feit of de extra geadresseerden worden opgenomen in het ATP-beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="a1f52-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>

- <span data-ttu-id="a1f52-127">Als een ontvanger wordt gedekt door een ATP-beleid voor veilige bijlagen met behulp van de optie dynamische bezorging, ziet de geadresseerde de tijdelijke aanduiding, met de mogelijkheid om compatibele bestanden te bekijken.</span><span class="sxs-lookup"><span data-stu-id="a1f52-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>

- <span data-ttu-id="a1f52-128">Als een ontvanger niet wordt gedekt door een ATP-beleid voor veilige bijlagen, worden de e-mailberichten en bijlagen doorgestuurd zonder dat een ATP-beleidsscan voor veilige bijlagen of tijdelijke aanduidingen voor bijlagen wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a1f52-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>

## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="a1f52-129">Wat is vereist voor een dynamische bezorging?</span><span class="sxs-lookup"><span data-stu-id="a1f52-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="a1f52-130">Uw organisatie moet beschikken over [Office 365 Advanced Threat Protection](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="a1f52-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>

- <span data-ttu-id="a1f52-131">Beleid moet worden gedefinieerd voor ATP-beleid voor veilige bijlagen met de optie voor Dynamische bezorging (Zie [ATP-beleid voor veilige bijlagen instellen in Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="a1f52-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>

- <span data-ttu-id="a1f52-132">Het e-mailsysteem van uw organisatie moet worden gehost in Office 365.</span><span class="sxs-lookup"><span data-stu-id="a1f52-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="a1f52-133">Hoewel [Office 365 Advanced Threat Protection kan worden gebruikt met elke SMTP-mailoverdrachtsagent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (zoals Exchange Server), vereist de optie dynamische bezorging voor ATP-beleid voor veilige bijlagen dat het e-mailsysteem van uw organisatie wordt gehost in Office 365.</span><span class="sxs-lookup"><span data-stu-id="a1f52-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="a1f52-134">Als uw e-mailsysteem niet wordt gehost in Office 365, kiest u een andere [optie voor het ATP-beleid voor veilige bijlagen](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), zoals **blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="a1f52-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="a1f52-135">Aanvullende overwegingen</span><span class="sxs-lookup"><span data-stu-id="a1f52-135">Additional considerations</span></span>

<span data-ttu-id="a1f52-136">Er zijn bepaalde scenario's waarin veilige bijlagen (waaronder dynamische bezorging niet wordt ondersteund).</span><span class="sxs-lookup"><span data-stu-id="a1f52-136">There are certain scenarios in which Safe Attachments (including Dynamic Delivery is not supported).</span></span> <span data-ttu-id="a1f52-137">Dit zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="a1f52-137">These include:</span></span>

- <span data-ttu-id="a1f52-138">E-mailberichten in openbare mappen.</span><span class="sxs-lookup"><span data-stu-id="a1f52-138">Email messages that are in public folders.</span></span>

- <span data-ttu-id="a1f52-139">E-mailberichten die zijn gerouteerd van en terug naar het postvak van de gebruiker via aangepaste regels.</span><span class="sxs-lookup"><span data-stu-id="a1f52-139">Email messages that are routed out of and then back into the user's mailbox using custom rules.</span></span>

- <span data-ttu-id="a1f52-140">E-mailberichten die in het gehoste postvak (automatisch of handmatig) van het gehoste postvak worden verplaatst en naar andere locaties, waaronder archief mappen.</span><span class="sxs-lookup"><span data-stu-id="a1f52-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders.</span></span>

- <span data-ttu-id="a1f52-141">Gewiste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="a1f52-141">Email messages that are deleted.</span></span>

- <span data-ttu-id="a1f52-142">De zoekmap van een gebruiker die in een fout staat.</span><span class="sxs-lookup"><span data-stu-id="a1f52-142">A user's mailbox search folder that is in an error state.</span></span>

- <span data-ttu-id="a1f52-143">Omgevingen waarin een Exchange Online-beheerder Exclaimer heeft ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a1f52-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="a1f52-144">Als u dit probleem wilt oplossen, raadpleegt u [berichten met bijlagen worden niet bezorgd wanneer ATP dynamische levering en Exclaimer worden gebruikt](https://support.microsoft.com/help/4014438).</span><span class="sxs-lookup"><span data-stu-id="a1f52-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438).</span></span>

- <span data-ttu-id="a1f52-145">Berichten versleuteld met [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md)).</span><span class="sxs-lookup"><span data-stu-id="a1f52-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md)).</span></span>

- <span data-ttu-id="a1f52-146">In situaties waarin dynamische bezorging niet wordt ondersteund, worden e-mailberichten niet gescand met veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="a1f52-146">In cases where Dynamic Delivery is not supported, Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="a1f52-147">Het afleveren van e-mailberichten met bijlagen die URL's bevatten, wordt echter gecontroleerd, afhankelijk van hoe uw [ATP-beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="a1f52-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="a1f52-148">In dergelijke gevallen worden URL's in e-mailberichten en Office-bestanden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="a1f52-148">In these cases, URLs in email messages and Office files are checked.</span></span>
