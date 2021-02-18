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
description: Gebruikers moeten machtigingen toegewezen krijgen in het Microsoft 365-beveiligings- & compliancecentrum voordat ze de beveiligings- of nalevingsfuncties kunnen beheren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289875"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="95398-103">Gebruikers toegang geven tot het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="95398-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95398-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="95398-104">**Applies to**</span></span>
- [<span data-ttu-id="95398-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="95398-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="95398-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="95398-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="95398-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95398-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="95398-108">Gebruikers moeten machtigingen toegewezen krijgen in het beveiligings- & voordat ze de beveiligings- of nalevingsfuncties kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="95398-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="95398-109">Als globale beheerder of lid van de rollengroep OrganizationManagement in het beveiligings- & compliancecentrum kunt u deze machtigingen aan gebruikers verlenen.</span><span class="sxs-lookup"><span data-stu-id="95398-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="95398-110">Gebruikers kunnen alleen de beveiligings- of nalevingsfuncties beheren die u hen toegang geeft.</span><span class="sxs-lookup"><span data-stu-id="95398-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="95398-111">Raadpleeg machtigingen in het beveiligings- & compliancecentrum voor meer informatie over de verschillende machtigingen die u gebruikers kunt geven in het beveiligings- & [compliancecentrum.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="95398-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95398-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="95398-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95398-113">U moet een globale beheerder of lid zijn van de rollengroep OrganizationManagement in het beveiligings- & compliancecentrum om de stappen in dit artikel te kunnen voltooien.</span><span class="sxs-lookup"><span data-stu-id="95398-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="95398-114">Rollengroepen voor het & compliancecentrum hebben mogelijk vergelijkbare namen als de rollengroepen in Exchange Online, maar deze zijn niet hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="95398-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="95398-115">Lidmaatschappen van rollengroep worden niet gedeeld tussen Exchange Online en het & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="95398-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="95398-116">DAP-partners (Gedelegeerde toegangsmachtiging) met AOBO-machtigingen (Administer On Behalf Of) hebben geen toegang tot het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="95398-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="95398-117">Het beveiligings- & compliancecentrum gebruiken om een andere gebruiker toegang te geven tot het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="95398-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="95398-118">Open het & compliancecentrum en <https://protection.office.com> ga naar **Machtigingen.**</span><span class="sxs-lookup"><span data-stu-id="95398-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="95398-119">Als u rechtstreeks naar het **tabblad Machtigingen wilt** gaan, opent u <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="95398-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="95398-120">Kies de rollengroep in de lijst met rollengroepen en klik op **het pictogram** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) Bewerken.</span><span class="sxs-lookup"><span data-stu-id="95398-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="95398-121">Klik op de eigenschappenpagina van de rollengroep onder **Leden** op Pictogram toevoegen en selecteer de naam van de gebruiker ![ ](../../media/ITPro-EAC-AddIcon.gif) (of gebruikers) die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="95398-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="95398-122">Wanneer u alle gebruikers hebt geselecteerd die u wilt toevoegen aan de rollengroep, klikt u op **Toevoegen en \>** vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="95398-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="95398-123">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="95398-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="95398-124">PowerShell voor & beveiligingscentrum gebruiken om een andere gebruiker toegang te geven tot het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="95398-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="95398-125">[Maak verbinding met beveiligings & Compliancecentrum PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="95398-125">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="95398-126">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="95398-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="95398-127">Zie [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember) voor gedetailleerde problemen met de syntaxis en parameter</span><span class="sxs-lookup"><span data-stu-id="95398-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="95398-128">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="95398-128">How do you know this worked?</span></span>

<span data-ttu-id="95398-129">Als u wilt controleren of u toegang hebt verleend tot het beveiligings- & compliancecentrum, gaat u op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="95398-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="95398-130">Ga in het & Compliancecentrum naar **Machtigingen** en selecteer de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="95398-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="95398-131">Controleer in de flyout met details die wordt geopend de leden van de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="95398-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="95398-132">Vervang in & Compliancecentrum PowerShell door de naam van de rollengroep en voer \<RoleGroupName\> de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="95398-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="95398-133">Zie [Get-RoleGroupMember voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="95398-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
