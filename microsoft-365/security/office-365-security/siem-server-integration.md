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
ms.openlocfilehash: 17e21d19463187744afe855b2304ac71956545d2
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919761"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="8ba16-103">Beveiligingsinformatie en Gebeurtenissenbeheer (SIEM) Serverintegratie met Microsoft 365-Services en-toepassingen</span><span class="sxs-lookup"><span data-stu-id="8ba16-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a><span data-ttu-id="8ba16-104">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="8ba16-104">Summary</span></span>

<span data-ttu-id="8ba16-105">Maakt uw organisatie gebruik van of planning voor een beveiligings-of SIEM-server?</span><span class="sxs-lookup"><span data-stu-id="8ba16-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="8ba16-106">U vraagt zich wellicht af hoe dit wordt geïntegreerd met Microsoft 365 of Office 365.</span><span class="sxs-lookup"><span data-stu-id="8ba16-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="8ba16-107">Dit artikel bevat een overzicht van bronnen die u kunt gebruiken om uw SIEM server te integreren met Microsoft 365-Services en-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="8ba16-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="8ba16-108">Als u nog geen SIEM-server hebt en uw opties wilt bekijken, kunt u overwegen **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="8ba16-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="8ba16-109">Heb ik een SIEM-server nodig?</span><span class="sxs-lookup"><span data-stu-id="8ba16-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="8ba16-110">Of u een SIEM-server nodig hebt, is afhankelijk van het aantal factoren, zoals de beveiligingsvereisten van uw organisatie en de locatie waar uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="8ba16-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="8ba16-111">Microsoft 365 omvat een groot aantal beveiligingsfuncties die voldoen aan de behoeften van een groot aantal organisaties zonder extra servers, zoals een SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="8ba16-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="8ba16-112">Sommige organisaties hebben speciale omstandigheden waarvoor het gebruik van een SIEM-server is vereist.</span><span class="sxs-lookup"><span data-stu-id="8ba16-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="8ba16-113">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="8ba16-113">Here are some examples:</span></span>

- <span data-ttu-id="8ba16-114">*Fabrikam* heeft bepaalde inhoud en toepassingen on-premises en in de Cloud (deze hebben een hybride implementatie van de Cloud).</span><span class="sxs-lookup"><span data-stu-id="8ba16-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="8ba16-115">Fabrikam heeft een SIEM-server geïmplementeerd voor het uitvoeren van beveiligingsrapporten over al hun inhoud en toepassingen.</span><span class="sxs-lookup"><span data-stu-id="8ba16-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="8ba16-116">*Contoso* is een organisatie met een financiële dienst die zeer stringente beveiligingsvereisten biedt.</span><span class="sxs-lookup"><span data-stu-id="8ba16-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="8ba16-117">Ze hebben een SIEM-server toegevoegd aan de omgeving om gebruik te kunnen maken van de extra beveiligings bescherming die ze nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="8ba16-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="8ba16-118">SIEM Server-integratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8ba16-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="8ba16-119">Een SIEM-server kan gegevens ontvangen van diverse Microsoft 365-Services en-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="8ba16-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="8ba16-120">In de volgende tabel vindt u een overzicht van diverse Microsoft 365-Services en-toepassingen, samen met SIEM-server ingangen en bronnen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8ba16-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="8ba16-121">Microsoft 365-service of-toepassing</span><span class="sxs-lookup"><span data-stu-id="8ba16-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="8ba16-122">SIEM-server ingangen/-methoden</span><span class="sxs-lookup"><span data-stu-id="8ba16-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="8ba16-123">Informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="8ba16-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="8ba16-124">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8ba16-124">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="8ba16-125">Controlelogboeken</span><span class="sxs-lookup"><span data-stu-id="8ba16-125">Audit logs</span></span>|[<span data-ttu-id="8ba16-126">SIEM-integratie met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8ba16-126">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="8ba16-127">Microsoft Defender voor Eindpunt </span><span class="sxs-lookup"><span data-stu-id="8ba16-127">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="8ba16-128">HTTPS-eindpunt gehost in azure</span><span class="sxs-lookup"><span data-stu-id="8ba16-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="8ba16-129">REST-API</span><span class="sxs-lookup"><span data-stu-id="8ba16-129">REST API</span></span>|[<span data-ttu-id="8ba16-130">Waarschuwingen aantrekken voor uw SIEM-hulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="8ba16-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="8ba16-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8ba16-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="8ba16-132">Integratie van logboek</span><span class="sxs-lookup"><span data-stu-id="8ba16-132">Log integration</span></span>|[<span data-ttu-id="8ba16-133">SIEM-integratie met Microsoft Cloud-app-beveiliging</span><span class="sxs-lookup"><span data-stu-id="8ba16-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="8ba16-134">Bekijk [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="8ba16-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="8ba16-135">Azure Sentinel wordt geleverd met connectors voor Microsoft-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="8ba16-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="8ba16-136">Deze verbindingslijnen bevinden zich in de loop van het vak en geven de mogelijkheid om in realtime te integreren.</span><span class="sxs-lookup"><span data-stu-id="8ba16-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="8ba16-137">U kunt Azure Sentinel gebruiken met uw Microsoft 365 Defender-oplossingen en Microsoft 365-Services, waaronder Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud app Security en meer.</span><span class="sxs-lookup"><span data-stu-id="8ba16-137">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="8ba16-138">Controlelogboekregistratie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="8ba16-138">Audit logging must be turned on</span></span>

<span data-ttu-id="8ba16-139">Zorg ervoor dat het logboekregistratie van gebeurtenissen is ingeschakeld voordat u SIEM Server-integratie configureert.</span><span class="sxs-lookup"><span data-stu-id="8ba16-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="8ba16-140">Voor SharePoint Online, OneDrive voor bedrijven en Azure Active Directory [is controlelogboekregistratie ingeschakeld in het beveiligings & nalevings centrum](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="8ba16-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="8ba16-141">Voor Exchange Online raadpleegt u [Postvak controle beheren](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="8ba16-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="8ba16-142">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="8ba16-142">More resources</span></span>

[<span data-ttu-id="8ba16-143">Beveiligingsoplossingen in azure Defender integreren</span><span class="sxs-lookup"><span data-stu-id="8ba16-143">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="8ba16-144">Microsoft Graph beveiligings API-waarschuwingen integreren met een SIEM</span><span class="sxs-lookup"><span data-stu-id="8ba16-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
