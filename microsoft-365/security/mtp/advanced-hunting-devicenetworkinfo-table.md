---
title: DeviceNetworkInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over Netwerkconfiguratiegegevens in de tabel DeviceNetworkInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, machinenetworkinfo, DeviceNetworkInfo, apparaat, computer, Mac, IP, adapter, computer, Mac, IP, adapter, DNS, DHCP, gateway, tunnel
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 05812ec1c747c019bdba1c7ecffc2b33bd5f793a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413876"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="f816a-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="f816a-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f816a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f816a-105">**Applies to:**</span></span>
- <span data-ttu-id="f816a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f816a-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="f816a-107">De `DeviceNetworkInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over de netwerkconfiguratie van machines, waaronder netwerkadapters, IP-adressen en MAC-adressen, en verbonden netwerken of domeinen.</span><span class="sxs-lookup"><span data-stu-id="f816a-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="f816a-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="f816a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f816a-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="f816a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f816a-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="f816a-110">Column name</span></span> | <span data-ttu-id="f816a-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="f816a-111">Data type</span></span> | <span data-ttu-id="f816a-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f816a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f816a-113">tijd</span><span class="sxs-lookup"><span data-stu-id="f816a-113">datetime</span></span> | <span data-ttu-id="f816a-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="f816a-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f816a-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-115">string</span></span> | <span data-ttu-id="f816a-116">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="f816a-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f816a-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-117">string</span></span> | <span data-ttu-id="f816a-118">FQDN-naam (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="f816a-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="f816a-119">lang</span><span class="sxs-lookup"><span data-stu-id="f816a-119">long</span></span> | <span data-ttu-id="f816a-120">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="f816a-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f816a-121">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de naam van het apparaat en de timestamp-kolommen.</span><span class="sxs-lookup"><span data-stu-id="f816a-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="f816a-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-122">string</span></span> | <span data-ttu-id="f816a-123">Naam van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="f816a-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="f816a-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-124">string</span></span> | <span data-ttu-id="f816a-125">MAC-adres van de netwerkadapter</span><span class="sxs-lookup"><span data-stu-id="f816a-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="f816a-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-126">string</span></span> | <span data-ttu-id="f816a-127">Type netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="f816a-127">Network adapter type.</span></span> <span data-ttu-id="f816a-128">Voor de mogelijke waarden raadpleegt u [deze inventarisatie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="f816a-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="f816a-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-129">string</span></span> | <span data-ttu-id="f816a-130">De operationele status van de netwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="f816a-130">Operational status of the network adapter.</span></span> <span data-ttu-id="f816a-131">Voor de mogelijke waarden raadpleegt u [deze inventarisatie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="f816a-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="f816a-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-132">string</span></span> | <span data-ttu-id="f816a-133">Protocol voor tunneling, als de interface voor dit doel wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH</span><span class="sxs-lookup"><span data-stu-id="f816a-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="f816a-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-134">string</span></span> | <span data-ttu-id="f816a-135">Netwerken waarmee de adapter is verbonden.</span><span class="sxs-lookup"><span data-stu-id="f816a-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="f816a-136">Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag waarmee wordt aangegeven of de verbinding openbaar met internet is verbonden.</span><span class="sxs-lookup"><span data-stu-id="f816a-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="f816a-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-137">string</span></span> | <span data-ttu-id="f816a-138">DNS-serveradressen in JSON-matrix indeling</span><span class="sxs-lookup"><span data-stu-id="f816a-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="f816a-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-139">string</span></span> | <span data-ttu-id="f816a-140">IPv4-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="f816a-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="f816a-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-141">string</span></span> | <span data-ttu-id="f816a-142">IPv6-adres van DHCP-server</span><span class="sxs-lookup"><span data-stu-id="f816a-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="f816a-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-143">string</span></span> | <span data-ttu-id="f816a-144">Standaardgatewayadressen in de JSON-matrix indeling</span><span class="sxs-lookup"><span data-stu-id="f816a-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="f816a-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f816a-145">string</span></span> | <span data-ttu-id="f816a-146">JSON-matrix met alle IP-adressen die zijn toegewezen aan de adapter, samen met hun bijbehorende subnet prefix en IP-adresruimte, zoals openbaar, privé, of link-local</span><span class="sxs-lookup"><span data-stu-id="f816a-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f816a-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f816a-147">Related topics</span></span>
- [<span data-ttu-id="f816a-148">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f816a-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f816a-149">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f816a-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f816a-150">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="f816a-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f816a-151">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="f816a-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f816a-152">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f816a-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f816a-153">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="f816a-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
