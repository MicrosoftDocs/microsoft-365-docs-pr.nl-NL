---
title: Hoe inhoud wordt geïdentificeerd voor aanbevelingen voor gegevensbeheer
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Het Microsoft 365-beveiligingscentrum en het Microsoft 365-compliancecentrum doen aanbevelingen voor gegevensbeheer op basis van de huidige instellingen van uw organisatie. U kunt met een paar klikken dingen instellen. Met sommige van deze aanbevelingen wordt specifieke inhoud in uw organisatie gedetecteerd en worden aanbevolen stappen gegeven voor het beheren van die inhoud. Zo kunnen met een aanbeveling items worden gedetecteerd die bedrijfskritische inhoud bevatten (zoals clientrechten of NDA-gegevens) en kunt u vervolgens automatisch een bewaarlabel op deze items toepassen om ervoor te zorgen dat deze worden geclassificeerd en bewaard als dat nodig is. In dit onderwerp worden aanbevelingen voor gegevensbeheer beschreven die u mogelijk ziet. Ook wordt beschreven welke inhoud wordt gedetecteerd om elk ervan te activeren.
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162085"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="e5c87-106">Hoe inhoud wordt geïdentificeerd voor aanbevelingen voor gegevensbeheer</span><span class="sxs-lookup"><span data-stu-id="e5c87-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="e5c87-107">Het Microsoft 365-beveiligingscentrum en het Microsoft 365-compliancecentrum doen aanbevelingen voor gegevensbeheer op basis van de huidige instellingen van uw organisatie. U kunt met een paar klikken dingen instellen.</span><span class="sxs-lookup"><span data-stu-id="e5c87-107">The Microsoft 365 security center and Microsoft 365 compliance center provide recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks.</span></span> <span data-ttu-id="e5c87-108">Met sommige van deze aanbevelingen wordt specifieke inhoud in uw organisatie gedetecteerd en worden aanbevolen stappen gegeven voor het beheren van die inhoud.</span><span class="sxs-lookup"><span data-stu-id="e5c87-108">Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content.</span></span> <span data-ttu-id="e5c87-109">Zo kunnen met een aanbeveling items worden gedetecteerd die bedrijfskritische inhoud bevatten (zoals clientrechten of NDA-gegevens) en kunt u vervolgens automatisch een bewaarlabel op deze items toepassen om ervoor te zorgen dat deze worden geclassificeerd en bewaard als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="e5c87-109">For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they're classified and retained as needed.</span></span>

<span data-ttu-id="e5c87-110">In dit onderwerp worden aanbevelingen voor gegevensbeheer beschreven die u mogelijk ziet. Ook wordt beschreven welke inhoud wordt gedetecteerd om elk ervan te activeren.</span><span class="sxs-lookup"><span data-stu-id="e5c87-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="e5c87-111">Voicemail opschonen</span><span class="sxs-lookup"><span data-stu-id="e5c87-111">Clean up voicemail</span></span>

<span data-ttu-id="e5c87-112">Deze aanbeveling wordt weergegeven wanneer e-mailberichten die zijn geïdentificeerd als het berichttype 'voicemail' in de postvakken van gebruikers worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="e5c87-112">This recommendation appears when email messages identified as the message type 'voicemail' are detected in users' mailboxes.</span></span> <span data-ttu-id="e5c87-113">Meer informatie over [berichteigenschappen in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="e5c87-113">Learn more about [message properties in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="e5c87-114">Labelen van inhoud met advocaat/cliënt-bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="e5c87-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="e5c87-115">Deze aanbeveling wordt weergegeven wanneer aan een van de volgende criteria wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="e5c87-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="e5c87-116">Er wordt een combinatie van de volgende trefwoorden aangetroffen in de tekst van een e-mailbericht:</span><span class="sxs-lookup"><span data-stu-id="e5c87-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="e5c87-117">ACP</span><span class="sxs-lookup"><span data-stu-id="e5c87-117">ACP</span></span>
    - <span data-ttu-id="e5c87-118">Advocaat/cliënt-bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="e5c87-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="e5c87-119">Advocaat-cliëntbevoegdheid</span><span class="sxs-lookup"><span data-stu-id="e5c87-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="e5c87-120">Advocaat-cliëntbevoegdheid</span><span class="sxs-lookup"><span data-stu-id="e5c87-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="e5c87-121">Er wordt een combinatie van de volgende trefwoorden aangetroffen in SharePoint- of OneDrive-bestanden:</span><span class="sxs-lookup"><span data-stu-id="e5c87-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="e5c87-122">ACP</span><span class="sxs-lookup"><span data-stu-id="e5c87-122">ACP</span></span>
    - <span data-ttu-id="e5c87-123">Advocaat-cliëntbevoegdheid\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="e5c87-124">AC-bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="e5c87-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="e5c87-125">Audiobestanden behouden</span><span class="sxs-lookup"><span data-stu-id="e5c87-125">Retain audio files</span></span>

