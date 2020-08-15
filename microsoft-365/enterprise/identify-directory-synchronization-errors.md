---
title: Fouten met adreslijstsynchronisatie bekijken in Microsoft 365
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
description: Meer informatie over het weergeven van fouten met adreslijstsynchronisatie en mogelijke oplossingen in Microsoft 365-Beheercentrum.
ms.openlocfilehash: 5103b1f8a8f0514ca30fd71b94dee2530f0b082f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689421"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="6f285-103">Fouten met adreslijstsynchronisatie bekijken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f285-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="6f285-104">U kunt fouten met adreslijstsynchronisatie bekijken in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="6f285-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6f285-105">Alleen de fouten van het gebruiker-object worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6f285-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="6f285-106">Zie [objecten identificeren met DirSyncProvisioningErrors](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)als u fouten wilt weergeven met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f285-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6f285-107">Fouten met adreslijstsynchronisatie bekijken in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="6f285-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6f285-108">Fouten bekijken in het Microsoft 365-Beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="6f285-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="6f285-109">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met het account van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="6f285-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="6f285-110">Op de **Start** pagina ziet u de kaart **Gebruikersbeheer** .</span><span class="sxs-lookup"><span data-stu-id="6f285-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![De kaart voor gebruikersbeheer in het Microsoft 365-Beheercentrum](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="6f285-112">Kies op de kaart de optie **synchronisatiefouten** onder **Azure AD Connect** om de fouten te zien op de pagina **fouten in adreslijstsynchronisatie** .</span><span class="sxs-lookup"><span data-stu-id="6f285-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Een voorbeeld van de pagina Adreslijstsynchronisatie fouten](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="6f285-114">Kies een van de fouten om het detaildeelvenster weer te geven met informatie over de fout en tips voor het oplossen van het probleem.</span><span class="sxs-lookup"><span data-stu-id="6f285-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Voorbeeld van de details van een adreslijstsynchronisatie fout](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="6f285-116">Nadat u hebt weergegeven, raadpleegt u [problemen met adreslijstsynchronisatie voor Microsoft 365](fix-problems-with-directory-synchronization.md) oplossen om de vastgestelde problemen te verhelpen.</span><span class="sxs-lookup"><span data-stu-id="6f285-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>

