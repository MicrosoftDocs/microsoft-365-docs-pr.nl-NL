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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD FS-migratiestappen voor de migratie van Microsoft Cloud Deutschland

Deze configuratiewijziging moet op elk moment worden toegepast voordat fase 2 begint.
Wanneer fase 2 is voltooid, werkt de configuratiewijziging en kunt u zich aanmelden via globale eindpunten van Office 365, zoals `https://portal.office.com` . Als u de configuratiewijziging implementeert vóór fase 2, werken  de globale eindpunten van Office 365 nog niet, maar maakt het vertrouwen van de nieuwe vertrouwensrelatie van de vertrouwenspartij nog steeds deel uit van uw AD FS-configuratie (Active Directory Federation Services).

Klanten die federatieverificatie met AD FS (Active Directory Federation Services) gebruiken, mogen tijdens de migratie geen wijzigingen aanbrengen in url's van uitgevende gebruikers die worden gebruikt voor alle verificaties met on-premises Active Directory Domain Services (AD DS). Als u url's voor uitgevende gebruikers verandert, kan dit leiden tot verificatiefouten voor gebruikers in het domein. Url's voor uitgevende uitgevende uri's kunnen  rechtstreeks worden gewijzigd in AD FS of wanneer een domein wordt geconverteerd van beheerd naar _federatief_ en omgekeerd. U wordt aangeraden een federatief domein niet toe te voegen, te verwijderen of te converteren in de Azure AD-tenant die is gemigreerd. U kunt URL's voor uitgevende uri's wijzigen nadat de migratie volledig is voltooid.

Voer de volgende stappen uit om uw AD FS-farm voor te bereiden op de migratie van Microsoft Cloud Deutschland:

