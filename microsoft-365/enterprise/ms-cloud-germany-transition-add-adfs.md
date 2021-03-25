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
ms.openlocfilehash: 12465acf5b4afe7e252586ddd076250628b57dd3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165655"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="9c8ed-103">AD FS-migratiestappen voor de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="9c8ed-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="9c8ed-104">Deze configuratiewijziging moet op elk moment worden toegepast voordat fase 2 begint.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="9c8ed-105">Wanneer fase 2 is voltooid, werkt de configuratiewijziging en kunt u zich aanmelden via globale eindpunten van Office 365, zoals `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="9c8ed-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="9c8ed-106">Als u de configuratiewijziging implementeert vóór fase 2, werken  de globale eindpunten van Office 365 nog niet, maar maakt het vertrouwen van de nieuwe vertrouwensrelatie van de vertrouwenspartij nog steeds deel uit van uw AD FS-configuratie (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="9c8ed-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="9c8ed-107">Klanten die federatieverificatie met AD FS (Active Directory Federation Services) gebruiken, mogen tijdens de migratie geen wijzigingen aanbrengen in url's van uitgevende gebruikers die worden gebruikt voor alle verificaties met on-premises Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="9c8ed-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="9c8ed-108">Als u url's voor uitgevende gebruikers verandert, kan dit leiden tot verificatiefouten voor gebruikers in het domein.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="9c8ed-109">Url's voor uitgevende uitgevende uri's kunnen  rechtstreeks worden gewijzigd in AD FS of wanneer een domein wordt geconverteerd van beheerd naar _federatief_ en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="9c8ed-110">U wordt aangeraden een federatief domein niet toe te voegen, te verwijderen of te converteren in de Azure AD-tenant die is gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="9c8ed-111">U kunt URL's voor uitgevende uri's wijzigen nadat de migratie volledig is voltooid.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="9c8ed-112">Voer de volgende stappen uit om uw AD FS-farm voor te bereiden op de migratie van Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="9c8ed-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="9c8ed-113">Een back-up maken van uw AD FS-instellingen, inclusief het bestaande vertrouwen van Microsoft Cloud Deutschland Relying Party, met [deze stappen.](#backup)</span><span class="sxs-lookup"><span data-stu-id="9c8ed-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="9c8ed-114">Geef de back-up **van MicrosoftCloudDeutschlandOnly een** naam om aan te geven dat alleen de tenantgegevens van Microsoft Cloud Deutschland beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9c8ed-115">De back-up bevat niet alleen de bestaande Vertrouwensrelatie van Office 365 Relying Party voor Microsoft Cloud Deutschland, maar ook alle andere Vertrouwensrelatie voor afhankelijke partijen die aanwezig zijn op de betreffende AD FS-farm.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="9c8ed-116">Test het herstel met behulp van de MicrosoftCloudDeutschlandOnly-back-up, de AD FS-farm moet alleen blijven werken als Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="9c8ed-117">Nadat u de AD FS-back-up hebt voltooid en getest, voert u de volgende stappen uit om een nieuwe vertrouwensrelatie van een vertrouwenspartij toe te voegen aan uw ADFS-configuratie:</span><span class="sxs-lookup"><span data-stu-id="9c8ed-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="9c8ed-118">Open de AD FS-beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="9c8ed-119">Ga in het linkerdeelvenster van de ADFS-beheerconsole naar het menu **Vertrouwensrelatie van relying party.**</span><span class="sxs-lookup"><span data-stu-id="9c8ed-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="9c8ed-120">Selecteer in het rechterdeelvenster **Vertrouwen van afhankelijke partij toevoegen...**</span><span class="sxs-lookup"><span data-stu-id="9c8ed-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="9c8ed-121">Selecteer **Start** op de **welkomstpagina** van de wizard Vertrouwen van afhankelijke partijen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="9c8ed-122">Selecteer op **de pagina Gegevensbron** selecteren de optie Gegevens importeren over de afhankelijke partij die online of **op een lokaal netwerk is gepubliceerd.**</span><span class="sxs-lookup"><span data-stu-id="9c8ed-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="9c8ed-123">De **waarde federatie metagegevens (hostnaam of URL)** moet zijn ingesteld op `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="9c8ed-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="9c8ed-124">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-124">Click **Next**.</span></span>

6. <span data-ttu-id="9c8ed-125">Typ op **de pagina Weergavenaam** opgeven de weergavenaam zoals **Microsoft Office 365 Identity Platform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="9c8ed-126">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-126">Click **Next**.</span></span>

