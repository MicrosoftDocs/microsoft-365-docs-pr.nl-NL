---
title: Gebruikers toegang geven tot het beveiligings- & compliancecentrum
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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gebruikers moeten machtigingen krijgen toegewezen in het Microsoft 365 Security & Compliance Center voordat ze een van de beveiligings- of compliancefuncties kunnen beheren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cd36ac0dec20851a423acd58e5ad7d38cb65d93
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599921"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="eda10-103">Gebruikers toegang geven tot het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="eda10-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eda10-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="eda10-104">**Applies to**</span></span>
- [<span data-ttu-id="eda10-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eda10-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eda10-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="eda10-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eda10-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eda10-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eda10-108">Gebruikers moeten worden toegewezen machtigingen in het Beveiligings- & compliancecentrum voordat ze een van de beveiligings- of compliancefuncties kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="eda10-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="eda10-109">Als globale beheerder of lid van de rollengroep Organisatiebeheer in het beveiligings- & Compliancecentrum, kunt u deze machtigingen aan gebruikers geven.</span><span class="sxs-lookup"><span data-stu-id="eda10-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="eda10-110">Gebruikers kunnen alleen de beveiligings- of compliancefuncties beheren die u hen toegang geeft.</span><span class="sxs-lookup"><span data-stu-id="eda10-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="eda10-111">Voor meer informatie over de verschillende machtigingen die u aan gebruikers kunt geven in het Beveiligings- & Compliancecentrum, raadpleegt u Machtigingen in het Beveiligings- [& Compliancecentrum.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="eda10-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eda10-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="eda10-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eda10-113">U moet een globale beheerder zijn of lid zijn van de rollengroep Organisatiebeheer in het beveiligings- & compliancecentrum, om de stappen in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="eda10-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="eda10-114">Rollengroepen voor het beveiligings- & compliancecentrum hebben mogelijk vergelijkbare namen als de rollengroepen in Exchange Online, maar ze zijn niet hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="eda10-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="eda10-115">Lidmaatschappen van rollengroep worden niet gedeeld tussen Exchange Online en het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="eda10-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="eda10-116">DAP-partners (Gedelegeerde Toegangsmachtiging) met machtigingen voor Beheer namens (AOBO) hebben geen toegang tot het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="eda10-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="eda10-117">Het beveiligings- & compliancecentrum gebruiken om een andere gebruiker toegang te geven tot het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="eda10-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="eda10-118">Open het Beveiligingscentrum & compliancecentrum op <https://protection.office.com> en ga naar **Machtigingen.**</span><span class="sxs-lookup"><span data-stu-id="eda10-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="eda10-119">Als u rechtstreeks naar het tabblad **Machtigingen** wilt gaan, opent u <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="eda10-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="eda10-120">Kies in de lijst met rollengroepen de rollengroep en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) bewerken.</span><span class="sxs-lookup"><span data-stu-id="eda10-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="eda10-121">Klik op de pagina Eigenschappen van de rollengroep onder **Leden** op Pictogram toevoegen toevoegen en selecteer de naam van de gebruiker ![ (of gebruikers) die u wilt ](../../media/ITPro-EAC-AddIcon.gif) toevoegen.</span><span class="sxs-lookup"><span data-stu-id="eda10-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="eda10-122">Wanneer u alle gebruikers hebt geselecteerd die u wilt toevoegen aan de rollengroep, klikt u op **Toevoegen en \>** vervolgens OP **OK.**</span><span class="sxs-lookup"><span data-stu-id="eda10-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="eda10-123">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="eda10-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="eda10-124">Gebruik Security & Compliance Center PowerShell om een andere gebruiker toegang te geven tot het & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="eda10-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="eda10-125">[Maak verbinding met & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="eda10-125">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="eda10-126">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="eda10-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="eda10-127">Zie [Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember) voor gedetailleerde syntaxis- en parameterproblemen</span><span class="sxs-lookup"><span data-stu-id="eda10-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="eda10-128">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="eda10-128">How do you know this worked?</span></span>

<span data-ttu-id="eda10-129">Als u wilt controleren of u toegang hebt verleend tot het beveiligings- & compliancecentrum, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="eda10-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="eda10-130">Ga in het & Compliancecentrum naar **Machtigingen** en selecteer de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="eda10-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="eda10-131">Controleer in de flyout details die wordt geopend de leden van de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="eda10-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="eda10-132">Vervang in & PowerShell van het Compliancecentrum door de naam van de rollengroep en \<RoleGroupName\> voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="eda10-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="eda10-133">Zie [Get-RoleGroupMember (Get-RoleGroupMember)](/powershell/module/exchange/Get-RoleGroupMember)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="eda10-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span></span>