---
title: Hoe Exchange Online uw e-mailgeheimen kan beveiligen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Naast het Office 365 Trust Center met beveiligings-, privacy- en compliancegegevens voor Microsoft 365, wilt u misschien weten hoe Microsoft u helpt bij het beschermen van geheimen die u in de datacenters opgeslagen. We gebruiken de technologie Distributed Key Manager (DKM).
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161873"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="6b252-104">Hoe Exchange Online uw e-mailgeheimen kan beveiligen</span><span class="sxs-lookup"><span data-stu-id="6b252-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="6b252-105">In dit artikel wordt beschreven hoe Microsoft uw e-mailgeheimen in de datacenters beveiligt.</span><span class="sxs-lookup"><span data-stu-id="6b252-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="6b252-106">Hoe beveiligen we geheime gegevens die door u worden verstrekt?</span><span class="sxs-lookup"><span data-stu-id="6b252-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="6b252-107">Naast het Office 365 Trust Center met [beveiligings-, privacy-](./get-started-with-service-trust-portal.md)en compliancegegevens voor Office 365, wilt u misschien weten hoe Microsoft helpt bij het beschermen van geheimen die u in de datacenters opgeeft.</span><span class="sxs-lookup"><span data-stu-id="6b252-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](./get-started-with-service-trust-portal.md), you might want to know how Microsoft helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="6b252-108">We gebruiken de technologie Distributed Key Manager (DKM).</span><span class="sxs-lookup"><span data-stu-id="6b252-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="6b252-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is een clientfunctionaliteit die een set geheime sleutels gebruikt om gegevens te versleutelen en te ontsleutelen.</span><span class="sxs-lookup"><span data-stu-id="6b252-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="6b252-110">Alleen leden van een specifieke beveiligingsgroep in Active Directory Domain Services hebben toegang tot deze sleutels om de gegevens te ontsleutelen die door DKM worden versleuteld.</span><span class="sxs-lookup"><span data-stu-id="6b252-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="6b252-111">In Exchange Online maken alleen bepaalde serviceaccounts waaronder de Exchange processen worden uitgevoerd deel uit van die beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="6b252-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="6b252-112">Als onderdeel van de standaardprocedure in het datacenter wordt geen mens referenties gegeven die deel uitmaken van deze beveiligingsgroep en heeft daarom geen mens toegang tot de sleutels die deze geheimen kunnen ontsleutelen.</span><span class="sxs-lookup"><span data-stu-id="6b252-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="6b252-113">Voor foutopsporing, probleemoplossing of controle moet een datacenterbeheerder verhoogde toegang aanvragen om tijdelijke referenties te verkrijgen die deel uitmaken van de beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="6b252-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="6b252-114">Voor dit proces zijn meerdere juridische goedkeuringsniveaus vereist.</span><span class="sxs-lookup"><span data-stu-id="6b252-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="6b252-115">Als toegang wordt verleend, worden alle activiteiten geregistreerd en gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="6b252-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="6b252-116">Daarnaast wordt toegang alleen verleend voor een ingesteld tijdsinterval waarna deze automatisch verloopt.</span><span class="sxs-lookup"><span data-stu-id="6b252-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="6b252-117">Voor extra beveiliging omvat DKM-technologie geautomatiseerde sleutelrollen en archivering.</span><span class="sxs-lookup"><span data-stu-id="6b252-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="6b252-118">Dit zorgt er ook voor dat u uw oudere inhoud kunt blijven openen zonder dat u voor onbepaalde tijd op dezelfde sleutel moet vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="6b252-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="6b252-119">Waar wordt Exchange Online DKM gebruikt?</span><span class="sxs-lookup"><span data-stu-id="6b252-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="6b252-120">Microsoft gebruikt [Distributed Key Manager om](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) uw geheimen te versleutelen in Exchange Online datacenters.</span><span class="sxs-lookup"><span data-stu-id="6b252-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="6b252-121">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6b252-121">For example:</span></span>
  
- <span data-ttu-id="6b252-122">Referenties voor e-mailaccounts voor verbonden accounts.</span><span class="sxs-lookup"><span data-stu-id="6b252-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="6b252-123">Verbonden accounts zijn accounts van derden, zoals Hotmail, Gmail en Yahoo!</span><span class="sxs-lookup"><span data-stu-id="6b252-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="6b252-124">e-mailaccounts.</span><span class="sxs-lookup"><span data-stu-id="6b252-124">mail accounts.</span></span>

- <span data-ttu-id="6b252-125">Klantcode.</span><span class="sxs-lookup"><span data-stu-id="6b252-125">Customer key.</span></span> <span data-ttu-id="6b252-126">Als u [serviceversleuteling gebruikt met klantsleutel,](customer-key-overview.md)gebruikt u [Azure Key Vault](/azure/key-vault/key-vault-whatis) om uw geheimen te beschermen.</span><span class="sxs-lookup"><span data-stu-id="6b252-126">If you are using [Service encryption with Customer Key](customer-key-overview.md), you'll use [Azure Key Vault](/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b252-127">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6b252-127">Related topics</span></span>

[<span data-ttu-id="6b252-128">Versleuteling in Office 365</span><span class="sxs-lookup"><span data-stu-id="6b252-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="6b252-129">Technische naslaginformatie over versleuteling</span><span class="sxs-lookup"><span data-stu-id="6b252-129">Technical reference details about encryption</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="6b252-130">Servicecontrole in het Beveiligings &amp; compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="6b252-130">Service assurance in the Security &amp; Compliance Center</span></span>](./service-assurance.md)
