---
title: Mobiele meldingen in- of uitschakelen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: De zoekfunctie auditlogboek in- of uitschakelen in het Microsoft 365 compliancecentrum om beheerders in of uit te schakelen om het auditlogboek te doorzoeken.
ms.openlocfilehash: 457f453b001f71a095bc60932c8e0cebf46aa7b1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706661"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="1f4ee-103">Mobiele meldingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="1f4ee-103">Turn auditing on or off</span></span>

<span data-ttu-id="1f4ee-104">Auditlogboekregistratie is standaard ingeschakeld voor organisaties met Microsoft 365 en Office 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="1f4ee-105">Dit geldt ook voor organisaties met een E3/G3- of E5/G5-abonnement.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="1f4ee-106">Wanneer de controle in het compliancecentrum is ingeschakeld, worden activiteiten van gebruikers en beheerders van uw organisatie opgenomen in het auditlogboek en bewaard voor 90 dagen en maximaal één jaar, afhankelijk van de licentie die aan gebruikers is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="1f4ee-107">Het is echter mogelijk dat uw organisatie redenen heeft om geen controlelogboekgegevens op te nemen en te bewaren.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="1f4ee-108">In die gevallen kan een globale beheerder besluiten de controle in de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f4ee-109">Als u auditing in Microsoft 365 uitschakelen, kunt u de Office 365 Management Activity API of Azure Sentinel niet gebruiken om toegang te krijgen tot controlegegevens voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="1f4ee-110">Als u auditing uitkeert door de stappen in dit artikel uit te voeren, worden er geen resultaten geretourneerd wanneer u in het auditlogboek zoekt met behulp van het Beveiligings- & Compliancecentrum of wanneer u de cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="1f4ee-111">Dit betekent ook dat auditlogboeken niet beschikbaar zijn via de Office 365 Management Activity API of Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="1f4ee-112">Voordat u controle in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="1f4ee-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="1f4ee-113">U moet de rol Auditlogboeken toegewezen krijgen in Exchange Online auditing in of uit te schakelen in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="1f4ee-114">Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheer  en Organisatiebeheer op de pagina Machtigingen in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="1f4ee-115">Globale beheerders in Microsoft 365 zijn lid van de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="1f4ee-116">Aan gebruikers moeten machtigingen zijn toegewezen in Exchange Online controle in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="1f4ee-117">Als u gebruikers de rol Auditlogboeken **toewijst** op de pagina Machtigingen in het Beveiligings- & Compliancecentrum, kunnen ze de controle niet in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="1f4ee-118">De onderliggende cmdlet is namelijk een Exchange Online PowerShell-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 

- <span data-ttu-id="1f4ee-119">Zie Het auditlogboek doorzoeken in het beveiligings- & compliancecentrum voor stapsgewijse instructies over het [doorzoeken van het auditlogboek.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="1f4ee-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="1f4ee-120">Zie Aan de slag met Microsoft 365 Management [API's](/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie over Microsoft 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="1f4ee-121">Als u wilt controleren of auditing is ingeschakeld, kunt u de volgende opdracht uitvoeren in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1f4ee-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="1f4ee-122">De waarde van  `True` voor de  _eigenschap UnifiedAuditLogIngestionEnabled_ geeft aan dat auditing is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="1f4ee-123">Controle in- en uit-</span><span class="sxs-lookup"><span data-stu-id="1f4ee-123">Turn on auditing</span></span>

<span data-ttu-id="1f4ee-124">Als auditing niet is ingeschakeld voor uw organisatie, kunt u deze in het compliancecentrum in- of Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="1f4ee-125">Het kan enkele uren duren nadat u de controle hebt in- of uitgevoerd voordat u resultaten kunt retourneren wanneer u in het auditlogboek zoekt.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="1f4ee-126">Het compliancecentrum gebruiken om controle in te zetten</span><span class="sxs-lookup"><span data-stu-id="1f4ee-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="1f4ee-127">Ga naar <https://compliance.microsoft.com> en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="1f4ee-128">Klik in het linkernavigatiedeelvenster van Microsoft 365 compliancecentrum op **Alles weergeven** en klik vervolgens op **Controleren.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="1f4ee-129">Als auditing niet is ingeschakeld voor uw organisatie, wordt er een banner weergegeven waarin u wordt gevraagd gebruikers- en beheerdersactiviteiten op te nemen.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Banner op de pagina Controle](../media/AuditingBanner.png)

3. <span data-ttu-id="1f4ee-131">Klik op **de banner Start recording user and admin activity** banner.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="1f4ee-132">Het kan tot 60 minuten duren voordat de wijziging van kracht wordt.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="1f4ee-133">PowerShell gebruiken om controle in te zetten</span><span class="sxs-lookup"><span data-stu-id="1f4ee-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="1f4ee-134">Verbinding maken powershell Exchange Online gebruiken</span><span class="sxs-lookup"><span data-stu-id="1f4ee-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="1f4ee-135">Voer de volgende PowerShell-opdracht uit om auditing in te Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="1f4ee-136">Er wordt een bericht weergegeven met de melding dat het tot 60 minuten kan duren voordat de wijziging van kracht wordt.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="1f4ee-137">Controle uitschakelen</span><span class="sxs-lookup"><span data-stu-id="1f4ee-137">Turn off auditing</span></span>

<span data-ttu-id="1f4ee-138">U moet de Exchange Online PowerShell gebruiken om auditing uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="1f4ee-139">Verbinding maken powershell Exchange Online gebruiken</span><span class="sxs-lookup"><span data-stu-id="1f4ee-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="1f4ee-140">Voer de volgende PowerShell-opdracht uit om auditing uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="1f4ee-141">Controleer na een tijdje of de controle is uitgeschakeld (uitgeschakeld).</span><span class="sxs-lookup"><span data-stu-id="1f4ee-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="1f4ee-142">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="1f4ee-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="1f4ee-143">Voer Exchange Online PowerShell de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="1f4ee-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="1f4ee-144">De waarde van  `False` voor de  _eigenschap UnifiedAuditLogIngestionEnabled_ geeft aan dat auditing is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="1f4ee-145">Ga naar de **pagina Audit** in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="1f4ee-146">Als auditing niet is ingeschakeld voor uw organisatie, wordt er een banner weergegeven waarin u wordt gevraagd gebruikers- en beheerdersactiviteiten op te nemen.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
