---
title: Beleidstips voor preventie van gegevensverlies (DLP)
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Lees hoe u een beleidstip toevoegt aan een DLP-beleid (Data Loss Prevention) om een gebruiker te laten weten dat deze werkt met inhoud die strijd is met een DLP-beleid.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 36e4d4f96146b51e0b31731c9e93222eed767045
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903800"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="a6f98-103">Beleidstips voor preventie van gegevensverlies (DLP)</span><span class="sxs-lookup"><span data-stu-id="a6f98-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="a6f98-104">DLP-beleidstips in Outlook Web Access worden ondersteund voor alle voorwaarden, uitzonderingen en acties die van toepassing zijn op Exchange-werkbelasting in een DLP-beleid, behalve de volgende:</span><span class="sxs-lookup"><span data-stu-id="a6f98-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="a6f98-105">**Voorwaarden:**</span><span class="sxs-lookup"><span data-stu-id="a6f98-105">**Conditions:**</span></span>

- <span data-ttu-id="a6f98-106">Afzender is</span><span class="sxs-lookup"><span data-stu-id="a6f98-106">Sender Is</span></span>
- <span data-ttu-id="a6f98-107">Sender Domain Is</span><span class="sxs-lookup"><span data-stu-id="a6f98-107">Sender Domain Is</span></span>
- <span data-ttu-id="a6f98-108">Geadresseerde is lid van</span><span class="sxs-lookup"><span data-stu-id="a6f98-108">Recipient is a member of</span></span>
- <span data-ttu-id="a6f98-109">Koptekst bevat woorden of woordgroepen</span><span class="sxs-lookup"><span data-stu-id="a6f98-109">Header contains words or phrases</span></span>
- <span data-ttu-id="a6f98-110">Koptekst komt overeen met patronen</span><span class="sxs-lookup"><span data-stu-id="a6f98-110">Header matches patterns</span></span>
- <span data-ttu-id="a6f98-111">De documentgrootte is gelijk aan of groter dan</span><span class="sxs-lookup"><span data-stu-id="a6f98-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="a6f98-112">Berichttype is</span><span class="sxs-lookup"><span data-stu-id="a6f98-112">Message type is</span></span>
- <span data-ttu-id="a6f98-113">Het belang van berichten is</span><span class="sxs-lookup"><span data-stu-id="a6f98-113">Message importance is</span></span>
- <span data-ttu-id="a6f98-114">Inhoudstekenset bevat woorden</span><span class="sxs-lookup"><span data-stu-id="a6f98-114">Content character set contains words</span></span>
- <span data-ttu-id="a6f98-115">Onderwerp of lichaam bevat woorden of woordgroepen</span><span class="sxs-lookup"><span data-stu-id="a6f98-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="a6f98-116">Patronen voor onderwerp of lichaam</span><span class="sxs-lookup"><span data-stu-id="a6f98-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="a6f98-117">Inhoudstekenset bevat woorden</span><span class="sxs-lookup"><span data-stu-id="a6f98-117">Content character set contains words</span></span>
- <span data-ttu-id="a6f98-118">Inhoud wordt ontvangen van</span><span class="sxs-lookup"><span data-stu-id="a6f98-118">Content is received from</span></span>
- <span data-ttu-id="a6f98-119">Heeft afzender de beleidstip overgenomen</span><span class="sxs-lookup"><span data-stu-id="a6f98-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="a6f98-120">Berichtgrootte is gelijk aan of groter dan</span><span class="sxs-lookup"><span data-stu-id="a6f98-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="a6f98-121">Ad-kenmerk Afzender bevat woorden of woordgroepen</span><span class="sxs-lookup"><span data-stu-id="a6f98-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="a6f98-122">Ad-kenmerk Afzender komt overeen met patronen</span><span class="sxs-lookup"><span data-stu-id="a6f98-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="a6f98-123">Documentinhoud bevat woorden of woordgroepen</span><span class="sxs-lookup"><span data-stu-id="a6f98-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="a6f98-124">Documentinhoud komt overeen met patronen</span><span class="sxs-lookup"><span data-stu-id="a6f98-124">Document content matches patterns</span></span>

<span data-ttu-id="a6f98-125">**Acties:**</span><span class="sxs-lookup"><span data-stu-id="a6f98-125">**Actions:**</span></span>

