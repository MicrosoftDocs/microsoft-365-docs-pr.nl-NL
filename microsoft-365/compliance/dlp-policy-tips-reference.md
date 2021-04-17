---
title: Tips voor preventie van gegevensverlies
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
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876798"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="257be-103">Tips voor preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="257be-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="257be-104">DLP-beleidstips in Outlook Web Access worden ondersteund voor alle voorwaarden, uitzonderingen en acties die van toepassing zijn op Exchange-werkbelasting in een DLP-beleid, behalve de volgende:</span><span class="sxs-lookup"><span data-stu-id="257be-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="257be-105">**Voorwaarden:**</span><span class="sxs-lookup"><span data-stu-id="257be-105">**Conditions:**</span></span>

- <span data-ttu-id="257be-106">Afzender is</span><span class="sxs-lookup"><span data-stu-id="257be-106">Sender Is</span></span>
- <span data-ttu-id="257be-107">Sender Domain Is</span><span class="sxs-lookup"><span data-stu-id="257be-107">Sender Domain Is</span></span>
- <span data-ttu-id="257be-108">Geadresseerde is lid van</span><span class="sxs-lookup"><span data-stu-id="257be-108">Recipient is a member of</span></span>
- <span data-ttu-id="257be-109">Koptekst bevat woorden of woordgroepen</span><span class="sxs-lookup"><span data-stu-id="257be-109">Header contains words or phrases</span></span>
- <span data-ttu-id="257be-110">Koptekst komt overeen met patronen</span><span class="sxs-lookup"><span data-stu-id="257be-110">Header matches patterns</span></span>
- <span data-ttu-id="257be-111">De documentgrootte is gelijk aan of groter dan</span><span class="sxs-lookup"><span data-stu-id="257be-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="257be-112">Berichttype is</span><span class="sxs-lookup"><span data-stu-id="257be-112">Message type is</span></span>
- <span data-ttu-id="257be-113">Het belang van berichten is</span><span class="sxs-lookup"><span data-stu-id="257be-113">Message importance is</span></span>
- <span data-ttu-id="257be-114">Inhoudstekenset bevat woorden</span><span class="sxs-lookup"><span data-stu-id="257be-114">Content character set contains words</span></span>
- <span data-ttu-id="257be-115">Onderwerp of lichaam bevat woorden of woordgroepen</span><span class="sxs-lookup"><span data-stu-id="257be-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="257be-116">Patronen voor onderwerp of lichaam</span><span class="sxs-lookup"><span data-stu-id="257be-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="257be-117">Inhoudstekenset bevat woorden</span><span class="sxs-lookup"><span data-stu-id="257be-117">Content character set contains words</span></span>
- <span data-ttu-id="257be-118">Inhoud wordt ontvangen van</span><span class="sxs-lookup"><span data-stu-id="257be-118">Content is received from</span></span>
- <span data-ttu-id="257be-119">Heeft afzender de beleidstip overgenomen</span><span class="sxs-lookup"><span data-stu-id="257be-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="257be-120">Berichtgrootte is gelijk aan of groter dan</span><span class="sxs-lookup"><span data-stu-id="257be-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="257be-121">Ad-kenmerk Afzender bevat woorden of woordgroepen</span><span class="sxs-lookup"><span data-stu-id="257be-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="257be-122">Ad-kenmerk Afzender komt overeen met patronen</span><span class="sxs-lookup"><span data-stu-id="257be-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="257be-123">Documentinhoud bevat woorden of woordgroepen</span><span class="sxs-lookup"><span data-stu-id="257be-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="257be-124">Documentinhoud komt overeen met patronen</span><span class="sxs-lookup"><span data-stu-id="257be-124">Document content matches patterns</span></span>

<span data-ttu-id="257be-125">**Acties:**</span><span class="sxs-lookup"><span data-stu-id="257be-125">**Actions:**</span></span>

- <span data-ttu-id="257be-126">Het bericht ter goedkeuring doorsturen naar de afzendermanager</span><span class="sxs-lookup"><span data-stu-id="257be-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="257be-127">Het bericht ter goedkeuring doorsturen naar specifieke goedkeurders</span><span class="sxs-lookup"><span data-stu-id="257be-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="257be-128">Het bericht omleiden naar specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="257be-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="257be-129">Geadresseerden toevoegen aan het vak Aan</span><span class="sxs-lookup"><span data-stu-id="257be-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="257be-130">Geadresseerden toevoegen aan het cc-vak</span><span class="sxs-lookup"><span data-stu-id="257be-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="257be-131">Geadresseerden toevoegen aan het BCC-vak</span><span class="sxs-lookup"><span data-stu-id="257be-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="257be-132">Manager van de afzender toevoegen als geadresseerde</span><span class="sxs-lookup"><span data-stu-id="257be-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="257be-133">HTML-vrijwaring toevoegen</span><span class="sxs-lookup"><span data-stu-id="257be-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="257be-134">Voorbereidend e-mailonderwerp</span><span class="sxs-lookup"><span data-stu-id="257be-134">Prepend email subject</span></span>
- <span data-ttu-id="257be-135">O365-berichtversleuteling en rechtenbescherming verwijderen</span><span class="sxs-lookup"><span data-stu-id="257be-135">Remove O365 Message Encryption and rights protection</span></span>
- <span data-ttu-id="257be-136">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="257be-136">Remove</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="257be-137">Outlook 2013 en hoger ondersteunt het weergeven van beleidstips voor slechts enkele voorwaarden en uitzonderingen</span><span class="sxs-lookup"><span data-stu-id="257be-137">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="257be-138">Momenteel ondersteunt Outlook 2013 en hoger het weergeven van beleidstips voor beleidsregels die geen voorwaarde of uitzondering bevatten, afgezien van de onderstaande voorwaarden en bijbehorende uitzonderingen:</span><span class="sxs-lookup"><span data-stu-id="257be-138">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="257be-139">Inhoud bevat (werkt alleen voor gevoelige informatietypen.</span><span class="sxs-lookup"><span data-stu-id="257be-139">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="257be-140">Gevoeligheidslabels worden niet ondersteund)</span><span class="sxs-lookup"><span data-stu-id="257be-140">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="257be-141">Inhoud wordt gedeeld</span><span class="sxs-lookup"><span data-stu-id="257be-141">Content is shared</span></span>

