---
title: Veelgestelde vragen over testbasis
description: Veelgestelde vragen bekijken
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322925"
---
# <a name="test-base-faq"></a><span data-ttu-id="72fbd-103">Veelgestelde vragen over testbasis</span><span class="sxs-lookup"><span data-stu-id="72fbd-103">Test Base FAQ</span></span>

<span data-ttu-id="72fbd-104">**V: Hoe verzenden we onze pakketten naar testbasisteam?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="72fbd-105">**A:** Verzend uw pakketten rechtstreeks naar de Test Base-omgeving via onze self-serve portal.</span><span class="sxs-lookup"><span data-stu-id="72fbd-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="72fbd-106">Als u uw toepassingspakket wilt verzenden, gaat u naar de [Azure Portal](https://www.aka.ms/testbaseportal "Startpagina testbasis") en uploadt u een geritste map met binaries, afhankelijkheden en testscripts van uw toepassing via het dashboard van de self-serve Test Base-portal.</span><span class="sxs-lookup"><span data-stu-id="72fbd-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="72fbd-107">Raadpleeg de onboarding-gebruikershandleiding voor meer informatie of neem contact op met ons team voor <testbasepreview@microsoft.com> hulp en meer informatie.</span><span class="sxs-lookup"><span data-stu-id="72fbd-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="72fbd-108">**V: Wat zijn out-of-box (OOB)-tests?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="72fbd-109">**A:** Out-of-box (OOB)-tests zijn gestandaardiseerd, standaard worden test uitgevoerd waarbij toepassingspakketten zijn geïnstalleerd, dertig (30) keer zijn gestart en gesloten en vervolgens worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="72fbd-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="72fbd-110">De pakketten die voor Test Base zijn gemaakt, hebben de volgende testscripts: installeren, starten, sluiten en eventueel het script verwijderen.</span><span class="sxs-lookup"><span data-stu-id="72fbd-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="72fbd-111">De out-of-box -tests (OOB) bieden u gestandaardiseerde telemetrie in uw toepassing om te vergelijken tussen Windows builds.</span><span class="sxs-lookup"><span data-stu-id="72fbd-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="72fbd-112">**V: Kunnen we tests indienen buiten de out-of-box-tests (installeren, starten, sluiten, testscripts verwijderen)?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="72fbd-113">**A:** Ja, klanten kunnen ook toepassingspakketten uploaden voor **functionele tests** via het dashboard van de self-serve portal.</span><span class="sxs-lookup"><span data-stu-id="72fbd-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="72fbd-114">**Functionele tests** zijn tests waarmee klanten hun scripts kunnen uitvoeren om aangepaste functionaliteit uit te voeren op hun toepassing.</span><span class="sxs-lookup"><span data-stu-id="72fbd-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="72fbd-115">Testen</span><span class="sxs-lookup"><span data-stu-id="72fbd-115">Testing</span></span>