- <span data-ttu-id="a6f98-126">Het bericht ter goedkeuring doorsturen naar de afzendermanager</span><span class="sxs-lookup"><span data-stu-id="a6f98-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="a6f98-127">Het bericht ter goedkeuring doorsturen naar specifieke goedkeurders</span><span class="sxs-lookup"><span data-stu-id="a6f98-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="a6f98-128">Het bericht omleiden naar specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="a6f98-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="a6f98-129">Geadresseerden toevoegen aan het vak Aan</span><span class="sxs-lookup"><span data-stu-id="a6f98-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="a6f98-130">Geadresseerden toevoegen aan het cc-vak</span><span class="sxs-lookup"><span data-stu-id="a6f98-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="a6f98-131">Geadresseerden toevoegen aan het BCC-vak</span><span class="sxs-lookup"><span data-stu-id="a6f98-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="a6f98-132">Manager van de afzender toevoegen als geadresseerde</span><span class="sxs-lookup"><span data-stu-id="a6f98-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="a6f98-133">HTML-vrijwaring toevoegen</span><span class="sxs-lookup"><span data-stu-id="a6f98-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="a6f98-134">Voorbereidend e-mailonderwerp</span><span class="sxs-lookup"><span data-stu-id="a6f98-134">Prepend email subject</span></span>
- <span data-ttu-id="a6f98-135">O365-berichtversleuteling en rechtenbescherming verwijderen</span><span class="sxs-lookup"><span data-stu-id="a6f98-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="a6f98-136">Outlook 2013 en hoger ondersteunt het weergeven van beleidstips voor slechts enkele voorwaarden en uitzonderingen</span><span class="sxs-lookup"><span data-stu-id="a6f98-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="a6f98-137">Momenteel ondersteunt Outlook 2013 en hoger het weergeven van beleidstips voor beleidsregels die geen voorwaarde of uitzondering bevatten, afgezien van de onderstaande voorwaarden en bijbehorende uitzonderingen:</span><span class="sxs-lookup"><span data-stu-id="a6f98-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="a6f98-138">Inhoud bevat (werkt alleen voor gevoelige informatietypen.</span><span class="sxs-lookup"><span data-stu-id="a6f98-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="a6f98-139">Gevoeligheidslabels worden niet ondersteund)</span><span class="sxs-lookup"><span data-stu-id="a6f98-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="a6f98-140">Inhoud wordt gedeeld</span><span class="sxs-lookup"><span data-stu-id="a6f98-140">Content is shared</span></span>