<span data-ttu-id="e5c87-126">Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e5c87-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="e5c87-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="e5c87-127">.MP3</span></span>
- <span data-ttu-id="e5c87-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="e5c87-128">.WMA</span></span>
- <span data-ttu-id="e5c87-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="e5c87-129">.WAV</span></span>
- <span data-ttu-id="e5c87-130">.RA</span><span class="sxs-lookup"><span data-stu-id="e5c87-130">.RA</span></span>
- <span data-ttu-id="e5c87-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="e5c87-131">.RAM</span></span>
- <span data-ttu-id="e5c87-132">.RM</span><span class="sxs-lookup"><span data-stu-id="e5c87-132">.RM</span></span>
- <span data-ttu-id="e5c87-133">.MID</span><span class="sxs-lookup"><span data-stu-id="e5c87-133">.MID</span></span>
- <span data-ttu-id="e5c87-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="e5c87-134">.OGG</span></span>
- <span data-ttu-id="e5c87-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="e5c87-135">.AIFF</span></span>
- <span data-ttu-id="e5c87-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="e5c87-136">.PCM</span></span>
- <span data-ttu-id="e5c87-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="e5c87-137">.AAC</span></span>
- <span data-ttu-id="e5c87-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="e5c87-138">.FLAC</span></span>
- <span data-ttu-id="e5c87-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="e5c87-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="e5c87-140">CAD-bestanden behouden</span><span class="sxs-lookup"><span data-stu-id="e5c87-140">Retain CAD files</span></span>

<span data-ttu-id="e5c87-141">Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e5c87-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="e5c87-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="e5c87-142">.3DXML</span></span>
- <span data-ttu-id="e5c87-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="e5c87-143">.ACIS</span></span>
- <span data-ttu-id="e5c87-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="e5c87-144">.ARC</span></span>
- <span data-ttu-id="e5c87-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="e5c87-145">.ASM</span></span>
- <span data-ttu-id="e5c87-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-146">.CAT\*</span></span>
- <span data-ttu-id="e5c87-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="e5c87-147">.CGR</span></span>
- <span data-ttu-id="e5c87-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-148">.DW\*</span></span>
- <span data-ttu-id="e5c87-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-149">.DX\*</span></span>
- <span data-ttu-id="e5c87-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="e5c87-150">.EDRW</span></span>
- <span data-ttu-id="e5c87-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="e5c87-151">.IAM</span></span>
- <span data-ttu-id="e5c87-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="e5c87-152">.IGES</span></span>
- <span data-ttu-id="e5c87-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="e5c87-153">.IGS</span></span>
- <span data-ttu-id="e5c87-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="e5c87-154">.IPT</span></span>
- <span data-ttu-id="e5c87-155">.JT</span><span class="sxs-lookup"><span data-stu-id="e5c87-155">.JT</span></span>
- <span data-ttu-id="e5c87-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="e5c87-156">.MF1</span></span>
- <span data-ttu-id="e5c87-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="e5c87-157">.NEU</span></span>
- <span data-ttu-id="e5c87-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="e5c87-158">.PAR</span></span>
- <span data-ttu-id="e5c87-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="e5c87-159">.PKG</span></span>
- <span data-ttu-id="e5c87-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="e5c87-160">.PRC</span></span>
- <span data-ttu-id="e5c87-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="e5c87-161">.PRT</span></span>
- <span data-ttu-id="e5c87-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="e5c87-162">.PSM</span></span>
- <span data-ttu-id="e5c87-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="e5c87-163">.PWD</span></span>
- <span data-ttu-id="e5c87-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-164">.SLD\*</span></span>
- <span data-ttu-id="e5c87-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="e5c87-165">.STEP</span></span>
- <span data-ttu-id="e5c87-166">.STL</span><span class="sxs-lookup"><span data-stu-id="e5c87-166">.STL</span></span>
- <span data-ttu-id="e5c87-167">.STP</span><span class="sxs-lookup"><span data-stu-id="e5c87-167">.STP</span></span>
- <span data-ttu-id="e5c87-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="e5c87-168">.U3D</span></span>
- <span data-ttu-id="e5c87-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="e5c87-169">.UNV</span></span>
- <span data-ttu-id="e5c87-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="e5c87-170">.VRML</span></span>
- <span data-ttu-id="e5c87-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="e5c87-171">.WRL</span></span>
- <span data-ttu-id="e5c87-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-172">.X_\*</span></span>
- <span data-ttu-id="e5c87-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="e5c87-173">.XAS</span></span>
- <span data-ttu-id="e5c87-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-174">.XMT\*</span></span>
- <span data-ttu-id="e5c87-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="e5c87-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="e5c87-176">Afbeeldingsbestanden behouden</span><span class="sxs-lookup"><span data-stu-id="e5c87-176">Retain image files</span></span>

