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
description: Meer informatie over Safe documenten in Microsoft 365 E5 of Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e1bd2150a04e51e0d06c6cd1c17a71a032df1a5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108605"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="f27b3-103">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f27b3-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f27b3-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="f27b3-104">**Applies to**</span></span>
- [<span data-ttu-id="f27b3-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f27b3-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f27b3-106">Safe Documenten is een functie in Microsoft 365 E5 of Microsoft 365 E5 Security die [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor Eindpunt gebruikt om documenten en bestanden te scannen die [worden](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) geopend in de beveiligde weergave of Application Guard voor [Office.](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)</span><span class="sxs-lookup"><span data-stu-id="f27b3-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f27b3-107">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f27b3-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f27b3-108">Safe Documenten zijn alleen beschikbaar voor gebruikers met *Microsoft 365 E5* of *Microsoft 365 E5 Security* licenties.</span><span class="sxs-lookup"><span data-stu-id="f27b3-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="f27b3-109">Deze licenties zijn niet opgenomen in Microsoft Defender voor Office 365 abonnementen.</span><span class="sxs-lookup"><span data-stu-id="f27b3-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="f27b3-110">Safe Documenten wordt ondersteund in Microsoft 365-apps voor ondernemingen (voorheen bekend als Office 365 ProPlus) versie 2004 of hoger.</span><span class="sxs-lookup"><span data-stu-id="f27b3-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="f27b3-111">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="f27b3-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="f27b3-112">Als u rechtstreeks naar de pagina Safe **bijlagen** wilt gaan, gebruikt u <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="f27b3-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="f27b3-113">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f27b3-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f27b3-114">U hebt machtigingen nodig in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="f27b3-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f27b3-115">Als u Safe documenteninstellingen wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="f27b3-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f27b3-116">Als u alleen-lezen toegang wilt tot Safe documenteninstellingen, moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="f27b3-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f27b3-117">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f27b3-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="f27b3-118">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f27b3-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f27b3-119">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f27b3-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="f27b3-120">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="f27b3-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="f27b3-121">Hoe gaat Microsoft om met uw gegevens?</span><span class="sxs-lookup"><span data-stu-id="f27b3-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="f27b3-122">Om u te beschermen, Safe documenten bestanden naar de [Microsoft Defender voor Eindpunt-cloud](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse.</span><span class="sxs-lookup"><span data-stu-id="f27b3-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="f27b3-123">Meer informatie over hoe Microsoft Defender voor Eindpunt met uw gegevens omgaat, vindt u hier: Microsoft Defender voor opslag en privacy van [eindpuntgegevens.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="f27b3-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="f27b3-124">Bestanden die door Safe Documenten worden niet bewaard in Defender na de tijd die nodig is voor analyse (meestal minder dan 24 uur).</span><span class="sxs-lookup"><span data-stu-id="f27b3-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="f27b3-125">De Microsoft 365 Defender gebruiken om documenten Safe configureren</span><span class="sxs-lookup"><span data-stu-id="f27b3-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="f27b3-126">Open de Microsoft 365 Defender portal en ga naar **E-mail & samenwerkingsbeleid** & pagina Beleidsregels voor bedreigingsbeleid Safe \>  \>  \>  \> **Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="f27b3-126">Open the Microsoft 365 Defender portal and go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="f27b3-127">Klik op **Safe pagina Bijlagen** op Algemene **instellingen.**</span><span class="sxs-lookup"><span data-stu-id="f27b3-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="f27b3-128">Configureer **de volgende instellingen** in de algemene instellingen die worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f27b3-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="f27b3-129">**Schakel Safe documenten in voor Office clients:** Verplaats de schakelknop naar rechts om de functie in te ![ schakelen: In- of ](../../media/scc-toggle-on.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="f27b3-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="f27b3-130">**Toestaan dat** personen door de beveiligde weergave kunnen klikken, zelfs als Safe Documenten het bestand als schadelijk hebben aangemerkt: U wordt aangeraden deze optie uitgeschakeld te laten (laat de schakeloptie links staan: Schakel de schakeloptie ![ ](../../media/scc-toggle-off.png) uit).</span><span class="sxs-lookup"><span data-stu-id="f27b3-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="f27b3-131">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="f27b3-131">When you're finished, click **Save**.</span></span>

   ![Safe Documenteninstellingen nadat u Globale instellingen op de pagina Safe bijlagen.](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="f27b3-133">PowerShell Exchange Online gebruiken om documenten Safe configureren</span><span class="sxs-lookup"><span data-stu-id="f27b3-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="f27b3-134">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f27b3-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="f27b3-135">Met _de parameter EnableSafeDocs_ worden Safe documenten voor de hele organisatie in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f27b3-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="f27b3-136">Met _de parameter AllowSafeDocsOpen_ kunnen of voorkomen dat gebruikers de beveiligde weergave (dat wil zeggen het openen van het document) verlaten als het document is geïdentificeerd als schadelijk.</span><span class="sxs-lookup"><span data-stu-id="f27b3-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="f27b3-137">In dit voorbeeld kunt Safe documenten voor de hele organisatie gebruiken en voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als schadelijk vanuit de beveiligde weergave.</span><span class="sxs-lookup"><span data-stu-id="f27b3-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="f27b3-138">Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f27b3-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="f27b3-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span><span class="sxs-lookup"><span data-stu-id="f27b3-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="f27b3-140">Als u Microsoft Defender voor Eindpunt wilt implementeren, moet u de verschillende fasen van de implementatie doorlopen.</span><span class="sxs-lookup"><span data-stu-id="f27b3-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="f27b3-141">Na onboarding kunt u controlemogelijkheden configureren in de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="f27b3-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="f27b3-142">Zie Onboard to the Microsoft Defender for Endpoint service (Onboard [to the Microsoft Defender for Endpoint service)](/microsoft-365/security/defender-endpoint/onboarding)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f27b3-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="f27b3-143">Als u extra hulp nodig hebt, raadpleegt u Microsoft Defender oplossen voor problemen met de [onboarding van eindpunten.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="f27b3-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="f27b3-144">Hoe weet ik of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="f27b3-144">How do I know this worked?</span></span>

<span data-ttu-id="f27b3-145">Als u wilt controleren of u documenten hebt ingeschakeld en geconfigureerd Safe documenten, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="f27b3-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="f27b3-146">Ga in de Microsoft 365 Defender-portal naar Het beleid voor e-mail **&** samenwerkingsbeleid & De pagina Beleidsregels voor bedreigingsbeleidsregels voor regels Safe Algemene instellingen bijlagen en controleer de sectie Safe-documenten in- en uitschakelen voor \>  \>  \>  \>  \>  **Office-clients**  en Personen toestaan door de beveiligde weergave te klikken, zelfs als Safe Documenten het bestand identificeert als schadelijke instellingen.</span><span class="sxs-lookup"><span data-stu-id="f27b3-146">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="f27b3-147">Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:</span><span class="sxs-lookup"><span data-stu-id="f27b3-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="f27b3-148">De volgende bestanden zijn beschikbaar om de Safe documenten te testen.</span><span class="sxs-lookup"><span data-stu-id="f27b3-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="f27b3-149">Deze documenten zijn vergelijkbaar met het EICAR.TXT bestand voor het testen van anti-malware- en anti-virusoplossingen.</span><span class="sxs-lookup"><span data-stu-id="f27b3-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="f27b3-150">De bestanden zijn niet schadelijk, maar ze worden wel Safe documentenbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="f27b3-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="f27b3-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="f27b3-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="f27b3-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="f27b3-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="f27b3-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="f27b3-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
