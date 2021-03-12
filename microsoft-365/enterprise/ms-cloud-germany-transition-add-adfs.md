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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD FS-migratiestappen voor de migratie van Microsoft Cloud Deutschland

Deze configuratiewijziging kan op elk moment worden toegepast voordat fase 4 begint.
Wanneer fase 2 is voltooid, werkt de configuratiewijziging en kunt u zich aanmelden bij globale eindpunten van Office 365, zoals `https://portal.office.com` . Als u de configuratiewijziging implementeert vóór fase 2, werken  de globale eindpunten van Office 365 nog niet, maar maakt het vertrouwen van de nieuwe vertrouwensrelatie van de vertrouwenspartij nog steeds deel uit van uw AD FS-configuratie (Active Directory Federation Services).

Als u uw AD FS-farm wilt migreren vanuit Microsoft Cloud Deutschland:

1. Met deze stappen maakt u een back-up van uw AD FS-instellingen, inclusief [FF-vertrouwensgegevens.](#backup) Geef de back-up **van Microsoft Cloud Deutschland_Only** om aan te geven dat deze alleen de tenantgegevens van Microsoft Cloud Deutschland heeft.
2. Test het herstellen met behulp van de Microsoft Cloud Deutschland_Only back-up, de AD FS-farm moet alleen blijven werken als Microsoft Cloud Deutschland.

Nadat u de AD FS-back-up hebt voltooid en getest, voert u de volgende stappen uit om een nieuwe vertrouwensrelatie van een vertrouwenspartij toe te voegen aan uw ADFS-configuratie:

1. De AD FS-beheerconsole openen
2. Vouw in het linkerdeelvenster van de ADFS-beheerconsole **ADFS** uit, vervolgens **Vertrouwensrelaties** en **vertrouwensrelaties van afhankelijke partijen**
3. Selecteer in het rechterdeelvenster **Vertrouwen van afhankelijke partij toevoegen...**
4. Selecteer **Volgende** op de **welkomstpagina** van de wizard Vertrouwen van afhankelijke partijen toevoegen.
5. Selecteer op **de pagina Gegevensbron** selecteren de optie Gegevens importeren over de afhankelijke partij die online of **op een lokaal netwerk is gepubliceerd.** De **waarde federatie metagegevens (hostnaam of URL)** moet zijn ingesteld op `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Klik vervolgens op **Volgende**.
6. Typ op **de pagina Gegevensbron** selecteren de weergavenaam zoals **Microsoft Office 365 Identity Platform WorldWide**. Klik vervolgens op **Volgende**.
7. Selecteer op de wizardpagina **Meervoudige verificatie nu configureren?** de juiste keuze op basis van uw verificatievereisten. Als u zich aan de standaardinstelling houdt, selecteert u Ik wil op dit moment geen instellingen voor meervoudige verificatie configureren voor dit vertrouwen van afhankelijke **partijen.** U kunt deze instelling later wijzigen als u dat wilt.
8. Houd in **de kies autorisatieregels** voor uitgifte toestaan dat alle gebruikers toegang hebben tot deze **afhankelijke partij** geselecteerd op **Volgende**
9. Klik **op Volgende** op de pagina Vertrouwen **toevoegen** om de wizard te voltooien.
10. Klik **op Sluiten** op de **pagina** Voltooien.

Door de wizard te sluiten, wordt het vertrouwen van afhankelijke partijen met de globale Office 365-services ingesteld. Er zijn echter nog geen regels voor uitgiftetransformator geconfigureerd.

U kunt [AD FS Help gebruiken om](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) de juiste regels voor uitgiftetransformator te genereren. De gegenereerde claimregels die zijn gemaakt met AD FS Help, kunnen handmatig worden toegevoegd via de AD FS-beheerconsole of met PowerShell. Ad FS Help genereert de benodigde PowerShell-scripts die moeten worden uitgevoerd.  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. Voer **help bij het** genereren van claims op AD  FS uit en kopieer het PowerShell-claimtransformatiescript met de optie Kopiëren in de rechterbovenhoek van het script.
2. Open de gewenste teksteditor en plak het PowerShell-script in een nieuw tekstvenster.
3. De volgende PowerShell-regels toevoegen aan het einde van het geperste script uit stap 2
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. Het PowerShell-script veilig en uitvoeren.
5. Controleer of er twee vertrouwensrelaties van relying party aanwezig zijn. een voor de Microsoft Cloud Deutschland en een voor de Globale Office 365-service.
6. Back-up maken van uw [vertrouwensrelatie met behulp van deze stappen.](#backup) Sla het op met de naam **FFAndWorldwide.**
7. Voltooi de backend-migratie en controleer of AD FS nog steeds werkt tijdens het migratieproces.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS Disaster Recovery (WID Database)

Als u de AD FS-farm wilt herstellen in een [ramp, moet ad FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) worden gebruikt. Daarom moet het hulpprogramma worden gedownload en moet vóór het begin van de migratie een back-up worden gemaakt en veilig worden opgeslagen. In dit voorbeeld (TAT-omgevingen) zijn de volgende opdrachten uitgevoerd om een back-up van de farm te maken:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Een back-up maken van een AD FS-farm

1. Installeer het HULPPROGRAMMA VOOR SNEL HERSTELLEN AD FS op de primaire AD FS-server.
2. Importeer de module in een PowerShell-sessie met deze opdracht.
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. Voer de back-upopdracht uit:
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. Sla de back-up veilig op een gewenste bestemming op.

### <a name="restore-an-ad-fs-farm"></a>Een AD FS-farm herstellen

Als uw farm volledig is mislukt en er geen manier is om terug te keren naar de oude farm, gaat u als volgt te werk. 

1. Verplaats de eerder gegenereerde en opgeslagen back-up naar de nieuwe primaire AD FS-server.
2. Voer de volgende `Restore-ADFS` PowerShell-opdracht uit. Importeer zo nodig het AD FS SSL-certificaat vooraf.

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. Wijs uw nieuwe DNS-records of load balancer naar de nieuwe AD FS-servers.

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland-migratiehulp](https://aka.ms/germanymigrateassist)
- [Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Dynamics 365-migratieprogrammagegevens](https://aka.ms/d365ceoptin)
- [Informatie over power bi-migratieprogramma's](https://aka.ms/pbioptin)
- [Aan de slag met uw Microsoft Teams-upgrade](https://aka.ms/SkypeToTeams-Home)
