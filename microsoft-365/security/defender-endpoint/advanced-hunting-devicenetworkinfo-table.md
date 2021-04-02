---
title: Tabel DeviceNetworkInfo in het geavanceerde schema voor de jacht
description: Meer informatie over netwerkconfiguratiegegevens in de tabel DeviceNetworkInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicenetworkinfo, device, device, mac, ip, adapter, dns, dhcp, gateway, tunnel, DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e63af4153804a09424c36fb03ac715da5f6d9485
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499142"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="b51ea-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="b51ea-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b51ea-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b51ea-105">**Applies to:**</span></span>
- [<span data-ttu-id="b51ea-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b51ea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="b51ea-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b51ea-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b51ea-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b51ea-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="b51ea-109">De tabel in het geavanceerde schema bevat informatie over netwerkconfiguratie van apparaten, zoals netwerkadapters, IP- en MAC-adressen en verbonden netwerken `DeviceNetworkInfo` of domeinen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b51ea-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="b51ea-110">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="b51ea-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b51ea-111">Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="b51ea-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="b51ea-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b51ea-112">Column name</span></span> | <span data-ttu-id="b51ea-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b51ea-113">Data type</span></span> | <span data-ttu-id="b51ea-114">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b51ea-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b51ea-115">datetime</span><span class="sxs-lookup"><span data-stu-id="b51ea-115">datetime</span></span> | <span data-ttu-id="b51ea-116">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="b51ea-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b51ea-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-117">string</span></span> | <span data-ttu-id="b51ea-118">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="b51ea-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b51ea-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-119">string</span></span> | <span data-ttu-id="b51ea-120">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="b51ea-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="b51ea-121">lang</span><span class="sxs-lookup"><span data-stu-id="b51ea-121">long</span></span> | <span data-ttu-id="b51ea-122">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="b51ea-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b51ea-123">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de `DeviceName` kolommen en `Timestamp` de kolommen</span><span class="sxs-lookup"><span data-stu-id="b51ea-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="b51ea-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-124">string</span></span> | <span data-ttu-id="b51ea-125">Naam van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="b51ea-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="b51ea-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-126">string</span></span> | <span data-ttu-id="b51ea-127">MAC-adres van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="b51ea-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="b51ea-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-128">string</span></span> | <span data-ttu-id="b51ea-129">Type netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="b51ea-129">Network adapter type.</span></span> <span data-ttu-id="b51ea-130">Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="b51ea-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="b51ea-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-131">string</span></span> | <span data-ttu-id="b51ea-132">Operationele status van de netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="b51ea-132">Operational status of the network adapter.</span></span> <span data-ttu-id="b51ea-133">Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="b51ea-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="b51ea-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-134">string</span></span> | <span data-ttu-id="b51ea-135">Tunneling protocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH</span><span class="sxs-lookup"><span data-stu-id="b51ea-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="b51ea-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-136">string</span></span> | <span data-ttu-id="b51ea-137">Netwerken waar de adapter mee is verbonden.</span><span class="sxs-lookup"><span data-stu-id="b51ea-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="b51ea-138">Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="b51ea-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="b51ea-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-139">string</span></span> | <span data-ttu-id="b51ea-140">DNS-serveradressen in JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="b51ea-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="b51ea-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-141">string</span></span> | <span data-ttu-id="b51ea-142">IPv4-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="b51ea-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="b51ea-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-143">string</span></span> | <span data-ttu-id="b51ea-144">IPv6-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="b51ea-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="b51ea-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-145">string</span></span> | <span data-ttu-id="b51ea-146">Standaardgatewayadressen in JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="b51ea-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="b51ea-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b51ea-147">string</span></span> | <span data-ttu-id="b51ea-148">JSON-matrix met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectievelijke subnet-voorvoegsel en IP-adresruimte, zoals openbaar, privé of link-local</span><span class="sxs-lookup"><span data-stu-id="b51ea-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b51ea-149">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b51ea-149">Related topics</span></span>
- [<span data-ttu-id="b51ea-150">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b51ea-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b51ea-151">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b51ea-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b51ea-152">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b51ea-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
