---
title: Beveiligen tegen bedreigingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie lezen over bedreigingsbeveiliging in Microsoft 365 en configureren hoe u deze voor uw organisatie gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826823"
---
# <a name="protect-against-threats"></a><span data-ttu-id="38812-103">Beveiligen tegen bedreigingen</span><span class="sxs-lookup"><span data-stu-id="38812-103">Protect against threats</span></span>

<span data-ttu-id="38812-104">Microsoft 365 omvat diverse functies voor beveiliging tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="38812-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="38812-105">Aan de slag met een handleiding kunt u ervoor zorgen dat de functies voor beveiliging van bedreigingen voor uw organisatie zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="38812-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="38812-106">Als u nog niet bekend bent met de functies voor beveiliging van bedreigingen in Office 365, of als u niet zeker weet waar u moet beginnen, kunt u de volgende richtlijnen gebruiken als uitgangspunt.</span><span class="sxs-lookup"><span data-stu-id="38812-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38812-107">De **Aanbevolen instellingen worden voor elk type beleid opgenomen, maar er zijn veel opties beschikbaar en u kunt de instellingen aanpassen aan de behoeften van uw specifieke organisatie**.</span><span class="sxs-lookup"><span data-stu-id="38812-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="38812-108">Sta ongeveer 30 minuten toe aan uw beleidsregels of wijzigingen die u kunt gebruiken in uw datacenter.</span><span class="sxs-lookup"><span data-stu-id="38812-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="38812-109">Vereisten</span><span class="sxs-lookup"><span data-stu-id="38812-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="38812-110">Abonnementen</span><span class="sxs-lookup"><span data-stu-id="38812-110">Subscriptions</span></span>

<span data-ttu-id="38812-111">De functies voor bedreigingsbeveiliging zijn opgenomen in alle Microsoft 365-abonnementen. Sommige abonnementen bevatten echter meer geavanceerde functies.</span><span class="sxs-lookup"><span data-stu-id="38812-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="38812-112">De volgende tabel bevat een overzicht van de beveiligingsfuncties die in dit artikel zijn opgenomen, samen met de minimale abonnements vereisten.</span><span class="sxs-lookup"><span data-stu-id="38812-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span>

****

|<span data-ttu-id="38812-113">Type beveiliging</span><span class="sxs-lookup"><span data-stu-id="38812-113">Protection type</span></span>|<span data-ttu-id="38812-114">Vereisten voor het abonnement</span><span class="sxs-lookup"><span data-stu-id="38812-114">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="38812-115">Beveiliging tegen malware</span><span class="sxs-lookup"><span data-stu-id="38812-115">Anti-malware protection</span></span>|<span data-ttu-id="38812-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="38812-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="38812-117">Beveiliging van schadelijke Url's en bestanden in e-mail en Office-documenten</span><span class="sxs-lookup"><span data-stu-id="38812-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="38812-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="38812-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="38812-119">Bescherming tegen phishing</span><span class="sxs-lookup"><span data-stu-id="38812-119">Anti-phishing protection</span></span>|[<span data-ttu-id="38812-120">EOP</span><span class="sxs-lookup"><span data-stu-id="38812-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="38812-121">Geavanceerde anti malafide beveiliging</span><span class="sxs-lookup"><span data-stu-id="38812-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="38812-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="38812-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="38812-123">Beveiliging tegen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="38812-123">Anti-spam protection</span></span>|[<span data-ttu-id="38812-124">EOP</span><span class="sxs-lookup"><span data-stu-id="38812-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="38812-125">Automatisch wissen van 0 uur (voor e-mail)</span><span class="sxs-lookup"><span data-stu-id="38812-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="38812-126">EOP</span><span class="sxs-lookup"><span data-stu-id="38812-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="38812-127">Controlelogboekregistratie (dit wordt gebruikt voor rapportagedoeleinden)</span><span class="sxs-lookup"><span data-stu-id="38812-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="38812-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38812-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="38812-129">Rollen en machtigingen</span><span class="sxs-lookup"><span data-stu-id="38812-129">Roles and permissions</span></span>