<span data-ttu-id="72fbd-116">**V: Ondersteunt u functionele tests?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="72fbd-117">**A:** Ja, Test Base ondersteunt functionele tests.</span><span class="sxs-lookup"><span data-stu-id="72fbd-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="72fbd-118">Functionele tests zijn tests waarmee onze klanten hun scripts kunnen uitvoeren om aangepaste functionaliteit voor hun toepassing uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="72fbd-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="72fbd-119">Als u uw toepassingspakket wilt indienen voor functionele tests, uploadt u de geritste map met de binaries, afhankelijkheden en testscripts van uw toepassing via ons self-serve portaldashboard.</span><span class="sxs-lookup"><span data-stu-id="72fbd-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="72fbd-120">Raadpleeg de onboarding-gebruikershandleiding voor meer informatie of neem contact op met ons team voor <testbasepreview@microsoft.com> hulp en meer informatie.</span><span class="sxs-lookup"><span data-stu-id="72fbd-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="72fbd-121">**V: Hoe gaat Test Base om met onze testgegevens?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="72fbd-122">**A:** Test Base verzamelt en beheert uw testgegevens veilig in de Azure-omgeving.</span><span class="sxs-lookup"><span data-stu-id="72fbd-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="72fbd-123">**V: Kan Test Base onze geautomatiseerde tests ondersteunen?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="72fbd-124">Ja, Test Base ondersteunt geautomatiseerde tests, maar op dit moment ondersteunen we geen handmatige tests vanwege servicemogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="72fbd-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="72fbd-125">**V: Welke talen en frameworks van geautomatiseerde tests ondersteunt u?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="72fbd-126">**A:** We ondersteunen alle talen en frameworks.</span><span class="sxs-lookup"><span data-stu-id="72fbd-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="72fbd-127">We roepen alle scripts aan via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72fbd-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="72fbd-128">U moet ook de afhankelijke binaries van het vereiste framework verstrekken (uploaden).</span><span class="sxs-lookup"><span data-stu-id="72fbd-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="72fbd-129">**V: Hoe snel levert Test Base testresultaten op?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="72fbd-130">**A:** Voor elke test die we uitvoeren met de pre-release builds, leveren we binnen 48 uur resultaten op uw [Azure Portal-dashboard.](https://www.aka.ms/testbaseportal "Startpagina testbasis")</span><span class="sxs-lookup"><span data-stu-id="72fbd-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="72fbd-131">**V: Kunt u opnieuw opstarten na de installatie?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="72fbd-132">**A:** Ja, ons proces ondersteunt opnieuw opstarten na de installatie.</span><span class="sxs-lookup"><span data-stu-id="72fbd-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="72fbd-133">Selecteer deze optie in de vervolgkeuzelijst 'Optionele  instellingen' wanneer u taken in de onboarding-portal instelt.</span><span class="sxs-lookup"><span data-stu-id="72fbd-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="72fbd-134">Voor OOB-tests (Out-of-box) kunt u opgeven of een herstart nodig is voor het _installatiescript._</span><span class="sxs-lookup"><span data-stu-id="72fbd-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![Afbeelding opnieuw opstarten](Media/reboot.png)

<span data-ttu-id="72fbd-136">Voor functionele tests kunt u opgeven of een herstart vereist is voor elk script dat wordt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="72fbd-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![Functionele tests selecteren](Media/functionalreboot.png)

<span data-ttu-id="72fbd-138">**V: Welke Windows versies ondersteunt u?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="72fbd-139">**A:** Momenteel ondersteunen we Windows 10 clients, Windows Server 2016, Windows Server 2016 Core-versie, Windows Server 2019 en Windows Server 2019 Core-versie.</span><span class="sxs-lookup"><span data-stu-id="72fbd-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="72fbd-140">**V: Wat is het verschil tussen beveiligingsupdatetests en functieupdatetests?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="72fbd-141">**A:** Voor beveiligingsupdatetests testen we de maandelijkse **<ins>pre-release</ins>** beveiligingsupdates op Windows die zijn gericht op het altijd beveiligen en beveiligen van onze gebruikers.</span><span class="sxs-lookup"><span data-stu-id="72fbd-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="72fbd-142">Voor de onderdelenupdatetests wordt getest op de tweejaarlijkse **<ins>pre-releasefunctieupdates</ins>** die nieuwe functies en mogelijkheden introduceren op Windows.</span><span class="sxs-lookup"><span data-stu-id="72fbd-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="72fbd-143">Opties voor debuggen</span><span class="sxs-lookup"><span data-stu-id="72fbd-143">Debugging options</span></span>

<span data-ttu-id="72fbd-144">**V: Krijgen we toegang tot virtuele machines (VM's) in geval van fouten? Wat deelt Test Base?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="72fbd-145">**A:** Als de service compatibel is en de pre-release-updates veilig zijn, heeft alleen Microsoft toegang tot de VM's.</span><span class="sxs-lookup"><span data-stu-id="72fbd-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="72fbd-146">Klanten kunnen echter testresultaten en andere testmetrische gegevens bekijken op hun portaldashboard, zoals crash- en hangsignalen, betrouwbaarheidsgegevens, geheugen- en CPU-gebruik, enzovoort. We genereren en bieden ook logboeken van test uitgevoerd op het dashboard voor download en verdere analyse.</span><span class="sxs-lookup"><span data-stu-id="72fbd-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="72fbd-147">We kunnen ook geheugendumps bieden voor crashdebugging als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="72fbd-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="72fbd-148">**V: Als er tijdens het testen problemen zijn gevonden, wat zijn de volgende stappen om deze problemen op te lossen?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="72fbd-149">**A:** Het Test Base-team voert een eerste triageproces uit om de hoofdoorzaak van de fout te bepalen. Afhankelijk van onze bevindingen worden we doorgeleid naar de klant of interne teams binnen Microsoft voor foutopsporing.</span><span class="sxs-lookup"><span data-stu-id="72fbd-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="72fbd-150">We werken altijd nauw samen met onze klanten in gezamenlijke herstel om eventuele problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="72fbd-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="72fbd-151">**V: Houdt Microsoft de release van de beveiligingspatch in stand totdat het probleem is opgelost? Welke alternatieve resoluties zijn beschikbaar?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="72fbd-152">**A:** Het doel van Test Base is ervoor te zorgen dat onze gezamenlijke eindklanten geen problemen hebben.</span><span class="sxs-lookup"><span data-stu-id="72fbd-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="72fbd-153">We zullen hard werken met Softwareleveranciers om eventuele problemen vóór de release op te lossen, maar voor het geval de oplossing niet haalbaar is, hebben we andere oplossingen, zoals shims en blokken.</span><span class="sxs-lookup"><span data-stu-id="72fbd-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="72fbd-154">Diversen</span><span class="sxs-lookup"><span data-stu-id="72fbd-154">Miscellaneous</span></span>

<span data-ttu-id="72fbd-155">**V: Hoe werkt de service met een on-prem-server?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="72fbd-156">**A:** We bieden momenteel geen ondersteuning voor on-prem-servers.</span><span class="sxs-lookup"><span data-stu-id="72fbd-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="72fbd-157">Als de server echter HTTP-eindpunt aan de dag leggen, kunnen we er verbinding mee maken via internet.</span><span class="sxs-lookup"><span data-stu-id="72fbd-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="72fbd-158">**V: Wie de VM's host?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="72fbd-159">**A:** Microsoft voor deze service stelt de VM in en neemt de belasting van de klant over.</span><span class="sxs-lookup"><span data-stu-id="72fbd-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="72fbd-160">**V: Biedt deze service ondersteuning voor web-, mobiele of desktoptoepassingen?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="72fbd-161">**A:** Op dit moment ligt onze focus op desktoptoepassingen, maar we hebben plannen om webtoepassingen in de toekomst aan te nemen, maar we ondersteunen op dit moment geen mobiele toepassingen.</span><span class="sxs-lookup"><span data-stu-id="72fbd-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="72fbd-162">**V: Wat is het verschil tussen Test Base en SUVP?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="72fbd-163">**A:** Het grootste verschil tussen Test Base en SUVP is dat onze partners hun toepassingen aan boord van de Test Base Azure-omgeving voor validatie uitvoeren tegen pre-releaseupdates in plaats van de tests zelf uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="72fbd-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="72fbd-164">Naast het testen van beveiligingsupdates die vooraf zijn uitgebracht, ondersteunen we het testen van functieupdates voor de pre-release op ons platform.</span><span class="sxs-lookup"><span data-stu-id="72fbd-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="72fbd-165">We hebben veel andere soorten updates en besturingssysteemtests op onze routekaart.</span><span class="sxs-lookup"><span data-stu-id="72fbd-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="72fbd-166">**V: Zijn er kosten aan de service gekoppeld?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="72fbd-167">**A:** De Test Base-service is gratis voor gebruikers tot algemene beschikbaarheid (GA).</span><span class="sxs-lookup"><span data-stu-id="72fbd-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="72fbd-168">Op dat moment kondigen we een kostenstructuur aan die van kracht wordt voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="72fbd-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="72fbd-169">**V: Hoe kan ik feedback geven over Test Base?**</span><span class="sxs-lookup"><span data-stu-id="72fbd-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="72fbd-170">**A:** Als u uw feedback over Test Base wilt delen, selecteert u het **pictogram Feedback** linksonder in de portal.</span><span class="sxs-lookup"><span data-stu-id="72fbd-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="72fbd-171">Voeg een schermafbeelding toe bij uw inzending om Microsoft te helpen uw feedback beter te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="72fbd-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="72fbd-172">U kunt ook productsuggesties indienen en andere ideeën upvote op <testbasepreview@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="72fbd-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
