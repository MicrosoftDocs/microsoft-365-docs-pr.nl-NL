---
title: SIEM-serverintegratie met Microsoft 365 services en toepassingen
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
description: Een overzicht krijgen van de siem-serverintegratie (Security Information and Event Management) met uw Microsoft 365 cloudservices en -toepassingen
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bea8aa3914da4b813f3928eddbb6df9c98ef6605
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599945"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="0b55c-103">Siem-serverintegratie (Security Information and Event Management) met Microsoft 365 services en toepassingen</span><span class="sxs-lookup"><span data-stu-id="0b55c-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="0b55c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="0b55c-104">**Applies to**</span></span>
- [<span data-ttu-id="0b55c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0b55c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0b55c-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0b55c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0b55c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b55c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="0b55c-108">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="0b55c-108">Summary</span></span>

<span data-ttu-id="0b55c-109">Gebruikt of plant uw organisatie een SIEM-server (Security Information and Event Management) te krijgen?</span><span class="sxs-lookup"><span data-stu-id="0b55c-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="0b55c-110">U vraagt zich misschien af hoe het wordt geïntegreerd met Microsoft 365 of Office 365.</span><span class="sxs-lookup"><span data-stu-id="0b55c-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0b55c-111">Dit artikel bevat een lijst met bronnen die u kunt gebruiken om uw SIEM-server te integreren met Microsoft 365 services en toepassingen.</span><span class="sxs-lookup"><span data-stu-id="0b55c-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="0b55c-112">Als u nog geen SIEM-server hebt en uw opties verkent, kunt u het Microsoft Azure **[Schildwacht.](/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="0b55c-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="0b55c-113">Heb ik een SIEM-server nodig?</span><span class="sxs-lookup"><span data-stu-id="0b55c-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="0b55c-114">Of u een SIEM-server nodig hebt, hangt af van veel factoren, zoals de beveiligingsvereisten van uw organisatie en waar uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="0b55c-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="0b55c-115">Microsoft 365 bevat een groot aantal beveiligingsfuncties die voldoen aan de beveiligingsbehoeften van veel organisaties zonder extra servers, zoals een SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="0b55c-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="0b55c-116">Sommige organisaties hebben speciale omstandigheden waarvoor het gebruik van een SIEM-server vereist is.</span><span class="sxs-lookup"><span data-stu-id="0b55c-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="0b55c-117">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="0b55c-117">Here are some examples:</span></span>

- <span data-ttu-id="0b55c-118">*Fabrikam* heeft een aantal on-premises inhoud en toepassingen, en sommige in de cloud (ze hebben een hybride cloudimplementatie).</span><span class="sxs-lookup"><span data-stu-id="0b55c-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="0b55c-119">Om beveiligingsrapporten over al hun inhoud en toepassingen te krijgen, heeft Fabrikam een SIEM-server geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="0b55c-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="0b55c-120">*Contoso* is een financiële serviceorganisatie die bijzonder strenge beveiligingsvereisten heeft.</span><span class="sxs-lookup"><span data-stu-id="0b55c-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="0b55c-121">Ze hebben een SIEM-server toegevoegd aan hun omgeving om te profiteren van de extra beveiliging die ze nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="0b55c-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="0b55c-122">SIEM-serverintegratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b55c-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="0b55c-123">Een SIEM-server kan gegevens ontvangen van een groot aantal Microsoft 365 services en toepassingen.</span><span class="sxs-lookup"><span data-stu-id="0b55c-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="0b55c-124">In de volgende tabel vindt u Microsoft 365 services en toepassingen, samen met SIEM-serverinvoer en -resources voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0b55c-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="0b55c-125">Microsoft 365 Service of Toepassing</span><span class="sxs-lookup"><span data-stu-id="0b55c-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="0b55c-126">SIEM-serverinvoer/-methoden</span><span class="sxs-lookup"><span data-stu-id="0b55c-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="0b55c-127">Informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="0b55c-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="0b55c-128">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0b55c-128">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)|<span data-ttu-id="0b55c-129">Auditlogboeken</span><span class="sxs-lookup"><span data-stu-id="0b55c-129">Audit logs</span></span>|[<span data-ttu-id="0b55c-130">SIEM-integratie met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0b55c-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="0b55c-131">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0b55c-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="0b55c-132">HTTPS-eindpunt dat wordt gehost in Azure</span><span class="sxs-lookup"><span data-stu-id="0b55c-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="0b55c-133">REST-API</span><span class="sxs-lookup"><span data-stu-id="0b55c-133">REST API</span></span>|[<span data-ttu-id="0b55c-134">Waarschuwingen naar uw SIEM-hulpprogramma's trekken</span><span class="sxs-lookup"><span data-stu-id="0b55c-134">Pull alerts to your SIEM tools</span></span>](../defender-endpoint/configure-siem.md)|
|[<span data-ttu-id="0b55c-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0b55c-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="0b55c-136">Logboekintegratie</span><span class="sxs-lookup"><span data-stu-id="0b55c-136">Log integration</span></span>|[<span data-ttu-id="0b55c-137">SIEM-integratie met Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0b55c-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="0b55c-138">Bekijk Azure [Sentinel.](/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="0b55c-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="0b55c-139">Azure Sentinel wordt geleverd met connectors voor Microsoft-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="0b55c-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="0b55c-140">Deze connectors zijn 'out of the box' beschikbaar en bieden realtime integratie.</span><span class="sxs-lookup"><span data-stu-id="0b55c-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="0b55c-141">U kunt Azure Sentinel gebruiken met uw Microsoft 365 Defender-oplossingen en Microsoft 365-services, waaronder Office 365, Azure AD, Microsoft Defender voor identiteit, Microsoft Cloud App Security en meer.</span><span class="sxs-lookup"><span data-stu-id="0b55c-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="0b55c-142">Auditregistratie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="0b55c-142">Audit logging must be turned on</span></span>

<span data-ttu-id="0b55c-143">Controleer of auditregistratie is ingeschakeld voordat u de SIEM-serverintegratie configureert.</span><span class="sxs-lookup"><span data-stu-id="0b55c-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="0b55c-144">Voor SharePoint Online, OneDrive voor Bedrijven en Azure Active Directory is auditregistratie ingeschakeld in het [Beveiligings- & Compliancecentrum.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="0b55c-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="0b55c-145">Zie Exchange Online controle van postvakken beheren voor [meer Exchange Online.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="0b55c-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="0b55c-146">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="0b55c-146">More resources</span></span>

[<span data-ttu-id="0b55c-147">Beveiligingsoplossingen integreren in Azure Defender</span><span class="sxs-lookup"><span data-stu-id="0b55c-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="0b55c-148">Microsoft-Graph beveiligings-API-waarschuwingen integreren met een SIEM</span><span class="sxs-lookup"><span data-stu-id="0b55c-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)