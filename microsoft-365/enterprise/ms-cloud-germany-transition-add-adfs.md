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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Migratiestappen voor AD FS voor de migratie van Microsoft Cloud Deutschland

U kunt als volgt uw AD FS-Farm (Active Directory Federation Services) migreren van Microsoft Cloud Deutschland:

1. U kunt een back-up maken van uw AD FS-instellingen, inclusief [de](#backup)geschiedenis van de FF-gegevens. Naam van de back-up **Microsoft cloud Deutschland_Only** om aan te geven dat alleen de Microsoft Cloud Deutschland-Tenant gegevens bevat.
2. Het herstel testen met de back-up van Microsoft Cloud Deutschland_Only de AD FS-farm moet blijven werken als Microsoft Cloud Deutschland.
3. Maak een nieuwe vertrouwensrelatie van een vertrouwens partij van **AD FS > Office 365-Services**.
4. Selecteer in de console voor het vertrouwen van **partijen vertrouwensrelaties** in de beheerconsole van een **vertrouwensrelatie de optie vertrouwensrelaties** van partijen toevoegen.
5. Selecteer **volgende** op de **welkomst** pagina van de wizard vertrouwen van een vertrouwensrelatie toevoegen.
6. Selecteer op de pagina **gegevensbron selecteren** de optie **gegevens importeren over de uitgenodigde partij die online is gepubliceerd of op een lokaal netwerk**. Het **adres van de Federatie metagegevens (host name of URL)** is ingesteld op `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Klik op **Volgende**.
7. Typ op de pagina **gegevensbron selecteren** de naam van de weergave. Microsoft adviseert Microsoft **Office 365 Identity platform wereldwijd**. Klik op **Volgende**.
8. Klik op **volgende** op de optie **multi-factor Authentication nu configureren?**, **Kies autorisatieregels voor uitgifte** en **klaar om vertrouwende pagina's toe te voegen** .
9. Klik op de pagina **Voltooien** op **sluiten** .

Door de wizard te sluiten, wordt de vertrouwensrelatie tussen de Relying Party en de Office 365-Services eSTS vastgesteld. Er worden echter geen regels voor de uitgifte transformatie gemaakt.

U kunt de [Help van AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) gebruiken om de juiste regels voor de uitgifte transformatie te genereren. De gegenereerde claimregels die zijn gemaakt met de Help voor AD FS, kunnen handmatig worden toegevoegd via de beheerconsole van AD FS of met PowerShell. In de Help van AD FS worden de benodigde PowerShell-scripts gegenereerd die moeten worden uitgevoerd.  

1. Voer **claims genereren** in de Help van AD FS uit en kopieer het PowerShell-transformatie-transformatie met de optie **kopiëren** in de rechterbovenhoek van het script.
2. Plak de gegenereerde PowerShell in de volgende opties:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Voer het voltooide script uit.
4.  Controleer of de twee vertrouwensrelaties van de Relying Party aanwezig zijn; een voor wereldwijd en een voor BF.
5.  Maak een back-up van uw vertrouwensrelaties met de [volgende stappen](#backup). Sla het bestand op onder de naam **FFAndWorldwide**.
6.  Voltooi de back-up van de backend en controleer of AD FS nog steeds werkt tijdens het migratieproces.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Noodherstel voor AD FS (WID-database)

Als u de AD FS-farm wilt herstellen in een noodherstel programma voor de snelle oplossing van [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) , moet u gebruikmaken van de oplossing. Daarom moet u het hulpmiddel downloaden en voordat u de migratie start, moet u eerst een back-up maken en deze veilig opslaan. In dit voorbeeld (TAT-omgevingen) zijn de volgende opdrachten uitgevoerd voor het maken van een back-up van de farm:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Een back-up maken van een AD FS-Farm

1. Installeer het hulpprogramma voor het snel herstellen van AD FS op de primaire AD FS-server.
2. Importeer de module in een PowerShell-sessie met deze opdracht.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. Voer de opdracht back-up uit:

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. Sla de back-up op een veilige locatie op. 

### <a name="restore-an-ad-fs-farm"></a>Een AD FS-Farm herstellen

Ga als volgt te werk als uw farm niet volledig is gelukt en u geen manier kunt teruggaan naar de oude farm. 

1. Verplaats de eerder gegenereerde en opgeslagen back-up naar de nieuwe primaire AD FS-server.
2. Voer de volgende `Restore-ADFS` PowerShell-opdracht uit. Importeer indien nodig het AD FS SSL-certificaat vooraf.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Plaats uw nieuwe DNS-records of Load Balancer naar de nieuwe AD FS-servers.

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden](ms-cloud-germany-transition.md)
- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](ms-cloud-germany-migration-opt-in.md)
- [Gebruikerservaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang navigeren:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra vooraf werken](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie over [Azure AD](ms-cloud-germany-transition-azure-ad.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
