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
ms.openlocfilehash: 6109cecc79b4db876ee595d4786d176ae7f42f5d
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656549"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0a528-103">ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen</span><span class="sxs-lookup"><span data-stu-id="0a528-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a528-104">Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="0a528-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="0a528-105">Als u een thuisgebruiker bent die op zoek bent naar informatie over veilige koppelingen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="0a528-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="0a528-106">[Office 365 ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md) beschermt uw organisatie per ongeluk om kwaadaardige bestanden te delen.</span><span class="sxs-lookup"><span data-stu-id="0a528-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="0a528-107">Wanneer een schadelijk bestand wordt gevonden, wordt het bestand geblokkeerd, zodat niemand dit kan openen, kopiëren, verplaatsen of delen totdat verdere acties worden uitgevoerd door het beveiligingsteam van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="0a528-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="0a528-108">Lees dit artikel om ATP voor SharePoint, OneDrive en teams in te schakelen, waarschuwingsmeldingen in te stellen voor gedetecteerde bestanden en de volgende stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0a528-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="0a528-109">Als u ATP-beleidsregels wilt definiëren (of bewerken), moet aan u de juiste rol zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0a528-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="0a528-110">In de volgende tabel worden enkele voorbeelden beschreven:</span><span class="sxs-lookup"><span data-stu-id="0a528-110">Some examples are described in the following table:</span></span>

****

