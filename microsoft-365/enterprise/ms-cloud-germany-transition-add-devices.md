---
title: Aanvullende apparaatgegevens voor de migratie van Microsoft Cloud Deutschland
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
description: 'Overzicht: Aanvullende apparaatinformatie over services bij de overstap van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928154"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Aanvullende apparaatgegevens voor de migratie van Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Hoe weet ik of mijn organisatie is beïnvloed?**

Beheerders moeten controleren of ze geregistreerde apparaten `https://portal.microsoftazure.de` hebben. Als uw organisatie geregistreerde apparaten heeft, is dit van invloed op u.

**Wat zijn de gevolgen voor mijn gebruikers?**

Gebruikers vanaf een geregistreerd apparaat kunnen zich niet meer aanmelden nadat uw migratie de [Azure AD-migratiefase](ms-cloud-germany-transition.md#how-is-the-migration-organized) definitief heeft bereikt.  

Zorg ervoor dat al uw apparaten zijn geregistreerd bij het wereldwijde eindpunt voordat uw organisatie is losgekoppeld van Microsoft Cloud Deutschland.
  
**Wanneer registreren mijn gebruikers hun apparaten opnieuw?**

Het is essentieel voor uw succes dat u uw apparaten alleen uitschrijft en opnieuw registreert tijdens de migratiefase Scheiden van [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

**Hoe herstel ik de status van mijn apparaat na de migratie?**

Voor hybride Windows-apparaten van Azure AD die zijn geregistreerd met Azure AD en die eigendom zijn van het bedrijf, kunnen beheerders de migratie van deze apparaten beheren via op afstand geactiveerde werkstromen die de registratie van de oude apparaatstatussen ongedaan maken.
  
Voor alle andere apparaten, inclusief persoonlijke Windows-apparaten die zijn geregistreerd in Azure AD, moet de eindgebruiker deze stappen handmatig uitvoeren. Voor apparaten die zijn verbonden met Azure AD, moeten gebruikers een lokaal beheerdersaccount hebben om de registratie uit te schrijven en vervolgens hun apparaten opnieuw te registreren.

Microsoft publiceert instructies voor het herstellen van de apparaattoestand. 
 
**Hoe weet ik dat al mijn apparaten zijn geregistreerd in de openbare cloud?**

Als u wilt controleren of uw apparaten zijn geregistreerd in de openbare cloud, moet u de lijst met apparaten exporteren en downloaden van de Azure AD-portal naar een Excel-spreadsheet. Filter vervolgens de apparaten die zijn geregistreerd (met behulp van de kolom _registeredTime)_ na de migratiefase Scheiden [van Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Apparaatregistratie wordt gedeactiveerd na de migratie van de tenant en kan niet worden ingeschakeld of uitgeschakeld. Als Intune niet wordt gebruikt, meld u dan aan bij uw abonnement en voer deze opdracht uit om de optie opnieuw te activeren:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a>Hybride Azure AD-join

### <a name="windows-down-level"></a>Windows down-level

_Windows down-level-apparaten zijn Windows-apparaten_ die momenteel eerdere versies van Windows uitvoeren (zoals Windows 8.1 of Windows 7), of die Windows Server-versies eerder dan 2019 en 2016 uitvoeren. Als dergelijke apparaten eerder zijn geregistreerd, moet u de registratie van deze apparaten ongedaan maken en opnieuw registreren. 

Gebruik de volgende opdracht op het apparaat om te bepalen of een Windows-apparaat op downniveau eerder is verbonden met Azure AD:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Als het apparaat eerder is verbonden met Azure AD en als het apparaat netwerkconnectiviteit heeft met globale Azure AD-eindpunten, ziet u de volgende uitvoer:

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

De betreffende apparaten hebben de 'Apparaattoestand' met de waarde 'Onbekend'. Als de uitvoer 'Apparaat niet is samengevoegd' is of waarvan de waarde 'Apparaatstaat' 'Ok' is, negeert u de volgende richtlijnen.

Alleen voor apparaten waaruit blijkt dat het apparaat is verbonden (op basis van apparaatId, duimafdruk, en dergelijke) en waarvan de waarde 'Apparaatstaat' onbekend is, moeten beheerders de volgende opdracht uitvoeren in de context van een domeingebruiker die zich aanmeldt op een dergelijk apparaat op een lager niveau:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

De vorige opdracht hoeft slechts één keer te worden uitgevoerd per domeingebruiker die zich aanmeldt op het windows-apparaat op downniveau. Deze opdracht moet worden uitgevoerd in de context van de domeingebruiker die zich aanmeldt. 

Er moet voldoende aandacht aan worden gegeven om deze opdracht niet uit te voeren wanneer de gebruiker zich vervolgens aan meldt. Wanneer de vorige opdracht wordt uitgevoerd, wordt de samengevoegde status van de lokale hybride Azure AD-computer geweken voor de gebruiker die zich heeft aangemeld. En als de computer nog steeds is geconfigureerd voor hybride Azure AD-join in de tenant, wordt geprobeerd deel te nemen wanneer de gebruiker zich opnieuw meldt.

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>Unjoin

Voer de volgende opdracht uit op het apparaat om te bepalen of het Windows 10-apparaat eerder is verbonden met Azure AD:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Als het apparaat hybride Azure AD-lid is, ziet de beheerder de volgende uitvoer:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Als de uitvoer 'AzureAdJoined: Nee' is, negeert u de volgende richtlijnen.

Voer als beheerder alleen de volgende opdracht uit als beheerder om de samengevoegde status van het apparaat te verwijderen voor apparaten die aantonen dat het apparaat is verbonden met Azure AD.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

De vorige opdracht hoeft slechts eenmaal in een beheercontext op het Windows-apparaat te worden uitgevoerd.

#### <a name="hybrid-ad-joinre-registration"></a>Hybride AD Join\Re-Registration

Het apparaat wordt automatisch zonder tussenkomst van de gebruiker of beheerder aan Azure AD verbonden, zolang het apparaat netwerkconnectiviteit heeft met globale Azure AD-eindpunten. 


## <a name="azure-ad-join"></a>Azure AD Join

**BELANGRIJK:** De Intune-service principal wordt ingeschakeld na de migratie van commerce, wat de activering van Azure AD Device Registration impliceert. Als u Azure AD Device Registration vóór de migratie hebt geblokkeerd, moet u de Intune-service principal met PowerShell uitschakelen om Azure AD Device Registration weer uit te schakelen met de Azure AD-portal. U kunt de Intune-service principal uitschakelen met deze opdracht in de Azure Active Directory PowerShell voor Graph-module.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Unjoin

Als u wilt bepalen of het Windows 10-apparaat eerder is verbonden met Azure AD, kan de gebruiker of beheerder de volgende opdracht uitvoeren op het apparaat:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Als het apparaat is verbonden met Azure AD, ziet de gebruiker of beheerder de volgende uitvoer:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Als de uitvoer 'AzureAdJoined: NO' is, negeert u de volgende richtlijnen.

Gebruiker: Als het apparaat is verbonden met Azure AD, kan een gebruiker de toegang tot het apparaat ontvoegen via de instellingen. Controleer of er een lokaal beheerdersaccount op het apparaat is voordat u het apparaat losvoegt vanuit Azure AD. Het lokale beheerdersaccount is vereist om u weer aan te melden bij het apparaat.

Beheerder: Als de beheerder van de organisatie de apparaten van de gebruikers wil ontvoegen die zijn verbonden met Azure AD, kunnen ze dit doen door de volgende opdracht uit te voeren op elk van de apparaten met behulp van een mechanisme zoals Groepsbeleid. De beheerder moet controleren of er een lokaal beheerdersaccount op het apparaat is voordat het apparaat wordt ontvoegd vanuit Azure AD. Het lokale beheerdersaccount is nodig om u weer aan te melden bij het apparaat.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

De vorige opdracht hoeft slechts eenmaal in een beheercontext op het Windows-apparaat te worden uitgevoerd. 

### <a name="azure-ad-joinre-registration"></a>Azure AD Join/Re-Registration

De gebruiker kan het apparaat koppelen aan Azure AD via Windows-instellingen: **Instellingen > Accounts > Access Work or School > Connect**.
 

## <a name="azure-ad-registered-company-owned"></a>Azure AD Registered (eigendom van het bedrijf)

Voer de volgende opdracht uit op het apparaat om te bepalen of het Windows 10-apparaat azure AD-geregistreerd is:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Als het apparaat Azure AD Registered is, ziet u de volgende uitvoer:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Het bestaande door Azure AD geregistreerde account op het apparaat verwijderen:

- Als u het door Azure AD geregistreerde account op het apparaat wilt verwijderen, gebruikt u CleanupWPJ, een hulpprogramma dat u hier kunt [downloaden:CleanupWPJ.zip. ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)

- Haal het ZIP-bestand op en voer **WPJCleanup.cmd uit.** Met dit hulpprogramma wordt de juiste uitvoerbare start gemaakt op basis van de versie van Windows op het apparaat.

- Met een mechanisme zoals Groepsbeleid kan de beheerder de opdracht uitvoeren op het apparaat in de context van elke gebruiker die is aangemeld op het apparaat.

Als u de aanwijzingen van Web Account Manager wilt uitschakelen om het apparaat in Azure AD te registreren, voegt u deze registerwaarde toe: 

- Locatie: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Type: DWORD (32 bits)
- Naam: BlockAADWorkplaceJoin
- Waardegegevens: 1

De aanwezigheid van deze registerwaarde moet de join van de werkplek blokkeren en voorkomen dat gebruikers aanwijzingen zien om deel te nemen aan het apparaat.

## <a name="android"></a>Android

Voor Android moeten gebruikers de registratie van hun apparaten ongedaan maken en opnieuw registreren. Dit kan via de Microsoft Authenticator-app of de bedrijfsportal-app. 

- Vanuit de Microsoft Authenticator-app kunnen gebruikers naar Instellingen **> Apparaatregistratie.** Van hieruit kunnen gebruikers hun registratie ongedaan maken en hun apparaat opnieuw registreren.
 
- Vanuit de bedrijfsportal kunnen gebruikers naar het tabblad **Apparaten** gaan en het apparaat verwijderen. Daarna kunt u het apparaat opnieuw registreren met behulp van bedrijfsportal.
 
- Gebruikers kunnen zich ook afmelden en opnieuw registreren door het account te verwijderen van de pagina accountinstellingen en vervolgens het werkaccount opnieuw toe te voegen.

U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren met de Microsoft Authenticator-app:

1.  Open de Microsoft Authenticator-app en ga naar **Instellingen.**
2.  Selecteer **Apparaatregistratie.**
3.  De registratie van het apparaat ongedaan maken door **Afmelden te selecteren.**
4.  Voor **apparaatregistratie,** moet u het apparaat opnieuw registreren door uw e-mailadres te typen en vervolgens **Registreren te selecteren.**

U kunt de registratie van een Android-apparaat op de pagina Android-instellingen ongedaan maken en opnieuw registreren:

1.  Open **Apparaatinstellingen** en ga naar **Accounts.**
2.  Selecteer het werkaccount dat u opnieuw wilt registreren en selecteer **Account verwijderen.**
3.  Nadat het account is verwijderd, selecteert u op de **pagina Accounts** de optie Account toevoegen **> werkaccount.**
4.  Voor **Workplace Join** typt u uw e-mailadres en **selecteert** u Deelnemen om de registratie van het apparaat te voltooien.

U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren via bedrijfsportal:

1.  Start Bedrijfsportal en ga naar **het tabblad** Apparaten.
2.  Selecteer het apparaat om de apparaatdetails te bekijken.
3.  Selecteer apparaat verwijderen in het menu drie puntjes (drie puntjes) en voltooi de verwijdering door dit te bevestigen in het dialoogvenster.
4.  U moet nu worden afgemeld bij de bedrijfsportal-app. Selecteer **Aanmelden om** het apparaat opnieuw te registreren.

Bekijk de informatie over Azure Active Directory (Azure AD) in Aanvullende Azure AD-informatie voor de migratie van [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)voor meer informatie over acties die nodig zijn tijdens de migratiefase van deze werkbelasting of de gevolgen voor beheer of gebruik.

## <a name="ios"></a>iOS

Op iOS-apparaten moet een gebruiker accounts in de cache handmatig verwijderen uit de Microsoft Authenticator, het apparaat uitschrijven en zich afmelden bij native apps op het apparaat.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Stap 1: Als dit wordt gebruikt, verwijdert u het account uit de Microsoft Authenticator-app

1. Tik op het account in de Microsoft Authenticator-app.
2. Tik op **het pictogram** Instellingen in de rechterbovenhoek. Als u het pictogram Instellingen **niet** ziet, gebruikt u mogelijk niet de nieuwste versie van Microsoft Authenticator.
3. Tik op **de knop Account** verwijderen.
4. Tik **op Alle apps op dit apparaat.**
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Stap 2: Het apparaat uit de Microsoft Authenticator-app verwijderen

1. Tik op het menupictogram in de rechterbovenhoek.
2. Tik **op Instellingen** en vervolgens op **Apparaatregistratie.**
4. Als uw account wordt weergegeven, tikt u **op Apparaat afmelden** en **doorgaan** in het dialoogvenster. Daarna ziet u geen account meer.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Stap 3: Meld u indien nodig af bij afzonderlijke apps

Gebruikers kunnen naar afzonderlijke apps zoals Outlook, Teams en OneDrive gaan en accounts uit die apps verwijderen.

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