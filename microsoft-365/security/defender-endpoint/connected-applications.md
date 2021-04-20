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
ms.openlocfilehash: 26c531c0544f92d664bfa0f1a21e4f33a0765d24
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893495"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Verbonden toepassingen in Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Verbonden toepassingen worden geïntegreerd met het Defender for Endpoint-platform met API's. 

Toepassingen gebruiken standaard OAuth 2.0-protocol om tokens te verifiëren en aan te bieden voor gebruik met Microsoft Defender voor eindpunt-API's.  Daarnaast kunnen tenantbeheerders met Azure Active Directory-toepassingen (Azure Ad) expliciet bepalen welke API's met de bijbehorende app kunnen worden gebruikt.
 
U moet deze stappen volgen [om](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) de API's te gebruiken met de verbonden toepassing.
 
## <a name="access-the-connected-application-page"></a>De pagina verbonden toepassing openen
Selecteer in het linkernavigatiemenu **Partners & API's verbonden**  >  **AAD-toepassingen.**

 
## <a name="view-connected-application-details"></a>Verbonden toepassingsgegevens weergeven
De pagina Verbonden toepassingen bevat informatie over de Azure AD-toepassingen die zijn verbonden met Microsoft Defender voor Eindpunt in uw organisatie. U kunt het gebruik van de verbonden toepassingen bekijken: laatst gezien, het aantal aanvragen in de afgelopen 24 uur en trends aanvragen in de afgelopen 30 dagen.

![Afbeelding van verbonden apps](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Een verbonden toepassing bewerken, opnieuw configureren of verwijderen
Met **de koppeling Toepassingsinstellingen** openen wordt de bijbehorende pagina Azure AD-toepassingsbeheer geopend in de Azure-portal. Vanuit de Azure-portal kunt u machtigingen beheren, de verbonden toepassingen opnieuw configureren of verwijderen.
