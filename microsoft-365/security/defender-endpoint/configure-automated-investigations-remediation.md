---
title: Geautomatiseerde onderzoeks- en herstelmogelijkheden configureren
description: Uw geautomatiseerde onderzoeks- en herstelmogelijkheden instellen in Microsoft Defender voor Eindpunt.
keywords: configureren, instellen, geautomatiseerd, onderzoek, detectie, waarschuwingen, herstel, antwoord
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841328"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="81779-104">Geautomatiseerde onderzoeks- en herstelmogelijkheden configureren in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="81779-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="81779-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="81779-105">**Applies to:**</span></span>
- [<span data-ttu-id="81779-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="81779-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="81779-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81779-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="81779-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="81779-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="81779-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="81779-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="81779-110">Als uw organisatie [Microsoft Defender voor Eindpunt](/windows/security/threat-protection/) (Defender voor Eindpunt) gebruikt, kunnen geautomatiseerde onderzoeks- en herstelmogelijkheden uw beveiligingsbewerkingen tijd en moeite besparen. [](/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="81779-110">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="81779-111">Zoals in dit [blogbericht](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)wordt beschreven, bootsen deze mogelijkheden de ideale stappen na die een beveiligingsanalist neemt om bedreigingen te onderzoeken en te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="81779-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="81779-112">[Meer informatie over geautomatiseerd onderzoek en herstel](/microsoft-365/security/defender-endpoint/automated-investigations).</span><span class="sxs-lookup"><span data-stu-id="81779-112">[Learn more about automated investigation and remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="81779-113">Als u geautomatiseerd onderzoek en herstel wilt configureren,</span><span class="sxs-lookup"><span data-stu-id="81779-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="81779-114">[De functies in- en uit-](#turn-on-automated-investigation-and-remediation) en</span><span class="sxs-lookup"><span data-stu-id="81779-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="81779-115">[Apparaatgroepen instellen.](#set-up-device-groups)</span><span class="sxs-lookup"><span data-stu-id="81779-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="81779-116">Automatisch onderzoek en herstel in- en uit-</span><span class="sxs-lookup"><span data-stu-id="81779-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="81779-117">Ga als globale beheerder of beveiligingsbeheerder naar de Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="81779-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="81779-118">Kies in het **navigatiedeelvenster Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="81779-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="81779-119">Selecteer geavanceerde functies in **de** sectie **Algemeen.**</span><span class="sxs-lookup"><span data-stu-id="81779-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="81779-120">Schakel zowel Automatisch **onderzoek als** Waarschuwingen automatisch **oplossen in.**</span><span class="sxs-lookup"><span data-stu-id="81779-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="81779-121">Apparaatgroepen instellen</span><span class="sxs-lookup"><span data-stu-id="81779-121">Set up device groups</span></span>

1. <span data-ttu-id="81779-122">Selecteer in Microsoft Defender-beveiligingscentrum ( ) op Instellingen pagina [https://securitycenter.windows.com](https://securitycenter.windows.com) onder Machtigingen de optie **Apparaatgroepen**. </span><span class="sxs-lookup"><span data-stu-id="81779-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="81779-123">Selecteer **+ Apparaatgroep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="81779-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="81779-124">Maak ten minste één apparaatgroep als volgt:</span><span class="sxs-lookup"><span data-stu-id="81779-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="81779-125">Geef een naam en beschrijving op voor de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="81779-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="81779-126">Selecteer in **de lijst Automatiseringsniveau** een niveau, zoals **Volledig, om bedreigingen automatisch te corrigeren.**</span><span class="sxs-lookup"><span data-stu-id="81779-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="81779-127">Het automatiseringsniveau bepaalt of herstelacties automatisch worden ondernomen of alleen na goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="81779-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="81779-128">Zie Automatiseringsniveaus in geautomatiseerd onderzoek en herstel [voor meer informatie.](automation-levels.md)</span><span class="sxs-lookup"><span data-stu-id="81779-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="81779-129">Gebruik in **de sectie** Leden een of meer voorwaarden om apparaten te identificeren en op te nemen.</span><span class="sxs-lookup"><span data-stu-id="81779-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="81779-130">Selecteer op **het tabblad** Gebruikerstoegang de [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) groepen die toegang moeten hebben tot de apparaatgroep die u maakt.</span><span class="sxs-lookup"><span data-stu-id="81779-130">On the **User access** tab, select the [Azure Active Directory groups](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="81779-131">Selecteer **Gereed** wanneer u klaar bent met het instellen van uw apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="81779-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="81779-132">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="81779-132">Next steps</span></span>

- [<span data-ttu-id="81779-133">Ga naar het Actiecentrum om in behandeling zijnde en voltooide herstelacties te bekijken</span><span class="sxs-lookup"><span data-stu-id="81779-133">Visit the Action Center to view pending and completed remediation actions</span></span>](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="81779-134">Lopende acties controleren en goedkeuren</span><span class="sxs-lookup"><span data-stu-id="81779-134">Review and approve pending actions</span></span>](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="81779-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="81779-135">See also</span></span>

- [<span data-ttu-id="81779-136">Actie ondernemen voor fout-positieven/-negatieven in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="81779-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
