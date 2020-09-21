---
title: Veilige documenten in Office 365 ATP
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
ms.openlocfilehash: 5e91c226102d60368bf08b09ae5f0239f63599d5
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132215"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="96de3-103">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="96de3-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="96de3-104">Veilige documenten is een functie in Microsoft 365 E5 of Microsoft 365 E5-beveiliging waarbij [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) gebruikmaakt voor het scannen van documenten en bestanden die worden geopend in de [beveiligde weergave](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="96de3-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="96de3-105">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="96de3-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="96de3-106">Veilige documenten zijn alleen beschikbaar voor gebruikers met de beveiligings licenties voor *Microsoft 365 E5* of *Microsoft 365 E5* .</span><span class="sxs-lookup"><span data-stu-id="96de3-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="96de3-107">Deze licenties zijn niet opgenomen in Office 365 Advanced Threat Protection (ATP)-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="96de3-107">These licenses are not included in Office 365 Advanced Threat Protection (ATP) plans.</span></span>

- <span data-ttu-id="96de3-108">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="96de3-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="96de3-109">Als u rechtstreeks naar de pagina met **veilige bijlage van ATP** wilt gaan, opent u deze <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="96de3-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="96de3-110">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96de3-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="96de3-111">U moet machtigingen zijn toegewezen voordat u de procedures in dit onderwerp kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="96de3-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="96de3-112">Als u veilige documenten wilt inschakelen en configureren, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="96de3-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="96de3-113">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="96de3-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="96de3-114">Om te beschermen, worden met veilige documenten bestanden naar de [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) -Cloud verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="96de3-114">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="96de3-115">Meer informatie over de manier waarop u uw gegevens in Microsoft Defender ATP verwerkt, vindt u hier: [Microsoft Defender ATP data storage en privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="96de3-115">Details on how Microsoft Defender ATP handles your data can be found here: [Microsoft Defender ATP data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

- <span data-ttu-id="96de3-116">Bestanden die door veilige documenten zijn verzonden, worden niet langer bewaard dan de tijd die nodig is voor de analyse (meestal minder dan 24 uur).</span><span class="sxs-lookup"><span data-stu-id="96de3-116">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="96de3-117">Beveiligings & voor naleving van Beveiligingscentrum gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="96de3-117">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="96de3-118">Ga in het beveiligings & compliance naar veilige bijlagen voor het beleid voor **bedreigings beheer** \> **Policy** \> **ATP Safe Attachments**en klik vervolgens op **algemene instellingen**.</span><span class="sxs-lookup"><span data-stu-id="96de3-118">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="96de3-119">Configureer de volgende instellingen in de **algemene instellingen** die worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="96de3-119">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="96de3-120">**Veilige documenten inschakelen voor Office-clients**: zet de wisselknop naar rechts om de functie in te schakelen: ![ wisselknop ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="96de3-120">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="96de3-121">**Toestaan dat personen kunnen klikken via de beveiligde weergave, zelfs als de veilige documenten het bestand als schadelijk identificeren**: u wordt aangeraden deze optie uit te schakelen (laat de schakeloptie links: ![ uit ](../../media/scc-toggle-off.png) ) staan.</span><span class="sxs-lookup"><span data-stu-id="96de3-121">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="96de3-122">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="96de3-122">When you're finished, click **Save**.</span></span>

   ![Instellingen voor veilige documenten nadat u wereldwijde instellingen hebt geselecteerd op de pagina met veilige ATP-bijlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="96de3-124">Veilige documenten configureren met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="96de3-124">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="96de3-125">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="96de3-125">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="96de3-126">Met de parameter _EnableSafeDocs_ kunt u veilige documenten voor de hele organisatie in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="96de3-126">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="96de3-127">Met de parameter _AllowSafeDocsOpen_ kunt u of voorkomen dat gebruikers de beveiligde weergave verlaten (dat wil zeggen, het document openen) als het document is geïdentificeerd als schadelijk.</span><span class="sxs-lookup"><span data-stu-id="96de3-127">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="96de3-128">In dit voorbeeld worden veilige documenten ingeschakeld voor de hele organisatie en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als schadelijk voor de beveiligde weergave.</span><span class="sxs-lookup"><span data-stu-id="96de3-128">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="96de3-129">Zie [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="96de3-129">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="96de3-130">Hoe weet ik of ik dit heb gewerkt?</span><span class="sxs-lookup"><span data-stu-id="96de3-130">How do I know this worked?</span></span>

<span data-ttu-id="96de3-131">Ga op een van de volgende manieren te werk om te controleren of u veilige documenten hebt ingeschakeld en geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="96de3-131">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="96de3-132">Ga in het beveiligings & compliance **naar het** beleid voor het oplossen van beveiligingsfuncties, ga naar \> **Policy** \> **veilige bijlagen** **voor Office** , klik op **algemene instellingen**en zorg ervoor **dat personen kunnen klikken op de beveiligde weergave, ongeacht of het bestand wordt geïdentificeerd als kwaadwillende documenten** .</span><span class="sxs-lookup"><span data-stu-id="96de3-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="96de3-133">Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapwaarden.</span><span class="sxs-lookup"><span data-stu-id="96de3-133">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="96de3-134">De volgende bestanden kunnen worden gebruikt om de beveiliging van veilige documenten te testen.</span><span class="sxs-lookup"><span data-stu-id="96de3-134">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="96de3-135">Deze documenten lijken op het EICAR.TXT-bestand voor het testen van anti-malware en anti-virus oplossingen.</span><span class="sxs-lookup"><span data-stu-id="96de3-135">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="96de3-136">De bestanden zijn niet schadelijk, maar de bescherming van veilige documenten wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="96de3-136">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="96de3-137">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="96de3-137">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="96de3-138">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="96de3-138">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="96de3-139">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="96de3-139">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
