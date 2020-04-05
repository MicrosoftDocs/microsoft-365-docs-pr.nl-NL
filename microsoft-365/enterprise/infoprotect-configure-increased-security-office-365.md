---
title: 'Stap 3: verbeterde beveiliging voor Microsoft 365 configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verbeterde beveiliging voor Microsoft 365 begrijpen en configureren.
ms.openlocfilehash: eabf0d60f3cfb61b7fffcc688a080ba99f83293e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805880"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="8932c-103">Stap 3: verbeterde beveiliging voor Microsoft 365 configureren</span><span class="sxs-lookup"><span data-stu-id="8932c-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="8932c-104">*Deze stap is vereist en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="8932c-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: gegevensbeveiliging](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="8932c-106">Als u er zeker van wilt zijn dat uw Microsoft 365-abonnement en de gegevens vanaf het begin beveiligd zijn tegen schadelijke bedreigingen, configureert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="8932c-106">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="8932c-107">Beleid voor het beheer van bedreigingen afstemmen</span><span class="sxs-lookup"><span data-stu-id="8932c-107">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [<span data-ttu-id="8932c-108">Aanvullende, tenant-brede Exchange Online-instellingen</span><span class="sxs-lookup"><span data-stu-id="8932c-108">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="8932c-109">Tenantbreed deelbeleid in SharePoint Online Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="8932c-109">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="8932c-110">Instellingen in Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8932c-110">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="8932c-111">Eenmaal geconfigureerd, kunt u informatie over uw beveiligingsstatus verkrijgen via:</span><span class="sxs-lookup"><span data-stu-id="8932c-111">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="8932c-112">Dashboards en rapporten in het Microsoft-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8932c-112">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [<span data-ttu-id="8932c-113">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="8932c-113">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="8932c-114">Een extra beveiligingsfunctie is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), waarmee uw organisatie veiliger kan samenwerken door:</span><span class="sxs-lookup"><span data-stu-id="8932c-114">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="8932c-115">[Koppelingen](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) en [bijlagen](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) te beschermen in e-mail.</span><span class="sxs-lookup"><span data-stu-id="8932c-115">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="8932c-116">Informatie voor spoofberichten en antiphishing te bieden voor e-mail in Exchange Online en [bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="8932c-116">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="8932c-117">Office 365 ATP is alleen beschikbaar met Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8932c-117">Office 365 ATP is only available with Microsoft 365 E5.</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="8932c-119">Handleiding testlab: configureer verhoogde Microsoft 365-beveiliging</span><span class="sxs-lookup"><span data-stu-id="8932c-119">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="8932c-120">Zie de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) voor deze stap als tussentijds controlepunt.</span><span class="sxs-lookup"><span data-stu-id="8932c-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8932c-121">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="8932c-121">Next step</span></span>


|||
|:-------|:-----|
|![Stap 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="8932c-123">Windows-gegevensbescherming configureren</span><span class="sxs-lookup"><span data-stu-id="8932c-123">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


