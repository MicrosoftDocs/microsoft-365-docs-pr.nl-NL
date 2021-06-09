---
title: Preventie van gegevensverlies voor eindpunten gebruiken
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Informatie over het configureren van beleid voor preventie van gegevensverlies (DLP) om locaties voor Microsoft 365 Eindpunt-DLP (EPDLP) te gebruiken.
ms.openlocfilehash: 1a0297271c3e0e8fb94a476982f146aa8c221e7a
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809129"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="738f7-103">Preventie van gegevensverlies van eindpunten gebruiken</span><span class="sxs-lookup"><span data-stu-id="738f7-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="738f7-104">In dit artikel worden drie scenario's beschreven waarin u een DLP-beleid maakt en wijzigt waarin apparaten als locatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="738f7-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="738f7-105">DLP-instellingen</span><span class="sxs-lookup"><span data-stu-id="738f7-105">DLP settings</span></span>

<span data-ttu-id="738f7-106">Voordat u begint, moet u de DLP-instellingen instellen die worden toegepast op alle DLP-beleidsregels voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="738f7-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="738f7-107">U moet deze configureren als u beleid wilt maken dat het volgende afdwingt:</span><span class="sxs-lookup"><span data-stu-id="738f7-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="738f7-108">cloud-uitgangsbeperkingen</span><span class="sxs-lookup"><span data-stu-id="738f7-108">cloud egress restrictions</span></span>
- <span data-ttu-id="738f7-109">Beperkingen voor niet-verschuldigde apps</span><span class="sxs-lookup"><span data-stu-id="738f7-109">unallowed apps restrictions</span></span>

<span data-ttu-id="738f7-110">Of</span><span class="sxs-lookup"><span data-stu-id="738f7-110">Or</span></span>

- <span data-ttu-id="738f7-111">Als u bestandspaden met veel ruis wilt uitsluiten van de controle</span><span class="sxs-lookup"><span data-stu-id="738f7-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="738f7-112">![DLP-instellingen](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="738f7-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="738f7-113">Bestandspaduitsluitingen</span><span class="sxs-lookup"><span data-stu-id="738f7-113">File path exclusions</span></span>

<span data-ttu-id="738f7-114">Mogelijk wilt u bepaalde paden uitsluiten van DLP-controle, DLP-waarschuwingen en DLP-beleid afdwingen op uw apparaten, omdat deze te veel worden gebruikt of geen bestanden bevatten waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="738f7-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="738f7-115">Bestanden op deze locaties worden niet gecontroleerd en bestanden die op deze locaties zijn gemaakt of gewijzigd, kunnen niet worden afdwingen met DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="738f7-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="738f7-116">U kunt uitsluitingen voor pad in DLP-instellingen configureren.</span><span class="sxs-lookup"><span data-stu-id="738f7-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="738f7-117">U kunt deze logica gebruiken om uw uitsluitingspaden te maken:</span><span class="sxs-lookup"><span data-stu-id="738f7-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="738f7-118">Geldig bestandspad dat eindigt op '\', wat betekent enkel bestanden die direct onder die map vallen.</span><span class="sxs-lookup"><span data-stu-id="738f7-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="738f7-119">Bijvoorbeeld C:\Temp</span><span class="sxs-lookup"><span data-stu-id="738f7-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="738f7-120">Geldig bestandspad dat eindigt op '\*', wat betekent enkel bestanden onder submappen, alsook bestanden die direct onder die map vallen.</span><span class="sxs-lookup"><span data-stu-id="738f7-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="738f7-121">Bijvoorbeeld C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="738f7-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="738f7-122">Geldig bestandspad dat niet eindigt op '\'of '\*', wat betekent enkel bestanden die direct onder die map en alle submappen vallen.</span><span class="sxs-lookup"><span data-stu-id="738f7-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="738f7-123">Bijvoorbeeld C:\Temp</span><span class="sxs-lookup"><span data-stu-id="738f7-123">For example: C:\Temp</span></span>

