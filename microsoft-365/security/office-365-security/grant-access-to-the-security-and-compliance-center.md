---
title: Gebruikers toegang geven tot de beveiligings & nalevings centrum
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gebruikers moeten zijn toegewezen machtigingen in het Microsoft 365-beveiligings & nalevings centrum voordat ze de functies voor beveiliging of compliance kunnen beheren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826599"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="51b79-103">Gebruikers toegang geven tot de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="51b79-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="51b79-104">Gebruikers moeten zijn toegewezen aan de beveiligings & compliance Center voordat ze de functies voor beveiliging of compliance kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="51b79-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="51b79-105">Als globale beheerder of als lid van de de organizationmanagement-rollen groep in het Beveiligingscentrum beveiligings &, kunt u deze machtigingen aan gebruikers verlenen.</span><span class="sxs-lookup"><span data-stu-id="51b79-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="51b79-106">Gebruikers kunnen alleen de functies voor beveiliging en compliance beheren waartoe u ze toegang geeft.</span><span class="sxs-lookup"><span data-stu-id="51b79-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="51b79-107">Als u meer wilt weten over de verschillende machtigingen die u aan gebruikers kunt geven in het compliance-& Beveiligingscentrum, raadpleegt u [machtigingen in het beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="51b79-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51b79-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="51b79-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51b79-109">U moet een globale beheerder of een lid van de rollen groep de organizationmanagement in het Beveiligingscentrum voor beveiliging & om de stappen in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="51b79-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="51b79-110">Rollen groepen voor de beveiligings & nalevings centrum kunnen soortgelijke namen hebben voor groepen met rollen in Exchange Online, maar ze zijn niet hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="51b79-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="51b79-111">Lidmaatschap van rollen groepen worden niet gedeeld tussen Exchange Online en de beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="51b79-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="51b79-112">Machtigingen voor gedelegeerde toegangsmachtigingen (DAP) met de machtiging beheren namens (AOBO) hebben geen toegang tot de beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="51b79-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="51b79-113">Met het Beheercentrum kunt u een andere gebruiker toegang geven tot de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="51b79-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="51b79-114">[Meld u aan en ga naar het Beheercentrum](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="51b79-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="51b79-115">Open in het Microsoft 365-Beheercentrum **beheer centra** en klik vervolgens op **beveiliging & naleving**.</span><span class="sxs-lookup"><span data-stu-id="51b79-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="51b79-116">Ga in het beveiligings & nalevings centrum naar **machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="51b79-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="51b79-117">Kies in de lijst de rollen groep waaraan u de gebruiker wilt toevoegen en klik op het **Edit** ![ pictogram bewerken bewerken ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="51b79-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="51b79-118">Klik op de pagina eigenschappen van rollen groep **Members**, onder leden **, op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.gif) en selecteer de naam van de gebruiker (s) die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="51b79-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="51b79-119">Wanneer u alle gebruikers hebt geselecteerd die u wilt toevoegen aan de rollen groep, klikt u op \*\*toevoegen \> \*\* en vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="51b79-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="51b79-120">Klik op **Opslaan** om de wijzigingen in de groep rollen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="51b79-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="51b79-121">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="51b79-121">How do you know this worked?</span></span>

1. <span data-ttu-id="51b79-122">Ga in het beveiligings & nalevings centrum naar **machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="51b79-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="51b79-123">Selecteer in de lijst de rollen groep om de leden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="51b79-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="51b79-124">Aan de rechterkant, in de groep Details van rollen, kunt u de leden van de groep rollen weergeven.</span><span class="sxs-lookup"><span data-stu-id="51b79-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="51b79-125">PowerShell gebruiken om een andere gebruiker toegang te geven tot de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="51b79-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="51b79-126">[Maak verbinding met beveiliging & nalevings centrum voor PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="51b79-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="51b79-127">Gebruik de opdracht **add-RoleGroupMember** om een gebruiker toe te voegen aan de rol van Organisatiebeheer, zoals in het volgende voorbeeld wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51b79-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="51b79-128">**Parameters**:</span><span class="sxs-lookup"><span data-stu-id="51b79-128">**Parameters**:</span></span>

   - <span data-ttu-id="51b79-129">_Identiteit_ is de rollen groep waaraan u een lid wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="51b79-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="51b79-130">_Lid_ is het postvak, de universele beveiligingsgroep (USG) of de computer die u wilt toevoegen aan de rollen groep.</span><span class="sxs-lookup"><span data-stu-id="51b79-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="51b79-131">U kunt slechts één lid tegelijk opgeven.</span><span class="sxs-lookup"><span data-stu-id="51b79-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="51b79-132">Zie [add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)voor meer informatie over de syntaxis en parameters.</span><span class="sxs-lookup"><span data-stu-id="51b79-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="51b79-133">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="51b79-133">How do you know this worked?</span></span>

<span data-ttu-id="51b79-134">Als u wilt controleren of u de gebruiker toegang wilt geven tot de beveiligings & nalevings centrum, gebruikt u de cmdlet **Get-RoleGroupMember** om de leden in de rollen groep Organisatiebeheer weer te geven, zoals in het volgende voorbeeld wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51b79-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="51b79-135">Zie [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)voor meer informatie over de syntaxis en parameters.</span><span class="sxs-lookup"><span data-stu-id="51b79-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
