---
title: Office 365 ATP inschakelen - SharePoint, OneDrive & Teams
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
description: Meer informatie over het inschakelen van ATP voor SharePoint, OneDrive en Teams, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 976911abe047be350ae6c64409cd6607ea75de7a
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811072"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="8de4c-103">ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen</span><span class="sxs-lookup"><span data-stu-id="8de4c-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8de4c-104">Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="8de4c-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="8de4c-105">Zie [Geavanceerde Outlook.com beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="8de4c-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="8de4c-106">[Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) beschermt uw organisatie tegen het per ongeluk delen van schadelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="8de4c-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="8de4c-107">Wanneer een kwaadaardig bestand wordt gedetecteerd, wordt dat bestand geblokkeerd, zodat niemand het kan openen, kopiëren, verplaatsen of delen totdat verdere acties worden ondernomen door het beveiligingsteam van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8de4c-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="8de4c-108">Lees dit artikel om ATP voor SharePoint, OneDrive en Teams in te schakelen, waarschuwingen in te stellen om een melding te krijgen over gedetecteerde bestanden en uw volgende stappen te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="8de4c-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="8de4c-109">Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen.</span><span class="sxs-lookup"><span data-stu-id="8de4c-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="8de4c-110">Enkele voorbeelden worden beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="8de4c-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="8de4c-111">Rol</span><span class="sxs-lookup"><span data-stu-id="8de4c-111">Role</span></span>|<span data-ttu-id="8de4c-112">Waar/hoe toegewezen</span><span class="sxs-lookup"><span data-stu-id="8de4c-112">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="8de4c-113">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="8de4c-113">global administrator</span></span>|<span data-ttu-id="8de4c-114">De persoon die zich aanmeldt om Microsoft 365 te kopen, is standaard een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="8de4c-114">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="8de4c-115">(Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)</span><span class="sxs-lookup"><span data-stu-id="8de4c-115">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="8de4c-116">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="8de4c-116">Security Administrator</span></span>|<span data-ttu-id="8de4c-117">Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="8de4c-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="8de4c-118">Exchange Online Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="8de4c-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="8de4c-119">Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="8de4c-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="8de4c-120">of</span><span class="sxs-lookup"><span data-stu-id="8de4c-120">or</span></span> <br>  <span data-ttu-id="8de4c-121">PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="8de4c-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="8de4c-122">ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen</span><span class="sxs-lookup"><span data-stu-id="8de4c-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="8de4c-123">**Voordat u met deze procedure begint, moet u ervoor zorgen dat controlelogboekregistratie al is ingeschakeld voor uw Microsoft 365-omgeving.**</span><span class="sxs-lookup"><span data-stu-id="8de4c-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="8de4c-124">Dit wordt meestal gedaan door iemand die de rol Controlelogboeken heeft toegewezen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8de4c-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="8de4c-125">Zie Zoeken in of uit controleren op [controlelogboeken in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8de4c-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="8de4c-126">Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="8de4c-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>

2. <span data-ttu-id="8de4c-127">Kies in het Security & Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**de optie **Veilige bijlagen voor beleid** \> **Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="8de4c-127">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![Kies in het Security & Compliance Center het beleid voor bedreigingsbeheer \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="8de4c-129">Selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="8de4c-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Geavanceerde bedreigingsbeveiliging inschakelen voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="8de4c-131">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8de4c-131">Click **Save**.</span></span>

5. <span data-ttu-id="8de4c-132">Controleer (en, in voorkomend geval, bewerken) het beleid voor veilige bijlagen en het beleid voor veilige [koppelingen](set-up-atp-safe-attachments-policies.md) [van](set-up-atp-safe-links-policies.md)uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8de4c-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="8de4c-133">(Aanbevolen) Voer als globale beheerder of SharePoint Online-beheerder de cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit met de parameter _DisallowInfectedFileDownload_ ingesteld op *true*.</span><span class="sxs-lookup"><span data-stu-id="8de4c-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="8de4c-134">Als u de parameter instelt op *true,* worden alle acties (behalve Verwijderen) voor gedetecteerde bestanden geblokt.</span><span class="sxs-lookup"><span data-stu-id="8de4c-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="8de4c-135">Mensen kunnen gedetecteerde bestanden niet openen, verplaatsen, kopiëren of delen.</span><span class="sxs-lookup"><span data-stu-id="8de4c-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="8de4c-136">Als u de parameter instelt op *false,* worden alle acties behalve Verwijderen en downloaden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8de4c-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="8de4c-137">Mensen kunnen ervoor kiezen om het risico te accepteren en een gedetecteerd bestand te downloaden.</span><span class="sxs-lookup"><span data-stu-id="8de4c-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="8de4c-138">Sta maximaal 30 minuten toe dat uw wijzigingen worden doorgevoerd naar alle Microsoft 365-datacenters.</span><span class="sxs-lookup"><span data-stu-id="8de4c-138">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

8. <span data-ttu-id="8de4c-139">(Aanbevolen) Ga over tot het instellen van waarschuwingen voor gedetecteerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="8de4c-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="8de4c-140">Zie [Microsoft 365 beheren met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)voor meer informatie over het gebruik van PowerShell met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8de4c-140">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="8de4c-141">Zie [Wat u moet doen wanneer een kwaadaardig bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)voor meer informatie over de gebruikerservaring wanneer een bestand als kwaadaardig is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="8de4c-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="8de4c-142">Waarschuwingen instellen voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="8de4c-142">Set up alerts for detected files</span></span>

<span data-ttu-id="8de4c-143">Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams als kwaadaardig is aangemerkt, u een waarschuwing instellen.</span><span class="sxs-lookup"><span data-stu-id="8de4c-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="8de4c-144">Kies in het [Security & Compliance Center](https://protection.office.com)de optie Waarschuwingen beheren van **Alerts** \> **waarschuwingen**.</span><span class="sxs-lookup"><span data-stu-id="8de4c-144">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="8de4c-145">Kies **Nieuw waarschuwingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="8de4c-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="8de4c-146">Geef een naam op voor de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="8de4c-146">Specify a name for the alert.</span></span> <span data-ttu-id="8de4c-147">U bijvoorbeeld schadelijke bestanden typen in bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="8de4c-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="8de4c-148">Typ een beschrijving voor de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="8de4c-148">Type a description for the alert.</span></span> <span data-ttu-id="8de4c-149">U bijvoorbeeld typen Beheerders op de hoogte stellen wanneer schadelijke bestanden worden gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8de4c-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="8de4c-150">Ga als volgt te werk in de sectie **Deze waarschuwing verzenden wanneer...** het volgende:</span><span class="sxs-lookup"><span data-stu-id="8de4c-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="8de4c-151">a.</span><span class="sxs-lookup"><span data-stu-id="8de4c-151">a.</span></span> <span data-ttu-id="8de4c-152">Kies **gedetecteerde malware in het bestand in**de lijst **Activiteiten.**</span><span class="sxs-lookup"><span data-stu-id="8de4c-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="8de4c-153">b.</span><span class="sxs-lookup"><span data-stu-id="8de4c-153">b.</span></span> <span data-ttu-id="8de4c-154">Laat het veld **Gebruikers** leeg.</span><span class="sxs-lookup"><span data-stu-id="8de4c-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="8de4c-155">Selecteer in de sectie **Deze waarschuwing verzenden naar...** een of meer globale beheerders, beveiligingsbeheerders of beveiligingslezers die een melding moeten ontvangen wanneer een kwaadaardig bestand wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="8de4c-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="8de4c-156">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8de4c-156">Click **Save**.</span></span>

<span data-ttu-id="8de4c-157">Zie [Activiteitswaarschuwingen maken in het Security & Compliance Center](../../compliance/create-activity-alerts.md)voor meer informatie over waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="8de4c-157">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8de4c-158">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="8de4c-158">Next steps</span></span>

1. [<span data-ttu-id="8de4c-159">Informatie weergeven over schadelijke bestanden die zijn gedetecteerd in SharePoint, OneDrive of Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8de4c-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="8de4c-160">Berichten en bestanden in quarantaine beheren als beheerder in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8de4c-160">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
