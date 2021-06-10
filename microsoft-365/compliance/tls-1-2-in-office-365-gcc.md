---
title: TLS 1.0 en 1.1 uitschakelen in Microsoft 365 GCC Hoog en DoD
description: Bespreekt hoe Microsoft ondersteuning voor TLS 1.1 en 1.0 in GCC High- en DoD-omgevingen in Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161963"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a><span data-ttu-id="71144-103">TLS 1.0 en 1.1 uitschakelen in Microsoft 365 GCC Hoog en DoD</span><span class="sxs-lookup"><span data-stu-id="71144-103">Disabling TLS 1.0 and 1.1 in Microsoft 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="71144-104">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="71144-104">Summary</span></span>

<span data-ttu-id="71144-105">Om te voldoen aan de meest recente nalevingsstandaarden voor het Federal Risk and Authorization Management Program (FedRAMP), worden de TLS-versies (Transport Layer Security) 1.1 en 1.0 in Microsoft 365 voor GCC High- en DoD-omgevingen uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="71144-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="71144-106">Deze wijziging is eerder aangekondigd via Microsoft Ondersteuning bij Het voorbereiden van het verplichte gebruik van [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="71144-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="71144-107">De beveiliging van uw gegevens is belangrijk en we willen transparantie over wijzigingen die van invloed kunnen zijn op uw gebruik van de service.</span><span class="sxs-lookup"><span data-stu-id="71144-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="71144-108">Hoewel de [Implementatie van Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) geen bekende beveiligingsproblemen heeft, blijven we ons houden aan de nalevingsstandaarden van FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="71144-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="71144-109">Daarom hebben we TLS 1.1 en 1.0 uitgeschakeld in Microsoft 365 in GCC High- en DoD-omgevingen op 15 januari 2020.</span><span class="sxs-lookup"><span data-stu-id="71144-109">Therefore, we disabled TLS 1.1 and 1.0 in Microsoft 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="71144-110">Zie de volgende whitepaper voor informatie over het verwijderen van TLS 1.1- en 1.0-afhankelijkheden:</span><span class="sxs-lookup"><span data-stu-id="71144-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="71144-111">Het TLS 1.0-probleem oplossen</span><span class="sxs-lookup"><span data-stu-id="71144-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="71144-112">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="71144-112">More information</span></span>

<span data-ttu-id="71144-113">Vanaf 15 januari 2020 worden Microsoft 365 TLS 1.1 en 1.0 uitgeschakeld in de GCC High- en DoD-omgevingen.</span><span class="sxs-lookup"><span data-stu-id="71144-113">Starting on January 15, 2020, Microsoft 365 in the GCC High and DoD environments will disable TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="71144-114">Op 15 januari 2020 moeten alle combinaties van clientservers en browserservers gebruik maken van TLS-versie 1.2 (of een latere versie) om ervoor te zorgen dat alle verbindingen kunnen worden gemaakt zonder problemen met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71144-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Microsoft 365.</span></span> <span data-ttu-id="71144-115">Hiervoor zijn mogelijk updates nodig voor bepaalde combinaties van clientservers en browserservers.</span><span class="sxs-lookup"><span data-stu-id="71144-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="71144-116">Voor SharePoint en OneDrive moet u .NET bijwerken en configureren om TLS 1.2 te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="71144-116">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="71144-117">Zie [TLS 1.2 inschakelen](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="71144-117">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="71144-118">U moet uw clientcomputers bijwerken om ervoor te zorgen dat u ononderbroken toegang hebt tot Office 365 GCC High en DoD.</span><span class="sxs-lookup"><span data-stu-id="71144-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="71144-119">U moet toepassingen bijwerken die via TLS 1.0 Microsoft 365 TLS 1.1 of TLS 1.1 bellen om TLS 1.2 te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="71144-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="71144-120">.NET 4.5 is standaard ingesteld op TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="71144-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="71144-121">Zie Transport Layer Security [(TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients inschakelen als u uw .NET-configuratie wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="71144-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="71144-122">Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Office 365.</span><span class="sxs-lookup"><span data-stu-id="71144-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="71144-123">We weten dat in de volgende clienttoepassingen TLS 1.2 niet kan worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="71144-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="71144-124">Android 4.3 en eerdere versies</span><span class="sxs-lookup"><span data-stu-id="71144-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="71144-125">Firefox versie 5.0 en eerdere versies</span><span class="sxs-lookup"><span data-stu-id="71144-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="71144-126">Internet Explorer 8–10 op Windows 7 en eerdere versies</span><span class="sxs-lookup"><span data-stu-id="71144-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="71144-127">Internet Explorer 10 op Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="71144-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="71144-128">Safari 6.0.4/OS X 10.8.4 en eerdere versies</span><span class="sxs-lookup"><span data-stu-id="71144-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="71144-129">Hoewel uit de huidige analyse van verbindingen met Microsoft Online-services blijkt dat de meeste services en eindpunten zeer weinig TLS 1.1- en 1.0-gebruik zien, geven we deze wijziging door, zodat u alle getroffen clients of servers zo nodig kunt bijwerken voordat de ondersteuning voor TLS 1.1 en 1.0 eindigt.</span><span class="sxs-lookup"><span data-stu-id="71144-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="71144-130">Als u een on-premises infrastructuur gebruikt voor hybride scenario's of Active Directory Federation Services (AD FS), moet u ervoor zorgen dat de infrastructuur zowel binnenkomende als uitgaande verbindingen ondersteunt die gebruikmaken van TLS 1.2 (of een latere versie).</span><span class="sxs-lookup"><span data-stu-id="71144-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="71144-131">Naast de uitval die u mogelijk ervaart als u de vermelde clients gebruikt die TLS 1.2 niet kunnen gebruiken, voorkomt u dat u het volgende Microsoft-product kunt gebruiken door TLS 1.1 en 1.0 te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="71144-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="71144-132">Lync-telefoon</span><span class="sxs-lookup"><span data-stu-id="71144-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="71144-133">Verwijzingen</span><span class="sxs-lookup"><span data-stu-id="71144-133">References</span></span>

<span data-ttu-id="71144-134">Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Office 365 voor richtlijnen en verwijzingen om ervoor te zorgen dat uw klanten TLS 1.2 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="71144-134">For guidance and references to help make sure that your clients are using TLS 1.2, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>