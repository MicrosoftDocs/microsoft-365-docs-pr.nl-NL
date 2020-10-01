---
title: Office 365 ATP-SharePoint, OneDrive, & teams inschakelen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Meer informatie over het inschakelen van ATP voor SharePoint, OneDrive en teams, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326899"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="03cba-103">ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen</span><span class="sxs-lookup"><span data-stu-id="03cba-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="03cba-104">Office 365 Advanced Threat Protection (ATP) voor SharePoint, OneDrive en Microsoft teams beschermt uw organisatie per ongeluk om kwaadaardige bestanden te delen.</span><span class="sxs-lookup"><span data-stu-id="03cba-104">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="03cba-105">Zie [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="03cba-106">Dit artikel bevat de stappen voor het inschakelen en configureren van ATP voor SharePoint, OneDrive en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="03cba-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="03cba-107">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="03cba-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="03cba-108">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="03cba-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="03cba-109">Als u rechtstreeks naar de pagina met **veilige bijlage van ATP** wilt gaan, opent u deze <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="03cba-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="03cba-110">Als u ATP wilt inschakelen voor SharePoint, OneDrive en Microsoft teams, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** in het beveiligings & compliance Center.</span><span class="sxs-lookup"><span data-stu-id="03cba-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="03cba-111">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="03cba-112">Als u wilt voorkomen dat mensen schadelijke bestanden kunnen downloaden met SharePoint Online PowerShell, moet u lid zijn van de [globale beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) of [SharePoint-beheerders](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) rollen in azure AD.</span><span class="sxs-lookup"><span data-stu-id="03cba-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="03cba-113">Controleer of de logboekregistratie van het controle is ingeschakeld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="03cba-114">Zie [auditlogboek zoeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="03cba-115">Maximaal 30 minuten toestaan voordat de instellingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="03cba-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="03cba-116">Stap 1: gebruik het beveiligings & nalevings centrum om ATP voor SharePoint, OneDrive en Microsoft teams in te schakelen</span><span class="sxs-lookup"><span data-stu-id="03cba-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="03cba-117">Ga in het beveiligings & nalevings centrum naar veilige bijlagen voor het beleid voor **bedreigings beheer** \> **Policy** \> **ATP Safe Attachments**en klik op **globale instellingen**.</span><span class="sxs-lookup"><span data-stu-id="03cba-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="03cba-118">Ga in de **algemene instellingen** die worden weergegeven naar de instelling **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams** .</span><span class="sxs-lookup"><span data-stu-id="03cba-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="03cba-119">Zet de wisselknop naar rechts om de ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ATP voor SharePoint, OneDrive en Microsoft teams in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="03cba-119">Move the toggle to the right ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="03cba-120">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="03cba-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="03cba-121">Gebruik Exchange Online PowerShell om ATP voor SharePoint, OneDrive en Microsoft teams in te schakelen</span><span class="sxs-lookup"><span data-stu-id="03cba-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="03cba-122">[Maak verbinding met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) en voer de volgende opdracht uit als u liever PowerShell wilt gebruiken voor het inschakelen van ATP voor SharePoint, OneDrive en Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="03cba-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="03cba-123">Zie [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="03cba-124">Stap 2: (aanbevolen) SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden</span><span class="sxs-lookup"><span data-stu-id="03cba-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="03cba-125">Gebruikers kunnen standaard schadelijke bestanden die zijn gedetecteerd met ATP niet openen, verplaatsen, kopiëren of delen.</span><span class="sxs-lookup"><span data-stu-id="03cba-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="03cba-126">Ze kunnen echter wel schadelijke bestanden verwijderen en downloaden.</span><span class="sxs-lookup"><span data-stu-id="03cba-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="03cba-127">Als u wilt voorkomen dat gebruikers schadelijke bestanden downloaden, [maakt u verbinding met de PowerShell van SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="03cba-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="03cba-128">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="03cba-128">**Notes**:</span></span>

- <span data-ttu-id="03cba-129">Deze instelling is van invloed op gebruikers en beheerders.</span><span class="sxs-lookup"><span data-stu-id="03cba-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="03cba-130">Personen kunnen wel schadelijke bestanden verwijderen.</span><span class="sxs-lookup"><span data-stu-id="03cba-130">People can still delete malicious files.</span></span>

<span data-ttu-id="03cba-131">Zie [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="03cba-132">Stap 3 (aanbevolen) gebruik het beveiligings & nalevings centrum voor het maken van een waarschuwings beleid voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="03cba-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="03cba-133">U kunt een waarschuwings beleid maken waarmee u op de hoogte wordt gesteld van een kwaadaardige voor SharePoint, OneDrive en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="03cba-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="03cba-134">Zie voor meer informatie over waarschuwingen [activiteiten meldingen maken in het beveiligings & nalevings centrum](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="03cba-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="03cba-135">Ga in het [beveiligings & nalevings centrum](https://protection.office.com)naar **Alerts** \> **waarschuwings beleid** voor meldingen of open <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="03cba-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="03cba-136">Klik op de pagina met **waarschuwings beleidsregels** op **Nieuw waarschuwings beleid**.</span><span class="sxs-lookup"><span data-stu-id="03cba-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="03cba-137">De wizard **Nieuw waarschuwings beleid** wordt in één vliegtuig geopend. Configureer de volgende instellingen op de pagina **naam van uw waarschuwing** :</span><span class="sxs-lookup"><span data-stu-id="03cba-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="03cba-138">**Naam**: Typ een unieke en een beschrijvende naam.</span><span class="sxs-lookup"><span data-stu-id="03cba-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="03cba-139">Bijvoorbeeld Kwaadwillende bestanden in bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="03cba-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="03cba-140">**Beschrijving**: Typ een optionele beschrijving.</span><span class="sxs-lookup"><span data-stu-id="03cba-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="03cba-141">U kunt bijvoorbeeld beheerders een melding sturen wanneer er schadelijke bestanden zijn gevonden in SharePoint Online, OneDrive of Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="03cba-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="03cba-142">**Ernst**: Zorg dat de standaardwaarde **laag** is geselecteerd of selecteer **normaal** of **hoog**.</span><span class="sxs-lookup"><span data-stu-id="03cba-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="03cba-143">**Selecteer een categorie**: Selecteer **risicobeheer**.</span><span class="sxs-lookup"><span data-stu-id="03cba-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="03cba-144">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="03cba-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="03cba-145">Configureer de volgende instellingen op de pagina instellingen voor het **maken van waarschuwingen** :</span><span class="sxs-lookup"><span data-stu-id="03cba-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="03cba-146">**Waarover wilt u een bericht doorvoeren?: activiteit is**: Selecteer **malware gedetecteerd in bestand**.</span><span class="sxs-lookup"><span data-stu-id="03cba-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="03cba-147">**Hoe wilt u dat de waarschuwing wordt geactiveerd?**: de standaardwaarde behouden **wanneer er een activiteit met de regel** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="03cba-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="03cba-148">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="03cba-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="03cba-149">Configureer de volgende instellingen op de pagina de **geadresseerden instellen** :</span><span class="sxs-lookup"><span data-stu-id="03cba-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="03cba-150">**E-mail meldingen verzenden**: Controleer deze optie is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="03cba-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="03cba-151">Selecteer in het dialoogvenster **e-mail geadresseerden** een of meer globale beheerders, beveiligingsbeheerders of beveiligings lezers die een bericht moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="03cba-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="03cba-152">**Daglimiet voor meldingen**: de standaardwaarde **hoeft niet** te zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="03cba-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="03cba-153">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="03cba-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="03cba-154">Controleer de instellingen op de pagina **uw instellingen controleren** en klik in een van de secties op **bewerken** om wijzigingen door te voeren.</span><span class="sxs-lookup"><span data-stu-id="03cba-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="03cba-155">Laat in het gedeelte **wilt u het beleid direct inschakelen?** de standaardwaarde **Ja, schakel deze optie aan de rechterkant** uit.</span><span class="sxs-lookup"><span data-stu-id="03cba-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="03cba-156">Wanneer u klaar bent, klikt u op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="03cba-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="03cba-157">Beveiligings & naleving in PowerShell gebruiken voor het maken van een waarschuwings beleid voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="03cba-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="03cba-158">Als u liever PowerShell gebruikt om hetzelfde waarschuwings beleid te maken zoals wordt beschreven in de vorige sectie, maakt u verbinding met de [beveiliging & nalevings centrum PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="03cba-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="03cba-159">**Opmerking**: de standaardwaarde voor de _Ernst_ is laag.</span><span class="sxs-lookup"><span data-stu-id="03cba-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="03cba-160">Als u gemiddeld of hoog wilt opgeven, voegt u de parameter voor de _Ernst_ en de waarde in de opdracht toe.</span><span class="sxs-lookup"><span data-stu-id="03cba-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="03cba-161">Zie [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="03cba-162">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="03cba-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="03cba-163">Voer een van de volgende stappen uit om te controleren of u de ATP hebt ingeschakeld voor SharePoint, OneDrive en Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="03cba-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="03cba-164">Ga in het [beveiligings & compliance](https://protection.office.com)naar veilige bijlagen voor het beleid voor **risicobeheer** \> **Policy** \> **ATP Safe Attachments**, selecteer **globale instellingen**en controleer de waarde van de instelling **ATP voor SharePoint, OneDrive en Microsoft teams inschakelen** .</span><span class="sxs-lookup"><span data-stu-id="03cba-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="03cba-165">In Exchange Online PowerShell voert u de volgende opdracht uit om de instelling van de eigenschap te controleren:</span><span class="sxs-lookup"><span data-stu-id="03cba-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="03cba-166">Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="03cba-167">Als u wilt controleren of u bent geblokkeerd voor het downloaden van schadelijke bestanden, opent u SharePoint Online PowerShell en voert u de volgende opdracht uit om de waarde van de eigenschap te controleren:</span><span class="sxs-lookup"><span data-stu-id="03cba-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="03cba-168">Zie [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="03cba-169">Voer een van de volgende stappen uit om te controleren of u een waarschuwings beleid voor gedetecteerde bestanden hebt geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="03cba-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="03cba-170">Ga in het beveiligings & compliance naar waarschuwings beleid voor **waarschuwingen** , \> **Alert policies** \> Selecteer het waarschuwings beleid en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="03cba-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="03cba-171">In het beveiligings & nalevings centrum voor PowerShell, vervangt u de \<AlertPolicyName\> naam van het waarschuwings beleid, voert u de volgende opdracht uit en controleert u de eigenschapwaarden:</span><span class="sxs-lookup"><span data-stu-id="03cba-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="03cba-172">Zie [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="03cba-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="03cba-173">Met het [rapport status beveiliging](view-email-security-reports.md#threat-protection-status-report) kunt u informatie weergeven over gedetecteerde bestanden in SharePoint, OneDrive en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="03cba-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="03cba-174">Met name kunt u de weergave **gegevens weergeven op: \> schadelijke inhoud** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="03cba-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
