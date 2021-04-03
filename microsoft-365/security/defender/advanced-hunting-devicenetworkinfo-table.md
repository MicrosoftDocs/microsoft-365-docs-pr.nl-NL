---
title: Tabel DeviceNetworkInfo in het geavanceerde schema voor de jacht
description: Meer informatie over netwerkconfiguratiegegevens in de tabel DeviceNetworkInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: 6d860e20bdd116d579b3cb178e3352825c60fe44
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500905"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="8a030-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="8a030-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a030-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8a030-105">**Applies to:**</span></span>
- <span data-ttu-id="8a030-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a030-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="8a030-107">De tabel in het geavanceerde schema bevat informatie over netwerkconfiguratie van machines, zoals netwerkadapters, IP- en MAC-adressen en verbonden netwerken `DeviceNetworkInfo` of domeinen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8a030-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="8a030-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="8a030-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8a030-109">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="8a030-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8a030-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="8a030-110">Column name</span></span> | <span data-ttu-id="8a030-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8a030-111">Data type</span></span> | <span data-ttu-id="8a030-112">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="8a030-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8a030-113">datetime</span><span class="sxs-lookup"><span data-stu-id="8a030-113">datetime</span></span> | <span data-ttu-id="8a030-114">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="8a030-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8a030-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-115">string</span></span> | <span data-ttu-id="8a030-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="8a030-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8a030-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-117">string</span></span> | <span data-ttu-id="8a030-118">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="8a030-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="8a030-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-119">string</span></span> | <span data-ttu-id="8a030-120">Naam van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="8a030-120">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="8a030-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-121">string</span></span> | <span data-ttu-id="8a030-122">MAC-adres van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="8a030-122">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="8a030-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-123">string</span></span> | <span data-ttu-id="8a030-124">Type netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="8a030-124">Network adapter type.</span></span> <span data-ttu-id="8a030-125">Voor de mogelijke waarden raadpleegt u [deze enumeratie](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="8a030-125">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="8a030-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-126">string</span></span> | <span data-ttu-id="8a030-127">Operationele status van de netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="8a030-127">Operational status of the network adapter.</span></span> <span data-ttu-id="8a030-128">Voor de mogelijke waarden raadpleegt u [deze enumeratie](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="8a030-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="8a030-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-129">string</span></span> | <span data-ttu-id="8a030-130">Tunneling protocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH</span><span class="sxs-lookup"><span data-stu-id="8a030-130">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="8a030-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-131">string</span></span> | <span data-ttu-id="8a030-132">Netwerken waar de adapter mee is verbonden.</span><span class="sxs-lookup"><span data-stu-id="8a030-132">Networks that the adapter is connected to.</span></span> <span data-ttu-id="8a030-133">Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="8a030-133">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="8a030-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-134">string</span></span> | <span data-ttu-id="8a030-135">DNS-serveradressen in JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="8a030-135">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="8a030-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-136">string</span></span> | <span data-ttu-id="8a030-137">IPv4-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="8a030-137">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="8a030-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-138">string</span></span> | <span data-ttu-id="8a030-139">IPv6-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="8a030-139">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="8a030-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-140">string</span></span> | <span data-ttu-id="8a030-141">Standaardgatewayadressen in JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="8a030-141">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="8a030-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a030-142">string</span></span> | <span data-ttu-id="8a030-143">JSON-matrix met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectievelijke subnet-voorvoegsel en IP-adresruimte, zoals openbaar, privé of link-local</span><span class="sxs-lookup"><span data-stu-id="8a030-143">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="8a030-144">lang</span><span class="sxs-lookup"><span data-stu-id="8a030-144">long</span></span> | <span data-ttu-id="8a030-145">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="8a030-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8a030-146">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="8a030-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8a030-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8a030-147">Related topics</span></span>
- [<span data-ttu-id="8a030-148">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="8a030-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a030-149">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="8a030-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8a030-150">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="8a030-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8a030-151">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="8a030-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8a030-152">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="8a030-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8a030-153">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="8a030-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)