<span data-ttu-id="e5c87-177">Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e5c87-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="e5c87-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="e5c87-178">.JPEG</span></span>
- <span data-ttu-id="e5c87-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="e5c87-179">.GIF</span></span>
- <span data-ttu-id="e5c87-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-180">.TIF\*</span></span>
- <span data-ttu-id="e5c87-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="e5c87-181">.BMP</span></span>
- <span data-ttu-id="e5c87-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="e5c87-182">.PNG</span></span>
- <span data-ttu-id="e5c87-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="e5c87-183">.RAW</span></span>
- <span data-ttu-id="e5c87-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="e5c87-184">.PSD</span></span>
- <span data-ttu-id="e5c87-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="e5c87-185">.PSP</span></span>
- <span data-ttu-id="e5c87-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="e5c87-186">.JPG</span></span>
- <span data-ttu-id="e5c87-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="e5c87-187">.EXIF</span></span>
- <span data-ttu-id="e5c87-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="e5c87-188">.PPM</span></span>
- <span data-ttu-id="e5c87-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="e5c87-189">.PGM</span></span>
- <span data-ttu-id="e5c87-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="e5c87-190">.PBM</span></span>
- <span data-ttu-id="e5c87-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="e5c87-191">.PNM</span></span>
- <span data-ttu-id="e5c87-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="e5c87-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="e5c87-193">NDA-inhoud behouden</span><span class="sxs-lookup"><span data-stu-id="e5c87-193">Retain NDA content</span></span> 

<span data-ttu-id="e5c87-194">Deze aanbeveling wordt weergegeven wanneer aan een van de volgende criteria wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="e5c87-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="e5c87-195">Er wordt een combinatie van de volgende trefwoorden aangetroffen in de tekst van een e-mailbericht:</span><span class="sxs-lookup"><span data-stu-id="e5c87-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="e5c87-196">NDA</span><span class="sxs-lookup"><span data-stu-id="e5c87-196">NDA</span></span>
    - <span data-ttu-id="e5c87-197">'Geheimhoudingsovereenkomst'</span><span class="sxs-lookup"><span data-stu-id="e5c87-197">"Non-Disclosure Agreement"</span></span>
    - <span data-ttu-id="e5c87-198">'Geheimhoudingsovereenkomst'</span><span class="sxs-lookup"><span data-stu-id="e5c87-198">"Non Disclosure Agreement"</span></span>

- <span data-ttu-id="e5c87-199">Er wordt een combinatie van de volgende trefwoorden aangetroffen in .PDF- of .DOC-bestanden in SharePoint of OneDrive:</span><span class="sxs-lookup"><span data-stu-id="e5c87-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="e5c87-200">NDA</span><span class="sxs-lookup"><span data-stu-id="e5c87-200">NDA</span></span>
    - <span data-ttu-id="e5c87-201">Geheimhoudingsovereenkomst</span><span class="sxs-lookup"><span data-stu-id="e5c87-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="e5c87-202">Bestanden voor softwareontwikkeling behouden</span><span class="sxs-lookup"><span data-stu-id="e5c87-202">Retain software development files</span></span>