7. <span data-ttu-id="9c8ed-127">Als u ADFS gebruikt in Windows Server 2012, selecteert u op de wizardpagina Meervoudige verificatie **nu configureren?** de juiste keuze op basis van uw verificatievereisten.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="9c8ed-128">Als u zich aan de standaardinstelling houdt, selecteert u Ik wil op dit moment geen instellingen voor meervoudige verificatie configureren voor dit vertrouwen van afhankelijke **partijen.**</span><span class="sxs-lookup"><span data-stu-id="9c8ed-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="9c8ed-129">U kunt deze instelling later wijzigen als u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="9c8ed-130">Voor AD FS 2012: In de autorisatieregels voor uitgifte kiezen blijven alle gebruikers toegang verlenen tot deze afhankelijke **partij** geselecteerd en klikt u op **Volgende.** </span><span class="sxs-lookup"><span data-stu-id="9c8ed-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

9. <span data-ttu-id="9c8ed-131">Voor AD FS 2016 en AD FS 2019: Selecteer op de pagina **Beleid** voor toegangsbeheer kiezen het juiste toegangsbeleid en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="9c8ed-132">Als er geen is gekozen, werkt het vertrouwen van de afhankelijke partij **NIET.**</span><span class="sxs-lookup"><span data-stu-id="9c8ed-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

10. <span data-ttu-id="9c8ed-133">Klik **op Volgende** op de pagina Vertrouwen **toevoegen** om de wizard te voltooien.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

11. <span data-ttu-id="9c8ed-134">Klik **op Sluiten** op de **pagina** Voltooien.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="9c8ed-135">Als u de wizard sluit, wordt de vertrouwensrelatie van relying party met de globale office 365-service ingesteld.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="9c8ed-136">Er zijn echter nog geen regels voor uitgiftetransformator geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="9c8ed-137">U kunt [AD FS Help gebruiken om](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) de juiste regels voor uitgiftetransformator te genereren.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="9c8ed-138">De gegenereerde claimregels die zijn gemaakt met AD FS Help, kunnen handmatig worden toegevoegd via de AD FS-beheerconsole of met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="9c8ed-139">Ad FS Help genereert de benodigde PowerShell-scripts die moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="9c8ed-140">[Ad FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) genereert de standaarduitgiftetransformatorregels die worden geleverd met het product.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="9c8ed-141">Als er echter aangepaste uitgiftetransformatorregels worden gebruikt in het vertrouwen van een vertrouwenspersoon in Microsoft Cloud Deutschland (bijvoorbeeld aangepaste URL's van uitgevende uitgevende e-mail, niet-standaardinmuteerbare ID's of andere aanpassingen), moeten de regels die door AD FS-help worden gegenereerd, worden gewijzigd op een manier die past bij de aangepaste logica die momenteel wordt gebruikt voor het vertrouwen van de vertrouwensrelatie van de vertrouwensrelatie van de microsoft Cloud Deutschland-afhankelijke partij.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="9c8ed-142">Als deze aanpassingen niet zijn geïntegreerd in de regels die worden gegenereerd via [AD FS Help,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)werkt verificatie naar **Microsoft Office 365 Identity Platform WorldWide** waarschijnlijk niet voor uw federatief identiteiten. </span><span class="sxs-lookup"><span data-stu-id="9c8ed-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="9c8ed-143">Voer **De Help Voor** het genereren van claims  op [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) uit en kopieer het PowerShell-script met de optie Kopiëren in de rechterbovenhoek van het script.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="9c8ed-144">Volg de stappen die worden beschreven bij [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) over het uitvoeren van het PowerShell-script in uw AD FS-farm om het globale vertrouwen van afhankelijke partijen te genereren.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span> <span data-ttu-id="9c8ed-145">Voordat u het script gaat uitvoeren, vervangt u de volgende coderegels in het gegenereerde script, zoals hieronder wordt beschreven:</span><span class="sxs-lookup"><span data-stu-id="9c8ed-145">Before you run the script, replace the following code lines in the generated script as outlined below:</span></span>

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. <span data-ttu-id="9c8ed-146">Controleer of er twee Relying PartyTtrusts aanwezig zijn. een voor Microsoft Cloud Deutschland en een voor de Globale Office 365-service.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-146">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="9c8ed-147">De volgende opdracht kan worden gebruikt voor de controle.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-147">The following command can be leveraged for the check.</span></span> <span data-ttu-id="9c8ed-148">Het moet twee rijen en de respectievelijke namen en id's retourneren.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-148">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="9c8ed-149">Gebruik deze stappen om een back-up te maken van uw volledige migratieconfiguratie, inclusief beide vertrouwensrelatie van Relying [Party.](#backup)</span><span class="sxs-lookup"><span data-stu-id="9c8ed-149">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="9c8ed-150">Sla het op met de naam **MicrosoftCloudDeutschlandAndWorldwide.**</span><span class="sxs-lookup"><span data-stu-id="9c8ed-150">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="9c8ed-151">Terwijl uw tenant bezig is met migratie, controleert u regelmatig of AD FS-verificatie werkt met Microsoft Cloud Deutschland en Microsoft Global cloud in de verschillende ondersteunde migratiestappen.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-151">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="9c8ed-152">AD FS Disaster Recovery (WID Database)</span><span class="sxs-lookup"><span data-stu-id="9c8ed-152">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="9c8ed-153">Als u de AD FS-farm wilt herstellen in een [ramp, moet ad FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-153">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="9c8ed-154">Daarom moet het hulpprogramma worden gedownload en moet vóór het begin van de migratie een back-up worden gemaakt en veilig worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-154">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="9c8ed-155">In dit voorbeeld zijn de volgende opdrachten uitgevoerd om een back-up te maken van een farm die wordt uitgevoerd in een WID-database:</span><span class="sxs-lookup"><span data-stu-id="9c8ed-155">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="9c8ed-156">Een back-up maken van een AD FS-farm</span><span class="sxs-lookup"><span data-stu-id="9c8ed-156">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="9c8ed-157">Installeer het HULPPROGRAMMA VOOR SNEL HERSTELLEN AD FS op de primaire AD FS-server.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-157">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="9c8ed-158">Importeer de module in een PowerShell-sessie met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-158">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="9c8ed-159">Voer de back-upopdracht uit:</span><span class="sxs-lookup"><span data-stu-id="9c8ed-159">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="9c8ed-160">Sla de back-up veilig op een gewenste bestemming op.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-160">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="9c8ed-161">Een AD FS-farm herstellen</span><span class="sxs-lookup"><span data-stu-id="9c8ed-161">Restore an AD FS Farm</span></span>

