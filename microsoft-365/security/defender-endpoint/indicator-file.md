---
title: Indicatoren voor bestanden maken
ms.reviewer: ''
description: Maak indicatoren voor een bestandshash die de detectie, preventie en uitsluiting van entiteiten definieert.
keywords: bestand, hash, beheren, toegestaan, geblokkeerd, blokkeren, schoon, schadelijk, bestandshash, ip-adres, url's, domein
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
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060118"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="b961d-104">Indicatoren voor bestanden maken</span><span class="sxs-lookup"><span data-stu-id="b961d-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b961d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b961d-105">**Applies to:**</span></span>
- [<span data-ttu-id="b961d-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b961d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b961d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b961d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="b961d-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b961d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b961d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b961d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="b961d-110">U kunt verdere verspreiding van een aanval in uw organisatie voorkomen door potentieel schadelijke bestanden of vermoedelijke malware te verbieden.</span><span class="sxs-lookup"><span data-stu-id="b961d-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="b961d-111">Als u een potentieel schadelijk bestand voor draagbaar uitvoerbaar (PE) kent, kunt u dit blokkeren.</span><span class="sxs-lookup"><span data-stu-id="b961d-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="b961d-112">Deze bewerking voorkomt dat deze wordt gelezen, geschreven of uitgevoerd op machines in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b961d-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="b961d-113">U kunt op twee manieren indicatoren voor bestanden maken:</span><span class="sxs-lookup"><span data-stu-id="b961d-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="b961d-114">Door een indicator te maken via de pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="b961d-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="b961d-115">Door een contextuele indicator te maken met behulp van de knop Indicator toevoegen op de pagina met bestandsgegevens</span><span class="sxs-lookup"><span data-stu-id="b961d-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="b961d-116">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b961d-116">Before you begin</span></span>
<span data-ttu-id="b961d-117">Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren voor bestanden maakt:</span><span class="sxs-lookup"><span data-stu-id="b961d-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="b961d-118">Deze functie is beschikbaar als uw organisatie Windows Defender Antivirus gebruikt en cloudbeveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b961d-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="b961d-119">Zie Technologieën van de volgende generatie gebruiken in Microsoft Defender Antivirus via beveiliging in de cloud voor [meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="b961d-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="b961d-120">De versie van de Antimalware-client moet 4.18.1901.x of hoger zijn.</span><span class="sxs-lookup"><span data-stu-id="b961d-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="b961d-121">Ondersteund op computers op Windows 10, versie 1703 of hoger, Windows Server 2016 en 2019.</span><span class="sxs-lookup"><span data-stu-id="b961d-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="b961d-122">Als u bestanden wilt blokkeren, moet u eerst de functie Blokkeren of toestaan [in-/uitschakelen  ](advanced-features.md) in Instellingen.</span><span class="sxs-lookup"><span data-stu-id="b961d-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="b961d-123">Deze functie is ontworpen om te voorkomen dat verdachte malware (of mogelijk schadelijke bestanden) van internet wordt gedownload.</span><span class="sxs-lookup"><span data-stu-id="b961d-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="b961d-124">Het ondersteunt momenteel draagbare uitvoerbare (PE)-bestanden, waaronder _.exe-_ en _.dll-bestanden._</span><span class="sxs-lookup"><span data-stu-id="b961d-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="b961d-125">De dekking wordt in de tijd uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="b961d-125">The coverage will be extended over time.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="b961d-126">De functie Toestaan of blokkeren kan niet worden uitgevoerd op bestanden als de classificatie van het bestand aanwezig is in de cache van het apparaat vóór de actie toestaan of blokkeren</span><span class="sxs-lookup"><span data-stu-id="b961d-126">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
>- <span data-ttu-id="b961d-127">Vertrouwde ondertekende bestanden worden anders behandeld.</span><span class="sxs-lookup"><span data-stu-id="b961d-127">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="b961d-128">Defender voor Eindpunt is geoptimaliseerd voor het verwerken van schadelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="b961d-128">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="b961d-129">Het blokkeren van vertrouwde ondertekende bestanden kan in sommige gevallen gevolgen hebben voor de prestaties.</span><span class="sxs-lookup"><span data-stu-id="b961d-129">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>

 
>[!NOTE]
><span data-ttu-id="b961d-130">Bestandsblokken worden meestal binnen een paar minuten afgedwongen, maar kunnen meer dan 30 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="b961d-130">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="b961d-131">Een indicator voor bestanden maken op de pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="b961d-131">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="b961d-132">Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="b961d-132">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="b961d-133">Selecteer het **tabblad Bestandshash.**</span><span class="sxs-lookup"><span data-stu-id="b961d-133">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="b961d-134">Selecteer **Indicator toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="b961d-134">Select **Add indicator**.</span></span>

4. <span data-ttu-id="b961d-135">Geef de volgende details op:</span><span class="sxs-lookup"><span data-stu-id="b961d-135">Specify the following details:</span></span>
   - <span data-ttu-id="b961d-136">Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.</span><span class="sxs-lookup"><span data-stu-id="b961d-136">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="b961d-137">Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="b961d-137">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="b961d-138">Bereik: definieer het bereik van de machinegroep.</span><span class="sxs-lookup"><span data-stu-id="b961d-138">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="b961d-139">Bekijk de details op het tabblad Overzicht en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="b961d-139">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="b961d-140">Een contextuele indicator maken op de pagina met bestandsgegevens</span><span class="sxs-lookup"><span data-stu-id="b961d-140">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="b961d-141">Een van de opties bij het [uitvoeren van antwoordacties in een bestand](respond-file-alerts.md) is het toevoegen van een indicator voor het bestand.</span><span class="sxs-lookup"><span data-stu-id="b961d-141">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="b961d-142">Wanneer u een indicatorhash voor een bestand toevoegt, kunt u ervoor kiezen om een waarschuwing te verhogen en het bestand te blokkeren wanneer een computer in uw organisatie dit probeert uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="b961d-142">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="b961d-143">Bestanden die automatisch worden geblokkeerd door een indicator, worden niet weergegeven in het actiecentrum van het bestand, maar de waarschuwingen blijven wel zichtbaar in de wachtrij Waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="b961d-143">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b961d-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b961d-144">Related topics</span></span>
- [<span data-ttu-id="b961d-145">Indicatoren maken</span><span class="sxs-lookup"><span data-stu-id="b961d-145">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="b961d-146">Indicatoren maken voor IPs en URL's/domeinen</span><span class="sxs-lookup"><span data-stu-id="b961d-146">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="b961d-147">Indicatoren maken op basis van certificaten</span><span class="sxs-lookup"><span data-stu-id="b961d-147">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="b961d-148">Indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="b961d-148">Manage indicators</span></span>](indicator-manage.md)