- <span data-ttu-id="738f7-124">Een pad met een jokerteken tussen '\' aan beide kanten.</span><span class="sxs-lookup"><span data-stu-id="738f7-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="738f7-125">Bijvoorbeeld: C:\Gebruikers\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="738f7-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="738f7-126">Een pad met een jokerteken tussen '\' aan beide kanten en met '(getal)' om het exacte aantal submappen op te geven.</span><span class="sxs-lookup"><span data-stu-id="738f7-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="738f7-127">Bijvoorbeeld: C:\Gebruikers\*(1)\Downloads</span><span class="sxs-lookup"><span data-stu-id="738f7-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="738f7-128">Een pad met omgevingsvariabelen voor SYSTEEM.</span><span class="sxs-lookup"><span data-stu-id="738f7-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="738f7-129">Bijvoorbeeld: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="738f7-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="738f7-130">Een combinatie van alle bovenstaande.</span><span class="sxs-lookup"><span data-stu-id="738f7-130">A mix of all the above.</span></span> <br/><span data-ttu-id="738f7-131">Bijvoorbeeld: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="738f7-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="738f7-132">Niet-toegestane apps</span><span class="sxs-lookup"><span data-stu-id="738f7-132">Unallowed apps</span></span>

<span data-ttu-id="738f7-133">Wanneer de beleidsinstelling **Toegang door niet-toegestane apps en browsers** is ingeschakeld en gebruikers proberen deze apps te gebruiken om toegang te krijgen tot een beveiligd bestand, wordt de activiteit toegestaan, geblokkeerd of geblokkeerd, maar kunnen gebruikers de beperking opheffen.</span><span class="sxs-lookup"><span data-stu-id="738f7-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="738f7-134">Alle activiteiten worden gecontroleerd en kunnen worden bekeken in activiteitenverkenner.</span><span class="sxs-lookup"><span data-stu-id="738f7-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="738f7-135">Neem het pad naar het uitvoerbare bestand niet op, maar alleen de uitvoerbare naam (zoals browser.exe).</span><span class="sxs-lookup"><span data-stu-id="738f7-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>

### <a name="unallowed-bluetooth-apps"></a><span data-ttu-id="738f7-136">Niet-toegestane Bluetooth-apps</span><span class="sxs-lookup"><span data-stu-id="738f7-136">Unallowed Bluetooth apps</span></span>

<span data-ttu-id="738f7-137">Voorkom dat personen bestanden die zijn beveiligd op basis van uw beleid, overbrengen via specifieke Bluetooth-apps.</span><span class="sxs-lookup"><span data-stu-id="738f7-137">Prevent people from transferring files protected by your policies via specific Bluetooth apps.</span></span>

### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="738f7-138">Browser- en domeinbeperkingen</span><span class="sxs-lookup"><span data-stu-id="738f7-138">Browser and domain restrictions</span></span>
<span data-ttu-id="738f7-139">Beperken dat vertrouwelijke bestanden die overeenkomen met uw beleid, worden gedeeld met beperkte cloudservicedomeinen.</span><span class="sxs-lookup"><span data-stu-id="738f7-139">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="738f7-140">Servicedomeinen</span><span class="sxs-lookup"><span data-stu-id="738f7-140">Service domains</span></span>

<span data-ttu-id="738f7-141">U kunt bepalen of vertrouwelijke bestanden die door uw beleid zijn beveiligd, vanuit Microsoft Edge kunnen worden geüpload naar specifieke servicedomeinen.</span><span class="sxs-lookup"><span data-stu-id="738f7-141">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="738f7-142">Als de lijstmodus is ingesteld op **Blokkeren**, kan de gebruiker geen vertrouwelijke items uploaden naar die domeinen.</span><span class="sxs-lookup"><span data-stu-id="738f7-142">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="738f7-143">Wanneer een uploadactie wordt geblokkeerd omdat een item overeenkomt met een DLP-beleid, genereert DLP een waarschuwing of blokkeert u de upload van het gevoelige item.</span><span class="sxs-lookup"><span data-stu-id="738f7-143">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="738f7-144">Als de lijstmodus is ingesteld op **Toestaan**, kunnen gebruikers gevoelige items **_enkel_** uploaden naar deze domeinen en is uploaden naar alle andere domeinen niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="738f7-144">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="738f7-145">Wanneer de servicebeperkingsmodus is ingesteld op Toestaan, moet er ten minste één servicedomein zijn geconfigureerd voordat de beperkingen worden afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="738f7-145">When the service restriction mode is set to "Allow", you must have at least one service domain configured before restrictions are enforced.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="738f7-146">Niet-toegestane browsers</span><span class="sxs-lookup"><span data-stu-id="738f7-146">Unallowed browsers</span></span>

