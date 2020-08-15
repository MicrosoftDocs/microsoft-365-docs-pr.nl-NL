---
title: Adreslijstsynchronisatie uitschakelen voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: In dit artikel vindt u informatie over het gebruik van PowerShell om adreslijstsynchronisatie voor Microsoft 365 uit te schakelen.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688920"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Adreslijstsynchronisatie uitschakelen voor Microsoft 365
U kunt PowerShell gebruiken om adreslijstsynchronisatie uit te schakelen. U wordt echter niet aangeraden om adreslijstsynchronisatie uit te schakelen als stap bij probleemoplossing. Als u hulp nodig hebt bij het oplossen van problemen met adreslijstsynchronisatie, raadpleegt u het artikel [problemen oplossen met adreslijstsynchronisatie voor Microsoft 365](fix-problems-with-directory-synchronization.md) . 
  
[Contact opnemen met ondersteuning](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) voor bedrijfsproducten, indien nodig.
  
## <a name="turn-off-directory-synchronization"></a>Adreslijstsynchronisatie uitschakelen  
Adreslijstsynchronisatie uitschakelen:
  
1. Installeer eerst de vereiste software en maak verbinding met uw Microsoft 365-abonnement. Zie [verbinding maken met de Microsoft Azure Active Directory-module voor Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)voor instructies.
    
2. Gebruik [set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) om adreslijstsynchronisatie uit te schakelen: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Als u deze opdracht gebruikt, moet u 72 uur wachten voordat u adreslijstsynchronisatie weer kunt inschakelen.
>
 
