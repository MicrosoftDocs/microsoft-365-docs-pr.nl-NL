---
title: Microsoft 365 Cloud-only-identiteit
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
description: Hierin wordt beschreven hoe u gebruikers en groepen maakt wanneer uw Microsoft 365-abonnement gebruikmaakt van Cloud-only-identiteit.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327925"
---
# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365 Cloud-only-identiteit

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met alleen Cloud identiteit worden al uw gebruikers, groepen en contactpersonen opgeslagen in de Azure AD-Tenant (Azure Active Directory) van uw Microsoft 365-abonnement. Hier volgen de basisonderdelen van de identiteit van de Cloud.
 
![De basisonderdelen van de alleen-Cloud identiteit](../media/about-microsoft-365-identity/cloud-only-identity.png)

Gebruikers en hun gebruikersaccounts in organisaties kunnen op verschillende manieren worden gecategoriseerd. De werknemers hebben bijvoorbeeld een permanente status. Sommige zijn leveranciers, contractant of partners met een tijdelijke status. Sommige externe gebruikers hebben geen gebruikersaccounts, maar moeten nog wel toegang krijgen tot bepaalde services en bronnen voor ondersteuning van interactie en samenwerking. Bijvoorbeeld:

- Tenant accounts stellen gebruikers binnen uw organisatie voor die u een licentie voor cloudservices geeft

- Accounts van Business to Business (B2B) vertegenwoordigen gebruikers van buiten uw organisatie die u uitnodigt om deel te nemen aan de samenwerking

Neem de voorraad van de soorten gebruikers in uw organisatie. Wat zijn de groeperingen? U kunt bijvoorbeeld gebruikers groeperen op een functie op hoog niveau of doel voor uw organisatie.

Daarnaast kunnen sommige cloudservices worden gedeeld met gebruikers buiten uw organisatie zonder gebruikersaccounts. U moet deze groepen gebruikers ook identificeren.

U kunt groepen in azure AD gebruiken om verschillende doeleinden te gebruiken om het beheer van de cloudomgeving te vereenvoudigen. Met een Azure AD-groep kunt u bijvoorbeeld:

- Gebruikslicenties voor groepen gebruiken om licenties voor Microsoft 365 automatisch toe te wijzen aan uw gebruikersaccounts zodra ze worden toegevoegd als leden.
- Gebruikersaccounts dynamisch toevoegen aan specifieke groepen, op basis van kenmerken van gebruikersaccounts, zoals naam van de afdeling.
- Automatisch gebruikers voor software inrichten als een service (SaaS)-toepassing en de toegang tot de toepassingen met multi-factor Authentication (MFA) en andere regels voor voorwaardelijke toegang beschermen.
- Het inrichten van machtigingen en toegangsniveaus voor SharePoint Online-team sites.

## <a name="next-steps-for-cloud-only-identity"></a>Volgende stappen voor de identiteit van de Cloud

- [Gebruikersaccounts beheren](manage-microsoft-365-accounts.md)
- [Licenties aan gebruikersaccounts toewijzen](assign-licenses-to-user-accounts.md)
- [Groepen en groepslidmaatschap beheren](manage-microsoft-365-groups.md)
- [Wachtwoorden van gebruikersaccounts beheren](manage-microsoft-365-passwords.md)
