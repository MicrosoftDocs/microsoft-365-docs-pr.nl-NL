---
title: Migratiestappen voor AD FS voor de migratie van Microsoft Cloud Deutschland
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
description: 'Overzicht: migratiestappen voor Active Directory Federation Services (AD FS) voor de migratie van Microsoft Cloud Deutschland.'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688663"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="62aa2-103">Migratiestappen voor AD FS voor de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="62aa2-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="62aa2-104">U kunt als volgt uw AD FS-Farm (Active Directory Federation Services) migreren van Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="62aa2-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="62aa2-105">U kunt een back-up maken van uw AD FS-instellingen, inclusief [de](#backup)geschiedenis van de FF-gegevens.</span><span class="sxs-lookup"><span data-stu-id="62aa2-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="62aa2-106">Naam van de back-up **Microsoft cloud Deutschland_Only** om aan te geven dat alleen de Microsoft Cloud Deutschland-Tenant gegevens bevat.</span><span class="sxs-lookup"><span data-stu-id="62aa2-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="62aa2-107">Het herstel testen met de back-up van Microsoft Cloud Deutschland_Only de AD FS-farm moet blijven werken als Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="62aa2-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="62aa2-108">Maak een nieuwe vertrouwensrelatie van een vertrouwens partij van **AD FS > Office 365-Services**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="62aa2-109">Selecteer in de console voor het vertrouwen van **partijen vertrouwensrelaties** in de beheerconsole van een **vertrouwensrelatie de optie vertrouwensrelaties** van partijen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="62aa2-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="62aa2-110">Selecteer **volgende** op de **welkomst** pagina van de wizard vertrouwen van een vertrouwensrelatie toevoegen.</span><span class="sxs-lookup"><span data-stu-id="62aa2-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="62aa2-111">Selecteer op de pagina **gegevensbron selecteren** de optie **gegevens importeren over de uitgenodigde partij die online is gepubliceerd of op een lokaal netwerk**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="62aa2-112">Het **adres van de Federatie metagegevens (host name of URL)** is ingesteld op `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="62aa2-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="62aa2-113">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-113">Click **Next**.</span></span>
7. <span data-ttu-id="62aa2-114">Typ op de pagina **gegevensbron selecteren** de naam van de weergave.</span><span class="sxs-lookup"><span data-stu-id="62aa2-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="62aa2-115">Microsoft adviseert Microsoft **Office 365 Identity platform wereldwijd**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="62aa2-116">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-116">Click **Next**.</span></span>
8. <span data-ttu-id="62aa2-117">Klik op **volgende** op de optie **multi-factor Authentication nu configureren?**, **Kies autorisatieregels voor uitgifte** en **klaar om vertrouwende pagina's toe te voegen** .</span><span class="sxs-lookup"><span data-stu-id="62aa2-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="62aa2-118">Klik op de pagina **Voltooien** op **sluiten** .</span><span class="sxs-lookup"><span data-stu-id="62aa2-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="62aa2-119">Door de wizard te sluiten, wordt de vertrouwensrelatie tussen de Relying Party en de Office 365-Services eSTS vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="62aa2-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="62aa2-120">Er worden echter geen regels voor de uitgifte transformatie gemaakt.</span><span class="sxs-lookup"><span data-stu-id="62aa2-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="62aa2-121">U kunt de [Help van AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) gebruiken om de juiste regels voor de uitgifte transformatie te genereren.</span><span class="sxs-lookup"><span data-stu-id="62aa2-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="62aa2-122">De gegenereerde claimregels die zijn gemaakt met de Help voor AD FS, kunnen handmatig worden toegevoegd via de beheerconsole van AD FS of met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62aa2-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="62aa2-123">In de Help van AD FS worden de benodigde PowerShell-scripts gegenereerd die moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="62aa2-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="62aa2-124">Voer **claims genereren** in de Help van AD FS uit en kopieer het PowerShell-transformatie-transformatie met de optie **kopiëren** in de rechterbovenhoek van het script.</span><span class="sxs-lookup"><span data-stu-id="62aa2-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="62aa2-125">Plak de gegenereerde PowerShell in de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="62aa2-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="62aa2-126">Voer het voltooide script uit.</span><span class="sxs-lookup"><span data-stu-id="62aa2-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="62aa2-127">Controleer of de twee vertrouwensrelaties van de Relying Party aanwezig zijn; een voor wereldwijd en een voor BF.</span><span class="sxs-lookup"><span data-stu-id="62aa2-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="62aa2-128">Maak een back-up van uw vertrouwensrelaties met de [volgende stappen](#backup).</span><span class="sxs-lookup"><span data-stu-id="62aa2-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="62aa2-129">Sla het bestand op onder de naam **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="62aa2-130">Voltooi de back-up van de backend en controleer of AD FS nog steeds werkt tijdens het migratieproces.</span><span class="sxs-lookup"><span data-stu-id="62aa2-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="62aa2-131">Noodherstel voor AD FS (WID-database)</span><span class="sxs-lookup"><span data-stu-id="62aa2-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="62aa2-132">Als u de AD FS-farm wilt herstellen in een noodherstel programma voor de snelle oplossing van [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) , moet u gebruikmaken van de oplossing.</span><span class="sxs-lookup"><span data-stu-id="62aa2-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="62aa2-133">Daarom moet u het hulpmiddel downloaden en voordat u de migratie start, moet u eerst een back-up maken en deze veilig opslaan.</span><span class="sxs-lookup"><span data-stu-id="62aa2-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="62aa2-134">In dit voorbeeld (TAT-omgevingen) zijn de volgende opdrachten uitgevoerd voor het maken van een back-up van de farm:</span><span class="sxs-lookup"><span data-stu-id="62aa2-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="62aa2-135">Een back-up maken van een AD FS-Farm</span><span class="sxs-lookup"><span data-stu-id="62aa2-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="62aa2-136">Installeer het hulpprogramma voor het snel herstellen van AD FS op de primaire AD FS-server.</span><span class="sxs-lookup"><span data-stu-id="62aa2-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="62aa2-137">Importeer de module in een PowerShell-sessie met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="62aa2-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="62aa2-138">Voer de opdracht back-up uit:</span><span class="sxs-lookup"><span data-stu-id="62aa2-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="62aa2-139">Sla de back-up op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="62aa2-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="62aa2-140">Een AD FS-Farm herstellen</span><span class="sxs-lookup"><span data-stu-id="62aa2-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="62aa2-141">Ga als volgt te werk als uw farm niet volledig is gelukt en u geen manier kunt teruggaan naar de oude farm.</span><span class="sxs-lookup"><span data-stu-id="62aa2-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="62aa2-142">Verplaats de eerder gegenereerde en opgeslagen back-up naar de nieuwe primaire AD FS-server.</span><span class="sxs-lookup"><span data-stu-id="62aa2-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="62aa2-143">Voer de volgende `Restore-ADFS` PowerShell-opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="62aa2-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="62aa2-144">Importeer indien nodig het AD FS SSL-certificaat vooraf.</span><span class="sxs-lookup"><span data-stu-id="62aa2-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="62aa2-145">Plaats uw nieuwe DNS-records of Load Balancer naar de nieuwe AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="62aa2-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="62aa2-146">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="62aa2-146">More information</span></span>

<span data-ttu-id="62aa2-147">Aan de slag:</span><span class="sxs-lookup"><span data-stu-id="62aa2-147">Getting started:</span></span>

- [<span data-ttu-id="62aa2-148">Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden</span><span class="sxs-lookup"><span data-stu-id="62aa2-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="62aa2-149">Migratie ondersteuning voor Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="62aa2-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="62aa2-150">Hoe kan ik me aanmelden voor migratie?</span><span class="sxs-lookup"><span data-stu-id="62aa2-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="62aa2-151">Gebruikerservaring tijdens de migratie</span><span class="sxs-lookup"><span data-stu-id="62aa2-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="62aa2-152">Door de overgang navigeren:</span><span class="sxs-lookup"><span data-stu-id="62aa2-152">Moving through the transition:</span></span>

- [<span data-ttu-id="62aa2-153">Acties en effecten voor de migratiefasen</span><span class="sxs-lookup"><span data-stu-id="62aa2-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="62aa2-154">Extra vooraf werken</span><span class="sxs-lookup"><span data-stu-id="62aa2-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="62aa2-155">Aanvullende informatie over [Azure AD](ms-cloud-germany-transition-azure-ad.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="62aa2-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="62aa2-156">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="62aa2-156">Cloud apps:</span></span>

- [<span data-ttu-id="62aa2-157">Dynamics 365-migratieprogramma gegevens</span><span class="sxs-lookup"><span data-stu-id="62aa2-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="62aa2-158">Informatie over migratieprogramma's voor Power BI</span><span class="sxs-lookup"><span data-stu-id="62aa2-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="62aa2-159">Aan de slag met uw upgrade naar Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="62aa2-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
