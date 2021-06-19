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
ms.openlocfilehash: 15aa8f2bda76d56d3e35af8e884193193bb78d40
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007559"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="c2954-103">Meldingen maken voor activiteiten met exacte gegevensovereenkomst</span><span class="sxs-lookup"><span data-stu-id="c2954-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="c2954-104">Wanneer u [aangepaste typen gevoelige informatie maakt met exacte gegevensovereenkomst (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), zijn er een aantal activiteiten die in het [auditlogboek](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c2954-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="c2954-105">U kunt de PowerShell-cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) gebruiken om meldingen te maken die u laten weten wanneer deze activiteiten plaatsvinden:</span><span class="sxs-lookup"><span data-stu-id="c2954-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="c2954-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="c2954-106">CreateSchema</span></span>
- <span data-ttu-id="c2954-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="c2954-107">EditSchema</span></span>
- <span data-ttu-id="c2954-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="c2954-108">RemoveSchema</span></span>
- <span data-ttu-id="c2954-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="c2954-109">UploadDataFailed</span></span>
- <span data-ttu-id="c2954-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="c2954-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="c2954-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="c2954-111">Pre-requisites</span></span>

<span data-ttu-id="c2954-112">Het account dat u gebruikt, moet een van de volgende zijn:</span><span class="sxs-lookup"><span data-stu-id="c2954-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="c2954-113">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="c2954-113">a global admin</span></span>
- <span data-ttu-id="c2954-114">compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="c2954-114">compliance administrator</span></span>
- <span data-ttu-id="c2954-115">Exchange Online-beheerder</span><span class="sxs-lookup"><span data-stu-id="c2954-115">Exchange Online administrator</span></span>

<span data-ttu-id="c2954-116">Zie [Machtigingen](data-loss-prevention-policies.md#permissions) voor meer informatie over DLP-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="c2954-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="c2954-117">EDM-gebaseerde classificatie is inbegrepen in deze abonnementen</span><span class="sxs-lookup"><span data-stu-id="c2954-117">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="c2954-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c2954-118">Office 365 E5</span></span>
- <span data-ttu-id="c2954-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c2954-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="c2954-120">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="c2954-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="c2954-121">Microsoft E5/A5 Gegevensbeveiliging en -beheer</span><span class="sxs-lookup"><span data-stu-id="c2954-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="c2954-122">Zie [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) voor meer informatie over DLP-licenties.</span><span class="sxs-lookup"><span data-stu-id="c2954-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="c2954-123">Meldingen configureren voor EDM-activiteiten</span><span class="sxs-lookup"><span data-stu-id="c2954-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="c2954-124">Verbinding maken met [PowerShell voor het Beveiligings- en compliancecentrum](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="c2954-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="c2954-125">Voer de cmdlet `New-ProtectionAlert` uit met behulp van de activiteit waarvoor u de melding wilt maken.</span><span class="sxs-lookup"><span data-stu-id="c2954-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="c2954-126">Als u bijvoorbeeld een melding wilt ontvangen wanneer de actie **UploadDataCompleted** heeft plaatsgevonden, gebruikt u</span><span class="sxs-lookup"><span data-stu-id="c2954-126">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="c2954-127">voor de **UploadDataFailed** gebruikt u</span><span class="sxs-lookup"><span data-stu-id="c2954-127">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="c2954-128">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="c2954-128">Related articles</span></span>

- [<span data-ttu-id="c2954-129">Aangepaste typen gevoelige informatie maken met exacte gegevensovereenkomsten (EDM)</span><span class="sxs-lookup"><span data-stu-id="c2954-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="c2954-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="c2954-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert?view=exchange-ps)