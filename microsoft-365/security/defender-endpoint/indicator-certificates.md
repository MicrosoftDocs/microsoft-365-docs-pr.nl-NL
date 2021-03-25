---
title: Indicatoren maken op basis van certificaten
ms.reviewer: ''
description: Indicatoren maken op basis van certificaten die de detectie, preventie en uitsluiting van entiteiten definiëren.
keywords: ioc, certificaat, certificaten, beheren, toegestaan, geblokkeerd, blokkeren, schoon, schadelijk, bestandshash, ip-adres, url's, domein
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164679"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="ab55f-104">Indicatoren maken op basis van certificaten</span><span class="sxs-lookup"><span data-stu-id="ab55f-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab55f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ab55f-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab55f-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="ab55f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab55f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab55f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="ab55f-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ab55f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab55f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ab55f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="ab55f-110">U kunt indicatoren voor certificaten maken.</span><span class="sxs-lookup"><span data-stu-id="ab55f-110">You can create indicators for certificates.</span></span> <span data-ttu-id="ab55f-111">Enkele veelgebruikte gevallen zijn:</span><span class="sxs-lookup"><span data-stu-id="ab55f-111">Some common use cases include:</span></span>

- <span data-ttu-id="ab55f-112">Scenario's wanneer u blokkeringstechnologieën moet implementeren, zoals regels voor het verlagen van het oppervlak van aanvallen en gecontroleerde maptoegang, maar het gedrag van ondertekende toepassingen moet toestaan door het certificaat toe te voegen aan de lijst toestaan. [](attack-surface-reduction.md) [](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="ab55f-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="ab55f-113">Het gebruik van een specifieke ondertekende toepassing in uw organisatie blokkeren.</span><span class="sxs-lookup"><span data-stu-id="ab55f-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="ab55f-114">Door een indicator te maken om het certificaat van de toepassing te blokkeren, voorkomt Windows Defender AV dat bestandsuitvoeringen worden uitgevoerd (blokkeren en herstellen) en de automatische controle en herstel zich hetzelfde gedragen.</span><span class="sxs-lookup"><span data-stu-id="ab55f-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="ab55f-115">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="ab55f-115">Before you begin</span></span>

<span data-ttu-id="ab55f-116">Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren voor certificaten maakt:</span><span class="sxs-lookup"><span data-stu-id="ab55f-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="ab55f-117">Deze functie is beschikbaar als uw organisatie Windows Defender Antivirus gebruikt en cloudbeveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ab55f-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="ab55f-118">Zie Beveiliging in de [cloud beheren voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="ab55f-118">For more information, see [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="ab55f-119">De versie van de Antimalware-client moet 4.18.1901.x of hoger zijn.</span><span class="sxs-lookup"><span data-stu-id="ab55f-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="ab55f-120">Ondersteund op computers op Windows 10, versie 1703 of hoger, Windows Server 2016 en 2019.</span><span class="sxs-lookup"><span data-stu-id="ab55f-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="ab55f-121">De definities voor virus- en bedreigingsbeveiliging moeten up-to-date zijn.</span><span class="sxs-lookup"><span data-stu-id="ab55f-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="ab55f-122">Deze functie ondersteunt momenteel het invoeren van . CER of . PEM-bestandsextensies.</span><span class="sxs-lookup"><span data-stu-id="ab55f-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="ab55f-123">Een geldig bladcertificaat is een handtekeningcertificaat dat een geldig certificeringspad heeft en moet zijn geketend aan de Hoofdcertificaatinstantie (CA) die door Microsoft wordt vertrouwd.</span><span class="sxs-lookup"><span data-stu-id="ab55f-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="ab55f-124">U kunt ook een aangepast (zelf ondertekend) certificaat gebruiken zolang het wordt vertrouwd door de client (Root CA-certificaat is geïnstalleerd onder de lokale computer 'Vertrouwde hoofdcertificeringsinstanties').</span><span class="sxs-lookup"><span data-stu-id="ab55f-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="ab55f-125">De kinderen of ouders van de IOC's voor het certificaat toestaan/blokkeren worden niet opgenomen in de IoC-functionaliteit toestaan/blokkeren, alleen bladcertificaten worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="ab55f-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="ab55f-126">Ondertekende microsoft-certificaten kunnen niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="ab55f-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="ab55f-127">Maak een indicator voor certificaten op de pagina Instellingen:</span><span class="sxs-lookup"><span data-stu-id="ab55f-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ab55f-128">Het kan maximaal 3 uur duren om een certificaat-IoC te maken en te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ab55f-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="ab55f-129">Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="ab55f-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="ab55f-130">Selecteer het **tabblad** Certificaat.</span><span class="sxs-lookup"><span data-stu-id="ab55f-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="ab55f-131">Selecteer **Indicator toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="ab55f-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="ab55f-132">Geef de volgende details op:</span><span class="sxs-lookup"><span data-stu-id="ab55f-132">Specify the following details:</span></span>
   - <span data-ttu-id="ab55f-133">Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.</span><span class="sxs-lookup"><span data-stu-id="ab55f-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="ab55f-134">Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="ab55f-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="ab55f-135">Bereik: definieer het bereik van de machinegroep.</span><span class="sxs-lookup"><span data-stu-id="ab55f-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="ab55f-136">Bekijk de details op het tabblad Overzicht en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="ab55f-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab55f-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ab55f-137">Related topics</span></span>
- [<span data-ttu-id="ab55f-138">Indicatoren maken</span><span class="sxs-lookup"><span data-stu-id="ab55f-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="ab55f-139">Indicatoren voor bestanden maken</span><span class="sxs-lookup"><span data-stu-id="ab55f-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="ab55f-140">Indicatoren maken voor IPs en URL's/domeinen</span><span class="sxs-lookup"><span data-stu-id="ab55f-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="ab55f-141">Indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="ab55f-141">Manage indicators</span></span>](indicator-manage.md)
