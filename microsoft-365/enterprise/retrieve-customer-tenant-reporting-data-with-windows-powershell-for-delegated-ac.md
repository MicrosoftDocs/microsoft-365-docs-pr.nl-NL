---
title: Klantten tenantrapportagegegevens ophalen met Windows PowerShell voor DAP-partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Overzicht: Gebruik externe Windows PowerShell voor Microsoft Exchange Online om rapporten op te halen van afzonderlijke klantten tenants.'
ms.openlocfilehash: 8a244e1178e64d27d5e0f061d094dccd39bb8275
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290073"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="ebe60-103">Rapportagegegevens van klantten tenants ophalen met Windows PowerShell voor DAP-partners (Gedelegeerde toegangsmachtigingen)</span><span class="sxs-lookup"><span data-stu-id="ebe60-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="ebe60-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ebe60-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ebe60-105">Gebruik externe Windows PowerShell voor Microsoft Exchange Online om rapporten op te halen bij afzonderlijke klantten tenants.</span><span class="sxs-lookup"><span data-stu-id="ebe60-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>

<span data-ttu-id="ebe60-106">Syndication- en Cloud Solution Provider (CSP)-partners hebben rechtstreeks via externe Windows PowerShell voor Exchange Online PowerShell toegang tot de gegevens die klant tenantrapporten maken.</span><span class="sxs-lookup"><span data-stu-id="ebe60-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="ebe60-107">Op deze manier kunnen partners de rapportagegegevens verzamelen en opslaan en vervolgens andere bewerkingen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ebe60-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="ebe60-108">Nadat u een externe verbinding hebt geopend, is het ophalen van rapportagegegevens over een klanthuur identiek aan het uitvoeren van een cmdlet tegen een klanthuur.</span><span class="sxs-lookup"><span data-stu-id="ebe60-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>

<span data-ttu-id="ebe60-109">In dit artikel gebruikt u externe Windows PowerShell voor Exchange Online verbinding te maken met één klant tenancy en een rapport op te halen.</span><span class="sxs-lookup"><span data-stu-id="ebe60-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="ebe60-110">Standaard biedt Windows PowerShell geen ondersteuning voor het aggregeren van rapportagegegevens van meerdere klantentenancies.</span><span class="sxs-lookup"><span data-stu-id="ebe60-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="ebe60-111">De rapporten die u met deze procedure op haalt, zijn alleen voor  _de GedelegeerdeOrg_ met wie u verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="ebe60-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ebe60-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="ebe60-112">Before you begin</span></span>

- <span data-ttu-id="ebe60-113">U moet verbinding maken met uw Exchange Online tenant met behulp van externe Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebe60-113">You need to connect to your Exchange Online tenant by using remote Windows PowerShell.</span></span> <span data-ttu-id="ebe60-114">Zie voor instructies Verbinding maken tenants Exchange Online met externe Windows PowerShell [voor DAP-partners (Gedelegeerde toegangsmachtigingen)](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ebe60-114">For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>

## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="ebe60-115">Het voorbeeld Get-StaleMailboxReport uitvoeren</span><span class="sxs-lookup"><span data-stu-id="ebe60-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="ebe60-116">Nadat u een externe sessie voor Exchange Online hebt geopend, kunt u deze opdracht uitvoeren om het **Get-StaleMailboxReport** op te halen voor het datumbereik 03-25-2015 tot en met 31-03-2015.</span><span class="sxs-lookup"><span data-stu-id="ebe60-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="ebe60-117">Er zijn veel andere rapportage-cmdlets beschikbaar voor Exchange Online, Lync Online en SharePoint Online, evenals andere voor het traceren van berichten die u kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ebe60-117">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use.</span></span> <span data-ttu-id="ebe60-118">Zie de onderwerpen in de volgende sectie voor meer informatie over de beschikbare rapportage-cmdlets en de Office 365 Reporting web service.</span><span class="sxs-lookup"><span data-stu-id="ebe60-118">To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebe60-119">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ebe60-119">See also</span></span>

<span data-ttu-id="ebe60-120">[Office 365 Rapportagewebservice](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="ebe60-120">[Office 365 Reporting web service](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span></span>

[<span data-ttu-id="ebe60-121">Cmdlets rapporteren in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ebe60-121">Reporting cmdlets in Exchange Online</span></span>](/powershell/module/exchange/get-csclientdevicedetailreport)

[<span data-ttu-id="ebe60-122">Help voor partners</span><span class="sxs-lookup"><span data-stu-id="ebe60-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)
