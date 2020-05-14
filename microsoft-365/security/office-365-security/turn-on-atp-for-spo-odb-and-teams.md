---
title: Office 365 ATP inschakelen - SharePoint, OneDrive, & Teams
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
ms.openlocfilehash: b4dfe56b635714cedf033f2d4f14cd6bc0286650
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224609"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bad4d-103">ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen</span><span class="sxs-lookup"><span data-stu-id="bad4d-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bad4d-104">Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="bad4d-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="bad4d-105">Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="bad4d-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="bad4d-106">[Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) beschermt uw organisatie tegen het per ongeluk delen van schadelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="bad4d-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="bad4d-107">Wanneer een kwaadaardig bestand wordt gedetecteerd, wordt dat bestand geblokkeerd, zodat niemand het kan openen, kopiëren, verplaatsen of delen totdat verdere acties zijn uitgevoerd door het beveiligingsteam van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="bad4d-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="bad4d-108">Lees dit artikel om ATP in te schakelen voor SharePoint, OneDrive en Teams, stel waarschuwingen in om op de hoogte te worden gesteld van gedetecteerde bestanden en vervolgstappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="bad4d-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="bad4d-109">Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen.</span><span class="sxs-lookup"><span data-stu-id="bad4d-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="bad4d-110">Enkele voorbeelden worden beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="bad4d-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="bad4d-111">Rol</span><span class="sxs-lookup"><span data-stu-id="bad4d-111">Role</span></span>|<span data-ttu-id="bad4d-112">Waar/hoe toegewezen</span><span class="sxs-lookup"><span data-stu-id="bad4d-112">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="bad4d-113">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="bad4d-113">global administrator</span></span>|<span data-ttu-id="bad4d-114">De persoon die zich aanmeldt om Microsoft 365 te kopen is standaard een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="bad4d-114">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="bad4d-115">(Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)</span><span class="sxs-lookup"><span data-stu-id="bad4d-115">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="bad4d-116">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="bad4d-116">Security Administrator</span></span>|<span data-ttu-id="bad4d-117">Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="bad4d-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="bad4d-118">Exchange Online Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="bad4d-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="bad4d-119">Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="bad4d-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="bad4d-120">of</span><span class="sxs-lookup"><span data-stu-id="bad4d-120">or</span></span> <br>  <span data-ttu-id="bad4d-121">PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="bad4d-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span>|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bad4d-122">ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen</span><span class="sxs-lookup"><span data-stu-id="bad4d-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="bad4d-123">**Controleer voordat u met deze procedure begint of de controlelogboekregistratie al is ingeschakeld voor uw Microsoft 365-omgeving.**</span><span class="sxs-lookup"><span data-stu-id="bad4d-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="bad4d-124">Dit wordt meestal gedaan door iemand die de rol Controlelogboeken heeft toegewezen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bad4d-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="bad4d-125">Zie [Zoeken in het controlelogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bad4d-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="bad4d-126">Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="bad4d-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>

2. <span data-ttu-id="bad4d-127">Kies in het Beveiligings- & Compliance Center in het **Policy** linkernavigatiedeelvenster onder **Bedreigingsbeheer**de optie Veilige bijlagen beleid \> **Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="bad4d-127">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![Kies in het Security & Compliance Center het beleid voor \> bedreigingsbeheer](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="bad4d-129">Selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="bad4d-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Geavanceerde bedreigingsbeveiliging inschakelen voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="bad4d-131">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bad4d-131">Click **Save**.</span></span>

5. <span data-ttu-id="bad4d-132">Bekijk (en bewerk, indien van toepassing, het [beleid voor veilige bijlagen van](set-up-atp-safe-attachments-policies.md) uw organisatie en het beleid voor veilige [koppelingen](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bad4d-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="bad4d-133">(Aanbevolen) Voer als globale beheerder of SharePoint Online-beheerder de cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit met de parameter _DisallowInfectedFileDownload_ ingesteld op *true.*</span><span class="sxs-lookup"><span data-stu-id="bad4d-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="bad4d-134">Als u de parameter instelt op *true* blokkeert alle acties (behalve Delete) voor gedetecteerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="bad4d-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="bad4d-135">Mensen kunnen gedetecteerde bestanden niet openen, verplaatsen, kopiëren of delen.</span><span class="sxs-lookup"><span data-stu-id="bad4d-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="bad4d-136">Als u de parameter instelt op *valse* blokken, behalve Verwijderen en downloaden.</span><span class="sxs-lookup"><span data-stu-id="bad4d-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="bad4d-137">Mensen kunnen ervoor kiezen om het risico te accepteren en een gedetecteerd bestand te downloaden.</span><span class="sxs-lookup"><span data-stu-id="bad4d-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="bad4d-138">Geef u tot 30 minuten de tijd om uw wijzigingen te verspreiden naar alle Microsoft 365-datacenters.</span><span class="sxs-lookup"><span data-stu-id="bad4d-138">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

8. <span data-ttu-id="bad4d-139">(Aanbevolen) Ga over tot het instellen van waarschuwingen voor gedetecteerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="bad4d-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="bad4d-140">Zie [Microsoft 365 beheren met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)voor meer informatie over het gebruik van PowerShell met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad4d-140">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="bad4d-141">Zie Wat moet u doen wanneer een kwaadaardig bestand [wordt gevonden in SharePoint Online, OneDrive of Microsoft Teams](https://support.microsoft.com/en-us/office/what-to-do-when-a-malicious-file-is-found-in-sharepoint-online-onedrive-or-microsoft-teams-01e902ad-a903-4e0f-b093-1e1ac0c37ad2)voor meer informatie over de gebruikerservaring wanneer een bestand als kwaadaardig wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="bad4d-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/en-us/office/what-to-do-when-a-malicious-file-is-found-in-sharepoint-online-onedrive-or-microsoft-teams-01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="bad4d-142">Waarschuwingen instellen voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="bad4d-142">Set up alerts for detected files</span></span>

<span data-ttu-id="bad4d-143">Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams als kwaadaardig is geïdentificeerd, u een waarschuwing instellen.</span><span class="sxs-lookup"><span data-stu-id="bad4d-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="bad4d-144">Kies **Waarschuwingen** beheren in het [Security & Compliance Center](https://protection.office.com) \> **Manage alerts**.</span><span class="sxs-lookup"><span data-stu-id="bad4d-144">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="bad4d-145">Kies **Nieuw waarschuwingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="bad4d-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="bad4d-146">Geef een naam op voor de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="bad4d-146">Specify a name for the alert.</span></span> <span data-ttu-id="bad4d-147">U bijvoorbeeld schadelijke bestanden typen in bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="bad4d-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="bad4d-148">Typ een beschrijving voor de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="bad4d-148">Type a description for the alert.</span></span> <span data-ttu-id="bad4d-149">U bijvoorbeeld Beheerders op de hoogte brengen wanneer schadelijke bestanden worden gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bad4d-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="bad4d-150">Ga in de sectie **Deze waarschuwing verzenden wanneer...** het volgende doet:</span><span class="sxs-lookup"><span data-stu-id="bad4d-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="bad4d-151">a.</span><span class="sxs-lookup"><span data-stu-id="bad4d-151">a.</span></span> <span data-ttu-id="bad4d-152">Kies **gedetecteerde malware in bestand in**de lijst **Activiteiten.**</span><span class="sxs-lookup"><span data-stu-id="bad4d-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="bad4d-153">b.</span><span class="sxs-lookup"><span data-stu-id="bad4d-153">b.</span></span> <span data-ttu-id="bad4d-154">Laat het veld **Gebruikers** leeg.</span><span class="sxs-lookup"><span data-stu-id="bad4d-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="bad4d-155">Selecteer in de sectie **Deze waarschuwing verzenden naar...** een of meer globale beheerders, beveiligingsbeheerders of beveiligingslezers die een melding moeten ontvangen wanneer een kwaadaardig bestand wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="bad4d-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="bad4d-156">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bad4d-156">Click **Save**.</span></span>

<span data-ttu-id="bad4d-157">Zie [Activiteitswaarschuwingen maken in het Security & Compliance Center](../../compliance/create-activity-alerts.md)voor meer informatie over waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="bad4d-157">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bad4d-158">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="bad4d-158">Next steps</span></span>

1. [<span data-ttu-id="bad4d-159">Informatie weergeven over schadelijke bestanden die zijn gedetecteerd in SharePoint, OneDrive of Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bad4d-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="bad4d-160">In quarantaine geplaatste berichten en bestanden beheren als beheerder in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bad4d-160">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