<span data-ttu-id="257be-142">Houd er rekening mee dat alle voorwaarden werken voor e-mailberichten die zijn geschreven in de Outlook-client-app, waar ze overeenkomen met inhoud en beschermende acties voor inhoud afdwingen.</span><span class="sxs-lookup"><span data-stu-id="257be-142">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="257be-143">Het weergeven van beleidstips voor gebruikers wordt echter nog niet ondersteund voor voorwaarden die behalve de hierboven genoemde voorwaarden worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="257be-143">However, showing policy tips to users is not yet supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="257be-144">Outlook 2013 en hoger ondersteunt het weergeven van beleidstips voor alleen bepaalde typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="257be-144">Outlook 2013 and later supports showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="257be-145">De lijst met out-of-the-box gevoelige informatietypen die worden gedetecteerd voor het weergeven van DLP-beleidstips in Outlook op bureaublad (2013 en hoger) zijn de volgende:</span><span class="sxs-lookup"><span data-stu-id="257be-145">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) are the following :</span></span>

- <span data-ttu-id="257be-146">ABA-routeringsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-146">ABA Routing Number</span></span>
- <span data-ttu-id="257be-147">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="257be-147">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="257be-148">Australië Bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="257be-148">Australia Bank Account Number</span></span>
- <span data-ttu-id="257be-149">Australië Medical Account Number</span><span class="sxs-lookup"><span data-stu-id="257be-149">Australia Medical Account Number</span></span>
- <span data-ttu-id="257be-150">Australië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-150">Australia Passport Number</span></span>
- <span data-ttu-id="257be-151">Australië Belastingbestandsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-151">Australia Tax File Number</span></span>
- <span data-ttu-id="257be-152">Azure DocumentDB Auth Key</span><span class="sxs-lookup"><span data-stu-id="257be-152">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="257be-153">Azure IAAS Database Connection String en Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="257be-153">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="257be-154">Azure IoT-verbindingsreeks</span><span class="sxs-lookup"><span data-stu-id="257be-154">Azure IoT Connection String</span></span>  
- <span data-ttu-id="257be-155">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="257be-155">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="257be-156">Verbindingsreeks Azure Redis Cache</span><span class="sxs-lookup"><span data-stu-id="257be-156">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="257be-157">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="257be-157">Azure SAS</span></span>  
- <span data-ttu-id="257be-158">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="257be-158">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="257be-159">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="257be-159">Azure Storage Account Key</span></span>  
- <span data-ttu-id="257be-160">Azure Storage Account Key (Generic)</span><span class="sxs-lookup"><span data-stu-id="257be-160">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="257be-161">Nationaal nummer belgië</span><span class="sxs-lookup"><span data-stu-id="257be-161">Belgium National Number</span></span>
- <span data-ttu-id="257be-162">Brazilië CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-162">Brazil CPF Number</span></span>
- <span data-ttu-id="257be-163">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="257be-163">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="257be-164">Nationale id-kaart brazilië (RG)</span><span class="sxs-lookup"><span data-stu-id="257be-164">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="257be-165">Canada Bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="257be-165">Canada Bank Account Number</span></span>
- <span data-ttu-id="257be-166">Canada Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-166">Canada Driver's License Number</span></span>
- <span data-ttu-id="257be-167">Canada Health Service Number</span><span class="sxs-lookup"><span data-stu-id="257be-167">Canada Health Service Number</span></span>
- <span data-ttu-id="257be-168">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-168">Canada Passport Number</span></span>
- <span data-ttu-id="257be-169">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="257be-169">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="257be-170">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="257be-170">Canada Social Insurance Number</span></span>
- <span data-ttu-id="257be-171">Chili-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-171">Chile Identity Card Number</span></span>
- <span data-ttu-id="257be-172">China Resident Identity Card (PRC) Number</span><span class="sxs-lookup"><span data-stu-id="257be-172">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="257be-173">Creditcardnummer</span><span class="sxs-lookup"><span data-stu-id="257be-173">Credit Card Number</span></span>
- <span data-ttu-id="257be-174">Kroatië-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-174">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="257be-175">OIB-nummer (Croatia Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="257be-175">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="257be-176">Tsjechische persoonlijke identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-176">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="257be-177">Denemarken Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-177">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="257be-178">Nummer van Het Bureau voor drugshandhaving (DEA)</span><span class="sxs-lookup"><span data-stu-id="257be-178">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="257be-179">EU-betaalkaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-179">EU Debit Card Number</span></span>
- <span data-ttu-id="257be-180">Eu-rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-180">EU Driver's License Number</span></span>  
- <span data-ttu-id="257be-181">NATIONAAL EU-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="257be-181">EU National Identification Number</span></span>  
- <span data-ttu-id="257be-182">EU-paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-182">EU Passport Number</span></span>  
- <span data-ttu-id="257be-183">EU-SSN -nummer (Social Security Number) of equivalente id</span><span class="sxs-lookup"><span data-stu-id="257be-183">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="257be-184">EU-belastingidentificatienummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="257be-184">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="257be-185">Nationale finland-id</span><span class="sxs-lookup"><span data-stu-id="257be-185">Finland National ID</span></span>
- <span data-ttu-id="257be-186">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-186">Finland Passport Number</span></span>
- <span data-ttu-id="257be-187">France Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-187">France Driver's License Number</span></span>
- <span data-ttu-id="257be-188">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="257be-188">France National ID Card (CNI)</span></span>
- <span data-ttu-id="257be-189">Frankrijk Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-189">France Passport Number</span></span>
- <span data-ttu-id="257be-190">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="257be-190">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="257be-191">Duits rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-191">German Driver's License Number</span></span>
- <span data-ttu-id="257be-192">Duits paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-192">German Passport Number</span></span>
- <span data-ttu-id="257be-193">Duitsland-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-193">Germany Identity Card Number</span></span>
- <span data-ttu-id="257be-194">Nationale griekenland-id-kaart</span><span class="sxs-lookup"><span data-stu-id="257be-194">Greece National ID Card</span></span>  
- <span data-ttu-id="257be-195">Hong Kong Identity Card (HKID) Number</span><span class="sxs-lookup"><span data-stu-id="257be-195">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="257be-196">India Permanent Account Number (PAN)</span><span class="sxs-lookup"><span data-stu-id="257be-196">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="257be-197">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="257be-197">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="257be-198">KTP-nummer (Indonesia Identity Card)</span><span class="sxs-lookup"><span data-stu-id="257be-198">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="257be-199">IBAN (International Banking Account Number)</span><span class="sxs-lookup"><span data-stu-id="257be-199">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="257be-200">Internationale classificatie van ziektes (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="257be-200">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="257be-201">Internationale classificatie van ziektes (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="257be-201">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="257be-202">IP Address</span><span class="sxs-lookup"><span data-stu-id="257be-202">IP Address</span></span>
- <span data-ttu-id="257be-203">Ierland Personal Public Service (PPS)-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-203">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="257be-204">Israel Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="257be-204">Israel Bank Account Number</span></span>
- <span data-ttu-id="257be-205">Nationale israël-id</span><span class="sxs-lookup"><span data-stu-id="257be-205">Israel National ID</span></span>
- <span data-ttu-id="257be-206">Rijbewijsnummer van Italië</span><span class="sxs-lookup"><span data-stu-id="257be-206">Italy Driver's License Number</span></span>
- <span data-ttu-id="257be-207">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="257be-207">Japan Bank Account Number</span></span>
- <span data-ttu-id="257be-208">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-208">Japan Driver's License Number</span></span>
- <span data-ttu-id="257be-209">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-209">Japan Passport Number</span></span>
- <span data-ttu-id="257be-210">Japan Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="257be-210">Japan Resident Registration Number</span></span>
- <span data-ttu-id="257be-211">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="257be-211">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="257be-212">Japans nummer van een verblijfskaart</span><span class="sxs-lookup"><span data-stu-id="257be-212">Japanese Residence Card Number</span></span>
- <span data-ttu-id="257be-213">Maleisische identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-213">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="257be-214">BSN-nummer (Netherlands Citizen's Service)</span><span class="sxs-lookup"><span data-stu-id="257be-214">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="257be-215">Nieuw-Zeelands ministerie van Gezondheid Nummer</span><span class="sxs-lookup"><span data-stu-id="257be-215">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="257be-216">Noorwegen-identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-216">Norway Identity Number</span></span>  
- <span data-ttu-id="257be-217">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="257be-217">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="257be-218">Polen-identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="257be-218">Poland Identity Card</span></span>
- <span data-ttu-id="257be-219">Nationale Polen-id (PESEL)</span><span class="sxs-lookup"><span data-stu-id="257be-219">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="257be-220">Polen-paspoort</span><span class="sxs-lookup"><span data-stu-id="257be-220">Poland Passport</span></span>
- <span data-ttu-id="257be-221">Portugal Burgerkaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-221">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="257be-222">Nationale id van Saudi-Arabië</span><span class="sxs-lookup"><span data-stu-id="257be-222">Saudi Arabia National ID</span></span>
- <span data-ttu-id="257be-223">NRIC-nummer (National Registration Identity Card) van Singapore</span><span class="sxs-lookup"><span data-stu-id="257be-223">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="257be-224">Zuid-Afrika-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="257be-224">South Africa Identification Number</span></span>  
- <span data-ttu-id="257be-225">Registratienummer voor inwoners van Zuid-Korea</span><span class="sxs-lookup"><span data-stu-id="257be-225">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="257be-226">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="257be-226">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="257be-227">SQL Server-verbindingsreeks</span><span class="sxs-lookup"><span data-stu-id="257be-227">SQL Server Connection String</span></span>  
- <span data-ttu-id="257be-228">Nationale id Zweden</span><span class="sxs-lookup"><span data-stu-id="257be-228">Sweden National ID</span></span>
- <span data-ttu-id="257be-229">Zweden Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-229">Sweden Passport Number</span></span>
- <span data-ttu-id="257be-230">SWIFT-code</span><span class="sxs-lookup"><span data-stu-id="257be-230">SWIFT Code</span></span>
- <span data-ttu-id="257be-231">Nationale taiwan-id</span><span class="sxs-lookup"><span data-stu-id="257be-231">Taiwan National ID</span></span>
- <span data-ttu-id="257be-232">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-232">Taiwan Passport Number</span></span>
- <span data-ttu-id="257be-233">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="257be-233">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="257be-234">Thaise bevolkingsidentificatiecode</span><span class="sxs-lookup"><span data-stu-id="257be-234">Thai Population Identification Code</span></span>
- <span data-ttu-id="257be-235">Turks nationaal identificatienummer</span><span class="sxs-lookup"><span data-stu-id="257be-235">Turkish National Identification number</span></span>
- <span data-ttu-id="257be-236">VK</span><span class="sxs-lookup"><span data-stu-id="257be-236">U.K.</span></span> <span data-ttu-id="257be-237">Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-237">Driver's License Number</span></span>
- <span data-ttu-id="257be-238">VK</span><span class="sxs-lookup"><span data-stu-id="257be-238">U.K.</span></span> <span data-ttu-id="257be-239">Kieslijstnummer</span><span class="sxs-lookup"><span data-stu-id="257be-239">Electoral Roll Number</span></span>
- <span data-ttu-id="257be-240">VK</span><span class="sxs-lookup"><span data-stu-id="257be-240">U.K.</span></span> <span data-ttu-id="257be-241">National Health Service Number</span><span class="sxs-lookup"><span data-stu-id="257be-241">National Health Service Number</span></span>
- <span data-ttu-id="257be-242">VK</span><span class="sxs-lookup"><span data-stu-id="257be-242">U.K.</span></span> <span data-ttu-id="257be-243">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="257be-243">National Insurance Number (NINO)</span></span>
- <span data-ttu-id="257be-244">V.S. / VK</span><span class="sxs-lookup"><span data-stu-id="257be-244">U.S. / U.K.</span></span> <span data-ttu-id="257be-245">Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-245">Passport Number</span></span>
- <span data-ttu-id="257be-246">Amerikaans bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="257be-246">U.S. Bank Account Number</span></span>
- <span data-ttu-id="257be-247">Amerikaans rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-247">U.S. Driver's License Number</span></span>
- <span data-ttu-id="257be-248">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="257be-248">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="257be-249">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="257be-249">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="257be-250">Houd er rekening mee dat aangepaste gevoelige informatietypen ook worden ondersteund voor DLP-beleidstips, naast de bovenstaande kant-en-kijkgevoelige informatietypen.</span><span class="sxs-lookup"><span data-stu-id="257be-250">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="257be-251">Preventie van gegevensverlies op eindpunt ondersteunt beleidstips voor alleen bepaalde typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="257be-251">Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="257be-252">De lijst met kant-en-weer gevoelige informatietypen die worden gedetecteerd in documenten die zich op eindpuntapparaten bewonen, zijn de volgende:</span><span class="sxs-lookup"><span data-stu-id="257be-252">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="257be-253">ABA-routeringsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-253">ABA Routing Number</span></span> 
- <span data-ttu-id="257be-254">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="257be-254">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="257be-255">Australië Bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="257be-255">Australia Bank Account Number</span></span> 
- <span data-ttu-id="257be-256">Australië Medical Account Number</span><span class="sxs-lookup"><span data-stu-id="257be-256">Australia Medical Account Number</span></span> 
- <span data-ttu-id="257be-257">Australië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-257">Australia Passport Number</span></span> 
- <span data-ttu-id="257be-258">Australië Belastingbestandsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-258">Australia Tax File Number</span></span> 
- <span data-ttu-id="257be-259">Australisch bedrijfsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-259">Australian Business Number</span></span> 
- <span data-ttu-id="257be-260">Australisch bedrijfsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-260">Australian Company Number</span></span> 
- <span data-ttu-id="257be-261">Oostenrijks rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-261">Austria Driver's License Number</span></span> 
- <span data-ttu-id="257be-262">Oostenrijk-identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="257be-262">Austria Identity Card</span></span> 
- <span data-ttu-id="257be-263">Oostenrijks paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-263">Austria Passport Number</span></span> 
- <span data-ttu-id="257be-264">Oostenrijks sociaal-zekerheidsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-264">Austria Social Security Number</span></span> 
- <span data-ttu-id="257be-265">Oostenrijks btw-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-265">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="257be-266">Oostenrijks btw-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-266">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="257be-267">Azure DocumentDB Auth Key</span><span class="sxs-lookup"><span data-stu-id="257be-267">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="257be-268">Azure IAAS Database Connection String en Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="257be-268">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="257be-269">Azure IoT-verbindingsreeks</span><span class="sxs-lookup"><span data-stu-id="257be-269">Azure IoT Connection String</span></span> 
- <span data-ttu-id="257be-270">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="257be-270">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="257be-271">Verbindingsreeks Azure Redis Cache</span><span class="sxs-lookup"><span data-stu-id="257be-271">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="257be-272">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="257be-272">Azure SAS</span></span> 
- <span data-ttu-id="257be-273">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="257be-273">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="257be-274">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="257be-274">Azure Storage Account Key</span></span> 
- <span data-ttu-id="257be-275">Azure Storage Account Key (Generic)</span><span class="sxs-lookup"><span data-stu-id="257be-275">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="257be-276">Nummer van het Rijbewijs van België</span><span class="sxs-lookup"><span data-stu-id="257be-276">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="257be-277">Nationaal nummer belgië</span><span class="sxs-lookup"><span data-stu-id="257be-277">Belgium National Number</span></span> 
- <span data-ttu-id="257be-278">België Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-278">Belgium Passport Number</span></span> 
- <span data-ttu-id="257be-279">België Btw-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-279">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="257be-280">Brazilië CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-280">Brazil CPF Number</span></span> 
- <span data-ttu-id="257be-281">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="257be-281">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="257be-282">Nationale id-kaart brazilië (RG)</span><span class="sxs-lookup"><span data-stu-id="257be-282">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="257be-283">Bulgarije Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-283">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="257be-284">Bulgarije Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-284">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="257be-285">Bulgarije Uniform Burgernummer</span><span class="sxs-lookup"><span data-stu-id="257be-285">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="257be-286">Canada Bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="257be-286">Canada Bank Account Number</span></span> 
- <span data-ttu-id="257be-287">Canada Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-287">Canada Driver's License Number</span></span> 
- <span data-ttu-id="257be-288">Canada Health Service Number</span><span class="sxs-lookup"><span data-stu-id="257be-288">Canada Health Service Number</span></span> 
- <span data-ttu-id="257be-289">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-289">Canada Passport Number</span></span> 
- <span data-ttu-id="257be-290">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="257be-290">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="257be-291">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="257be-291">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="257be-292">Chili-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-292">Chile Identity Card Number</span></span> 
- <span data-ttu-id="257be-293">China Resident Identity Card (PRC) Number</span><span class="sxs-lookup"><span data-stu-id="257be-293">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="257be-294">Creditcardnummer</span><span class="sxs-lookup"><span data-stu-id="257be-294">Credit Card Number</span></span> 
- <span data-ttu-id="257be-295">Kroatische nummer van het rijbewijs</span><span class="sxs-lookup"><span data-stu-id="257be-295">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="257be-296">Kroatië-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-296">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="257be-297">Kroatië National ID Card Number</span><span class="sxs-lookup"><span data-stu-id="257be-297">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="257be-298">Kroatië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-298">Croatia Passport Number</span></span> 
- <span data-ttu-id="257be-299">OIB-nummer (Croatia Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="257be-299">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="257be-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span><span class="sxs-lookup"><span data-stu-id="257be-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="257be-301">CSCAN-GENERAL0140 General Symmetric Key</span><span class="sxs-lookup"><span data-stu-id="257be-301">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="257be-302">Cyprus Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-302">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="257be-303">Cyprus-identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="257be-303">Cyprus Identity Card</span></span> 
- <span data-ttu-id="257be-304">Cyprus Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-304">Cyprus Passport Number</span></span> 
- <span data-ttu-id="257be-305">Cyprus Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-305">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="257be-306">Tsjechisch rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-306">Czech Driver's License Number</span></span> 
- <span data-ttu-id="257be-307">Tsjechische persoonlijke identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-307">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="257be-308">Tsjechische Republiek Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-308">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="257be-309">Rijbewijsnummer van Denemarken</span><span class="sxs-lookup"><span data-stu-id="257be-309">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="257be-310">Denemarken Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-310">Denmark Passport Number</span></span> 
- <span data-ttu-id="257be-311">Denemarken Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-311">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="257be-312">Nummer van Het Bureau voor drugshandhaving (DEA)</span><span class="sxs-lookup"><span data-stu-id="257be-312">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="257be-313">Estlands rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-313">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="257be-314">Estlands paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-314">Estonia Passport Number</span></span> 
- <span data-ttu-id="257be-315">Estlandse persoonlijke identificatiecode</span><span class="sxs-lookup"><span data-stu-id="257be-315">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="257be-316">EU-betaalkaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-316">EU Debit Card Number</span></span> 
- <span data-ttu-id="257be-317">Eu-rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-317">EU Driver's License Number</span></span> 
- <span data-ttu-id="257be-318">NATIONAAL EU-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="257be-318">EU National Identification Number</span></span> 
- <span data-ttu-id="257be-319">EU-paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-319">EU Passport Number</span></span> 
- <span data-ttu-id="257be-320">EU-SSN -nummer (Social Security Number) of equivalente id</span><span class="sxs-lookup"><span data-stu-id="257be-320">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="257be-321">EU-belastingidentificatienummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="257be-321">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="257be-322">Finland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-322">Finland Driver's License Number</span></span> 
- <span data-ttu-id="257be-323">Finland European Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="257be-323">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="257be-324">Nationale finland-id</span><span class="sxs-lookup"><span data-stu-id="257be-324">Finland National ID</span></span> 
- <span data-ttu-id="257be-325">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-325">Finland Passport Number</span></span> 
- <span data-ttu-id="257be-326">France Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-326">France Driver's License Number</span></span> 
- <span data-ttu-id="257be-327">France Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="257be-327">France Health Insurance Number</span></span> 
- <span data-ttu-id="257be-328">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="257be-328">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="257be-329">Frankrijk Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-329">France Passport Number</span></span> 
- <span data-ttu-id="257be-330">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="257be-330">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="257be-331">France Tax Identification Number (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="257be-331">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="257be-332">Frankrijk Btw-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-332">France Value Added Tax Number</span></span> 
- <span data-ttu-id="257be-333">Duits rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-333">German Driver's License Number</span></span> 
- <span data-ttu-id="257be-334">Duits paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-334">German Passport Number</span></span> 
- <span data-ttu-id="257be-335">Duitsland-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-335">Germany Identity Card Number</span></span> 
- <span data-ttu-id="257be-336">Duitsland Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-336">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="257be-337">Duitsland Btw-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-337">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="257be-338">Griekenland Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-338">Greece Driver's License Number</span></span> 
- <span data-ttu-id="257be-339">Nationale griekenland-id-kaart</span><span class="sxs-lookup"><span data-stu-id="257be-339">Greece National ID Card</span></span> 
- <span data-ttu-id="257be-340">Griekenland Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-340">Greece Passport Number</span></span> 
- <span data-ttu-id="257be-341">Griekenland-nummer voor sociale zekerheid (AMKA)</span><span class="sxs-lookup"><span data-stu-id="257be-341">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="257be-342">Griekse btw-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="257be-342">Greek Tax identification Number</span></span> 
- <span data-ttu-id="257be-343">Hong Kong Identity Card (HKID) Number</span><span class="sxs-lookup"><span data-stu-id="257be-343">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="257be-344">Hongaars sociaal-zekerheidsnummer (TAJ)</span><span class="sxs-lookup"><span data-stu-id="257be-344">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="257be-345">Hongaars btw-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-345">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="257be-346">Licentienummer van Hongarije</span><span class="sxs-lookup"><span data-stu-id="257be-346">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="257be-347">Hongarije Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-347">Hungary Passport Number</span></span> 
- <span data-ttu-id="257be-348">Hongarije Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-348">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="257be-349">Btw-nummer van Hongarije</span><span class="sxs-lookup"><span data-stu-id="257be-349">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="257be-350">India Permanent Account Number (PAN)</span><span class="sxs-lookup"><span data-stu-id="257be-350">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="257be-351">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="257be-351">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="257be-352">KTP-nummer (Indonesia Identity Card)</span><span class="sxs-lookup"><span data-stu-id="257be-352">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="257be-353">IBAN (International Banking Account Number)</span><span class="sxs-lookup"><span data-stu-id="257be-353">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="257be-354">Internationale classificatie van ziektes (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="257be-354">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="257be-355">Internationale classificatie van ziektes (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="257be-355">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="257be-356">IP Address</span><span class="sxs-lookup"><span data-stu-id="257be-356">IP Address</span></span> 
- <span data-ttu-id="257be-357">Ireland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-357">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="257be-358">Ierland Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-358">Ireland Passport Number</span></span> 
- <span data-ttu-id="257be-359">Ierland Personal Public Service (PPS)-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-359">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="257be-360">Israel Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="257be-360">Israel Bank Account Number</span></span> 
- <span data-ttu-id="257be-361">Nationale israël-id</span><span class="sxs-lookup"><span data-stu-id="257be-361">Israel National ID</span></span> 
- <span data-ttu-id="257be-362">Rijbewijsnummer van Italië</span><span class="sxs-lookup"><span data-stu-id="257be-362">Italy Driver's License Number</span></span> 
- <span data-ttu-id="257be-363">Italiaanse fiscale code</span><span class="sxs-lookup"><span data-stu-id="257be-363">Italy Fiscal Code</span></span> 
- <span data-ttu-id="257be-364">Italië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-364">Italy Passport Number</span></span> 
- <span data-ttu-id="257be-365">#A0 #A0 #A0 #A0 #A0 #A</span><span class="sxs-lookup"><span data-stu-id="257be-365">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="257be-366">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="257be-366">Japan Bank Account Number</span></span> 
- <span data-ttu-id="257be-367">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-367">Japan Driver's License Number</span></span> 
- <span data-ttu-id="257be-368">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-368">Japan Passport Number</span></span> 
- <span data-ttu-id="257be-369">Japan Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="257be-369">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="257be-370">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="257be-370">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="257be-371">Japans My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="257be-371">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="257be-372">Japans Mijn nummer Persoonlijk</span><span class="sxs-lookup"><span data-stu-id="257be-372">Japanese My Number Personal</span></span> 
- <span data-ttu-id="257be-373">Japans nummer van een verblijfskaart</span><span class="sxs-lookup"><span data-stu-id="257be-373">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="257be-374">Letlandse rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-374">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="257be-375">Letland Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-375">Latvia Passport Number</span></span> 
- <span data-ttu-id="257be-376">Persoonlijke code letland</span><span class="sxs-lookup"><span data-stu-id="257be-376">Latvia Personal Code</span></span> 
- <span data-ttu-id="257be-377">Litouws rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-377">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="257be-378">Litouws paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-378">Lithuania Passport Number</span></span> 
- <span data-ttu-id="257be-379">Persoonlijke code litouwen</span><span class="sxs-lookup"><span data-stu-id="257be-379">Lithuania Personal Code</span></span> 
- <span data-ttu-id="257be-380">Luxemburgs rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-380">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="257be-381">Luxemburg National Identification Number (Natuurlijke personen)</span><span class="sxs-lookup"><span data-stu-id="257be-381">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="257be-382">Luxemburg National Identification Number (Niet-natuurlijke personen)</span><span class="sxs-lookup"><span data-stu-id="257be-382">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="257be-383">Luxemburg Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-383">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="257be-384">Maleisische identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-384">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="257be-385">Malta Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="257be-385">Malta Driver's License Number</span></span> 
- <span data-ttu-id="257be-386">Malta-identiteitskaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-386">Malta Identity Card Number</span></span> 
- <span data-ttu-id="257be-387">Malta Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-387">Malta Passport Number</span></span> 
- <span data-ttu-id="257be-388">Malta Tax ID-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-388">Malta Tax ID Number</span></span> 
- <span data-ttu-id="257be-389">BSN-nummer (Netherlands Citizen's Service)</span><span class="sxs-lookup"><span data-stu-id="257be-389">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="257be-390">Nederlands rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-390">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="257be-391">Nederlands paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-391">Netherlands Passport Number</span></span> 
- <span data-ttu-id="257be-392">Btw-nummer van Nederland</span><span class="sxs-lookup"><span data-stu-id="257be-392">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="257be-393">Btw-nummer voor Nederland</span><span class="sxs-lookup"><span data-stu-id="257be-393">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="257be-394">Nieuw-Zeelands bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="257be-394">New Zealand bank account number</span></span> 
- <span data-ttu-id="257be-395">Nieuw-Zeelandse rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-395">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="257be-396">Nieuw-Zeelandse belastingdienst</span><span class="sxs-lookup"><span data-stu-id="257be-396">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="257be-397">Nieuw-Zeelands ministerie van Gezondheid Nummer</span><span class="sxs-lookup"><span data-stu-id="257be-397">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="257be-398">Nieuw-Zeelandse sociale voorzieningennummer</span><span class="sxs-lookup"><span data-stu-id="257be-398">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="257be-399">Noorwegen-identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-399">Norway Identity Number</span></span> 
- <span data-ttu-id="257be-400">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="257be-400">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="257be-401">Polen Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-401">Poland Driver's License Number</span></span> 
- <span data-ttu-id="257be-402">Polen-identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="257be-402">Poland Identity Card</span></span> 
- <span data-ttu-id="257be-403">Nationale Polen-id (PESEL)</span><span class="sxs-lookup"><span data-stu-id="257be-403">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="257be-404">Polen-paspoort</span><span class="sxs-lookup"><span data-stu-id="257be-404">Poland Passport</span></span> 
- <span data-ttu-id="257be-405">Polen Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-405">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="257be-406">Pools REGON-nummer</span><span class="sxs-lookup"><span data-stu-id="257be-406">Polish REGON Number</span></span> 
- <span data-ttu-id="257be-407">Portugal Burgerkaartnummer</span><span class="sxs-lookup"><span data-stu-id="257be-407">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="257be-408">Portugal Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-408">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="257be-409">Portugal Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-409">Portugal Passport Number</span></span> 
- <span data-ttu-id="257be-410">Portugal Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-410">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="257be-411">Roemenië Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-411">Romania Driver's License Number</span></span> 
- <span data-ttu-id="257be-412">Roemenië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-412">Romania Passport Number</span></span> 
- <span data-ttu-id="257be-413">Roemeense persoonlijke numerieke code (CNP)</span><span class="sxs-lookup"><span data-stu-id="257be-413">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="257be-414">Russisch paspoortnummer (binnenlands)</span><span class="sxs-lookup"><span data-stu-id="257be-414">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="257be-415">Russisch paspoortnummer (internationaal)</span><span class="sxs-lookup"><span data-stu-id="257be-415">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="257be-416">Nationale id van Saudi-Arabië</span><span class="sxs-lookup"><span data-stu-id="257be-416">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="257be-417">NRIC-nummer (National Registration Identity Card) van Singapore</span><span class="sxs-lookup"><span data-stu-id="257be-417">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="257be-418">Slowakije Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-418">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="257be-419">Slowakije Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-419">Slovakia Passport Number</span></span> 
- <span data-ttu-id="257be-420">Slowakije Persoonlijk Nummer</span><span class="sxs-lookup"><span data-stu-id="257be-420">Slovakia Personal Number</span></span> 
- <span data-ttu-id="257be-421">Sloveens rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-421">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="257be-422">Slovenië Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-422">Slovenia Passport Number</span></span> 
- <span data-ttu-id="257be-423">Slovenië Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-423">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="257be-424">Slovenië Unique Master Citizen Number</span><span class="sxs-lookup"><span data-stu-id="257be-424">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="257be-425">Zuid-Afrika-identificatienummer</span><span class="sxs-lookup"><span data-stu-id="257be-425">South Africa Identification Number</span></span> 
- <span data-ttu-id="257be-426">Registratienummer voor inwoners van Zuid-Korea</span><span class="sxs-lookup"><span data-stu-id="257be-426">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="257be-427">Spanje DNI</span><span class="sxs-lookup"><span data-stu-id="257be-427">Spain DNI</span></span> 
- <span data-ttu-id="257be-428">Rijbewijsnummer van Spanje</span><span class="sxs-lookup"><span data-stu-id="257be-428">Spain Driver's License Number</span></span> 
- <span data-ttu-id="257be-429">Spanje Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-429">Spain Passport Number</span></span> 
- <span data-ttu-id="257be-430">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="257be-430">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="257be-431">Spanje Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-431">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="257be-432">SQL Server-verbindingsreeks</span><span class="sxs-lookup"><span data-stu-id="257be-432">SQL Server Connection String</span></span> 
- <span data-ttu-id="257be-433">Zweden Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-433">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="257be-434">Nationale id Zweden</span><span class="sxs-lookup"><span data-stu-id="257be-434">Sweden National ID</span></span> 
- <span data-ttu-id="257be-435">Zweden Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-435">Sweden Passport Number</span></span> 
- <span data-ttu-id="257be-436">Zweden Tax Identification Number</span><span class="sxs-lookup"><span data-stu-id="257be-436">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="257be-437">SWIFT-code</span><span class="sxs-lookup"><span data-stu-id="257be-437">SWIFT Code</span></span> 
- <span data-ttu-id="257be-438">Zwitserse socialezekerheidsnummer AHV</span><span class="sxs-lookup"><span data-stu-id="257be-438">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="257be-439">Nationale taiwan-id</span><span class="sxs-lookup"><span data-stu-id="257be-439">Taiwan National ID</span></span> 
- <span data-ttu-id="257be-440">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="257be-440">Taiwan Passport Number</span></span> 
- <span data-ttu-id="257be-441">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="257be-441">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="257be-442">Thaise bevolkingsidentificatiecode</span><span class="sxs-lookup"><span data-stu-id="257be-442">Thai Population Identification Code</span></span> 
- <span data-ttu-id="257be-443">Turks nationaal identificatienummer</span><span class="sxs-lookup"><span data-stu-id="257be-443">Turkish National Identification number</span></span> 
- <span data-ttu-id="257be-444">VK</span><span class="sxs-lookup"><span data-stu-id="257be-444">U.K.</span></span> <span data-ttu-id="257be-445">Rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-445">Driver's License Number</span></span> 
- <span data-ttu-id="257be-446">VK</span><span class="sxs-lookup"><span data-stu-id="257be-446">U.K.</span></span> <span data-ttu-id="257be-447">Kieslijstnummer</span><span class="sxs-lookup"><span data-stu-id="257be-447">Electoral Roll Number</span></span> 
- <span data-ttu-id="257be-448">VK</span><span class="sxs-lookup"><span data-stu-id="257be-448">U.K.</span></span> <span data-ttu-id="257be-449">National Health Service Number</span><span class="sxs-lookup"><span data-stu-id="257be-449">National Health Service Number</span></span> 
- <span data-ttu-id="257be-450">VK</span><span class="sxs-lookup"><span data-stu-id="257be-450">U.K.</span></span> <span data-ttu-id="257be-451">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="257be-451">National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="257be-452">VK</span><span class="sxs-lookup"><span data-stu-id="257be-452">U.K.</span></span> <span data-ttu-id="257be-453">Uniek referentienummer voor belastingbetalers</span><span class="sxs-lookup"><span data-stu-id="257be-453">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="257be-454">V.S. / VK</span><span class="sxs-lookup"><span data-stu-id="257be-454">U.S. / U.K.</span></span> <span data-ttu-id="257be-455">Paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="257be-455">Passport Number</span></span> 
- <span data-ttu-id="257be-456">Amerikaans bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="257be-456">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="257be-457">Amerikaans rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="257be-457">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="257be-458">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="257be-458">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="257be-459">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="257be-459">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="257be-460">Oekraine Paspoortnummer (binnenlands)</span><span class="sxs-lookup"><span data-stu-id="257be-460">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="257be-461">Oekraine Paspoortnummer (internationaal)</span><span class="sxs-lookup"><span data-stu-id="257be-461">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="257be-462">Houd er rekening mee dat aangepaste gevoelige informatietypen ook worden gedetecteerd naast de bovenstaande kant-en-zeker gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="257be-462">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="257be-463">Ondersteuningsmatrix voor DLP-beleidstips in Microsoft-apps</span><span class="sxs-lookup"><span data-stu-id="257be-463">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="257be-464">**App en platform**</span><span class="sxs-lookup"><span data-stu-id="257be-464">**App and platform**</span></span>|<span data-ttu-id="257be-465">**Ondersteuning voor DLP-beleidstips**</span><span class="sxs-lookup"><span data-stu-id="257be-465">**DLP policy tip support**</span></span>|<span data-ttu-id="257be-466">**Ondersteunde typen gevoelige informatie**</span><span class="sxs-lookup"><span data-stu-id="257be-466">**Sensitive information types supported**</span></span>|<span data-ttu-id="257be-467">**Ondersteunde predicaten en acties**</span><span class="sxs-lookup"><span data-stu-id="257be-467">**Predicates and actions supported**</span></span>|<span data-ttu-id="257be-468">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="257be-468">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="257be-469">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="257be-469">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="257be-470">Alles</span><span class="sxs-lookup"><span data-stu-id="257be-470">All</span></span>|<span data-ttu-id="257be-471">Subset</span><span class="sxs-lookup"><span data-stu-id="257be-471">Subset</span></span>|<span data-ttu-id="257be-472">Zie [Tips voor beleidstips voor preventie van gegevensverlies](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="257be-472">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="257be-473">**Outlook Win32 (Outlook 2013 en hoger)**</span><span class="sxs-lookup"><span data-stu-id="257be-473">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="257be-474">Subset</span><span class="sxs-lookup"><span data-stu-id="257be-474">Subset</span></span>|<span data-ttu-id="257be-475">Subset</span><span class="sxs-lookup"><span data-stu-id="257be-475">Subset</span></span>|<span data-ttu-id="257be-476">Zie Ondersteuning voor [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) en hoger met beleidstips voor slechts enkele voorwaarden en uitzonderingen en Ondersteuning voor [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) en later met beleidstips voor alleen bepaalde typen gevoelige informatie voor meer informatie over ondersteuning voor gevoelige informatietypen en DLP-voorwaarden en -acties die worden ondersteund voor het weergeven van DLP-beleidstips in Outlook Win32.</span><span class="sxs-lookup"><span data-stu-id="257be-476">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later supports showing policy tips for only some sensitive information types](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="257be-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="257be-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="257be-478">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-478">None</span></span>|<span data-ttu-id="257be-479">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-479">None</span></span>|<span data-ttu-id="257be-480">DLP-beleidstips worden niet ondersteund in Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="257be-480">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="257be-481">**Sharepoint Online/One Drive for Business Web Client**</span><span class="sxs-lookup"><span data-stu-id="257be-481">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="257be-482">Alles</span><span class="sxs-lookup"><span data-stu-id="257be-482">All</span></span>|<span data-ttu-id="257be-483">Alle SPO/ODB-predicaten en acties in DLP</span><span class="sxs-lookup"><span data-stu-id="257be-483">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="257be-484">**Win32/ One Drive for Business Win32-client van Sharepoint**</span><span class="sxs-lookup"><span data-stu-id="257be-484">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="257be-485">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-485">None</span></span>|<span data-ttu-id="257be-486">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-486">None</span></span>|<span data-ttu-id="257be-487">DLP-beleidstips worden niet ondersteund in sharepoint- of OneDrive-bureaubladclient-apps</span><span class="sxs-lookup"><span data-stu-id="257be-487">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="257be-488">**Word, Excel, Powerpoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="257be-488">**Word, Excel, Powerpoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="257be-489">Alles</span><span class="sxs-lookup"><span data-stu-id="257be-489">All</span></span>|<span data-ttu-id="257be-490">Alle SPO/ODB-predicaten en acties in DLP</span><span class="sxs-lookup"><span data-stu-id="257be-490">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="257be-491">DLP-beleidstip wordt ondersteund als het document wordt gehost in de SPO- of ODB-web-app en het DLP-beleid al is gestempeld.</span><span class="sxs-lookup"><span data-stu-id="257be-491">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="257be-492">**Word, Excel, Powerpoint Mobile Client**</span><span class="sxs-lookup"><span data-stu-id="257be-492">**Word, Excel, Powerpoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="257be-493">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-493">None</span></span>|<span data-ttu-id="257be-494">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-494">None</span></span>|<span data-ttu-id="257be-495">DLP-beleidstips worden niet ondersteund in mobiele apps voor Office.</span><span class="sxs-lookup"><span data-stu-id="257be-495">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="257be-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="257be-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="257be-497">Alles</span><span class="sxs-lookup"><span data-stu-id="257be-497">All</span></span>|<span data-ttu-id="257be-498">Alle Teams-predicaten in DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="257be-498">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="257be-499">Beleidstips worden weergegeven wanneer een bericht wordt gemarkeerd als 'Dit bericht is gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="257be-499">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="257be-500">Wat kan ik doen?</span><span class="sxs-lookup"><span data-stu-id="257be-500">What can I do?”</span></span> <span data-ttu-id="257be-501">Wanneer u op de koppeling klikt, kan de gebruiker de gevoelige informatietypen controleren die zijn gedetecteerd en een probleem kunnen overschrijven of rapporteren indien toegestaan door de beheerder. Houd er rekening mee dat er geen beleidstips worden weergegeven voor bestanden.</span><span class="sxs-lookup"><span data-stu-id="257be-501">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="257be-502">Wanneer de geadresseerde toegang probeert te krijgen tot het document, krijgen ze mogelijk toegang geweigerd als dit niet is toegestaan.</span><span class="sxs-lookup"><span data-stu-id="257be-502">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="257be-503">**Win32 Endpoint-apparaten**</span><span class="sxs-lookup"><span data-stu-id="257be-503">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="257be-504">Subset</span><span class="sxs-lookup"><span data-stu-id="257be-504">Subset</span></span>|<span data-ttu-id="257be-505">Alle endpoint DLP-predicaten en acties in DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="257be-505">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="257be-506">Zie [Preventie van gegevensverlies op Eindpunt ondersteunt beleidstips voor alleen bepaalde typen gevoelige informatie](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="257be-506">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="257be-507">**Mac-apparaten**</span><span class="sxs-lookup"><span data-stu-id="257be-507">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="257be-508">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-508">None</span></span>|<span data-ttu-id="257be-509">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-509">None</span></span>|<span data-ttu-id="257be-510">Preventie van gegevensverlies kan vandaag niet worden afgedwongen op Mac-apparaten</span><span class="sxs-lookup"><span data-stu-id="257be-510">Data loss prevention are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="257be-511">**Cloud-apps van derden**</span><span class="sxs-lookup"><span data-stu-id="257be-511">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="257be-512">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-512">None</span></span>|<span data-ttu-id="257be-513">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-513">None</span></span>|<span data-ttu-id="257be-514">Preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="257be-514">Data Loss Prevention</span></span>|
|<span data-ttu-id="257be-515">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="257be-515">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="257be-516">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-516">None</span></span>|<span data-ttu-id="257be-517">Geen</span><span class="sxs-lookup"><span data-stu-id="257be-517">None</span></span>||
|<span data-ttu-id="257be-518">**Word, Excel, Powerpoint Win32-client**</span><span class="sxs-lookup"><span data-stu-id="257be-518">**Word, Excel, Powerpoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="257be-519">Subset</span><span class="sxs-lookup"><span data-stu-id="257be-519">Subset</span></span>|<span data-ttu-id="257be-520">Subset</span><span class="sxs-lookup"><span data-stu-id="257be-520">Subset</span></span>|<span data-ttu-id="257be-521">Beleidstips voor WXP-client-apps werken voor documenten die zijn opgeslagen op Sharepoint Online of One Drive for Business Sites voor alle DLP-beleidsregels die precies de onderstaande of een subset met voorwaarden of acties in het DLP-beleid bevatten:</span><span class="sxs-lookup"><span data-stu-id="257be-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="257be-522">Inhoud bevat gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="257be-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="257be-523">Access-bereik (Inhoud wordt intern/extern gedeeld)</span><span class="sxs-lookup"><span data-stu-id="257be-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="257be-524">Gebruiker op de hoogte stellen (beleidstips/gebruikersmeldingen)</span><span class="sxs-lookup"><span data-stu-id="257be-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="257be-525">Iedereen blokkeren</span><span class="sxs-lookup"><span data-stu-id="257be-525">Block everyone</span></span></li><li><span data-ttu-id="257be-526">Incidentenrapporten</span><span class="sxs-lookup"><span data-stu-id="257be-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="257be-527">Als er een andere voorwaarde of actie aanwezig is, wordt de DLP-beleidstip voor dat beleid niet weergegeven in de bureaublad-apps van Word, Excel of PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="257be-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span>|
||||||