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
ms.openlocfilehash: 851b27769badb2629b7e9fb1c93992c76828a633
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615646"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="2376f-103">Beveiligingsinformatie en Gebeurtenissenbeheer (SIEM) Serverintegratie met Microsoft 365-Services en-toepassingen</span><span class="sxs-lookup"><span data-stu-id="2376f-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a><span data-ttu-id="2376f-104">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="2376f-104">Summary</span></span>

<span data-ttu-id="2376f-105">Maakt uw organisatie gebruik van of planning voor een beveiligings-of SIEM-server?</span><span class="sxs-lookup"><span data-stu-id="2376f-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="2376f-106">U vraagt zich wellicht af hoe dit wordt geïntegreerd met Microsoft 365 of Office 365.</span><span class="sxs-lookup"><span data-stu-id="2376f-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2376f-107">Dit artikel bevat een overzicht van bronnen die u kunt gebruiken om uw SIEM server te integreren met Microsoft 365-Services en-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="2376f-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="2376f-108">Als u nog geen SIEM-server hebt en uw opties wilt bekijken, kunt u overwegen **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="2376f-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="2376f-109">Heb ik een SIEM-server nodig?</span><span class="sxs-lookup"><span data-stu-id="2376f-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="2376f-110">Of u een SIEM-server nodig hebt, is afhankelijk van het aantal factoren, zoals de beveiligingsvereisten van uw organisatie en de locatie waar uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="2376f-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="2376f-111">Microsoft 365 omvat een groot aantal beveiligingsfuncties die voldoen aan de behoeften van een groot aantal organisaties zonder extra servers, zoals een SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="2376f-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="2376f-112">Sommige organisaties hebben speciale omstandigheden waarvoor het gebruik van een SIEM-server is vereist.</span><span class="sxs-lookup"><span data-stu-id="2376f-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="2376f-113">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="2376f-113">Here are some examples:</span></span>

- <span data-ttu-id="2376f-114">*Fabrikam* heeft bepaalde inhoud en toepassingen on-premises en in de Cloud (deze hebben een hybride implementatie van de Cloud).</span><span class="sxs-lookup"><span data-stu-id="2376f-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="2376f-115">Fabrikam heeft een SIEM-server geïmplementeerd voor het uitvoeren van beveiligingsrapporten over al hun inhoud en toepassingen.</span><span class="sxs-lookup"><span data-stu-id="2376f-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="2376f-116">*Contoso* is een organisatie met een financiële dienst die zeer stringente beveiligingsvereisten biedt.</span><span class="sxs-lookup"><span data-stu-id="2376f-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="2376f-117">Ze hebben een SIEM-server toegevoegd aan de omgeving om gebruik te kunnen maken van de extra beveiligings bescherming die ze nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="2376f-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="2376f-118">SIEM Server-integratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2376f-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="2376f-119">Een SIEM-server kan gegevens ontvangen van diverse Microsoft 365-Services en-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="2376f-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="2376f-120">In de volgende tabel vindt u een overzicht van diverse Microsoft 365-Services en-toepassingen, samen met SIEM-server ingangen en bronnen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2376f-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="2376f-121">Microsoft 365-service of-toepassing</span><span class="sxs-lookup"><span data-stu-id="2376f-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="2376f-122">SIEM-server ingangen/-methoden</span><span class="sxs-lookup"><span data-stu-id="2376f-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="2376f-123">Informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="2376f-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="2376f-124">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2376f-124">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="2376f-125">Controlelogboeken</span><span class="sxs-lookup"><span data-stu-id="2376f-125">Audit logs</span></span>|[<span data-ttu-id="2376f-126">SIEM-integratie met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2376f-126">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="2376f-127">Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="2376f-127">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="2376f-128">HTTPS-eindpunt gehost in azure</span><span class="sxs-lookup"><span data-stu-id="2376f-128">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="2376f-129">REST-API</span><span class="sxs-lookup"><span data-stu-id="2376f-129">REST API</span></span>|[<span data-ttu-id="2376f-130">Waarschuwingen aantrekken voor uw SIEM-hulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="2376f-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="2376f-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2376f-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="2376f-132">Integratie van logboek</span><span class="sxs-lookup"><span data-stu-id="2376f-132">Log integration</span></span>|[<span data-ttu-id="2376f-133">SIEM-integratie met Microsoft Cloud-app-beveiliging</span><span class="sxs-lookup"><span data-stu-id="2376f-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="2376f-134">Bekijk [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="2376f-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="2376f-135">Azure Sentinel wordt geleverd met connectors voor Microsoft-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="2376f-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="2376f-136">Deze verbindingslijnen bevinden zich in de loop van het vak en geven de mogelijkheid om in realtime te integreren.</span><span class="sxs-lookup"><span data-stu-id="2376f-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="2376f-137">U kunt Azure Sentinel gebruiken met uw Microsoft 365 Defender-oplossingen en Microsoft 365-Services, waaronder Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud app Security en meer.</span><span class="sxs-lookup"><span data-stu-id="2376f-137">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="2376f-138">Controlelogboekregistratie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="2376f-138">Audit logging must be turned on</span></span>

<span data-ttu-id="2376f-139">Zorg ervoor dat het logboekregistratie van gebeurtenissen is ingeschakeld voordat u SIEM Server-integratie configureert.</span><span class="sxs-lookup"><span data-stu-id="2376f-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="2376f-140">Voor SharePoint Online, OneDrive voor bedrijven en Azure Active Directory [is controlelogboekregistratie ingeschakeld in het beveiligings & nalevings centrum](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="2376f-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="2376f-141">Voor Exchange Online raadpleegt u [Postvak controle beheren](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="2376f-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="2376f-142">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="2376f-142">More resources</span></span>

[<span data-ttu-id="2376f-143">Beveiligingsoplossingen in azure Defender integreren</span><span class="sxs-lookup"><span data-stu-id="2376f-143">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="2376f-144">Microsoft Graph beveiligings API-waarschuwingen integreren met een SIEM</span><span class="sxs-lookup"><span data-stu-id="2376f-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