<span data-ttu-id="738f7-147">U voegt browsers toe die zijn geïdentificeerd met de uitvoerbare namen, en die worden geblokkeerd voor toegang tot bestanden die voldoen aan de voorwaarden van een afgedwongen DLP-beleid waarbij de beperking voor het uploaden naar cloudservices is ingesteld op blokkeren of blokkering overschrijven.</span><span class="sxs-lookup"><span data-stu-id="738f7-147">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="738f7-148">Wanneer deze browsers geen toegang meer hebben tot een bestand, krijgen de eindgebruikers een pop-upmelding te zien waarin ze worden gevraagd het bestand te openen via Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="738f7-148">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="738f7-149">Zakelijke redenen in beleidstips</span><span class="sxs-lookup"><span data-stu-id="738f7-149">Business justification in policy tips</span></span>

<span data-ttu-id="738f7-150">U kunt bepalen hoe gebruikers werken met de optie voor zakelijke rechtvaardigingsopties in meldingen van DLP-beleidstips.</span><span class="sxs-lookup"><span data-stu-id="738f7-150">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="738f7-151">Deze optie wordt weergegeven wanneer gebruikers een activiteit uitvoeren die is beveiligd door de instelling **Blokkeren met overschrijven** in een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="738f7-151">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="738f7-152">U kunt een van de volgende opties kiezen:</span><span class="sxs-lookup"><span data-stu-id="738f7-152">You can choose from one the following options:</span></span>

- <span data-ttu-id="738f7-153">Gebruikers kunnen standaard een ingebouwde reden kiezen of hun eigen tekst invoeren.</span><span class="sxs-lookup"><span data-stu-id="738f7-153">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="738f7-154">Gebruikers kunnen alleen een ingebouwde reden selecteren.</span><span class="sxs-lookup"><span data-stu-id="738f7-154">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="738f7-155">Gebruikers kunnen alleen hun eigen reden invoeren.</span><span class="sxs-lookup"><span data-stu-id="738f7-155">Users can only enter their own justification.</span></span>

### <a name="always-audit-file-activity-for-devices"></a><span data-ttu-id="738f7-156">Bestandsactiviteiten voor apparaten altijd controleren</span><span class="sxs-lookup"><span data-stu-id="738f7-156">Always audit file activity for devices</span></span>

<span data-ttu-id="738f7-157">Wanneer apparaten zijn geregistreerd, worden activiteiten voor Office-, PDF- en CSV-bestanden standaard automatisch gecontroleerd en beschikbaar voor beoordeling in Activiteitenverkenner.</span><span class="sxs-lookup"><span data-stu-id="738f7-157">By default, when devices are onboarded, activity for Office, PDF, and CSV files is automatically audited and available for review in activity explorer.</span></span> <span data-ttu-id="738f7-158">Schakel deze functie uit als u wilt dat deze activiteit alleen wordt gecontroleerd wanneer geregistreerde apparaten worden opgenomen in een actief beleid.</span><span class="sxs-lookup"><span data-stu-id="738f7-158">Turn this feature off if you want this activity to be audited only when onboarded devices are included in an active policy.</span></span>

<span data-ttu-id="738f7-159">Bestandsactiviteiten worden altijd gecontroleerd op geregistreerde apparaten, ongeacht of ze zijn opgenomen in een actief beleid.</span><span class="sxs-lookup"><span data-stu-id="738f7-159">File activity will always be audited for onboarded devices, regardless of whether they are included in an active policy.</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="738f7-160">DLP-instellingen samenhangen</span><span class="sxs-lookup"><span data-stu-id="738f7-160">Tying DLP settings together</span></span>

