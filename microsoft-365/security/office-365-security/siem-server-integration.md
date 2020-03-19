---
title: " Siem-serverintegratie (Security Information and Event Management) met Microsoft 365-services en -toepassingen"
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
description: Krijg een overzicht van siem-serverintegratie (Security Information and Event Management) met uw Microsoft 365-cloudservices en -toepassingen
ms.openlocfilehash: d5adf0a72ac78475cb47f06732375ce01c0d72be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805709"
---
#  <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="7c83c-103">Siem-serverintegratie (Security Information and Event Management) met Microsoft 365-services en -toepassingen</span><span class="sxs-lookup"><span data-stu-id="7c83c-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="7c83c-104">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="7c83c-104">Summary</span></span>

<span data-ttu-id="7c83c-105">Gebruikt of is uw organisatie van plan om een SIEM-server (Security Information and Event Management) te krijgen?</span><span class="sxs-lookup"><span data-stu-id="7c83c-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="7c83c-106">U vraagt zich misschien af hoe het integreert met Microsoft 365 of Office 365.</span><span class="sxs-lookup"><span data-stu-id="7c83c-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7c83c-107">In dit artikel vindt u een lijst met bronnen die u gebruiken om uw SIEM-server te integreren met Microsoft 365-services en -toepassingen.</span><span class="sxs-lookup"><span data-stu-id="7c83c-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="7c83c-108">Als u nog geen SIEM-server hebt en uw opties verkent, u **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** overwegen.</span><span class="sxs-lookup"><span data-stu-id="7c83c-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="7c83c-109">Heb ik een SIEM-server nodig?</span><span class="sxs-lookup"><span data-stu-id="7c83c-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="7c83c-110">Of u een SIEM-server nodig hebt, hangt af van vele factoren, zoals de beveiligingsvereisten van uw organisatie en waar uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="7c83c-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="7c83c-111">Microsoft 365 bevat een breed scala aan beveiligingsfuncties die voldoen aan de beveiligingsbehoeften van veel organisaties zonder extra servers, zoals een SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="7c83c-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="7c83c-112">Sommige organisaties hebben speciale omstandigheden die het gebruik van een SIEM-server vereisen.</span><span class="sxs-lookup"><span data-stu-id="7c83c-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="7c83c-113">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="7c83c-113">Here are some examples:</span></span>

- <span data-ttu-id="7c83c-114">*Fabrikam* heeft een aantal inhoud en applicaties on premises, en sommige in de cloud (ze hebben een hybride cloud implementatie).</span><span class="sxs-lookup"><span data-stu-id="7c83c-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="7c83c-115">Om beveiligingsrapporten over al hun inhoud en toepassingen te krijgen, heeft Fabrikam een SIEM-server geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="7c83c-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="7c83c-116">*Contoso* is een financiële dienstverlener met bijzonder strenge veiligheidseisen.</span><span class="sxs-lookup"><span data-stu-id="7c83c-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="7c83c-117">Ze hebben een SIEM-server aan hun omgeving toegevoegd om te profiteren van de extra beveiligingsbeveiliging die ze nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="7c83c-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="7c83c-118">SIEM-serverintegratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c83c-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="7c83c-119">Een SIEM-server kan gegevens ontvangen van een breed scala aan Microsoft 365-services en -toepassingen.</span><span class="sxs-lookup"><span data-stu-id="7c83c-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="7c83c-120">In de volgende tabel worden verschillende Microsoft 365-services en -toepassingen weergegeven, samen met SIEM-serveringangen en -bronnen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7c83c-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span> 

| <span data-ttu-id="7c83c-121">Microsoft 365-service of -toepassing</span><span class="sxs-lookup"><span data-stu-id="7c83c-121">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="7c83c-122">SIEM-serveringangen/-methoden</span><span class="sxs-lookup"><span data-stu-id="7c83c-122">SIEM server inputs/methods</span></span> | <span data-ttu-id="7c83c-123">Bronnen voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="7c83c-123">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="7c83c-124">Geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="7c83c-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="7c83c-125">Controlelogboeken</span><span class="sxs-lookup"><span data-stu-id="7c83c-125">Audit logs</span></span> | [<span data-ttu-id="7c83c-126">SIEM-integratie met Geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="7c83c-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="7c83c-127">Geavanceerde bescherming voor geavanceerde bedreigingen van Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7c83c-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="7c83c-128">HTTPS-eindpunt gehost in Azure</span><span class="sxs-lookup"><span data-stu-id="7c83c-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="7c83c-129">REST-API</span><span class="sxs-lookup"><span data-stu-id="7c83c-129">REST API</span></span>| [<span data-ttu-id="7c83c-130">Waarschuwingen voor uw SIEM-hulpprogramma's weergeven</span><span class="sxs-lookup"><span data-stu-id="7c83c-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="7c83c-131">Beveiliging van Microsoft Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="7c83c-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="7c83c-132">Logintegratie</span><span class="sxs-lookup"><span data-stu-id="7c83c-132">Log integration</span></span> | [<span data-ttu-id="7c83c-133">SIEM-integratie met Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7c83c-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="7c83c-134">Neem een kijkje op [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="7c83c-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="7c83c-135">Azure Sentinel wordt geleverd met connectors voor Microsoft-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="7c83c-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="7c83c-136">Deze connectoren zijn beschikbaar "out of the box" en zorgen voor real-time integratie.</span><span class="sxs-lookup"><span data-stu-id="7c83c-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="7c83c-137">U Azure Sentinel gebruiken met uw Microsoft Threat Protection-oplossingen en Microsoft 365-services, waaronder Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security en meer.</span><span class="sxs-lookup"><span data-stu-id="7c83c-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="7c83c-138">Controlelogboekregistratie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="7c83c-138">Audit logging must be turned on</span></span>

<span data-ttu-id="7c83c-139">Controleer of de controlelogboekregistratie is ingeschakeld voordat u siem-serverintegratie configureert.</span><span class="sxs-lookup"><span data-stu-id="7c83c-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="7c83c-140">Voor SharePoint Online, OneDrive voor Bedrijven en Azure Active Directory [is controlelogboekregistratie ingeschakeld in het Beveiligingscentrum & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="7c83c-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="7c83c-141">Voor Exchange Online [is controlelogboekregistratie ingeschakeld met Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="7c83c-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="more-resources"></a><span data-ttu-id="7c83c-142">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="7c83c-142">More resources</span></span>

[<span data-ttu-id="7c83c-143">Beveiligingsoplossingen integreren in Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="7c83c-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="7c83c-144">Microsoft Graph Security API-waarschuwingen integreren met een SIEM</span><span class="sxs-lookup"><span data-stu-id="7c83c-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
