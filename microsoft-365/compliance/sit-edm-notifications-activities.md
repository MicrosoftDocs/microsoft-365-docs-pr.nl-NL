---
title: Meldingen maken voor activiteiten met exacte gegevensovereenkomst (preview)
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
ms.openlocfilehash: 2e2f67ef0f276211483519bd5e246e4e041b2b15
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161965"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="e6bb4-103">Meldingen maken voor activiteiten met exacte gegevensovereenkomst (preview)</span><span class="sxs-lookup"><span data-stu-id="e6bb4-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="e6bb4-104">Wanneer u [aangepaste typen gevoelige informatie maakt met exacte gegevensovereenkomst (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), zijn er een aantal activiteiten die in het [auditlogboek](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e6bb4-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="e6bb4-105">U kunt de PowerShell-cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) gebruiken om meldingen te maken die u laten weten wanneer deze activiteiten plaatsvinden:</span><span class="sxs-lookup"><span data-stu-id="e6bb4-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="e6bb4-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="e6bb4-106">CreateSchema</span></span>
- <span data-ttu-id="e6bb4-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="e6bb4-107">EditSchema</span></span>
- <span data-ttu-id="e6bb4-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="e6bb4-108">RemoveSchema</span></span>
- <span data-ttu-id="e6bb4-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="e6bb4-109">UploadDataFailed</span></span>
- <span data-ttu-id="e6bb4-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="e6bb4-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="e6bb4-111">De mogelijkheid om meldingen voor EDM-activiteiten te maken, is alleen beschikbaar voor de wereldwijde en GCC-cloud.</span><span class="sxs-lookup"><span data-stu-id="e6bb4-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="e6bb4-112">Vereisten</span><span class="sxs-lookup"><span data-stu-id="e6bb4-112">Pre-requisites</span></span>

<span data-ttu-id="e6bb4-113">Het account dat u gebruikt, moet een van de volgende zijn:</span><span class="sxs-lookup"><span data-stu-id="e6bb4-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="e6bb4-114">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="e6bb4-114">a global admin</span></span>
- <span data-ttu-id="e6bb4-115">compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="e6bb4-115">compliance administrator</span></span>
- <span data-ttu-id="e6bb4-116">Exchange Online-beheerder</span><span class="sxs-lookup"><span data-stu-id="e6bb4-116">Exchange Online administrator</span></span>

<span data-ttu-id="e6bb4-117">Zie [Machtigingen](data-loss-prevention-policies.md#permissions) voor meer informatie over DLP-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e6bb4-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="e6bb4-118">EDM-gebaseerde classificatie is inbegrepen in deze abonnementen</span><span class="sxs-lookup"><span data-stu-id="e6bb4-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="e6bb4-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e6bb4-119">Office 365 E5</span></span>
- <span data-ttu-id="e6bb4-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e6bb4-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="e6bb4-121">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="e6bb4-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="e6bb4-122">Microsoft E5/A5 Gegevensbeveiliging en -beheer</span><span class="sxs-lookup"><span data-stu-id="e6bb4-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="e6bb4-123">Zie [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) voor meer informatie over DLP-licenties.</span><span class="sxs-lookup"><span data-stu-id="e6bb4-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="e6bb4-124">Meldingen configureren voor EDM-activiteiten</span><span class="sxs-lookup"><span data-stu-id="e6bb4-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="e6bb4-125">Verbinding maken met [PowerShell voor het Beveiligings- en compliancecentrum](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="e6bb4-125">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="e6bb4-126">Voer de cmdlet `New-ProtectionAlert` uit met behulp van de activiteit waarvoor u de melding wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e6bb4-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="e6bb4-127">Als u bijvoorbeeld een melding wilt ontvangen wanneer de actie **UploadDataCompleted** heeft plaatsgevonden, gebruikt u</span><span class="sxs-lookup"><span data-stu-id="e6bb4-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="e6bb4-128">voor de **UploadDataFailed** gebruikt u</span><span class="sxs-lookup"><span data-stu-id="e6bb4-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="e6bb4-129">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e6bb4-129">Related articles</span></span>

- [<span data-ttu-id="e6bb4-130">Aangepaste typen gevoelige informatie maken met exacte gegevensovereenkomsten (EDM)</span><span class="sxs-lookup"><span data-stu-id="e6bb4-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="e6bb4-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="e6bb4-131">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert?view=exchange-ps)