---
title: Automatiseringsbestandsuploads beheren
description: Inhoudsanalyse inschakelen en de bestandsextensies en e-mailbijlageextensies configureren die voor analyse worden ingediend
keywords: automatisering, bestand, uploads, inhoud, analyse, bestand, extensie, e-mail, bijlage
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185847"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="989fa-104">Automatiseringsbestandsuploads beheren</span><span class="sxs-lookup"><span data-stu-id="989fa-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="989fa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="989fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="989fa-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="989fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="989fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="989fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="989fa-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="989fa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="989fa-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="989fa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="989fa-110">Schakel de mogelijkheid voor inhoudsanalyse in, zodat bepaalde bestanden en e-mailbijlagen automatisch naar de cloud kunnen worden geüpload voor aanvullende controle in Geautomatiseerd onderzoek.</span><span class="sxs-lookup"><span data-stu-id="989fa-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="989fa-111">Identificeer de bestanden en e-mailbijlagen door de namen van de bestandsextensie en de extensienamen voor e-mailbijlagen op te geven.</span><span class="sxs-lookup"><span data-stu-id="989fa-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="989fa-112">Als u bijvoorbeeld *exe* en *bat* toevoegt als bestands- of bijlageextensienamen, worden alle bestanden of bijlagen met deze extensies automatisch naar de cloud verzonden voor aanvullende controle tijdens geautomatiseerd onderzoek.</span><span class="sxs-lookup"><span data-stu-id="989fa-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="989fa-113">Bestandsextensienamen en naam van bijlageextensie toevoegen.</span><span class="sxs-lookup"><span data-stu-id="989fa-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="989fa-114">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Automatiseringsbestand uploadt.**</span><span class="sxs-lookup"><span data-stu-id="989fa-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="989fa-115">Schakel de instelling voor inhoudsanalyse in **tussen Aan** en **Uit.**</span><span class="sxs-lookup"><span data-stu-id="989fa-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="989fa-116">Configureer de volgende extensienamen en scheid extensienamen met een komma:</span><span class="sxs-lookup"><span data-stu-id="989fa-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="989fa-117">**Bestandsextensienamen:** verdachte bestanden, behalve e-mailbijlagen, worden ter aanvullende controle ingediend</span><span class="sxs-lookup"><span data-stu-id="989fa-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="989fa-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="989fa-118">Related topics</span></span>
- [<span data-ttu-id="989fa-119">Uitsluitingen van automatiseringsmappen beheren</span><span class="sxs-lookup"><span data-stu-id="989fa-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