<span data-ttu-id="a6f98-141">Houd er rekening mee dat alle voorwaarden werken voor e-mailberichten die zijn geschreven in de Outlook-client-app, waar ze overeenkomen met inhoud en beschermende acties voor inhoud afdwingen.</span><span class="sxs-lookup"><span data-stu-id="a6f98-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="a6f98-142">Het weergeven van beleidstips voor gebruikers wordt echter niet ondersteund voor voorwaarden die behalve de hierboven genoemde voorwaarden worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a6f98-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="a6f98-143">Ondersteuning voor Outlook 2013 en hoger en Office-apps op bureaublad met beleidstips voor slechts enkele typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="a6f98-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="a6f98-144">De lijst met out-of-the-box gevoelige informatietypen die worden gedetecteerd voor het weergeven van DLP-beleidstips in Outlook op bureaublad (2013 en hoger) en Office-apps (Word, Excel, PowerPoint) op bureaublad zijn de volgende:</span><span class="sxs-lookup"><span data-stu-id="a6f98-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="a6f98-145">ABA-routeringsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-145">ABA Routing Number</span></span>
- <span data-ttu-id="a6f98-146">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="a6f98-147">Australië Bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="a6f98-148">Australië Medical Account Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="a6f98-149">Australië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-149">Australia Passport Number</span></span>
- <span data-ttu-id="a6f98-150">Australië Belastingbestandsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-150">Australia Tax File Number</span></span>
- <span data-ttu-id="a6f98-151">Azure DocumentDB Auth Key</span><span class="sxs-lookup"><span data-stu-id="a6f98-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="a6f98-152">Azure IAAS Database Connection String en Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="a6f98-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="a6f98-153">Azure IoT-verbindingsreeks</span><span class="sxs-lookup"><span data-stu-id="a6f98-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="a6f98-154">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="a6f98-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="a6f98-155">Verbindingsreeks Azure Redis Cache</span><span class="sxs-lookup"><span data-stu-id="a6f98-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="a6f98-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="a6f98-156">Azure SAS</span></span>  
- <span data-ttu-id="a6f98-157">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="a6f98-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="a6f98-158">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="a6f98-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="a6f98-159">Azure Storage Account Key (Generic)</span><span class="sxs-lookup"><span data-stu-id="a6f98-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="a6f98-160">Nationaal nummer belgië</span><span class="sxs-lookup"><span data-stu-id="a6f98-160">Belgium National Number</span></span>
- <span data-ttu-id="a6f98-161">Brazilië CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-161">Brazil CPF Number</span></span>
- <span data-ttu-id="a6f98-162">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="a6f98-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="a6f98-163">Nationale id-kaart brazilië (RG)</span><span class="sxs-lookup"><span data-stu-id="a6f98-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="a6f98-164">Canada Bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="a6f98-165">Canada Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="a6f98-166">Canada Health Service Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-166">Canada Health Service Number</span></span>
- <span data-ttu-id="a6f98-167">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-167">Canada Passport Number</span></span>
- <span data-ttu-id="a6f98-168">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="a6f98-169">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="a6f98-170">Chili-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="a6f98-171">China Resident Identity Card (PRC) Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="a6f98-172">Creditcardnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-172">Credit Card Number</span></span>
- <span data-ttu-id="a6f98-173">Kroatië-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="a6f98-174">OIB-nummer (Croatia Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="a6f98-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="a6f98-175">Tsjechische persoonlijke identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="a6f98-176">Denemarken Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="a6f98-177">Nummer van Het Bureau voor drugshandhaving (DEA)</span><span class="sxs-lookup"><span data-stu-id="a6f98-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="a6f98-178">EU-betaalkaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-178">EU Debit Card Number</span></span>
- <span data-ttu-id="a6f98-179">Eu-rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="a6f98-180">NATIONAAL EU-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-180">EU National Identification Number</span></span>  
- <span data-ttu-id="a6f98-181">EU-paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-181">EU Passport Number</span></span>  
- <span data-ttu-id="a6f98-182">EU-SSN -nummer (Social Security Number) of equivalente id</span><span class="sxs-lookup"><span data-stu-id="a6f98-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="a6f98-183">EU-belastingidentificatienummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="a6f98-184">Nationale finland-id</span><span class="sxs-lookup"><span data-stu-id="a6f98-184">Finland National ID</span></span>
- <span data-ttu-id="a6f98-185">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-185">Finland Passport Number</span></span>
- <span data-ttu-id="a6f98-186">France Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-186">France Driver's License Number</span></span>
- <span data-ttu-id="a6f98-187">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="a6f98-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="a6f98-188">Frankrijk Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-188">France Passport Number</span></span>
- <span data-ttu-id="a6f98-189">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a6f98-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="a6f98-190">Duits rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-190">German Driver's License Number</span></span>
- <span data-ttu-id="a6f98-191">Duits paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-191">German Passport Number</span></span>
- <span data-ttu-id="a6f98-192">Duitsland-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="a6f98-193">Nationale griekenland-id-kaart</span><span class="sxs-lookup"><span data-stu-id="a6f98-193">Greece National ID Card</span></span>  
- <span data-ttu-id="a6f98-194">Hong Kong Identity Card (HKID) Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="a6f98-195">India Permanent Account Number (PAN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="a6f98-196">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="a6f98-197">KTP-nummer (Indonesia Identity Card)</span><span class="sxs-lookup"><span data-stu-id="a6f98-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="a6f98-198">IBAN (International Banking Account Number)</span><span class="sxs-lookup"><span data-stu-id="a6f98-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="a6f98-199">Internationale classificatie van ziektes (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="a6f98-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="a6f98-200">Internationale classificatie van ziektes (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="a6f98-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="a6f98-201">IP Address</span><span class="sxs-lookup"><span data-stu-id="a6f98-201">IP Address</span></span>
- <span data-ttu-id="a6f98-202">Ierland Personal Public Service (PPS)-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="a6f98-203">Israel Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="a6f98-204">Nationale israël-id</span><span class="sxs-lookup"><span data-stu-id="a6f98-204">Israel National ID</span></span>
- <span data-ttu-id="a6f98-205">Rijbewijsnummer van Italië</span><span class="sxs-lookup"><span data-stu-id="a6f98-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="a6f98-206">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="a6f98-207">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="a6f98-208">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-208">Japan Passport Number</span></span>
- <span data-ttu-id="a6f98-209">Japan Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="a6f98-210">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="a6f98-211">Japans nummer van een verblijfskaart</span><span class="sxs-lookup"><span data-stu-id="a6f98-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="a6f98-212">Maleisische identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="a6f98-213">BSN-nummer (Netherlands Citizen's Service)</span><span class="sxs-lookup"><span data-stu-id="a6f98-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="a6f98-214">Nieuw-Zeelands ministerie van Gezondheid Nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="a6f98-215">Noorwegen-identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-215">Norway Identity Number</span></span>  
- <span data-ttu-id="a6f98-216">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="a6f98-217">Polen-identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a6f98-217">Poland Identity Card</span></span>
- <span data-ttu-id="a6f98-218">Nationale Polen-id (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a6f98-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="a6f98-219">Polen-paspoort</span><span class="sxs-lookup"><span data-stu-id="a6f98-219">Poland Passport</span></span>
- <span data-ttu-id="a6f98-220">Portugal Burgerkaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="a6f98-221">Nationale id van Saudi-Arabië</span><span class="sxs-lookup"><span data-stu-id="a6f98-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="a6f98-222">NRIC-nummer (National Registration Identity Card) van Singapore</span><span class="sxs-lookup"><span data-stu-id="a6f98-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="a6f98-223">Zuid-Afrika-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="a6f98-224">Registratienummer voor inwoners van Zuid-Korea</span><span class="sxs-lookup"><span data-stu-id="a6f98-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="a6f98-225">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="a6f98-226">SQL Server-verbindingsreeks</span><span class="sxs-lookup"><span data-stu-id="a6f98-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="a6f98-227">Nationale id Zweden</span><span class="sxs-lookup"><span data-stu-id="a6f98-227">Sweden National ID</span></span>
- <span data-ttu-id="a6f98-228">Zweden Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-228">Sweden Passport Number</span></span>
- <span data-ttu-id="a6f98-229">SWIFT-code</span><span class="sxs-lookup"><span data-stu-id="a6f98-229">SWIFT Code</span></span>
- <span data-ttu-id="a6f98-230">Nationale taiwan-id</span><span class="sxs-lookup"><span data-stu-id="a6f98-230">Taiwan National ID</span></span>
- <span data-ttu-id="a6f98-231">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="a6f98-232">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="a6f98-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="a6f98-233">Thaise bevolkingsidentificatiecode</span><span class="sxs-lookup"><span data-stu-id="a6f98-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="a6f98-234">Turks nationaal identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-234">Turkish National Identification number</span></span>
- <span data-ttu-id="a6f98-235">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-235">U.K.</span></span> <span data-ttu-id="a6f98-236">Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-236">Driver's License Number</span></span>
- <span data-ttu-id="a6f98-237">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-237">U.K.</span></span> <span data-ttu-id="a6f98-238">Kieslijstnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-238">Electoral Roll Number</span></span>
- <span data-ttu-id="a6f98-239">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-239">U.K.</span></span> <span data-ttu-id="a6f98-240">National Health Service Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-240">National Health Service Number</span></span>
- <span data-ttu-id="a6f98-241">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-241">U.K.</span></span> <span data-ttu-id="a6f98-242">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="a6f98-242">National Insurance Number (NINO)</span></span>
- <span data-ttu-id="a6f98-243">V.S. / VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-243">U.S. / U.K.</span></span> <span data-ttu-id="a6f98-244">Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-244">Passport Number</span></span>
- <span data-ttu-id="a6f98-245">Amerikaans bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="a6f98-246">Amerikaans rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="a6f98-247">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="a6f98-248">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="a6f98-249">Houd er rekening mee dat aangepaste gevoelige informatietypen ook worden ondersteund voor DLP-beleidstips, naast de bovenstaande kant-en-kijkgevoelige informatietypen.</span><span class="sxs-lookup"><span data-stu-id="a6f98-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="a6f98-250">Preventie van gegevensverlies op eindpuntapparaten ondersteunt beleidstips voor alleen bepaalde typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="a6f98-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="a6f98-251">De lijst met kant-en-weer gevoelige informatietypen die worden gedetecteerd in documenten die zich op eindpuntapparaten bewonen, zijn de volgende:</span><span class="sxs-lookup"><span data-stu-id="a6f98-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="a6f98-252">ABA-routeringsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-252">ABA Routing Number</span></span> 
- <span data-ttu-id="a6f98-253">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="a6f98-254">Australië Bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="a6f98-255">Australië Medical Account Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="a6f98-256">Australië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-256">Australia Passport Number</span></span> 
- <span data-ttu-id="a6f98-257">Australië Belastingbestandsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="a6f98-258">Australisch bedrijfsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-258">Australian Business Number</span></span> 
- <span data-ttu-id="a6f98-259">Australisch bedrijfsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-259">Australian Company Number</span></span> 
- <span data-ttu-id="a6f98-260">Oostenrijks rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-261">Oostenrijk-identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a6f98-261">Austria Identity Card</span></span> 
- <span data-ttu-id="a6f98-262">Oostenrijks paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-262">Austria Passport Number</span></span> 
- <span data-ttu-id="a6f98-263">Oostenrijks sociaal-zekerheidsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="a6f98-264">Oostenrijks btw-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-265">Oostenrijks btw-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="a6f98-266">Azure DocumentDB Auth Key</span><span class="sxs-lookup"><span data-stu-id="a6f98-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="a6f98-267">Azure IAAS Database Connection String en Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="a6f98-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="a6f98-268">Azure IoT-verbindingsreeks</span><span class="sxs-lookup"><span data-stu-id="a6f98-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="a6f98-269">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="a6f98-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="a6f98-270">Verbindingsreeks Azure Redis Cache</span><span class="sxs-lookup"><span data-stu-id="a6f98-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="a6f98-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="a6f98-271">Azure SAS</span></span> 
- <span data-ttu-id="a6f98-272">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="a6f98-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="a6f98-273">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="a6f98-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="a6f98-274">Azure Storage Account Key (Generic)</span><span class="sxs-lookup"><span data-stu-id="a6f98-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="a6f98-275">Nummer van het Rijbewijs van België</span><span class="sxs-lookup"><span data-stu-id="a6f98-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-276">Nationaal nummer belgië</span><span class="sxs-lookup"><span data-stu-id="a6f98-276">Belgium National Number</span></span> 
- <span data-ttu-id="a6f98-277">België Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="a6f98-278">België Btw-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="a6f98-279">Brazilië CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="a6f98-280">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="a6f98-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="a6f98-281">Nationale id-kaart brazilië (RG)</span><span class="sxs-lookup"><span data-stu-id="a6f98-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="a6f98-282">Bulgarije Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-283">Bulgarije Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="a6f98-284">Bulgarije Uniform Burgernummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="a6f98-285">Canada Bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="a6f98-286">Canada Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-287">Canada Health Service Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="a6f98-288">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-288">Canada Passport Number</span></span> 
- <span data-ttu-id="a6f98-289">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="a6f98-290">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="a6f98-291">Chili-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="a6f98-292">China Resident Identity Card (PRC) Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="a6f98-293">Creditcardnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-293">Credit Card Number</span></span> 
- <span data-ttu-id="a6f98-294">Kroatische nummer van het rijbewijs</span><span class="sxs-lookup"><span data-stu-id="a6f98-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-295">Kroatië-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="a6f98-296">Kroatië National ID Card Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="a6f98-297">Kroatië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="a6f98-298">OIB-nummer (Croatia Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="a6f98-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="a6f98-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span><span class="sxs-lookup"><span data-stu-id="a6f98-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="a6f98-300">CSCAN-GENERAL0140 General Symmetric Key</span><span class="sxs-lookup"><span data-stu-id="a6f98-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="a6f98-301">Cyprus Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-302">Cyprus-identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a6f98-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="a6f98-303">Cyprus Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="a6f98-304">Cyprus Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-305">Tsjechisch rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-306">Tsjechische persoonlijke identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="a6f98-307">Tsjechische Republiek Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="a6f98-308">Rijbewijsnummer van Denemarken</span><span class="sxs-lookup"><span data-stu-id="a6f98-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-309">Denemarken Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="a6f98-310">Denemarken Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="a6f98-311">Nummer van Het Bureau voor drugshandhaving (DEA)</span><span class="sxs-lookup"><span data-stu-id="a6f98-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="a6f98-312">Estlands rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-313">Estlands paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="a6f98-314">Estlandse persoonlijke identificatiecode</span><span class="sxs-lookup"><span data-stu-id="a6f98-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="a6f98-315">EU-betaalkaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="a6f98-316">Eu-rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-317">NATIONAAL EU-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-317">EU National Identification Number</span></span> 
- <span data-ttu-id="a6f98-318">EU-paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-318">EU Passport Number</span></span> 
- <span data-ttu-id="a6f98-319">EU-SSN -nummer (Social Security Number) of equivalente id</span><span class="sxs-lookup"><span data-stu-id="a6f98-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="a6f98-320">EU-belastingidentificatienummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="a6f98-321">Finland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-322">Finland European Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="a6f98-323">Nationale finland-id</span><span class="sxs-lookup"><span data-stu-id="a6f98-323">Finland National ID</span></span> 
- <span data-ttu-id="a6f98-324">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-324">Finland Passport Number</span></span> 
- <span data-ttu-id="a6f98-325">France Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-325">France Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-326">France Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="a6f98-327">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="a6f98-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="a6f98-328">Frankrijk Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-328">France Passport Number</span></span> 
- <span data-ttu-id="a6f98-329">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a6f98-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="a6f98-330">France Tax Identification Number (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="a6f98-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="a6f98-331">Frankrijk Btw-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="a6f98-332">Duits rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-332">German Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-333">Duits paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-333">German Passport Number</span></span> 
- <span data-ttu-id="a6f98-334">Duitsland-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="a6f98-335">Duitsland Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-336">Duitsland Btw-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="a6f98-337">Griekenland Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-338">Nationale griekenland-id-kaart</span><span class="sxs-lookup"><span data-stu-id="a6f98-338">Greece National ID Card</span></span> 
- <span data-ttu-id="a6f98-339">Griekenland Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-339">Greece Passport Number</span></span> 
- <span data-ttu-id="a6f98-340">Griekenland-nummer voor sociale zekerheid (AMKA)</span><span class="sxs-lookup"><span data-stu-id="a6f98-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="a6f98-341">Griekse btw-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="a6f98-342">Hong Kong Identity Card (HKID) Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="a6f98-343">Hongaars sociaal-zekerheidsnummer (TAJ)</span><span class="sxs-lookup"><span data-stu-id="a6f98-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="a6f98-344">Hongaars btw-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="a6f98-345">Licentienummer van Hongarije</span><span class="sxs-lookup"><span data-stu-id="a6f98-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-346">Hongarije Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="a6f98-347">Hongarije Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="a6f98-348">Btw-nummer van Hongarije</span><span class="sxs-lookup"><span data-stu-id="a6f98-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="a6f98-349">India Permanent Account Number (PAN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="a6f98-350">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="a6f98-351">KTP-nummer (Indonesia Identity Card)</span><span class="sxs-lookup"><span data-stu-id="a6f98-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="a6f98-352">IBAN (International Banking Account Number)</span><span class="sxs-lookup"><span data-stu-id="a6f98-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="a6f98-353">Internationale classificatie van ziektes (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="a6f98-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="a6f98-354">Internationale classificatie van ziektes (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="a6f98-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="a6f98-355">IP Address</span><span class="sxs-lookup"><span data-stu-id="a6f98-355">IP Address</span></span> 
- <span data-ttu-id="a6f98-356">Ireland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-357">Ierland Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="a6f98-358">Ierland Personal Public Service (PPS)-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="a6f98-359">Israel Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="a6f98-360">Nationale israël-id</span><span class="sxs-lookup"><span data-stu-id="a6f98-360">Israel National ID</span></span> 
- <span data-ttu-id="a6f98-361">Rijbewijsnummer van Italië</span><span class="sxs-lookup"><span data-stu-id="a6f98-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-362">Italiaanse fiscale code</span><span class="sxs-lookup"><span data-stu-id="a6f98-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="a6f98-363">Italië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-363">Italy Passport Number</span></span> 
- <span data-ttu-id="a6f98-364">#A0 #A0 #A0 #A0 #A0 #A</span><span class="sxs-lookup"><span data-stu-id="a6f98-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="a6f98-365">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="a6f98-366">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-367">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-367">Japan Passport Number</span></span> 
- <span data-ttu-id="a6f98-368">Japan Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="a6f98-369">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="a6f98-370">Japans My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="a6f98-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="a6f98-371">Japans Mijn nummer Persoonlijk</span><span class="sxs-lookup"><span data-stu-id="a6f98-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="a6f98-372">Japans nummer van een verblijfskaart</span><span class="sxs-lookup"><span data-stu-id="a6f98-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="a6f98-373">Letlandse rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-374">Letland Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="a6f98-375">Persoonlijke code letland</span><span class="sxs-lookup"><span data-stu-id="a6f98-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="a6f98-376">Litouws rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-377">Litouws paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="a6f98-378">Persoonlijke code litouwen</span><span class="sxs-lookup"><span data-stu-id="a6f98-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="a6f98-379">Luxemburgs rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-380">Luxemburg National Identification Number (Natuurlijke personen)</span><span class="sxs-lookup"><span data-stu-id="a6f98-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="a6f98-381">Luxemburg National Identification Number (Niet-natuurlijke personen)</span><span class="sxs-lookup"><span data-stu-id="a6f98-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="a6f98-382">Luxemburg Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="a6f98-383">Maleisische identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="a6f98-384">Malta Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-385">Malta-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="a6f98-386">Malta Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-386">Malta Passport Number</span></span> 
- <span data-ttu-id="a6f98-387">Malta Tax ID-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="a6f98-388">BSN-nummer (Netherlands Citizen's Service)</span><span class="sxs-lookup"><span data-stu-id="a6f98-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="a6f98-389">Nederlands rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-390">Nederlands paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="a6f98-391">Btw-nummer van Nederland</span><span class="sxs-lookup"><span data-stu-id="a6f98-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-392">Btw-nummer voor Nederland</span><span class="sxs-lookup"><span data-stu-id="a6f98-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="a6f98-393">Nieuw-Zeelands bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="a6f98-394">Nieuw-Zeelandse rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="a6f98-395">Nieuw-Zeelandse belastingdienst</span><span class="sxs-lookup"><span data-stu-id="a6f98-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="a6f98-396">Nieuw-Zeelands ministerie van Gezondheid Nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="a6f98-397">Nieuw-Zeelandse sociale voorzieningennummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="a6f98-398">Noorwegen-identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-398">Norway Identity Number</span></span> 
- <span data-ttu-id="a6f98-399">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="a6f98-400">Polen Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-401">Polen-identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a6f98-401">Poland Identity Card</span></span> 
- <span data-ttu-id="a6f98-402">Nationale Polen-id (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a6f98-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="a6f98-403">Polen-paspoort</span><span class="sxs-lookup"><span data-stu-id="a6f98-403">Poland Passport</span></span> 
- <span data-ttu-id="a6f98-404">Polen Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-405">Pools REGON-nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-405">Polish REGON Number</span></span> 
- <span data-ttu-id="a6f98-406">Portugal Burgerkaartnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="a6f98-407">Portugal Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-408">Portugal Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="a6f98-409">Portugal Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-410">Roemenië Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-411">Roemenië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-411">Romania Passport Number</span></span> 
- <span data-ttu-id="a6f98-412">Roemeense persoonlijke numerieke code (CNP)</span><span class="sxs-lookup"><span data-stu-id="a6f98-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="a6f98-413">Russisch paspoortnummer (binnenlands)</span><span class="sxs-lookup"><span data-stu-id="a6f98-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="a6f98-414">Russisch paspoortnummer (internationaal)</span><span class="sxs-lookup"><span data-stu-id="a6f98-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="a6f98-415">Nationale id van Saudi-Arabië</span><span class="sxs-lookup"><span data-stu-id="a6f98-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="a6f98-416">NRIC-nummer (National Registration Identity Card) van Singapore</span><span class="sxs-lookup"><span data-stu-id="a6f98-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="a6f98-417">Slowakije Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-418">Slowakije Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="a6f98-419">Slowakije Persoonlijk Nummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="a6f98-420">Sloveens rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-421">Slovenië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="a6f98-422">Slovenië Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-423">Slovenië Unique Master Citizen Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="a6f98-424">Zuid-Afrika-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="a6f98-425">Registratienummer voor inwoners van Zuid-Korea</span><span class="sxs-lookup"><span data-stu-id="a6f98-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="a6f98-426">Spanje DNI</span><span class="sxs-lookup"><span data-stu-id="a6f98-426">Spain DNI</span></span> 
- <span data-ttu-id="a6f98-427">Rijbewijsnummer van Spanje</span><span class="sxs-lookup"><span data-stu-id="a6f98-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-428">Spanje Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-428">Spain Passport Number</span></span> 
- <span data-ttu-id="a6f98-429">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="a6f98-430">Spanje Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-431">SQL Server-verbindingsreeks</span><span class="sxs-lookup"><span data-stu-id="a6f98-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="a6f98-432">Zweden Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-433">Nationale id Zweden</span><span class="sxs-lookup"><span data-stu-id="a6f98-433">Sweden National ID</span></span> 
- <span data-ttu-id="a6f98-434">Zweden Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="a6f98-435">Zweden Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="a6f98-436">SWIFT-code</span><span class="sxs-lookup"><span data-stu-id="a6f98-436">SWIFT Code</span></span> 
- <span data-ttu-id="a6f98-437">Zwitserse socialezekerheidsnummer AHV</span><span class="sxs-lookup"><span data-stu-id="a6f98-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="a6f98-438">Nationale taiwan-id</span><span class="sxs-lookup"><span data-stu-id="a6f98-438">Taiwan National ID</span></span> 
- <span data-ttu-id="a6f98-439">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="a6f98-440">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="a6f98-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="a6f98-441">Thaise bevolkingsidentificatiecode</span><span class="sxs-lookup"><span data-stu-id="a6f98-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="a6f98-442">Turks nationaal identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="a6f98-443">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-443">U.K.</span></span> <span data-ttu-id="a6f98-444">Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-444">Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-445">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-445">U.K.</span></span> <span data-ttu-id="a6f98-446">Kieslijstnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-446">Electoral Roll Number</span></span> 
- <span data-ttu-id="a6f98-447">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-447">U.K.</span></span> <span data-ttu-id="a6f98-448">National Health Service Number</span><span class="sxs-lookup"><span data-stu-id="a6f98-448">National Health Service Number</span></span> 
- <span data-ttu-id="a6f98-449">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-449">U.K.</span></span> <span data-ttu-id="a6f98-450">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="a6f98-450">National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="a6f98-451">VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-451">U.K.</span></span> <span data-ttu-id="a6f98-452">Uniek referentienummer voor belastingbetalers</span><span class="sxs-lookup"><span data-stu-id="a6f98-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="a6f98-453">V.S. / VK</span><span class="sxs-lookup"><span data-stu-id="a6f98-453">U.S. / U.K.</span></span> <span data-ttu-id="a6f98-454">Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-454">Passport Number</span></span> 
- <span data-ttu-id="a6f98-455">Amerikaans bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="a6f98-456">Amerikaans rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a6f98-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="a6f98-457">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="a6f98-458">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="a6f98-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="a6f98-459">Oekraine Paspoortnummer (binnenlands)</span><span class="sxs-lookup"><span data-stu-id="a6f98-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="a6f98-460">Oekraine Paspoortnummer (internationaal)</span><span class="sxs-lookup"><span data-stu-id="a6f98-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="a6f98-461">Houd er rekening mee dat aangepaste gevoelige informatietypen ook worden gedetecteerd naast de bovenstaande kant-en-zeker gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="a6f98-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="a6f98-462">Ondersteuningsmatrix voor DLP-beleidstips in Microsoft-apps</span><span class="sxs-lookup"><span data-stu-id="a6f98-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="a6f98-463">**App en platform**</span><span class="sxs-lookup"><span data-stu-id="a6f98-463">**App and platform**</span></span>|<span data-ttu-id="a6f98-464">**Ondersteuning voor DLP-beleidstips**</span><span class="sxs-lookup"><span data-stu-id="a6f98-464">**DLP policy tip support**</span></span>|<span data-ttu-id="a6f98-465">**Ondersteunde typen gevoelige informatie**</span><span class="sxs-lookup"><span data-stu-id="a6f98-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="a6f98-466">**Ondersteunde predicaten en acties**</span><span class="sxs-lookup"><span data-stu-id="a6f98-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="a6f98-467">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="a6f98-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="a6f98-468">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="a6f98-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a6f98-469">Alles</span><span class="sxs-lookup"><span data-stu-id="a6f98-469">All</span></span>|<span data-ttu-id="a6f98-470">Subset</span><span class="sxs-lookup"><span data-stu-id="a6f98-470">Subset</span></span>|<span data-ttu-id="a6f98-471">Zie [Tips voor beleidstips voor preventie van gegevensverlies](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="a6f98-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="a6f98-472">**Outlook Win32 (Outlook 2013 en hoger)**</span><span class="sxs-lookup"><span data-stu-id="a6f98-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a6f98-473">Subset</span><span class="sxs-lookup"><span data-stu-id="a6f98-473">Subset</span></span>|<span data-ttu-id="a6f98-474">Subset</span><span class="sxs-lookup"><span data-stu-id="a6f98-474">Subset</span></span>|<span data-ttu-id="a6f98-475">Zie Ondersteuning voor [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) en hoger met beleidstips voor slechts enkele voorwaarden en uitzonderingen en Ondersteuning voor [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) en hoger en Office-apps op bureaublad, met beleidstips voor slechts enkele typen gevoelige informatie voor meer informatie over ondersteuning voor gevoelige informatietypen en DLP-voorwaarden en -acties die worden ondersteund voor het weergeven van DLP-beleidstips in Outlook Win32.</span><span class="sxs-lookup"><span data-stu-id="a6f98-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="a6f98-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="a6f98-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a6f98-477">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-477">None</span></span>|<span data-ttu-id="a6f98-478">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-478">None</span></span>|<span data-ttu-id="a6f98-479">DLP-beleidstips worden niet ondersteund in Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="a6f98-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="a6f98-480">**Sharepoint Online/One Drive for Business Web Client**</span><span class="sxs-lookup"><span data-stu-id="a6f98-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a6f98-481">Alles</span><span class="sxs-lookup"><span data-stu-id="a6f98-481">All</span></span>|<span data-ttu-id="a6f98-482">Alle SPO/ODB-predicaten en acties in DLP</span><span class="sxs-lookup"><span data-stu-id="a6f98-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="a6f98-483">**Win32/ One Drive for Business Win32-client van Sharepoint**</span><span class="sxs-lookup"><span data-stu-id="a6f98-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a6f98-484">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-484">None</span></span>|<span data-ttu-id="a6f98-485">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-485">None</span></span>|<span data-ttu-id="a6f98-486">DLP-beleidstips worden niet ondersteund in sharepoint- of OneDrive-bureaubladclient-apps</span><span class="sxs-lookup"><span data-stu-id="a6f98-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="a6f98-487">**Word, Excel, PowerPoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="a6f98-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a6f98-488">Alles</span><span class="sxs-lookup"><span data-stu-id="a6f98-488">All</span></span>|<span data-ttu-id="a6f98-489">Alle SPO/ODB-predicaten en acties in DLP</span><span class="sxs-lookup"><span data-stu-id="a6f98-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="a6f98-490">DLP-beleidstip wordt ondersteund als het document wordt gehost in de SPO- of ODB-web-app en het DLP-beleid al is gestempeld.</span><span class="sxs-lookup"><span data-stu-id="a6f98-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="a6f98-491">**Word, Excel, PowerPoint Mobile Client**</span><span class="sxs-lookup"><span data-stu-id="a6f98-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a6f98-492">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-492">None</span></span>|<span data-ttu-id="a6f98-493">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-493">None</span></span>|<span data-ttu-id="a6f98-494">DLP-beleidstips worden niet ondersteund in mobiele apps voor Office.</span><span class="sxs-lookup"><span data-stu-id="a6f98-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="a6f98-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="a6f98-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a6f98-496">Alles</span><span class="sxs-lookup"><span data-stu-id="a6f98-496">All</span></span>|<span data-ttu-id="a6f98-497">Alle Teams-predicaten in DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="a6f98-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="a6f98-498">Beleidstips worden weergegeven wanneer een bericht wordt gemarkeerd als 'Dit bericht is gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="a6f98-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="a6f98-499">Wat kan ik doen?</span><span class="sxs-lookup"><span data-stu-id="a6f98-499">What can I do?”</span></span> <span data-ttu-id="a6f98-500">Wanneer u op de koppeling klikt, kan de gebruiker de gevoelige informatietypen controleren die zijn gedetecteerd en een probleem kunnen overschrijven of rapporteren indien toegestaan door de beheerder. Houd er rekening mee dat er geen beleidstips worden weergegeven voor bestanden.</span><span class="sxs-lookup"><span data-stu-id="a6f98-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="a6f98-501">Wanneer de geadresseerde toegang probeert te krijgen tot het document, krijgen ze mogelijk toegang geweigerd als dit niet is toegestaan.</span><span class="sxs-lookup"><span data-stu-id="a6f98-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="a6f98-502">**Win32 Endpoint-apparaten**</span><span class="sxs-lookup"><span data-stu-id="a6f98-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a6f98-503">Subset</span><span class="sxs-lookup"><span data-stu-id="a6f98-503">Subset</span></span>|<span data-ttu-id="a6f98-504">Alle endpoint DLP-predicaten en acties in DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="a6f98-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="a6f98-505">Zie [Preventie van gegevensverlies op Eindpunt ondersteunt beleidstips voor alleen bepaalde typen gevoelige informatie](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="a6f98-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="a6f98-506">**Mac-apparaten**</span><span class="sxs-lookup"><span data-stu-id="a6f98-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a6f98-507">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-507">None</span></span>|<span data-ttu-id="a6f98-508">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-508">None</span></span>|<span data-ttu-id="a6f98-509">Beleid voor preventie van gegevensverlies kan momenteel niet worden afgedwongen op Mac-apparaten</span><span class="sxs-lookup"><span data-stu-id="a6f98-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="a6f98-510">**Cloud-apps van derden**</span><span class="sxs-lookup"><span data-stu-id="a6f98-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a6f98-511">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-511">None</span></span>|<span data-ttu-id="a6f98-512">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-512">None</span></span>|<span data-ttu-id="a6f98-513">Tips voor preventie van gegevensverlies worden niet ondersteund in cloud-apps van derden</span><span class="sxs-lookup"><span data-stu-id="a6f98-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="a6f98-514">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="a6f98-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a6f98-515">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-515">None</span></span>|<span data-ttu-id="a6f98-516">Geen</span><span class="sxs-lookup"><span data-stu-id="a6f98-516">None</span></span>||
|<span data-ttu-id="a6f98-517">**Word, Excel, PowerPoint Win32-client**</span><span class="sxs-lookup"><span data-stu-id="a6f98-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a6f98-518">Subset</span><span class="sxs-lookup"><span data-stu-id="a6f98-518">Subset</span></span>|<span data-ttu-id="a6f98-519">Subset</span><span class="sxs-lookup"><span data-stu-id="a6f98-519">Subset</span></span>|<span data-ttu-id="a6f98-520">Zie [Ondersteuning voor Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) en hoger en Office-apps op bureaublad met beleidstips voor alleen bepaalde typen gevoelige informatie voor de lijst met ondersteunde typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="a6f98-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="a6f98-521">Beleidstips voor WXP-client-apps werken voor documenten die zijn opgeslagen op Sharepoint Online of One Drive for Business Sites voor alle DLP-beleidsregels die precies de onderstaande of een subset met voorwaarden of acties in het DLP-beleid bevatten:</span><span class="sxs-lookup"><span data-stu-id="a6f98-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="a6f98-522">Inhoud bevat gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="a6f98-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="a6f98-523">Access-bereik (Inhoud wordt intern/extern gedeeld)</span><span class="sxs-lookup"><span data-stu-id="a6f98-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="a6f98-524">Gebruiker op de hoogte stellen (beleidstips/gebruikersmeldingen)</span><span class="sxs-lookup"><span data-stu-id="a6f98-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="a6f98-525">Iedereen blokkeren</span><span class="sxs-lookup"><span data-stu-id="a6f98-525">Block everyone</span></span></li><li><span data-ttu-id="a6f98-526">Incidentenrapporten</span><span class="sxs-lookup"><span data-stu-id="a6f98-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="a6f98-527">Als er een andere voorwaarde of actie aanwezig is, wordt de DLP-beleidstip voor dat beleid niet weergegeven in de bureaublad-apps van Word, Excel of PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="a6f98-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="a6f98-528">Zie [Beleidstips in Excel, PowerPoint en Word voor](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) meer informatie</span><span class="sxs-lookup"><span data-stu-id="a6f98-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
