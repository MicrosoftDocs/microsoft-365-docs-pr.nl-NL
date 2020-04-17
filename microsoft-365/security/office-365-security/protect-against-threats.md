---
title: Beschermen tegen bedreigingen in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Gebruik dit artikel als een handleiding om uw functies voor bedreigingsbescherming nu te configureren.
ms.openlocfilehash: 34a89f9db0ca7424d90909f09f7a2bfb4fcf3b6a
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528555"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="7d9d3-103">Beschermen tegen bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="7d9d3-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="7d9d3-104">Office 365 bevat verschillende functies voor bedreigingsbescherming.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="7d9d3-105">Hier is een handleiding voor snel starten die u gebruiken als checklist om ervoor te zorgen dat uw functies voor bedreigingsbescherming zijn ingesteld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="7d9d3-106">Als u nieuw bent in functies voor bedreigingsbeveiliging in Office 365 of als u niet zeker weet waar u moet beginnen, gebruikt u de volgende richtlijnen als uitgangspunt.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d9d3-107">**De eerste aanbevolen instellingen zijn opgenomen voor elk type beleid; er zijn echter veel opties beschikbaar en u uw instellingen aanpassen aan de behoeften van uw specifieke organisatie.**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="7d9d3-108">Geef uw beleid of wijzigingen ongeveer 30 minuten de tijd om zich een weg te banen door uw datacenter.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d9d3-109">Vereisten</span><span class="sxs-lookup"><span data-stu-id="7d9d3-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="7d9d3-110">Abonnementen</span><span class="sxs-lookup"><span data-stu-id="7d9d3-110">Subscriptions</span></span>

<span data-ttu-id="7d9d3-111">Functies voor bedreigingsbescherming zijn opgenomen in alle Office 365-abonnementen; Sommige abonnementen bevatten echter meer geavanceerde functies.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="7d9d3-112">In de volgende tabel worden de beveiligingsfuncties in dit artikel weergegeven, samen met de minimale abonnementsvereisten.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span>

|||
|---|---|
|<span data-ttu-id="7d9d3-113">**Beschermingstype**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-113">**Protection type**</span></span>|<span data-ttu-id="7d9d3-114">**Abonnementsvereiste**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-114">**Subscription requirement**</span></span>|
|<span data-ttu-id="7d9d3-115">Beveiliging tegen malware</span><span class="sxs-lookup"><span data-stu-id="7d9d3-115">Anti-malware protection</span></span>|<span data-ttu-id="7d9d3-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="7d9d3-117">Bescherming tegen schadelijke URL's en bestanden in e-mail- en Office-documenten</span><span class="sxs-lookup"><span data-stu-id="7d9d3-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="7d9d3-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="7d9d3-119">Bescherming tegen phishing</span><span class="sxs-lookup"><span data-stu-id="7d9d3-119">Anti-phishing protection</span></span>|[<span data-ttu-id="7d9d3-120">Eop</span><span class="sxs-lookup"><span data-stu-id="7d9d3-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="7d9d3-121">Geavanceerde bescherming tegen phishing</span><span class="sxs-lookup"><span data-stu-id="7d9d3-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="7d9d3-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="7d9d3-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="7d9d3-123">Beveiliging tegen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="7d9d3-123">Anti-spam protection</span></span>|[<span data-ttu-id="7d9d3-124">Eop</span><span class="sxs-lookup"><span data-stu-id="7d9d3-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="7d9d3-125">Automatische zuivering van nul uur (voor e-mail)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="7d9d3-126">Eop</span><span class="sxs-lookup"><span data-stu-id="7d9d3-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="7d9d3-127">Controlelogboekregistratie (dit wordt gebruikt voor rapportagedoeleinden)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="7d9d3-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7d9d3-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="7d9d3-129">Rollen en machtigingen</span><span class="sxs-lookup"><span data-stu-id="7d9d3-129">Roles and permissions</span></span>

