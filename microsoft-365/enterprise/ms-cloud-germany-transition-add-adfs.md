---
title: AD FS-migratiestappen voor de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Overzicht: Ad FS-migratiestappen (Active Directory Federation Services) voor de migratie vanuit Microsoft Cloud Deutschland.'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727465"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="90489-103">AD FS-migratiestappen voor de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="90489-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="90489-104">Deze configuratiewijziging kan op elk moment worden toegepast voordat fase 4 begint.</span><span class="sxs-lookup"><span data-stu-id="90489-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="90489-105">Wanneer fase 2 is voltooid, werkt de configuratiewijziging en kunt u zich aanmelden bij globale eindpunten van Office 365, zoals `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="90489-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="90489-106">Als u de configuratiewijziging implementeert vóór fase 2, werken  de globale eindpunten van Office 365 nog niet, maar maakt het vertrouwen van de nieuwe vertrouwensrelatie van de vertrouwenspartij nog steeds deel uit van uw AD FS-configuratie (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="90489-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="90489-107">Als u uw AD FS-farm wilt migreren vanuit Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="90489-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="90489-108">Met deze stappen maakt u een back-up van uw AD FS-instellingen, inclusief [FF-vertrouwensgegevens.](#backup)</span><span class="sxs-lookup"><span data-stu-id="90489-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="90489-109">Geef de back-up **van Microsoft Cloud Deutschland_Only** om aan te geven dat deze alleen de tenantgegevens van Microsoft Cloud Deutschland heeft.</span><span class="sxs-lookup"><span data-stu-id="90489-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="90489-110">Test het herstellen met behulp van de Microsoft Cloud Deutschland_Only back-up, de AD FS-farm moet alleen blijven werken als Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="90489-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="90489-111">Nadat u de AD FS-back-up hebt voltooid en getest, voert u de volgende stappen uit om een nieuwe vertrouwensrelatie van een vertrouwenspartij toe te voegen aan uw ADFS-configuratie:</span><span class="sxs-lookup"><span data-stu-id="90489-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="90489-112">De AD FS-beheerconsole openen</span><span class="sxs-lookup"><span data-stu-id="90489-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="90489-113">Vouw in het linkerdeelvenster van de ADFS-beheerconsole **ADFS** uit, vervolgens **Vertrouwensrelaties** en **vertrouwensrelaties van afhankelijke partijen**</span><span class="sxs-lookup"><span data-stu-id="90489-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="90489-114">Selecteer in het rechterdeelvenster **Vertrouwen van afhankelijke partij toevoegen...**</span><span class="sxs-lookup"><span data-stu-id="90489-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="90489-115">Selecteer **Volgende** op de **welkomstpagina** van de wizard Vertrouwen van afhankelijke partijen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="90489-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="90489-116">Selecteer op **de pagina Gegevensbron** selecteren de optie Gegevens importeren over de afhankelijke partij die online of **op een lokaal netwerk is gepubliceerd.**</span><span class="sxs-lookup"><span data-stu-id="90489-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="90489-117">De **waarde federatie metagegevens (hostnaam of URL)** moet zijn ingesteld op `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="90489-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="90489-118">Klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="90489-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="90489-119">Typ op **de pagina Gegevensbron** selecteren de weergavenaam zoals **Microsoft Office 365 Identity Platform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="90489-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="90489-120">Klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="90489-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="90489-121">Selecteer op de wizardpagina **Meervoudige verificatie nu configureren?** de juiste keuze op basis van uw verificatievereisten.</span><span class="sxs-lookup"><span data-stu-id="90489-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="90489-122">Als u zich aan de standaardinstelling houdt, selecteert u Ik wil op dit moment geen instellingen voor meervoudige verificatie configureren voor dit vertrouwen van afhankelijke **partijen.**</span><span class="sxs-lookup"><span data-stu-id="90489-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="90489-123">U kunt deze instelling later wijzigen als u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="90489-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="90489-124">Houd in **de kies autorisatieregels** voor uitgifte toestaan dat alle gebruikers toegang hebben tot deze **afhankelijke partij** geselecteerd op **Volgende**</span><span class="sxs-lookup"><span data-stu-id="90489-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="90489-125">Klik **op Volgende** op de pagina Vertrouwen **toevoegen** om de wizard te voltooien.</span><span class="sxs-lookup"><span data-stu-id="90489-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="90489-126">Klik **op Sluiten** op de **pagina** Voltooien.</span><span class="sxs-lookup"><span data-stu-id="90489-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="90489-127">Door de wizard te sluiten, wordt het vertrouwen van afhankelijke partijen met de globale Office 365-services ingesteld.</span><span class="sxs-lookup"><span data-stu-id="90489-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="90489-128">Er zijn echter nog geen regels voor uitgiftetransformator geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="90489-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="90489-129">U kunt [AD FS Help gebruiken om](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) de juiste regels voor uitgiftetransformator te genereren.</span><span class="sxs-lookup"><span data-stu-id="90489-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="90489-130">De gegenereerde claimregels die zijn gemaakt met AD FS Help, kunnen handmatig worden toegevoegd via de AD FS-beheerconsole of met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90489-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="90489-131">Ad FS Help genereert de benodigde PowerShell-scripts die moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="90489-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="90489-132">Voer **help bij het** genereren van claims op AD  FS uit en kopieer het PowerShell-claimtransformatiescript met de optie Kopiëren in de rechterbovenhoek van het script.</span><span class="sxs-lookup"><span data-stu-id="90489-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="90489-133">Open de gewenste teksteditor en plak het PowerShell-script in een nieuw tekstvenster.</span><span class="sxs-lookup"><span data-stu-id="90489-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="90489-134">De volgende PowerShell-regels toevoegen aan het einde van het geperste script uit stap 2</span><span class="sxs-lookup"><span data-stu-id="90489-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="90489-135">Het PowerShell-script veilig en uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="90489-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="90489-136">Controleer of er twee vertrouwensrelaties van relying party aanwezig zijn. een voor de Microsoft Cloud Deutschland en een voor de Globale Office 365-service.</span><span class="sxs-lookup"><span data-stu-id="90489-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="90489-137">Back-up maken van uw [vertrouwensrelatie met behulp van deze stappen.](#backup)</span><span class="sxs-lookup"><span data-stu-id="90489-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="90489-138">Sla het op met de naam **FFAndWorldwide.**</span><span class="sxs-lookup"><span data-stu-id="90489-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="90489-139">Voltooi de backend-migratie en controleer of AD FS nog steeds werkt tijdens het migratieproces.</span><span class="sxs-lookup"><span data-stu-id="90489-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="90489-140">AD FS Disaster Recovery (WID Database)</span><span class="sxs-lookup"><span data-stu-id="90489-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="90489-141">Als u de AD FS-farm wilt herstellen in een [ramp, moet ad FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="90489-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="90489-142">Daarom moet het hulpprogramma worden gedownload en moet vóór het begin van de migratie een back-up worden gemaakt en veilig worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="90489-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="90489-143">In dit voorbeeld (TAT-omgevingen) zijn de volgende opdrachten uitgevoerd om een back-up van de farm te maken:</span><span class="sxs-lookup"><span data-stu-id="90489-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="90489-144">Een back-up maken van een AD FS-farm</span><span class="sxs-lookup"><span data-stu-id="90489-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="90489-145">Installeer het HULPPROGRAMMA VOOR SNEL HERSTELLEN AD FS op de primaire AD FS-server.</span><span class="sxs-lookup"><span data-stu-id="90489-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="90489-146">Importeer de module in een PowerShell-sessie met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="90489-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="90489-147">Voer de back-upopdracht uit:</span><span class="sxs-lookup"><span data-stu-id="90489-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="90489-148">Sla de back-up veilig op een gewenste bestemming op.</span><span class="sxs-lookup"><span data-stu-id="90489-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="90489-149">Een AD FS-farm herstellen</span><span class="sxs-lookup"><span data-stu-id="90489-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="90489-150">Als uw farm volledig is mislukt en er geen manier is om terug te keren naar de oude farm, gaat u als volgt te werk.</span><span class="sxs-lookup"><span data-stu-id="90489-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="90489-151">Verplaats de eerder gegenereerde en opgeslagen back-up naar de nieuwe primaire AD FS-server.</span><span class="sxs-lookup"><span data-stu-id="90489-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="90489-152">Voer de volgende `Restore-ADFS` PowerShell-opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="90489-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="90489-153">Importeer zo nodig het AD FS SSL-certificaat vooraf.</span><span class="sxs-lookup"><span data-stu-id="90489-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="90489-154">Wijs uw nieuwe DNS-records of load balancer naar de nieuwe AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="90489-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="90489-155">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="90489-155">More information</span></span>

