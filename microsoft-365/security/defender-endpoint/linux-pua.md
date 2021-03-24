---
title: Potentieel ongewenste toepassingen detecteren en blokkeren met Microsoft Defender ATP voor Linux
description: Detecteer en blokkeer potentieel ongewenste toepassingen (PUA) met Microsoft Defender ATP voor Linux.
keywords: microsoft, defender, atp, linux, pua, pus
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
ms.openlocfilehash: af4d1a548d34e1a9974ce5d4a6a32361d14d3548
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059126"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="dc79a-104">Potentieel ongewenste toepassingen detecteren en blokkeren met Microsoft Defender voor Eindpunt voor Linux</span><span class="sxs-lookup"><span data-stu-id="dc79a-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dc79a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="dc79a-105">**Applies to:**</span></span>
- [<span data-ttu-id="dc79a-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc79a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="dc79a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc79a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dc79a-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="dc79a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dc79a-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="dc79a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="dc79a-110">De mogelijk ongewenste beveiligingsfunctie voor toepassingen (PUA) in Defender voor Eindpunt voor Linux kan PUA-bestanden op eindpunten in uw netwerk detecteren en blokkeren.</span><span class="sxs-lookup"><span data-stu-id="dc79a-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint for Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="dc79a-111">Deze toepassingen worden niet beschouwd als virussen, malware of andere soorten bedreigingen, maar kunnen acties uitvoeren op eindpunten die de prestaties of het gebruik ervan nadelig beïnvloeden.</span><span class="sxs-lookup"><span data-stu-id="dc79a-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="dc79a-112">PUA kan ook verwijzen naar toepassingen die worden beschouwd als een slechte reputatie.</span><span class="sxs-lookup"><span data-stu-id="dc79a-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="dc79a-113">Deze toepassingen kunnen het risico vergroten dat uw netwerk wordt geïnfecteerd met malware, dat malware-infecties moeilijker te identificeren zijn en dat it-resources worden verspild bij het opruimen van de toepassingen.</span><span class="sxs-lookup"><span data-stu-id="dc79a-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="dc79a-114">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="dc79a-114">How it works</span></span>

<span data-ttu-id="dc79a-115">Defender voor Eindpunt voor Linux kan PUA-bestanden detecteren en rapporteren.</span><span class="sxs-lookup"><span data-stu-id="dc79a-115">Defender for Endpoint for Linux can detect and report PUA files.</span></span> <span data-ttu-id="dc79a-116">Wanneer het bestand is geconfigureerd in de blokkeringsmodus, worden PUA-bestanden verplaatst naar de quarantaine.</span><span class="sxs-lookup"><span data-stu-id="dc79a-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="dc79a-117">Wanneer een PUA wordt gedetecteerd op een eindpunt, houdt Defender voor Endpoint voor Linux een record bij van de infectie in de bedreigingsgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="dc79a-117">When a PUA is detected on an endpoint, Defender for Endpoint for Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="dc79a-118">De geschiedenis kan worden gevisualiseerd vanuit de Microsoft Defender-beveiligingscentrumportal of via het `mdatp` opdrachtregelprogramma.</span><span class="sxs-lookup"><span data-stu-id="dc79a-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="dc79a-119">De bedreigingsnaam bevat het woord 'Toepassing'.</span><span class="sxs-lookup"><span data-stu-id="dc79a-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="dc79a-120">PUA-beveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="dc79a-120">Configure PUA protection</span></span>

<span data-ttu-id="dc79a-121">PUA-beveiliging in Defender voor Endpoint voor Linux kan op een van de volgende manieren worden geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="dc79a-121">PUA protection in Defender for Endpoint for Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="dc79a-122">**Uit:** PUA-beveiliging is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="dc79a-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="dc79a-123">**Audit:** PUA-bestanden worden gerapporteerd in de productlogboeken, maar niet in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="dc79a-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="dc79a-124">Er wordt geen record van de infectie opgeslagen in de bedreigingsgeschiedenis en er wordt geen actie ondernomen door het product.</span><span class="sxs-lookup"><span data-stu-id="dc79a-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="dc79a-125">**Blokkeren:** PUA-bestanden worden gerapporteerd in de productlogboeken en in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="dc79a-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="dc79a-126">Een record van de infectie wordt opgeslagen in de bedreigingsgeschiedenis en er wordt actie ondernomen door het product.</span><span class="sxs-lookup"><span data-stu-id="dc79a-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="dc79a-127">Pua-beveiliging is standaard geconfigureerd in de **auditmodus.**</span><span class="sxs-lookup"><span data-stu-id="dc79a-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="dc79a-128">U kunt configureren hoe PUA-bestanden worden verwerkt vanaf de opdrachtregel of vanaf de beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="dc79a-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="dc79a-129">Gebruik het opdrachtregelhulpmiddel om PUA-beveiliging te configureren:</span><span class="sxs-lookup"><span data-stu-id="dc79a-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="dc79a-130">Voer in Terminal de volgende opdracht uit om PUA-beveiliging te configureren:</span><span class="sxs-lookup"><span data-stu-id="dc79a-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="dc79a-131">Gebruik de beheerconsole om PUA-beveiliging te configureren:</span><span class="sxs-lookup"><span data-stu-id="dc79a-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="dc79a-132">In uw bedrijf kunt u PUA-beveiliging configureren vanuit een beheerconsole, zoals Poppenkast of Ansible, net zoals andere productinstellingen zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="dc79a-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="dc79a-133">Zie de sectie Instellingen voor [bedreigingstype](linux-preferences.md#threat-type-settings) van het artikel Voorkeuren instellen voor [Defender voor eindpunt voor Linux voor meer](linux-preferences.md) informatie.</span><span class="sxs-lookup"><span data-stu-id="dc79a-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint for Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dc79a-134">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="dc79a-134">Related articles</span></span>

- [<span data-ttu-id="dc79a-135">Voorkeuren instellen voor Defender voor Eindpunt voor Linux</span><span class="sxs-lookup"><span data-stu-id="dc79a-135">Set preferences for Defender for Endpoint for Linux</span></span>](linux-preferences.md)
