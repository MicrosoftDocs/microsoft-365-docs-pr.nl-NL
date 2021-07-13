---
title: Vereisten voor Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Voor MSP's (Managed Service Providers) krijgt u een lijst met vereisten voor het gebruik van Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395186"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="053ce-103">Vereisten voor Microsoft 365 Lighthouse</span><span class="sxs-lookup"><span data-stu-id="053ce-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="053ce-104">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die voldoen aan de vereisten in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="053ce-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="053ce-105">Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="053ce-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="053ce-106">Microsoft 365 Lighthouse is een beheerportal waarmee beheerde serviceproviders (MSP's) apparaten, gegevens en gebruikers op grote schaal kunnen beveiligen en beheren voor klanten van kleine en middelgrote bedrijven (SMB).</span><span class="sxs-lookup"><span data-stu-id="053ce-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="053ce-107">MSP's moeten zijn geregistreerd in het Cloud Solution Provider (CSP)-programma als indirecte wederverkoper of direct bill-partner om de Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="053ce-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="053ce-108">Bovendien moet elke MSP-klant tenant in aanmerking komen voor Microsoft 365 Lighthouse voldoen aan de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="053ce-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="053ce-109">Gedelegeerde beheerdersbevoegdheden (DAP) voor de MSP</span><span class="sxs-lookup"><span data-stu-id="053ce-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="053ce-110">Ten minste één Microsoft 365 Business Premium licentie</span><span class="sxs-lookup"><span data-stu-id="053ce-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="053ce-111">Minder dan 500 gebruikers met een licentie</span><span class="sxs-lookup"><span data-stu-id="053ce-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="053ce-112">Vereisten voor het inschakelen van apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="053ce-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="053ce-113">Als u tenantapparaten van klanten wilt weergeven op de pagina's voor apparaatbeheer, moet een MSP:</span><span class="sxs-lookup"><span data-stu-id="053ce-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="053ce-114">Schrijf alle klantapparaten in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="053ce-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="053ce-115">Zie Apparaten registreren [in Microsoft Intune.](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="053ce-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="053ce-116">Wijs compliancebeleid toe aan alle apparaten van klanten.</span><span class="sxs-lookup"><span data-stu-id="053ce-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="053ce-117">Zie Een compliancebeleid maken [in](/mem/intune/protect/create-compliance-policy)Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="053ce-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="053ce-118">Vereisten voor het inschakelen van gebruikersbeheer</span><span class="sxs-lookup"><span data-stu-id="053ce-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="053ce-119">Als klantgegevens worden weergegeven in rapporten op gebruikersbeheerpagina's, waaronder Risicovolle gebruikers, Meervoudige verificatie en Wachtwoord opnieuw instellen, moeten klantten over licenties voor Azure Active Directory Premium P1 of hoger hebben.</span><span class="sxs-lookup"><span data-stu-id="053ce-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="053ce-120">Azure AD Premium P1 is inbegrepen bij Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="053ce-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="053ce-121">Vereisten voor het inschakelen van bedreigingsbeheer</span><span class="sxs-lookup"><span data-stu-id="053ce-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="053ce-122">Als u tenantapparaten en bedreigingen van klanten wilt weergeven op de pagina's voor bedreigingsbeheer, moet u alle tenantapparaten van klanten registreren in Microsoft Endpoint Manager (MEM) en deze beveiligen door Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="053ce-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="053ce-123">Zie Apparaten registreren [in Microsoft Intune.](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="053ce-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="053ce-124">Microsoft Defender Antivirus maakt deel uit van het Windows besturingssysteem en is standaard ingeschakeld op apparaten met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="053ce-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="053ce-125">Als u een niet-Microsoft-antivirusoplossing gebruikt en niet Microsoft Defender Antivirus, Microsoft Defender Antivirus automatisch uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="053ce-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="053ce-126">Wanneer u de antivirusoplossing van niet-Microsoft verwijdert, Microsoft Defender Antivirus automatisch geactiveerd om uw apparaten Windows te beschermen tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="053ce-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="053ce-127">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="053ce-127">Related content</span></span>   

<span data-ttu-id="053ce-128">[Beveiliging Microsoft 365 Lighthouse portal configureren](m365-lighthouse-configure-portal-security.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="053ce-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="053ce-129">[Microsoft 365 Lighthouse pagina overzicht van apparaat compliance](m365-lighthouse-device-compliance-page-overview.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="053ce-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="053ce-130">[Microsoft 365 Lighthouse Paginaoverzicht gebruikers](m365-lighthouse-users-page-overview.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="053ce-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="053ce-131">[Microsoft 365 Lighthouse overzicht van de pagina Bedreigingsbeheer](m365-lighthouse-threat-management-page-overview.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="053ce-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="053ce-132">[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml)   (artikel)</span><span class="sxs-lookup"><span data-stu-id="053ce-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

