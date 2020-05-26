---
title: Gebruikers toegang geven tot het Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gebruikers moeten machtigingen krijgen toegewezen in het Microsoft 365 Security & Compliance Center voordat ze een van de beveiligings- of nalevingsfuncties kunnen beheren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 19358e3cca0c4d47338fe5fc72b671e36477ce7e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351949"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="ffada-103">Gebruikers toegang geven tot het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ffada-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="ffada-104">Gebruikers moeten machtigingen krijgen toegewezen in het Security & Compliance Center voordat ze een van de beveiligings- of nalevingsfuncties kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="ffada-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="ffada-105">Als globale beheerder of lid van de rolegroup OrganizationManagement in het Security & Compliance Center u deze machtigingen aan gebruikers geven.</span><span class="sxs-lookup"><span data-stu-id="ffada-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="ffada-106">Gebruikers kunnen alleen de beveiligings- of nalevingsfuncties beheren waartoe u hen toegang geeft.</span><span class="sxs-lookup"><span data-stu-id="ffada-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="ffada-107">Raadpleeg [machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over de verschillende machtigingen die u aan gebruikers in het Security & Compliance Center geven.</span><span class="sxs-lookup"><span data-stu-id="ffada-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ffada-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ffada-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ffada-109">U moet een globale beheerder of lid zijn van de rolegroup OrganizationManagement in het Security & Compliance Center om de stappen in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ffada-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="ffada-110">Rolgroepen voor het Security & Compliance Center hebben mogelijk vergelijkbare namen als de rolgroepen in Exchange Online, maar ze zijn niet hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="ffada-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="ffada-111">Groepslidmaatschappen voor rollen worden niet gedeeld tussen Exchange Online en het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ffada-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="ffada-112">DAP-machtigingen (Delegated Access Permission) met AOBO-machtigingen (Administer Namens Beheren namens AOBO) hebben geen toegang tot het Beveiligingscentrum & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ffada-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="ffada-113">Gebruik het beheercentrum om een andere gebruiker toegang te geven tot het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ffada-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="ffada-114">[Log in en ga naar het beheercentrum](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="ffada-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="ffada-115">Open in het Microsoft 365-beheercentrum **beheercentra** en klik vervolgens op **Beveiliging & Naleving**.</span><span class="sxs-lookup"><span data-stu-id="ffada-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="ffada-116">Ga in het Beveiligingscentrum & naar **Machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="ffada-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="ffada-117">Kies in de lijst de rolgroep waaraan u de gebruiker wilt toevoegen en klik op pictogram Bewerken **bewerken** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="ffada-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="ffada-118">**Klik**op de eigenschappenpagina van de rolgroep onder **Leden**op Pictogram Toevoegen en selecteer de naam van de ![ gebruiker ](../../media/ITPro-EAC-AddIcon.gif) (of gebruikers) die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ffada-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="ffada-119">Wanneer u alle gebruikers hebt geselecteerd die u aan de rolgroep wilt toevoegen, klikt u op \*\*Toevoegen \> \*\* en vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffada-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="ffada-120">Klik **op Opslaan** om de wijzigingen in de rolgroep op te slaan.</span><span class="sxs-lookup"><span data-stu-id="ffada-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ffada-121">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="ffada-121">How do you know this worked?</span></span>

1. <span data-ttu-id="ffada-122">Ga in het Beveiligingscentrum & naar **Machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="ffada-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="ffada-123">Selecteer in de lijst de rolgroep om de leden te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ffada-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="ffada-124">Aan de rechterkant, in de details van de rolgroep, u de leden van de rolgroep bekijken.</span><span class="sxs-lookup"><span data-stu-id="ffada-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="ffada-125">PowerShell gebruiken om een andere gebruiker toegang te geven tot het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ffada-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="ffada-126">[Maak verbinding met Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="ffada-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="ffada-127">Gebruik de opdracht **Groep Lid voor extra rollen** om een gebruiker toe te voegen aan de organisatiebeheerrol, zoals in het volgende voorbeeld wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ffada-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="ffada-128">**Parameters**:</span><span class="sxs-lookup"><span data-stu-id="ffada-128">**Parameters**:</span></span>

   - <span data-ttu-id="ffada-129">_Identiteit_ is de rolgroep waaraan een lid moet worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="ffada-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="ffada-130">_Lid_ is de mailbox, universal security group (USG) of computer die aan de rolgroep moet worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="ffada-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="ffada-131">U slechts één lid tegelijk opgeven.</span><span class="sxs-lookup"><span data-stu-id="ffada-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="ffada-132">Zie [Groeplid toevoegen](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)voor gedetailleerde informatie over syntaxis en parameters.</span><span class="sxs-lookup"><span data-stu-id="ffada-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ffada-133">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="ffada-133">How do you know this worked?</span></span>

<span data-ttu-id="ffada-134">Als u wilt controleren of u gebruikers toegang hebt gegeven tot het Beveiligings- & Compliance Center, gebruikt u de cmdlet **Get-RoleGroupMember** om de leden in de rolgroep Organisatiebeheer weer te geven, zoals in het volgende voorbeeld wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ffada-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="ffada-135">Zie [Groepslid voor get-rolegroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="ffada-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
