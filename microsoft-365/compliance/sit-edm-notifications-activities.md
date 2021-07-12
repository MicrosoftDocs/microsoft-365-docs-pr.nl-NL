---
title: Meldingen maken voor activiteiten met exacte gegevensovereenkomst
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Leer hoe u meldingen maakt voor activiteiten met exacte gegevensovereenkomst.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 263dc319d7e7d3ee5f12ebe374e8f5bd44c4cc8c
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341674"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="cb875-103">Meldingen maken voor activiteiten met exacte gegevensovereenkomst</span><span class="sxs-lookup"><span data-stu-id="cb875-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="cb875-104">Wanneer u [aangepaste typen gevoelige informatie maakt met exacte gegevensovereenkomst (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), zijn er een aantal activiteiten die in het [auditlogboek](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log) worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="cb875-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).</span></span> <span data-ttu-id="cb875-105">U kunt de PowerShell-cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) gebruiken om meldingen te maken die u laten weten wanneer deze activiteiten plaatsvinden:</span><span class="sxs-lookup"><span data-stu-id="cb875-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="cb875-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="cb875-106">CreateSchema</span></span>
- <span data-ttu-id="cb875-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="cb875-107">EditSchema</span></span>
- <span data-ttu-id="cb875-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="cb875-108">RemoveSchema</span></span>
- <span data-ttu-id="cb875-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="cb875-109">UploadDataFailed</span></span>
- <span data-ttu-id="cb875-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="cb875-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="cb875-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="cb875-111">Pre-requisites</span></span>

<span data-ttu-id="cb875-112">Het account dat u gebruikt, moet een van de volgende zijn:</span><span class="sxs-lookup"><span data-stu-id="cb875-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="cb875-113">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="cb875-113">a global admin</span></span>
- <span data-ttu-id="cb875-114">compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="cb875-114">compliance administrator</span></span>
- <span data-ttu-id="cb875-115">Exchange Online-beheerder</span><span class="sxs-lookup"><span data-stu-id="cb875-115">Exchange Online administrator</span></span>

<span data-ttu-id="cb875-116">Zie [Machtigingen](data-loss-prevention-policies.md#permissions) voor meer informatie over DLP-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="cb875-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="cb875-117">EDM-classificatie is inbegrepen in deze abonnementen:</span><span class="sxs-lookup"><span data-stu-id="cb875-117">EDM-based classification is included in these subscriptions:</span></span>

- <span data-ttu-id="cb875-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="cb875-118">Office 365 E5</span></span>
- <span data-ttu-id="cb875-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cb875-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="cb875-120">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="cb875-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="cb875-121">Microsoft E5/A5 Gegevensbeveiliging en -beheer</span><span class="sxs-lookup"><span data-stu-id="cb875-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="cb875-122">Zie [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance voor meer informatie over DLP-licenties](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="cb875-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="cb875-123">Meldingen configureren voor EDM-activiteiten</span><span class="sxs-lookup"><span data-stu-id="cb875-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="cb875-124">Verbinding maken met [PowerShell voor het Beveiligings- en compliancecentrum.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="cb875-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="cb875-125">Voer de cmdlet `New-ProtectionAlert` uit met behulp van de activiteit waarvoor u de melding wilt maken.</span><span class="sxs-lookup"><span data-stu-id="cb875-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="cb875-126">Als u bijvoorbeeld een melding wilt ontvangen wanneer de actie **UploadDataCompleted** heeft plaatsgevonden, gebruikt u:</span><span class="sxs-lookup"><span data-stu-id="cb875-126">For example, if you want to be notified when the **UploadDataCompleted** action occurred, run:</span></span>

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    <span data-ttu-id="cb875-127">voor de **UploadDataFailed** gebruikt u:</span><span class="sxs-lookup"><span data-stu-id="cb875-127">for the **UploadDataFailed** you can run:</span></span>
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a><span data-ttu-id="cb875-128">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="cb875-128">Related articles</span></span>

- [<span data-ttu-id="cb875-129">Aangepaste typen gevoelige informatie maken met exacte gegevensovereenkomsten (EDM)</span><span class="sxs-lookup"><span data-stu-id="cb875-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="cb875-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="cb875-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert)