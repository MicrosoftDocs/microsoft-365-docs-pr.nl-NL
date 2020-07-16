---
title: Toegang tot de beheerportal
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146265"
---
# <a name="access-the-admin-portal"></a>Toegang tot de beheerportal

Uw gateway naar de Microsoft Managed Desktop-service is de Microsoft [Azure-portal](https://portal.azure.com). Zie de [Azure-portaldocumentatie](https://docs.microsoft.com/azure/azure-portal/)voor meer informatie over het gebruik en aanpassen van uw Azure-portalervaring in het algemeen. 

Uw beheeraccount heeft specifieke machtigingen nodig om toegang te krijgen tot de Microsoft Managed Desktop Admin-portal. U de toegang van beheerders tot deze functies binnen uw organisatie beheren met behulp van Role-based Access Control (RBAC). Zie [Machtigingen administratorrol in Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)meer informatie over Azure Active Directory-rollen.

Wijs uw beheerdersaccounts een van de volgende rollen toe om toegang te garanderen:

|Azure AD-rol  |Machtigingen voor Microsoft Managed Desktop  |
|---------|---------|
|Globale beheerder     | Beheerders met deze rol hebben **lees- en schrijfmachtigingen** voor alle functies in de Microsoft Managed Desktop Admin-portal.         |
|Global Reader     | Beheerders met deze rol hebben **alleen-lezen machtigingen** voor alle functies in de Microsoft Managed Desktop Admin-portal.         |
|Intune-servicebeheerder     |  Beheerders met deze rol hebben **lees- en schrijfmachtigingen** voor alle functies in de Microsoft Managed Desktop Admin-portal.       |
|Beheerder van serviceondersteuning     | Beheerders met deze rol hebben **lees- en schrijfmachtigingen** voor alle functies in de Microsoft Managed Desktop Admin-portal.         |

> [!IMPORTANT]
> Alleen de rol Global Administrator heeft de benodigde machtigingen om uw organisatie in te *schrijven* in Microsoft Managed Desktop. Houd er rekening mee dat Azure Active Directory-rollen gebruikersaccounts bevoegdheden geven voor verschillende Microsoft-services. Nadat u de inschrijving bij Microsoft Managed Desktop hebt voltooid, moet u altijd de rol gebruiken met de *minste* bevoegdheden die nodig zijn om uw andere taken uit te voeren.

## <a name="assigning-roles-to-administrators"></a>Rollen toewijzen aan beheerders

Zie [Machtigingen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor beheerdersrol in Azure Active Directory als u hulp nodig hebt bij het toewijzen van Azure Active Directory-rollen.
