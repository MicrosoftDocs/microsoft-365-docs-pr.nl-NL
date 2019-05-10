---
title: Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Informatie over het maken van een beleid voor het beheer van app en werkbestanden op Windows 10-apparaten te beschermen.
ms.openlocfilehash: f649454417dceae05255df6b37760af99c0b8d4f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660339"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="4a428-103">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="4a428-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="4a428-104">Beleid voor app-beheer maken voor Windows 10</span><span class="sxs-lookup"><span data-stu-id="4a428-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="4a428-105">Als uw gebruikers persoonlijke Windows 10-apparaten gebruiken voor hun werk, kunt u de gegevens op die apparaten ook beschermen.</span><span class="sxs-lookup"><span data-stu-id="4a428-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="4a428-106">Ga naar de admin center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="4a428-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="4a428-107">Kies op de Linkernavigatie **apparaten** \> **beleid** \> **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4a428-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="4a428-108">Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid.</span><span class="sxs-lookup"><span data-stu-id="4a428-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="4a428-109">Kies onder **Type beleid** de optie **Toepassingsbeheer voor Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="4a428-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="4a428-110">Kies onder **type apparaat**, **persoonlijke** of **Bedrijf eigendom**.</span><span class="sxs-lookup"><span data-stu-id="4a428-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="4a428-111">De optie **Werkbestanden versleutelen** is automatisch ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="4a428-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="4a428-112">Stel **Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden en afdwingen dat werkbestanden worden opgeslagen in OneDrive voor Bedrijven** in op **Aan** als u niet wilt dat de gebruikers werkbestanden opslaan op hun pc.</span><span class="sxs-lookup"><span data-stu-id="4a428-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="4a428-113">Vouw **Gegevens herstellen op Windows-apparaten** uit. U wordt aangeraden de optie **in te schakelen**.</span><span class="sxs-lookup"><span data-stu-id="4a428-113">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="4a428-p101">Voordat u naar de locatie van het certificaat voor de gegevensherstelagent kunt bladeren, moet u deze eerst maken. Zie [Een certificaat voor een gegevensherstelagent voor het Encrypting File System (EFS) maken en verifiëren](https://go.microsoft.com/fwlink/p/?linkid=853700) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="4a428-p101">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="4a428-p102">Werkbestanden worden standaard versleuteld met een geheime code die wordt opgeslagen op het apparaat en die gekoppeld is aan het profiel van de gebruiker. Alleen de gebruiker kan het bestand openen en ontsleutelen. Als een apparaat zoekraakt of als een gebruiker wordt verwijderd, kan een bestand echter blijven steken in versleutelde toestand. Het certificaat van de Gegevensherstelagent (DRA - Data Recovery Agent) kan door een beheerder worden gebruikt om het bestand te ontsleutelen.</span><span class="sxs-lookup"><span data-stu-id="4a428-p102">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="4a428-p103">Vouw **Meer netwerk- en cloudlocaties beveiligen** uit als u extra domeinen of SharePoint Online-locaties wilt toevoegen om ervoor te zorgen dat bestanden in alle weergegeven apps worden beveiligd. Als u meerdere items moet opgeven voor een veld, gebruikt u een puntkomma (;) tussen de items.</span><span class="sxs-lookup"><span data-stu-id="4a428-p103">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="4a428-p104">Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kiest u **Wijzigen**, zoekt u de beveiligingsgroep die deze instellingen krijgt \> **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="4a428-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="4a428-126">Kies ten slotte **Toevoegen** om het beleid op te slaan en dit toe te wijzen aan apparaten.</span><span class="sxs-lookup"><span data-stu-id="4a428-126">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 