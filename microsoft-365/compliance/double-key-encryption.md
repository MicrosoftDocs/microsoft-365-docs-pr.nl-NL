---
title: Dubbele sleutelcodering (DKE)
description: Met DKE kunt u zeer gevoelige gegevens beveiligen met behoud van volledige controle over uw sleutel.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 746f1345b47694f4a4122edc5d89cc924441ea81
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2021
ms.locfileid: "52162489"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="aa38f-103">Dubbele sleutelversleuteling voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aa38f-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="aa38f-104">*Van toepassing op: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), Azure [Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="aa38f-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="aa38f-105">*Instructies voor: [Geïntegreerde labelingclient](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients) voor Azure Information Protection voor Windows*</span><span class="sxs-lookup"><span data-stu-id="aa38f-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="aa38f-106">*Servicebeschrijving voor: [Microsoft 365 Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="aa38f-106">*Service description for: [Microsoft 365 Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="aa38f-107">Double Key Encryption (DKE) gebruikt twee toetsen samen om beveiligde inhoud te openen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="aa38f-108">Microsoft slaat één sleutel op in Microsoft Azure en u houdt de andere sleutel vast.</span><span class="sxs-lookup"><span data-stu-id="aa38f-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="aa38f-109">U hebt volledige controle over een van uw sleutels met de service Dubbele sleutelversleuteling.</span><span class="sxs-lookup"><span data-stu-id="aa38f-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="aa38f-110">U kunt beveiliging toepassen met de geïntegreerde labelingclient van Azure Information Protection op uw zeer gevoelige inhoud.</span><span class="sxs-lookup"><span data-stu-id="aa38f-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="aa38f-111">Double Key Encryption ondersteunt zowel cloud- als on-premises implementaties.</span><span class="sxs-lookup"><span data-stu-id="aa38f-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="aa38f-112">Deze implementaties helpen ervoor te zorgen dat versleutelde gegevens ondoorzichtig blijven, waar u de beveiligde gegevens ook opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="aa38f-113">Zie Uw [Azure Information Protection-tenantsleutel](/azure/information-protection/plan-implement-tenant-key)plannen en implementeren voor meer informatie over de standaardsleutels voor tenants in de cloud.</span><span class="sxs-lookup"><span data-stu-id="aa38f-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="aa38f-114">Wanneer uw organisatie DKE moet aannemen</span><span class="sxs-lookup"><span data-stu-id="aa38f-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="aa38f-115">Dubbele sleutelversleuteling is bedoeld voor uw meest gevoelige gegevens die aan de strengste beveiligingsvereisten zijn onderworpen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="aa38f-116">DKE is niet bedoeld voor alle gegevens.</span><span class="sxs-lookup"><span data-stu-id="aa38f-116">DKE is not intended for all data.</span></span> <span data-ttu-id="aa38f-117">Over het algemeen gebruikt u Dubbele sleutelversleuteling om slechts een klein deel van uw algehele gegevens te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="aa38f-118">U dient zorgvuldig te werk te gaan bij het identificeren van de juiste gegevens voor deze oplossing voordat u deze implementeert.</span><span class="sxs-lookup"><span data-stu-id="aa38f-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="aa38f-119">In sommige gevallen moet u mogelijk uw bereik beperken en gebruikmaken van andere oplossingen voor de meeste gegevens, zoals Microsoft Information Protection met door Microsoft beheerde sleutels of BYOK.</span><span class="sxs-lookup"><span data-stu-id="aa38f-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="aa38f-120">Deze oplossingen zijn voldoende voor documenten die niet onderhevig zijn aan verbeterde beveiliging en wettelijke vereisten.</span><span class="sxs-lookup"><span data-stu-id="aa38f-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="aa38f-121">Met deze oplossingen kunt u ook de krachtigste services Office 365 gebruiken. services die u niet kunt gebruiken met DKE-versleutelde inhoud.</span><span class="sxs-lookup"><span data-stu-id="aa38f-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="aa38f-122">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-122">For example:</span></span>

- <span data-ttu-id="aa38f-123">Transportregels, waaronder anti-malware en spam die zichtbaarheid in de bijlage vereisen</span><span class="sxs-lookup"><span data-stu-id="aa38f-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="aa38f-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="aa38f-124">Microsoft Delve</span></span>
- <span data-ttu-id="aa38f-125">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="aa38f-125">eDiscovery</span></span>
- <span data-ttu-id="aa38f-126">Zoeken en indexeren van inhoud</span><span class="sxs-lookup"><span data-stu-id="aa38f-126">Content search and indexing</span></span>
- <span data-ttu-id="aa38f-127">Office Web-apps, inclusief coauthoringsfunctionaliteit</span><span class="sxs-lookup"><span data-stu-id="aa38f-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="aa38f-128">Externe toepassingen of services die niet zijn geïntegreerd met DKE via de MIP SDK, kunnen geen acties uitvoeren op de versleutelde gegevens.</span><span class="sxs-lookup"><span data-stu-id="aa38f-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="aa38f-129">De Microsoft Information Protection SDK 1.7+ ondersteunt Dubbele sleutelversleuteling. toepassingen die met onze SDK zijn geïntegreerd, kunnen deze gegevens overreden met voldoende machtigingen en integraties.</span><span class="sxs-lookup"><span data-stu-id="aa38f-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="aa38f-130">We raden organisaties aan Microsoft Information Protection-mogelijkheden (classificatie en labeling) te gebruiken om de meeste gevoelige gegevens te beveiligen en alleen DKE te gebruiken voor hun bedrijfskritische gegevens.</span><span class="sxs-lookup"><span data-stu-id="aa38f-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="aa38f-131">Dubbele sleutelversleuteling is relevant voor gevoelige gegevens in sterk gereguleerde bedrijfstakken, zoals financiële services en gezondheidszorg.</span><span class="sxs-lookup"><span data-stu-id="aa38f-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="aa38f-132">Als uw organisaties een van de volgende vereisten hebben, kunt u DKE gebruiken om uw inhoud te beveiligen:</span><span class="sxs-lookup"><span data-stu-id="aa38f-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="aa38f-133">U wilt ervoor zorgen dat *alleen u* beveiligde inhoud onder alle omstandigheden kunt ontsleutelen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="aa38f-134">U wilt niet dat Microsoft zelf toegang heeft tot beveiligde gegevens.</span><span class="sxs-lookup"><span data-stu-id="aa38f-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="aa38f-135">U hebt wettelijke vereisten voor het vasthouden van sleutels binnen een geografische grens.</span><span class="sxs-lookup"><span data-stu-id="aa38f-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="aa38f-136">Alle sleutels die u hebt voor gegevensversleuteling en ontsleuteling, worden bewaard in uw datacenter.</span><span class="sxs-lookup"><span data-stu-id="aa38f-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="aa38f-137">Systeem- en licentievereisten voor DKE</span><span class="sxs-lookup"><span data-stu-id="aa38f-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="aa38f-138">**Dubbele sleutelversleuteling voor Microsoft 365** wordt geleverd met Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="aa38f-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="aa38f-139">Als u geen licentie voor Microsoft 365 E5 hebt, kunt u zich registreren voor een [proefabonnement.](https://aka.ms/M365E5ComplianceTrial)</span><span class="sxs-lookup"><span data-stu-id="aa38f-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="aa38f-140">Zie voor meer informatie over deze licenties Microsoft 365 richtlijnen voor [beveiligings- & naleving.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="aa38f-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="aa38f-141">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-141">**Azure Information Protection**.</span></span> <span data-ttu-id="aa38f-142">DKE werkt met gevoeligheidslabels en vereist Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="aa38f-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="aa38f-143">DKE-gevoeligheidslabels worden beschikbaar gesteld voor eindgebruikers via het lint gevoeligheid in Office Bureaublad-apps.</span><span class="sxs-lookup"><span data-stu-id="aa38f-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="aa38f-144">Installeer deze vereisten op elke clientcomputer waar u beveiligde documenten wilt beveiligen en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="aa38f-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="aa38f-145">**Microsoft Office Apps voor enterprise** versie 2009 of hoger (bureaubladversies van Word, PowerPoint en Excel) op Windows.</span><span class="sxs-lookup"><span data-stu-id="aa38f-145">**Microsoft Office Apps for enterprise** version 2009 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="aa38f-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 of hoger.</span><span class="sxs-lookup"><span data-stu-id="aa38f-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="aa38f-147">Download en installeer de Unified Labeling-client vanuit het [Microsoft-downloadcentrum.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="aa38f-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="aa38f-148">Ondersteunde omgevingen voor het opslaan en weergeven van DKE-beveiligde inhoud</span><span class="sxs-lookup"><span data-stu-id="aa38f-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="aa38f-149">**Ondersteunde toepassingen**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-149">**Supported applications**.</span></span> <span data-ttu-id="aa38f-150">[Microsoft 365-apps voor ondernemingen](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients op Windows, waaronder Word, Excel en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="aa38f-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="aa38f-151">**Ondersteuning voor online-inhoud.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-151">**Online content support**.</span></span> <span data-ttu-id="aa38f-152">U kunt documenten en bestanden die zijn beveiligd met Dubbele sleutelversleuteling online opslaan in zowel Microsoft-SharePoint als OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="aa38f-152">You can store documents and files protected with Double Key Encryption online in both Microsoft SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="aa38f-153">U moet documenten en bestanden labelen en beveiligen met DKE door ondersteunde toepassingen voordat u naar deze locaties uploadt.</span><span class="sxs-lookup"><span data-stu-id="aa38f-153">You must label and protect documents and files with DKE by supported applications before you upload to these locations.</span></span> <span data-ttu-id="aa38f-154">U kunt versleutelde inhoud per e-mail delen, maar u kunt versleutelde documenten en bestanden niet online bekijken.</span><span class="sxs-lookup"><span data-stu-id="aa38f-154">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="aa38f-155">In plaats daarvan moet u beveiligde inhoud weergeven met behulp van de ondersteunde bureaubladtoepassingen en -clients op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="aa38f-155">Instead, you must view protected content using the supported desktop applications and clients on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="aa38f-156">Overzicht van de implementatie van DKE</span><span class="sxs-lookup"><span data-stu-id="aa38f-156">Overview of deploying DKE</span></span>

<span data-ttu-id="aa38f-157">U volgt deze algemene stappen om DKE in te stellen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-157">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="aa38f-158">Nadat u deze stappen hebt voltooid, kunnen uw eindgebruikers uw zeer gevoelige gegevens beschermen met Dubbele sleutelversleuteling.</span><span class="sxs-lookup"><span data-stu-id="aa38f-158">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="aa38f-159">Implementeer de DKE-service zoals beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="aa38f-159">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="aa38f-160">Maak een label met Dubbele sleutelversleuteling.</span><span class="sxs-lookup"><span data-stu-id="aa38f-160">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="aa38f-161">Ga naar Informatiebeveiliging onder het [Microsoft 365 compliancecentrum](https://compliance.microsoft.com) en maak een nieuw label met Dubbele sleutelversleuteling.</span><span class="sxs-lookup"><span data-stu-id="aa38f-161">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="aa38f-162">Zie [Toegang tot inhoud beperken door gevoeligheidslabels te gebruiken om versleuteling toe te passen.](./encryption-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="aa38f-162">See [Restrict access to content by using sensitivity labels to apply encryption](./encryption-sensitivity-labels.md).</span></span>

3. <span data-ttu-id="aa38f-163">Gebruik dubbele sleutelversleutelingslabels.</span><span class="sxs-lookup"><span data-stu-id="aa38f-163">Use Double Key Encryption labels.</span></span> <span data-ttu-id="aa38f-164">Bescherm gegevens door het label Versleutelde dubbele sleutel te selecteren op het lint Gevoeligheid in Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="aa38f-164">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="aa38f-165">U kunt enkele stappen voor het implementeren van dubbele sleutelversleuteling op verschillende manieren voltooien.</span><span class="sxs-lookup"><span data-stu-id="aa38f-165">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="aa38f-166">Dit artikel bevat gedetailleerde instructies, zodat minder ervaren beheerders de service kunnen implementeren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-166">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="aa38f-167">Als u dit prettig vindt, kunt u ervoor kiezen om uw eigen methoden te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="aa38f-167">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="aa38f-168">DKE implementeren</span><span class="sxs-lookup"><span data-stu-id="aa38f-168">Deploy DKE</span></span>

<span data-ttu-id="aa38f-169">In dit artikel en de implementatievideo wordt Azure gebruikt als implementatiebestemming voor de DKE-service.</span><span class="sxs-lookup"><span data-stu-id="aa38f-169">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="aa38f-170">Als u naar een andere locatie implementeert, moet u uw eigen waarden geven.</span><span class="sxs-lookup"><span data-stu-id="aa38f-170">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="aa38f-171">Bekijk de [video over de implementatie van dubbele sleutelversleuteling](https://youtu.be/vDWfHN_kygg) voor een stapsgewijs overzicht van de concepten in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="aa38f-171">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="aa38f-172">De video duurt ongeveer 18 minuten.</span><span class="sxs-lookup"><span data-stu-id="aa38f-172">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="aa38f-173">U volgt deze algemene stappen om Dubbele sleutelversleuteling in te stellen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-173">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="aa38f-174">Software-vereisten voor de DKE-service installeren</span><span class="sxs-lookup"><span data-stu-id="aa38f-174">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="aa38f-175">De dubbele sleutelversleutelingsopslagplaats GitHub kloon</span><span class="sxs-lookup"><span data-stu-id="aa38f-175">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="aa38f-176">Toepassingsinstellingen wijzigen</span><span class="sxs-lookup"><span data-stu-id="aa38f-176">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="aa38f-177">Testtoetsen genereren</span><span class="sxs-lookup"><span data-stu-id="aa38f-177">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="aa38f-178">Het project maken</span><span class="sxs-lookup"><span data-stu-id="aa38f-178">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="aa38f-179">De DKE-service implementeren en het sleutelopslaghuis publiceren</span><span class="sxs-lookup"><span data-stu-id="aa38f-179">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="aa38f-180">Uw implementatie valideren</span><span class="sxs-lookup"><span data-stu-id="aa38f-180">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="aa38f-181">Uw sleutelwinkel registreren</span><span class="sxs-lookup"><span data-stu-id="aa38f-181">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="aa38f-182">Gevoeligheidslabels maken met DKE</span><span class="sxs-lookup"><span data-stu-id="aa38f-182">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="aa38f-183">DKE inschakelen in uw client</span><span class="sxs-lookup"><span data-stu-id="aa38f-183">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="aa38f-184">Beveiligde bestanden migreren van HYOK-labels naar DKE-labels</span><span class="sxs-lookup"><span data-stu-id="aa38f-184">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="aa38f-185">Wanneer u klaar bent, kunt u documenten en bestanden versleutelen met DKE.</span><span class="sxs-lookup"><span data-stu-id="aa38f-185">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="aa38f-186">Zie Gevoeligheidslabels toepassen op uw bestanden en [e-mail in](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)Office.</span><span class="sxs-lookup"><span data-stu-id="aa38f-186">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="aa38f-187">Software-vereisten voor de DKE-service installeren</span><span class="sxs-lookup"><span data-stu-id="aa38f-187">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="aa38f-188">Installeer deze vereisten op de computer waarop u de DKE-service wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-188">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="aa38f-189">**.NET Core 3.1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-189">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="aa38f-190">Download en installeer de SDK van [Download .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="aa38f-190">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="aa38f-191">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-191">**Visual Studio Code**.</span></span> <span data-ttu-id="aa38f-192">Download Visual Studio code van [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="aa38f-192">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="aa38f-193">Nadat u de code Visual Studio en **selecteert** u \> **Extensies weergeven.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-193">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="aa38f-194">Installeer deze extensies.</span><span class="sxs-lookup"><span data-stu-id="aa38f-194">Install these extensions.</span></span>

- <span data-ttu-id="aa38f-195">C# voor Visual Studio code</span><span class="sxs-lookup"><span data-stu-id="aa38f-195">C# for Visual Studio Code</span></span>

- <span data-ttu-id="aa38f-196">NuGet Pakketbeheer</span><span class="sxs-lookup"><span data-stu-id="aa38f-196">NuGet Package Manager</span></span>

<span data-ttu-id="aa38f-197">**Git-resources**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-197">**Git resources**.</span></span> <span data-ttu-id="aa38f-198">Download en installeer een van de volgende opties.</span><span class="sxs-lookup"><span data-stu-id="aa38f-198">Download and install one of the following.</span></span>

- [<span data-ttu-id="aa38f-199">Git</span><span class="sxs-lookup"><span data-stu-id="aa38f-199">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="aa38f-200">GitHub Bureaublad</span><span class="sxs-lookup"><span data-stu-id="aa38f-200">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="aa38f-201">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="aa38f-201">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="aa38f-202">**OpenSSL** OpenSSL moet [zijn geïnstalleerd](https://slproweb.com/products/Win32OpenSSL.html) om [testtoetsen te genereren](#generate-test-keys) nadat u DKE hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="aa38f-202">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="aa38f-203">Zorg ervoor dat u het correct inroept vanuit het pad met omgevingsvariabelen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-203">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="aa38f-204">Zie bijvoorbeeld 'De installatiemap toevoegen aan PAD' op [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-204">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="aa38f-205">De DKE-GitHub kloon</span><span class="sxs-lookup"><span data-stu-id="aa38f-205">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="aa38f-206">Microsoft levert de DKE-bronbestanden in een GitHub opslagplaats.</span><span class="sxs-lookup"><span data-stu-id="aa38f-206">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="aa38f-207">U kloont de opslagplaats om het project lokaal te maken voor gebruik door uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-207">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="aa38f-208">De DKE GitHub repository bevindt zich op [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="aa38f-208">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="aa38f-209">De volgende instructies zijn bedoeld voor onervaren gebruikers van git of Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="aa38f-209">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="aa38f-210">Ga in uw browser naar: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="aa38f-210">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="aa38f-211">Selecteer Code aan de rechterkant van het **scherm.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-211">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="aa38f-212">Uw versie van de gebruikersinterface kan een knop **Kloon of download** weergeven.</span><span class="sxs-lookup"><span data-stu-id="aa38f-212">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="aa38f-213">Selecteer vervolgens in de vervolgkeuzebalk die wordt weergegeven het kopieerpictogram om de URL naar het klembord te kopiëren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-213">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="aa38f-214">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-214">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aa38f-215">![Kloon de serviceopslagplaats voor dubbele sleutelversleuteling van GitHub](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="aa38f-215">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="aa38f-216">Selecteer Visual Studio Opdrachtpalet  weergeven en \>  selecteer **Git: Kloon.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-216">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="aa38f-217">Als u naar de optie in de lijst wilt gaan, begint u te typen om de items te filteren en selecteert u deze `git: clone` vervolgens in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="aa38f-217">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="aa38f-218">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-218">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aa38f-219">![Visual Studio Optie Code GIT:Kloon](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="aa38f-219">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="aa38f-220">Plak in het tekstvak de URL die u hebt gekopieerd van Git en selecteer **Kloon uit GitHub.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-220">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="aa38f-221">Blader in **het dialoogvenster Map** selecteren dat wordt weergegeven naar een locatie om de opslagplaats op te slaan en selecteer deze.</span><span class="sxs-lookup"><span data-stu-id="aa38f-221">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="aa38f-222">Selecteer bij de prompt **Openen**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-222">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="aa38f-223">De opslagplaats wordt geopend in Visual Studio Code en geeft de huidige Git-branch linksonder weer.</span><span class="sxs-lookup"><span data-stu-id="aa38f-223">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="aa38f-224">De vertakking moet bijvoorbeeld hoofd **zijn.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-224">For example,  The branch should be **main**.</span></span> <span data-ttu-id="aa38f-225">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-225">For example:</span></span>

   ![Schermafbeelding van de DKE-repo in Visual Studio Code waarin de hoofdtak wordt weergegeven](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="aa38f-227">Als u niet in de hoofdtak zit, moet u deze selecteren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-227">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="aa38f-228">In Visual Studio Code selecteert u de vertakking en kiest u **hoofd** in de lijst met vertakkingen die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="aa38f-228">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="aa38f-229">Als u de hoofdtak selecteert, hebt u de juiste bestanden om het project te maken.</span><span class="sxs-lookup"><span data-stu-id="aa38f-229">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="aa38f-230">Als u niet de juiste vertakking kiest, mislukt de implementatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-230">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="aa38f-231">Uw DKE-bronopslagplaats is nu lokaal ingesteld.</span><span class="sxs-lookup"><span data-stu-id="aa38f-231">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="aa38f-232">Wijzig vervolgens [de toepassingsinstellingen](#modify-application-settings) voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-232">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="aa38f-233">Toepassingsinstellingen wijzigen</span><span class="sxs-lookup"><span data-stu-id="aa38f-233">Modify application settings</span></span>

<span data-ttu-id="aa38f-234">Als u de DKE-service wilt implementeren, moet u de volgende typen toepassingsinstellingen wijzigen:</span><span class="sxs-lookup"><span data-stu-id="aa38f-234">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="aa38f-235">Toegangsinstellingen voor sleutel</span><span class="sxs-lookup"><span data-stu-id="aa38f-235">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="aa38f-236">Tenant- en sleutelinstellingen</span><span class="sxs-lookup"><span data-stu-id="aa38f-236">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="aa38f-237">U wijzigt de toepassingsinstellingen in appsettings.jsbestand.</span><span class="sxs-lookup"><span data-stu-id="aa38f-237">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="aa38f-238">Dit bestand bevindt zich in de DoubleKeyEncryptionService repo die u lokaal hebt gekloond onder DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="aa38f-238">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="aa38f-239">In Visual Studio code kunt u bijvoorbeeld naar het bestand bladeren, zoals wordt weergegeven in de volgende afbeelding.</span><span class="sxs-lookup"><span data-stu-id="aa38f-239">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![De locatie van appsettings.jsbestand voor DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="aa38f-241">Toegangsinstellingen voor sleutel</span><span class="sxs-lookup"><span data-stu-id="aa38f-241">Key access settings</span></span>

<span data-ttu-id="aa38f-242">Kies of u e-mail of rolautorisatie wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="aa38f-242">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="aa38f-243">DKE ondersteunt slechts één van deze verificatiemethoden tegelijk.</span><span class="sxs-lookup"><span data-stu-id="aa38f-243">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="aa38f-244">**E-mailautorisatie**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-244">**Email authorization**.</span></span> <span data-ttu-id="aa38f-245">Hiermee kan uw organisatie alleen toegang verlenen tot sleutels op basis van e-mailadressen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-245">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="aa38f-246">**Rolautorisatie**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-246">**Role authorization**.</span></span> <span data-ttu-id="aa38f-247">Hiermee kan uw organisatie toegang verlenen tot sleutels op basis van Active Directory-groepen en moet de webservice LDAP kunnen query's uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-247">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="aa38f-248">**Belangrijke toegangsinstellingen voor DKE instellen met behulp van e-mailautorisatie**</span><span class="sxs-lookup"><span data-stu-id="aa38f-248">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="aa38f-249">Open het **appsettings.jsbestand en** zoek de `AuthorizedEmailAddress` instelling.</span><span class="sxs-lookup"><span data-stu-id="aa38f-249">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="aa38f-250">Voeg het e-mailadres of de adressen toe die u wilt machtigen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-250">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="aa38f-251">Scheid meerdere e-mailadressen met dubbele aanhalingstekens en komma's.</span><span class="sxs-lookup"><span data-stu-id="aa38f-251">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="aa38f-252">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-252">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="aa38f-253">Zoek de `LDAPPath` instelling en verwijder de tekst tussen de dubbele `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="aa38f-253">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="aa38f-254">Laat de dubbele aanhalingstekens op hun plaats.</span><span class="sxs-lookup"><span data-stu-id="aa38f-254">Leave the double quotes in place.</span></span> <span data-ttu-id="aa38f-255">Wanneer u klaar bent, ziet de instelling er zo uit.</span><span class="sxs-lookup"><span data-stu-id="aa38f-255">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="aa38f-256">Zoek de `AuthorizedRoles` instelling en verwijder de hele regel.</span><span class="sxs-lookup"><span data-stu-id="aa38f-256">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="aa38f-257">In deze afbeelding ziet **uappsettings.jsbestand** dat correct is opgemaakt voor e-mailautorisatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-257">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![De appsettings.jsbestand met e-mailautorisatiemethode](../media/dke-email-accesssetting.png)

<span data-ttu-id="aa38f-259">**Sleuteltoegangsinstellingen voor DKE instellen met behulp van rolautorisatie**</span><span class="sxs-lookup"><span data-stu-id="aa38f-259">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="aa38f-260">Open het **appsettings.jsbestand en** zoek de `AuthorizedRoles` instelling.</span><span class="sxs-lookup"><span data-stu-id="aa38f-260">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="aa38f-261">Voeg de namen van de Active Directory-groep toe die u wilt machtigen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-261">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="aa38f-262">Scheid meerdere groepsnamen met dubbele aanhalingstekens en komma's.</span><span class="sxs-lookup"><span data-stu-id="aa38f-262">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="aa38f-263">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-263">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="aa38f-264">Zoek de `LDAPPath` instelling en voeg het Active Directory-domein toe.</span><span class="sxs-lookup"><span data-stu-id="aa38f-264">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="aa38f-265">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-265">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="aa38f-266">Zoek de `AuthorizedEmailAddress` instelling en verwijder de hele regel.</span><span class="sxs-lookup"><span data-stu-id="aa38f-266">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="aa38f-267">In deze afbeelding ziet **uappsettings.jsbestand** correct is opgemaakt voor rolautorisatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-267">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsin bestand met de methode voor rolautorisatie](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="aa38f-269">Tenant- en sleutelinstellingen</span><span class="sxs-lookup"><span data-stu-id="aa38f-269">Tenant and key settings</span></span>

<span data-ttu-id="aa38f-270">DKE-tenant- en sleutelinstellingen bevinden zich in de **appsettings.jsbestand.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-270">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="aa38f-271">**Tenant- en sleutelinstellingen voor DKE configureren**</span><span class="sxs-lookup"><span data-stu-id="aa38f-271">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="aa38f-272">Open het **appsettings.jsbestand.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-272">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="aa38f-273">Zoek de `ValidIssuers` instelling en vervang deze door uw `<tenantid>` tenant-id.</span><span class="sxs-lookup"><span data-stu-id="aa38f-273">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="aa38f-274">U kunt uw tenant-id vinden door naar de Azure-portal te gaan en de [tenanteigenschappen weer te geven.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="aa38f-274">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="aa38f-275">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-275">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```
> [!NOTE]
> <span data-ttu-id="aa38f-276">Als u externe B2B-toegang tot uw sleutelopslag wilt inschakelen, moet u deze externe tenants ook opnemen als onderdeel van de lijst met geldige uitgifters.</span><span class="sxs-lookup"><span data-stu-id="aa38f-276">If you want to enable external B2B access to your key store, you will also need to include these external tenants as part of the valid issuers' list.</span></span>

<span data-ttu-id="aa38f-277">Zoek de `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="aa38f-277">Locate the `JwtAudience`.</span></span> <span data-ttu-id="aa38f-278">Vervang `<yourhostname>` deze door de hostnaam van de computer waarop de DKE-service wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="aa38f-278">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="aa38f-279">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-279">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="aa38f-280">De waarde voor `JwtAudience` moet exact overeenkomen met de naam van uw host.</span><span class="sxs-lookup"><span data-stu-id="aa38f-280">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="aa38f-281">U kunt **localhost:5001 gebruiken** tijdens debuggen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-281">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="aa38f-282">Als u echter klaar bent met debuggen, moet u deze waarde bijwerken naar de hostnaam van de server.</span><span class="sxs-lookup"><span data-stu-id="aa38f-282">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="aa38f-283">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="aa38f-283">`TestKeys:Name`.</span></span> <span data-ttu-id="aa38f-284">Voer een naam voor uw sleutel in.</span><span class="sxs-lookup"><span data-stu-id="aa38f-284">Enter a name for your key.</span></span> <span data-ttu-id="aa38f-285">Bijvoorbeeld: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="aa38f-285">For example: `TestKey1`</span></span>
- <span data-ttu-id="aa38f-286">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="aa38f-286">`TestKeys:Id`.</span></span> <span data-ttu-id="aa38f-287">Maak een GUID en voer deze in als de `TestKeys:ID` waarde.</span><span class="sxs-lookup"><span data-stu-id="aa38f-287">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="aa38f-288">Bijvoorbeeld `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="aa38f-288">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="aa38f-289">U kunt een site zoals [Online GUID Generator](https://guidgenerator.com/) gebruiken om willekeurig een GUID te genereren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-289">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="aa38f-290">In deze afbeelding ziet u de juiste indeling voor tenant- en toetseninstellingen in **appsettings.jsop**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-290">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="aa38f-291">`LDAPPath` is geconfigureerd voor rolautorisatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-291">`LDAPPath` is configured for role authorization.</span></span>

![Toont de juiste tenant- en sleutelinstellingen voor DKE in appsettings.jsbestand.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="aa38f-293">Testtoetsen genereren</span><span class="sxs-lookup"><span data-stu-id="aa38f-293">Generate test keys</span></span>

<span data-ttu-id="aa38f-294">Wanneer u de toepassingsinstellingen hebt gedefinieerd, kunt u openbare en persoonlijke testtoetsen genereren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-294">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="aa38f-295">Sleutels genereren:</span><span class="sxs-lookup"><span data-stu-id="aa38f-295">To generate keys:</span></span>

1. <span data-ttu-id="aa38f-296">Voer in Windows startmenu de Opdrachtprompt OpenSSL uit.</span><span class="sxs-lookup"><span data-stu-id="aa38f-296">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="aa38f-297">Ga naar de map waar u de toetstoetsen wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="aa38f-297">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="aa38f-298">De bestanden die u maakt door de stappen in deze taak uit te voeren, worden in dezelfde map opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-298">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="aa38f-299">Genereer de nieuwe toets.</span><span class="sxs-lookup"><span data-stu-id="aa38f-299">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="aa38f-300">Genereer de persoonlijke sleutel.</span><span class="sxs-lookup"><span data-stu-id="aa38f-300">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="aa38f-301">Genereer de openbare sleutel.</span><span class="sxs-lookup"><span data-stu-id="aa38f-301">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="aa38f-302">Open **pubkeyonly.pem** in een teksteditor.</span><span class="sxs-lookup"><span data-stu-id="aa38f-302">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="aa38f-303">Kopieer alle inhoud in het **bestand pubkeyonly.pem,** behalve de eerste en laatste regels, naar de sectie van het bestand `PublicPem`appsettings.js **bestand.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-303">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="aa38f-304">Open **privkeynopass.pem** in een teksteditor.</span><span class="sxs-lookup"><span data-stu-id="aa38f-304">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="aa38f-305">Kopieer alle inhoud in het **bestand privkeynopass.pem,** behalve de eerste en laatste regels, naar de sectie van hetappsettings.js`PrivatePem` **bestand.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-305">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="aa38f-306">Verwijder alle lege spaties en nieuwelines in zowel de `PublicPem` `PrivatePem` secties als de secties.</span><span class="sxs-lookup"><span data-stu-id="aa38f-306">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="aa38f-307">Wanneer u deze inhoud kopieert, verwijdert u geen van de PEM-gegevens.</span><span class="sxs-lookup"><span data-stu-id="aa38f-307">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="aa38f-308">Blader Visual Studio code naar het **bestand Startup.cs.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-308">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="aa38f-309">Dit bestand bevindt zich in de DoubleKeyEncryptionService repo die u lokaal hebt gekloond onder DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="aa38f-309">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="aa38f-310">Zoek de volgende regels:</span><span class="sxs-lookup"><span data-stu-id="aa38f-310">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="aa38f-311">Vervang deze regels door de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="aa38f-311">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="aa38f-312">De eindresultaten moeten er ongeveer als volgt uitzien.</span><span class="sxs-lookup"><span data-stu-id="aa38f-312">The end results should look similar to the following.</span></span>

    ![startup.cs-bestand voor openbaar voorbeeld](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="aa38f-314">Nu bent u klaar om uw [DKE-project te bouwen.](#build-the-project)</span><span class="sxs-lookup"><span data-stu-id="aa38f-314">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="aa38f-315">Het project maken</span><span class="sxs-lookup"><span data-stu-id="aa38f-315">Build the project</span></span>

<span data-ttu-id="aa38f-316">Gebruik de volgende instructies om het DKE-project lokaal te maken:</span><span class="sxs-lookup"><span data-stu-id="aa38f-316">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="aa38f-317">Selecteer Visual Studio opdrachtpalet weergeven in de DKE-serviceopslagplaats in de DKE-servicebibliotheek en typ  \>  **build** op de prompt.</span><span class="sxs-lookup"><span data-stu-id="aa38f-317">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="aa38f-318">Kies taken in de **lijst: Buildtaak uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-318">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="aa38f-319">Als er geen buildtaken zijn gevonden, selecteert u **Buildtaak configureren** en maakt u er een voor .NET-kern als volgt.</span><span class="sxs-lookup"><span data-stu-id="aa38f-319">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Ontbrekende buildtaak configureren voor .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="aa38f-321">Kies **Maken tasks.jsop van sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-321">Choose **Create tasks.json from template**.</span></span>

      ![Een tasks.jsbestand maken op basis van sjabloon voor DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="aa38f-323">Selecteer .NET Core in de lijst met **sjabloontypen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-323">From the list of template types, select **.NET Core**.</span></span>

      ![Selecteer de juiste sjabloon voor DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="aa38f-325">Zoek in de buildsectie het pad naar het **bestand customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-325">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="aa38f-326">Als deze er niet is, voegt u de volgende regel toe:</span><span class="sxs-lookup"><span data-stu-id="aa38f-326">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="aa38f-327">Voer de build opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="aa38f-327">Run the build again.</span></span>

3. <span data-ttu-id="aa38f-328">Controleer of er geen rode fouten zijn in het uitvoervenster.</span><span class="sxs-lookup"><span data-stu-id="aa38f-328">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="aa38f-329">Als er rode fouten zijn, controleert u de uitvoer van de console.</span><span class="sxs-lookup"><span data-stu-id="aa38f-329">If there are red errors, check the console output.</span></span> <span data-ttu-id="aa38f-330">Controleer of u alle vorige stappen correct hebt uitgevoerd en dat de juiste buildversies aanwezig zijn.</span><span class="sxs-lookup"><span data-stu-id="aa38f-330">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="aa38f-331">Selecteer  \> **Foutopsporing starten uitvoeren** om het proces te debuggen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-331">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="aa38f-332">Als u wordt gevraagd een omgeving te selecteren, selecteert **u .NET-kern.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-332">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="aa38f-333">De .NET-kerndebugger wordt meestal op `https://localhost:5001` .</span><span class="sxs-lookup"><span data-stu-id="aa38f-333">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="aa38f-334">Als u de toets wilt weergeven, gaat u naar een slash (/) en de `https://localhost:5001` naam van de sleutel.</span><span class="sxs-lookup"><span data-stu-id="aa38f-334">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="aa38f-335">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-335">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="aa38f-336">De toets moet worden weergegeven in de JSON-indeling.</span><span class="sxs-lookup"><span data-stu-id="aa38f-336">The key should display in JSON format.</span></span>

<span data-ttu-id="aa38f-337">Uw installatie is nu voltooid.</span><span class="sxs-lookup"><span data-stu-id="aa38f-337">Your setup is now complete.</span></span> <span data-ttu-id="aa38f-338">Voordat u de keystore publiceert, controleert u in appsettings.jsde instelling JwtAudience of de waarde voor hostnaam exact overeenkomt met de naam van uw App Service-host.</span><span class="sxs-lookup"><span data-stu-id="aa38f-338">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="aa38f-339">Mogelijk hebt u deze gewijzigd in localhost om problemen met de build op te lossen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-339">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="aa38f-340">De DKE-service implementeren en het sleutelopslaghuis publiceren</span><span class="sxs-lookup"><span data-stu-id="aa38f-340">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="aa38f-341">Implementeer de service voor productie-implementaties in een cloud van derden of publiceer deze naar [een on-premises systeem.](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)</span><span class="sxs-lookup"><span data-stu-id="aa38f-341">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1).</span></span>

<span data-ttu-id="aa38f-342">Mogelijk geeft u de voorkeur aan andere methoden om uw sleutels te implementeren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-342">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="aa38f-343">Selecteer de methode die het beste werkt voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa38f-343">Select the method that works best for your organization.</span></span>

<span data-ttu-id="aa38f-344">Voor pilotimplementaties kunt u implementeren in Azure en meteen aan de slag gaan.</span><span class="sxs-lookup"><span data-stu-id="aa38f-344">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="aa38f-345">**Een Azure Web App-exemplaar maken om uw DKE-implementatie te hosten**</span><span class="sxs-lookup"><span data-stu-id="aa38f-345">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="aa38f-346">Als u het sleutelopslagopslag wilt publiceren, maakt u een Azure App Service-exemplaar om uw DKE-implementatie te hosten.</span><span class="sxs-lookup"><span data-stu-id="aa38f-346">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="aa38f-347">Vervolgens publiceert u de gegenereerde sleutels voor Azure.</span><span class="sxs-lookup"><span data-stu-id="aa38f-347">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="aa38f-348">Meld u in uw browser aan bij de [Microsoft Azure portal](https://ms.portal.azure.com)en ga naar **App Services**  >  **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-348">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="aa38f-349">Selecteer uw abonnement en resourcegroep en definieert de details van uw exemplaar.</span><span class="sxs-lookup"><span data-stu-id="aa38f-349">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="aa38f-350">Voer de hostnaam in van de computer waarop u de DKE-service wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-350">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="aa38f-351">Zorg ervoor dat deze dezelfde naam heeft als de naam die is gedefinieerd voor de instelling JwtAudience in [**hetappsettings.jsbestand.**](#tenant-and-key-settings)</span><span class="sxs-lookup"><span data-stu-id="aa38f-351">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="aa38f-352">De waarde die u voor de naam opwaardeerd, is ook de WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="aa38f-352">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="aa38f-353">Selecteer **voor Publiceren,** **selecteer code** en selecteer voor **Runtime stack** **.NET Core 3.1.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-353">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="aa38f-354">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-354">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aa38f-355">![Uw app-service toevoegen](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="aa38f-355">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="aa38f-356">Selecteer onder aan de pagina **Controleren + maken** en selecteer vervolgens **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-356">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="aa38f-357">Ga op een van de volgende stappen te werk om de gegenereerde sleutels te publiceren:</span><span class="sxs-lookup"><span data-stu-id="aa38f-357">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="aa38f-358">Publiceren via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="aa38f-358">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="aa38f-359">Publiceren via FTP</span><span class="sxs-lookup"><span data-stu-id="aa38f-359">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="aa38f-360">Publiceren via Visual Studio 2019 of hoger</span><span class="sxs-lookup"><span data-stu-id="aa38f-360">Publish via Visual Studio 2019 or later</span></span>](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="aa38f-361">Publiceren via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="aa38f-361">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="aa38f-362">Ga naar `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="aa38f-362">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="aa38f-363">Bijvoorbeeld: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="aa38f-363">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="aa38f-364">Ga in de codebase voor de sleutelwinkel naar de map **customer-key-store\src\customer-key-store** en controleer of deze map het **bestand customerkeystore.csproj** bevat.</span><span class="sxs-lookup"><span data-stu-id="aa38f-364">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="aa38f-365">Uitvoeren: **dotnet publiceren**</span><span class="sxs-lookup"><span data-stu-id="aa38f-365">Run: **dotnet publish**</span></span>

   <span data-ttu-id="aa38f-366">In het uitvoervenster wordt de adreslijst weergegeven waar de publicatie is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="aa38f-366">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="aa38f-367">Bijvoorbeeld: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="aa38f-367">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="aa38f-368">Verzend alle bestanden in de adreslijst publiceren naar een .zip bestand.</span><span class="sxs-lookup"><span data-stu-id="aa38f-368">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="aa38f-369">Wanneer u het .zip bestand maakt, moet u ervoor zorgen dat alle bestanden in de adreslijst zich op het hoofdniveau van het .zip bestand.</span><span class="sxs-lookup"><span data-stu-id="aa38f-369">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="aa38f-370">Sleep en zet het .zip bestand dat u maakt naar de ZipDeployUI-site die u hierboven hebt geopend.</span><span class="sxs-lookup"><span data-stu-id="aa38f-370">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="aa38f-371">Bijvoorbeeld: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="aa38f-371">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="aa38f-372">DKE wordt geïmplementeerd en u kunt naar de testtoetsen bladeren die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="aa38f-372">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="aa38f-373">Ga verder [met Uw implementatie valideren](#validate-your-deployment) hieronder.</span><span class="sxs-lookup"><span data-stu-id="aa38f-373">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="aa38f-374">Publiceren via FTP</span><span class="sxs-lookup"><span data-stu-id="aa38f-374">Publish via FTP</span></span>

1. <span data-ttu-id="aa38f-375">Verbinding maken app-service die u hierboven hebt [gemaakt.](#deploy-the-dke-service-and-publish-the-key-store)</span><span class="sxs-lookup"><span data-stu-id="aa38f-375">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="aa38f-376">Ga in uw browser naar: **Azure Portal**  >  **App Service** Deployment  >  **Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-376">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="aa38f-377">Kopieer de verbindingsreeksen die worden weergegeven naar een lokaal bestand.</span><span class="sxs-lookup"><span data-stu-id="aa38f-377">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="aa38f-378">U gebruikt deze tekenreeksen om verbinding te maken met de Web App-service en bestanden te uploaden via FTP.</span><span class="sxs-lookup"><span data-stu-id="aa38f-378">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="aa38f-379">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-379">For example:</span></span>

   ![Verbindingsreeksen kopiëren vanuit het FTP-dashboard](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="aa38f-381">Ga in de codebase voor de sleutelopslag naar de **adreslijst customer-key-store\src\customer-key-store.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-381">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="aa38f-382">Controleer of deze adreslijst het **bestand customerkeystore.csproj** bevat.</span><span class="sxs-lookup"><span data-stu-id="aa38f-382">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="aa38f-383">Uitvoeren: **dotnet publiceren**</span><span class="sxs-lookup"><span data-stu-id="aa38f-383">Run: **dotnet publish**</span></span>

   <span data-ttu-id="aa38f-384">De uitvoer bevat de adreslijst waar de publicatie is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="aa38f-384">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="aa38f-385">Bijvoorbeeld: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="aa38f-385">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="aa38f-386">Verzend alle bestanden in de adreslijst publiceren naar een zip-bestand.</span><span class="sxs-lookup"><span data-stu-id="aa38f-386">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="aa38f-387">Wanneer u het .zip bestand maakt, moet u ervoor zorgen dat alle bestanden in de adreslijst zich op het hoofdniveau van het .zip bestand.</span><span class="sxs-lookup"><span data-stu-id="aa38f-387">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="aa38f-388">Gebruik vanuit uw FTP-client de verbindingsgegevens die u hebt gekopieerd om verbinding te maken met uw App Service.</span><span class="sxs-lookup"><span data-stu-id="aa38f-388">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="aa38f-389">Upload het .zip bestand dat u in de vorige stap hebt gemaakt naar de hoofdadreslijst van uw Web App.</span><span class="sxs-lookup"><span data-stu-id="aa38f-389">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="aa38f-390">DKE wordt geïmplementeerd en u kunt naar de testtoetsen bladeren die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="aa38f-390">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="aa38f-391">Valideer [vervolgens uw implementatie.](#validate-your-deployment)</span><span class="sxs-lookup"><span data-stu-id="aa38f-391">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="aa38f-392">Uw implementatie valideren</span><span class="sxs-lookup"><span data-stu-id="aa38f-392">Validate your deployment</span></span>

<span data-ttu-id="aa38f-393">Nadat u DKE met een van de hierboven beschreven methoden heeft geïmplementeerd, valideert u de implementatie en de instellingen voor het sleutelopslagopslag.</span><span class="sxs-lookup"><span data-stu-id="aa38f-393">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="aa38f-394">Uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="aa38f-394">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="aa38f-395">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-395">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="aa38f-396">Zorg ervoor dat er geen fouten worden weergegeven in de uitvoer.</span><span class="sxs-lookup"><span data-stu-id="aa38f-396">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="aa38f-397">Wanneer u klaar bent, registreert [u uw sleutelwinkel.](#register-your-key-store)</span><span class="sxs-lookup"><span data-stu-id="aa38f-397">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="aa38f-398">De sleutelnaam is hoofdsyteergevoelig.</span><span class="sxs-lookup"><span data-stu-id="aa38f-398">The key name is case sensitive.</span></span> <span data-ttu-id="aa38f-399">Voer de sleutelnaam in zoals deze wordt weergegeven in appsettings.jsbestand.</span><span class="sxs-lookup"><span data-stu-id="aa38f-399">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="aa38f-400">Uw sleutelwinkel registreren</span><span class="sxs-lookup"><span data-stu-id="aa38f-400">Register your key store</span></span>

<span data-ttu-id="aa38f-401">Met de volgende stappen kunt u uw DKE-service registreren.</span><span class="sxs-lookup"><span data-stu-id="aa38f-401">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="aa38f-402">Het registreren van uw DKE-service is de laatste stap bij het implementeren van DKE voordat u labels kunt gaan maken.</span><span class="sxs-lookup"><span data-stu-id="aa38f-402">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="aa38f-403">De DKE-service registreren:</span><span class="sxs-lookup"><span data-stu-id="aa38f-403">To register the DKE service:</span></span>

1. <span data-ttu-id="aa38f-404">Open in uw browser de [Microsoft Azure portal](https://ms.portal.azure.com/)en ga naar **Alle** \> **identiteitsregistraties voor** \> **services.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-404">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="aa38f-405">Selecteer **Nieuwe registratie** en voer een duidelijke naam in.</span><span class="sxs-lookup"><span data-stu-id="aa38f-405">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="aa38f-406">Selecteer een accounttype in de weergegeven opties.</span><span class="sxs-lookup"><span data-stu-id="aa38f-406">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="aa38f-407">Als u een Microsoft Azure gebruikt met een niet-aangepast domein, zoals **onmicrosoft.com,** selecteert u Alleen accounts in deze organisatiemap **(Alleen Microsoft - Enkele tenant).**</span><span class="sxs-lookup"><span data-stu-id="aa38f-407">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="aa38f-408">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-408">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aa38f-409">![Nieuwe app-registratie](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="aa38f-409">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="aa38f-410">Selecteer onder aan de pagina Registreren **om** de nieuwe app-registratie te maken.</span><span class="sxs-lookup"><span data-stu-id="aa38f-410">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="aa38f-411">Selecteer in de nieuwe app-registratie in het linkerdeelvenster onder **Beheren** de optie **Verificatie**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-411">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="aa38f-412">Selecteer **Een platform toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-412">Select **Add a platform**.</span></span>

7. <span data-ttu-id="aa38f-413">Selecteer in **de pop-up Platforms** configureren de optie **Web**.</span><span class="sxs-lookup"><span data-stu-id="aa38f-413">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="aa38f-414">Voer **onder Omleidings-URL's** de URI in van uw dubbele-sleutelversleutelingsservice.</span><span class="sxs-lookup"><span data-stu-id="aa38f-414">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="aa38f-415">Voer de URL van de App-service in, inclusief zowel de hostnaam als het domein.</span><span class="sxs-lookup"><span data-stu-id="aa38f-415">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="aa38f-416">Bijvoorbeeld: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="aa38f-416">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="aa38f-417">De URL die u typt, moet overeenkomen met de hostnaam waar uw DKE-service is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="aa38f-417">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="aa38f-418">Als u lokaal test met Visual Studio, gebruikt u **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="aa38f-418">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="aa38f-419">In alle gevallen moet het schema **https zijn.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-419">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="aa38f-420">Controleer of de hostnaam exact overeenkomt met de hostnaam van uw App Service.</span><span class="sxs-lookup"><span data-stu-id="aa38f-420">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="aa38f-421">Mogelijk hebt u deze gewijzigd om `localhost` problemen met de build op te lossen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-421">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="aa38f-422">In **appsettings.jsis** deze waarde de hostnaam die u hebt ingesteld voor `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="aa38f-422">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="aa38f-423">Schakel **onder Impliciet verlenen** het selectievakje **Id-tokens** in.</span><span class="sxs-lookup"><span data-stu-id="aa38f-423">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="aa38f-424">Selecteer **Opslaan** om de wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="aa38f-424">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="aa38f-425">Selecteer in het linkerdeelvenster **Een API weergeven** en selecteer vervolgens naast Toepassings-id URI de optie **Instellen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-425">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="aa38f-426">Selecteer nog steeds op de pagina Een **API blootstellen** in **de scopes** die door dit API-gebied zijn gedefinieerd, de optie **Een bereik toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-426">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="aa38f-427">In het nieuwe bereik:</span><span class="sxs-lookup"><span data-stu-id="aa38f-427">In the new scope:</span></span>

    1. <span data-ttu-id="aa38f-428">De naam van het bereik definiëren **als user_impersonation.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-428">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="aa38f-429">Selecteer de beheerders en gebruikers die toestemming kunnen geven.</span><span class="sxs-lookup"><span data-stu-id="aa38f-429">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="aa38f-430">Definieer de resterende waarden die nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="aa38f-430">Define any remaining values required.</span></span>

    4. <span data-ttu-id="aa38f-431">Selecteer **Bereik toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-431">Select **Add scope**.</span></span>

    5. <span data-ttu-id="aa38f-432">Selecteer **Opslaan** bovenaan om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="aa38f-432">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="aa38f-433">Selecteer nog steeds **op de pagina** Een API openen in het gebied **Geautoriseerde clienttoepassingen** de optie **Een clienttoepassing toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-433">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="aa38f-434">In de nieuwe clienttoepassing:</span><span class="sxs-lookup"><span data-stu-id="aa38f-434">In the new client application:</span></span>

    1. <span data-ttu-id="aa38f-435">De client-id definiëren als `d3590ed6-52b3-4102-aeff-aad2292ab01c` .</span><span class="sxs-lookup"><span data-stu-id="aa38f-435">Define the Client ID as `d3590ed6-52b3-4102-aeff-aad2292ab01c`.</span></span> <span data-ttu-id="aa38f-436">Deze waarde is de Microsoft Office client-id en stelt u Office toegangstoken te verkrijgen voor uw sleutelopslag.</span><span class="sxs-lookup"><span data-stu-id="aa38f-436">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="aa38f-437">Selecteer **onder Geautoriseerde bereik de** **user_impersonation** bereik.</span><span class="sxs-lookup"><span data-stu-id="aa38f-437">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="aa38f-438">Selecteer **Toepassing toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aa38f-438">Select **Add application**.</span></span>

    4. <span data-ttu-id="aa38f-439">Selecteer **Opslaan** bovenaan om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="aa38f-439">Select **Save** at the top to save your changes.</span></span>

    5. <span data-ttu-id="aa38f-440">Herhaal deze stappen, maar definieert deze keer de client-id als `c00e9d32-3c8d-4a7d-832b-029040e7db99` .</span><span class="sxs-lookup"><span data-stu-id="aa38f-440">Repeat these steps, but this time, define the client ID as `c00e9d32-3c8d-4a7d-832b-029040e7db99`.</span></span> <span data-ttu-id="aa38f-441">Deze waarde is de geïntegreerde labelingclient-id van Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="aa38f-441">This value is the Azure Information Protection unified labeling client ID.</span></span> 

<span data-ttu-id="aa38f-442">Uw DKE-service is nu geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="aa38f-442">Your DKE service is now registered.</span></span> <span data-ttu-id="aa38f-443">Ga door met [DKE labels te maken.](#create-sensitivity-labels-using-dke)</span><span class="sxs-lookup"><span data-stu-id="aa38f-443">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="aa38f-444">Gevoeligheidslabels maken met DKE</span><span class="sxs-lookup"><span data-stu-id="aa38f-444">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="aa38f-445">Maak in Microsoft 365 compliancecentrum een nieuw gevoeligheidslabel en pas versleuteling toe zoals u anders zou doen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-445">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="aa38f-446">Selecteer **Dubbele sleutelversleuteling gebruiken** en voer de EINDPUNT-URL voor uw sleutel in.</span><span class="sxs-lookup"><span data-stu-id="aa38f-446">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="aa38f-447">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa38f-447">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="aa38f-448">![Selecteer Dubbele sleutelversleuteling gebruiken in het Microsoft 365 compliancecentrum](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="aa38f-448">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="aa38f-449">Alle DKE-labels die u toevoegt, worden weergegeven voor gebruikers in de meest recente versies van Microsoft 365-apps voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="aa38f-449">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="aa38f-450">Het kan tot 24 uur duren voordat de clients worden vernieuwd met de nieuwe labels.</span><span class="sxs-lookup"><span data-stu-id="aa38f-450">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="aa38f-451">DKE inschakelen in uw client</span><span class="sxs-lookup"><span data-stu-id="aa38f-451">Enable DKE in your client</span></span>

<span data-ttu-id="aa38f-452">Als u een insider Office, is DKE voor u ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="aa38f-452">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="aa38f-453">Schakel anders DKE voor uw client in door de volgende registersleutels toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="aa38f-453">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="aa38f-454">Beveiligde bestanden migreren van HYOK-labels naar DKE-labels</span><span class="sxs-lookup"><span data-stu-id="aa38f-454">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="aa38f-455">Als u klaar bent met het instellen van DKE, kunt u de inhoud die u hebt beveiligd met HYOK-labels migreren naar DKE-labels.</span><span class="sxs-lookup"><span data-stu-id="aa38f-455">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="aa38f-456">Als u wilt migreren, gebruikt u de AIP-scanner.</span><span class="sxs-lookup"><span data-stu-id="aa38f-456">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="aa38f-457">Zie Wat is de geïntegreerde labelscanner van [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)om aan de slag te gaan met de scanner.</span><span class="sxs-lookup"><span data-stu-id="aa38f-457">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="aa38f-458">Als u geen inhoud migreert, blijft de met HYOK beveiligde inhoud ongewijzigd.</span><span class="sxs-lookup"><span data-stu-id="aa38f-458">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
