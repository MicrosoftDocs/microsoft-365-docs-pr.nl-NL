---
title: Bestaande apparaten zelf registreren
description: Registreer hergebruikte apparaten die u misschien al zelf hebt, zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: abe9e63eb4fcd31993bd26822dc445ff0e48e369
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101483"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="02f09-103">Bestaande apparaten zelf registreren</span><span class="sxs-lookup"><span data-stu-id="02f09-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="02f09-104">In dit onderwerp worden de stappen beschreven die u uitvoeren om apparaten die u al hebt, opnieuw te gebruiken en deze te registreren in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="02f09-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="02f09-105">Als u met gloednieuwe apparaten werkt, volgt u de stappen in [Het registreren van nieuwe apparaten in Microsoft Managed Desktop zelf.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="02f09-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="02f09-106">Het proces voor partners wordt gedocumenteerd in [Stappen voor partners om apparaten te registreren.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="02f09-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="02f09-107">Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u apparaten die u mogelijk al hebt hergebruiken (waarvoor u ze opnieuw moet imagen).</span><span class="sxs-lookup"><span data-stu-id="02f09-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="02f09-108">U apparaten registreren met behulp van de Microsoft Managed Desktop Admin Portal.</span><span class="sxs-lookup"><span data-stu-id="02f09-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="02f09-109">Voorbereiden om bestaande apparaten te registreren</span><span class="sxs-lookup"><span data-stu-id="02f09-109">Prepare to register existing devices</span></span>


<span data-ttu-id="02f09-110">Voer de volgende stappen uit om bestaande apparaten te registreren:</span><span class="sxs-lookup"><span data-stu-id="02f09-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="02f09-111">Verkrijg de hardwarehash voor elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="02f09-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="02f09-112">De hash-gegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="02f09-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="02f09-113">[Registreer de apparaten in Microsoft Managed Desktop](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="02f09-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="02f09-114">Controleer of de afbeelding juist is.</span><span class="sxs-lookup"><span data-stu-id="02f09-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="02f09-115">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="02f09-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="02f09-116">De hardwarehash verkrijgen</span><span class="sxs-lookup"><span data-stu-id="02f09-116">Obtain the hardware hash</span></span>

<span data-ttu-id="02f09-117">Microsoft Managed Desktop identificeert elk apparaat op unieke wijze door te verwijzen naar de hardwarehash.</span><span class="sxs-lookup"><span data-stu-id="02f09-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="02f09-118">Je hebt vier opties om deze informatie te verkrijgen van apparaten die je al gebruikt:</span><span class="sxs-lookup"><span data-stu-id="02f09-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="02f09-119">Vraag uw OEM-leverancier om het AutoPilot-registratiebestand, dat de hardwarehashes bevat.</span><span class="sxs-lookup"><span data-stu-id="02f09-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="02f09-120">Een aangepast rapport maken in [Configuratiebeheer](#configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="02f09-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="02f09-121">Voer een Windows PowerShell-script uit met [Active Directory](#active-directory-powershell-script-method) of [handmatig](#manual-powershell-script-method) op elk apparaat en verzamel de resultaten in een bestand.</span><span class="sxs-lookup"><span data-stu-id="02f09-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="02f09-122">Start elk apparaat - maar voltooi de Windows-installatieervaring niet - en [verzamel de hashes op een verwisselbaar flashstation](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="02f09-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="02f09-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02f09-123">Configuration Manager</span></span>

<span data-ttu-id="02f09-124">U Microsoft Endpoint Configuration Manager gebruiken om de hardwarehashes te verzamelen van bestaande apparaten die u wilt registreren bij Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="02f09-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02f09-125">Alle apparaten waarvoor u deze informatie wilt krijgen, moeten Windows 10, versie 1703 of hoger hebben uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="02f09-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="02f09-126">U hebt ook een apparaat nodig dat een Configuratiebeheerclient is die is verbonden met de site Configuration Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="02f09-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="02f09-127">U hebt ook de rol Van het rapportagepuntsitesysteem in uw omgeving nodig met SQL Server Reporting Services ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="02f09-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="02f09-128">Als u aan al deze voorwaarden hebt voldaan, u de informatie verzamelen door de volgende stappen te volgen:</span><span class="sxs-lookup"><span data-stu-id="02f09-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="02f09-129">Selecteer In de console Configuratiebeheer de optie **Controle**.</span><span class="sxs-lookup"><span data-stu-id="02f09-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="02f09-130">Vouw **rapportage**uit in de werkruimte Controle en selecteer **vervolgens Rapporten**.</span><span class="sxs-lookup"><span data-stu-id="02f09-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="02f09-131">Selecteer **op** het tabblad Start in de sectie **Maken** de optie **Rapport maken** om de wizard Rapport maken te openen.</span><span class="sxs-lookup"><span data-stu-id="02f09-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="02f09-132">Stel **op** de pagina Informatie de volgende instellingen in:</span><span class="sxs-lookup"><span data-stu-id="02f09-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="02f09-133">**Naam:** Geef een naam op voor het rapport.</span><span class="sxs-lookup"><span data-stu-id="02f09-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="02f09-134">**Beschrijving:** Geef een beschrijving op voor het rapport.</span><span class="sxs-lookup"><span data-stu-id="02f09-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="02f09-135">**Server:** Hiermee geeft u de naam weer van de rapportserver waarop u dit rapport maakt.</span><span class="sxs-lookup"><span data-stu-id="02f09-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="02f09-136">**Pad:** Selecteer **Bladeren** om een map op te geven waarin u het rapport wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="02f09-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="02f09-137">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="02f09-137">Select **Next**.</span></span> 
6. <span data-ttu-id="02f09-138">Bekijk **op** de pagina Samenvatting de instellingen.</span><span class="sxs-lookup"><span data-stu-id="02f09-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="02f09-139">Selecteer **Vorige** om de instellingen te wijzigen of selecteer **Volgende** om het rapport in Configuratiebeheer te maken.</span><span class="sxs-lookup"><span data-stu-id="02f09-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="02f09-140">Selecteer **op** de pagina Voltooiing **sluiten** om de wizard af te sluiten en **open Rapportbouwer** om de rapportinstellingen in te voeren.</span><span class="sxs-lookup"><span data-stu-id="02f09-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="02f09-141">Voer uw gebruikersaccount en wachtwoord in als u daarom wordt gevraagd en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="02f09-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="02f09-142">Als Rapportbouwer niet op het apparaat is geïnstalleerd, wordt u gevraagd deze te installeren.</span><span class="sxs-lookup"><span data-stu-id="02f09-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="02f09-143">Selecteer **Uitvoeren om Rapportbouwer te installeren,** die nodig is om rapporten te wijzigen en te maken.</span><span class="sxs-lookup"><span data-stu-id="02f09-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="02f09-144">**Geef in Microsoft Report Builder**de SQL-instructie voor het rapport op en volg de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="02f09-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="02f09-145">Selecteer **gegevenssets**in het linkerdeelvenster en klik vervolgens met de rechtermuisknop op **Gegevensset toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="02f09-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="02f09-146">Ga naar het tabblad **Query** en voer de naam in als *DataSet0*.</span><span class="sxs-lookup"><span data-stu-id="02f09-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="02f09-147">Selecteer **Een gegevensset gebruiken die is ingesloten in mijn rapport;** Rapportbouwer wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="02f09-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="02f09-148">Selecteer **gegevensbron**in **Rapportbouwer:**.</span><span class="sxs-lookup"><span data-stu-id="02f09-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="02f09-149">Selecteer de standaardgegevensbron, die moet beginnen met 'AutoGen'.</span><span class="sxs-lookup"><span data-stu-id="02f09-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="02f09-150">Kies **Querytype als tekst**en voer deze query in:</span><span class="sxs-lookup"><span data-stu-id="02f09-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="02f09-151">Navigeer naar het tabblad **Veld,** wehre-waarden voor **veldnaam** en **veldbron** moeten al worden ingevuld.</span><span class="sxs-lookup"><span data-stu-id="02f09-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="02f09-152">Als dit niet het gaat, selecteert u **Toevoegen**en selecteert u **Queryveld**.</span><span class="sxs-lookup"><span data-stu-id="02f09-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="02f09-153">Voer de **veldnaam** en **veldbron in**.</span><span class="sxs-lookup"><span data-stu-id="02f09-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="02f09-154">Herhaal dit voor elk van deze waarden:</span><span class="sxs-lookup"><span data-stu-id="02f09-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="02f09-155">Fabrikant</span><span class="sxs-lookup"><span data-stu-id="02f09-155">Manufacturer</span></span> 
    - <span data-ttu-id="02f09-156">Model</span><span class="sxs-lookup"><span data-stu-id="02f09-156">Model</span></span> 
    - <span data-ttu-id="02f09-157">Serieel_getal</span><span class="sxs-lookup"><span data-stu-id="02f09-157">Serial_Number</span></span> 
    - <span data-ttu-id="02f09-158">HardwareHash</span><span class="sxs-lookup"><span data-stu-id="02f09-158">HardwareHash</span></span>
7. <span data-ttu-id="02f09-159">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="02f09-159">Select **OK**.</span></span>

<span data-ttu-id="02f09-160">**Definieer vervolgens de rapportweergave en maak het rapport** door de volgende stappen te volgen:</span><span class="sxs-lookup"><span data-stu-id="02f09-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="02f09-161">Selecteer **tabel of matrix**; een nieuwe wizard wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="02f09-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="02f09-162">Selecteer **in Een gegevensset**kiezen de optie **Een bestaande gegevensset kiezen in dit rapport of een gedeelde gegevensset**.</span><span class="sxs-lookup"><span data-stu-id="02f09-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="02f09-163">Selecteer **DataSet0** (de standaardinstelling) en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="02f09-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="02f09-164">Sleep **fabrikant,** **model**en **serienummer** naar het vak **Rijgroepen.**</span><span class="sxs-lookup"><span data-stu-id="02f09-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="02f09-165">Sleep **HardwareHash** naar het vak **Waarden** en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="02f09-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="02f09-166">Schakel de selectievakjes uit voor **Subtotalen en eindtotalen en** **Groepen Vouwen/samenvouwen**.</span><span class="sxs-lookup"><span data-stu-id="02f09-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="02f09-167">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="02f09-167">Select **Next**.</span></span>
6. <span data-ttu-id="02f09-168">Selecteer **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="02f09-168">Select **Finish**.</span></span>
7. <span data-ttu-id="02f09-169">Selecteer **Uitvoeren** om uw rapport uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="02f09-169">Select **Run** to run your report.</span></span> <span data-ttu-id="02f09-170">Controleer of het rapport de informatie bevat die u verwacht.</span><span class="sxs-lookup"><span data-stu-id="02f09-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="02f09-171">Selecteer indien nodig **Het ontwerp** om terug te keren naar de ontwerpweergave om het rapport te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="02f09-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="02f09-172">Selecteer **Opslaan** om het rapport op te slaan op de rapportserver.</span><span class="sxs-lookup"><span data-stu-id="02f09-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="02f09-173">U het nieuwe rapport uitvoeren in het knooppunt Rapporten in de werkruimte Bewaken.</span><span class="sxs-lookup"><span data-stu-id="02f09-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="02f09-174">**Ten slotte exporteert u het rapport en gebruikt u het om apparaten te registreren** door deze stappen te volgen.</span><span class="sxs-lookup"><span data-stu-id="02f09-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="02f09-175">(U hoeft alleen stappen 1 en 2 van deze sectie te volgen als u na de vorige stappen hebt weggevigerd.):</span><span class="sxs-lookup"><span data-stu-id="02f09-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="02f09-176">Selecteer In de console Configuratiebeheer de optie **Controle**.</span><span class="sxs-lookup"><span data-stu-id="02f09-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="02f09-177">Vouw **rapportage**uit in **Bewaking**en selecteer **vervolgens Rapporten**.</span><span class="sxs-lookup"><span data-stu-id="02f09-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="02f09-178">Zoek het rapport met de naam die u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="02f09-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="02f09-179">Klik met de rechtermuisknop op dit rapport en selecteer **Uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="02f09-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="02f09-180">Selecteer **exporteren** in het dialoogvenster dat wordt geopend en selecteer **Opslaan als CSV**.</span><span class="sxs-lookup"><span data-stu-id="02f09-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="02f09-181">In deze versie van het rapport worden hashes geëxtraheerd van alle Windows 10-apparaten waarmee Configuration Manager communiceert.</span><span class="sxs-lookup"><span data-stu-id="02f09-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="02f09-182">U moet de resultaten filteren op alleen die apparaten die u wilt registreren bij Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="02f09-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="02f09-183">Met de query in Configuratiebeheer staan geen spaties toe in geëxporteerde kolomnamen. Daarom heb je tijdens de stappen 'Serial_Number' en 'HardwareHash' ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="02f09-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="02f09-184">Nu u het geëxporteerde CSV-bestand hebt, moet u de rapportkoppen bewerken om *serienummer* en *hardwarehash* te lezen, zoals hier wordt weergegeven voordat u verdergaat met apparaatregistratie.</span><span class="sxs-lookup"><span data-stu-id="02f09-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="02f09-185">Nu u overgaan tot [apparaten registreren met behulp van de Admin Portal](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="02f09-185">Now you can proceed to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="02f09-186">Active Directory PowerShell-scriptmethode</span><span class="sxs-lookup"><span data-stu-id="02f09-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="02f09-187">In een Active Directory-omgeving u de `Get-MMDRegistrationInfo` PowerShell-cmdlet gebruiken om de informatie op afstand te verzamelen van apparaten in Active Directory Groups met Behulp van WinRM.</span><span class="sxs-lookup"><span data-stu-id="02f09-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="02f09-188">U de cmdlet ook gebruiken `Get-AD Computer` en gefilterde resultaten krijgen voor een specifieke hardwaremodelnamen die in de catalogus zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="02f09-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="02f09-189">Als u dit wilt doen, bevestigt u eerst deze vereisten en gaat u vervolgens verder met de stappen:</span><span class="sxs-lookup"><span data-stu-id="02f09-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="02f09-190">WinRM is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="02f09-190">WinRM is enabled.</span></span>
- <span data-ttu-id="02f09-191">De apparaten die u wilt registreren, zijn actief in het netwerk (dat wil zeggen dat ze niet zijn losgekoppeld of uitgeschakeld).</span><span class="sxs-lookup"><span data-stu-id="02f09-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="02f09-192">Zorg ervoor dat u een parameter voor domeinreferenties hebt die toestemming heeft om op afstand op de apparaten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="02f09-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="02f09-193">Zorg ervoor dat Windows Firewall toegang biedt tot WMI.</span><span class="sxs-lookup"><span data-stu-id="02f09-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="02f09-194">Voer hiervoor de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="02f09-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="02f09-195">Open het configuratiescherm van **Het Configuratiescherm** van Windows Defender Firewall en selecteer **Een app of functie toestaan via Windows Defender Firewall**.</span><span class="sxs-lookup"><span data-stu-id="02f09-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="02f09-196">Zoek **Windows Management Instrumentation (WMI)** in de lijst, schakel zowel privé als **openbaar**in en selecteer **vervolgens OK**.</span><span class="sxs-lookup"><span data-stu-id="02f09-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="02f09-197">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="02f09-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="02f09-198">Voer *een* van deze scripts uit:</span><span class="sxs-lookup"><span data-stu-id="02f09-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="02f09-199">Toegang tot alle mappen waar er mogelijk vermeldingen voor de apparaten.</span><span class="sxs-lookup"><span data-stu-id="02f09-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="02f09-200">Verwijder vermeldingen voor elk apparaat uit *alle* mappen, waaronder Windows Server Active Directory Domain Services en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="02f09-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="02f09-201">Wees ervan bewust dat deze verwijdering kan een paar uur duren om volledig te verwerken.</span><span class="sxs-lookup"><span data-stu-id="02f09-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="02f09-202">Toegangsbeheerservices waar mogelijk vermeldingen voor de apparaten zijn.</span><span class="sxs-lookup"><span data-stu-id="02f09-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="02f09-203">Verwijder vermeldingen voor elk apparaat uit *alle* beheerservices, waaronder Microsoft Endpoint Configuration Manager, Microsoft Intune en Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="02f09-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="02f09-204">Wees ervan bewust dat deze verwijdering kan een paar uur duren om volledig te verwerken.</span><span class="sxs-lookup"><span data-stu-id="02f09-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="02f09-205">Nu u overgaan tot [het registreren van apparaten.](#register-devices)</span><span class="sxs-lookup"><span data-stu-id="02f09-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="02f09-206">Handmatige PowerShell-scriptmethode</span><span class="sxs-lookup"><span data-stu-id="02f09-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="02f09-207">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="02f09-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="02f09-208">Uitvoeren`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="02f09-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="02f09-209">Uitvoeren`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="02f09-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="02f09-210">Voeg de hash-gegevens samen.</span><span class="sxs-lookup"><span data-stu-id="02f09-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="02f09-211">Flash-stationmethode</span><span class="sxs-lookup"><span data-stu-id="02f09-211">Flash drive method</span></span>

1. <span data-ttu-id="02f09-212">Plaats een ander apparaat dan het apparaat dat u registreert, een USB-station.</span><span class="sxs-lookup"><span data-stu-id="02f09-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="02f09-213">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="02f09-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="02f09-214">Uitvoeren`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="02f09-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="02f09-215">Schakel het apparaat in dat u registreert, maar *start de installatie-ervaring niet.*</span><span class="sxs-lookup"><span data-stu-id="02f09-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="02f09-216">Als u per ongeluk de installatie-ervaring start, moet u het apparaat opnieuw instellen of opnieuwimen.</span><span class="sxs-lookup"><span data-stu-id="02f09-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="02f09-217">Plaats het USB-station en druk op Shift + F10.</span><span class="sxs-lookup"><span data-stu-id="02f09-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="02f09-218">Open een PowerShell-prompt met beheerdersrechten en voer `cd <pathToUsb>` vervolgens uit .</span><span class="sxs-lookup"><span data-stu-id="02f09-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="02f09-219">Uitvoeren`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="02f09-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="02f09-220">Uitvoeren`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="02f09-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="02f09-221">Verwijder het USB-station en schakel het apparaat uit door`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="02f09-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="02f09-222">Voeg de hash-gegevens samen.</span><span class="sxs-lookup"><span data-stu-id="02f09-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="02f09-223">Geef het apparaat dat u opnieuw registreert niet weer aan totdat u de registratie ervoor hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="02f09-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="02f09-224">Hash-gegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="02f09-224">Merge hash data</span></span>

<span data-ttu-id="02f09-225">Als u de hardwarehashgegevens hebt verzameld via de handmatige PowerShell- of flashdrive-methoden, moet u de gegevens in de CSV-bestanden nu hebben gecombineerd in één bestand om de registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="02f09-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="02f09-226">Hier volgt een PowerShell-script om dit eenvoudig te maken:</span><span class="sxs-lookup"><span data-stu-id="02f09-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="02f09-227">Met de hash-gegevens samengevoegd in één CSV-bestand, u nu doorgaan met [het registreren van de apparaten.](#register-devices)</span><span class="sxs-lookup"><span data-stu-id="02f09-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="02f09-228">Apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="02f09-228">Register devices</span></span>

<span data-ttu-id="02f09-229">Het CSV-bestand moet in een bepaald formaat voor registratie staan.</span><span class="sxs-lookup"><span data-stu-id="02f09-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="02f09-230">Als u de gegevens zelf hebt verzameld in de vorige stappen, moet het bestand al in de juiste indeling zijn. als u het bestand bij een leverancier verkrijgt, moet u mogelijk het formaat aanpassen.</span><span class="sxs-lookup"><span data-stu-id="02f09-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="02f09-231">Voor uw gemak u een [sjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) voor dit CSV-bestand downloaden.</span><span class="sxs-lookup"><span data-stu-id="02f09-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="02f09-232">Uw bestand moet **exact dezelfde kolomkoppen** bevatten als de voorbeeldkoppen (fabrikant, model, enz.), maar uw eigen gegevens voor de andere rijen.</span><span class="sxs-lookup"><span data-stu-id="02f09-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="02f09-233">Als u de sjabloon gebruikt, opent u deze in een tekstbewerkingsgereedschap zoals Kladblok en u overwegen alle gegevens in rij 1 alleen te laten, waarbij alleen gegevens in rij 2 en lager worden invoeren.</span><span class="sxs-lookup"><span data-stu-id="02f09-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="02f09-234">Als u vergeet een van de voorbeeldgegevens te wijzigen, mislukt de registratie.</span><span class="sxs-lookup"><span data-stu-id="02f09-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="02f09-235">Apparaten registreren met behulp van de adminportal</span><span class="sxs-lookup"><span data-stu-id="02f09-235">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="02f09-236">Selecteer **Apparaten** in het linkernavigatiedeelvenster in de Microsoft Managed Desktop [Admin Portal.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="02f09-236">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="02f09-237">Selecteer **+ Apparaten registreren**; de fly-in opent:</span><span class="sxs-lookup"><span data-stu-id="02f09-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="02f09-238">[![Fly-in na het selecteren van Apparaten registreren, apparaten met kolommen voor toegewezen gebruikers, serienummer, status, laatst geziene datum en leeftijd vermelden](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="02f09-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Helaas is dit niet waar. We kunnen deze notitie verwijderen - maar laat het nu tot we een kans om te chatten over.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="02f09-240">Volg deze stappen:</span><span class="sxs-lookup"><span data-stu-id="02f09-240">Follow these steps:</span></span>

1. <span data-ttu-id="02f09-241">Geef in **Bestandsupload**een pad op naar het CSV-bestand dat u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="02f09-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="02f09-242">Optioneel u een **bestel-id** of **aankoop-id** toevoegen voor uw eigen trackingdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="02f09-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="02f09-243">Er zijn geen indelingsvereisten voor deze waarden.</span><span class="sxs-lookup"><span data-stu-id="02f09-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="02f09-244">Selecteer **Apparaten registreren**.</span><span class="sxs-lookup"><span data-stu-id="02f09-244">Select **Register devices**.</span></span> <span data-ttu-id="02f09-245">Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad,** gemarkeerd als **Registratie in behandeling.**</span><span class="sxs-lookup"><span data-stu-id="02f09-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="02f09-246">Registratie duurt meestal minder dan 10 minuten, en wanneer het apparaat succesvol is, wordt weergegeven als **Klaar voor de gebruiker,** wat betekent dat het klaar is en wacht tot een eindgebruiker begint te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="02f09-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="02f09-247">U de voortgang van apparaatregistratie volgen op de hoofdpagina **van Microsoft Managed Desktop - Devices.**</span><span class="sxs-lookup"><span data-stu-id="02f09-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="02f09-248">Mogelijke staten gemeld zijn er:</span><span class="sxs-lookup"><span data-stu-id="02f09-248">Possible states reported there include:</span></span>

| <span data-ttu-id="02f09-249">Status</span><span class="sxs-lookup"><span data-stu-id="02f09-249">State</span></span> | <span data-ttu-id="02f09-250">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="02f09-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="02f09-251">Inschrijving in behandeling</span><span class="sxs-lookup"><span data-stu-id="02f09-251">Registration pending</span></span> | <span data-ttu-id="02f09-252">Registratie is nog niet gedaan.</span><span class="sxs-lookup"><span data-stu-id="02f09-252">Registration is not done yet.</span></span> <span data-ttu-id="02f09-253">Kom later terug.</span><span class="sxs-lookup"><span data-stu-id="02f09-253">Check back later.</span></span> |
| <span data-ttu-id="02f09-254">Registratie is mislukt</span><span class="sxs-lookup"><span data-stu-id="02f09-254">Registration failed</span></span> | <span data-ttu-id="02f09-255">De inschrijving kon niet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="02f09-255">Registration could not be completed.</span></span> <span data-ttu-id="02f09-256">Raadpleeg [de registratie van het apparaat voor probleemoplossing](#troubleshooting-device-registration) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="02f09-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="02f09-257">Klaar voor de gebruiker</span><span class="sxs-lookup"><span data-stu-id="02f09-257">Ready for user</span></span> | <span data-ttu-id="02f09-258">De registratie is geslaagd en het apparaat is nu klaar om te worden geleverd aan de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="02f09-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="02f09-259">Microsoft Managed Desktop begeleidt ze door de eerste tijdset-up, dus u hoeft geen verdere voorbereidingen te treffen.</span><span class="sxs-lookup"><span data-stu-id="02f09-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="02f09-260">Actief</span><span class="sxs-lookup"><span data-stu-id="02f09-260">Active</span></span> | <span data-ttu-id="02f09-261">Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="02f09-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="02f09-262">Dit geeft ook aan dat ze het apparaat regelmatig gebruiken.</span><span class="sxs-lookup"><span data-stu-id="02f09-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="02f09-263">Inactief</span><span class="sxs-lookup"><span data-stu-id="02f09-263">Inactive</span></span> | <span data-ttu-id="02f09-264">Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="02f09-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="02f09-265">Ze hebben het apparaat echter niet onlangs (in de afgelopen 7 dagen) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="02f09-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="02f09-266">Apparaatregistratie oplossen</span><span class="sxs-lookup"><span data-stu-id="02f09-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="02f09-267">Foutbericht</span><span class="sxs-lookup"><span data-stu-id="02f09-267">Error message</span></span> | <span data-ttu-id="02f09-268">Details</span><span class="sxs-lookup"><span data-stu-id="02f09-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="02f09-269">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="02f09-269">Device not found</span></span> | <span data-ttu-id="02f09-270">We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de geleverde fabrikant, het model of het serienummer.</span><span class="sxs-lookup"><span data-stu-id="02f09-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="02f09-271">Bevestig deze waarden met uw apparaatleverancier.</span><span class="sxs-lookup"><span data-stu-id="02f09-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="02f09-272">Hardware hash niet geldig</span><span class="sxs-lookup"><span data-stu-id="02f09-272">Hardware hash not valid</span></span> | <span data-ttu-id="02f09-273">De hardwarehash die u voor dit apparaat hebt geleverd, is niet correct opgemaakt.</span><span class="sxs-lookup"><span data-stu-id="02f09-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="02f09-274">Controleer de hardware hash en vervolgens opnieuw in te dienen.</span><span class="sxs-lookup"><span data-stu-id="02f09-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="02f09-275">Apparaat al geregistreerd</span><span class="sxs-lookup"><span data-stu-id="02f09-275">Device already registered</span></span> | <span data-ttu-id="02f09-276">Dit apparaat is al geregistreerd bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="02f09-276">This device is already registered to your organization.</span></span> <span data-ttu-id="02f09-277">Geen verdere actie vereist.</span><span class="sxs-lookup"><span data-stu-id="02f09-277">No further action required.</span></span> |
| <span data-ttu-id="02f09-278">Apparaat geclaimd door een andere organisatie</span><span class="sxs-lookup"><span data-stu-id="02f09-278">Device claimed by another organization</span></span> | <span data-ttu-id="02f09-279">Dit apparaat is al geclaimd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="02f09-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="02f09-280">Neem contact op met uw apparaatleverancier.</span><span class="sxs-lookup"><span data-stu-id="02f09-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="02f09-281">Onverwachte fout</span><span class="sxs-lookup"><span data-stu-id="02f09-281">Unexpected error</span></span> | <span data-ttu-id="02f09-282">Uw aanvraag kan niet automatisch worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="02f09-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="02f09-283">Neem contact op met de ondersteuning en geef de aanvraag-id op:<requestId></span><span class="sxs-lookup"><span data-stu-id="02f09-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="02f09-284">De afbeelding controleren</span><span class="sxs-lookup"><span data-stu-id="02f09-284">Check the image</span></span>

<span data-ttu-id="02f09-285">Als uw apparaat afkomstig is van een microsoft managed desktop-partnerleverancier, moet de afbeelding correct zijn.</span><span class="sxs-lookup"><span data-stu-id="02f09-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="02f09-286">U bent ook van harte welkom om de afbeelding toe te passen op uw eigen als u dat liever.</span><span class="sxs-lookup"><span data-stu-id="02f09-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="02f09-287">Neem voor u contact op met de Microsoft-vertegenwoordiger waarmee u werkt en deze biedt u de locatie en stappen voor het toepassen van de afbeelding.</span><span class="sxs-lookup"><span data-stu-id="02f09-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="02f09-288">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="02f09-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02f09-289">Voordat u het apparaat aan uw gebruiker overhandigt, moet u ervoor zorgen dat u de [juiste licenties](../get-ready/prerequisites.md) voor die gebruiker hebt verkregen en toegepast.</span><span class="sxs-lookup"><span data-stu-id="02f09-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="02f09-290">Als alle licenties worden toegepast, u [uw gebruikers klaar maken om apparaten te gebruiken,](get-started-devices.md)en vervolgens kan uw gebruiker het apparaat opstarten en doorgaan met de Windows-installatieervaring.</span><span class="sxs-lookup"><span data-stu-id="02f09-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









