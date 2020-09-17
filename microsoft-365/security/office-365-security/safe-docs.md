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
ms.openlocfilehash: 8918c7da26a60c7cfd64b7148d0added82cc6642
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949452"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="32c6f-103">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="32c6f-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="32c6f-104">Veilige documenten is een functie in Microsoft 365 E5 of Microsoft 365 E5-beveiliging waarbij [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) gebruikmaakt voor het scannen van documenten en bestanden die worden geopend in de [beveiligde weergave](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="32c6f-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="32c6f-105">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="32c6f-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="32c6f-106">Veilige documenten zijn nu algemeen beschikbaar voor gebruikers met Office versie 2004 (12730. x) of hoger.</span><span class="sxs-lookup"><span data-stu-id="32c6f-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="32c6f-107">Deze functie is standaard uitgeschakeld en moet worden ingeschakeld door de beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="32c6f-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="32c6f-108">Deze functie is alleen beschikbaar voor gebruikers met de beveiligings licentie voor *Microsoft 365 E5* of *Microsoft 365 E5* (deze functie is niet opgenomen in Office 365 ATP-abonnementen).</span><span class="sxs-lookup"><span data-stu-id="32c6f-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="32c6f-109">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32c6f-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="32c6f-110">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32c6f-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="32c6f-111">Voor meer informatie over</span><span class="sxs-lookup"><span data-stu-id="32c6f-111">For more information about</span></span> 

- <span data-ttu-id="32c6f-112">U moet machtigingen zijn toegewezen voordat u de procedures in dit onderwerp kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="32c6f-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="32c6f-113">Als u veilige documenten wilt inschakelen en configureren, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="32c6f-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="32c6f-114">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="32c6f-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="32c6f-115">Hoe bewerkt Microsoft uw gegevens?</span><span class="sxs-lookup"><span data-stu-id="32c6f-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="32c6f-116">Om te beschermen, worden met veilige documenten bestanden naar de [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) -Cloud verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="32c6f-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="32c6f-117">In [dit onderwerp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)vindt u meer informatie over de manier waarop u uw gegevens kunt vinden in Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="32c6f-117">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>
- <span data-ttu-id="32c6f-118">Naast de bovenstaande richtlijnen, worden bestanden die zijn verzonden via veilige documenten niet bewaard na de tijd die nodig is om te worden geanalyseerd, wat meestal minder dan 24 uur duurt.</span><span class="sxs-lookup"><span data-stu-id="32c6f-118">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours.</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="32c6f-119">Beveiligings & voor naleving van Beveiligingscentrum gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="32c6f-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="32c6f-120">Open het beveiligings & nalevings centrum op <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="32c6f-120">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="32c6f-121">Ga naar **Threat management** \> **Policy** \> **veilige bijlagen**voor het beleid voor risicobeheer.</span><span class="sxs-lookup"><span data-stu-id="32c6f-121">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="32c6f-122">Configureer een van de volgende instellingen in de sectie **Help personen veilig houden wanneer u een bestand vertrouwt om buiten de beveiligde weergave te openen in** de sectie Office-toepassingen:</span><span class="sxs-lookup"><span data-stu-id="32c6f-122">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="32c6f-123">**Veilige documenten voor Office-clients inschakelen**</span><span class="sxs-lookup"><span data-stu-id="32c6f-123">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="32c6f-124">**Toestaan dat mensen kunnen klikken via de beveiligde weergave, zelfs als een veilig document het bestand als schadelijk identificeert**: u wordt aangeraden deze optie niet in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="32c6f-124">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="32c6f-125">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="32c6f-125">When you're finished, click **Save**.</span></span>

![Pagina voor veilige bijlagen met ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="32c6f-127">Veilige documenten configureren met Exchange Online PowerShell of zelfstandige EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="32c6f-127">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="32c6f-128">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="32c6f-128">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="32c6f-129">Met de parameter _EnableSafeDocs_ kunt u veilige documenten voor de hele organisatie in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="32c6f-129">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="32c6f-130">Met de parameter _AllowSafeDocsOpen_ kunt u of voorkomen dat gebruikers de beveiligde weergave verlaten (dat wil zeggen, het document openen) als het document is geïdentificeerd als schadelijk.</span><span class="sxs-lookup"><span data-stu-id="32c6f-130">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="32c6f-131">In dit voorbeeld worden veilige documenten ingeschakeld voor de hele organisatie en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als schadelijk voor de beveiligde weergave.</span><span class="sxs-lookup"><span data-stu-id="32c6f-131">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="32c6f-132">Zie [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="32c6f-132">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="32c6f-133">Hoe weet ik of ik dit heb gewerkt?</span><span class="sxs-lookup"><span data-stu-id="32c6f-133">How do I know this worked?</span></span>

<span data-ttu-id="32c6f-134">Ga op een van de volgende manieren te werk om te controleren of u veilige documenten hebt ingeschakeld en geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="32c6f-134">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="32c6f-135">Ga in het beveiligings & compliance naar veilige bijlagen voor het beleid voor **bedreigings beheer** \> **Policy** \> **ATP Safe Attachments**en controleer de selecties in de secties **Help-personen veilig blijven als u een bestand vertrouwt om buiten de beveiligde weergave te openen in** de sectie Office-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="32c6f-135">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="32c6f-136">Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapwaarden.</span><span class="sxs-lookup"><span data-stu-id="32c6f-136">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
