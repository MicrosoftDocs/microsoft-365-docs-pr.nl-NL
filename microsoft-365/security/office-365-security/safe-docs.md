---
title: Veilige documenten in Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over veilige documenten in Microsoft 365 E5 of Microsoft 365 E5 Security.
ms.openlocfilehash: 1861671df5cfa9dab4b57d5fb53af8712a2a64ce
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811060"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="cbb74-103">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cbb74-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="cbb74-104">Safe Documents is een functie in Microsoft 365 E5 of Microsoft 365 E5 Security die [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) gebruikt om documenten en bestanden te scannen die zijn geopend in de beveiligde [weergave.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="cbb74-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cbb74-105">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="cbb74-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cbb74-106">Deze functie is alleen beschikbaar voor gebruikers met de Microsoft 365 E5- of Microsoft 365 E5-beveiligingslicentie.</span><span class="sxs-lookup"><span data-stu-id="cbb74-106">This feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security license.</span></span>

- <span data-ttu-id="cbb74-107">Veilige documenten zijn momenteel beschikbaar voor openbare preview, beschikbaar voor gebruikers die deel uitmaken van het [Office Insider-programma](https://insider.office.com/join) op huidig kanaal (Preview) met Office Version 2002 (12527.20092) of hoger.</span><span class="sxs-lookup"><span data-stu-id="cbb74-107">Safe Documents is currently available for public preview, available to users that are part of the [Office Insider Program](https://insider.office.com/join) on Current Channel (Preview) with Office Version 2002 (12527.20092) or greater.</span></span> <span data-ttu-id="cbb74-108">Deze functie is standaard uitgeschakeld en moet worden ingeschakeld door de beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="cbb74-108">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="cbb74-109">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbb74-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cbb74-110">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbb74-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cbb74-111">U moet machtigingen krijgen toegewezen voordat u de procedures in dit onderwerp uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="cbb74-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="cbb74-112">Als u veilige documenten wilt in- en configureren, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="cbb74-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="cbb74-113">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="cbb74-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="cbb74-114">Hoe gaat Microsoft om met uw gegevens?</span><span class="sxs-lookup"><span data-stu-id="cbb74-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="cbb74-115">Om u te beschermen, stuurt Safe Documents bestanden naar de [Microsoft Defender Advanced Threat Protection-cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse.</span><span class="sxs-lookup"><span data-stu-id="cbb74-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="cbb74-116">Details over hoe Microsoft Defender Advanced Thread Protection omgaat met uw gegevens vindt u [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="cbb74-116">Details on how Microsoft Defender Advanced Thread Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="cbb74-117">Naast de bovenstaande richtlijnen worden bestanden die door veilige documenten worden verzonden, niet langer bewaard in Defender dan de tijd die nodig is voor analyse, wat meestal minder dan 24 uur is</span><span class="sxs-lookup"><span data-stu-id="cbb74-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="cbb74-118">Gebruik het Security & Compliance Center om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="cbb74-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="cbb74-119">Open het Security & Compliance Center op <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="cbb74-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="cbb74-120">Ga **Threat management** naar \> ATP Safe Attachments voor **bedreigingsbeheer.** \> **ATP Safe Attachments**</span><span class="sxs-lookup"><span data-stu-id="cbb74-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="cbb74-121">Configureer in de sectie **Help-mensen veilig wanneer u vertrouwt dat een bestand buiten de sectie Beveiligde weergave in Office-toepassingen** wordt geopend, een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="cbb74-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="cbb74-122">**Veilige documenten voor Office-clients inschakelen (bestanden worden ook naar Microsoft Cloud verzonden voor diepgaande analyses)**</span><span class="sxs-lookup"><span data-stu-id="cbb74-122">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="cbb74-123">**Laat mensen door de beveiligde weergave klikken, zelfs als Veilige documenten het bestand als kwaadaardig identificeert:** We raden u aan deze optie niet in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="cbb74-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="cbb74-124">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="cbb74-124">When you're finished, click **Save**.</span></span>

![ATP Safe-bijlagenpagina](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="cbb74-126">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="cbb74-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="cbb74-127">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cbb74-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="cbb74-128">De parameter _EnableSafeDocs_ schakelt veilige documenten voor de hele organisatie in of uit.</span><span class="sxs-lookup"><span data-stu-id="cbb74-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="cbb74-129">Met de parameter _AllowSafeDocsOpen_ kunnen of voorkomen dat gebruikers de beveiligde weergave verlaten (dat wil zeggen het document openen) als het document als kwaadaardig is aangemerkt.</span><span class="sxs-lookup"><span data-stu-id="cbb74-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="cbb74-130">In dit voorbeeld worden veilige documenten voor de hele organisatie mogelijk en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als kwaadaardig in de beveiligde weergave.</span><span class="sxs-lookup"><span data-stu-id="cbb74-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="cbb74-131">Zie [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="cbb74-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="cbb74-132">Hoe weet ik dat dit werkte?</span><span class="sxs-lookup"><span data-stu-id="cbb74-132">How do I know this worked?</span></span>

<span data-ttu-id="cbb74-133">Als u wilt controleren of u veilige documenten hebt ingeschakeld en geconfigureerd, voert u een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="cbb74-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="cbb74-134">Ga in het Security & Compliance Center naar **ATP** Safe Attachments voor \> **Policy** \> **bedreigingsbeheerbeleid**en controleer of de selecties in de **sectie Help-mensen veilig blijven wanneer ze vertrouwen dat een bestand buiten de sectie Beveiligde weergave in Office-toepassingen** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="cbb74-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="cbb74-135">Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:</span><span class="sxs-lookup"><span data-stu-id="cbb74-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
