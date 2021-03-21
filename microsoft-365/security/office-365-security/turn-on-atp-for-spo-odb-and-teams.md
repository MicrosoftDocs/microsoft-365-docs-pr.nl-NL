---
title: Veilige bijlagen uitschakelen voor SharePoint, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Beheerders kunnen leren hoe ze Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in kunnen zetten, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 300cb3e004010e8ff22de7393d3f3e039bf8cfdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921142"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="b77a5-103">Veilige bijlagen uitschakelen voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b77a5-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b77a5-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b77a5-104">**Applies to**</span></span>
- [<span data-ttu-id="b77a5-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b77a5-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b77a5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b77a5-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b77a5-107">Microsoft Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams beschermt uw organisatie tegen onbedoeld delen van schadelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="b77a5-108">Zie Veilige bijlagen voor [SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b77a5-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="b77a5-109">Dit artikel bevat de stappen voor het in- en configureren van veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b77a5-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b77a5-110">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="b77a5-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b77a5-111">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="b77a5-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="b77a5-112">Als u rechtstreeks naar de **pagina Veilige bijlagen van ATP** wilt gaan, opent u <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="b77a5-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="b77a5-113">Als u Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams wilt  in-  en uit te zetten, moet u lid zijn van de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b77a5-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="b77a5-114">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b77a5-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b77a5-115">Als u SharePoint Online PowerShell wilt gebruiken om te voorkomen dat [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) personen schadelijke bestanden downloaden, moet u lid zijn van de rollen globale beheerder of [SharePoint-beheerder](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b77a5-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="b77a5-116">Controleer of auditregistratie is ingeschakeld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b77a5-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="b77a5-117">Zie Zoeken in [auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="b77a5-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="b77a5-118">Laat de instellingen maximaal 30 minuten van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="b77a5-119">Stap 1: Gebruik het beveiligings- & compliancecentrum om veilige bijlagen in te zetten voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b77a5-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="b77a5-120">Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments** en klik op **Algemene instellingen.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="b77a5-121">Ga in **de algemene** instellingen die worden weergegeven naar de instelling Defender in- en uitschakelen voor **Office 365 voor SharePoint, OneDrive en Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="b77a5-122">Verplaats de schakelknop naar rechts Om veilige bijlagen in te schakelen voor ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b77a5-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="b77a5-123">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="b77a5-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="b77a5-124">Exchange Online PowerShell gebruiken om veilige bijlagen in te zetten voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b77a5-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="b77a5-125">Als u Liever PowerShell gebruikt om veilige bijlagen in te zetten voor SharePoint, OneDrive en Microsoft Teams, maakt u verbinding met [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="b77a5-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="b77a5-126">Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b77a5-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="b77a5-127">Stap 2: (Aanbevolen) Gebruik SharePoint Online PowerShell om te voorkomen dat gebruikers schadelijke bestanden downloaden</span><span class="sxs-lookup"><span data-stu-id="b77a5-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="b77a5-128">Gebruikers kunnen schadelijke bestanden die door ATP worden gedetecteerd, standaard niet openen, verplaatsen, kopiëren of delen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="b77a5-129">Ze kunnen echter schadelijke bestanden verwijderen en downloaden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="b77a5-130">Als u wilt voorkomen dat gebruikers schadelijke bestanden downloaden, maakt u [verbinding met SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="b77a5-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="b77a5-131">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="b77a5-131">**Notes**:</span></span>

- <span data-ttu-id="b77a5-132">Deze instelling is van invloed op zowel gebruikers als beheerders.</span><span class="sxs-lookup"><span data-stu-id="b77a5-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="b77a5-133">Personen kunnen nog steeds schadelijke bestanden verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-133">People can still delete malicious files.</span></span>

<span data-ttu-id="b77a5-134">Zie [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b77a5-134">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="b77a5-135">Stap 3 (Aanbevolen) Gebruik het beveiligings- & compliancecentrum om een waarschuwingsbeleid te maken voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="b77a5-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="b77a5-136">U kunt een waarschuwingsbeleid maken waarin u en andere beheerders worden gewaarschuwd wanneer met veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams een schadelijk bestand wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="b77a5-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="b77a5-137">Zie Activiteitswaarschuwingen maken in het beveiligings- & [compliancecentrum voor meer informatie over waarschuwingen.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="b77a5-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="b77a5-138">Ga in [het & Compliancecentrum](https://protection.office.com)naar  \> **Waarschuwingenwaarschuwingsbeleid** of open <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="b77a5-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="b77a5-139">Klik op **de pagina Waarschuwingsbeleid** op **Nieuw waarschuwingsbeleid.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="b77a5-140">De **wizard Nieuw waarschuwingsbeleid** wordt in een uitvliegende versie geopend. Configureer **op de pagina** Naam uw waarschuwing de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b77a5-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="b77a5-141">**Naam:** Typ een unieke en beschrijvende naam.</span><span class="sxs-lookup"><span data-stu-id="b77a5-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="b77a5-142">Bijvoorbeeld schadelijke bestanden in bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="b77a5-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="b77a5-143">**Beschrijving:** Typ een optionele beschrijving.</span><span class="sxs-lookup"><span data-stu-id="b77a5-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="b77a5-144">Zo worden beheerders op de in SharePoint Online, OneDrive of Microsoft Teams gedetecteerde schadelijke bestanden op de website van de beheerder op de lijst geplaatst.</span><span class="sxs-lookup"><span data-stu-id="b77a5-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="b77a5-145">**Ernst:** Laat de standaardwaarde **Laag** geselecteerd of selecteer **Gemiddeld** of **Hoog.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="b77a5-146">**Selecteer een categorie:** Selecteer **Bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="b77a5-147">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b77a5-148">Configureer **op de pagina Waarschuwingsinstellingen** maken de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b77a5-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="b77a5-149">**Waar wilt u op waarschuwen?: Activiteit is:** Selecteer **Gedetecteerde malware in bestand.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="b77a5-150">**Hoe wilt u dat de waarschuwing wordt geactiveerd?**: De standaardwaarde verlaten Telkens wanneer een **activiteit overeenkomt met de geselecteerde** regel.</span><span class="sxs-lookup"><span data-stu-id="b77a5-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="b77a5-151">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b77a5-152">Configureer op de pagina Uw **geadresseerden** instellen de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b77a5-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="b77a5-153">**E-mailmeldingen verzenden:** controleer of deze instelling is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="b77a5-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="b77a5-154">Selecteer in het vak E-mailontvangers een of meer globale beheerders, beveiligingsbeheerders of **beveiligingslezers** die een melding moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="b77a5-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="b77a5-155">**Dagelijkse meldingslimiet:** Laat de standaardwaarde **Geen limiet** geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="b77a5-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="b77a5-156">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b77a5-157">Controleer op **de pagina** Uw instellingen controleren de instellingen en klik op **Bewerken** in een van de secties om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="b77a5-158">Laat in **de sectie Wilt** u het beleid meteen in- of uit? de standaardwaarde **Ja,** schakel het direct ingeschakeld in.</span><span class="sxs-lookup"><span data-stu-id="b77a5-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="b77a5-159">Wanneer u klaar bent, klikt u op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="b77a5-160">Beveiligingsbeleid & Compliance PowerShell gebruiken om een waarschuwingsbeleid te maken voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="b77a5-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="b77a5-161">Als u Liever PowerShell gebruikt om hetzelfde waarschuwingsbeleid te maken als in de vorige sectie, maakt u verbinding met [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) en voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="b77a5-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="b77a5-162">**Opmerking:** De _standaardwaarde Ernst_ is laag.</span><span class="sxs-lookup"><span data-stu-id="b77a5-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="b77a5-163">Als u Gemiddeld of Hoog wilt opgeven, moet u de parameter _Ernst_ en de waarde in de opdracht opnemen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="b77a5-164">Zie [New-ActivityAlert](/powershell/module/exchange/new-activityalert)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b77a5-164">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b77a5-165">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="b77a5-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="b77a5-166">Als u wilt controleren of u veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams hebt ingeschakeld, gebruikt u een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="b77a5-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="b77a5-167">Ga in het [beveiligings- & compliancecentrum](https://protection.office.com)naar Atp Safe Attachments  voor bedreigingsbeleid , selecteer Globale instellingen en controleer de waarde van de instelling Defender in- en uitschakelen voor Office \>  \>  **365 voor SharePoint, OneDrive** en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b77a5-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="b77a5-168">Voer in Exchange Online PowerShell de volgende opdracht uit om de eigenschapsinstelling te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="b77a5-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="b77a5-169">Zie [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b77a5-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="b77a5-170">Als u wilt controleren of u personen hebt geblokkeerd om schadelijke bestanden te downloaden, opent u SharePoint Online PowerShell en voer u de volgende opdracht uit om de eigenschapswaarde te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="b77a5-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="b77a5-171">Zie [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b77a5-171">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="b77a5-172">Als u wilt controleren of u een waarschuwingsbeleid voor gedetecteerde bestanden hebt geconfigureerd, gebruikt u een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="b77a5-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="b77a5-173">Ga in & Beveiligingscentrum naar Waarschuwingenwaarschuwingsbeleid selecteer het waarschuwingsbeleid  \>  \> en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="b77a5-174">Vervang in & PowerShell van het beveiligingscentrum de naam van het waarschuwingsbeleid, voer de volgende opdracht uit en controleer \<AlertPolicyName\> de eigenschapswaarden:</span><span class="sxs-lookup"><span data-stu-id="b77a5-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="b77a5-175">Zie [Get-ActivityAlert](/powershell/module/exchange/get-activityalert)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b77a5-175">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="b77a5-176">Gebruik het [rapport Bedreigingsbeveiliging om](view-email-security-reports.md#threat-protection-status-report) informatie weer te geven over gedetecteerde bestanden in SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b77a5-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="b77a5-177">U kunt in het bijzonder de **weergave gegevens gebruiken op: de weergave \> Inhouds malware.**</span><span class="sxs-lookup"><span data-stu-id="b77a5-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>