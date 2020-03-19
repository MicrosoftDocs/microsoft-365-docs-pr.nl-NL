---
title: DeviceNetworkInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over netwerkconfiguratie-informatie in de tabel DeviceNetworkInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, machinenetworkinfo, DeviceNetworkInfo, apparaat, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: ce392ee074327114b0794edfeef9eb83091447d6
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42812073"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="b848d-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="b848d-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="b848d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b848d-105">**Applies to:**</span></span>
- <span data-ttu-id="b848d-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="b848d-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="b848d-107">De `DeviceNetworkInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over netwerkconfiguratie van machines, waaronder netwerkadapters, IP- en MAC-adressen en verbonden netwerken of domeinen.</span><span class="sxs-lookup"><span data-stu-id="b848d-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="b848d-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="b848d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b848d-109">Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b848d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b848d-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b848d-110">Column name</span></span> | <span data-ttu-id="b848d-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b848d-111">Data type</span></span> | <span data-ttu-id="b848d-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b848d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b848d-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="b848d-113">datetime</span></span> | <span data-ttu-id="b848d-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="b848d-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b848d-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-115">string</span></span> | <span data-ttu-id="b848d-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="b848d-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b848d-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-117">string</span></span> | <span data-ttu-id="b848d-118">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="b848d-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="b848d-119">Lange</span><span class="sxs-lookup"><span data-stu-id="b848d-119">long</span></span> | <span data-ttu-id="b848d-120">Gebeurtenis-id op basis van een herhalingsteller.</span><span class="sxs-lookup"><span data-stu-id="b848d-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b848d-121">Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="b848d-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="b848d-122">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-122">string</span></span> | <span data-ttu-id="b848d-123">Naam van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="b848d-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="b848d-124">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-124">string</span></span> | <span data-ttu-id="b848d-125">MAC-adres van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="b848d-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="b848d-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-126">string</span></span> | <span data-ttu-id="b848d-127">Type netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="b848d-127">Network adapter type.</span></span> <span data-ttu-id="b848d-128">Voor de mogelijke waarden, verwijzen wij u naar [deze opsomming](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="b848d-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="b848d-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-129">string</span></span> | <span data-ttu-id="b848d-130">Operationele status van de netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="b848d-130">Operational status of the network adapter.</span></span> <span data-ttu-id="b848d-131">Voor de mogelijke waarden, verwijzen wij u naar [deze opsomming](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="b848d-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="b848d-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-132">string</span></span> | <span data-ttu-id="b848d-133">Tunnelingprotocol, als de interface voor dit doel wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH</span><span class="sxs-lookup"><span data-stu-id="b848d-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="b848d-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-134">string</span></span> | <span data-ttu-id="b848d-135">Netwerken waarmee de adapter is verbonden.</span><span class="sxs-lookup"><span data-stu-id="b848d-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="b848d-136">Elke JSON-array bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="b848d-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="b848d-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-137">string</span></span> | <span data-ttu-id="b848d-138">DNS-serveradressen in JSON-arrayindeling</span><span class="sxs-lookup"><span data-stu-id="b848d-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="b848d-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-139">string</span></span> | <span data-ttu-id="b848d-140">IPv4-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="b848d-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="b848d-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-141">string</span></span> | <span data-ttu-id="b848d-142">IPv6-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="b848d-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="b848d-143">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-143">string</span></span> | <span data-ttu-id="b848d-144">Standaardgatewayadressen in JSON-arrayindeling</span><span class="sxs-lookup"><span data-stu-id="b848d-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="b848d-145">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b848d-145">string</span></span> | <span data-ttu-id="b848d-146">JSON-array met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectieve subnetvoorvoegsel- en IP-adresruimte, zoals openbare, particuliere of link-lokale</span><span class="sxs-lookup"><span data-stu-id="b848d-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b848d-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b848d-147">Related topics</span></span>
- [<span data-ttu-id="b848d-148">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="b848d-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b848d-149">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b848d-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b848d-150">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="b848d-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b848d-151">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="b848d-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b848d-152">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="b848d-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b848d-153">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="b848d-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
