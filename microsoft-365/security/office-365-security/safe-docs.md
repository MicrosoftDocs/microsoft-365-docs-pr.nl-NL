---
title: Veilige documenten in Microsoft Defender voor Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over veilige documenten in Microsoft 365 E5 of Microsoft 365 E5-beveiliging.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f67dd21c4cea62012af4713bceddc2eebae33c7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908804"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="f7211-103">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f7211-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f7211-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="f7211-104">**Applies to**</span></span>
- [<span data-ttu-id="f7211-105">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f7211-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f7211-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7211-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f7211-107">Veilige documenten is een functie in Microsoft 365 E5- of Microsoft 365 E5-beveiliging waarmee [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor Eindpunt wordt gebruikt om documenten en bestanden te scannen die worden geopend in de [beveiligde weergave.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="f7211-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f7211-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f7211-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f7211-109">Veilige documenten is alleen beschikbaar voor gebruikers met *Microsoft 365 E5-* of *Microsoft 365 E5-beveiligingslicenties.*</span><span class="sxs-lookup"><span data-stu-id="f7211-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="f7211-110">Deze licenties zijn niet opgenomen in Microsoft Defender voor Office 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="f7211-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="f7211-111">Veilige documenten wordt ondersteund in Microsoft 365 Apps voor ondernemingen (voorheen Bekend als Office 365 ProPlus) versie 2004 of hoger.</span><span class="sxs-lookup"><span data-stu-id="f7211-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="f7211-112">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="f7211-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="f7211-113">Als u rechtstreeks naar de **pagina Veilige bijlagen van ATP** wilt gaan, opent u <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="f7211-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="f7211-114">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7211-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f7211-115">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="f7211-115">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f7211-116">Als u instellingen voor veilige documenten wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="f7211-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f7211-117">Als u alleen-lezen toegang wilt tot instellingen voor veilige documenten, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="f7211-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f7211-118">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f7211-118">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="f7211-119">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7211-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f7211-120">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f7211-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="f7211-121">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="f7211-121">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="f7211-122">Hoe gaat Microsoft om met uw gegevens?</span><span class="sxs-lookup"><span data-stu-id="f7211-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="f7211-123">Veilige documenten sturen bestanden naar de [Microsoft Defender for Endpoint-cloud](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse om u te beschermen.</span><span class="sxs-lookup"><span data-stu-id="f7211-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="f7211-124">Meer informatie over hoe Microsoft Defender voor Eindpunt met uw gegevens omgaat, vindt u hier: Microsoft Defender voor opslag en privacy van [eindpuntgegevens.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="f7211-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="f7211-125">Bestanden die door veilige documenten worden verzonden, worden niet bewaard in Defender na de tijd die nodig is voor analyse (meestal minder dan 24 uur).</span><span class="sxs-lookup"><span data-stu-id="f7211-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="f7211-126">Gebruik het Beveiligings- & compliancecentrum om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="f7211-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="f7211-127">Ga in het & Compliancecentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments** en klik vervolgens op **Algemene instellingen.**</span><span class="sxs-lookup"><span data-stu-id="f7211-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="f7211-128">Configureer **de volgende instellingen** in de algemene instellingen die worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f7211-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f7211-129">**Veilige documenten voor Office-clients in-** of uitschakelen: Verplaats de schakelknop naar rechts om de functie in te ![ schakelen: Schakelen ](../../media/scc-toggle-on.png) in.</span><span class="sxs-lookup"><span data-stu-id="f7211-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="f7211-130">**Toestaan dat** personen door de beveiligde weergave kunnen klikken, zelfs als veilige documenten het bestand als schadelijk identificeren: U wordt aangeraden deze optie uitgeschakeld te laten (laat de schakeloptie links: Schakel de schakeloptie ![ ](../../media/scc-toggle-off.png) uit).</span><span class="sxs-lookup"><span data-stu-id="f7211-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="f7211-131">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="f7211-131">When you're finished, click **Save**.</span></span>

   ![Instellingen voor veilige documenten nadat u Globale instellingen op de pagina Veilige bijlagen heeft geselecteerd.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="f7211-133">Exchange Online PowerShell gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="f7211-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="f7211-134">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f7211-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="f7211-135">Met _de parameter EnableSafeDocs_ worden veilige documenten voor de hele organisatie in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f7211-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="f7211-136">Met _de parameter AllowSafeDocsOpen_ kunnen of voorkomen dat gebruikers de beveiligde weergave (dat wil zeggen het openen van het document) verlaten als het document is geïdentificeerd als schadelijk.</span><span class="sxs-lookup"><span data-stu-id="f7211-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="f7211-137">In dit voorbeeld worden veilige documenten voor de hele organisatie in gebruik en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als schadelijk vanuit de beveiligde weergave.</span><span class="sxs-lookup"><span data-stu-id="f7211-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="f7211-138">Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f7211-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="f7211-139">Hoe weet ik of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="f7211-139">How do I know this worked?</span></span>

<span data-ttu-id="f7211-140">Ga als volgt te werk om te controleren of u veilige documenten hebt ingeschakeld en geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="f7211-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="f7211-141">Ga in het beveiligings- &  compliancecentrum naar Beveiligingsbeheerbeleid \>  \> **ATP-veilige** bijlagen , klik op Algemene  instellingen en controleer of veilige documenten voor **Office-clients** in- en toestaan dat personen door de beveiligde weergave kunnen klikken, zelfs als veilige documenten het bestand identificeren als schadelijke instellingen.</span><span class="sxs-lookup"><span data-stu-id="f7211-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="f7211-142">Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:</span><span class="sxs-lookup"><span data-stu-id="f7211-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="f7211-143">De volgende bestanden zijn beschikbaar om de beveiliging van veilige documenten te testen.</span><span class="sxs-lookup"><span data-stu-id="f7211-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="f7211-144">Deze documenten zijn vergelijkbaar met het EICAR.TXT bestand voor het testen van anti-malware- en anti-virusoplossingen.</span><span class="sxs-lookup"><span data-stu-id="f7211-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="f7211-145">De bestanden zijn niet schadelijk, maar ze activeren wel de beveiliging van veilige documenten.</span><span class="sxs-lookup"><span data-stu-id="f7211-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="f7211-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="f7211-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="f7211-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="f7211-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="f7211-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="f7211-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)