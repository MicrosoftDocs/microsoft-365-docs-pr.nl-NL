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
ms.openlocfilehash: b51007221257b9adac46c31295e13b20b12342ab
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868919"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="37df7-103">Gebruikers toegang geven tot de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="37df7-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="37df7-104">Gebruikers moeten zijn toegewezen aan de beveiligings & compliance Center voordat ze de functies voor beveiliging of compliance kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="37df7-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="37df7-105">Als globale beheerder of als lid van de de organizationmanagement-rollen groep in het Beveiligingscentrum beveiligings &, kunt u deze machtigingen aan gebruikers verlenen.</span><span class="sxs-lookup"><span data-stu-id="37df7-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="37df7-106">Gebruikers kunnen alleen de functies voor beveiliging en compliance beheren waartoe u ze toegang geeft.</span><span class="sxs-lookup"><span data-stu-id="37df7-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="37df7-107">Als u meer wilt weten over de verschillende machtigingen die u aan gebruikers kunt geven in het compliance-& Beveiligingscentrum, raadpleegt u [machtigingen in het beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="37df7-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="37df7-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="37df7-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="37df7-109">U moet een globale beheerder of een lid van de rollen groep de organizationmanagement in het Beveiligingscentrum voor beveiliging & om de stappen in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="37df7-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="37df7-110">Rollen groepen voor de beveiligings & nalevings centrum kunnen soortgelijke namen hebben voor groepen met rollen in Exchange Online, maar ze zijn niet hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="37df7-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="37df7-111">Lidmaatschap van rollen groepen worden niet gedeeld tussen Exchange Online en de beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="37df7-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="37df7-112">Machtigingen voor gedelegeerde toegangsmachtigingen (DAP) met de machtiging beheren namens (AOBO) hebben geen toegang tot de beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="37df7-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="37df7-113">Met behulp van het beveiligings & nalevings centrum kunt u een andere gebruiker toegang geven tot de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="37df7-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="37df7-114">Open het beveiligings & nalevings centrum aan <https://protection.office.com> en ga vervolgens naar **machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="37df7-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="37df7-115">Ga direct naar het tabblad **machtigingen** en open <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="37df7-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="37df7-116">Kies in de lijst met rollen groepen de rollen groep en klik vervolgens op het **Edit** ![ pictogram bewerken bewerken ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="37df7-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="37df7-117">Klik op de pagina eigenschappen van rollen groep **Members**, onder leden **, op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.gif) en selecteer de naam van de gebruiker (s) die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="37df7-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="37df7-118">Wanneer u alle gebruikers hebt geselecteerd die u wilt toevoegen aan de rollen groep, klikt u op \*\*toevoegen \> \*\* en vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="37df7-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="37df7-119">Wanneer u gereed bent, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="37df7-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="37df7-120">Beveiligings & PowerShell gebruiken om een andere gebruiker toegang te geven tot de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="37df7-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="37df7-121">[Maak verbinding met beveiliging & nalevings centrum voor PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="37df7-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="37df7-122">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="37df7-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="37df7-123">Zie [add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember) voor gedetailleerde syntaxis-en Parameterproblemen.</span><span class="sxs-lookup"><span data-stu-id="37df7-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="37df7-124">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="37df7-124">How do you know this worked?</span></span>

<span data-ttu-id="37df7-125">Voer een van de volgende stappen uit om te controleren of u toegang hebt tot de beveiligings & nalevings centrum:</span><span class="sxs-lookup"><span data-stu-id="37df7-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="37df7-126">Ga in het beveiligings & nalevings centrum naar **machtigingen** en selecteer de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="37df7-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="37df7-127">Controleer de leden van de groep rollen in het flyout Details dat wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="37df7-127">In the details flyout that opens, verify the members of the role group.</span></span> 

- <span data-ttu-id="37df7-128">In het beveiligings & nalevings centrum voor PowerShell, vervangt u \<RoleGroupName\> de naam van de rolgroep en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="37df7-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="37df7-129">Zie [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="37df7-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
