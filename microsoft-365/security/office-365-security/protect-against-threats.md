---
title: Beveiligen tegen bedreigingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: Beheerders kunnen meer te weten komen over bedreigingsbeveiliging in Microsoft 365 en configureren hoe deze voor uw organisatie kunnen worden gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4176aabb88d177c7cff0f32f32543a251b558170
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587990"
---
# <a name="protect-against-threats"></a><span data-ttu-id="47e71-103">Beveiligen tegen bedreigingen</span><span class="sxs-lookup"><span data-stu-id="47e71-103">Protect against threats</span></span>

<span data-ttu-id="47e71-104">Microsoft 365 bevat een verscheidenheid aan functies voor bedreigingsbescherming.</span><span class="sxs-lookup"><span data-stu-id="47e71-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="47e71-105">Hier is een handleiding die u gebruiken als checklist om ervoor te zorgen dat uw functies voor bedreigingsbescherming zijn ingesteld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="47e71-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="47e71-106">Als u de functies voor bedreigingsbeveiliging in Office 365 nieuw bent of als u niet zeker weet waar u moet beginnen, gebruikt u de volgende richtlijnen als uitgangspunt.</span><span class="sxs-lookup"><span data-stu-id="47e71-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47e71-107">**Initiële aanbevolen instellingen zijn inbegrepen voor elk soort beleid; er zijn echter veel opties beschikbaar en u uw instellingen aanpassen aan de behoeften van uw specifieke organisatie.**</span><span class="sxs-lookup"><span data-stu-id="47e71-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="47e71-108">Sta ongeveer 30 minuten toe voor uw beleid of wijzigingen om zich een weg te banen door uw datacenter.</span><span class="sxs-lookup"><span data-stu-id="47e71-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="47e71-109">Vereisten</span><span class="sxs-lookup"><span data-stu-id="47e71-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="47e71-110">Abonnementen</span><span class="sxs-lookup"><span data-stu-id="47e71-110">Subscriptions</span></span>

<span data-ttu-id="47e71-111">Functies voor bedreigingsbescherming zijn opgenomen in alle Microsoft 365-abonnementen; Sommige abonnementen bevatten echter meer geavanceerde functies.</span><span class="sxs-lookup"><span data-stu-id="47e71-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="47e71-112">In de volgende tabel vindt u de beveiligingsfuncties in dit artikel samen met de minimale abonnementsvereisten.</span><span class="sxs-lookup"><span data-stu-id="47e71-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|||
|---|---|
|<span data-ttu-id="47e71-113">**Beveiligingstype**</span><span class="sxs-lookup"><span data-stu-id="47e71-113">**Protection type**</span></span>|<span data-ttu-id="47e71-114">**Abonnementsvereiste**</span><span class="sxs-lookup"><span data-stu-id="47e71-114">**Subscription requirement**</span></span>|
|<span data-ttu-id="47e71-115">Beveiliging tegen malware</span><span class="sxs-lookup"><span data-stu-id="47e71-115">Anti-malware protection</span></span>|<span data-ttu-id="47e71-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="47e71-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="47e71-117">Bescherming tegen schadelijke URL's en bestanden in e-mail- en Office-documenten</span><span class="sxs-lookup"><span data-stu-id="47e71-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="47e71-118">[Atp (Advanced Threat Protection) voor Office 365 (Advanced Threat Protection)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="47e71-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="47e71-119">Bescherming tegen phishing</span><span class="sxs-lookup"><span data-stu-id="47e71-119">Anti-phishing protection</span></span>|[<span data-ttu-id="47e71-120">Eop</span><span class="sxs-lookup"><span data-stu-id="47e71-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="47e71-121">Geavanceerde bescherming tegen phishing</span><span class="sxs-lookup"><span data-stu-id="47e71-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="47e71-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="47e71-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="47e71-123">Beveiliging tegen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="47e71-123">Anti-spam protection</span></span>|[<span data-ttu-id="47e71-124">Eop</span><span class="sxs-lookup"><span data-stu-id="47e71-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="47e71-125">Zero-hour automatische zuivering (voor e-mail)</span><span class="sxs-lookup"><span data-stu-id="47e71-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="47e71-126">Eop</span><span class="sxs-lookup"><span data-stu-id="47e71-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="47e71-127">Controlelogboekregistratie (dit wordt gebruikt voor rapportagedoeleinden)</span><span class="sxs-lookup"><span data-stu-id="47e71-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="47e71-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="47e71-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="47e71-129">Rollen en machtigingen</span><span class="sxs-lookup"><span data-stu-id="47e71-129">Roles and permissions</span></span>