<span data-ttu-id="e5c87-203">Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e5c87-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="e5c87-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="e5c87-204">.ASAX</span></span>
- <span data-ttu-id="e5c87-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="e5c87-205">.ASM</span></span>
- <span data-ttu-id="e5c87-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-206">.ASP\*</span></span>
- <span data-ttu-id="e5c87-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="e5c87-207">.BAT</span></span>
- <span data-ttu-id="e5c87-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="e5c87-208">.CONFIG</span></span>
- <span data-ttu-id="e5c87-209">.CS</span><span class="sxs-lookup"><span data-stu-id="e5c87-209">.CS</span></span>
- <span data-ttu-id="e5c87-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="e5c87-210">.CSS</span></span>
- <span data-ttu-id="e5c87-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="e5c87-211">.DISCO</span></span>
- <span data-ttu-id="e5c87-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-212">.HTM\*</span></span>
- <span data-ttu-id="e5c87-213">.INC</span><span class="sxs-lookup"><span data-stu-id="e5c87-213">.INC</span></span>
- <span data-ttu-id="e5c87-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="e5c87-214">.JAD</span></span>
- <span data-ttu-id="e5c87-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="e5c87-215">.JAVA</span></span>
- <span data-ttu-id="e5c87-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-216">.JS\*</span></span>
- <span data-ttu-id="e5c87-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="e5c87-217">.LIB</span></span>
- <span data-ttu-id="e5c87-218">.O</span><span class="sxs-lookup"><span data-stu-id="e5c87-218">.O</span></span>
- <span data-ttu-id="e5c87-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="e5c87-219">.PHP</span></span>
- <span data-ttu-id="e5c87-220">.RC</span><span class="sxs-lookup"><span data-stu-id="e5c87-220">.RC</span></span>
- <span data-ttu-id="e5c87-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="e5c87-221">.RESX</span></span>
- <span data-ttu-id="e5c87-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="e5c87-222">.RPT</span></span>
- <span data-ttu-id="e5c87-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="e5c87-223">.RSS</span></span>
- <span data-ttu-id="e5c87-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="e5c87-224">.SCPT</span></span>
- <span data-ttu-id="e5c87-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="e5c87-225">.SRC</span></span>
- <span data-ttu-id="e5c87-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-226">.VB\*</span></span>
- <span data-ttu-id="e5c87-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="e5c87-227">.WSF</span></span>
- <span data-ttu-id="e5c87-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="e5c87-228">.XCODEPROJ</span></span>
- <span data-ttu-id="e5c87-229">.XML</span><span class="sxs-lookup"><span data-stu-id="e5c87-229">.XML</span></span>
- <span data-ttu-id="e5c87-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="e5c87-230">.XSD</span></span>
- <span data-ttu-id="e5c87-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="e5c87-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="e5c87-232">Videobestanden behouden</span><span class="sxs-lookup"><span data-stu-id="e5c87-232">Retain video files</span></span>

<span data-ttu-id="e5c87-233">Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e5c87-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="e5c87-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="e5c87-234">.AVCHD</span></span>
- <span data-ttu-id="e5c87-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="e5c87-235">.AVI</span></span>
- <span data-ttu-id="e5c87-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="e5c87-236">.FLV</span></span>
- <span data-ttu-id="e5c87-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="e5c87-237">.MOV</span></span>
- <span data-ttu-id="e5c87-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="e5c87-238">.MP2V</span></span>
- <span data-ttu-id="e5c87-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="e5c87-239">.MP4</span></span>
- <span data-ttu-id="e5c87-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="e5c87-240">.MP4V</span></span>
- <span data-ttu-id="e5c87-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="e5c87-241">.MPE</span></span>
- <span data-ttu-id="e5c87-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="e5c87-242">.MPEG</span></span>
- <span data-ttu-id="e5c87-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="e5c87-243">.MPEG1</span></span>
- <span data-ttu-id="e5c87-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="e5c87-244">.MPEG2</span></span>
- <span data-ttu-id="e5c87-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="e5c87-245">.MPEG4</span></span>
- <span data-ttu-id="e5c87-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="e5c87-246">.MPG</span></span>
- <span data-ttu-id="e5c87-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="e5c87-247">.MPG2</span></span>
- <span data-ttu-id="e5c87-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="e5c87-248">.MPG4</span></span>
- <span data-ttu-id="e5c87-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="e5c87-249">.WMV</span></span>
- <span data-ttu-id="e5c87-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="e5c87-250">.XMV</span></span>