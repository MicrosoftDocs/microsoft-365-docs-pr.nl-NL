---
title: Gebruikerstoegang toewijzen aan Microsoft Defender-beveiligingscentrum
description: Wijs alleen lees- en schrijf- of leestoegang toe aan de Microsoft Defender for Endpoint-portal.
keywords: gebruikersrollen toewijzen, lees- en schrijftoegang toewijzen, alleen-lezentoegang toewijzen, gebruiker, gebruikersrollen, rollen
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
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164753"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Gebruikerstoegang toewijzen aan Microsoft Defender-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Azure Active Directory
- Office 365
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender voor Eindpunt ondersteunt twee manieren om machtigingen te beheren:

- **Beheer van basismachtigingen:** Machtigingen instellen voor volledige toegang of alleen-lezen.
- **RBAC (Role-based Access Control)**: Stel granulaire machtigingen in door rollen te definiëren, Gebruikersgroepen van Azure AD toe te wijzen aan de rollen en gebruikersgroepen toegang te verlenen tot apparaatgroepen. Zie Portaltoegang beheren met behulp van op rollen [gebaseerd toegangsbeheer](rbac.md)voor meer informatie over RBAC.

> [!NOTE]
> Als u al basismachtigingen hebt toegewezen, kunt u op elk gewenst moment overschakelen naar RBAC. Houd rekening met het volgende voordat u overschakelt:
> 
> - Gebruikers met volledige toegang (gebruikers die de directoryrol globale beheerder of beveiligingsbeheerder in Azure AD hebben toegewezen), krijgen automatisch de standaardrol van de Defender voor eindpuntbeheerder toegewezen, die ook volledige toegang heeft. Extra Azure AD-gebruikersgroepen kunnen worden toegewezen aan de beheerdersrol van Defender voor Eindpunt nadat u bent overstappen op RBAC.  Alleen gebruikers die zijn toegewezen aan de beheerdersrol van Defender voor Eindpunt, kunnen machtigingen beheren met RBAC. 
> - Gebruikers met alleen-lezentoegang (beveiligingslezers) hebben geen toegang meer tot de portal totdat ze een rol krijgen toegewezen. Houd er rekening mee dat alleen Azure AD-gebruikersgroepen een rol kunnen worden toegewezen onder RBAC.
> - Nadat u bent overschakelt naar RBAC, kunt u niet meer teruggaan naar basismachtigingenbeheer.

## <a name="related-topics"></a>Verwante onderwerpen

- [Basismachtigingen gebruiken voor toegang tot de portal](basic-permissions.md)
- [Portaltoegang beheren met RBAC](rbac.md)
