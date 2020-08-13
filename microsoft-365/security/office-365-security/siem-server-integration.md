---
title: SIEM Server-integratie met Microsoft 365-Services en-toepassingen
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Een overzicht van beveiligings-en SIEM-Serverintegratie met Microsoft 365-cloudservices en-toepassingen
ms.openlocfilehash: d2be5e0127adf25b3884e3717caccf60d4db1d28
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653568"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="02654-103">Beveiligingsinformatie en Gebeurtenissenbeheer (SIEM) Serverintegratie met Microsoft 365-Services en-toepassingen</span><span class="sxs-lookup"><span data-stu-id="02654-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="02654-104">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="02654-104">Summary</span></span>

<span data-ttu-id="02654-105">Maakt uw organisatie gebruik van of planning voor een beveiligings-of SIEM-server?</span><span class="sxs-lookup"><span data-stu-id="02654-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="02654-106">U vraagt zich wellicht af hoe dit wordt geïntegreerd met Microsoft 365 of Office 365.</span><span class="sxs-lookup"><span data-stu-id="02654-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="02654-107">Dit artikel bevat een overzicht van bronnen die u kunt gebruiken om uw SIEM server te integreren met Microsoft 365-Services en-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="02654-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="02654-108">Als u nog geen SIEM-server hebt en uw opties wilt bekijken, kunt u overwegen **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="02654-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="02654-109">Heb ik een SIEM-server nodig?</span><span class="sxs-lookup"><span data-stu-id="02654-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="02654-110">Of u een SIEM-server nodig hebt, is afhankelijk van het aantal factoren, zoals de beveiligingsvereisten van uw organisatie en de locatie waar uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="02654-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="02654-111">Microsoft 365 omvat een groot aantal beveiligingsfuncties die voldoen aan de behoeften van een groot aantal organisaties zonder extra servers, zoals een SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="02654-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="02654-112">Sommige organisaties hebben speciale omstandigheden waarvoor het gebruik van een SIEM-server is vereist.</span><span class="sxs-lookup"><span data-stu-id="02654-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="02654-113">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="02654-113">Here are some examples:</span></span>

- <span data-ttu-id="02654-114">*Fabrikam* heeft bepaalde inhoud en toepassingen on-premises en in de Cloud (deze hebben een hybride implementatie van de Cloud).</span><span class="sxs-lookup"><span data-stu-id="02654-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="02654-115">Fabrikam heeft een SIEM-server geïmplementeerd voor het uitvoeren van beveiligingsrapporten over al hun inhoud en toepassingen.</span><span class="sxs-lookup"><span data-stu-id="02654-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="02654-116">*Contoso* is een organisatie met een financiële dienst die zeer stringente beveiligingsvereisten biedt.</span><span class="sxs-lookup"><span data-stu-id="02654-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="02654-117">Ze hebben een SIEM-server toegevoegd aan de omgeving om gebruik te kunnen maken van de extra beveiligings bescherming die ze nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="02654-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="02654-118">SIEM Server-integratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="02654-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="02654-119">Een SIEM-server kan gegevens ontvangen van diverse Microsoft 365-Services en-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="02654-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="02654-120">In de volgende tabel vindt u een overzicht van diverse Microsoft 365-Services en-toepassingen, samen met SIEM-server ingangen en bronnen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="02654-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="02654-121">Microsoft 365-service of-toepassing</span><span class="sxs-lookup"><span data-stu-id="02654-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="02654-122">SIEM-server ingangen/-methoden</span><span class="sxs-lookup"><span data-stu-id="02654-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="02654-123">Informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="02654-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="02654-124">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="02654-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="02654-125">Controlelogboeken</span><span class="sxs-lookup"><span data-stu-id="02654-125">Audit logs</span></span>|[<span data-ttu-id="02654-126">SIEM-integratie met Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="02654-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="02654-127">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="02654-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="02654-128">HTTPS-eindpunt gehost in azure</span><span class="sxs-lookup"><span data-stu-id="02654-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="02654-129">REST-API</span><span class="sxs-lookup"><span data-stu-id="02654-129">REST API</span></span>|[<span data-ttu-id="02654-130">Waarschuwingen aantrekken voor uw SIEM-hulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="02654-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="02654-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="02654-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="02654-132">Integratie van logboek</span><span class="sxs-lookup"><span data-stu-id="02654-132">Log integration</span></span>|[<span data-ttu-id="02654-133">SIEM-integratie met Microsoft Cloud-app-beveiliging</span><span class="sxs-lookup"><span data-stu-id="02654-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="02654-134">Bekijk [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="02654-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="02654-135">Azure Sentinel wordt geleverd met connectors voor Microsoft-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="02654-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="02654-136">Deze verbindingslijnen bevinden zich in de loop van het vak en geven de mogelijkheid om in realtime te integreren.</span><span class="sxs-lookup"><span data-stu-id="02654-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="02654-137">U kunt Azure verklikker gebruiken met uw Microsoft Threat Protection-oplossingen en Microsoft 365-Services, waaronder Office 365, Azure AD, Azure Office, Azure ATP, Microsoft Cloud app Security en meer.</span><span class="sxs-lookup"><span data-stu-id="02654-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="02654-138">Controlelogboekregistratie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="02654-138">Audit logging must be turned on</span></span>

<span data-ttu-id="02654-139">Zorg ervoor dat het logboekregistratie van gebeurtenissen is ingeschakeld voordat u SIEM Server-integratie configureert.</span><span class="sxs-lookup"><span data-stu-id="02654-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="02654-140">Voor SharePoint Online, OneDrive voor bedrijven en Azure Active Directory [is controlelogboekregistratie ingeschakeld in het beveiligings & nalevings centrum](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="02654-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="02654-141">Voor Exchange Online raadpleegt u [Postvak controle beheren](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="02654-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="02654-142">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="02654-142">More resources</span></span>

[<span data-ttu-id="02654-143">Beveiligingsoplossingen integreren in azure Security Center</span><span class="sxs-lookup"><span data-stu-id="02654-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="02654-144">Microsoft Graph beveiligings API-waarschuwingen integreren met een SIEM</span><span class="sxs-lookup"><span data-stu-id="02654-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
