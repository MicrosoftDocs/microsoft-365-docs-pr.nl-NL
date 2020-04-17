---
title: Het standaard beleid voor antiphishing configureren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie vinden over het wijzigen van de anti-spoofing-instellingen die beschikbaar zijn in het standaard beleid voor antiphishing in Office 365-organisaties met Exchange Online-postvakken.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537531"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="9fc31-103">Het standaard beleid voor antiphishing configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="9fc31-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="9fc31-104">Office 365-organisaties met Exchange Online-postvakken en zelfstandige Exchange Online Protection -organisaties (EOP)-organisaties zonder Exchange Online-postvakken hebben een standaard beleid voor antiphishing.</span><span class="sxs-lookup"><span data-stu-id="9fc31-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="9fc31-105">Dit beleid bevat een beperkt aantal anti-spoofing functies die standaard zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9fc31-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="9fc31-106">Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9fc31-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="9fc31-107">Office 365-organisaties met Exchange Online-postvakken kunnen het standaard beleid voor phishing-phishing wijzigen in het Office 365 Security & Compliance Center of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fc31-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="9fc31-108">Zelfstandige EOP-organisaties zonder Exchange Online-postvakken kunnen hun standaardbeleid voor antiphishing niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9fc31-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="9fc31-109">Zie [ATP-antiphishingbeleid configureren in Office 365](configure-atp-anti-phishing-policies.md)voor informatie over het maken en wijzigen van de meer geavanceerde ATP-antiphishingbeleidsregels die beschikbaar zijn in Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="9fc31-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9fc31-110">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="9fc31-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9fc31-111">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9fc31-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9fc31-112">Gebruik . **Anti-phishing** <https://protection.office.com/antiphishing></span><span class="sxs-lookup"><span data-stu-id="9fc31-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="9fc31-113">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fc31-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="9fc31-114">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="9fc31-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="9fc31-115">Als u antiphishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="9fc31-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="9fc31-116">Voor alleen-lezen toegang tot anti-phishingbeleid moet u lid zijn van de rolgroep **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="9fc31-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="9fc31-117">Zie [Machtigingen in het Office 365-beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="9fc31-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="9fc31-118">Zie [EOP standaard antiphishingbeleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor het standaardbeleid tegen phishing.</span><span class="sxs-lookup"><span data-stu-id="9fc31-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="9fc31-119">Sta maximaal 30 minuten toe voordat het bijgewerkte beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="9fc31-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="9fc31-120">Zie [Volgorde en voorrang van e-mailbeveiliging in Office 365](how-policies-and-protections-are-combined.md)voor informatie over waar antiphishingbeleid wordt toegepast in de filterpijplijn.</span><span class="sxs-lookup"><span data-stu-id="9fc31-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="9fc31-121">Het Beveiligingscentrum & gebruiken om het standaardbeleid voor phishing te wijzigen</span><span class="sxs-lookup"><span data-stu-id="9fc31-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="9fc31-122">Het standaard beleid voor antiphishing heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="9fc31-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="9fc31-123">Ga als volgt te werk om het standaard beleid voor antiphishing te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="9fc31-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="9fc31-124">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="9fc31-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="9fc31-125">Klik op de pagina **Anti-phishing** op **Standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="9fc31-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="9fc31-126">De pagina **Standaardinstelling voor uw beleid Office365 AntiPhish** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9fc31-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="9fc31-127">Klik **in** de sectie Spoof op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9fc31-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="9fc31-128">Houd er rekening mee dat deze instellingen identiek zijn aan de spoofinstellingen die beschikbaar zijn in het ATP-beleid voor phishing.</span><span class="sxs-lookup"><span data-stu-id="9fc31-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="9fc31-129">**Instellingen voor spoofingfilters:** de standaardwaarde is **ingeschakeld**en we raden u aan deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="9fc31-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="9fc31-130">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="9fc31-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="9fc31-131">Zie [Spoofinformatie configureren in Office 365](learn-about-spoof-intelligence.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9fc31-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="9fc31-132">U hoeft anti-spoofingbeveiliging niet uit te schakelen als uw MX-record niet naar Office 365 wijst. u schakelt in plaats daarvan Uitgebreide filtering voor connectors in.</span><span class="sxs-lookup"><span data-stu-id="9fc31-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="9fc31-133">Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .</span><span class="sxs-lookup"><span data-stu-id="9fc31-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="9fc31-134">**Functie Niet-geverifieerde afzender inschakelen:** hiermee voegt u een vraagteken toe aan de foto van de afzender als het bericht de verificatiecontroles van e-mailmislukt.</span><span class="sxs-lookup"><span data-stu-id="9fc31-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="9fc31-135">Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9fc31-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="9fc31-136">De standaardwaarde is **Aan**.</span><span class="sxs-lookup"><span data-stu-id="9fc31-136">The default value is **On**.</span></span> <span data-ttu-id="9fc31-137">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="9fc31-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="9fc31-138">**Acties:** Geef de actie op die moet worden uitgevoerd met berichten die niet in de spoofinformatie zijn geslaagd:</span><span class="sxs-lookup"><span data-stu-id="9fc31-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="9fc31-139">**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen:**</span><span class="sxs-lookup"><span data-stu-id="9fc31-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="9fc31-140">**Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden** (dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="9fc31-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="9fc31-141">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="9fc31-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="9fc31-142">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="9fc31-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="9fc31-143">U in elke sectie op **Bewerken** klikken om terug te gaan naar de desbetreffende pagina.</span><span class="sxs-lookup"><span data-stu-id="9fc31-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="9fc31-144">U de volgende instellingen direct op deze pagina **in-** of **uitschakelen:**</span><span class="sxs-lookup"><span data-stu-id="9fc31-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="9fc31-145">**Antispoofing-beveiliging inschakelen**</span><span class="sxs-lookup"><span data-stu-id="9fc31-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="9fc31-146">**Functie Niet-geverifieerde afzender inschakelen**</span><span class="sxs-lookup"><span data-stu-id="9fc31-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="9fc31-147">Klik op **Opslaan** op een pagina als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="9fc31-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="9fc31-148">Terug op de standaardpagina **van uw beleid Office365 AntiPhish,** controleert u uw instellingen en klikt u op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="9fc31-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="9fc31-149">Gebruik het Beveiligings& Compliance Center om het standaard antiphishingbeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="9fc31-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="9fc31-150">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="9fc31-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9fc31-151">Klik **op Standaardbeleid** om het standaard beleid voor antiphishing weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9fc31-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="9fc31-152">Exchange Online PowerShell gebruiken om het standaard beleid voor antiphishing te configureren</span><span class="sxs-lookup"><span data-stu-id="9fc31-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="9fc31-153">PowerShell gebruiken om het standaard anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="9fc31-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="9fc31-154">Voer de volgende opdracht uit om het standaard anti-phish-beleid weer te geven:</span><span class="sxs-lookup"><span data-stu-id="9fc31-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="9fc31-155">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9fc31-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="9fc31-156">PowerShell gebruiken om het standaard anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="9fc31-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="9fc31-157">Als u het standaard anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="9fc31-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="9fc31-158">In dit voorbeeld wordt de actie voor vervalste berichten die geen verificatiecontroles uitvoeren, gewijzigd in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="9fc31-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="9fc31-159">Zie [Set-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9fc31-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9fc31-160">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="9fc31-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="9fc31-161">Ga een van de volgende stappen uit om te controleren of u het standaardbeleid voor antiphishing hebt geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="9fc31-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="9fc31-162">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span><span class="sxs-lookup"><span data-stu-id="9fc31-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="9fc31-163">Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="9fc31-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
