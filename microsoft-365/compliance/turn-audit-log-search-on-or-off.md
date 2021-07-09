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
description: De zoekfunctie auditlogboek in- of uitschakelen in de Microsoft 365-compliancecentrum om beheerders in of uit te schakelen om het auditlogboek te doorzoeken.
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341494"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="13884-103">Mobiele meldingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="13884-103">Turn auditing on or off</span></span>

<span data-ttu-id="13884-104">Auditlogboekregistratie is standaard ingeschakeld voor organisaties met Microsoft 365 en Office 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="13884-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="13884-105">Wanneer de controle in de Microsoft 365-compliancecentrum is ingeschakeld, worden activiteiten van gebruikers en beheerders van uw organisatie opgenomen in het auditlogboek en bewaard voor 90 dagen, en maximaal één jaar, afhankelijk van de licentie die aan gebruikers is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="13884-105">When auditing in the Microsoft 365 compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="13884-106">Het is echter mogelijk dat uw organisatie redenen heeft om geen controlelogboekgegevens op te nemen en te bewaren.</span><span class="sxs-lookup"><span data-stu-id="13884-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="13884-107">In die gevallen kan een globale beheerder besluiten de controle in de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13884-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

<span data-ttu-id="13884-108">Bij het instellen van een nieuwe Microsoft 365 of Office 365 organisatie, kunt u de controlestatus voor uw organisatie controleren.</span><span class="sxs-lookup"><span data-stu-id="13884-108">When setting up a new Microsoft 365 or Office 365 organization, you can verify the auditing status for your organization.</span></span> <span data-ttu-id="13884-109">Zie de sectie [](#verify-the-auditing-status-for-your-organization) Controlestatus controleren voor uw organisatie in dit artikel voor instructies.</span><span class="sxs-lookup"><span data-stu-id="13884-109">For instructions, see the [Verify the auditing status for your organization](#verify-the-auditing-status-for-your-organization) section in this article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13884-110">Als u auditing in Microsoft 365 uitschakelen, kunt u de Office 365 Management Activity API of Azure Sentinel niet gebruiken om toegang te krijgen tot controlegegevens voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="13884-110">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="13884-111">Als u auditing uitkeert door de stappen in dit artikel uit te voeren, worden er geen resultaten geretourneerd wanneer u in het auditlogboek zoekt met de Microsoft 365-compliancecentrum of wanneer u de cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13884-111">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Microsoft 365 compliance center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="13884-112">Dit betekent ook dat auditlogboeken niet beschikbaar zijn via de Office 365 Management Activity API of Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="13884-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="13884-113">Voordat u controle in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="13884-113">Before you turn auditing on or off</span></span>

- <span data-ttu-id="13884-114">U moet de rol Auditlogboeken toegewezen krijgen in Exchange Online auditing in of uit te schakelen in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="13884-114">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="13884-115">Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheer  en Organisatiebeheer op de pagina Machtigingen in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="13884-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="13884-116">Globale beheerders in Microsoft 365 zijn lid van de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="13884-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13884-117">Aan gebruikers moeten machtigingen zijn toegewezen in Exchange Online controle in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="13884-117">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="13884-118">Als u gebruikers de rol Auditlogboeken op de pagina Machtigingen in de Microsoft 365-compliancecentrum **toewijst,** kunnen ze de controle niet in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="13884-118">If you assign users the Audit Logs role on the **Permissions** page in the Microsoft 365 compliance center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="13884-119">De onderliggende cmdlet is namelijk een Exchange Online PowerShell-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="13884-119">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span>

- <span data-ttu-id="13884-120">Zie Het auditlogboek doorzoeken voor stapsgewijs instructies over het doorzoeken van het [auditlogboek.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="13884-120">For step-by-step instructions on searching the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="13884-121">Zie Aan de slag met Microsoft 365 Management [API's](/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie over Microsoft 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="13884-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="verify-the-auditing-status-for-your-organization"></a><span data-ttu-id="13884-122">De controlestatus voor uw organisatie controleren</span><span class="sxs-lookup"><span data-stu-id="13884-122">Verify the auditing status for your organization</span></span>

<span data-ttu-id="13884-123">Als u wilt controleren of auditing is ingeschakeld voor uw organisatie, kunt u de volgende opdracht uitvoeren in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="13884-123">To verify that auditing is turned on for your organization, you can run the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

<span data-ttu-id="13884-124">Een waarde van `True` voor de  _eigenschap UnifiedAuditLogIngestionEnabled_ geeft aan dat auditing is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="13884-124">A value of `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> <span data-ttu-id="13884-125">Een waarde van `False` geeft aan dat auditing niet is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="13884-125">A value of `False` indicates that auditing is not turned on.</span></span>

## <a name="turn-on-auditing"></a><span data-ttu-id="13884-126">Controle in- en uit-</span><span class="sxs-lookup"><span data-stu-id="13884-126">Turn on auditing</span></span>

<span data-ttu-id="13884-127">Als auditing niet is ingeschakeld voor uw organisatie, kunt u deze in de Microsoft 365-compliancecentrum of met behulp van Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13884-127">If auditing is not turned on for your organization, you can turn it on in the Microsoft 365 compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="13884-128">Het kan enkele uren duren nadat u de controle hebt in- of uitgevoerd voordat u resultaten kunt retourneren wanneer u in het auditlogboek zoekt.</span><span class="sxs-lookup"><span data-stu-id="13884-128">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="13884-129">Het compliancecentrum gebruiken om controle in te zetten</span><span class="sxs-lookup"><span data-stu-id="13884-129">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="13884-130">Ga naar <https://compliance.microsoft.com> en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="13884-130">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="13884-131">Klik in het linkernavigatiedeelvenster van Microsoft 365-compliancecentrum op **Controleren.**</span><span class="sxs-lookup"><span data-stu-id="13884-131">In the left navigation pane of the Microsoft 365 compliance center, click **Audit**.</span></span>

   <span data-ttu-id="13884-132">Als auditing niet is ingeschakeld voor uw organisatie, wordt er een banner weergegeven waarin u wordt gevraagd gebruikers- en beheerdersactiviteiten op te nemen.</span><span class="sxs-lookup"><span data-stu-id="13884-132">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Banner op de pagina Controle](../media/AuditingBanner.png)

3. <span data-ttu-id="13884-134">Klik op **de banner Start recording user and admin activity** banner.</span><span class="sxs-lookup"><span data-stu-id="13884-134">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="13884-135">Het kan tot 60 minuten duren voordat de wijziging van kracht wordt.</span><span class="sxs-lookup"><span data-stu-id="13884-135">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="13884-136">PowerShell gebruiken om controle in te zetten</span><span class="sxs-lookup"><span data-stu-id="13884-136">Use PowerShell to turn on auditing</span></span>

1. <span data-ttu-id="13884-137">[Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="13884-137">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="13884-138">Voer de volgende PowerShell-opdracht uit om auditing in te zetten.</span><span class="sxs-lookup"><span data-stu-id="13884-138">Run the following PowerShell command to turn on auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="13884-139">Er wordt een bericht weergegeven met de melding dat het tot 60 minuten kan duren voordat de wijziging van kracht wordt.</span><span class="sxs-lookup"><span data-stu-id="13884-139">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="13884-140">Controle uitschakelen</span><span class="sxs-lookup"><span data-stu-id="13884-140">Turn off auditing</span></span>

<span data-ttu-id="13884-141">U moet de Exchange Online PowerShell gebruiken om auditing uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="13884-141">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. <span data-ttu-id="13884-142">[Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="13884-142">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="13884-143">Voer de volgende PowerShell-opdracht uit om auditing uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="13884-143">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="13884-144">Controleer na een tijdje of de controle is uitgeschakeld (uitgeschakeld).</span><span class="sxs-lookup"><span data-stu-id="13884-144">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="13884-145">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="13884-145">There are two ways to do this:</span></span>

    - <span data-ttu-id="13884-146">Voer Exchange Online PowerShell de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="13884-146">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="13884-147">De waarde van  `False` voor de  _eigenschap UnifiedAuditLogIngestionEnabled_ geeft aan dat auditing is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="13884-147">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="13884-148">Ga naar de **pagina Audit** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="13884-148">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="13884-149">Als auditing niet is ingeschakeld voor uw organisatie, wordt er een banner weergegeven waarin u wordt gevraagd gebruikers- en beheerdersactiviteiten op te nemen.</span><span class="sxs-lookup"><span data-stu-id="13884-149">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
