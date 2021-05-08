---
title: Compatibiliteit met antivirusoplossingen met Defender voor Eindpunt
description: Meer informatie over hoe Windows Defender werkt met Microsoft Defender voor Eindpunt en hoe deze werkt wanneer een antimalwareclient van derden wordt gebruikt.
keywords: windows defender compatibility, defender, Microsoft Defender for Endpoint, defender for endpoint, antivirus, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: 84c523b721596d9c467f01cf6b8a0685b2091669
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274878"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="aced1-104">Compatibiliteit met antivirusoplossingen met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="aced1-104">Antivirus solution compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aced1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aced1-105">**Applies to:**</span></span>
- [<span data-ttu-id="aced1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="aced1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aced1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aced1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="aced1-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="aced1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aced1-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="aced1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="aced1-110">De Microsoft Defender voor Eindpunt-agent is afhankelijk van Microsoft Defender Antivirus voor bepaalde mogelijkheden, zoals bestandsscans.</span><span class="sxs-lookup"><span data-stu-id="aced1-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="aced1-111">Defender voor Eindpunt voldoet niet aan de instellingen voor Microsoft Defender Antivirus Exclusions.</span><span class="sxs-lookup"><span data-stu-id="aced1-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="aced1-112">U moet beveiligingsintelligentie-updates configureren op de Defender voor Eindpunt-apparaten, ongeacht of Microsoft Defender Antivirus de actieve antimalware is of niet.</span><span class="sxs-lookup"><span data-stu-id="aced1-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="aced1-113">Zie Microsoft [Defender Antivirus-updates](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)beheren en basislijnen toepassen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aced1-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="aced1-114">Als een onboarded-apparaat is beveiligd door een antimalwareclient van derden, gaat Microsoft Defender Antivirus op dat eindpunt in de passieve modus.</span><span class="sxs-lookup"><span data-stu-id="aced1-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="aced1-115">Microsoft Defender Antivirus blijft updates ontvangen en het *mspeng.exe-proces* wordt weergegeven als een service die wordt uitgevoerd, maar er worden geen scans uitgevoerd en de lopende antimalwareclient van derden wordt niet vervangen.</span><span class="sxs-lookup"><span data-stu-id="aced1-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="aced1-116">De Microsoft Defender Antivirus-interface wordt uitgeschakeld en gebruikers op het apparaat kunnen Microsoft Defender Antivirus niet gebruiken om on-demand scans uit te voeren of de meeste opties te configureren.</span><span class="sxs-lookup"><span data-stu-id="aced1-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="aced1-117">Zie het onderwerp [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic (Microsoft Defender Antivirus and Defender for Endpoint compatibility topic) voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="aced1-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
