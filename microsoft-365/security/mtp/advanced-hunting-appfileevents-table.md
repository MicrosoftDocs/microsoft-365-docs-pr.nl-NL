---
title: AppFileEvents tabel in het geavanceerde jachtschema
description: Meer informatie over bestandsgerelateerde gebeurtenissen die zijn gekoppeld aan cloud-apps en -services in de tabel AppFileEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, AppFileEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899337"
---
# <a name="appfileevents"></a><span data-ttu-id="66d90-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="66d90-104">AppFileEvents</span></span>

<span data-ttu-id="66d90-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="66d90-105">**Applies to:**</span></span>
- <span data-ttu-id="66d90-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66d90-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="66d90-107">De `AppFileEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over bestandsgerelateerde activiteiten in cloud-apps en -services die worden gecontroleerd door Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="66d90-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="66d90-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="66d90-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="66d90-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="66d90-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="66d90-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="66d90-110">Column name</span></span> | <span data-ttu-id="66d90-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="66d90-111">Data type</span></span> | <span data-ttu-id="66d90-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="66d90-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="66d90-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="66d90-113">datetime</span></span> | <span data-ttu-id="66d90-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="66d90-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="66d90-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-115">string</span></span> | <span data-ttu-id="66d90-116">Type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="66d90-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="66d90-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-117">string</span></span> | <span data-ttu-id="66d90-118">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="66d90-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="66d90-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-119">string</span></span> | <span data-ttu-id="66d90-120">Naam van het bestand waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="66d90-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="66d90-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-121">string</span></span> | <span data-ttu-id="66d90-122">Map met het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="66d90-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="66d90-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-123">string</span></span> | <span data-ttu-id="66d90-124">Oorspronkelijke naam van het bestand dat naar aanleiding van de actie is hernoemd</span><span class="sxs-lookup"><span data-stu-id="66d90-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="66d90-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-125">string</span></span> | <span data-ttu-id="66d90-126">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="66d90-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="66d90-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-127">string</span></span> | <span data-ttu-id="66d90-128">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="66d90-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="66d90-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-129">string</span></span> | <span data-ttu-id="66d90-130">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="66d90-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="66d90-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-131">string</span></span> | <span data-ttu-id="66d90-132">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="66d90-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="66d90-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-133">string</span></span> | <span data-ttu-id="66d90-134">Naam van de accountgebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="66d90-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="66d90-135">Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="66d90-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="66d90-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-136">string</span></span> | <span data-ttu-id="66d90-137">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="66d90-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="66d90-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="66d90-138">string</span></span> | <span data-ttu-id="66d90-139">Plaats, land of andere geografische locatie die aan het evenement is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="66d90-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="66d90-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="66d90-140">Related topics</span></span>
- [<span data-ttu-id="66d90-141">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="66d90-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="66d90-142">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="66d90-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="66d90-143">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="66d90-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="66d90-144">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="66d90-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="66d90-145">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="66d90-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="66d90-146">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="66d90-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