<span data-ttu-id="90489-156">Aan de slag:</span><span class="sxs-lookup"><span data-stu-id="90489-156">Getting started:</span></span>

- [<span data-ttu-id="90489-157">Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's</span><span class="sxs-lookup"><span data-stu-id="90489-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="90489-158">Microsoft Cloud Deutschland-migratiehulp</span><span class="sxs-lookup"><span data-stu-id="90489-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="90489-159">Opt-in voor migratie</span><span class="sxs-lookup"><span data-stu-id="90489-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="90489-160">Klantervaring tijdens de migratie</span><span class="sxs-lookup"><span data-stu-id="90489-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="90489-161">Door de overgang lopen:</span><span class="sxs-lookup"><span data-stu-id="90489-161">Moving through the transition:</span></span>

- [<span data-ttu-id="90489-162">Acties en effecten voor de migratiefasen</span><span class="sxs-lookup"><span data-stu-id="90489-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="90489-163">Extra pre-work</span><span class="sxs-lookup"><span data-stu-id="90489-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="90489-164">Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="90489-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="90489-165">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="90489-165">Cloud apps:</span></span>

- [<span data-ttu-id="90489-166">Dynamics 365-migratieprogrammagegevens</span><span class="sxs-lookup"><span data-stu-id="90489-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="90489-167">Informatie over power bi-migratieprogramma's</span><span class="sxs-lookup"><span data-stu-id="90489-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="90489-168">Aan de slag met uw Microsoft Teams-upgrade</span><span class="sxs-lookup"><span data-stu-id="90489-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
