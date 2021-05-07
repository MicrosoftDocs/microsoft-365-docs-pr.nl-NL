---
title: Problemen met AzCopy oplossen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Problemen met Azure AzCopy oplossen bij het laden van niet-Office 365 gegevens voor foutsanering in Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161958"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="17802-103">Problemen met AzCopy oplossen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="17802-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="17802-104">Wanneer u niet-Microsoft 365-gegevens of documenten laadt voor foutsanering in Advanced eDiscovery, levert de gebruikersinterface een Azure AzCopy-opdracht die parameters bevat met de locatie waar de bestanden die u wilt uploaden zijn opgeslagen en de Azure-opslaglocatie waar de bestanden naar worden geüpload.</span><span class="sxs-lookup"><span data-stu-id="17802-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="17802-105">Als u uw documenten wilt uploaden, kopieert u deze opdracht en voer u deze uit in een opdrachtprompt op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="17802-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="17802-106">In de volgende schermafbeelding ziet u een voorbeeld van een AzCopy-opdracht:</span><span class="sxs-lookup"><span data-stu-id="17802-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Upload niet-Microsoft 365 bestanden](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="17802-108">Meestal werkt de opdracht die wordt geleverd wanneer u deze uitwerkt.</span><span class="sxs-lookup"><span data-stu-id="17802-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="17802-109">Er kunnen echter gevallen zijn waarin de weergegeven opdracht niet wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="17802-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="17802-110">Hier zijn een paar mogelijke redenen.</span><span class="sxs-lookup"><span data-stu-id="17802-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="17802-111">De ondersteunde versie van AzCopy is niet geïnstalleerd op de lokale computer</span><span class="sxs-lookup"><span data-stu-id="17802-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="17802-112">Op dit moment moet u AzCopy v8.1 gebruiken om niet-Microsoft 365 gegevens in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="17802-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="17802-113">De opdracht AzCopy die wordt weergegeven op de **pagina Upload** bestanden die in de vorige schermafbeelding wordt weergegeven, geeft een fout als u AzCopy v8.1 niet gebruikt.</span><span class="sxs-lookup"><span data-stu-id="17802-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="17802-114">Zie Gegevens overbrengen met [de AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)op Windows .</span><span class="sxs-lookup"><span data-stu-id="17802-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="17802-115">AzCopy is niet geïnstalleerd op de lokale computer of niet op de standaardlocatie</span><span class="sxs-lookup"><span data-stu-id="17802-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="17802-116">Als AzCopy niet is geïnstalleerd of is geïnstalleerd op een andere locatie dan de standaardlocatie voor installeren (dat wil zeggen), wordt mogelijk de volgende fout weergegeven wanneer u de `%ProgramFiles(x86)%` opdracht AzCopy uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="17802-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="17802-117">Het systeem kan het opgegeven pad niet vinden.</span><span class="sxs-lookup"><span data-stu-id="17802-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="17802-118">Als AzCopy niet is geïnstalleerd op de lokale computer, vindt u installatiegegevens in Gegevens overbrengen met [de AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)op Windows.</span><span class="sxs-lookup"><span data-stu-id="17802-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="17802-119">Installeer deze op de standaardlocatie.</span><span class="sxs-lookup"><span data-stu-id="17802-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="17802-120">Als AzCopy is geïnstalleerd, maar deze is geïnstalleerd op een andere locatie dan de standaardlocatie, kunt u de opdracht kopiëren, plakken in een tekstbestand en vervolgens het pad wijzigen naar de locatie waar AzCopy is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="17802-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="17802-121">Als Azcopy zich bijvoorbeeld in bevindt, kunt u het eerste deel van de `%ProgramFiles%` opdracht wijzigen in `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="17802-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="17802-122">Nadat u deze wijziging hebt gemaakt, kopieert u deze uit het tekstbestand en voer u de opdrachtprompt uit.</span><span class="sxs-lookup"><span data-stu-id="17802-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="17802-123">Als AzCopy is geïnstalleerd op een andere locatie dan de standaardinstallatielocatie, kunt u overwegen deze te verwijderen en vervolgens opnieuw te installeren op de standaardlocatie.</span><span class="sxs-lookup"><span data-stu-id="17802-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="17802-124">Dit helpt dit probleem in de toekomst te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="17802-124">This will help prevent this issue in the future.</span></span>