|<span data-ttu-id="0a528-111">Rol</span><span class="sxs-lookup"><span data-stu-id="0a528-111">Role</span></span>|<span data-ttu-id="0a528-112">Where/hoe toegewezen</span><span class="sxs-lookup"><span data-stu-id="0a528-112">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="0a528-113">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="0a528-113">global administrator</span></span>|<span data-ttu-id="0a528-114">De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="0a528-114">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="0a528-115">(Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)</span><span class="sxs-lookup"><span data-stu-id="0a528-115">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="0a528-116">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="0a528-116">Security Administrator</span></span>|<span data-ttu-id="0a528-117">Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="0a528-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="0a528-118">Beheer van organisatie van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0a528-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="0a528-119">Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="0a528-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="0a528-120">of</span><span class="sxs-lookup"><span data-stu-id="0a528-120">or</span></span> <br>  <span data-ttu-id="0a528-121">PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="0a528-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0a528-122">ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen</span><span class="sxs-lookup"><span data-stu-id="0a528-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="0a528-123">**Voordat u met deze procedure begint, controleert u of logboekregistratie al is ingeschakeld voor uw Microsoft 365-omgeving**.</span><span class="sxs-lookup"><span data-stu-id="0a528-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="0a528-124">Dit gebeurt meestal door iemand die de rol audit logboeken heeft toegewezen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0a528-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="0a528-125">Zie [auditlogboek zoeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0a528-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="0a528-126">Ga naar <https://protection.office.com> en meld u aan met uw werk-of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="0a528-126">Go to <https://protection.office.com>, and sign in with your work or school account.</span></span>

2. <span data-ttu-id="0a528-127">Kies in het gedeelte beveiligings & compliance in het linker navigatiedeelvenster onder **Threat Management**de optie **beleids** \> **veilige bijlagen**.</span><span class="sxs-lookup"><span data-stu-id="0a528-127">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![Kies in het beveiligings & nalevings centrum de optie beleid voor Threat Management \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="0a528-129">Selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="0a528-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Geavanceerde Bedreigingsbeveiliging inschakelen voor SharePoint Online, OneDrive voor bedrijven en Microsoft teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="0a528-131">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0a528-131">Click **Save**.</span></span>

5. <span data-ttu-id="0a528-132">Bekijk (en, indien nodig, bewerken) het beleid voor [veilige bijlagen](set-up-atp-safe-attachments-policies.md) van uw organisatie en het [beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0a528-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="0a528-133">Beter Als globale beheerder of een SharePoint Online-beheerder voert u de cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit waarbij de _DisallowInfectedFileDownload_ -parameter is ingesteld op *waar*.</span><span class="sxs-lookup"><span data-stu-id="0a528-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="0a528-134">Als u de parameter instelt op *True* , worden alle acties (met uitzondering van verwijderen) voor gedetecteerde bestanden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="0a528-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="0a528-135">Personen kunnen geen gevonden bestanden openen, verplaatsen, kopiëren of delen.</span><span class="sxs-lookup"><span data-stu-id="0a528-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="0a528-136">Als u de parameter instelt op *False* , worden alle acties geblokkeerd, behalve verwijderen en downloaden.</span><span class="sxs-lookup"><span data-stu-id="0a528-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="0a528-137">Gebruikers kunnen ervoor kiezen het risico te accepteren en een gevonden bestand te downloaden.</span><span class="sxs-lookup"><span data-stu-id="0a528-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="0a528-138">Maximaal 30 minuten wachten tot de wijzigingen zijn doorgevoerd naar alle Microsoft 365-datacenters.</span><span class="sxs-lookup"><span data-stu-id="0a528-138">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

8. <span data-ttu-id="0a528-139">Beter Ga verder met het instellen van waarschuwingen voor gedetecteerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="0a528-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="0a528-140">Zie [Microsoft 365 beheren met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)voor meer informatie over het gebruik van PowerShell met microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a528-140">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="0a528-141">Zie [wat u moet doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)voor meer informatie over de gebruikerservaring wanneer een bestand als schadelijk is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="0a528-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="0a528-142">Waarschuwingen instellen voor gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="0a528-142">Set up alerts for detected files</span></span>

<span data-ttu-id="0a528-143">Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online, OneDrive voor bedrijven of Microsoft teams is herkend als schadelijk, kunt u een melding instellen.</span><span class="sxs-lookup"><span data-stu-id="0a528-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="0a528-144">Kies in het [beveiligings & nalevings centrum](https://protection.office.com) **waarschuwingen** \> **beheren**.</span><span class="sxs-lookup"><span data-stu-id="0a528-144">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="0a528-145">Kies **Nieuw waarschuwings beleid**.</span><span class="sxs-lookup"><span data-stu-id="0a528-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="0a528-146">Geef een naam op voor de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="0a528-146">Specify a name for the alert.</span></span> <span data-ttu-id="0a528-147">U kunt bijvoorbeeld schadelijke bestanden in bibliotheken typen.</span><span class="sxs-lookup"><span data-stu-id="0a528-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="0a528-148">Typ een beschrijving voor de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="0a528-148">Type a description for the alert.</span></span> <span data-ttu-id="0a528-149">U kunt bijvoorbeeld een melding van de beheerder doen wanneer er kwaadaardige bestanden zijn gevonden in SharePoint Online, OneDrive of Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0a528-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="0a528-150">Voer de volgende handelingen uit in de sectie **deze melding verzenden wanneer...** :</span><span class="sxs-lookup"><span data-stu-id="0a528-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="0a528-151">a.</span><span class="sxs-lookup"><span data-stu-id="0a528-151">a.</span></span> <span data-ttu-id="0a528-152">Kies in de lijst **activiteiten** de optie **malware gevonden in bestand**.</span><span class="sxs-lookup"><span data-stu-id="0a528-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="0a528-153">b.</span><span class="sxs-lookup"><span data-stu-id="0a528-153">b.</span></span> <span data-ttu-id="0a528-154">Laat het veld **gebruikers** leeg.</span><span class="sxs-lookup"><span data-stu-id="0a528-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="0a528-155">Selecteer in de sectie **Deze waarschuwing verzenden naar...** een of meer globale beheerders, beveiligingsbeheerders of beveiligings lezers die een bericht moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="0a528-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="0a528-156">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0a528-156">Click **Save**.</span></span>

<span data-ttu-id="0a528-157">Zie voor meer informatie over waarschuwingen [activiteiten meldingen maken in het beveiligings & nalevings centrum](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="0a528-157">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a528-158">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="0a528-158">Next steps</span></span>

1. [<span data-ttu-id="0a528-159">Informatie over schadelijke bestanden weergeven die zijn gevonden in SharePoint, OneDrive of Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="0a528-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="0a528-160">In quarantaine geplaatste berichten en bestanden als beheerder beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a528-160">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
