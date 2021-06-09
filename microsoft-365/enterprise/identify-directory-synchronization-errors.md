---
title: Adreslijstsynchronisatiefouten weergeven in Microsoft 365
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
description: Meer informatie over het weergeven van fouten bij adreslijstsynchronisatie en mogelijke oplossingen in Microsoft 365 beheercentrum.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907502"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="15a4e-103">Adreslijstsynchronisatiefouten weergeven in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="15a4e-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="15a4e-104">U kunt adreslijstsynchronisatiefouten weergeven in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="15a4e-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="15a4e-105">Alleen de objectfouten van de gebruiker worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="15a4e-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="15a4e-106">Zie Objecten identificeren met [DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)als u fouten met PowerShell wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="15a4e-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="15a4e-107">Adreslijstsynchronisatiefouten weergeven in het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="15a4e-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="15a4e-108">Fouten weergeven in het Microsoft 365 beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="15a4e-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="15a4e-109">Meld u aan bij [het Microsoft 365 beheercentrum](https://admin.microsoft.com) met een globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="15a4e-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="15a4e-110">Op de **startpagina** ziet u de **gebruikersbeheerkaart.**</span><span class="sxs-lookup"><span data-stu-id="15a4e-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![De gebruikersbeheerkaart in het Microsoft 365 beheercentrum](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="15a4e-112">Kies op de kaart **Synchronisatiefouten** onder **Azure AD Verbinding maken** om de fouten op de pagina **Adreslijstsynchronisatiefouten weer te** geven.</span><span class="sxs-lookup"><span data-stu-id="15a4e-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Een voorbeeld van de pagina Adreslijstsynchronisatiefouten](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="15a4e-114">Kies een van de fouten om het detailvenster weer te geven met informatie over de fout en tips voor het oplossen ervan.</span><span class="sxs-lookup"><span data-stu-id="15a4e-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Voorbeeld van de details van een adreslijstsynchronisatiefout](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="15a4e-116">Zie na het weergeven [problemen met adreslijstsynchronisatie](fix-problems-with-directory-synchronization.md) oplossen om Microsoft 365 geïdentificeerde problemen te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="15a4e-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>