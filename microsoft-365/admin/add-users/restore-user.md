---
title: Een gebruiker herstellen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Binnen 30 dagen na het verwijderen van een gebruikersaccount kunt u het account en alle gegevens herstellen en kan de gebruiker zich aanmelden met hetzelfde account.
ms.openlocfilehash: f849fe8e403aa9a72eccb4dd65665ec9f33618d1
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779648"
---
# <a name="restore-a-user"></a><span data-ttu-id="0bc33-103">Een gebruiker herstellen</span><span class="sxs-lookup"><span data-stu-id="0bc33-103">Restore a user</span></span>
   
<span data-ttu-id="0bc33-p101">Wanneer u een gebruikersaccount binnen 30 dagen na verwijderen herstelt, worden het account en alle bijbehorende gegevens hersteld. De gebruiker kan zich met hetzelfde werk- of schoolaccount aanmelden. Het postvak wordt volledig hersteld. [Neem contact met ons op](../../business-video/get-help-support.md) als u wilt weten na hoeveel dagen een specifiek gebruikersaccount niet meer kan worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="0bc33-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="0bc33-108">Hier zijn een paar tips:</span><span class="sxs-lookup"><span data-stu-id="0bc33-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="0bc33-109">Zorg ervoor dat licenties beschikbaar zijn om toe te wijzen aan het account.</span><span class="sxs-lookup"><span data-stu-id="0bc33-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="0bc33-110">Als uw bedrijf Active Directory gebruikt voor instrutcions bij het herstellen van een gebruikersaccount, zie Hoe u problemen kunt oplossen met verwijderde gebruikersaccounts [in](/office365/troubleshoot/active-directory/restore-deleted-user-accounts)Office 365.</span><span class="sxs-lookup"><span data-stu-id="0bc33-110">If your business uses Active Directory, for instrutcions on restoring a user account, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts).</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="0bc33-111">Een of meer gebruikersaccounts herstellen</span><span class="sxs-lookup"><span data-stu-id="0bc33-111">Restore one or more user accounts</span></span>

