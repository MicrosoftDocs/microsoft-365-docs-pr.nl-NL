---
title: Niet-Microsoft 365 in een revisieset laden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het importeren van niet-Microsoft 365 gegevens in een revisieset voor analyse in Advanced eDiscovery geval.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161757"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="9985b-103">Niet-Microsoft 365 in een revisieset laden</span><span class="sxs-lookup"><span data-stu-id="9985b-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="9985b-104">Niet alle documenten die u moet analyseren in Advanced eDiscovery bevinden zich in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9985b-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="9985b-105">Met de functie Microsoft 365 gegevens importeren in Advanced eDiscovery, kunt u documenten die zich niet in Microsoft 365 bevinden, uploaden naar een revisieset.</span><span class="sxs-lookup"><span data-stu-id="9985b-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="9985b-106">In dit artikel wordt beschreven hoe u uw niet-Microsoft 365 documenten kunt Advanced eDiscovery voor analyse.</span><span class="sxs-lookup"><span data-stu-id="9985b-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="9985b-107">Vereisten voor het uploaden van niet-Office 365 inhoud</span><span class="sxs-lookup"><span data-stu-id="9985b-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="9985b-108">Voor het gebruik van de functie Microsoft 365 uploaden die in dit artikel wordt beschreven, moet u het volgende hebben:</span><span class="sxs-lookup"><span data-stu-id="9985b-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="9985b-109">Aan alle bewaarders die u niet-Microsoft 365 wilt koppelen, moet de juiste licentie worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="9985b-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="9985b-110">Zie Aan de slag [met Advanced eDiscovery.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)</span><span class="sxs-lookup"><span data-stu-id="9985b-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="9985b-111">Een bestaand Advanced eDiscovery geval.</span><span class="sxs-lookup"><span data-stu-id="9985b-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="9985b-112">Bewaarders moeten aan de zaak worden toegevoegd voordat u de niet-Microsoft 365 gegevens kunt uploaden en eraan kunt koppelen.</span><span class="sxs-lookup"><span data-stu-id="9985b-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="9985b-113">Niet-Microsoft 365 gegevens moeten een bestandstype zijn dat wordt ondersteund door Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9985b-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="9985b-114">Zie Ondersteunde [bestandstypen in Advanced eDiscovery.](supported-filetypes-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="9985b-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="9985b-115">Alle bestanden die naar een revisieset worden geüpload, moeten zich bevinden in mappen, waar elke map is gekoppeld aan een specifieke bewaarder.</span><span class="sxs-lookup"><span data-stu-id="9985b-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="9985b-116">De namen voor deze mappen moeten de volgende naamgevingsindeling gebruiken: *alias@domainname.*</span><span class="sxs-lookup"><span data-stu-id="9985b-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="9985b-117">De alias@domainname moet de alias en het domein van Microsoft 365 gebruiker zijn.</span><span class="sxs-lookup"><span data-stu-id="9985b-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="9985b-118">U kunt alle mappen alias@domainname in een hoofdmap verzamelen.</span><span class="sxs-lookup"><span data-stu-id="9985b-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="9985b-119">De hoofdmap kan alleen de alias@domainname bevatten.</span><span class="sxs-lookup"><span data-stu-id="9985b-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="9985b-120">Losse bestanden in de hoofdmap worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="9985b-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="9985b-121">De mapstructuur voor de niet-Microsoft 365 gegevens die u wilt uploaden, lijkt op het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9985b-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="9985b-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9985b-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="9985b-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9985b-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="9985b-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9985b-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="9985b-125">Waar abraham.mcmahon@contoso.com, jewell.gordon@contoso.com en staci.gonzalez@contoso.com de SMTP-adressen van bewaarders in de zaak zijn.</span><span class="sxs-lookup"><span data-stu-id="9985b-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Mapstructuur voor niet-Microsoft 365 gegevens uploaden](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="9985b-127">Een account dat is toegewezen aan de rollengroep eDiscovery Manager (en is toegevoegd als eDiscovery-beheerder).</span><span class="sxs-lookup"><span data-stu-id="9985b-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="9985b-128">Het hulpprogramma AzCopy v8.1 is geïnstalleerd op een computer die toegang heeft tot de niet-Microsoft 365 inhoudsmapstructuur.</span><span class="sxs-lookup"><span data-stu-id="9985b-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="9985b-129">Zie Gegevens overbrengen met de [AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)op Windows .</span><span class="sxs-lookup"><span data-stu-id="9985b-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="9985b-130">Installeer AzCopy op de standaardlocatie, **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.**</span><span class="sxs-lookup"><span data-stu-id="9985b-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="9985b-131">U moet AzCopy v8.1 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9985b-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="9985b-132">Andere versies van AzCopy werken mogelijk niet bij het laden van niet-Microsoft 365 gegevens in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9985b-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="9985b-133">Upload niet-Microsoft 365 inhoud in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9985b-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="9985b-134">Als eDiscovery Manager of eDiscovery-beheerder opent u Advanced eDiscovery en gaat u naar het geval dat de niet-Microsoft 365 gegevens worden geüpload naar.</span><span class="sxs-lookup"><span data-stu-id="9985b-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="9985b-135">Klik **op Revisiesets** en selecteer vervolgens de revisieset om de niet-Microsoft 365 te uploaden.</span><span class="sxs-lookup"><span data-stu-id="9985b-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="9985b-136">Als u geen revisieset hebt, kunt u er een maken.</span><span class="sxs-lookup"><span data-stu-id="9985b-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="9985b-137">Klik in de revisieset op **Controleset beheren** en klik vervolgens op **Uploads weergeven** op de **tegel Niet-Microsoft 365 gegevens.**</span><span class="sxs-lookup"><span data-stu-id="9985b-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="9985b-138">Klik **Upload om** de wizard Gegevens importeren te starten.</span><span class="sxs-lookup"><span data-stu-id="9985b-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Upload bestanden](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="9985b-140">De eerste stap in de wizard bereidt een beveiligde door Microsoft verstrekte Azure Storage voor om de bestanden te uploaden naar.</span><span class="sxs-lookup"><span data-stu-id="9985b-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="9985b-141">Wanneer de voorbereiding is voltooid, wordt de **knop Volgende: Upload bestanden** actief.</span><span class="sxs-lookup"><span data-stu-id="9985b-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Niet-Microsoft 365 importeren: Voorbereiden](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="9985b-143">Klik **op Volgende: Upload bestanden.**</span><span class="sxs-lookup"><span data-stu-id="9985b-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="9985b-144">Ga op **Upload pagina bestanden** als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="9985b-144">On the **Upload files** page, do the following:</span></span>

   ![Niet-Microsoft 365 importeren: Upload bestanden](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="9985b-146">a.</span><span class="sxs-lookup"><span data-stu-id="9985b-146">a.</span></span> <span data-ttu-id="9985b-147">Controleer  of typ in het vak Pad naar locatie van bestanden de locatie van de hoofdmap waar u de niet-Microsoft 365 gegevens hebt opgeslagen die u wilt uploaden.</span><span class="sxs-lookup"><span data-stu-id="9985b-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="9985b-148">Voor de locatie van de voorbeeldbestanden die worden weergegeven in de sectie Voordat u **begint,** typt u **bijvoorbeeld %USERPROFILE\Downloads\nonO365.**</span><span class="sxs-lookup"><span data-stu-id="9985b-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="9985b-149">Als u de juiste locatie geeft, zorgt u ervoor dat de opdracht AzCopy die in het vak onder het pad wordt weergegeven, correct wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="9985b-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="9985b-150">b.</span><span class="sxs-lookup"><span data-stu-id="9985b-150">b.</span></span> <span data-ttu-id="9985b-151">Klik **op Kopiëren naar klembord** om de opdracht te kopiëren die in het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9985b-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="9985b-152">Start een Windows opdrachtprompt, plak de opdracht die u hebt gekopieerd in de vorige stap en druk vervolgens op **Enter** om de opdracht AzCopy te starten.</span><span class="sxs-lookup"><span data-stu-id="9985b-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="9985b-153">Nadat u de opdracht hebt start, worden de niet-Microsoft 365 geüpload naar de Azure Storage locatie die is voorbereid in stap 4.</span><span class="sxs-lookup"><span data-stu-id="9985b-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Niet-Microsoft 365 importeren: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="9985b-155">Zoals eerder vermeld, moet u AzCopy v8.1 gebruiken om de opdracht te kunnen gebruiken die is opgegeven op de pagina Upload **bestanden.**</span><span class="sxs-lookup"><span data-stu-id="9985b-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="9985b-156">Als de opgegeven Opdracht AzCopy mislukt, raadpleegt u [AzCopy](troubleshooting-azcopy.md)oplossen in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9985b-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="9985b-157">Ga terug naar het beveiligings- & compliancecentrum en klik op **Volgende: Bestanden** verwerken in de wizard.</span><span class="sxs-lookup"><span data-stu-id="9985b-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="9985b-158">Hiermee start u de verwerking, tekstextractie en indexering van de niet-Microsoft 365 bestanden die zijn geüpload naar de Azure Storage locatie.</span><span class="sxs-lookup"><span data-stu-id="9985b-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="9985b-159">Volg de voortgang van het  verwerken van de  bestanden op de pagina Bestanden verwerken of op het tabblad Taken door een taak met de naam Niet-Microsoft 365 toevoegen aan **een revisieset weer te geven.**</span><span class="sxs-lookup"><span data-stu-id="9985b-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="9985b-160">Nadat de taak is voltooid, zijn de nieuwe bestanden beschikbaar in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="9985b-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Niet-Microsoft 365 importeren: Bestanden verwerken](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="9985b-162">Nadat de verwerking is voltooid, kunt u de wizard sluiten.</span><span class="sxs-lookup"><span data-stu-id="9985b-162">After the processing is finished, you can close the wizard.</span></span>