<span data-ttu-id="38812-130">U moet beschikken over de juiste rol voor het configureren van beleid in de [beveiligings & nalevings centrum](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="38812-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="38812-131">De volgende tabel bevat enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="38812-131">The following table includes some examples:</span></span>

****

|<span data-ttu-id="38812-132">Rol of rollengroep</span><span class="sxs-lookup"><span data-stu-id="38812-132">Role or role group</span></span>|<span data-ttu-id="38812-133">Waar vind ik meer informatie?</span><span class="sxs-lookup"><span data-stu-id="38812-133">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="38812-134">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="38812-134">global administrator</span></span>|[<span data-ttu-id="38812-135">Over Microsoft 365-beheersrollen</span><span class="sxs-lookup"><span data-stu-id="38812-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="38812-136">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="38812-136">Security Administrator</span></span>|[<span data-ttu-id="38812-137">Machtigingen voor beheerdersrollen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="38812-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="38812-138">Beheer van organisatie van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38812-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="38812-139">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38812-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="38812-140">en</span><span class="sxs-lookup"><span data-stu-id="38812-140">and</span></span><br> [<span data-ttu-id="38812-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="38812-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="38812-142">Zie [machtigingen in het beveiligings &amp; centrum](permissions-in-the-security-and-compliance-center.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="38812-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="38812-143">Deel 1 – bescherming tegen malware</span><span class="sxs-lookup"><span data-stu-id="38812-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="38812-144">[Beveiliging tegen malware](anti-malware-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="38812-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="38812-145">Kies in het [beveiligings & compliance](https://protection.office.com)de optie **Threat management**  >  **Policy**  >  **anti-malware**van beleid voor bedreigings beheer.</span><span class="sxs-lookup"><span data-stu-id="38812-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="38812-146">Dubbelklik op het **standaard** beleid en kies vervolgens **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="38812-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="38812-147">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="38812-147">Specify the following settings:</span></span>

    - <span data-ttu-id="38812-148">In de sectie **Detectieantwoord van malware** moet u de standaardinstelling **Nee**opgeven.</span><span class="sxs-lookup"><span data-stu-id="38812-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="38812-149">Kies in de sectie **common Attachment types filter** de optie **on**.</span><span class="sxs-lookup"><span data-stu-id="38812-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="38812-150">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="38812-150">Click **Save**.</span></span>

<span data-ttu-id="38812-151">Zie [beleid voor malware van malware configureren](configure-anti-malware-policies.md)voor meer informatie over beleidsopties voor anti malware.</span><span class="sxs-lookup"><span data-stu-id="38812-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="38812-152">Deel 2-beveiliging van schadelijke Url's en bestanden</span><span class="sxs-lookup"><span data-stu-id="38812-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="38812-153">Beveiliging tegen tijd van schadelijke Url's en bestanden is beschikbaar in abonnementen die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) bevatten en wordt ingesteld via [ATP veilige bijlagen](atp-safe-attachments.md) en profielen voor [veilige koppelingen](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="38812-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="38812-154">Beleid voor veilige bijlagen met ATP</span><span class="sxs-lookup"><span data-stu-id="38812-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="38812-155">Voor het instellen van documenten met ATP voor de [vrije](atp-safe-attachments.md)tijd moet u minimaal één beleid voor veilige bijlagen met ATP definiëren.</span><span class="sxs-lookup"><span data-stu-id="38812-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="38812-156">Kies in het [beveiligings & compliance](https://protection.office.com)de optie voor het oplossen van **bedreigings beheer**  >  **beleid**voor  >  **veilige bijlagen**.</span><span class="sxs-lookup"><span data-stu-id="38812-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="38812-157">Selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="38812-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="38812-158">Klik in de sectie **e-mailbijlagen beveiligen** op het plusteken ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="38812-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="38812-159">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="38812-159">Specify the following settings:</span></span>

   - <span data-ttu-id="38812-160">Typ in het vak **naam** de tekst `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="38812-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="38812-161">Kies in de sectie antwoord de optie **blok**.</span><span class="sxs-lookup"><span data-stu-id="38812-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="38812-162">Selecteer in de sectie **bijlage omleiden** de optie **omleiden inschakelen**en geef vervolgens het e-mailadres op van de beveiligingsbeheerder of operator van uw organisatie die gedetecteerde bestanden moet controleren.</span><span class="sxs-lookup"><span data-stu-id="38812-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="38812-163">Kies in de sectie **toegepast op** **het domein van de ontvanger**.</span><span class="sxs-lookup"><span data-stu-id="38812-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="38812-164">Selecteer uw domein, kies **toevoegen**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="38812-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="38812-165">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="38812-165">Click **Save**.</span></span>

6. <span data-ttu-id="38812-166">(**Aanbevolen extra stap**) Als globale beheerder of een SharePoint Online-beheerder voert u de cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit waarbij de **DisallowInfectedFileDownload** -parameter is ingesteld op  *waar* voor uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="38812-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="38812-167">(Hiermee voorkomt u dat gebruikers bestanden openen, verplaatsen, kopiëren of delen die als schadelijk zijn gevonden.)</span><span class="sxs-lookup"><span data-stu-id="38812-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="38812-168">Zie voor meer informatie [office 365-beleid voor veilige bijlagen van office](set-up-atp-safe-attachments-policies.md) en [Schakel Office 365 ATP in voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="38812-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="38812-169">Beleid voor veilige koppelingen voor ATP</span><span class="sxs-lookup"><span data-stu-id="38812-169">ATP Safe Links policies</span></span>

<span data-ttu-id="38812-170">Voor het instellen van [veilige koppelingen voor ATP](atp-safe-links.md), controleert en bewerkt u uw standaardbeleid en voegt u een beleid toe voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="38812-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="38812-171">Kies in het [beveiligings & nalevings centrum](https://protection.office.com)de optie veilige koppelingen voor het beleid voor **bedreigings beheer**  >  **Policy**  >  **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="38812-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="38812-172">Dubbelklik op het **standaard** beleid.</span><span class="sxs-lookup"><span data-stu-id="38812-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="38812-173">Selecteer in de sectie **veilige koppelingen gebruiken in** de optie **Microsoft 365-apps voor Enterprise, Office voor IOS en Android**, en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="38812-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="38812-174">Klik in de sectie **beleidsregels die gelden voor specifieke geadresseerden** op het plusteken ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="38812-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="38812-175">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="38812-175">Specify the following settings:</span></span>

   - <span data-ttu-id="38812-176">Typ een naam in het vak **naam** , zoals `Safe Links` .</span><span class="sxs-lookup"><span data-stu-id="38812-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="38812-177">Kies in de sectie **Selecteer de actie** **aan**.</span><span class="sxs-lookup"><span data-stu-id="38812-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="38812-178">Selecteer de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="38812-178">Select these options:</span></span>

     - <span data-ttu-id="38812-179">**Veilige bijlagen gebruiken om downloadbare inhoud te scannen**</span><span class="sxs-lookup"><span data-stu-id="38812-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="38812-180">**Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**</span><span class="sxs-lookup"><span data-stu-id="38812-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="38812-181">**Gebruikers niet laten klikken via veilige koppelingen naar de oorspronkelijke URL**</span><span class="sxs-lookup"><span data-stu-id="38812-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="38812-182">Kies in de sectie **toegepast op** **het domein van de ontvanger**.</span><span class="sxs-lookup"><span data-stu-id="38812-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="38812-183">Selecteer uw domein, kies **toevoegen**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="38812-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="38812-184">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="38812-184">Click **Save**.</span></span>

<span data-ttu-id="38812-185">Zie [Beleid voor veilige koppelingen in ATP instellen in Office 365](set-up-atp-safe-links-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="38812-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="38812-186">Deel 3: bescherming tegen phishing</span><span class="sxs-lookup"><span data-stu-id="38812-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="38812-187">[Anti-phishing]</span><span class="sxs-lookup"><span data-stu-id="38812-187">[Anti-phishing]</span></span>

<span data-ttu-id="38812-188">[Bescherming tegen phishing](anti-phishing-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="38812-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="38812-189">Geavanceerde beveiliging tegen phishing is beschikbaar in de [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="38812-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="38812-190">In de volgende procedure wordt beschreven hoe u een ATP anti-phishingfilter kunt configureren.</span><span class="sxs-lookup"><span data-stu-id="38812-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="38812-191">De stappen zijn vergelijkbaar voor het configureren van een anti-phishingfilter-beleid (zonder ATP).</span><span class="sxs-lookup"><span data-stu-id="38812-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="38812-192">Kies in het [beveiligings & nalevings centrum](https://protection.office.com)de optie voor het instellen van het beleid voor het **beheer van bedreiging**  >  **Policy**  >  **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="38812-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="38812-193">Klik op **standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="38812-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="38812-194">Klik in het gedeelte **imitatie** op **bewerken**en geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="38812-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="38812-195">Schakel op het tabblad **gebruikers toevoegen om** beveiliging in.</span><span class="sxs-lookup"><span data-stu-id="38812-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="38812-196">Vervolgens voegt u gebruikers toe, zoals leden van de afdeling van uw organisatie, uw CEO, CFO en andere Senior leiders.</span><span class="sxs-lookup"><span data-stu-id="38812-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="38812-197">(U kunt een apart e-mailadres typen of klikken om een lijst weer te geven.)</span><span class="sxs-lookup"><span data-stu-id="38812-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="38812-198">Schakel op het tabblad **domein toevoegen om te beschermen** **de optie automatisch de domeinnamen toevoegen waarvan ik de eigenaar**is in.</span><span class="sxs-lookup"><span data-stu-id="38812-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="38812-199">Als u aangepaste domeinen hebt, kunt u deze ook toevoegen.</span><span class="sxs-lookup"><span data-stu-id="38812-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="38812-200">Selecteer op het tabblad **acties** **de optie quarantaine** voor de opties voor **geïmiteerde gebruiker** en **geïmiteerd domein** .</span><span class="sxs-lookup"><span data-stu-id="38812-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="38812-201">Daarnaast schakelt u de veiligheidstips van de persoon in.</span><span class="sxs-lookup"><span data-stu-id="38812-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="38812-202">Zorg dat op het tabblad **Postvak Intelligence** de optie Postvak Intelligence is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="38812-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="38812-203">Schakel daarnaast ook de bescherming van imitatie via postvak in.</span><span class="sxs-lookup"><span data-stu-id="38812-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="38812-204">Kies in het **e-mailbericht wordt verzonden door een geïmiteerde gebruikers** lijst **de optie Quarantine the Message**.</span><span class="sxs-lookup"><span data-stu-id="38812-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="38812-205">Geef op het tabblad **vertrouwde afzenders en domeinen toevoegen** de vertrouwde afzenders of domeinen op die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="38812-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="38812-206">Wanneer u de instellingen hebt gecontroleerd, klikt u op het tabblad **uw instellingen controleren** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="38812-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="38812-207">Klik in de sectie **spoof** op **bewerken**en geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="38812-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="38812-208">Zorg dat op het tabblad **instellingen voor spoofing filter** de optie anti-spoofing beveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="38812-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="38812-209">Kies op het tabblad **acties** **de optie Quarantine the Message**.</span><span class="sxs-lookup"><span data-stu-id="38812-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="38812-210">Wanneer u de instellingen hebt gecontroleerd, klikt u op het tabblad **uw instellingen controleren** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="38812-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="38812-211">(Als u geen wijzigingen hebt aangebracht, klikt u op **Annuleren**.)</span><span class="sxs-lookup"><span data-stu-id="38812-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="38812-212">Sluit de standaardpagina met beleidsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="38812-212">Close the default policy settings page.</span></span>

<span data-ttu-id="38812-213">Zie voor meer informatie over de opties voor het [instellen](configure-atp-anti-phishing-policies.md)van een anti-phishingfilter beleid.</span><span class="sxs-lookup"><span data-stu-id="38812-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="38812-214">Deel 4-anti spam bescherming</span><span class="sxs-lookup"><span data-stu-id="38812-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="38812-215">[Bescherming tegen ongewenste e-mail](anti-spam-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="38812-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="38812-216">Kies in het [beveiligings & compliance](https://protection.office.com)de optie **Threat management**  >  **Policy**  >  **anti-spam**beleid voor Threat Management.</span><span class="sxs-lookup"><span data-stu-id="38812-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="38812-217">Schakel op het tabblad **aangepast** de optie **aangepaste instellingen** in.</span><span class="sxs-lookup"><span data-stu-id="38812-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="38812-218">Vouw het **standaardbeleid voor spamfilters**uit, klik op **beleid bewerken**en geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="38812-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="38812-219">In de sectie **spam en Bulkacties** stelt u de drempelwaarde in op de waarde 5 of 6.</span><span class="sxs-lookup"><span data-stu-id="38812-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="38812-220">In het gedeelte **lijsten toestaan** controleert u de toegestane afzenders en domeinen en, indien nodig, bewerken.</span><span class="sxs-lookup"><span data-stu-id="38812-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="38812-221">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="38812-221">Click **Save**.</span></span>

<span data-ttu-id="38812-222">Zie [Antispambeleid in EOP](configure-your-spam-filter-policies.md)voor meer informatie over de opties voor anti-spam beleid.</span><span class="sxs-lookup"><span data-stu-id="38812-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="38812-223">Deel 5-aanvullende instellingen voor het configureren van</span><span class="sxs-lookup"><span data-stu-id="38812-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="38812-224">U wordt aangeraden uw instellingen voor automatisch wissen van Zero-hours en logboekregistratie te configureren voor het automatisch opschonen van een uur van malware, schadelijke Url's en bestanden, phishing en spam.</span><span class="sxs-lookup"><span data-stu-id="38812-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="38812-225">Zero-Hour automatisch wissen voor e-mail</span><span class="sxs-lookup"><span data-stu-id="38812-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="38812-226">[Het gebruik van Zero-Hour auto leegmaak](zero-hour-auto-purge.md) (ZAP) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="38812-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="38812-227">Deze bescherming is standaard ingeschakeld. u moet echter aan de volgende voorwaarden voldoen om beveiliging te activeren:</span><span class="sxs-lookup"><span data-stu-id="38812-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="38812-228">Spam acties worden ingesteld op **bericht verplaatsen naar map Ongewenste e-mail** in [Antispambeleid](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="38812-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="38812-229">Gebruikers hebben hun standaard [instellingen voor ongewenste](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e-mail bewaard en hebben niet de bescherming tegen ongewenste e-mail uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="38812-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="38812-230">Voor meer informatie raadpleegt u [Zero-Hour auto opgeschoond-bescherming tegen spam en malware](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="38812-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="38812-231">Controlelogboekregistratie voor rapportage en onderzoek</span><span class="sxs-lookup"><span data-stu-id="38812-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="38812-232">Controlelogboekregistratie is beschikbaar voor abonnementen die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)omvatten.</span><span class="sxs-lookup"><span data-stu-id="38812-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="38812-233">Als u gegevens wilt weergeven in rapporten over bedreigingsbeveiliging, zoals het [beveiligings dashboard](security-dashboard.md), de [rapporten voor e-mail beveiliging](view-email-security-reports.md)en de [Verkenner](threat-explorer.md), moet u logboekregistratie inschakelen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="38812-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="38812-234">Voor meer informatie raadpleegt u de [zoekfunctie voor auditlogboeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="38812-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="38812-235">Taken na de instelling</span><span class="sxs-lookup"><span data-stu-id="38812-235">Post-setup tasks</span></span>

<span data-ttu-id="38812-236">Nadat u uw beveiligingsfuncties hebt geconfigureerd, controleert u of de functies van deze functies werken, controleert u uw beleidsregels en wijzigt u deze naar wens, en bekijkt u de nieuwe functies en service-updates.</span><span class="sxs-lookup"><span data-stu-id="38812-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

****

|<span data-ttu-id="38812-237">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="38812-237">What to do</span></span>|<span data-ttu-id="38812-238">Informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="38812-238">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="38812-239">Kijk hoe de functies voor bedreigingsbeveiliging voor uw organisatie werken door rapporten weer te geven</span><span class="sxs-lookup"><span data-stu-id="38812-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="38812-240">Beveiligings dashboard</span><span class="sxs-lookup"><span data-stu-id="38812-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="38812-241">E-mail beveiligingsrapporten</span><span class="sxs-lookup"><span data-stu-id="38812-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="38812-242">Rapporten voor Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="38812-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="38812-243">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="38812-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="38812-244">Uw beveiligingsbeleid periodiek controleren en zo nodig herzien</span><span class="sxs-lookup"><span data-stu-id="38812-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="38812-245">Secure Score</span><span class="sxs-lookup"><span data-stu-id="38812-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="38812-246">Slimme rapporten en inzichten</span><span class="sxs-lookup"><span data-stu-id="38812-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="38812-247">Microsoft 365 Threat onderzoek en antwoord functies</span><span class="sxs-lookup"><span data-stu-id="38812-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="38812-248">Bekijk de nieuwe functies en service-updates</span><span class="sxs-lookup"><span data-stu-id="38812-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="38812-249">Standaard en gerichte release-opties</span><span class="sxs-lookup"><span data-stu-id="38812-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="38812-250">Berichtencentrum</span><span class="sxs-lookup"><span data-stu-id="38812-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="38812-251">Microsoft 365-wegwijzer</span><span class="sxs-lookup"><span data-stu-id="38812-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="38812-252">Service beschrijvingen</span><span class="sxs-lookup"><span data-stu-id="38812-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
