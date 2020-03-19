---
title: Criteria voor het afsluiten van infrastructuur voor mobiele apparaten
description: Microsoft 365 Enterprise omvat beheer van mobiele apparaten met Microsoft Intune. Bekijk de vereisten en vereisten, stel Intune in met uw Azure Active Directory-bron, schrijf iOS-, macOS-, Android- en Windows-apparaten in, implementeer apps, maak een profiel configureren, gebruik een nalevingsbeleid en schakel Voorwaardelijke toegang in voor mobiel apparaatbeheer met Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, beheer van mobiele apparaten, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806610"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="87da9-105">Criteria voor het afsluiten van infrastructuur voor mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="87da9-105">Mobile device management infrastructure exit criteria</span></span>

![Fase 5: Beheer van mobiele apparaten](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="87da9-107">*Dit geldt voor de E3- en E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="87da9-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="87da9-108">Zorg ervoor dat uw configuratie voldoet aan de volgende vereisten voor infrastructuur voor het beheer van mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="87da9-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="87da9-109">Intune is ingesteld, inclusief het maken van Azure Active Directory -gebruikers en groepen (Azure AD) om de regels van uw organisatie toe te passen voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="87da9-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="87da9-110">U hebt apparaten ingeschreven in Intune, zodat de apparaten het beleid kunnen ontvangen dat u maakt.</span><span class="sxs-lookup"><span data-stu-id="87da9-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="87da9-111">Apps worden toegevoegd aan apparaten, zodat uw gebruikers toegang krijgen tot de Microsoft 365-cloudservices van uw organisatie, zoals Exchange Online en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="87da9-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="87da9-112">Functies en instellingen worden geconfigureerd en toegepast op uw apparaten met behulp van de Azure AD-gebruikers en groepen die u maakt, waaronder het inschakelen van anti-virus en het beperken van specifieke apps.</span><span class="sxs-lookup"><span data-stu-id="87da9-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="87da9-113">Er zijn nalevingsbeleidsregels vereist om een firewall of een wachtwoordlengte op een apparaat te vereisen.</span><span class="sxs-lookup"><span data-stu-id="87da9-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="87da9-114">Als apparaten niet compatibel zijn, blokkeert Voorwaardelijke toegang de toegang tot de gegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="87da9-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="87da9-115">Resultaten en volgende stappen</span><span class="sxs-lookup"><span data-stu-id="87da9-115">Results and next steps</span></span>

<span data-ttu-id="87da9-116">Uw apparaten zijn ingeschreven in Intune en geconfigureerd met het juiste beleid.</span><span class="sxs-lookup"><span data-stu-id="87da9-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![Fase 6: Informatiebescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="87da9-118">Als u de fasen voor de end-to-end implementatie van Microsoft 365 Enterprise volgt, is uw volgende fase [informatiebeveiliging.](infoprotect-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="87da9-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