<span data-ttu-id="738f7-161">Met de webbrowser Endpoint DLP en Edge Chromium kunt u het onbedoeld delen van gevoelige items beperken tot niet-toegestane cloud-apps en -services.</span><span class="sxs-lookup"><span data-stu-id="738f7-161">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="738f7-162">Edge Chromium begrijpt wanneer een item wordt beperkt door DLP-beleid voor eindpunten en dwingt toegangsbeperkingen af.</span><span class="sxs-lookup"><span data-stu-id="738f7-162">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="738f7-163">Wanneer u Endpoint DLP gebruikt als locatie in een correct geconfigureerd DLP-beleid en de Edge Ium-browser, hebben de niet-verschuldigde browsers die u hebt gedefinieerd in deze instellingen geen toegang tot de gevoelige items die overeenkomen met uw DLP-beleidsbesturingselementen.</span><span class="sxs-lookup"><span data-stu-id="738f7-163">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="738f7-164">In plaats daarvan worden gebruikers omgeleid voor het gebruik van Edge Chromium en Edge Chromium, vanwege het inzicht in de door DLP opgelegde beperkingen, om activiteiten te blokkeren of te beperken wanneer aan de voorwaarden in het DLP-beleid wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="738f7-164">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="738f7-165">Als u deze beperking wilt gebruiken, moet u drie belangrijke onderdelen configureren:</span><span class="sxs-lookup"><span data-stu-id="738f7-165">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="738f7-166">Geef de locaties (services, domeinen en IP-adressen) op met wie u wilt voorkomen dat gevoelige items worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="738f7-166">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="738f7-167">Voeg de browsers toe die geen toegang hebben tot bepaalde gevoelige items wanneer er een DLP-beleidsmatch plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="738f7-167">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="738f7-168">Configureer DLP-beleid voor het definiëren van de soorten gevoelige items waarvoor uploaden moet worden beperkt tot deze locaties door **Uploaden naar cloudservices** en **Access in te stellen vanuit een niet-toegestaan browser**.</span><span class="sxs-lookup"><span data-stu-id="738f7-168">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="738f7-169">U kunt nieuwe services, apps en beleidsregels blijven toevoegen om uw beperkingen uit te breiden en aan te passen aan uw bedrijfsbehoeften en gevoelige gegevens te beschermen.</span><span class="sxs-lookup"><span data-stu-id="738f7-169">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="738f7-170">Deze configuratie zorgt ervoor dat uw gegevens veilig blijven en vermijdt ook onnodige beperkingen die voorkomen dat gebruikers niet-vertrouwelijke items kunnen openen en delen.</span><span class="sxs-lookup"><span data-stu-id="738f7-170">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="738f7-171">DLP-beleidsscenario's voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="738f7-171">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="738f7-172">Om u vertrouwd te maken met de on-premises functies van Endpoint DLP en hoe deze worden gebruikt in DLP-beleid, hebben we enkele scenario's opgesteld die u kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="738f7-172">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="738f7-173">Deze on-premises Endpoint DLP-scenario's zijn niet de officiële procedures voor het maken en afstemmen van DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="738f7-173">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="738f7-174">Raadpleeg de onderstaande onderwerpen wanneer u in het algemeen met DLP-beleid moet werken:</span><span class="sxs-lookup"><span data-stu-id="738f7-174">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>

