---
title: SIEM-serverintegratie met Microsoft 365-services en -toepassingen
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Krijg een overzicht van de integratie van de SIEM-server (Security Information and Event Management) met uw Microsoft 365-cloudservices en -toepassingen
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f29da87aa6eab1852330092d93187a27b2d36eb2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167141"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="f40ab-103">SiEM-serverintegratie (Security Information and Event Management) met Microsoft 365-services en -toepassingen</span><span class="sxs-lookup"><span data-stu-id="f40ab-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="f40ab-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="f40ab-104">**Applies to**</span></span>
- [<span data-ttu-id="f40ab-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f40ab-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="f40ab-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f40ab-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="f40ab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f40ab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="f40ab-108">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="f40ab-108">Summary</span></span>

<span data-ttu-id="f40ab-109">Gebruikt uw organisatie een SIEM-server (Security Information and Event Management) of gaat u deze gebruiken?</span><span class="sxs-lookup"><span data-stu-id="f40ab-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="f40ab-110">Misschien vraagt u zich af hoe dit programma kan worden geïntegreerd met Microsoft 365 of Office 365.</span><span class="sxs-lookup"><span data-stu-id="f40ab-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f40ab-111">Dit artikel bevat een lijst met bronnen die u kunt gebruiken om uw SIEM-server te integreren met Microsoft 365-services en -toepassingen.</span><span class="sxs-lookup"><span data-stu-id="f40ab-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="f40ab-112">Als u nog geen SIEM-server hebt en uw opties verkent, overweeg dan **[Microsoft Azure Azure.](https://docs.microsoft.com/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="f40ab-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="f40ab-113">Heb ik een SIEM-server nodig?</span><span class="sxs-lookup"><span data-stu-id="f40ab-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="f40ab-114">Of u een SIEM-server nodig hebt, hangt af van een groot aantal factoren, zoals de beveiligingsvereisten van uw organisatie en waar uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="f40ab-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="f40ab-115">Microsoft 365 bevat een groot aantal beveiligingsfuncties die voldoen aan de beveiligingsbehoeften van veel organisaties zonder extra servers, zoals een SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="f40ab-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="f40ab-116">Sommige organisaties hebben speciale omstandigheden waaronder het gebruik van een SIEM-server is vereist.</span><span class="sxs-lookup"><span data-stu-id="f40ab-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="f40ab-117">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="f40ab-117">Here are some examples:</span></span>

- <span data-ttu-id="f40ab-118">*Fabrikam heeft* enkele inhoud en toepassingen on-premises, en sommige in de cloud (ze hebben een hybride cloudimplementatie).</span><span class="sxs-lookup"><span data-stu-id="f40ab-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="f40ab-119">Fabrikam heeft een SIEM-server geïmplementeerd om beveiligingsrapporten over alle inhoud en toepassingen te krijgen.</span><span class="sxs-lookup"><span data-stu-id="f40ab-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="f40ab-120">*Contoso* is een financiële dienstverleningsorganisatie die zeer strikte beveiligingsvereisten kent.</span><span class="sxs-lookup"><span data-stu-id="f40ab-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="f40ab-121">Ze hebben een SIEM-server aan hun omgeving toegevoegd om te profiteren van de extra beveiligingsbescherming die ze vereisen.</span><span class="sxs-lookup"><span data-stu-id="f40ab-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="f40ab-122">SIEM-serverintegratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f40ab-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="f40ab-123">Een SIEM-server kan gegevens ontvangen van diverse Microsoft 365-services en -toepassingen.</span><span class="sxs-lookup"><span data-stu-id="f40ab-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="f40ab-124">De volgende tabel bevat een aantal Microsoft 365-services en -toepassingen, samen met SIEM-serverinvoer en bronnen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f40ab-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="f40ab-125">Microsoft 365-service of -toepassing</span><span class="sxs-lookup"><span data-stu-id="f40ab-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="f40ab-126">SIEM-serverinvoer/-methoden</span><span class="sxs-lookup"><span data-stu-id="f40ab-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="f40ab-127">Informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="f40ab-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="f40ab-128">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f40ab-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="f40ab-129">Auditlogboeken</span><span class="sxs-lookup"><span data-stu-id="f40ab-129">Audit logs</span></span>|[<span data-ttu-id="f40ab-130">SIEM-integratie met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f40ab-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="f40ab-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f40ab-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="f40ab-132">HTTPS-eindpunt gehost in Azure</span><span class="sxs-lookup"><span data-stu-id="f40ab-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="f40ab-133">REST API</span><span class="sxs-lookup"><span data-stu-id="f40ab-133">REST API</span></span>|[<span data-ttu-id="f40ab-134">Waarschuwingen trekken voor uw SIEM-hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="f40ab-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="f40ab-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f40ab-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="f40ab-136">Logboekintegratie</span><span class="sxs-lookup"><span data-stu-id="f40ab-136">Log integration</span></span>|[<span data-ttu-id="f40ab-137">SIEM-integratie met Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f40ab-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="f40ab-138">Bekijk Azure [Azure](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="f40ab-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="f40ab-139">Azure Azure Is voorzien van connectors voor Microsoft-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="f40ab-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="f40ab-140">Deze connectors zijn 'out-of-the-box' beschikbaar en bieden ondersteuning voor realtime-integratie.</span><span class="sxs-lookup"><span data-stu-id="f40ab-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="f40ab-141">U kunt Azure Azure Azure Gebruiken met uw Microsoft 365 Defender-oplossingen en Microsoft 365-services, waaronder Office 365, Azure AD, Microsoft Defender voor identiteit, Microsoft Cloud App-beveiliging en meer.</span><span class="sxs-lookup"><span data-stu-id="f40ab-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="f40ab-142">Auditlogregistratie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="f40ab-142">Audit logging must be turned on</span></span>

<span data-ttu-id="f40ab-143">Zorg ervoor dat auditlogregistratie is ingeschakeld voordat u de SIEM-serverintegratie configureert.</span><span class="sxs-lookup"><span data-stu-id="f40ab-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="f40ab-144">Voor SharePoint Online, OneDrive voor Bedrijven en Azure Active Directory is auditlogboekregistratie ingeschakeld in het [beveiligings- & compliancecentrum.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="f40ab-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="f40ab-145">Zie Postvak controleren beheren [voor](../../compliance/enable-mailbox-auditing.md)Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f40ab-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="f40ab-146">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="f40ab-146">More resources</span></span>

[<span data-ttu-id="f40ab-147">Beveiligingsoplossingen integreren in Azure Defender</span><span class="sxs-lookup"><span data-stu-id="f40ab-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="f40ab-148">Microsoft Graph Security API-waarschuwingen integreren met een SIEM</span><span class="sxs-lookup"><span data-stu-id="f40ab-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