<span data-ttu-id="9c8ed-162">Als uw farm volledig is mislukt en er geen manier is om terug te keren naar de oude farm, gaat u als volgt te werk.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-162">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="9c8ed-163">Verplaats de eerder gegenereerde en opgeslagen back-up naar de nieuwe primaire AD FS-server.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-163">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="9c8ed-164">Voer de volgende `Restore-ADFS` PowerShell-opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-164">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="9c8ed-165">Importeer zo nodig het AD FS SSL-certificaat vooraf.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-165">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="9c8ed-166">Wijs uw nieuwe DNS-records of load balancer naar de nieuwe AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="9c8ed-166">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="9c8ed-167">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="9c8ed-167">More information</span></span>

<span data-ttu-id="9c8ed-168">Aan de slag:</span><span class="sxs-lookup"><span data-stu-id="9c8ed-168">Getting started:</span></span>

- [<span data-ttu-id="9c8ed-169">Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's</span><span class="sxs-lookup"><span data-stu-id="9c8ed-169">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="9c8ed-170">Microsoft Cloud Deutschland-migratiehulp</span><span class="sxs-lookup"><span data-stu-id="9c8ed-170">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="9c8ed-171">Opt-in voor migratie</span><span class="sxs-lookup"><span data-stu-id="9c8ed-171">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="9c8ed-172">Klantervaring tijdens de migratie</span><span class="sxs-lookup"><span data-stu-id="9c8ed-172">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="9c8ed-173">Door de overgang lopen:</span><span class="sxs-lookup"><span data-stu-id="9c8ed-173">Moving through the transition:</span></span>

- [<span data-ttu-id="9c8ed-174">Acties en effecten voor de migratiefasen</span><span class="sxs-lookup"><span data-stu-id="9c8ed-174">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="9c8ed-175">Extra pre-work</span><span class="sxs-lookup"><span data-stu-id="9c8ed-175">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="9c8ed-176">Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="9c8ed-176">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="9c8ed-177">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="9c8ed-177">Cloud apps:</span></span>

- [<span data-ttu-id="9c8ed-178">Dynamics 365-migratieprogrammagegevens</span><span class="sxs-lookup"><span data-stu-id="9c8ed-178">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="9c8ed-179">Informatie over power bi-migratieprogramma's</span><span class="sxs-lookup"><span data-stu-id="9c8ed-179">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="9c8ed-180">Aan de slag met uw Microsoft Teams-upgrade</span><span class="sxs-lookup"><span data-stu-id="9c8ed-180">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
