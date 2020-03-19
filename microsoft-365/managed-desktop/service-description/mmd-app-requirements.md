---
title: Vereisten voor Microsoft Managed Desktop-apps
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 01c580cd671a84ef68c18b114e133f046a3e5b3b
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/28/2020
ms.locfileid: "42812017"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="92662-103">Vereisten voor Microsoft Managed Desktop-apps</span><span class="sxs-lookup"><span data-stu-id="92662-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="92662-104">Om de prestaties, betrouwbaarheid en bruikbaarheid van Microsoft Managed Desktop-apparaten te garanderen, mag de zakelijke app van een klant geen ernstige invloed hebben op de gebruikerservaring of de beveiligingshouding wijzigen.</span><span class="sxs-lookup"><span data-stu-id="92662-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="92662-105">Daarom moeten de zakelijke toepassingen die u wilt implementeren naar Microsoft Managed Desktop-apparaten voldoen aan de vereisten in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="92662-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="92662-106">Toepassingsvoorwaarde</span><span class="sxs-lookup"><span data-stu-id="92662-106">Application condition</span></span>

<span data-ttu-id="92662-107">Het is belangrijk dat toepassingen geen negatieve invloed hebben op de Microsoft Managed Desktop-omgeving.</span><span class="sxs-lookup"><span data-stu-id="92662-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="92662-108">Hieronder volgen de vereisten waaraan een toepassing moet voldoen om een toepassing te kunnen implementeren.</span><span class="sxs-lookup"><span data-stu-id="92662-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="92662-109">Voor een bepaalde toepassing of stuurprogramma kan Microsoft afzien van de hierin vermelde eis.</span><span class="sxs-lookup"><span data-stu-id="92662-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="92662-110">Microsoft kan besluiten om een toepassing of stuurprogramma te verwijderen die een negatieve invloed heeft op de prestaties en betrouwbaarheid van Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="92662-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="92662-111">Centraal beheerde apps</span><span class="sxs-lookup"><span data-stu-id="92662-111">Centrally managed apps</span></span>

<span data-ttu-id="92662-112">Alle toepassingen en stuurprogramma's die op Microsoft Managed Devices zijn geïnstalleerd, moeten worden geïmplementeerd via Microsoft Intune, de Microsoft Store of de Microsoft Store voor Bedrijven. indien beschikbaar, worden stuurprogramma's ook geïmplementeerd via de Windows Update-service.</span><span class="sxs-lookup"><span data-stu-id="92662-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="92662-113">Verboden app-lessen</span><span class="sxs-lookup"><span data-stu-id="92662-113">Prohibited app classes</span></span>

<span data-ttu-id="92662-114">Bepaalde toepassingstypen zijn niet toegestaan op Microsoft Managed Desktop-apparaten:</span><span class="sxs-lookup"><span data-stu-id="92662-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="92662-115">Anti-virus-, beveiligings- of auditsoftware van derden</span><span class="sxs-lookup"><span data-stu-id="92662-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="92662-116">Versies van Microsoft Office voorafgaand aan Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="92662-116">Versions of Microsoft Office prior to Office 365 ProPlus</span></span>
- <span data-ttu-id="92662-117">Toepassingen die andere software van derden installeren of bundelen</span><span class="sxs-lookup"><span data-stu-id="92662-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="92662-118">Beperkt app-gedrag</span><span class="sxs-lookup"><span data-stu-id="92662-118">Restricted app behaviors</span></span>

<span data-ttu-id="92662-119">Bepaalde app-gedragkan een negatieve invloed hebben op de gebruikerservaring of een beveiligingsrisico vormen voor Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="92662-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="92662-120">Apps met het volgende gedrag mogen niet worden uitgevoerd in de Microsoft Managed Desktop-omgeving zonder een specifieke van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92662-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific  from Microsoft.</span></span>

<span data-ttu-id="92662-121">Gebruikerservaring:</span><span class="sxs-lookup"><span data-stu-id="92662-121">User Experience:</span></span>
- <span data-ttu-id="92662-122">Achtergrondservices installeren</span><span class="sxs-lookup"><span data-stu-id="92662-122">Install background services</span></span>
- <span data-ttu-id="92662-123">Zichzelf toevoegen aan het opstartpad van Windows</span><span class="sxs-lookup"><span data-stu-id="92662-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="92662-124">Toepassingen die afhankelijk zijn van stuurprogramma's</span><span class="sxs-lookup"><span data-stu-id="92662-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="92662-125">Webbrowsers van derden</span><span class="sxs-lookup"><span data-stu-id="92662-125">3rd party web browsers</span></span>

<span data-ttu-id="92662-126">Veiligheid:</span><span class="sxs-lookup"><span data-stu-id="92662-126">Security:</span></span>
- <span data-ttu-id="92662-127">De bevoegdheden van de eindgebruiker verhogen</span><span class="sxs-lookup"><span data-stu-id="92662-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="92662-128">Fungeren als app store of een ingebouwde extensiemanager</span><span class="sxs-lookup"><span data-stu-id="92662-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="92662-129">Hebben bekende beveiligingsproblemen</span><span class="sxs-lookup"><span data-stu-id="92662-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="92662-130">Toegang tot gegevens van eindgebruikers versleutelen of beperken</span><span class="sxs-lookup"><span data-stu-id="92662-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="92662-131">Is niet ondertekend of is ondertekend met behulp van een certificaat dat niet wordt oprollen naar een vertrouwde root</span><span class="sxs-lookup"><span data-stu-id="92662-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="92662-132">Stuurprogramma-implementatie</span><span class="sxs-lookup"><span data-stu-id="92662-132">Driver deployment</span></span>

<span data-ttu-id="92662-133">Microsoft Managed Desktop ondersteunt alleen apparaatstuurprogramma's die beschikbaar zijn via Windows Update of geïnstalleerdpostvak met het Microsoft Managed Device.</span><span class="sxs-lookup"><span data-stu-id="92662-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="92662-134">Als een toepassing vereist dat een specifiek stuurprogramma(s) wordt uitgevoerd, wordt dit beschouwd als een beperkte toepassing en is een uitzondering vereist voordat deze wordt geïmplementeerd op Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="92662-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exception before being deployed to Microsoft Managed Desktop.</span></span> 

