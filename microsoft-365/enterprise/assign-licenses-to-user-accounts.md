---
title: Microsoft 365-licenties toewijzen aan gebruikersaccounts
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Hierin wordt beschreven hoe u Microsoft 365-licenties toewijst aan gebruikersaccounts, afzonderlijk of op basis van groepslidmaatschap.
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326505"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Microsoft 365-licenties toewijzen aan gebruikersaccounts

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Voor het identiteits model Cloud only kunt u Microsoft 365-licenties toewijzen aan gebruikersaccounts wanneer ze worden gemaakt, afhankelijk van hoe u ze maakt.

Wanneer gebruikersaccounts van Active Directory Domain Services (AD DS) voor de eerste keer worden gesynchroniseerd, worden er niet automatisch een locatie of een Microsoft 365-licentie toegewezen. **U moet elk gebruikersaccount configureren met een gebruikerslocatie, voorafgaand aan of samen met het toewijzen van een licentie.**

In beide gevallen moet u een licentie toewijzen aan gebruikersaccounts, zodat uw gebruikers toegang hebben tot Microsoft 365-Services, zoals e-mail en Microsoft teams.

U kunt licenties toewijzen aan gebruikersaccounts afzonderlijk of automatisch via groepslidmaatschap.

U kunt Microsoft 365-licenties toewijzen aan afzonderlijke gebruikersaccounts via:

- [Het Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Het Azure AD-Beheercentrum

## <a name="group-based-licensing"></a>Licenties op groepsbasis

U kunt beveiligingsgroepen configureren in azure AD om automatisch licenties toe te wijzen aan een reeks abonnementen voor alle leden van de groep. Dit wordt *licenties op groepsbasis* genoemd. Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. 

Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden. Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.

>[!Note]
>Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u licenties op groepsbasis niet te configureren.
>

Zie voor meer informatie over licenties op [groeps basis in azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Volgende stappen

Met de juiste set gebruikersaccounts waaraan een licentie is toegewezen, kunt u nu:

- [Beveiliging implementeren](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Clientsoftware installeren, zoals Microsoft 365-apps](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Apparaatbeheer instellen](device-management-roadmap-microsoft-365.md)
- [Services en toepassingen configureren](configure-services-and-applications.md)
