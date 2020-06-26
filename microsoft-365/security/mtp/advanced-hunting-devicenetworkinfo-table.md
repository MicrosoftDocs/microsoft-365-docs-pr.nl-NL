---
title: DeviceNetworkInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over netwerkconfiguratie-informatie in de tabel DeviceNetworkInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, datatype, beschrijving, machinenetworkinfo, DeviceNetworkInfo, apparaat, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel
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
ms.openlocfilehash: 0fd6000f4d3a4b9fafb0eede74cbbe4e6c3d494e
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899241"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="68754-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="68754-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="68754-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="68754-105">**Applies to:**</span></span>
- <span data-ttu-id="68754-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="68754-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="68754-107">De `DeviceNetworkInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over netwerkconfiguratie van machines, waaronder netwerkadapters, IP- en MAC-adressen en verbonden netwerken of domeinen.</span><span class="sxs-lookup"><span data-stu-id="68754-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="68754-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="68754-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="68754-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="68754-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="68754-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="68754-110">Column name</span></span> | <span data-ttu-id="68754-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="68754-111">Data type</span></span> | <span data-ttu-id="68754-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="68754-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="68754-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="68754-113">datetime</span></span> | <span data-ttu-id="68754-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="68754-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="68754-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-115">string</span></span> | <span data-ttu-id="68754-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="68754-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="68754-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-117">string</span></span> | <span data-ttu-id="68754-118">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="68754-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="68754-119">Lange</span><span class="sxs-lookup"><span data-stu-id="68754-119">long</span></span> | <span data-ttu-id="68754-120">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="68754-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="68754-121">Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="68754-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="68754-122">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-122">string</span></span> | <span data-ttu-id="68754-123">Naam van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="68754-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="68754-124">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-124">string</span></span> | <span data-ttu-id="68754-125">MAC-adres van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="68754-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="68754-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-126">string</span></span> | <span data-ttu-id="68754-127">Type netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="68754-127">Network adapter type.</span></span> <span data-ttu-id="68754-128">Voor de mogelijke waarden, verwijzen naar [deze opsoming](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="68754-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="68754-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-129">string</span></span> | <span data-ttu-id="68754-130">Operationele status van de netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="68754-130">Operational status of the network adapter.</span></span> <span data-ttu-id="68754-131">Voor de mogelijke waarden, verwijzen naar [deze opsoming](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="68754-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="68754-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-132">string</span></span> | <span data-ttu-id="68754-133">Tunnelingprotocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH</span><span class="sxs-lookup"><span data-stu-id="68754-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="68754-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-134">string</span></span> | <span data-ttu-id="68754-135">Netwerken waarmee de adapter is verbonden.</span><span class="sxs-lookup"><span data-stu-id="68754-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="68754-136">Elke JSON-array bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="68754-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="68754-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-137">string</span></span> | <span data-ttu-id="68754-138">DNS-serveradressen in JSON-arrayindeling</span><span class="sxs-lookup"><span data-stu-id="68754-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="68754-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-139">string</span></span> | <span data-ttu-id="68754-140">IPv4-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="68754-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="68754-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-141">string</span></span> | <span data-ttu-id="68754-142">IPv6-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="68754-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="68754-143">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-143">string</span></span> | <span data-ttu-id="68754-144">Standaardgatewayadressen in JSON-arrayindeling</span><span class="sxs-lookup"><span data-stu-id="68754-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="68754-145">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="68754-145">string</span></span> | <span data-ttu-id="68754-146">JSON-array met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectieve subnetvoorvoegsel en IP-adresruimte, zoals openbaar, privé of linklokal</span><span class="sxs-lookup"><span data-stu-id="68754-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="68754-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="68754-147">Related topics</span></span>
- [<span data-ttu-id="68754-148">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="68754-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="68754-149">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="68754-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="68754-150">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="68754-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="68754-151">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="68754-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="68754-152">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="68754-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="68754-153">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="68754-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
