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
description: Beheerders kunnen onder meer lezen hoe ze veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in kunnen stellen, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286367"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ec101-103">Veilige bijlagen uitschakelen voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec101-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ec101-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ec101-104">**Applies to**</span></span>
- [<span data-ttu-id="ec101-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ec101-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ec101-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec101-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ec101-107">Met Microsoft Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams wordt uw organisatie beschermd tegen het onbedoeld delen van schadelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="ec101-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="ec101-108">Zie Veilige bijlagen voor [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md)en Microsoft Teams voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ec101-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="ec101-109">Dit artikel bevat de stappen voor het inschakelen en configureren van veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec101-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ec101-110">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ec101-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ec101-111">U opent het beveiligings- en compliancecentrum in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="ec101-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="ec101-112">Als u rechtstreeks naar de pagina Veilige **bijlagen met ATP wilt** gaan, opent u <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="ec101-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="ec101-113">Als u veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams wilt  in te  schakeln, moet u lid zijn van de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="ec101-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="ec101-114">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ec101-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="ec101-115">Als u SharePoint Online PowerShell wilt gebruiken om te voorkomen dat [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) personen schadelijke bestanden downloaden, moet u lid zijn van de rollen van de globale beheerder of [van SharePoint-beheerders](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ec101-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="ec101-116">Controleer of auditlogregistratie is ingeschakeld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ec101-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="ec101-117">Zie Zoeken in [auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="ec101-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="ec101-118">Het duurt maximaal 30 minuten voordat de instellingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="ec101-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ec101-119">Stap 1: Het beveiligings- & gebruiken om veilige bijlagen in te schakel voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec101-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="ec101-120">Ga in het & compliancecentrum naar  Veilige bijlagen van ATP voor risicobeheer en klik \>  \> op **Globale instellingen.**</span><span class="sxs-lookup"><span data-stu-id="ec101-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="ec101-121">In de **globale instellingen** die worden weergegeven, gaat u naar de instelling Defender voor **Office 365 voor SharePoint, OneDrive** en Microsoft Teams in bedrijf nemen.</span><span class="sxs-lookup"><span data-stu-id="ec101-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="ec101-122">Zet de schakelaar naar rechts om Veilige bijlagen in te schakelen voor ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec101-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="ec101-123">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ec101-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ec101-124">Exchange Online PowerShell gebruiken om veilige bijlagen in te zetten voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec101-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ec101-125">Als u liever PowerShell gebruikt om veilige bijlagen in te voeren voor SharePoint, OneDrive en Microsoft Teams, maakt u verbinding met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) en voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="ec101-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="ec101-126">Zie [Set-AtpPolicyForO365 voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ec101-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="ec101-127">Stap 2: (Aanbevolen) Gebruik SharePoint Online PowerShell om te voorkomen dat gebruikers schadelijke bestanden downloaden</span><span class="sxs-lookup"><span data-stu-id="ec101-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="ec101-128">Standaard kunnen gebruikers geen schadelijke bestanden openen, verplaatsen, kopiëren of delen die door ATP worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="ec101-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="ec101-129">Ze kunnen echter wel schadelijke bestanden verwijderen en downloaden.</span><span class="sxs-lookup"><span data-stu-id="ec101-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="ec101-130">Als u wilt voorkomen dat gebruikers schadelijke bestanden downloaden, maakt u [verbinding met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="ec101-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="ec101-131">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ec101-131">**Notes**:</span></span>

- <span data-ttu-id="ec101-132">Deze instelling is van invloed op zowel gebruikers als beheerders.</span><span class="sxs-lookup"><span data-stu-id="ec101-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="ec101-133">Schadelijke bestanden kunnen nog steeds worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ec101-133">People can still delete malicious files.</span></span>

<span data-ttu-id="ec101-134">Zie [Set-SPOTenant voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="ec101-134">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="ec101-135">Stap 3 (aanbevolen) Gebruik het beveiligings- & voor het maken van een waarschuwingsbeleid voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="ec101-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="ec101-136">U kunt een waarschuwingsbeleid maken dat u en andere beheerders waarschuwt wanneer met veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams een schadelijk bestand wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="ec101-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="ec101-137">Zie Activiteitswaarschuwingen maken in het beveiligings- & compliancecentrum voor meer [informatie over waarschuwingen.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="ec101-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="ec101-138">Ga in [het & Compliancecentrum](https://protection.office.com)naar **Waarschuwingsbeleid** \> **voor** waarschuwingen of <https://protection.office.com/alertpolicies> open.</span><span class="sxs-lookup"><span data-stu-id="ec101-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="ec101-139">Klik op **de pagina Waarschuwingsbeleid** op **Nieuw waarschuwingsbeleid.**</span><span class="sxs-lookup"><span data-stu-id="ec101-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="ec101-140">De **wizard Nieuw waarschuwingsbeleid** wordt in een fly out geopend. Configureer **de volgende instellingen op de** pagina Uw waarschuwing een naam geven:</span><span class="sxs-lookup"><span data-stu-id="ec101-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="ec101-141">**Naam:** typ een unieke en beschrijvende naam.</span><span class="sxs-lookup"><span data-stu-id="ec101-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="ec101-142">Bijvoorbeeld schadelijke bestanden in bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="ec101-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="ec101-143">**Beschrijving:** typ een optionele beschrijving.</span><span class="sxs-lookup"><span data-stu-id="ec101-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="ec101-144">Beheerders krijgen bijvoorbeeld een e-mail wanneer er schadelijke bestanden worden aangetroffen in SharePoint Online, OneDrive of Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec101-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="ec101-145">**Ernst:** laat de standaardwaarde **Laag** geselecteerd of selecteer **Normaal** of **Hoog.**</span><span class="sxs-lookup"><span data-stu-id="ec101-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="ec101-146">**Selecteer een categorie:** **Risicobeheer selecteren.**</span><span class="sxs-lookup"><span data-stu-id="ec101-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="ec101-147">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="ec101-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ec101-148">Configureer **de volgende instellingen op** de pagina Waarschuwingsinstellingen maken:</span><span class="sxs-lookup"><span data-stu-id="ec101-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="ec101-149">**Waarvoor wilt u een waarschuwing ontvangen?: Activiteit is:** Selecteer **Gedetecteerde malware in bestand.**</span><span class="sxs-lookup"><span data-stu-id="ec101-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="ec101-150">**Hoe wilt u dat de waarschuwing wordt geactiveerd?**: Laat de standaardwaarde staan telkens wanneer een **activiteit overeenkomt met de geselecteerde** regel.</span><span class="sxs-lookup"><span data-stu-id="ec101-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="ec101-151">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="ec101-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ec101-152">Configureer **de volgende instellingen op de** pagina Geadresseerden instellen:</span><span class="sxs-lookup"><span data-stu-id="ec101-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="ec101-153">**E-mailmeldingen verzenden:** controleer of deze instelling is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="ec101-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="ec101-154">Selecteer in het vak E-mailontvangers een of meer globale beheerders, beveiligingsbeheerders of **beveiligingslezers** die een melding moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="ec101-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="ec101-155">**Dagelijkse meldingslimiet:** laat de standaardwaarde **Geen limiet** geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="ec101-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="ec101-156">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="ec101-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ec101-157">Controleer **de instellingen op de pagina** Uw instellingen en klik in een van de secties op Bewerken om wijzigingen aan te brengen. </span><span class="sxs-lookup"><span data-stu-id="ec101-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="ec101-158">In de sectie Wilt u het beleid meteen in ingeschakeld **laten?** Laat de standaardwaarde **Ja, schakel** deze meteen in.</span><span class="sxs-lookup"><span data-stu-id="ec101-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="ec101-159">Klik op Voltooien wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="ec101-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="ec101-160">Beveiligings- & PowerShell gebruiken om een waarschuwingsbeleid te maken voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="ec101-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="ec101-161">Als u liever PowerShell gebruikt om hetzelfde waarschuwingsbeleid te maken als in de vorige sectie is beschreven, maakt u verbinding met [security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) en voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="ec101-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="ec101-162">**Opmerking:** de _standaardwaarde Ernst_ is laag.</span><span class="sxs-lookup"><span data-stu-id="ec101-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="ec101-163">Als u normaal of hoog wilt opgeven, moet u de parameter _Ernst_ en de waarde opnemen in de opdracht.</span><span class="sxs-lookup"><span data-stu-id="ec101-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="ec101-164">Zie [New-ActivityAlert voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="ec101-164">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ec101-165">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="ec101-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="ec101-166">Als u wilt controleren of veilige bijlagen zijn ingeschakeld voor SharePoint, OneDrive en Microsoft Teams, gebruikt u een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="ec101-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="ec101-167">Ga in het [& Compliancecentrum](https://protection.office.com)voor  beveiligingsinstellingen naar Veilige bijlagen van ATP-beleid voor bedreigingsbeheer, selecteer algemene instellingen en controleer de waarde van de instelling Defender voor \>  \>  **Office 365 voor SharePoint, OneDrive** en Microsoft Teams in te stellen.</span><span class="sxs-lookup"><span data-stu-id="ec101-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="ec101-168">Voer in Exchange Online PowerShell de volgende opdracht uit om de eigenschapsinstelling te controleren:</span><span class="sxs-lookup"><span data-stu-id="ec101-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="ec101-169">Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ec101-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="ec101-170">Als u wilt controleren of het downloaden van schadelijke bestanden door personen is geblokkeerd, opent u SharePoint Online PowerShell en voer u de volgende opdracht uit om de waarde van de eigenschap te controleren:</span><span class="sxs-lookup"><span data-stu-id="ec101-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="ec101-171">Zie [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ec101-171">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="ec101-172">Als u wilt controleren of u een waarschuwingsbeleid voor gedetecteerde bestanden hebt geconfigureerd, gebruikt u een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="ec101-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="ec101-173">Ga in het & Compliancecentrum naar  Het beleid voor waarschuwingenwaarschuwingen selecteer het waarschuwingsbeleid \>  \> en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="ec101-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="ec101-174">Vervang in & Compliancecentrum PowerShell de naam van het waarschuwingsbeleid, voer de volgende opdracht uit en controleer \<AlertPolicyName\> de eigenschapswaarden:</span><span class="sxs-lookup"><span data-stu-id="ec101-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="ec101-175">Zie [Get-ActivityAlert voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="ec101-175">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="ec101-176">Gebruik het [statusrapport Risicobeveiliging om](view-email-security-reports.md#threat-protection-status-report) informatie weer te geven over gedetecteerde bestanden in SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec101-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="ec101-177">U kunt de weergavegegevens gebruiken **op: de weergave \> Malware** van inhoud.</span><span class="sxs-lookup"><span data-stu-id="ec101-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
