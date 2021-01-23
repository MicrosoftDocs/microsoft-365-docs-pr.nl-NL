---
title: Microsoft Defender voor Office 365 samen met Microsoft Defender voor eindpunt gebruiken
f1.keywords:
- NOCSH
keywords: integreren, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Gebruik Microsoft Defender voor Office 365 samen met Microsoft Defender for Endpoint voor meer informatie over bedreigingen voor uw apparaten en e-mail inhoud.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24b81bb4c445c44d7c0228fa1c4440faff642816
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939330"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="596d4-104">Microsoft Defender voor Office 365 samen met Microsoft Defender voor eindpunt gebruiken</span><span class="sxs-lookup"><span data-stu-id="596d4-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="596d4-105">[Microsoft Defender voor Office 365](office-365-atp.md) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="596d4-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="596d4-106">Integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor eindpunten kan uw beheer van beveiligingsactiviteiten ondersteunen en snel actie ondernemen als de apparaten van de gebruikers risico lopen.</span><span class="sxs-lookup"><span data-stu-id="596d4-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="596d4-107">Wanneer de integratie is ingeschakeld, kunnen uw beveiligingsteam bijvoorbeeld de apparaten zien die van invloed zijn op het gedetecteerde e-mailbericht, en het aantal recente waarschuwingen voor deze apparaten in Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="596d4-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="596d4-108">In de volgende afbeelding wordt getoond waarop op het tabblad **apparaten** de integratie met Microsoft Defender voor eindpunten is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="596d4-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wanneer Microsoft Defender for Endpoint is ingeschakeld, kunt u een lijst met apparaten met waarschuwingen weergeven.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="596d4-110">In dit voorbeeld ziet u dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en dat er een waarschuwing is.</span><span class="sxs-lookup"><span data-stu-id="596d4-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="596d4-111">Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender-Beveiligingscentrum <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="596d4-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="596d4-112">Meer **[informatie over het Microsoft Defender-Beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel Microsoft Defender for Endpoint Portal genoemd).</span><span class="sxs-lookup"><span data-stu-id="596d4-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="596d4-113">Vereisten</span><span class="sxs-lookup"><span data-stu-id="596d4-113">Requirements</span></span>

- <span data-ttu-id="596d4-114">Uw organisatie moet Microsoft Defender voor Office 365 (of Office 365 E5) en Microsoft Defender voor eindpunten hebben.</span><span class="sxs-lookup"><span data-stu-id="596d4-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="596d4-115">U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder, zoals beveiligingsbeheerder, hebben toegewezen in het [beveiligings & nalevings centrum](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="596d4-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="596d4-116">(Zie [machtigingen in de beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="596d4-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="596d4-117">U moet in de beveiligings & nalevings centrum en het Microsoft Defender-Beveiligingscentrum toegang hebben tot zowel de [Verkenner (of realtime detectie)](threat-explorer.md) .</span><span class="sxs-lookup"><span data-stu-id="596d4-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="596d4-118">Microsoft Defender voor Office 365 integreren met Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="596d4-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="596d4-119">Integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor eindpunt is ingesteld met behulp van het beveiligings & nalevings centrum en het Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="596d4-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="596d4-120">Ga als globale beheerder of een beveiligingsbeheerder naar <https://protection.office.com> en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="596d4-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="596d4-121">(U gaat nu naar het Beveiligingscentrum van Office 365 & nalevings centrum.)</span><span class="sxs-lookup"><span data-stu-id="596d4-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="596d4-122">Kies in het navigatiedeelvenster de optie **Threat Management** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="596d4-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Verkenner in het menu Threat Management](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="596d4-124">Kies in de rechterbovenhoek van het scherm de optie **Defender voor eindpunten (MDE-instellingen)**.</span><span class="sxs-lookup"><span data-stu-id="596d4-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="596d4-125">Schakel in het dialoogvenster Microsoft Defender for Endpoint verbinding het selectievakje **verbinding maken met Microsoft Defender voor eindpunt** in.</span><span class="sxs-lookup"><span data-stu-id="596d4-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender voor eindpunt verbinding](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="596d4-127">Ga naar het Microsoft Defender-Beveiligingscentrum ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="596d4-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="596d4-128">Kies in de navigatiebalk de optie **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="596d4-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="596d4-129">Kies vervolgens onder **Algemeen** **geavanceerde functies**.</span><span class="sxs-lookup"><span data-stu-id="596d4-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="596d4-130">Schuif omlaag naar **Office 365 Threat Intelligence-verbinding** en zet de verbinding aan.</span><span class="sxs-lookup"><span data-stu-id="596d4-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 Threat Intelligence-verbinding](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="596d4-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="596d4-132">Related articles</span></span>

[<span data-ttu-id="596d4-133">Oplossing voor onderzoek en antwoord van bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="596d4-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="596d4-134">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="596d4-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="596d4-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="596d4-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
