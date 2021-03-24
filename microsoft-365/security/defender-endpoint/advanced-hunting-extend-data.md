---
title: Geavanceerde dekking voor jagen uitbreiden met de juiste instellingen
description: Controleer de controle-instellingen op Windows-apparaten en andere instellingen om ervoor te zorgen dat u de meest uitgebreide gegevens krijgt in geavanceerde jacht
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: 60e8710415e328d06fac4c02e428094e5e4bcc92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059993"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="96e66-104">Geavanceerde dekking voor jagen uitbreiden met de juiste instellingen</span><span class="sxs-lookup"><span data-stu-id="96e66-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="96e66-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="96e66-105">**Applies to:**</span></span>
- [<span data-ttu-id="96e66-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="96e66-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="96e66-107">[Geavanceerde jacht](advanced-hunting-overview.md) is afhankelijk van gegevens die afkomstig zijn uit uw hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="96e66-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="96e66-108">Als u de meest uitgebreide gegevens wilt krijgen, moet u ervoor zorgen dat u de juiste instellingen hebt in de bijbehorende gegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="96e66-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="96e66-109">Geavanceerde beveiligingsaudits op Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="96e66-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="96e66-110">Schakel deze geavanceerde controle-instellingen in om ervoor te zorgen dat u gegevens krijgt over activiteiten op uw apparaten, zoals lokaal accountbeheer, lokaal beveiligingsgroepbeheer en het maken van service.</span><span class="sxs-lookup"><span data-stu-id="96e66-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="96e66-111">Data</span><span class="sxs-lookup"><span data-stu-id="96e66-111">Data</span></span> | <span data-ttu-id="96e66-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="96e66-112">Description</span></span> | <span data-ttu-id="96e66-113">Schematabel</span><span class="sxs-lookup"><span data-stu-id="96e66-113">Schema table</span></span> | <span data-ttu-id="96e66-114">Configureren</span><span class="sxs-lookup"><span data-stu-id="96e66-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="96e66-115">Accountbeheer</span><span class="sxs-lookup"><span data-stu-id="96e66-115">Account management</span></span> | <span data-ttu-id="96e66-116">Gebeurtenissen die zijn vastgelegd als verschillende waarden die het maken, verwijderen en `ActionType` andere accountgerelateerde activiteiten aangeven</span><span class="sxs-lookup"><span data-stu-id="96e66-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="96e66-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="96e66-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="96e66-118">- Een geavanceerd beveiligingsauditbeleid implementeren: [Gebruikersaccountbeheer controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="96e66-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="96e66-119">- [Meer informatie over geavanceerd beveiligingsauditbeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="96e66-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="96e66-120">Beveiligingsgroepsbeheer</span><span class="sxs-lookup"><span data-stu-id="96e66-120">Security group management</span></span> | <span data-ttu-id="96e66-121">Gebeurtenissen die zijn vastgelegd als verschillende waarden die het maken van `ActionType` lokale beveiligingsgroepen en andere lokale activiteiten voor groepsbeheer aangeven</span><span class="sxs-lookup"><span data-stu-id="96e66-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="96e66-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="96e66-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="96e66-123">- Een geavanceerd beveiligingsauditbeleid implementeren: [Beveiligingsgroepsbeheer controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="96e66-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="96e66-124">- [Meer informatie over geavanceerd beveiligingsauditbeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="96e66-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="96e66-125">Service-installatie</span><span class="sxs-lookup"><span data-stu-id="96e66-125">Service installation</span></span> | <span data-ttu-id="96e66-126">Gebeurtenissen die zijn vastgelegd met de waarde, waarmee wordt `ActionType` aangegeven dat er een service is `ServiceInstalled` gemaakt</span><span class="sxs-lookup"><span data-stu-id="96e66-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="96e66-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="96e66-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="96e66-128">- Een geavanceerd beveiligingsauditbeleid implementeren: [Systeemextensie voor auditbeveiliging](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="96e66-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="96e66-129">- [Meer informatie over geavanceerd beveiligingsauditbeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="96e66-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="96e66-130">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="96e66-130">Related topics</span></span>

- [<span data-ttu-id="96e66-131">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="96e66-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="96e66-132">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="96e66-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="96e66-133">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="96e66-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="96e66-134">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="96e66-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="96e66-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="96e66-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="96e66-136">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="96e66-136">Custom detections overview</span></span>](overview-custom-detections.md)
