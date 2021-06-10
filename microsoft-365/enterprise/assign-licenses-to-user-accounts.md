---
title: Licenties Microsoft 365 gebruikersaccounts toewijzen
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
description: Hier wordt beschreven hoe u Microsoft 365 licenties toewijst aan gebruikersaccounts, afzonderlijk of op basis van groepslidmaatschap.
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051530"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Licenties Microsoft 365 gebruikersaccounts toewijzen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Voor het cloud-only-identiteitsmodel kunt u Microsoft 365 licenties toewijzen aan gebruikersaccounts terwijl deze worden gemaakt, afhankelijk van hoe u deze maakt.

Voor het hybride identiteitsmodel worden gebruikersaccounts van Active Directory Domain Services (AD DS) niet automatisch een locatie of een Microsoft 365 toegewezen. **U moet elk gebruikersaccount configureren met een gebruikerslocatie vóór of samen met het toewijzen van een licentie.**

In beide gevallen moet u een licentie toewijzen aan gebruikersaccounts, zodat uw gebruikers toegang hebben tot Microsoft 365 services, zoals e-mail en Microsoft Teams.

U kunt licenties aan gebruikersaccounts afzonderlijk of automatisch toewijzen via groepslidmaatschap.

Als u Microsoft 365 licenties wilt toewijzen aan afzonderlijke gebruikersaccounts, kunt u het volgende gebruiken:

- [Het Microsoft 365-beheercentrum](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Het Azure AD-beheercentrum

## <a name="group-based-licensing"></a>Licenties op groepsbasis

U kunt beveiligingsgroepen configureren in Azure AD om automatisch licenties van een set abonnementen toe te wijzen aan alle leden van de groep. Dit wordt *licenties op groepsbasis* genoemd. Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. 

Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden. Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.

>[!Note]
>Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u licenties op groepsbasis niet te configureren.
>

Zie groepslicenties in Azure AD voor [meer informatie.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)

## <a name="next-steps"></a>Volgende stappen

Met de juiste set gebruikersaccounts die zijn toegewezen aan licenties, kunt u nu het volgende doen:

- [Beveiliging implementeren](../security/defender-365-security/security-roadmap.md)
- [Clientsoftware implementeren, zoals Microsoft 365-apps](/DeployOffice/deployment-guide-microsoft-365-apps)
- [Apparaatbeheer instellen](device-management-roadmap-microsoft-365.md)
- [Services en toepassingen configureren](configure-services-and-applications.md)