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
# <a name="create-notifications-for-exact-data-match-activities"></a>Meldingen maken voor activiteiten met exacte gegevensovereenkomst

Wanneer u [aangepaste typen gevoelige informatie maakt met exacte gegevensovereenkomst (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), zijn er een aantal activiteiten die in het [auditlogboek](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) worden gemaakt. U kunt de PowerShell-cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) gebruiken om meldingen te maken die u laten weten wanneer deze activiteiten plaatsvinden:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

## <a name="pre-requisites"></a>Vereisten

Het account dat u gebruikt, moet een van de volgende zijn:

- globale beheerder
- compliancebeheerder
- Exchange Online-beheerder

Zie [Machtigingen](data-loss-prevention-policies.md#permissions) voor meer informatie over DLP-machtigingen.

EDM-gebaseerde classificatie is inbegrepen in deze abonnementen

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft E5/A5 Gegevensbeveiliging en -beheer

Zie [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) voor meer informatie over DLP-licenties.

## <a name="configure-notifications-for-edm-activities"></a>Meldingen configureren voor EDM-activiteiten

1. Verbinding maken met [PowerShell voor het Beveiligings- en compliancecentrum](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps) 

2. Voer de cmdlet `New-ProtectionAlert` uit met behulp van de activiteit waarvoor u de melding wilt maken.  Als u bijvoorbeeld een melding wilt ontvangen wanneer de actie **UploadDataCompleted** heeft plaatsgevonden, gebruikt u

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

voor de **UploadDataFailed** gebruikt u

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a>Verwante artikelen

- [Aangepaste typen gevoelige informatie maken met exacte gegevensovereenkomsten (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps)