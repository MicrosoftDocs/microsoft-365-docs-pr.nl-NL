---
title: Verbonden toepassingen in Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: Bekijk verbonden partnertoepassingen die gebruikmaken van het standaard OAuth 2.0-protocol voor verificatie en het verstrekken van tokens voor gebruik met Microsoft Defender voor eindpunt-API's.
keywords: partners, toepassingen, derden, verbindingen, schildwachten, lookout, bitdefender, corrata, morphisec, paloalto, ziften, beter mobiel
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
ms.technology: mde
ms.openlocfilehash: 4b212acdf4bdf8fa53ef00763463190e204fc1ed
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339164"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="db0e1-104">Verbonden toepassingen in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="db0e1-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db0e1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="db0e1-105">**Applies to:**</span></span>
- [<span data-ttu-id="db0e1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="db0e1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db0e1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db0e1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="db0e1-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="db0e1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="db0e1-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="db0e1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="db0e1-110">Verbonden toepassingen worden geïntegreerd met het Defender for Endpoint-platform met API's.</span><span class="sxs-lookup"><span data-stu-id="db0e1-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="db0e1-111">Toepassingen gebruiken standaard OAuth 2.0-protocol om tokens te verifiëren en aan te bieden voor gebruik met Microsoft Defender voor eindpunt-API's.</span><span class="sxs-lookup"><span data-stu-id="db0e1-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="db0e1-112">Bovendien kunnen tenantbeheerders Azure Active Directory (Azure AD)-toepassingen expliciet bepalen welke API's met de bijbehorende app kunnen worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="db0e1-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="db0e1-113">U moet deze stappen volgen [om](/microsoft-365/security/defender-endpoint/apis-intro) de API's te gebruiken met de verbonden toepassing.</span><span class="sxs-lookup"><span data-stu-id="db0e1-113">You'll need to follow [these steps](/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="db0e1-114">De pagina verbonden toepassing openen</span><span class="sxs-lookup"><span data-stu-id="db0e1-114">Access the connected application page</span></span>
<span data-ttu-id="db0e1-115">Selecteer in het linkernavigatiemenu **Endpoints**  >  **Partners en API's**  >  **Verbonden toepassingen.**</span><span class="sxs-lookup"><span data-stu-id="db0e1-115">From the left navigation menu, select **Endpoints** > **Partners and APIs** > **Connected applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="db0e1-116">Verbonden toepassingsgegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="db0e1-116">View connected application details</span></span>
<span data-ttu-id="db0e1-117">De pagina Verbonden toepassingen bevat informatie over de Azure AD-toepassingen die zijn verbonden met Microsoft Defender voor Eindpunt in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="db0e1-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="db0e1-118">U kunt het gebruik van de verbonden toepassingen bekijken: laatst gezien, het aantal aanvragen in de afgelopen 24 uur en trends aanvragen in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="db0e1-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![Afbeelding van verbonden apps](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="db0e1-120">Een verbonden toepassing bewerken, opnieuw configureren of verwijderen</span><span class="sxs-lookup"><span data-stu-id="db0e1-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="db0e1-121">Met **de koppeling Toepassingsinstellingen** openen wordt de bijbehorende pagina Azure AD-toepassingsbeheer geopend in de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="db0e1-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="db0e1-122">Vanuit de Azure-portal kunt u machtigingen beheren, de verbonden toepassingen opnieuw configureren of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db0e1-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
