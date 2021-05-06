---
title: Serviceversleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Overzicht: Inzicht in gegevensweerbaarheid in Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2021
ms.locfileid: "52161680"
---
# <a name="service-encryption"></a><span data-ttu-id="cb3d0-103">Serviceversleuteling</span><span class="sxs-lookup"><span data-stu-id="cb3d0-103">Service Encryption</span></span>

<span data-ttu-id="cb3d0-104">Naast het gebruik van volumeversleuteling, Exchange Online, Microsoft Teams, SharePoint Online en OneDrive voor Bedrijven ook serviceversleuteling gebruiken om klantgegevens te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="cb3d0-105">Serviceversleuteling biedt twee belangrijke beheeropties:</span><span class="sxs-lookup"><span data-stu-id="cb3d0-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="cb3d0-106">Door Microsoft beheerde sleutels</span><span class="sxs-lookup"><span data-stu-id="cb3d0-106">Microsoft-managed keys</span></span>
<span data-ttu-id="cb3d0-107">Microsoft beheert alle cryptografische sleutels, inclusief de hoofdsleutels voor serviceversleuteling.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="cb3d0-108">Deze optie is momenteel standaard ingeschakeld voor Exchange Online, SharePoint Online, OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="cb3d0-109">Door Microsoft beheerde sleutels bieden standaardserviceversleuteling, tenzij u besluit om aan boord te gaan met de klantsleutel.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="cb3d0-110">Als u op een later tijdstip besluit de klantsleutel niet meer te gebruiken zonder het pad voor gegevensre purge te volgen, blijven uw gegevens versleuteld met behulp van de door Microsoft beheerde sleutels.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="cb3d0-111">Uw gegevens worden altijd minimaal op dit standaardniveau versleuteld.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="cb3d0-112">Klantsleutel</span><span class="sxs-lookup"><span data-stu-id="cb3d0-112">Customer Key</span></span>
<span data-ttu-id="cb3d0-113">U levert hoofdsleutels die worden gebruikt met serviceversleuteling en u beheert deze sleutels met Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="cb3d0-114">Microsoft beheert alle andere sleutels.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="cb3d0-115">Deze optie heet Klantsleutel en is momenteel beschikbaar voor Exchange Online, SharePoint Online en OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="cb3d0-116">(Eerder geavanceerde versleuteling genoemd met BYOK.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="cb3d0-117">Zie [Meer transparantie en controle voor Office 365 klanten](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) voor de oorspronkelijke aankondiging.)</span><span class="sxs-lookup"><span data-stu-id="cb3d0-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="cb3d0-118">Serviceversleuteling biedt meerdere voordelen:</span><span class="sxs-lookup"><span data-stu-id="cb3d0-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="cb3d0-119">Biedt een extra beveiligingslaag boven aan BitLocker.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="cb3d0-120">Biedt scheiding van Windows besturingssysteembeheerders van toegang tot toepassingsgegevens die zijn opgeslagen of verwerkt door het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="cb3d0-121">Bevat een optie Klantsleutel waarmee multi-tenantservices per tenant sleutelbeheer kunnen bieden.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="cb3d0-122">Verbetert de mogelijkheid om te Microsoft 365 voldoen aan de vereisten van klanten die specifieke compliancevereisten hebben met betrekking tot versleuteling.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="cb3d0-123">Met klantsleutel kunt u uw eigen cryptografische sleutels genereren met een on-premises Hardware Service Module (HSM) of Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="cb3d0-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="cb3d0-124">Ongeacht hoe u de sleutel genereert, gebruikt u AKV om de cryptografische sleutels te beheren die door Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="cb3d0-125">Wanneer uw sleutels zijn opgeslagen in AKV, kunnen ze worden gebruikt als de hoofdmap van een van de sleutelhangers waarmee uw postvakgegevens of bestanden worden versleuteld.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="cb3d0-126">Een ander voordeel van Customer Key is de controle die u hebt over de mogelijkheid van Microsoft om uw gegevens te verwerken.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="cb3d0-127">Als u gegevens wilt verwijderen uit Office 365, bijvoorbeeld als u de service bij Microsoft wilt beëindigen of een deel van uw gegevens wilt verwijderen dat is opgeslagen in de cloud, kunt u dit doen en Klantcode gebruiken als een technisch beheer.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="cb3d0-128">Als u gegevens verwijdert, kan niemand, inclusief Microsoft, de gegevens openen of verwerken.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="cb3d0-129">Klantcode is bovendien een aanvulling op het Klantenvergrendelingsvak dat u gebruikt om de toegang tot uw gegevens door Microsoft-personeel te bepalen.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="cb3d0-130">Zie deze artikelen voor informatie over het instellen van klantcode voor Microsoft 365 voor Exchange Online, Microsoft Teams, SharePoint Online, inclusief teamsites en OneDrive voor Bedrijven:</span><span class="sxs-lookup"><span data-stu-id="cb3d0-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="cb3d0-131">Serviceversleuteling met klantsleutel</span><span class="sxs-lookup"><span data-stu-id="cb3d0-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="cb3d0-132">Klantsleutel instellen</span><span class="sxs-lookup"><span data-stu-id="cb3d0-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="cb3d0-133">Klantcode beheren</span><span class="sxs-lookup"><span data-stu-id="cb3d0-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="cb3d0-134">Een klantsleutel of een beschikbaarheidssleutel rollen of draaien</span><span class="sxs-lookup"><span data-stu-id="cb3d0-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="cb3d0-135">De beschikbaarheidscode begrijpen</span><span class="sxs-lookup"><span data-stu-id="cb3d0-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
