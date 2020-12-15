---
title: Veilige documenten in Microsoft Defender voor Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over veilige documenten in Microsoft 365 E5 of Microsoft 365 E5 beveiliging.
ms.openlocfilehash: 1bf802422dc05babaf5e2616468f8326b7007dc8
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682935"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="13b17-103">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="13b17-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="13b17-104">Veilige documenten is een functie in Microsoft 365 E5 of Microsoft 365 E5-beveiliging waarbij [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) wordt gebruikt om documenten en bestanden te scannen die worden geopend in de [beveiligde weergave](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="13b17-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="13b17-105">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="13b17-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="13b17-106">Veilige documenten zijn alleen beschikbaar voor gebruikers met de beveiligings licenties voor *Microsoft 365 E5* of *Microsoft 365 E5* .</span><span class="sxs-lookup"><span data-stu-id="13b17-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="13b17-107">Deze licenties zijn niet opgenomen in Microsoft Defender for Office 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="13b17-107">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="13b17-108">Veilige documenten worden ondersteund in Microsoft 365-apps voor Enterprise (voorheen bekend als Office 365 ProPlus) versie 2004 of hoger.</span><span class="sxs-lookup"><span data-stu-id="13b17-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="13b17-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="13b17-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="13b17-110">Als u rechtstreeks naar de pagina met **veilige bijlage van ATP** wilt gaan, opent u deze <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="13b17-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="13b17-111">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13b17-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="13b17-112">Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="13b17-112">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="13b17-113">Als u instellingen voor veilige documenten wilt configureren, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="13b17-113">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="13b17-114">Voor alleen-lezen toegang tot instellingen voor veilige documenten moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .</span><span class="sxs-lookup"><span data-stu-id="13b17-114">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="13b17-115">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="13b17-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="13b17-116">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="13b17-116">**Notes**:</span></span>

  - <span data-ttu-id="13b17-117">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b17-117">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="13b17-118">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="13b17-118">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="13b17-119">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="13b17-119">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="13b17-120">Hoe bewerkt Microsoft uw gegevens?</span><span class="sxs-lookup"><span data-stu-id="13b17-120">How does Microsoft handle your data?</span></span>

<span data-ttu-id="13b17-121">Om te beschermen, worden met veilige documenten bestanden naar de [Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) van de Cloud verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="13b17-121">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="13b17-122">In dit onderwerp vindt u informatie over de manier waarop u uw gegevens kunt vinden in Microsoft Defender for endpoints: [Microsoft Defender for Endpoint data storage en privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="13b17-122">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="13b17-123">Bestanden die door veilige documenten zijn verzonden, worden niet langer bewaard dan de tijd die nodig is voor de analyse (meestal minder dan 24 uur).</span><span class="sxs-lookup"><span data-stu-id="13b17-123">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="13b17-124">Beveiligings & voor naleving van Beveiligingscentrum gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="13b17-124">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="13b17-125">Ga in het beveiligings & compliance naar veilige bijlagen voor het beleid voor **bedreigings beheer** \>  \> en klik vervolgens op **algemene instellingen**.</span><span class="sxs-lookup"><span data-stu-id="13b17-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="13b17-126">Configureer de volgende instellingen in de **algemene instellingen** die worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="13b17-126">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="13b17-127">**Veilige documenten inschakelen voor Office-clients**: zet de wisselknop naar rechts om de functie in te schakelen: ![ wisselknop ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="13b17-127">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="13b17-128">**Toestaan dat personen kunnen klikken via de beveiligde weergave, zelfs als de veilige documenten het bestand als schadelijk identificeren**: u wordt aangeraden deze optie uit te schakelen (laat de schakeloptie links: ![ uit ](../../media/scc-toggle-off.png) ) staan.</span><span class="sxs-lookup"><span data-stu-id="13b17-128">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="13b17-129">Wanneer u gereed bent, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="13b17-129">When you're finished, click **Save**.</span></span>

   ![Instellingen voor veilige documenten nadat u wereldwijde instellingen hebt geselecteerd op de pagina voor veilige bijlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="13b17-131">Veilige documenten configureren met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="13b17-131">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="13b17-132">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="13b17-132">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="13b17-133">Met de parameter _EnableSafeDocs_ kunt u veilige documenten voor de hele organisatie in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="13b17-133">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="13b17-134">Met de parameter _AllowSafeDocsOpen_ kunt u of voorkomen dat gebruikers de beveiligde weergave verlaten (dat wil zeggen, het document openen) als het document is geïdentificeerd als schadelijk.</span><span class="sxs-lookup"><span data-stu-id="13b17-134">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="13b17-135">In dit voorbeeld worden veilige documenten ingeschakeld voor de hele organisatie en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als schadelijk voor de beveiligde weergave.</span><span class="sxs-lookup"><span data-stu-id="13b17-135">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="13b17-136">Zie [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="13b17-136">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="13b17-137">Hoe weet ik of ik dit heb gewerkt?</span><span class="sxs-lookup"><span data-stu-id="13b17-137">How do I know this worked?</span></span>

<span data-ttu-id="13b17-138">Ga op een van de volgende manieren te werk om te controleren of u veilige documenten hebt ingeschakeld en geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="13b17-138">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="13b17-139">Ga in het beveiligings & compliance **naar het** beleid voor het oplossen van beveiligingsfuncties, ga naar \>  \> **veilige bijlagen** **voor Office** , klik op **algemene instellingen** en zorg ervoor **dat personen kunnen klikken op de beveiligde weergave, ongeacht of het bestand wordt geïdentificeerd als kwaadwillende documenten** .</span><span class="sxs-lookup"><span data-stu-id="13b17-139">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="13b17-140">Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapwaarden.</span><span class="sxs-lookup"><span data-stu-id="13b17-140">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="13b17-141">De volgende bestanden kunnen worden gebruikt om de beveiliging van veilige documenten te testen.</span><span class="sxs-lookup"><span data-stu-id="13b17-141">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="13b17-142">Deze documenten lijken op het EICAR.TXT-bestand voor het testen van anti-malware en anti-virus oplossingen.</span><span class="sxs-lookup"><span data-stu-id="13b17-142">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="13b17-143">De bestanden zijn niet schadelijk, maar de bescherming van veilige documenten wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="13b17-143">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="13b17-144">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="13b17-144">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="13b17-145">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="13b17-145">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="13b17-146">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="13b17-146">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
