---
title: Potentieel ongewenste toepassingen detecteren en blokkeren met Microsoft Defender voor Eindpunt op Mac
description: Detecteer en blokkeer potentieel ongewenste toepassingen (PUA) met Microsoft Defender op Endpoint voor Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2d32dd96cd506ebf1752e48d2b7c66208b1abc11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934535"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d7653-104">Potentieel ongewenste toepassingen detecteren en blokkeren met Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="d7653-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d7653-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d7653-105">**Applies to:**</span></span>
- [<span data-ttu-id="d7653-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d7653-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d7653-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7653-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d7653-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d7653-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d7653-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d7653-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="d7653-110">De potentieel ongewenste beveiligingsfunctie voor toepassingen (PUA) in Microsoft Defender voor Eindpunt op macOS kan PUA-bestanden op eindpunten in uw netwerk detecteren en blokkeren.</span><span class="sxs-lookup"><span data-stu-id="d7653-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint on macOS can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="d7653-111">Deze toepassingen worden niet beschouwd als virussen, malware of andere soorten bedreigingen, maar kunnen acties uitvoeren op eindpunten die de prestaties of het gebruik ervan nadelig beïnvloeden.</span><span class="sxs-lookup"><span data-stu-id="d7653-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="d7653-112">PUA kan ook verwijzen naar toepassingen die worden beschouwd als een slechte reputatie.</span><span class="sxs-lookup"><span data-stu-id="d7653-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="d7653-113">Deze toepassingen kunnen het risico vergroten dat uw netwerk wordt geïnfecteerd met malware, dat malware-infecties moeilijker te identificeren zijn en dat it-resources worden verspild bij het opruimen van de toepassingen.</span><span class="sxs-lookup"><span data-stu-id="d7653-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="d7653-114">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="d7653-114">How it works</span></span>

<span data-ttu-id="d7653-115">Microsoft Defender voor Eindpunt op macOS kan PUA-bestanden detecteren en rapporteren.</span><span class="sxs-lookup"><span data-stu-id="d7653-115">Microsoft Defender for Endpoint on macOS can detect and report PUA files.</span></span> <span data-ttu-id="d7653-116">Wanneer het bestand is geconfigureerd in de blokkeringsmodus, worden PUA-bestanden verplaatst naar de quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d7653-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="d7653-117">Wanneer een PUA wordt gedetecteerd op een eindpunt, wordt in Microsoft Defender voor Eindpunt in macOS een melding aan de gebruiker voorgemeld, tenzij meldingen zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d7653-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint on macOS presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="d7653-118">De bedreigingsnaam bevat het woord 'Toepassing'.</span><span class="sxs-lookup"><span data-stu-id="d7653-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="d7653-119">PUA-beveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="d7653-119">Configure PUA protection</span></span>

<span data-ttu-id="d7653-120">PUA-beveiliging in Microsoft Defender voor Eindpunt op macOS kan op een van de volgende manieren worden geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="d7653-120">PUA protection in Microsoft Defender for Endpoint on macOS can be configured in one of the following ways:</span></span>

- <span data-ttu-id="d7653-121">**Uit:** PUA-beveiliging is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d7653-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="d7653-122">**Audit:** PUA-bestanden worden gerapporteerd in de productlogboeken, maar niet in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d7653-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="d7653-123">Er wordt geen melding weergegeven aan de gebruiker en er wordt geen actie ondernomen door het product.</span><span class="sxs-lookup"><span data-stu-id="d7653-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="d7653-124">**Blokkeren:** PUA-bestanden worden gerapporteerd in de productlogboeken en in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d7653-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="d7653-125">De gebruiker krijgt een melding te zien en er wordt actie ondernomen door het product.</span><span class="sxs-lookup"><span data-stu-id="d7653-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="d7653-126">Pua-beveiliging is standaard geconfigureerd in de **auditmodus.**</span><span class="sxs-lookup"><span data-stu-id="d7653-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="d7653-127">U kunt configureren hoe PUA-bestanden worden verwerkt vanaf de opdrachtregel of vanaf de beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="d7653-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="d7653-128">Gebruik het opdrachtregelhulpmiddel om PUA-beveiliging te configureren:</span><span class="sxs-lookup"><span data-stu-id="d7653-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="d7653-129">Voer in Terminal de volgende opdracht uit om PUA-beveiliging te configureren:</span><span class="sxs-lookup"><span data-stu-id="d7653-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="d7653-130">Gebruik de beheerconsole om PUA-beveiliging te configureren:</span><span class="sxs-lookup"><span data-stu-id="d7653-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="d7653-131">In uw bedrijf kunt u PUA-beveiliging configureren vanuit een beheerconsole, zoals JAMF of Intune, net zoals andere productinstellingen zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="d7653-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="d7653-132">Zie de sectie Instellingen voor [bedreigingstype](mac-preferences.md#threat-type-settings) van het onderwerp Voorkeuren instellen voor [Microsoft Defender voor Eindpunt voor macOS voor meer](mac-preferences.md) informatie.</span><span class="sxs-lookup"><span data-stu-id="d7653-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d7653-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d7653-133">Related topics</span></span>

- [<span data-ttu-id="d7653-134">Voorkeuren instellen voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="d7653-134">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>](mac-preferences.md)
