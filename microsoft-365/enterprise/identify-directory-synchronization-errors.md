---
title: Fouten met adreslijstsynchronisatie weergeven in Microsoft 365
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
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Meer informatie over het weergeven van fouten bij adreslijstsynchronisatie en mogelijke oplossingen in het Microsoft 365-beheercentrum.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907502"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Fouten met adreslijstsynchronisatie weergeven in Microsoft 365

U kunt adreslijstsynchronisatiefouten weergeven in het Microsoft 365-beheercentrum. Alleen de objectfouten van de gebruiker worden weergegeven. Zie Objecten identificeren met [DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)als u fouten met PowerShell wilt weergeven.

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Fouten met adreslijstsynchronisatie weergeven in het Microsoft 365-beheercentrum

Fouten weergeven in het Microsoft 365-beheercentrum:
  
1. Meld u aan bij [het Microsoft 365-beheercentrum](https://admin.microsoft.com) met een globale beheerdersaccount. 
    
2. Op de **startpagina** ziet u de **gebruikersbeheerkaart.** 
    
    ![De gebruikersbeheerkaart in het Microsoft 365-beheercentrum](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. Kies op de kaart **Synchronisatiefouten** onder **Azure AD Connect** om de fouten op de pagina **Adreslijstsynchronisatiefouten weer te** geven.   
    
    ![Een voorbeeld van de pagina Adreslijstsynchronisatiefouten](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Kies een van de fouten om het detailvenster weer te geven met informatie over de fout en tips voor het oplossen ervan.

   ![Voorbeeld van de details van een adreslijstsynchronisatiefout](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Zie na het weergeven [problemen met adreslijstsynchronisatie voor Microsoft 365](fix-problems-with-directory-synchronization.md) oplossen om geïdentificeerde problemen op te lossen.