1. Een back-up maken van uw AD FS-instellingen, inclusief het bestaande vertrouwen van Microsoft Cloud Deutschland Relying Party, met [deze stappen.](#backup) Geef de back-up **van MicrosoftCloudDeutschlandOnly een** naam om aan te geven dat alleen de tenantgegevens van Microsoft Cloud Deutschland beschikbaar zijn.

   > [!NOTE]
   > De back-up bevat niet alleen de bestaande Vertrouwensrelatie van Office 365 Relying Party voor Microsoft Cloud Deutschland, maar ook alle andere Vertrouwensrelatie voor afhankelijke partijen die aanwezig zijn op de betreffende AD FS-farm.

2. Test het herstel met behulp van de MicrosoftCloudDeutschlandOnly-back-up, de AD FS-farm moet alleen blijven werken als Microsoft Cloud Deutschland.

Nadat u de AD FS-back-up hebt voltooid en getest, voert u de volgende stappen uit om een nieuwe vertrouwensrelatie van een vertrouwenspartij toe te voegen aan uw ADFS-configuratie:

1. Open de AD FS-beheerconsole.

2. Ga in het linkerdeelvenster van de ADFS-beheerconsole naar het menu **Vertrouwensrelatie van relying party.**

3. Selecteer in het rechterdeelvenster **Vertrouwen van afhankelijke partij toevoegen...**

4. Selecteer **Start** op de **welkomstpagina** van de wizard Vertrouwen van afhankelijke partijen toevoegen.

5. Selecteer op **de pagina Gegevensbron** selecteren de optie Gegevens importeren over de afhankelijke partij die online of **op een lokaal netwerk is gepubliceerd.** De **waarde federatie metagegevens (hostnaam of URL)** moet zijn ingesteld op `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Klik op **Volgende**.

6. Typ op **de pagina Weergavenaam** opgeven de weergavenaam zoals **Microsoft Office 365 Identity Platform WorldWide**. Klik op **Volgende**.

7. Als u ADFS gebruikt in Windows Server 2012, selecteert u op de wizardpagina Meervoudige verificatie **nu configureren?** de juiste keuze op basis van uw verificatievereisten. Als u zich aan de standaardinstelling houdt, selecteert u Ik wil op dit moment geen instellingen voor meervoudige verificatie configureren voor dit vertrouwen van afhankelijke **partijen.** U kunt deze instelling later wijzigen als u dat wilt.

8. Voor AD FS 2012: In de autorisatieregels voor uitgifte kiezen blijven alle gebruikers toegang verlenen tot deze afhankelijke **partij** geselecteerd en klikt u op **Volgende.** 

9. Voor AD FS 2016 en AD FS 2019: Selecteer op de pagina **Beleid** voor toegangsbeheer kiezen het juiste toegangsbeleid en klik op **Volgende**. Als er geen is gekozen, werkt het vertrouwen van de afhankelijke partij **NIET.**

10. Klik **op Volgende** op de pagina Vertrouwen **toevoegen** om de wizard te voltooien.

11. Klik **op Sluiten** op de **pagina** Voltooien.

Als u de wizard sluit, wordt de vertrouwensrelatie van relying party met de globale office 365-service ingesteld. Er zijn echter nog geen regels voor uitgiftetransformator geconfigureerd.

U kunt [AD FS Help gebruiken om](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) de juiste regels voor uitgiftetransformator te genereren. De gegenereerde claimregels die zijn gemaakt met AD FS Help, kunnen handmatig worden toegevoegd via de AD FS-beheerconsole of met PowerShell. Ad FS Help genereert de benodigde PowerShell-scripts die moeten worden uitgevoerd.  

> [!NOTE]
> [Ad FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) genereert de standaarduitgiftetransformatorregels die worden geleverd met het product. Als er echter aangepaste uitgiftetransformatorregels worden gebruikt in het vertrouwen van een vertrouwenspersoon in Microsoft Cloud Deutschland (bijvoorbeeld aangepaste URL's van uitgevende uitgevende e-mail, niet-standaardinmuteerbare ID's of andere aanpassingen), moeten de regels die door AD FS-help worden gegenereerd, worden gewijzigd op een manier die past bij de aangepaste logica die momenteel wordt gebruikt voor het vertrouwen van de vertrouwensrelatie van de vertrouwensrelatie van de microsoft Cloud Deutschland-afhankelijke partij. Als deze aanpassingen niet zijn geïntegreerd in de regels die worden gegenereerd via [AD FS Help,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)werkt verificatie naar **Microsoft Office 365 Identity Platform WorldWide** waarschijnlijk niet voor uw federatief identiteiten. 

1. Voer **De Help Voor** het genereren van claims  op [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) uit en kopieer het PowerShell-script met de optie Kopiëren in de rechterbovenhoek van het script.

2. Volg de stappen die worden beschreven bij [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) over het uitvoeren van het PowerShell-script in uw AD FS-farm om het globale vertrouwen van afhankelijke partijen te genereren. Voordat u het script gaat uitvoeren, vervangt u de volgende coderegels in het gegenereerde script, zoals hieronder wordt beschreven:

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

3. Controleer of er twee Relying PartyTtrusts aanwezig zijn. een voor Microsoft Cloud Deutschland en een voor de Globale Office 365-service. De volgende opdracht kan worden gebruikt voor de controle. Het moet twee rijen en de respectievelijke namen en id's retourneren.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. Gebruik deze stappen om een back-up te maken van uw volledige migratieconfiguratie, inclusief beide vertrouwensrelatie van Relying [Party.](#backup) Sla het op met de naam **MicrosoftCloudDeutschlandAndWorldwide.**

5. Terwijl uw tenant bezig is met migratie, controleert u regelmatig of AD FS-verificatie werkt met Microsoft Cloud Deutschland en Microsoft Global cloud in de verschillende ondersteunde migratiestappen.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS Disaster Recovery (WID Database)

Als u de AD FS-farm wilt herstellen in een [ramp, moet ad FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) worden gebruikt. Daarom moet het hulpprogramma worden gedownload en moet vóór het begin van de migratie een back-up worden gemaakt en veilig worden opgeslagen. In dit voorbeeld zijn de volgende opdrachten uitgevoerd om een back-up te maken van een farm die wordt uitgevoerd in een WID-database:

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

- [Dynamics 365-migratieprogrammagegevens](/dynamics365/get-started/migrate-data-german-region)
- [Informatie over power bi-migratieprogramma's](/power-bi/admin/service-admin-migrate-data-germany)
- [Aan de slag met uw Microsoft Teams-upgrade](/microsoftteams/upgrade-start-here)
