---
title: Gegevens van de Tenant rapporten van klanten ophalen met Windows PowerShell voor DAP partners
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
description: 'Overzicht: gebruik externe Windows PowerShell voor Microsoft Exchange Online om rapporten van afzonderlijke tenants van klanten op te halen.'
ms.openlocfilehash: 24d56fffa60232c4ea39f4fe7769131cab23be2f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689013"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="354ac-103">Gegevens van de Tenant met informatie van klanten ophalen met Windows PowerShell voor partners met een gedelegeerde toegangsrechten (DAP)</span><span class="sxs-lookup"><span data-stu-id="354ac-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="354ac-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="354ac-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="354ac-105">Gebruik externe Windows PowerShell voor Microsoft Exchange Online om rapporten op te halen uit afzonderlijke tenants van klanten.</span><span class="sxs-lookup"><span data-stu-id="354ac-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>
  
<span data-ttu-id="354ac-106">Service providers voor de syndicatie en Cloud solution provider hebben toegang tot de gegevens die via externe Windows PowerShell voor Exchange Online PowerShell rechtstreeks met de Tenant rapporten van klanten worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="354ac-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="354ac-107">Hierdoor kunnen partners de rapportagegegevens verzamelen en opslaan en daarna andere bewerkingen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="354ac-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="354ac-108">Wanneer u een externe verbinding hebt geopend, wordt het verkrijgen van rapportagegegevens over een klant pacht identiek aan de uitvoering van een cmdlet voor een klant van pacht.</span><span class="sxs-lookup"><span data-stu-id="354ac-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>
  
<span data-ttu-id="354ac-109">In dit artikel moet u extern Windows PowerShell voor Exchange Online gebruiken om verbinding te maken met één klant pacht en een rapport op te halen.</span><span class="sxs-lookup"><span data-stu-id="354ac-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="354ac-110">Standaard biedt Windows PowerShell geen ondersteuning voor het samenvoegen van rapportagegegevens van meerdere klant tenancies.</span><span class="sxs-lookup"><span data-stu-id="354ac-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="354ac-111">De rapporten die u met deze procedure ophaalt, gelden alleen voor de  _DelegatedOrg_ waarmee u verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="354ac-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>
  
 
## <a name="before-you-begin"></a><span data-ttu-id="354ac-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="354ac-112">Before you begin</span></span>

- <span data-ttu-id="354ac-113">U moet verbinding maken met uw Exchange Online-Tenant via externe Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="354ac-113">You need to connect to your Exchange Online tenant by using remote Windows PowerShell.</span></span> <span data-ttu-id="354ac-114">Zie [verbinding maken met Exchange Online-tenants met externe Windows PowerShell voor instructies voor gedelegeerde toegangsmachtigingen (DAP)](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="354ac-114">For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)</span></span>
    
## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="354ac-115">Het voorbeeld voor Get-StaleMailboxReport uitvoeren</span><span class="sxs-lookup"><span data-stu-id="354ac-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="354ac-116">Wanneer u een externe sessie voor Exchange Online hebt geopend, voert u deze opdracht uit om de **Get-StaleMailboxReport** voor het datumbereik van 03/25/2015 tot en met 03/31/2015 op te halen.</span><span class="sxs-lookup"><span data-stu-id="354ac-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="354ac-117">Er zijn veel andere rapportage-cmdlets beschikbaar voor Exchange Online, Lync online en SharePoint Online en andere voor de tracering van berichten die u kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="354ac-117">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use.</span></span> <span data-ttu-id="354ac-118">Zie de onderwerpen in de volgende sectie voor meer informatie over de beschikbare rapportage-cmdlets en de Office 365 Reporting-webservice.</span><span class="sxs-lookup"><span data-stu-id="354ac-118">To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="354ac-119">Zie ook</span><span class="sxs-lookup"><span data-stu-id="354ac-119">See also</span></span>

#### 

[<span data-ttu-id="354ac-120">Service Office 365 Reporting voor de webservice</span><span class="sxs-lookup"><span data-stu-id="354ac-120">Office 365 Reporting web service</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532777)
  
[<span data-ttu-id="354ac-121">Cmdlets voor rapporten in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="354ac-121">Reporting cmdlets in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526430)
  
[<span data-ttu-id="354ac-122">Help voor partners</span><span class="sxs-lookup"><span data-stu-id="354ac-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)

