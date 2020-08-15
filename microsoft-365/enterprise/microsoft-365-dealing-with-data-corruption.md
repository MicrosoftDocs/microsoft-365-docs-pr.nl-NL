---
title: Microsoft 365 omgaan met gegevensbeschadiging
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In dit artikel worden de beschadigde gegevens in Microsoft 365 besproken en de inspanningen van Microsoft getroffen om gegevens te voorkomen en te herstellen.
ms.openlocfilehash: fabecf8e368813e2f895669edc19c3f74e305c35
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689137"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a><span data-ttu-id="c7a50-103">Omgaan met gegevensbeschadiging in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c7a50-103">Dealing with Data Corruption in Microsoft 365</span></span>

<span data-ttu-id="c7a50-104">Een van de problematische aspecten van het uitvoeren van een grootschalige cloudservice is het afhandelen van beschadigde gegevens, gelet op het grote volume van gegevens en onafhankelijke systemen.</span><span class="sxs-lookup"><span data-stu-id="c7a50-104">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems.</span></span> <span data-ttu-id="c7a50-105">Beschadigde gegevens kunnen worden veroorzaakt door:</span><span class="sxs-lookup"><span data-stu-id="c7a50-105">Data corruption can be caused by:</span></span>

- <span data-ttu-id="c7a50-106">Bugs van toepassingen of infrastructuur, waarbij sommige of alle toepassingsstatus beschadigd raken</span><span class="sxs-lookup"><span data-stu-id="c7a50-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span>
- <span data-ttu-id="c7a50-107">Hardwareproblemen die tot gegevensverlies leiden of een onvermogen om gegevens te lezen</span><span class="sxs-lookup"><span data-stu-id="c7a50-107">Hardware issues that result in lost data or an inability to read data</span></span>
- <span data-ttu-id="c7a50-108">Menselijke operationele fouten</span><span class="sxs-lookup"><span data-stu-id="c7a50-108">Human operational errors</span></span>
- <span data-ttu-id="c7a50-109">Kwaadwillende hackers en disgruntled-medewerkers</span><span class="sxs-lookup"><span data-stu-id="c7a50-109">Malicious hackers and disgruntled employees</span></span>
- <span data-ttu-id="c7a50-110">Incidenten in externe services die tot enig verlies van gegevens leiden</span><span class="sxs-lookup"><span data-stu-id="c7a50-110">Incidents in external services that result in some loss of data</span></span>

<span data-ttu-id="c7a50-111">Aangezien een hogere tolerantie voor de integriteit van gegevens minder gegevens veroorzaakt, heeft Microsoft ingebouwde beveiligingsmechanismen voor Microsoft 365 om te voorkomen dat een bestand wordt beschadigd, en systemen en processen waarmee wij gegevens kunnen herstellen.</span><span class="sxs-lookup"><span data-stu-id="c7a50-111">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Microsoft 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does.</span></span> <span data-ttu-id="c7a50-112">Er bestaan controles en processen binnen de verschillende fasen van het updateproces voor de ontwikkeling van de productiviteit tegen beschadiging van gegevens, waaronder:</span><span class="sxs-lookup"><span data-stu-id="c7a50-112">Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>

- <span data-ttu-id="c7a50-113">Systeemontwerp</span><span class="sxs-lookup"><span data-stu-id="c7a50-113">System Design</span></span>
- <span data-ttu-id="c7a50-114">Code organisatie en structuur</span><span class="sxs-lookup"><span data-stu-id="c7a50-114">Code organization and structure</span></span>
- <span data-ttu-id="c7a50-115">Code beoordeling</span><span class="sxs-lookup"><span data-stu-id="c7a50-115">Code review</span></span>
- <span data-ttu-id="c7a50-116">Unit tests, integratie tests en systeemtests</span><span class="sxs-lookup"><span data-stu-id="c7a50-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="c7a50-117">Tests/poorten voor reis draden</span><span class="sxs-lookup"><span data-stu-id="c7a50-117">Trip wires tests/gates</span></span>

<span data-ttu-id="c7a50-118">In Microsoft 365-productieomgevingen zorgt peer replicatie tussen datacenters ervoor dat er altijd meerdere Live kopieën van gegevens zijn.</span><span class="sxs-lookup"><span data-stu-id="c7a50-118">Within Microsoft 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data.</span></span> <span data-ttu-id="c7a50-119">Standaardafbeeldingen en scripts worden gebruikt om verloren servers te herstellen, en gerepliceerde gegevens worden gebruikt om klantgegevens te herstellen.</span><span class="sxs-lookup"><span data-stu-id="c7a50-119">Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data.</span></span> <span data-ttu-id="c7a50-120">Vanwege de ingebouwde gegevens tolerantie controles en-processen worden in Microsoft reservekopieën van Microsoft 365 Information System Documentation (waaronder documentatie voor beveiliging) bijgehouden, met behulp van de ingebouwde replicatie in SharePoint Online en ons programma voor interne code-opslag, bron depot.</span><span class="sxs-lookup"><span data-stu-id="c7a50-120">Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Microsoft 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot.</span></span> <span data-ttu-id="c7a50-121">Systeemdocumentatie wordt opgeslagen in SharePoint Online en bron depot bevat systeem-en toepassings afbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="c7a50-121">System documentation is stored in SharePoint Online, and Source Depot contains system and application images.</span></span> <span data-ttu-id="c7a50-122">Zowel SharePoint Online als bron-depot gebruiken versiebeheer en worden in de nabije werkelijke termijn gerepliceerd.</span><span class="sxs-lookup"><span data-stu-id="c7a50-122">Both SharePoint Online and Source Depot use versioning and are replicated in near real time.</span></span>
