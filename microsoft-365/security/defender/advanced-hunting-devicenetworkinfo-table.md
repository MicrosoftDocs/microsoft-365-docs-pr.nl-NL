---
title: Tabel DeviceNetworkInfo in het geavanceerde schema voor de jacht
description: Meer informatie over netwerkconfiguratiegegevens in de tabel DeviceNetworkInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023187"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="01fa3-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="01fa3-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01fa3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="01fa3-105">**Applies to:**</span></span>
- <span data-ttu-id="01fa3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01fa3-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="01fa3-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="01fa3-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="01fa3-108">De tabel in het geavanceerde schema bevat informatie over netwerkconfiguratie van machines, zoals netwerkadapters, IP- en MAC-adressen en verbonden netwerken `DeviceNetworkInfo` of domeinen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="01fa3-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="01fa3-109">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="01fa3-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="01fa3-110">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="01fa3-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="01fa3-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="01fa3-111">Column name</span></span> | <span data-ttu-id="01fa3-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="01fa3-112">Data type</span></span> | <span data-ttu-id="01fa3-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="01fa3-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="01fa3-114">datetime</span><span class="sxs-lookup"><span data-stu-id="01fa3-114">datetime</span></span> | <span data-ttu-id="01fa3-115">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="01fa3-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="01fa3-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-116">string</span></span> | <span data-ttu-id="01fa3-117">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="01fa3-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="01fa3-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-118">string</span></span> | <span data-ttu-id="01fa3-119">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="01fa3-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="01fa3-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-120">string</span></span> | <span data-ttu-id="01fa3-121">Naam van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="01fa3-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="01fa3-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-122">string</span></span> | <span data-ttu-id="01fa3-123">MAC-adres van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="01fa3-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="01fa3-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-124">string</span></span> | <span data-ttu-id="01fa3-125">Type netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="01fa3-125">Network adapter type.</span></span> <span data-ttu-id="01fa3-126">Voor de mogelijke waarden raadpleegt u [deze enumeratie](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="01fa3-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="01fa3-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-127">string</span></span> | <span data-ttu-id="01fa3-128">Operationele status van de netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="01fa3-128">Operational status of the network adapter.</span></span> <span data-ttu-id="01fa3-129">Voor de mogelijke waarden raadpleegt u [deze enumeratie](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="01fa3-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="01fa3-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-130">string</span></span> | <span data-ttu-id="01fa3-131">Tunneling protocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH</span><span class="sxs-lookup"><span data-stu-id="01fa3-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="01fa3-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-132">string</span></span> | <span data-ttu-id="01fa3-133">Netwerken waar de adapter mee is verbonden.</span><span class="sxs-lookup"><span data-stu-id="01fa3-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="01fa3-134">Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="01fa3-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="01fa3-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-135">string</span></span> | <span data-ttu-id="01fa3-136">DNS-serveradressen in JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="01fa3-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="01fa3-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-137">string</span></span> | <span data-ttu-id="01fa3-138">IPv4-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="01fa3-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="01fa3-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-139">string</span></span> | <span data-ttu-id="01fa3-140">IPv6-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="01fa3-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="01fa3-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-141">string</span></span> | <span data-ttu-id="01fa3-142">Standaardgatewayadressen in JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="01fa3-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="01fa3-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="01fa3-143">string</span></span> | <span data-ttu-id="01fa3-144">JSON-matrix met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectievelijke subnet-voorvoegsel en IP-adresruimte, zoals openbaar, privé of link-local</span><span class="sxs-lookup"><span data-stu-id="01fa3-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="01fa3-145">lang</span><span class="sxs-lookup"><span data-stu-id="01fa3-145">long</span></span> | <span data-ttu-id="01fa3-146">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="01fa3-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="01fa3-147">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="01fa3-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="01fa3-148">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="01fa3-148">Related topics</span></span>
- [<span data-ttu-id="01fa3-149">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="01fa3-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01fa3-150">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="01fa3-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="01fa3-151">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="01fa3-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="01fa3-152">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="01fa3-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="01fa3-153">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="01fa3-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="01fa3-154">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="01fa3-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)