>- [<span data-ttu-id="738f7-175">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="738f7-175">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
>- [<span data-ttu-id="738f7-176">Aan de slag met het standaard DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="738f7-176">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="738f7-177">Een DLP-beleid maken vanuit een sjabloon</span><span class="sxs-lookup"><span data-stu-id="738f7-177">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="738f7-178">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="738f7-178">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="738f7-179">Scenario 1: Een beleid maken op basis van een sjabloon, alleen audit</span><span class="sxs-lookup"><span data-stu-id="738f7-179">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="738f7-180">Voor deze scenario's moeten apparaten a geïmplementeerd zijn en rapporteren in Activity Explorer.</span><span class="sxs-lookup"><span data-stu-id="738f7-180">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="738f7-181">Als u nog geen onboarded apparaten hebt, gaat u naar [Aan de slag met preventie van gegevensverlies in eindpunten](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="738f7-181">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="738f7-182">Open de [pagina Preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="738f7-182">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="738f7-183">Kies **Beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="738f7-183">Choose **Create policy**.</span></span>

3. <span data-ttu-id="738f7-184">In dit scenario kiest u **Privacy** en vervolgens **U.S. PII-gegevens (Persoonlijk identificeerbare informatie)** en kiest u **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="738f7-184">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="738f7-185">U kunt het veld **Status** uitschakelen voor alle locaties, behalve **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="738f7-185">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="738f7-186">Kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="738f7-186">Choose **Next**.</span></span>

5. <span data-ttu-id="738f7-187">Accepteer de standaardinstellingen **Instellingen uit de sjabloonselectie** en pas deze aan en kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="738f7-187">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="738f7-188">Accepteer de standaardacties **beschermingsacties** waarden en kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="738f7-188">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="738f7-189">Selecteer **Activiteiten controleren of beperken op Windows-apparaten** en laat de acties ingesteld op **Enkel audit**.</span><span class="sxs-lookup"><span data-stu-id="738f7-189">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="738f7-190">Kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="738f7-190">Choose **Next**.</span></span>

8. <span data-ttu-id="738f7-191">Accepteer de standaardinstellingen **Ik deze eerst wil testen** en kies **Beleidstips in de testmodus weergeven**.</span><span class="sxs-lookup"><span data-stu-id="738f7-191">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="738f7-192">Kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="738f7-192">Choose **Next**.</span></span>

9. <span data-ttu-id="738f7-193">Controleer uw instellingen en kies **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="738f7-193">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="738f7-194">Het nieuwe DLP-beleid wordt weergegeven in de beleidslijst.</span><span class="sxs-lookup"><span data-stu-id="738f7-194">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="738f7-195">Controleer Activiteitenverkenner op gegevens van de bewaakte eindpunten.</span><span class="sxs-lookup"><span data-stu-id="738f7-195">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="738f7-196">Stel het locatiefilter in voor apparaten en voeg het beleid toe. Filter vervolgens op de naam van het beleid om de gevolgen van dit beleid te bekijken.</span><span class="sxs-lookup"><span data-stu-id="738f7-196">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="738f7-197">ZIe [Aan de slag met activiteitenverkenner](data-classification-activity-explorer.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="738f7-197">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="738f7-p116">Probeer een test te delen die inhoud bevat die de Amerikaanse PII-gegevensvoorwaarde (Persoonlijk identificeerbare informatie) activeert met iemand buiten uw organisatie. Dit activeert het beleid.</span><span class="sxs-lookup"><span data-stu-id="738f7-p116">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

13. <span data-ttu-id="738f7-200">Controleer Activiteitenverkenner op de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="738f7-200">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="738f7-201">Scenario 2: Het bestaande beleid wijzigen, een waarschuwing instellen</span><span class="sxs-lookup"><span data-stu-id="738f7-201">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="738f7-202">Open de [pagina Preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="738f7-202">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="738f7-203">Kies het **PII-gegevens (Persoonlijk identificeerbare informatie)** die u hebt gemaakt in scenario 1.</span><span class="sxs-lookup"><span data-stu-id="738f7-203">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="738f7-204">Kies **Profiel bewerken**.</span><span class="sxs-lookup"><span data-stu-id="738f7-204">Choose **edit policy**.</span></span>

4. <span data-ttu-id="738f7-205">Ga naar de pagina **Geavanceerde DLP-regels** en bewerk het **lage volume aan gevonden inhoud in de Verenigde Staten. Persoonlijk identificeerbare informatie**.</span><span class="sxs-lookup"><span data-stu-id="738f7-205">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="738f7-206">Scroll omlaag naar de sectie **Incidentrapporten** en stel **Een waarschuwing verzenden naar beheerders wanneer er een regelmatch plaatsvindt** in op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="738f7-206">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="738f7-207">E-mailwaarschuwingen worden automatisch verzonden naar de beheerder en iedereen die u toevoegt aan de lijst met geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="738f7-207">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="738f7-208">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="738f7-208">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="738f7-209">In dit scenario kiest u **Waarschuwing verzenden wanneer een activiteit overeenkomt met de regel**.</span><span class="sxs-lookup"><span data-stu-id="738f7-209">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="738f7-210">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="738f7-210">Choose **Save**.</span></span>

8. <span data-ttu-id="738f7-211">Behoud alle vorige instellingen door **Volgende** te kiezen en vervolgens de beleidswijzigingen te **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="738f7-211">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="738f7-p118">Probeer een test te delen die inhoud bevat die de Amerikaanse PII-gegevensvoorwaarde (Persoonlijk identificeerbare informatie) activeert met iemand buiten uw organisatie. Dit activeert het beleid.</span><span class="sxs-lookup"><span data-stu-id="738f7-p118">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

10. <span data-ttu-id="738f7-214">Controleer Activiteitenverkenner op de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="738f7-214">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="738f7-215">Scenario 3: Het bestaande beleid wijzigen, de actie blokkeren met toestemming om te vervangen</span><span class="sxs-lookup"><span data-stu-id="738f7-215">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="738f7-216">Open de [pagina Preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="738f7-216">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="738f7-217">Kies het **PII-gegevens (Persoonlijk identificeerbare informatie)** die u hebt gemaakt in scenario 1.</span><span class="sxs-lookup"><span data-stu-id="738f7-217">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="738f7-218">Kies **Profiel bewerken**.</span><span class="sxs-lookup"><span data-stu-id="738f7-218">Choose **edit policy**.</span></span>

4. <span data-ttu-id="738f7-219">Ga naar de pagina **Geavanceerde DLP-regels** en bewerk het **lage volume aan gevonden inhoud in de Verenigde Staten. Persoonlijk identificeerbare informatie**.</span><span class="sxs-lookup"><span data-stu-id="738f7-219">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="738f7-220">Schuif omlaag naar de sectie **Activiteiten controleren of beperken op Windows-apparaat** en stel voor elke activiteit de bijbehorende actie in op **Blokkeren met overschrijven**.</span><span class="sxs-lookup"><span data-stu-id="738f7-220">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="738f7-221">![blokkeren met actie overschrijven instellen](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="738f7-221">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="738f7-222">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="738f7-222">Choose **Save**.</span></span>

7. <span data-ttu-id="738f7-223">Herhaal stap 4-7 voor het **grote hoeveelheid inhoud die in de Verenigde Staten is gedetecteerd. Persoonlijk identificeerbare informatie**.</span><span class="sxs-lookup"><span data-stu-id="738f7-223">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="738f7-224">Behoud alle vorige instellingen door **Volgende** te kiezen en vervolgens de beleidswijzigingen te **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="738f7-224">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="738f7-p119">Probeer een test te delen die inhoud bevat die de Amerikaanse PII-gegevensvoorwaarde (Persoonlijk identificeerbare informatie) activeert met iemand buiten uw organisatie. Dit activeert het beleid.</span><span class="sxs-lookup"><span data-stu-id="738f7-p119">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

   <span data-ttu-id="738f7-227">U ziet een pop-up zoals deze op het clientapparaat:</span><span class="sxs-lookup"><span data-stu-id="738f7-227">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="738f7-228">![DLP-client geblokkeerde overschrijvenmelding](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="738f7-228">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="738f7-229">Controleer Activiteitenverkenner op de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="738f7-229">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="738f7-230">Zie ook</span><span class="sxs-lookup"><span data-stu-id="738f7-230">See also</span></span>

- [<span data-ttu-id="738f7-231">Meer informatie over preventie van gegevensverlies van eindpunten</span><span class="sxs-lookup"><span data-stu-id="738f7-231">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="738f7-232">Aan de slag met Eindpunt-DLP (gegevensverlies voor eindpunten)</span><span class="sxs-lookup"><span data-stu-id="738f7-232">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="738f7-233">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="738f7-233">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="738f7-234">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="738f7-234">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="738f7-235">Aan de slag met Activity Explorer</span><span class="sxs-lookup"><span data-stu-id="738f7-235">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="738f7-236">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="738f7-236">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="738f7-237">Hulpmiddelen en methoden onboarden voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="738f7-237">Onboarding tools and methods for Windows 10 machines</span></span>](/microsoft-365/compliance/dlp-configure-endpoints)
- [<span data-ttu-id="738f7-238">Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="738f7-238">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="738f7-239">gekoppeld met Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="738f7-239">Azure Active Directory (AAD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="738f7-240">De nieuwe Microsoft Edge op basis van Chromium downloaden</span><span class="sxs-lookup"><span data-stu-id="738f7-240">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="738f7-241">Aan de slag met het standaard DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="738f7-241">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="738f7-242">Een DLP-beleid maken vanuit een sjabloon</span><span class="sxs-lookup"><span data-stu-id="738f7-242">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