<span data-ttu-id="7d9d3-130">U moet een geschikte rol toegewezen krijgen om beleid te configureren in het [Security & Compliance Center.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="7d9d3-131">De volgende tabel bevat enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-131">The following table includes some examples:</span></span>

|||
|---|---|
|<span data-ttu-id="7d9d3-132">**Rol of rollengroep**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-132">**Role or role group**</span></span>|<span data-ttu-id="7d9d3-133">**Waar u meer leren**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-133">**Where to learn more**</span></span>|
|<span data-ttu-id="7d9d3-134">Globale beheerder van Office 365</span><span class="sxs-lookup"><span data-stu-id="7d9d3-134">Office 365 Global Administrator</span></span>|[<span data-ttu-id="7d9d3-135">Informatie over beheerdersrollen in Office 365</span><span class="sxs-lookup"><span data-stu-id="7d9d3-135">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="7d9d3-136">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="7d9d3-136">Security Administrator</span></span>|[<span data-ttu-id="7d9d3-137">Machtigingen voor beheerdersrollen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7d9d3-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="7d9d3-138">Exchange Online Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="7d9d3-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="7d9d3-139">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7d9d3-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="7d9d3-140">En</span><span class="sxs-lookup"><span data-stu-id="7d9d3-140">and</span></span><br> [<span data-ttu-id="7d9d3-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d9d3-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

<span data-ttu-id="7d9d3-142">Zie [Machtigingen in het Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-142">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="7d9d3-143">Deel 1 - Bescherming tegen malware</span><span class="sxs-lookup"><span data-stu-id="7d9d3-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="7d9d3-144">[Anti-malware bescherming](anti-malware-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="7d9d3-145">Kies in het [Security & Compliance Center](https://protection.office.com)de optie Threat **management** > **Policy** > **Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="7d9d3-146">Dubbelklik op het **standaardbeleid** en kies **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="7d9d3-147">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-147">Specify the following settings:</span></span>

    - <span data-ttu-id="7d9d3-148">Houd in de sectie **Reactie op malwaredetectie** de standaardinstelling **Nr.**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="7d9d3-149">Kies in de sectie **Common Attachment Types Filter** de optie **Op**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="7d9d3-150">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-150">Click **Save**.</span></span>

<span data-ttu-id="7d9d3-151">Zie Beleid voor antimalware configureren voor meer informatie over beleidsopties voor [antimalware.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="7d9d3-152">Deel 2 - Bescherming tegen schadelijke URL's en bestanden</span><span class="sxs-lookup"><span data-stu-id="7d9d3-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="7d9d3-153">Time-of-click bescherming tegen schadelijke URL's en bestanden is beschikbaar in abonnementen die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) bevatten en is ingesteld via [ATP Safe Attachments](atp-safe-attachments.md) en [ATP Safe Links-beleid.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="7d9d3-154">Beleid voor veilige bijlagen van ATP</span><span class="sxs-lookup"><span data-stu-id="7d9d3-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="7d9d3-155">Als u [ATP Safe Attachments](atp-safe-attachments.md)wilt instellen, moet u ten minste één ATP-beleid voor veilige bijlagen definiëren.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="7d9d3-156">Kies [in](https://protection.office.com)het Security & Compliance Center de optie**Policy** > **ATP-veilige bijlagen**voor **beleid voor bedreigingen** > .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="7d9d3-157">Selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="7d9d3-158">Klik in de sectie **E-mailbijlagen** **+** beveiligen op het plusteken ( ).</span><span class="sxs-lookup"><span data-stu-id="7d9d3-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="7d9d3-159">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-159">Specify the following settings:</span></span>

   - <span data-ttu-id="7d9d3-160">Typ **Name** in het `Block malware`vak Naam .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="7d9d3-161">Kies **Blokkeren**in de sectie Antwoord .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="7d9d3-162">Selecteer in de sectie **Bijlage omleiden** de optie **Omleiding inschakelen**en geef vervolgens het e-mailadres op voor de beveiligingsbeheerder of -operator van uw organisatie die gedetecteerde bestanden controleert.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="7d9d3-163">Kies **Het** **geadresseerdendomein is**in de sectie Toegepast op .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="7d9d3-164">Selecteer vervolgens uw domein, kies **Toevoegen**en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="7d9d3-165">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-165">Click **Save**.</span></span>

6. <span data-ttu-id="7d9d3-166">(**Aanbevolen extra stap**) Als globale beheerder of SharePoint Online-beheerder voert u de cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit met de parameter **DisallowInfectedFileDownload** die is ingesteld op *true* voor uw Office 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="7d9d3-167">(Dit voorkomt dat mensen bestanden openen, verplaatsen, kopiëren of delen die als kwaadaardig worden gedetecteerd.)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="7d9d3-168">Zie Office [365 ATP-beleid voor veilige bijlagen instellen](set-up-atp-safe-attachments-policies.md) en Office [365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7d9d3-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="7d9d3-169">Beleid voor veilige links van ATP</span><span class="sxs-lookup"><span data-stu-id="7d9d3-169">ATP Safe Links policies</span></span>

<span data-ttu-id="7d9d3-170">Als u [ATP Safe Links wilt](atp-safe-links.md)instellen, controleert en bewerkt u uw standaardbeleid en voegt u een beleid toe voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="7d9d3-171">Kies [in](https://protection.office.com)het Security & Compliance Center de optie Atp Safe > **Links** **voor bedreigingsbeheerbeleid** > **Policy**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="7d9d3-172">Dubbelklik op het **standaardbeleid.**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="7d9d3-173">Selecteer **in** de sectie Veilige koppelingen gebruiken in de optie **Office 365 ProPlus, Office voor iOS en Android**en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-173">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="7d9d3-174">Klik **in de sectie Beleid dat van toepassing is op specifieke ontvangers** op het plusteken (**+**).</span><span class="sxs-lookup"><span data-stu-id="7d9d3-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="7d9d3-175">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-175">Specify the following settings:</span></span>

   - <span data-ttu-id="7d9d3-176">Typ in het vak **Naam** een `Safe Links`naam, zoals .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="7d9d3-177">Kies in de sectie **De actie selecteren de** optie **Aan**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="7d9d3-178">Selecteer de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-178">Select these options:</span></span>

     - <span data-ttu-id="7d9d3-179">**Veilige bijlagen gebruiken om downloadbare inhoud te scannen**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="7d9d3-180">**Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="7d9d3-181">**Laat gebruikers niet door veilige links naar de oorspronkelijke URL klikken**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="7d9d3-182">Kies **Het** **geadresseerdendomein is**in de sectie Toegepast op .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="7d9d3-183">Selecteer vervolgens uw domein, kies **Toevoegen**en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="7d9d3-184">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-184">Click **Save**.</span></span>

<span data-ttu-id="7d9d3-185">Zie [Beleid voor veilige koppelingen in ATP instellen in Office 365](set-up-atp-safe-links-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="7d9d3-186">Deel 3 - Bescherming tegen phishing</span><span class="sxs-lookup"><span data-stu-id="7d9d3-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="7d9d3-187">[Anti-phishing]</span><span class="sxs-lookup"><span data-stu-id="7d9d3-187">[Anti-phishing]</span></span>

<span data-ttu-id="7d9d3-188">[Bescherming tegen phishing](anti-phishing-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="7d9d3-189">Geavanceerde bescherming tegen phishing is beschikbaar in [ATP.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="7d9d3-190">In de volgende procedure wordt beschreven hoe u een ATP-antiphishingbeleid configureert.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="7d9d3-191">De stappen zijn vergelijkbaar voor het configureren van een anti-phishing beleid (zonder ATP).</span><span class="sxs-lookup"><span data-stu-id="7d9d3-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="7d9d3-192">Kies [in](https://protection.office.com)het Security & Compliance Center de optie Threat **management** > **Policy** > **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7d9d3-193">Klik **op Standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="7d9d3-194">Klik **in** de sectie Imitatie op **Bewerken**en geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="7d9d3-195">Schakel op het tabblad **Gebruikers toevoegen om het** tabblad te beschermen in.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="7d9d3-196">Voeg vervolgens gebruikers toe, zoals de leden van uw organisatie, uw CEO, CFO en andere senior leiders.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="7d9d3-197">(U een individueel e-mailadres typen of klikken om een lijst weer te geven.)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="7d9d3-198">Schakel op het tabblad **Domeinen toevoegen om te beschermen** automatisch de domeinen in die ik **bezit.**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="7d9d3-199">Als u aangepaste domeinen hebt, voegt u deze ook toe.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="7d9d3-200">Selecteer op het tabblad **Acties** de optie **Het bericht in quarantaine plaatsen** voor zowel de **nagebootste gebruiker** als de **nagebootste domeinopties.**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="7d9d3-201">Schakel bovendien veiligheidstips voor imitatie in.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="7d9d3-202">Controleer op het tabblad **Postvakintelligentie** of postvakinformatie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="7d9d3-203">Schakel bovendien op basis van de bescherming van postvakintelligentie op basis van imitatie in.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="7d9d3-204">Kies in de **lijst Als-e-mail wordt verzonden door een nagebootste gebruikerslijst** de optie **Het bericht in quarantaine plaatsen.**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="7d9d3-205">Geef op het tabblad **Vertrouwde afzenders en domeinen toevoegen** alle vertrouwde afzenders of domeinen op die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="7d9d3-206">Klik op het tabblad **Instellingen controleren** nadat u uw instellingen hebt gecontroleerd op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="7d9d3-207">Klik in de sectie **Spoof** op **Bewerken**en geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="7d9d3-208">Controleer op het tabblad **Instellingen voor spoofing-filterinstellingen** of anti-spoofing-beveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="7d9d3-209">Kies op het tabblad **Acties** de optie **Het bericht in quarantaine**plaatsen .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="7d9d3-210">Klik op het tabblad **Instellingen controleren** nadat u uw instellingen hebt gecontroleerd op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="7d9d3-211">(Als u geen wijzigingen hebt aangebracht, klikt u op **Annuleren**.)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="7d9d3-212">Sluit de pagina standaardbeleidsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-212">Close the default policy settings page.</span></span>

<span data-ttu-id="7d9d3-213">Zie [ATP-beleid voor phishing configureren in Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie over de anti-phishingbeleidsopties.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="7d9d3-214">Deel 4 - Bescherming tegen spam</span><span class="sxs-lookup"><span data-stu-id="7d9d3-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="7d9d3-215">[Bescherming tegen spam](anti-spam-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="7d9d3-216">Kies in het [Security & Compliance Center](https://protection.office.com)de optie **Bedreigingsbeheer** > **Anti-spam\*\*\*\*Policy** > .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="7d9d3-217">Schakel op het tabblad **Aangepast** **aangepaste instellingen** in.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="7d9d3-218">Standaardbeleid **voor spamfilters**uitvouwen, op **Beleid bewerken**klikken en vervolgens de volgende instellingen opgeven:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="7d9d3-219">Stel in de sectie **Spam- en bulkacties** de drempelwaarde in op een waarde van 5 of 6.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="7d9d3-220">Controleer in de sectie Lijsten toestaan de toegestane afzenders en domeinen.In the **Allow lists** section, review (and if necessary, edit) your llowed senders and domains.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="7d9d3-221">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-221">Click **Save**.</span></span>

<span data-ttu-id="7d9d3-222">Zie [Beleid voor antispam configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie over de opties voor antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="7d9d3-223">Deel 5 - Extra instellingen om te configureren</span><span class="sxs-lookup"><span data-stu-id="7d9d3-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="7d9d3-224">Naast het configureren van bescherming tegen malware, schadelijke URL's en bestanden, phishing en spam, raden we u aan uw instellingen voor automatische controle en controle van nul uur te configureren.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="7d9d3-225">Nuluur automatische zuivering voor e-mail</span><span class="sxs-lookup"><span data-stu-id="7d9d3-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="7d9d3-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="7d9d3-227">Deze beveiliging is standaard ingeschakeld; er moet echter aan de volgende voorwaarden worden voldaan om de bescherming van kracht te kunnen hebben:</span><span class="sxs-lookup"><span data-stu-id="7d9d3-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="7d9d3-228">Spamacties zijn ingesteld op **Bericht verplaatsen naar de map Ongewenste e-mail** in [antispambeleid.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="7d9d3-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="7d9d3-229">Gebruikers hebben hun standaard [instellingen voor ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)behouden en hebben de beveiliging van ongewenste e-mail niet uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="7d9d3-230">Zie [Zero-hour auto purge voor](zero-hour-auto-purge.md)meer informatie - bescherming tegen spam en malware .</span><span class="sxs-lookup"><span data-stu-id="7d9d3-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="7d9d3-231">Controlelogboekregistratie voor rapportage en onderzoek</span><span class="sxs-lookup"><span data-stu-id="7d9d3-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="7d9d3-232">Controlelogboekregistratie is beschikbaar in abonnementen die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="7d9d3-233">Als u gegevens wilt weergeven in meldingen van bedreigingsbeveiliging, zoals het [beveiligingsdashboard,](security-dashboard.md) [e-mailbeveiligingsrapporten](view-email-security-reports.md)en [Explorer,](threat-explorer.md)moet controlelogboekregistratie voor uw organisatie worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="7d9d3-234">Zie [Office 365-controlelogboekzoeken in of uit zetten](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-234">To learn more, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="7d9d3-235">Taken na het instellen</span><span class="sxs-lookup"><span data-stu-id="7d9d3-235">Post-setup tasks</span></span>

<span data-ttu-id="7d9d3-236">Nadat u uw functies voor bedreigingsbeveiliging hebt geconfigureerd, moet u controleren hoe deze functies werken, uw beleid bekijken en zo nodig herzien en op nieuwe functies en service-updates letten.</span><span class="sxs-lookup"><span data-stu-id="7d9d3-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|||
|---|---|
|<span data-ttu-id="7d9d3-237">**Wat te doen**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-237">**What to do**</span></span>|<span data-ttu-id="7d9d3-238">**Informatiebronnen**</span><span class="sxs-lookup"><span data-stu-id="7d9d3-238">**Resources to learn more**</span></span>|
|<span data-ttu-id="7d9d3-239">Bekijk hoe functies voor bedreigingsbescherming voor uw organisatie werken door rapporten te bekijken</span><span class="sxs-lookup"><span data-stu-id="7d9d3-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="7d9d3-240">Beveiligingsdashboard</span><span class="sxs-lookup"><span data-stu-id="7d9d3-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="7d9d3-241">Beveiligingsrapporten per e-mail</span><span class="sxs-lookup"><span data-stu-id="7d9d3-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="7d9d3-242">Rapporten voor Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="7d9d3-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="7d9d3-243">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="7d9d3-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="7d9d3-244">Uw beleid voor bedreigingsbescherming regelmatig controleren en herzien als dat nodig is</span><span class="sxs-lookup"><span data-stu-id="7d9d3-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="7d9d3-245">Secure Score</span><span class="sxs-lookup"><span data-stu-id="7d9d3-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="7d9d3-246">Slimme rapporten en inzichten</span><span class="sxs-lookup"><span data-stu-id="7d9d3-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="7d9d3-247">Functies voor het onderzoeken en reageren van Office 365-bedreigingen</span><span class="sxs-lookup"><span data-stu-id="7d9d3-247">Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="7d9d3-248">Kijk uit voor nieuwe functies en service-updates</span><span class="sxs-lookup"><span data-stu-id="7d9d3-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="7d9d3-249">Standaard- en gerichte releaseopties</span><span class="sxs-lookup"><span data-stu-id="7d9d3-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="7d9d3-250">Berichtencentrum</span><span class="sxs-lookup"><span data-stu-id="7d9d3-250">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="7d9d3-251">Microsoft 365-roadmap</span><span class="sxs-lookup"><span data-stu-id="7d9d3-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="7d9d3-252">Servicebeschrijvingen</span><span class="sxs-lookup"><span data-stu-id="7d9d3-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