<span data-ttu-id="0bc33-112">U moet een globale beheerder Microsoft 365 beheerder van gebruikersbeheer zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0bc33-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="0bc33-113">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">verwijderde gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="0bc33-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="0bc33-114">Selecteer **op de pagina** Verwijderde gebruikers de namen van de gebruikers die u wilt terugzetten en selecteer vervolgens **Herstellen.**</span><span class="sxs-lookup"><span data-stu-id="0bc33-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="0bc33-115">Volg de aanwijzingen om hun wachtwoord in te stellen en selecteer vervolgens **Herstellen.**</span><span class="sxs-lookup"><span data-stu-id="0bc33-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="0bc33-116">Als de gebruiker is hersteld, selecteert u **E-mail verzenden en sluiten.**</span><span class="sxs-lookup"><span data-stu-id="0bc33-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="0bc33-117">Zie onderstaande instructies voor het herstellen van deze accounts als u te maken krijgt met een tegenstrijdigheid in de namen of proxyadressen.</span><span class="sxs-lookup"><span data-stu-id="0bc33-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="0bc33-118">Nadat u een gebruiker hebt hersteld, moet u ervoor zorgen dat u hen op de hoogte stelt dat hun wachtwoord is gewijzigd en dat u deze opvolgt.</span><span class="sxs-lookup"><span data-stu-id="0bc33-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="0bc33-119">Een gebruiker met een gebruikersnaamconflict herstellen</span><span class="sxs-lookup"><span data-stu-id="0bc33-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="0bc33-120">Een gebruikersnaamconflict doet zich voor wanneer u een gebruikersaccount verwijdert, een nieuw gebruikersaccount met dezelfde gebruikersnaam maakt (voor dezelfde gebruiker of voor een andere gebruiker met een soortgelijke naam) en daarna het verwijderde account wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="0bc33-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="0bc33-p103">U kunt dit oplossen door het actieve gebruikersaccount te vervangen door het account dat u herstelt. U kunt ook een andere gebruikersnaam toewijzen aan het account dat u herstelt, zodat er niet twee accounts met dezelfde gebruikersnaam zijn. Hierna ziet u de stappen.</span><span class="sxs-lookup"><span data-stu-id="0bc33-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="0bc33-124">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">verwijderde gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="0bc33-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="0bc33-125">Selecteer **op de pagina** Verwijderde gebruikers de namen van de gebruikers die u wilt herstellen en selecteer vervolgens **Herstellen.**</span><span class="sxs-lookup"><span data-stu-id="0bc33-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0bc33-p104">Als twee of meer gebruikers niet kunnen worden hersteld, wordt in een foutbericht aangegeven dat de herstelbewerking voor sommige gebruikers is mislukt. Kijk in het logbestand welke gebruikers niet zijn hersteld en herstel die accounts een voor een.</span><span class="sxs-lookup"><span data-stu-id="0bc33-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="0bc33-128">Volg de aanwijzingen om het wachtwoord in te stellen en selecteer **Herstellen.**</span><span class="sxs-lookup"><span data-stu-id="0bc33-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="0bc33-p105">In een bericht wordt aangegeven dat er een probleem is opgetreden bij het herstellen van het account. Voer een van de volgende handelingen uit:</span><span class="sxs-lookup"><span data-stu-id="0bc33-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="0bc33-p106">Annuleer het herstellen en geef de huidige actieve gebruiker een andere naam. Probeer vervolgens opnieuw te herstellen.</span><span class="sxs-lookup"><span data-stu-id="0bc33-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="0bc33-133">OF typ een nieuw primair e-mailadres voor de gebruiker en selecteer **Herstellen.**</span><span class="sxs-lookup"><span data-stu-id="0bc33-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="0bc33-134">Controleer het resultaat en selecteer vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="0bc33-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="0bc33-135">Een gebruiker met een proxyadresconflict herstellen</span><span class="sxs-lookup"><span data-stu-id="0bc33-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="0bc33-p107">Een proxy-adresconflict doet zich voor wanneer u een gebruikersaccount verwijdert dat een proxyadres bevat, hetzelfde proxyadres toewijst aan een ander account en daarna het verwijderde account wilt herstellen. Voer de onderstaande stappen uit om dit probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0bc33-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="0bc33-138">Hiervoor moet [u beheerdersmachtigingen](about-admin-roles.md) Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0bc33-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="0bc33-139">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">verwijderde gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="0bc33-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="0bc33-140">Selecteer op de pagina **Verwijderde gebruikers** de gebruikers die u wilt herstellen en selecteer vervolgens **Herstellen**.</span><span class="sxs-lookup"><span data-stu-id="0bc33-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="0bc33-141">Volg op **de** pagina Herstellen de instructies om het wachtwoord in te stellen en selecteer **Herstellen.**</span><span class="sxs-lookup"><span data-stu-id="0bc33-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="0bc33-142">Alle conflicterende proxyadressen worden automatisch verwijderd van de gebruiker die u herstelt.</span><span class="sxs-lookup"><span data-stu-id="0bc33-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="0bc33-143">Controleer het resultaat en selecteer vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="0bc33-143">Review the results, and then select **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="0bc33-144">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="0bc33-144">Related content</span></span>

<span data-ttu-id="0bc33-145">[Een gebruiker verwijderen](delete-a-user.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="0bc33-145">[Delete a user](delete-a-user.md) (article)</span></span>\
<span data-ttu-id="0bc33-146">[Beheerdersrollen toewijzen](assign-admin-roles.md) (video)</span><span class="sxs-lookup"><span data-stu-id="0bc33-146">[Assign admin roles](assign-admin-roles.md) (video)</span></span>\
<span data-ttu-id="0bc33-147">[Licenties toewijzen aan gebruikers](../manage/assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="0bc33-147">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>
