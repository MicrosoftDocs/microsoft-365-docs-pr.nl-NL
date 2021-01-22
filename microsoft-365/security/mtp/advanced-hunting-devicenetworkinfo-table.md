---
title: DeviceNetworkInfo-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over netwerkconfiguratiegegevens vindt u in de tabel DeviceNetworkInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, gateway, tunnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931204"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="a529e-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="a529e-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a529e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a529e-105">**Applies to:**</span></span>
- <span data-ttu-id="a529e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a529e-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="a529e-107">De tabel in het geavanceerde schema voor zoeken bevat informatie over de netwerkconfiguratie van computers, waaronder `DeviceNetworkInfo` netwerkadapters, IP- en MAC-adressen en verbonden netwerken [](advanced-hunting-overview.md) of domeinen.</span><span class="sxs-lookup"><span data-stu-id="a529e-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="a529e-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="a529e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a529e-109">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="a529e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a529e-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="a529e-110">Column name</span></span> | <span data-ttu-id="a529e-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="a529e-111">Data type</span></span> | <span data-ttu-id="a529e-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a529e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a529e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a529e-113">datetime</span></span> | <span data-ttu-id="a529e-114">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="a529e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a529e-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-115">string</span></span> | <span data-ttu-id="a529e-116">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="a529e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a529e-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-117">string</span></span> | <span data-ttu-id="a529e-118">FQDN (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="a529e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="a529e-119">lang</span><span class="sxs-lookup"><span data-stu-id="a529e-119">long</span></span> | <span data-ttu-id="a529e-120">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="a529e-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a529e-121">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen Apparaatnaam en Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="a529e-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="a529e-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-122">string</span></span> | <span data-ttu-id="a529e-123">Naam van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="a529e-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="a529e-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-124">string</span></span> | <span data-ttu-id="a529e-125">Mac-adres van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="a529e-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="a529e-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-126">string</span></span> | <span data-ttu-id="a529e-127">Type netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="a529e-127">Network adapter type.</span></span> <span data-ttu-id="a529e-128">Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="a529e-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="a529e-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-129">string</span></span> | <span data-ttu-id="a529e-130">De operationele status van de netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="a529e-130">Operational status of the network adapter.</span></span> <span data-ttu-id="a529e-131">Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="a529e-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="a529e-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-132">string</span></span> | <span data-ttu-id="a529e-133">Tunneling-protocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH</span><span class="sxs-lookup"><span data-stu-id="a529e-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="a529e-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-134">string</span></span> | <span data-ttu-id="a529e-135">Netwerken waar de adapter mee is verbonden.</span><span class="sxs-lookup"><span data-stu-id="a529e-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="a529e-136">Elke JSON-matrix bevat de netwerknaam, -categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="a529e-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="a529e-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-137">string</span></span> | <span data-ttu-id="a529e-138">DNS-serveradressen in JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="a529e-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="a529e-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-139">string</span></span> | <span data-ttu-id="a529e-140">IPv4-adres van SERVER</span><span class="sxs-lookup"><span data-stu-id="a529e-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="a529e-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-141">string</span></span> | <span data-ttu-id="a529e-142">IPv6-adres van SERVER SERVER</span><span class="sxs-lookup"><span data-stu-id="a529e-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="a529e-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-143">string</span></span> | <span data-ttu-id="a529e-144">Standaard gatewayadressen in JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="a529e-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="a529e-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a529e-145">string</span></span> | <span data-ttu-id="a529e-146">JSON-matrix met alle IP-adressen die aan de adapter zijn toegewezen, samen met het desbetreffende subnetnummer en de IP-adresruimte, zoals openbaar, privé of link-lokaal</span><span class="sxs-lookup"><span data-stu-id="a529e-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a529e-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a529e-147">Related topics</span></span>
- [<span data-ttu-id="a529e-148">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="a529e-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a529e-149">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="a529e-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a529e-150">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="a529e-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a529e-151">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="a529e-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a529e-152">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="a529e-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a529e-153">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="a529e-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
