---
title: Microsoft Compliance Configuration Analyzer voor Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het gebruik van Microsoft Compliance Configuration Analyzer om snel aan de weg te gaan met Microsoft Compliance Manager.
ms.openlocfilehash: 2b91ac274d7270f5be9530742cf711a3918b287d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162526"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="29eb4-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span><span class="sxs-lookup"><span data-stu-id="29eb4-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="29eb4-104">**In dit artikel:** Meer informatie over het installeren en uitvoeren van het hulpprogramma Microsoft Compliance Configure Analyzer om snel aan de slag te gaan met Microsoft Compliance Manger.</span><span class="sxs-lookup"><span data-stu-id="29eb4-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="29eb4-105">Overzicht van Microsoft Compliance Configuration Analyzer (MCCA) (preview)</span><span class="sxs-lookup"><span data-stu-id="29eb4-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="29eb4-106">De Microsoft Compliance Configuration Analyzer (MCCA) is een preview-hulpprogramma waarmee u aan de slag kunt met [Microsoft Compliance Manager.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="29eb4-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="29eb4-107">MCCA is een op PowerShell gebaseerd hulpprogramma dat de huidige configuraties van uw organisatie op haalt en valideert op basis van Microsoft 365 aanbevolen aanbevolen procedures.</span><span class="sxs-lookup"><span data-stu-id="29eb4-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="29eb4-108">Deze best practices zijn gebaseerd op een reeks besturingselementen die belangrijke voorschriften en standaarden bevatten voor gegevensbescherming en gegevensbeheer.</span><span class="sxs-lookup"><span data-stu-id="29eb4-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="29eb4-109">Met MCCA kunt u snel zien welke verbeteracties in Compliance Manger van toepassing zijn op uw huidige Microsoft 365 omgeving.</span><span class="sxs-lookup"><span data-stu-id="29eb4-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="29eb4-110">Elke actie die door MCCA wordt geïdentificeerd, geeft u aanbevelingen voor de implementatie, met directe koppelingen naar Compliance Manager en de toepasselijke oplossing om corrigerende actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="29eb4-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="29eb4-111">Een extra bron voor het begrijpen van MCCA is door de [README-instructies op GitHub.](https://github.com/OfficeDev/MCCA#overview)</span><span class="sxs-lookup"><span data-stu-id="29eb4-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="29eb4-112">Deze pagina bevat gedetailleerde informatie over vereisten en bevat volledige installatie-instructies.</span><span class="sxs-lookup"><span data-stu-id="29eb4-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="29eb4-113">U hebt geen account nodig GitHub om toegang te krijgen tot deze pagina.</span><span class="sxs-lookup"><span data-stu-id="29eb4-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="29eb4-114">**Beschikbaarheid:** MCCA is beschikbaar voor alle organisaties met Office 365- en Microsoft 365-licenties en klanten van de Amerikaanse overheid (GCC) Moderate, GCC High en Ministerie van Defensie (DoD).</span><span class="sxs-lookup"><span data-stu-id="29eb4-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="29eb4-115">MCCA installeren en een rapport uitvoeren</span><span class="sxs-lookup"><span data-stu-id="29eb4-115">Install MCCA and run a report</span></span>

<span data-ttu-id="29eb4-116">U kunt het hulpprogramma MCCA installeren met Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29eb4-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="29eb4-117">Nadat u het hulpprogramma hebt gedownload en geïnstalleerd, hoeft u deze stappen niet te herhalen om rapporten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="29eb4-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="29eb4-118">Telkens wanneer u MCCA opent, wordt u om uw aanmeldingsreferenties gevraagd en wordt er een nieuw, bijgewerkt rapport gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="29eb4-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="29eb4-119">Stap 1: Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29eb4-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="29eb4-120">Om te beginnen hebt u de Exchange Online PowerShell-module (v2.0.3 of hoger) nodig die beschikbaar is in de PowerShell-galerie.</span><span class="sxs-lookup"><span data-stu-id="29eb4-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="29eb4-121">[Installatie-instructies krijgen.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)</span><span class="sxs-lookup"><span data-stu-id="29eb4-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="29eb4-122">Stap 2: MCCA installeren</span><span class="sxs-lookup"><span data-stu-id="29eb4-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="29eb4-123">Als u MCCA wilt installeren, gebruikt u Eerst PowerShell in de beheerdersmodus.</span><span class="sxs-lookup"><span data-stu-id="29eb4-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="29eb4-124">Volg de onderstaande stappen:</span><span class="sxs-lookup"><span data-stu-id="29eb4-124">Follow the steps below:</span></span>

1. <span data-ttu-id="29eb4-125">Selecteer de Windows **startknop.**</span><span class="sxs-lookup"><span data-stu-id="29eb4-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="29eb4-126">Typ **PowerShell,** klik met de rechtermuisknop op **Windows PowerShell** en selecteer vervolgens Als **beheerder uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="29eb4-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="29eb4-127">Typ bij de opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="29eb4-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="29eb4-128">Stap 3: Een rapport uitvoeren</span><span class="sxs-lookup"><span data-stu-id="29eb4-128">Step 3: Run a report</span></span>

<span data-ttu-id="29eb4-129">Nadat u MCCA hebt geïnstalleerd, kunt u MCCA uitvoeren en een rapport genereren.</span><span class="sxs-lookup"><span data-stu-id="29eb4-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="29eb4-130">Een rapport uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="29eb4-130">To run a report:</span></span>

1. <span data-ttu-id="29eb4-131">PowerShell openen</span><span class="sxs-lookup"><span data-stu-id="29eb4-131">Open PowerShell</span></span>
2. <span data-ttu-id="29eb4-132">Voer de cmdlet uit:</span><span class="sxs-lookup"><span data-stu-id="29eb4-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```

   <span data-ttu-id="29eb4-133">Als u een GCC hoge klant bent, moet u een extra invoerparameter opgeven om het rapport uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="29eb4-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="29eb4-134">Wanneer MCCA is uitgevoerd, wordt er een eerste versiecontrole uitgevoerd en wordt om referenties gevraagd.</span><span class="sxs-lookup"><span data-stu-id="29eb4-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="29eb4-135">Meld u bij de prompt Invoer van de gebruikersnaam aan met uw e-mailadres Microsoft 365 account ( bekijk de rollen die in aanmerking komen om[rapporten te maken).](#role-based-reporting)</span><span class="sxs-lookup"><span data-stu-id="29eb4-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="29eb4-136">Voer vervolgens uw wachtwoord in bij de wachtwoordprompt.</span><span class="sxs-lookup"><span data-stu-id="29eb4-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="29eb4-137">Het genereren van uw rapport duurt ongeveer 2-5 minuten.</span><span class="sxs-lookup"><span data-stu-id="29eb4-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="29eb4-138">Wanneer het klaar is, wordt een browservenster geopend en wordt uw HTML-rapport weergegeven.</span><span class="sxs-lookup"><span data-stu-id="29eb4-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="29eb4-139">Telkens wanneer u het hulpprogramma uit runt, wordt om uw referenties gevraagd en wordt er een nieuw rapport gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="29eb4-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="29eb4-140">Dit rapport wordt lokaal opgeslagen in de volgende adreslijst:</span><span class="sxs-lookup"><span data-stu-id="29eb4-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="29eb4-141">C:\Gebruikers \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="29eb4-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="29eb4-142">U hebt toegang tot eerder gegenereerde rapporten vanuit deze adreslijst.</span><span class="sxs-lookup"><span data-stu-id="29eb4-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="29eb4-143">Uw rapport begrijpen</span><span class="sxs-lookup"><span data-stu-id="29eb4-143">Understanding your report</span></span>

<span data-ttu-id="29eb4-144">Uw rapport geeft gegevens weer op basis van de datum en tijd waarop het is gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="29eb4-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="29eb4-145">De bovenste sectie bevat details over wanneer deze is gegenereerd, de naam van uw organisatie en de tenant-id.</span><span class="sxs-lookup"><span data-stu-id="29eb4-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="29eb4-146">Geolocation-based reporting</span><span class="sxs-lookup"><span data-stu-id="29eb4-146">Geolocation-based reporting</span></span>

<span data-ttu-id="29eb4-147">In **de sectie** Notitie ziet u dat uw rapport is aangepast op basis van de geografische locatie van uw tenant.</span><span class="sxs-lookup"><span data-stu-id="29eb4-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="29eb4-148">Aanbevelingen in het hulpprogramma wordt vermeld, is specifiek voor uw land of regio.</span><span class="sxs-lookup"><span data-stu-id="29eb4-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="29eb4-149">Uw geolocatieselectie wordt gebruikt om gevoelige informatietypen (SIT's) te beoordelen die relevant zijn voor die geolocatie en om een rapport te genereren dat is afgestemd op uw land of regio.</span><span class="sxs-lookup"><span data-stu-id="29eb4-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="29eb4-150">Kies geolocaties op basis van gegevens in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="29eb4-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="29eb4-151">Als u de locatiegegevens van uw rapport wilt wijzigen, moet u een geolocatie-invoerparameter opgeven.</span><span class="sxs-lookup"><span data-stu-id="29eb4-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="29eb4-152">U kunt een of meerdere geolocaties kiezen die van toepassing zijn op uw tenant.</span><span class="sxs-lookup"><span data-stu-id="29eb4-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="29eb4-153">Volg deze instructies om een rapport uit te voeren op basis van een specifieke locatie:</span><span class="sxs-lookup"><span data-stu-id="29eb4-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="29eb4-154">PowerShell openen</span><span class="sxs-lookup"><span data-stu-id="29eb4-154">Open PowerShell</span></span>
2. <span data-ttu-id="29eb4-155">Als u een bepaald gebied wilt opgeven, wordt een cmdlet uitgevoerd met behulp van de getallen uit de onderstaande tabel die overeenkomen met het land of de regio.</span><span class="sxs-lookup"><span data-stu-id="29eb4-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="29eb4-156">Voer meerdere getallen in door ze te scheiden met een komma.</span><span class="sxs-lookup"><span data-stu-id="29eb4-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="29eb4-157">Op de cmdlet hieronder wordt bijvoorbeeld een aangepast rapport uitgevoerd voor Asia-Pacific en Japan:</span><span class="sxs-lookup"><span data-stu-id="29eb4-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="29eb4-158">Invoer</span><span class="sxs-lookup"><span data-stu-id="29eb4-158">Input</span></span> |  <span data-ttu-id="29eb4-159">Land of regio</span><span class="sxs-lookup"><span data-stu-id="29eb4-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="29eb4-160">1</span><span class="sxs-lookup"><span data-stu-id="29eb4-160">1</span></span> | <span data-ttu-id="29eb4-161">Asia-Pacific</span><span class="sxs-lookup"><span data-stu-id="29eb4-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="29eb4-162">2</span><span class="sxs-lookup"><span data-stu-id="29eb4-162">2</span></span> | <span data-ttu-id="29eb4-163">Australië</span><span class="sxs-lookup"><span data-stu-id="29eb4-163">Australia</span></span> |
  | <span data-ttu-id="29eb4-164">3</span><span class="sxs-lookup"><span data-stu-id="29eb4-164">3</span></span> | <span data-ttu-id="29eb4-165">Canada</span><span class="sxs-lookup"><span data-stu-id="29eb4-165">Canada</span></span> |
  | <span data-ttu-id="29eb4-166">4</span><span class="sxs-lookup"><span data-stu-id="29eb4-166">4</span></span> | <span data-ttu-id="29eb4-167">Europa (exclusief Frankrijk) / Midden-Oosten / Afrika</span><span class="sxs-lookup"><span data-stu-id="29eb4-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="29eb4-168">5</span><span class="sxs-lookup"><span data-stu-id="29eb4-168">5</span></span> | <span data-ttu-id="29eb4-169">Frankrijk</span><span class="sxs-lookup"><span data-stu-id="29eb4-169">France</span></span> |
  | <span data-ttu-id="29eb4-170">6</span><span class="sxs-lookup"><span data-stu-id="29eb4-170">6</span></span> | <span data-ttu-id="29eb4-171">India</span><span class="sxs-lookup"><span data-stu-id="29eb4-171">India</span></span> |
  | <span data-ttu-id="29eb4-172">7</span><span class="sxs-lookup"><span data-stu-id="29eb4-172">7</span></span> | <span data-ttu-id="29eb4-173">Japan </span><span class="sxs-lookup"><span data-stu-id="29eb4-173">Japan</span></span> |
  | <span data-ttu-id="29eb4-174">8</span><span class="sxs-lookup"><span data-stu-id="29eb4-174">8</span></span> | <span data-ttu-id="29eb4-175">Korea </span><span class="sxs-lookup"><span data-stu-id="29eb4-175">Korea</span></span> |
  | <span data-ttu-id="29eb4-176">9</span><span class="sxs-lookup"><span data-stu-id="29eb4-176">9</span></span> | <span data-ttu-id="29eb4-177">Noord-Amerika (met uitzondering van Canada)</span><span class="sxs-lookup"><span data-stu-id="29eb4-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="29eb4-178">10</span><span class="sxs-lookup"><span data-stu-id="29eb4-178">10</span></span> | <span data-ttu-id="29eb4-179">Zuid-Amerika</span><span class="sxs-lookup"><span data-stu-id="29eb4-179">South America</span></span> |
  | <span data-ttu-id="29eb4-180">11</span><span class="sxs-lookup"><span data-stu-id="29eb4-180">11</span></span> | <span data-ttu-id="29eb4-181">Zuid-Afrika</span><span class="sxs-lookup"><span data-stu-id="29eb4-181">South Africa</span></span> |
  | <span data-ttu-id="29eb4-182">12</span><span class="sxs-lookup"><span data-stu-id="29eb4-182">12</span></span> | <span data-ttu-id="29eb4-183">Zwitserland</span><span class="sxs-lookup"><span data-stu-id="29eb4-183">Switzerland</span></span> |
  | <span data-ttu-id="29eb4-184">13</span><span class="sxs-lookup"><span data-stu-id="29eb4-184">13</span></span> | <span data-ttu-id="29eb4-185">Verenigde Arabische Emiraten</span><span class="sxs-lookup"><span data-stu-id="29eb4-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="29eb4-186">14</span><span class="sxs-lookup"><span data-stu-id="29eb4-186">14</span></span> | <span data-ttu-id="29eb4-187">Verenigd Koninkrijk</span><span class="sxs-lookup"><span data-stu-id="29eb4-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="29eb4-188">Het rapport bevat altijd door MCCA ondersteunde internationale gevoelige informatietypen, zoals SWIFT-code, creditcardnummer, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="29eb4-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="29eb4-189">Rapportering op basis van rollen</span><span class="sxs-lookup"><span data-stu-id="29eb4-189">Role-based reporting</span></span>

<span data-ttu-id="29eb4-190">Uw rapport wordt ook aangepast op basis van uw rol.</span><span class="sxs-lookup"><span data-stu-id="29eb4-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="29eb4-191">In de onderstaande tabel ziet u welke rollen toegang hebben tot welke secties van het rapport.</span><span class="sxs-lookup"><span data-stu-id="29eb4-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="29eb4-192">Andere rollen binnen uw organisatie (die niet worden vermeld in de onderstaande tabel) kunnen het hulpprogramma mogelijk niet uitvoeren of ze kunnen het hulpprogramma uitvoeren en hebben beperkte toegang tot informatie in het uiteindelijke rapport.</span><span class="sxs-lookup"><span data-stu-id="29eb4-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="29eb4-193">![MCCA - rollen](../media/compliance-manager-mcca-roles.png "MCCA-rollen")</span><span class="sxs-lookup"><span data-stu-id="29eb4-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="29eb4-194">Uitzonderingen:</span><span class="sxs-lookup"><span data-stu-id="29eb4-194">Exceptions:</span></span>
1. <span data-ttu-id="29eb4-195">Gebruikers kunnen geen rapport voor IP genereren, afgezien van de sectie 'IRM gebruiken Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="29eb4-195">Users won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="29eb4-196">Gebruikers kunnen rapport genereren voor IP, afgezien van de sectie 'IRM gebruiken Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="29eb4-196">Users will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="29eb4-197">Gebruikers kunnen rapport voor IP genereren, afgezien van de sectie Communicatie compliance in O365 inschakelen.</span><span class="sxs-lookup"><span data-stu-id="29eb4-197">Users will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="29eb4-198">Gebruikers kunnen geen rapport voor IP genereren, afgezien van de sectie 'Auditing inschakelen in Office 365' sectie.</span><span class="sxs-lookup"><span data-stu-id="29eb4-198">Users won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="29eb4-199">Gebruikers kunnen rapport genereren voor IP, behalve 'Auditing inschakelen in Office 365' sectie.</span><span class="sxs-lookup"><span data-stu-id="29eb4-199">Users will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="29eb4-200">Sectie Overzicht van oplossingen</span><span class="sxs-lookup"><span data-stu-id="29eb4-200">Solutions Summary section</span></span>

<span data-ttu-id="29eb4-201">De **sectie Oplossingenoverzicht** van het rapport bevat een overzicht van verbeteracties die uw organisatie in Compliance Manager kan uitvoeren om uw nalevingsstatus te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="29eb4-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="29eb4-202">![MCCA - samenvatting van oplossingen](../media/compliance-manager-mcca-solutions.png "Overzichtsscherm MCCA Solutions")</span><span class="sxs-lookup"><span data-stu-id="29eb4-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="29eb4-203">MCCA evalueert uw huidige configuraties op basis van de aanbevolen verbeteringsacties in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="29eb4-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="29eb4-204">Elke verbeteringsactie die door het hulpprogramma MCCA wordt geïdentificeerd als het nodig heeft om aandacht te krijgen, wordt weergegeven in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="29eb4-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="29eb4-205">Naast elke Microsoft-oplossing staan vakken met kleurcode die het aantal items aangeven dat overeenkomt met verbeteracties in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="29eb4-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="29eb4-206">De acties zijn onderverdeeld in drie statusstatussen:</span><span class="sxs-lookup"><span data-stu-id="29eb4-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="29eb4-207">**OK:** de acties die voldoen aan aanbevolen voorwaarden en op dit moment geen aandacht nodig hebben</span><span class="sxs-lookup"><span data-stu-id="29eb4-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="29eb4-208">**Verbetering:** acties die aandacht nodig hebben</span><span class="sxs-lookup"><span data-stu-id="29eb4-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="29eb4-209">**Aanbeveling:** acties die geen aandacht nodig hebben, maar waarvoor we aanbevolen aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="29eb4-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="29eb4-210">Selecteer een vak om verbeteringen en aanbevelingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="29eb4-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="29eb4-211">**Items met de status Verbetering**</span><span class="sxs-lookup"><span data-stu-id="29eb4-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="29eb4-212">Selecteer de vervolgkeuzekeuze naast het label **Verbetering** rechts van de verbeteringsactie.</span><span class="sxs-lookup"><span data-stu-id="29eb4-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="29eb4-213">U ziet een beknopt overzicht en informatie over uw huidige instellingen en de aanbevolen verbeteracties.</span><span class="sxs-lookup"><span data-stu-id="29eb4-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="29eb4-214">De samenvatting bevat directe koppelingen naar Compliance Manager, de toepasselijke oplossing in het Microsoft 365 compliancecentrum en relevante documentatie.</span><span class="sxs-lookup"><span data-stu-id="29eb4-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="29eb4-215">Als u op de koppeling Compliancebeheer klikt, gaat u naar een gefilterde weergave van alle verbeteracties binnen die oplossing die u nog niet hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="29eb4-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="29eb4-216">Hier ziet u het aantal punten dat u kunt behalen om uw [nalevingsscore](compliance-score-calculation.md)te verhogen, en de beoordelingen die erop van toepassing zijn, en de toepasselijke voorschriften en certificeringen.</span><span class="sxs-lookup"><span data-stu-id="29eb4-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="29eb4-217">Voor DLP is er een knop **Herstelscript** waarmee u een vooraf gegenereerd PowerShell-script krijgt op basis van wat wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="29eb4-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="29eb4-218">U kunt deze rechtstreeks kopiëren en plakken in uw PowerShell-console.</span><span class="sxs-lookup"><span data-stu-id="29eb4-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="29eb4-219">Er wordt een DLP-beleid in de testmodus</span><span class="sxs-lookup"><span data-stu-id="29eb4-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="29eb4-220">**Items met de status Aanbeveling**</span><span class="sxs-lookup"><span data-stu-id="29eb4-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="29eb4-221">Selecteer de vervolgkeuzekeuze naast het label **Aanbeveling** rechts van de verbeteringsactie.</span><span class="sxs-lookup"><span data-stu-id="29eb4-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="29eb4-222">U ziet een overzicht van de huidige omgeving van uw organisatie Microsoft 365 de verbeteringsactie, samen met aanbevolen aanbevolen aanbevolen procedures.</span><span class="sxs-lookup"><span data-stu-id="29eb4-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="29eb4-223">Resources</span><span class="sxs-lookup"><span data-stu-id="29eb4-223">Resources</span></span>

<span data-ttu-id="29eb4-224">Zie de INSTRUCTIES VOOR LEZEN op GitHub (geen GitHub [](https://github.com/OfficeDev/MCCA#overview) vereist) voor meer informatie over het installeren, instellen en gebruiken van MCCA.</span><span class="sxs-lookup"><span data-stu-id="29eb4-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="29eb4-225">Voor meer informatie over Windows PowerShell, start u bij [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="29eb4-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="29eb4-226">Zie ook [Windows PowerShell.](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="29eb4-226">See also [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>