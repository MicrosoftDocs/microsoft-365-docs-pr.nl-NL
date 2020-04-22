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
description: Meer informatie over veilige documenten in Office 365 ATP.
ms.openlocfilehash: b70c7013ce038a3934b7ea5e62d1d0530f12e4e6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634314"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="4ac6c-103">Veilige documenten in geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="4ac6c-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="4ac6c-104">Safe Documents is een functie in Office 365 Advanced Threat Protection (ATP) die [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) gebruikt om documenten en bestanden te scannen die in de beveiligde [weergave](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)worden geopend.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4ac6c-105">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="4ac6c-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4ac6c-106">Deze functie is alleen beschikbaar voor gebruikers met de Microsoft 365 E5- of Microsoft 365 E5-beveiligingslicentie.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-106">This feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security license.</span></span>

- <span data-ttu-id="4ac6c-107">Veilige documenten zijn momenteel beschikbaar voor een openbare preview, beschikbaar voor gebruikers die deel uitmaken van het [Office Insider-programma](https://insider.office.com/en-us/join) op het 'Monthly Channel (Targeted)' met Office Version 2002 (12527.20092) of hoger.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-107">Safe Documents is currently available for public preview, available to users that are part of the [Office Insider Program](https://insider.office.com/en-us/join) on the 'Monthly Channel (Targeted)' with Office Version 2002 (12527.20092) or greater.</span></span> <span data-ttu-id="4ac6c-108">Deze functie is standaard uitgeschakeld en moet worden ingeschakeld door de beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-108">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="4ac6c-109">Alleen de Amerikaanse regio wordt momenteel ondersteund voor compatibele bestandsverwerking (Alle bestanden worden naar de Amerikaanse regio afgereisd om te scannen).</span><span class="sxs-lookup"><span data-stu-id="4ac6c-109">Only US Region currently supported for compliant file processing (All files will travel to the US Region for scanning).</span></span> <span data-ttu-id="4ac6c-110">Steun voor de VK/EU-regio is gepland in een toekomstige update.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-110">Support for UK/EU region is planned in a future update.</span></span>

- <span data-ttu-id="4ac6c-111">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4ac6c-112">Zie Verbinding maken met Exchange [Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u verbinding wilt maken met Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-112">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4ac6c-113">U moet machtigingen toegewezen krijgen voordat u de procedures in dit onderwerp uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-113">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="4ac6c-114">Als u veilige documenten wilt in- en configureren, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="4ac6c-114">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="4ac6c-115">Zie Machtigingen in het Security & Compliance [Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rolgroepen in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="4ac6c-116">Het beveiligingscentrum & compliance center gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="4ac6c-116">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="4ac6c-117">Open het Security & <https://protection.office.com>Compliance Center op .</span><span class="sxs-lookup"><span data-stu-id="4ac6c-117">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="4ac6c-118">Ga naar **ATP-veilige bijlagen**voor **bedreigingsbeheerbeleid** \> **Policy** \> .</span><span class="sxs-lookup"><span data-stu-id="4ac6c-118">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="4ac6c-119">Configureer een van de volgende instellingen in de **sectie Help-personen die veilig zijn wanneer ze een bestand buiten de beveiligde weergave in office-toepassingen vertrouwen,** een van de volgende instellingen configureren:</span><span class="sxs-lookup"><span data-stu-id="4ac6c-119">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="4ac6c-120">**Veilige documenten inschakelen voor Office-clients (bestanden worden ook naar Microsoft Cloud verzonden voor diepgaande analyses)**</span><span class="sxs-lookup"><span data-stu-id="4ac6c-120">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="4ac6c-121">**Personen toestaan om door de beveiligde weergave te klikken, zelfs als safe documents het bestand als kwaadaardig identificeert:** we raden u aan deze optie niet in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-121">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="4ac6c-122">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-122">When you're finished, click **Save**.</span></span>

![Pagina ATP Safe-bijlagen](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="4ac6c-124">Exchange Online PowerShell of Exchange Online Protection PowerShell gebruiken om veilige documenten te configureren</span><span class="sxs-lookup"><span data-stu-id="4ac6c-124">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="4ac6c-125">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="4ac6c-125">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="4ac6c-126">Met de parameter _EnableSafeDocs_ worden veilige documenten voor de hele organisatie in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-126">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="4ac6c-127">Met de parameter _AllowSafeDocsOpen_ kunnen of voorkomen dat gebruikers de beveiligde weergave verlaten (dat wil zeggen het openen van het document) als het document als kwaadaardig is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-127">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="4ac6c-128">In dit voorbeeld worden veilige documenten voor de hele organisatie ingeschakeld en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als kwaadaardig vanuit de beveiligde weergave.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-128">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="4ac6c-129">Zie [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="4ac6c-129">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="4ac6c-130">Hoe weet ik dat dit werkte?</span><span class="sxs-lookup"><span data-stu-id="4ac6c-130">How do I know this worked?</span></span>

<span data-ttu-id="4ac6c-131">Ga een van de volgende stappen uit om te controleren of u veilige documenten hebt ingeschakeld en geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="4ac6c-131">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="4ac6c-132">Ga in het Security & Compliance Center naar ATP \> **Safe Attachments**voor **bedreigingsbeheerbeleid** \> **Policy** en controleer of de selecties in de **sectie Help-personen veilig blijven wanneer ze een bestand vertrouwen dat wordt geopend buiten de sectie Beveiligde weergave in Office-toepassingen.**</span><span class="sxs-lookup"><span data-stu-id="4ac6c-132">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="4ac6c-133">Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:</span><span class="sxs-lookup"><span data-stu-id="4ac6c-133">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
