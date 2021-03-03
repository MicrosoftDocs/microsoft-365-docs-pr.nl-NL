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
description: Meer informatie over de beveiliging van Veilige documenten in Microsoft 365 E5 of Microsoft 365 E5.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 75dfa9e5687a4c4b561067190e7ce338074b2f66
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407418"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="7b678-103">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7b678-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7b678-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="7b678-104">**Applies to**</span></span>
- [<span data-ttu-id="7b678-105">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="7b678-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="7b678-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b678-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="7b678-107">Veilige documenten is een functie in microsoft 365 E5- of Microsoft 365 E5-beveiliging waarmee [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor het eindpunt wordt gebruikt om documenten en bestanden te scannen die worden geopend in de [beveiligde weergave.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="7b678-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7b678-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="7b678-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7b678-109">Veilige documenten is alleen beschikbaar voor gebruikers met een beveiligingslicentie voor *Microsoft 365 E5* of *Microsoft 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="7b678-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="7b678-110">Deze licenties zijn niet opgenomen in Microsoft Defender voor Office 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="7b678-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="7b678-111">Veilige documenten wordt ondersteund in Microsoft 365-apps voor ondernemingen (voorheen Bekend als Office 365 ProPlus) versie 2004 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7b678-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="7b678-112">U opent het beveiligings- en compliancecentrum in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="7b678-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="7b678-113">Als u rechtstreeks naar de pagina Veilige **bijlagen met ATP wilt** gaan, opent u <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="7b678-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="7b678-114">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b678-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7b678-115">U moet machtigingen toegewezen krijgen in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="7b678-115">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7b678-116">Als u instellingen voor veilige documenten wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="7b678-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="7b678-117">Voor alleen-lezen toegang tot instellingen voor veilige documenten  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="7b678-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="7b678-118">Zie Machtigingen [in Exchange Online voor meer informatie.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="7b678-118">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="7b678-119">Als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol  in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b678-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7b678-120">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7b678-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="7b678-121">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="7b678-121">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="7b678-122">Hoe gaat Microsoft om met uw gegevens?</span><span class="sxs-lookup"><span data-stu-id="7b678-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="7b678-123">Om u te beschermen, verzendt Veilige documenten bestanden naar de [Cloud van Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse.</span><span class="sxs-lookup"><span data-stu-id="7b678-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="7b678-124">Meer informatie over hoe Microsoft Defender voor eindpunt uw gegevens verwerkt, vindt u hier: Gegevensopslag en privacy van [Microsoft Defender voor eindpunt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="7b678-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="7b678-125">Bestanden die door Veilige documenten worden verzonden, worden niet bewaard in Defender na de tijd die nodig is voor analyse (meestal minder dan 24 uur).</span><span class="sxs-lookup"><span data-stu-id="7b678-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="7b678-126">Het beveiligings- & gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="7b678-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="7b678-127">Ga in het & Compliancecentrum  voor beveiligingsinstellingen naar Veilige bijlagen met ATP-beleid voor \>  \> **bedreigingsbeheer** en klik op **Globale instellingen.**</span><span class="sxs-lookup"><span data-stu-id="7b678-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="7b678-128">Configureer **de volgende instellingen** in de fly-out met globale instellingen:</span><span class="sxs-lookup"><span data-stu-id="7b678-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7b678-129">**Veilige documenten voor Office-clients** in schakelen: verplaats de schakelaar naar rechts om de functie in te schakelen: ![ In-/uitschakelen. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="7b678-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="7b678-130">**Personen toestaan** door de beveiligde weergave te klikken, zelfs als veilige documenten het bestand als schadelijk identificeren: het is raadzaam deze optie uitgeschakeld te laten (laat de schakelaar aan de linkerkant staan: Schakel de schakelaar ![ ](../../media/scc-toggle-off.png) uit).</span><span class="sxs-lookup"><span data-stu-id="7b678-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="7b678-131">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="7b678-131">When you're finished, click **Save**.</span></span>

   ![Instellingen voor veilige documenten nadat u algemene instellingen op de pagina Veilige bijlagen heeft geselecteerd.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="7b678-133">Exchange Online PowerShell gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="7b678-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="7b678-134">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="7b678-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="7b678-135">Met de parameter _EnableSafeDocs_ schakelt u veilige documenten in of uit voor de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="7b678-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="7b678-136">Met de parameter _AllowSafeDocsOpen_ kunnen gebruikers de beveiligde weergave (dat wil zeggen het document openen) verlaten als het document is geïdentificeerd als schadelijk.</span><span class="sxs-lookup"><span data-stu-id="7b678-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="7b678-137">In dit voorbeeld worden veilige documenten voor de hele organisatie gebruikt en kunnen gebruikers geen documenten openen die in de beveiligde weergave als schadelijk zijn aangemerkt.</span><span class="sxs-lookup"><span data-stu-id="7b678-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="7b678-138">Zie [Set-AtpPolicyForO365 voor](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7b678-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="7b678-139">Hoe weet ik of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="7b678-139">How do I know this worked?</span></span>

<span data-ttu-id="7b678-140">Ga op een van de volgende stappen te werk om te controleren of u Veilige documenten hebt ingeschakeld en geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="7b678-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="7b678-141">Ga in het & Compliancecentrum  voor beveiligingsbeheer naar VEILIGE bijlagen van ATP-beleid voor \>  \> **bedreigingsbeheer,**   klik op Algemene instellingen en controleer of veilige documenten voor **Office-clients** worden in- of uitschakelen en personen toestaan om door de beveiligde weergave te klikken, zelfs als het bestand wordt geïdentificeerd als schadelijke instellingen.</span><span class="sxs-lookup"><span data-stu-id="7b678-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="7b678-142">Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:</span><span class="sxs-lookup"><span data-stu-id="7b678-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="7b678-143">De volgende bestanden zijn beschikbaar om de beveiliging van veilige documenten te testen.</span><span class="sxs-lookup"><span data-stu-id="7b678-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="7b678-144">Deze documenten zijn vergelijkbaar met het EICAR.TXT voor het testen van antivirus- en antivirusoplossingen.</span><span class="sxs-lookup"><span data-stu-id="7b678-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="7b678-145">De bestanden zijn niet schadelijk, maar activeren wel de beveiliging van veilige documenten.</span><span class="sxs-lookup"><span data-stu-id="7b678-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="7b678-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="7b678-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="7b678-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="7b678-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="7b678-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="7b678-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