<span data-ttu-id="47e71-130">U moet een geschikte rol toegewezen krijgen om beleid te configureren in het [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="47e71-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="47e71-131">De volgende tabel bevat enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="47e71-131">The following table includes some examples:</span></span>

|<span data-ttu-id="47e71-132">Rol of rollengroep</span><span class="sxs-lookup"><span data-stu-id="47e71-132">Role or role group</span></span>|<span data-ttu-id="47e71-133">Waar meer informatie te leren</span><span class="sxs-lookup"><span data-stu-id="47e71-133">Where to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="47e71-134">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="47e71-134">global administrator</span></span>|[<span data-ttu-id="47e71-135">Over Microsoft 365-beheersrollen</span><span class="sxs-lookup"><span data-stu-id="47e71-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="47e71-136">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="47e71-136">Security Administrator</span></span>|[<span data-ttu-id="47e71-137">Machtigingen voor beheerdersrollen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="47e71-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="47e71-138">Exchange Online Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="47e71-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="47e71-139">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="47e71-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="47e71-140">En</span><span class="sxs-lookup"><span data-stu-id="47e71-140">and</span></span><br> [<span data-ttu-id="47e71-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="47e71-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

<span data-ttu-id="47e71-142">Zie [Machtigingen in het Security &amp; Compliance Center voor](permissions-in-the-security-and-compliance-center.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="47e71-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="47e71-143">Deel 1 - Bescherming tegen malware</span><span class="sxs-lookup"><span data-stu-id="47e71-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="47e71-144">[Bescherming tegen malware](anti-malware-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="47e71-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="47e71-145">Kies in het [Security & Compliance Center](https://protection.office.com)voor Threat **management**  >  **Policy**  >  **Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="47e71-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="47e71-146">Dubbelklik op het **standaardbeleid** en kies **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="47e71-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="47e71-147">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="47e71-147">Specify the following settings:</span></span>

    - <span data-ttu-id="47e71-148">Houd in de sectie **Malwaredetectierespons** de standaardinstelling van **Nr.**</span><span class="sxs-lookup"><span data-stu-id="47e71-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="47e71-149">Kies in de sectie **Filter gemeenschappelijke bijlagetypen** de optie **Aan**.</span><span class="sxs-lookup"><span data-stu-id="47e71-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="47e71-150">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="47e71-150">Click **Save**.</span></span>

<span data-ttu-id="47e71-151">Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie over beleidsopties voor malwarebestrijding.</span><span class="sxs-lookup"><span data-stu-id="47e71-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="47e71-152">Deel 2 - Bescherming tegen kwaadaardige URL's en bestanden</span><span class="sxs-lookup"><span data-stu-id="47e71-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="47e71-153">Tijd-van-klik bescherming tegen kwaadaardige URL's en bestanden is beschikbaar in abonnementen die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) bevatten en is ingesteld via [ATP Safe Attachments](atp-safe-attachments.md) en [ATP Safe Links](atp-safe-links.md) beleid.</span><span class="sxs-lookup"><span data-stu-id="47e71-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="47e71-154">Atp-beleid voor veilige bijlagen</span><span class="sxs-lookup"><span data-stu-id="47e71-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="47e71-155">Als u [ATP Safe Attachments](atp-safe-attachments.md)wilt instellen, moet u ten minste één ATP-beleid voor veilige bijlagen definiëren.</span><span class="sxs-lookup"><span data-stu-id="47e71-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="47e71-156">Kies in het [Security & Compliance Center](https://protection.office.com)de ATP-veilige bijlagen voor **bedreigingsbeheerbeleid**  >  **Policy**  >  **ATP safe attachments**.</span><span class="sxs-lookup"><span data-stu-id="47e71-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="47e71-157">Selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="47e71-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="47e71-158">Klik in de sectie **E-mailbijlagen beveiligen** op het plusteken ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="47e71-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="47e71-159">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="47e71-159">Specify the following settings:</span></span>

   - <span data-ttu-id="47e71-160">Typ **in** het vak Naam `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="47e71-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="47e71-161">Kies in de sectie Antwoord de optie **Blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="47e71-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="47e71-162">Selecteer in de sectie **Bijlage Omleiden** de optie **Omleiding inschakelen**en geef vervolgens het e-mailadres op voor de beveiligingsbeheerder of -operator van uw organisatie die gedetecteerde bestanden controleert.</span><span class="sxs-lookup"><span data-stu-id="47e71-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="47e71-163">Kies **in** de sectie Toegepast op **de optie Het domein van de ontvanger is**.</span><span class="sxs-lookup"><span data-stu-id="47e71-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="47e71-164">Selecteer vervolgens uw domein, kies **Toevoegen**en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="47e71-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="47e71-165">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="47e71-165">Click **Save**.</span></span>

6. <span data-ttu-id="47e71-166">(**Aanbevolen extra stap**) Voer als globale beheerder of SharePoint Online-beheerder de cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit met de parameter **DisallowInfectedFileDownload** ingesteld op *true* voor uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="47e71-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="47e71-167">(Dit voorkomt dat mensen bestanden openen, verplaatsen, kopiëren of delen die als kwaadaardig worden gedetecteerd.)</span><span class="sxs-lookup"><span data-stu-id="47e71-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="47e71-168">Zie [Office 365 ATP Safe Attachments-beleid instellen](set-up-atp-safe-attachments-policies.md) en Office [365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams voor](turn-on-atp-for-spo-odb-and-teams.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="47e71-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="47e71-169">ATP Safe Links beleid</span><span class="sxs-lookup"><span data-stu-id="47e71-169">ATP Safe Links policies</span></span>

<span data-ttu-id="47e71-170">Als u [veilige verbindingsknopen ATP](atp-safe-links.md)wilt instellen, controleert en bewerkt u uw standaardbeleid en voegt u een beleid toe voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="47e71-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="47e71-171">Kies in het [Security & Compliance Center](https://protection.office.com)de ATP Safe Links voor **bedreigingsbeheerbeleid**  >  **Policy**  >  **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="47e71-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="47e71-172">Dubbelklik op het **standaardbeleid.**</span><span class="sxs-lookup"><span data-stu-id="47e71-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="47e71-173">Selecteer in de sectie **Veilige koppelingen gebruiken in** de sectie De optie Microsoft **365 Apps voor bedrijven, Office voor iOS en Android**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="47e71-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="47e71-174">Klik in de sectie **Beleid dat van toepassing is op specifieke geadresseerden** op het plusteken ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="47e71-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="47e71-175">Geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="47e71-175">Specify the following settings:</span></span>

   - <span data-ttu-id="47e71-176">Typ in het vak **Naam** een naam, zoals `Safe Links` .</span><span class="sxs-lookup"><span data-stu-id="47e71-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="47e71-177">Kies in **de sectie Selecteer de actie** de optie **Aan**.</span><span class="sxs-lookup"><span data-stu-id="47e71-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="47e71-178">Selecteer de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="47e71-178">Select these options:</span></span>

     - <span data-ttu-id="47e71-179">**Veilige bijlagen gebruiken om downloadbare inhoud te scannen**</span><span class="sxs-lookup"><span data-stu-id="47e71-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="47e71-180">**Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**</span><span class="sxs-lookup"><span data-stu-id="47e71-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="47e71-181">**Laat gebruikers niet doorklikken naar veilige links naar de oorspronkelijke URL**</span><span class="sxs-lookup"><span data-stu-id="47e71-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="47e71-182">Kies **in** de sectie Toegepast op **de optie Het domein van de ontvanger is**.</span><span class="sxs-lookup"><span data-stu-id="47e71-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="47e71-183">Selecteer vervolgens uw domein, kies **Toevoegen**en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="47e71-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="47e71-184">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="47e71-184">Click **Save**.</span></span>

<span data-ttu-id="47e71-185">Zie [Beleid voor veilige koppelingen in ATP instellen in Office 365](set-up-atp-safe-links-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="47e71-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="47e71-186">Deel 3 - Bescherming tegen phishing</span><span class="sxs-lookup"><span data-stu-id="47e71-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="47e71-187">[Anti-phishing]</span><span class="sxs-lookup"><span data-stu-id="47e71-187">[Anti-phishing]</span></span>

<span data-ttu-id="47e71-188">[Bescherming tegen phishing](anti-phishing-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="47e71-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="47e71-189">Geavanceerde anti-phishing bescherming is beschikbaar in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="47e71-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="47e71-190">In de volgende procedure wordt beschreven hoe u een ATP-antiphishingbeleid configureert.</span><span class="sxs-lookup"><span data-stu-id="47e71-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="47e71-191">De stappen zijn vergelijkbaar voor het configureren van een anti-phishing beleid (zonder ATP).</span><span class="sxs-lookup"><span data-stu-id="47e71-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="47e71-192">Kies in het [Security & Compliance Center](https://protection.office.com)voor **Threat management**  >  **Policy**  >  **ATP-antiphishing**van bedreigingsbeheerbeleid .</span><span class="sxs-lookup"><span data-stu-id="47e71-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="47e71-193">Klik **op Standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="47e71-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="47e71-194">Klik in de sectie **Imitatie** op **Bewerken**en geef vervolgens de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="47e71-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="47e71-195">Schakel op het tabblad **Gebruikers toevoegen om te beveiligen** de beveiliging in.</span><span class="sxs-lookup"><span data-stu-id="47e71-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="47e71-196">Voeg vervolgens gebruikers toe, zoals de bestuursleden van uw organisatie, uw CEO, CFO en andere senior leiders.</span><span class="sxs-lookup"><span data-stu-id="47e71-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="47e71-197">(U een individueel e-mailadres typen of klikken om een lijst weer te geven.)</span><span class="sxs-lookup"><span data-stu-id="47e71-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="47e71-198">Schakel op het tabblad **Domeinen toevoegen om te beveiligen** automatisch de **domeinen op die ik bezit.**</span><span class="sxs-lookup"><span data-stu-id="47e71-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="47e71-199">Als u aangepaste domeinen hebt, voegt u deze ook toe.</span><span class="sxs-lookup"><span data-stu-id="47e71-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="47e71-200">Selecteer **op** het tabblad Handelingen **het bericht in quarantaine** plaatsen voor zowel de **geïmiteerde gebruiker als** de **geïmiteerde domeinopties.**</span><span class="sxs-lookup"><span data-stu-id="47e71-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="47e71-201">Schakel bovendien impersonatieveiligheidstips in.</span><span class="sxs-lookup"><span data-stu-id="47e71-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="47e71-202">Controleer op het tabblad **Inlichtingendienst Postvak** of de inlichtingendienst is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47e71-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="47e71-203">Schakel bovendien de op basis van postvakintelligentie op basis van imitatiebeveiliging in.</span><span class="sxs-lookup"><span data-stu-id="47e71-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="47e71-204">Kies in de **e-mail als e-mail wordt verzonden door een geïmiteerde gebruikerslijst,** **de optie Het bericht in quarantaine**plaatsen .</span><span class="sxs-lookup"><span data-stu-id="47e71-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="47e71-205">Geef op het tabblad **Vertrouwde afzenders en domeinen toevoegen** alle vertrouwde afzenders of domeinen op die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="47e71-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="47e71-206">Klik op het tabblad **Instellingen controleren** nadat u uw instellingen hebt gecontroleerd op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="47e71-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="47e71-207">Klik in de sectie **Spoof** op **Bewerken**en geef de volgende instellingen op:</span><span class="sxs-lookup"><span data-stu-id="47e71-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="47e71-208">Controleer op het tabblad **Instellingen voor spoofingfilterinstellingen** of anti-spoofingbeveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47e71-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="47e71-209">Kies **op** het tabblad Handelingen **het bericht in quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="47e71-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="47e71-210">Klik op het tabblad **Instellingen controleren** nadat u uw instellingen hebt gecontroleerd op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="47e71-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="47e71-211">(Als u geen wijzigingen hebt aangebracht, klikt u op **Annuleren**.)</span><span class="sxs-lookup"><span data-stu-id="47e71-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="47e71-212">Sluit de pagina standaardbeleidsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="47e71-212">Close the default policy settings page.</span></span>

<span data-ttu-id="47e71-213">Zie [ATP-antiphishingbeleid configureren](configure-atp-anti-phishing-policies.md)voor meer informatie over uw anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="47e71-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="47e71-214">Deel 4 - Anti-spam bescherming</span><span class="sxs-lookup"><span data-stu-id="47e71-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="47e71-215">[Antispambeveiliging](anti-spam-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="47e71-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="47e71-216">Kies in het [Security & Compliance Center](https://protection.office.com)voor Threat **management**  >  **Policy**  >  **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="47e71-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="47e71-217">Schakel op het tabblad **Aangepast** **aangepaste instellingen** in.</span><span class="sxs-lookup"><span data-stu-id="47e71-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="47e71-218">Uitvouwen **Standaard spam filter beleid,** klik op **Beleid bewerken**, en geef vervolgens de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="47e71-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="47e71-219">Stel in de sectie **Spam- en bulkacties** de drempel in op een waarde van 5 of 6.</span><span class="sxs-lookup"><span data-stu-id="47e71-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="47e71-220">Controleer (en bewerk) in de sectie **Lijsten toestaan** uw toegestane afzenders en domeinen indient (en indien nodig) bewerkt.</span><span class="sxs-lookup"><span data-stu-id="47e71-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="47e71-221">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="47e71-221">Click **Save**.</span></span>

<span data-ttu-id="47e71-222">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor meer informatie over uw antispambeleidsopties.</span><span class="sxs-lookup"><span data-stu-id="47e71-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="47e71-223">Deel 5 - Extra instellingen om te configureren</span><span class="sxs-lookup"><span data-stu-id="47e71-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="47e71-224">Naast het configureren van bescherming tegen malware, kwaadaardige URL's en bestanden, phishing en spam, raden we u aan uw instellingen voor automatische zuivering en controleregistratie van nul uur te configureren.</span><span class="sxs-lookup"><span data-stu-id="47e71-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="47e71-225">Zero-hour automatische zuivering voor e-mail</span><span class="sxs-lookup"><span data-stu-id="47e71-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="47e71-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="47e71-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="47e71-227">Deze beveiliging is standaard ingeschakeld. aan de volgende voorwaarden moet echter worden voldaan om de bescherming van kracht te maken:</span><span class="sxs-lookup"><span data-stu-id="47e71-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="47e71-228">Spamacties zijn ingesteld op **Bericht verplaatsen naar map Ongewenste e-mail** in [antispambeleid.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="47e71-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="47e71-229">Gebruikers hebben hun standaard [instellingen voor ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)behouden en hebben de beveiliging van ongewenste e-mail niet uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47e71-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="47e71-230">Zie voor meer informatie [de automatische zuivering van zero-uur - bescherming tegen spam en malware.](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="47e71-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="47e71-231">Controleregistratie voor rapportage en onderzoek</span><span class="sxs-lookup"><span data-stu-id="47e71-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="47e71-232">Controlelogboekregistratie is beschikbaar in abonnementen die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)bevatten.</span><span class="sxs-lookup"><span data-stu-id="47e71-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="47e71-233">Als u gegevens wilt weergeven in rapporten over bedreigingsbescherming, zoals het [beveiligingsdashboard,](security-dashboard.md) [e-mailbeveiligingsrapporten](view-email-security-reports.md)en [Explorer,](threat-explorer.md)moet controleregistratie zijn ingeschakeld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="47e71-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="47e71-234">Zie [Zoeken in of uit controleren op controlelogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="47e71-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="47e71-235">Taken na het instellen</span><span class="sxs-lookup"><span data-stu-id="47e71-235">Post-setup tasks</span></span>

<span data-ttu-id="47e71-236">Nadat u uw functies voor bedreigingsbeveiliging hebt geconfigureerd, controleert u hoe deze functies werken, controleert en herziet u uw beleid indien nodig en kijkt u naar nieuwe functies en service-updates.</span><span class="sxs-lookup"><span data-stu-id="47e71-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|||
|---|---|
|<span data-ttu-id="47e71-237">**Wat te doen**</span><span class="sxs-lookup"><span data-stu-id="47e71-237">**What to do**</span></span>|<span data-ttu-id="47e71-238">**Informatiebronnen**</span><span class="sxs-lookup"><span data-stu-id="47e71-238">**Resources to learn more**</span></span>|
|<span data-ttu-id="47e71-239">Bekijk hoe functies voor bedreigingsbescherming voor uw organisatie werken door rapporten te bekijken</span><span class="sxs-lookup"><span data-stu-id="47e71-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="47e71-240">Beveiligingsdashboard</span><span class="sxs-lookup"><span data-stu-id="47e71-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="47e71-241">Beveiligingsrapporten voor e-mail</span><span class="sxs-lookup"><span data-stu-id="47e71-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="47e71-242">Rapporten voor Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="47e71-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="47e71-243">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="47e71-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="47e71-244">Uw beleid voor bedreigingsbescherming periodiek herzien en herzien indien nodig</span><span class="sxs-lookup"><span data-stu-id="47e71-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="47e71-245">Veilige score</span><span class="sxs-lookup"><span data-stu-id="47e71-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="47e71-246">Slimme rapporten en inzichten</span><span class="sxs-lookup"><span data-stu-id="47e71-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="47e71-247">Microsoft 365-functies voor bedreigingsonderzoek en -reactie</span><span class="sxs-lookup"><span data-stu-id="47e71-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="47e71-248">Kijk voor nieuwe functies en service-updates</span><span class="sxs-lookup"><span data-stu-id="47e71-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="47e71-249">Standaard- en gerichte releaseopties</span><span class="sxs-lookup"><span data-stu-id="47e71-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="47e71-250">Berichtencentrum</span><span class="sxs-lookup"><span data-stu-id="47e71-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="47e71-251">Microsoft 365-routekaart</span><span class="sxs-lookup"><span data-stu-id="47e71-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="47e71-252">Servicebeschrijvingen</span><span class="sxs-lookup"><span data-stu-id="47e71-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
