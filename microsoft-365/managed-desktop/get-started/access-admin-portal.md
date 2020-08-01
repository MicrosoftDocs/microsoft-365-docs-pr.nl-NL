---
title: Ga naar de beheerdersportal
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 420cdaabb607eacf0d7a7109827fe5437e2f999c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530221"
---
# <a name="access-the-admin-portal"></a>Toegang tot de beheerportal

Uw gateway naar de Microsoft Managed Desktop-service is de Microsoft [Azure-portal](https://portal.azure.com). Zie de [Azure-portaldocumentatie](https://docs.microsoft.com/azure/azure-portal/)voor meer informatie over het gebruik en aanpassen van uw Azure-portalervaring in het algemeen. Nu beschikbaar in preview, u ook Microsoft Managed Desktop vinden in [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Als u niet bekend bent met de mogelijkheden van deze portal voor apparaatbeheer, raadpleegt u de [documentatie van Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

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
