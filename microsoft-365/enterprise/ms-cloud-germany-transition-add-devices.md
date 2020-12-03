---
title: Aanvullende informatie over apparaten voor de migratie van Microsoft Cloud Deutschland
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
description: 'Overzicht: aanvullende informatie over apparaten voor services wanneer u overstapt van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: 941b836871f4ffb7f39f6e144675e9ee15510270
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560854"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Aanvullende informatie over apparaten voor de migratie van Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Hoe weet ik of mijn organisatie van invloed is?**

Beheerders moeten `https://portal.microsoftazure.de` nagaan of ze geregistreerde apparaten hebben. Als uw organisatie geregistreerde apparaten heeft, hebt u last van.

**Wat is de gevolgen voor mijn gebruikers?**

Gebruikers van een geregistreerd apparaat kunnen zich niet meer aanmelden nadat de migratie is voltooid met de [Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) -migratie fase.  

Zorg ervoor dat al uw apparaten geregistreerd zijn met het wereldwijde eindpunt voordat uw organisatie wordt losgekoppeld van Microsoft Cloud Deutschland.
  
**Wanneer worden mijn gebruikers hun apparaten opnieuw registreren?**

Het is belangrijk dat u het niet meer registreert en uw apparaten opnieuw registreert onder de migratie fase [van Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

**Hoe kan ik de status van mijn apparaat na migratie herstellen?**

Voor hybride Azure AD-en bedrijfsgeschikte Windows-apparaten die zijn geregistreerd bij Azure AD, kunnen beheerders de migratie van deze apparaten beheren via externe, geactiveerde werkstromen waarmee de registratie van de oude status van het oude apparaat wordt opgeheven.
  
Voor alle andere apparaten, waaronder persoonlijke Windows-apparaten die in azure AD zijn geregistreerd, moet de eindgebruiker deze stappen handmatig uitvoeren. Voor Azure AD – gekoppelde apparaten moet de gebruiker een lokaal beheerdersaccount hebben om de registratie te deactiveren en de apparaten vervolgens opnieuw te registreren.

In Microsoft wordt de instructies gepubliceerd voor het herstellen van de status van het apparaat. 
 
**Hoe weet ik of al mijn apparaten geregistreerd zijn in de openbare Cloud?**

Als u wilt controleren of de apparaten in de openbare Cloud zijn geregistreerd, moet u de lijst met apparaten in de Azure AD-Portal exporteren naar een Excel-spreadsheet en deze downloaden. Vervolgens kunt u de geregistreerde apparaten filteren (met behulp van de kolom _registeredTime_ ), na de [afzonderlijke migratie van Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migratie fase.

Apparaatregistratie wordt gedeactiveerd na migratie van de Tenant en kan niet worden ingeschakeld of uitgeschakeld. Als intune niet wordt gebruikt, meldt u zich aan bij uw abonnement en voert u deze opdracht uit om de optie weer te activeren:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Windows Hybrid Azure AD join

### <a name="windows-down-level"></a>Windows-downlevel

_Windows-apparaten op een lager niveau_ zijn Windows-apparaten die op dit moment eerdere versies van Windows gebruiken (zoals Windows 8,1 of Windows 7) of die Windows Server-versies ouder dan 2019 en 2016 uitvoeren. Als deze apparatuur eerder geregistreerd is, moet u de registratie van deze apparaten ongedaan maken en opnieuw registreren. 

Gebruik de volgende opdracht op het apparaat om te bepalen of een apparaat op het Windows-apparaat eerder lid is van Azure AD:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Als het apparaat eerder is verbonden met Azure AD en als het apparaat netwerkverbinding heeft met globale Azure AD-eindpunten, ziet u de volgende uitvoer:

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

De beïnvloede apparaten hebben de ' apparaat State ' met de waarde ' onbekend '. Als de uitvoer de waarde ' apparaat niet meeneemt ' of waarvan de waarde ' apparaat State ' ' ' u ' is, negeert u de volgende richtlijnen.

Alleen voor apparaten die aangeven dat het apparaat is verbonden (op basis van deviceId, vingerafdruk, enzovoort) en waarvan de waarde ' apparaat State ' ' onbekend ' is, moeten beheerders de volgende opdracht uitvoeren in de context van een domeingebruiker die zich aanmeldt op een dergelijk apparaat met een lager niveau:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

De bovenstaande opdracht hoeft slechts één keer per domeingebruiker te worden uitgevoerd op het Windows-apparaat op het niveau van het laagste niveau. Deze opdracht moet worden uitgevoerd in de context van de domeingebruiker die zich aanmeldt. 

U dient deze opdracht niet uit te voeren wanneer de gebruiker zich daarna aanmeldt. Wanneer de vorige opdracht wordt uitgevoerd, wordt de gekoppelde status gewist van de lokale hybride Azure AD-computer die is gekoppeld aan de gebruiker die zich heeft aangemeld. En als de computer nog steeds is geconfigureerd voor hybride Azure AD – deelnemen aan de Tenant, wordt geprobeerd deel te nemen wanneer de gebruiker zich opnieuw aanmeldt.

### <a name="windows-current"></a>Windows-actueel

#### <a name="unjoin"></a>Ontkoppelen

Voer de volgende opdracht uit op het apparaat om te controleren of het Windows 10-apparaat eerder lid is van Azure AD:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Als het apparaat hybride Azure AD bevat, ziet de beheerder de volgende uitvoer:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Als de uitvoer ' AzureAdJoined: Nee ' is, negeert u de volgende richtlijnen.

Voor apparaten die aangeven dat het apparaat is verbonden met Azure AD, voert u de volgende opdracht uit als beheerder om de gekoppelde status van het apparaat te verwijderen.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

De bovenstaande opdracht hoeft slechts eenmaal te worden uitgevoerd in een beheer context op het Windows-apparaat.

#### <a name="hybrid-ad-joinre-registration"></a>Hybrid AD Join\Re-Registration

Het apparaat maakt automatisch deel uit van Azure AD zonder dat de gebruiker of de beheerder van de beheerder zijn, zolang het apparaat netwerkverbinding heeft met globale Azure AD-eindpunten. 


## <a name="windows-azure-ad-join"></a>Deelnemen aan Windows Azure AD

**Belangrijk:** De intune service-principal wordt ingeschakeld na commerce Migration, wat impliceert het activeren van Azure AD-apparaatregistratie. Als u ervoor hebt gezorgd dat u de registratie van Azure AD-apparaat voorafgaand aan de migratie hebt geblokkeerd, moet u de intune-Service-Principal uitschakelen met PowerShell om Azure AD-apparaatregistratie opnieuw te uitschakelen met de Azure AD-Portal U kunt tijdens de module Azure Active Directory PowerShell voor Graph de intune-Service-Principal uitschakelen met deze opdracht.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Ontkoppelen

Als u wilt controleren of het Windows 10-apparaat eerder is verbonden met Azure AD, kunt u de volgende opdracht op het apparaat uitvoeren met de gebruiker of beheerder:

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

Als de uitvoer ' AzureAdJoined: Nee ' is, negeert u de volgende richtlijnen.

Gebruiker: als het apparaat Azure Active Directory is, kan een gebruiker het apparaat loskoppelen van de instellingen. Controleer of er een lokaal beheerdersaccount op het apparaat staat voordat u de verbinding maakt met het apparaat via Azure AD. U moet het lokale beheerdersaccount opnieuw aanmelden bij het apparaat.

Beheerder: als de beheerder van de organisatie wil deelnemen aan de apparaten van de gebruikers die lid zijn van Azure AD – u kunt dat doen door de volgende opdracht uit te voeren op alle apparaten met behulp van een mechanisme, zoals Groepsbeleid. De beheerder moet controleren of er een lokaal beheerdersaccount op het apparaat staat voordat u de verbinding met het apparaat via Azure AD verzorgt. Het lokale beheerdersaccount is nodig om u weer aan te melden bij het apparaat.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

De bovenstaande opdracht hoeft slechts eenmaal te worden uitgevoerd in een beheer context op het Windows-apparaat. 

### <a name="azure-ad-joinre-registration"></a>Azure AD deelnemen/opnieuw registreren

De gebruiker kan deelnemen aan Azure AD via Windows-instellingen: **instellingen > Accounts > toegang tot werk of School > verbinding maken**.
 

## <a name="windows-azure-ad-registered-company-owned"></a>Geregistreerde Windows Azure AD (bedrijfseigenaar)

Voer de volgende opdracht uit op het apparaat om te controleren of het apparaat met Windows 10 Azure AD is geregistreerd:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Als Azure AD is geregistreerd, ziet u de volgende uitvoer:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

U kunt als volgt het bestaande in azure AD geregistreerde account van het apparaat verwijderen:

- Als u het door u geregistreerde Azure AD-account op het apparaat wilt verwijderen, gebruikt u CleanupWPJ, een hulpmiddel dat u kunt downloaden: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Uitpak het ZIP-bestand en voer **WPJCleanup. cmd** uit. Met dit hulpprogramma wordt het juiste uitvoerbare bestand geopend op basis van de versie van Windows op het apparaat.

- Met behulp van een mechanisme, zoals Groepsbeleid, kan de beheerder de opdracht op het apparaat uitvoeren in de context van elke gebruiker die zich op het apparaat heeft aangemeld.

Als u wilt dat webaccount manager vraagt om het apparaat te registreren in azure AD, voegt u deze registerwaarde toe: 

- Locatie: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Type: DWORD (32 bits)
- Naam: BlockAADWorkplaceJoin
- Waardegegevens: 1

De aanwezigheid van deze registerwaarde moet de verbinding voor werkplek blokkeren en voorkomen dat gebruikers prompts zien om lid te worden van het apparaat.

## <a name="android"></a>Android

Voor Android moeten gebruikers hun apparaten registreren en opnieuw registreren. U kunt dit doen via de Microsoft Authenticator-app of de bedrijfsportal-app. 

- Via de Microsoft Authenticator-app kunnen gebruikers naar **instellingen > apparaatregistratie** gaan. Van de gebruikers kunnen zich registreren en het apparaat opnieuw registreren.
 
- Vanuit de bedrijfs portal kunnen gebruikers naar het tabblad **apparaten** gaan en het apparaat verwijderen. Registreer vervolgens het apparaat opnieuw via de bedrijfs portal.
 
- Gebruikers kunnen zich ook registreren en opnieuw registreren door het account uit de pagina Accountinstellingen te verwijderen en vervolgens de werkaccount opnieuw toe te voegen.

Met de Microsoft Authenticator-app kunt u de registratie en het apparaat opnieuw registreren voor Android met behulp van de Microsoft Authenticator-app:

1.  Open de Microsoft Authenticator-app en ga naar **instellingen**.
2.  Selecteer **apparaatregistratie**.
3.  Hef de registratie van het apparaat op door **register** te selecteren.
4.  Voor apparaatregistratie meldt u het apparaat **opnieuw aan door** uw e-mailadres te typen en vervolgens **registreren** te selecteren.

De registratie van een Android-apparaat opheffen en opnieuw registreren met de pagina Android-instellingen:

1.  Open **device settings** en ga naar **accounts**.
2.  Selecteer het werkaccount dat u opnieuw wilt registreren en selecteer **account verwijderen**.
3.  Nadat het account is verwijderd, selecteert u op de pagina **accounts** de optie **account toevoegen > werkaccount**.
4.  Voor **Workplace join** typt u uw e-mailadres en selecteert u **deelnemen** om het registreren van het apparaat te voltooien.

Als u het apparaat wilt registreren en opnieuw wilt registreren voor Android vanuit de bedrijfs portal, doet u het volgende:

1.  Start Company Portal en ga naar het tabblad **apparaten** .
2.  Selecteer het apparaat om de details van het apparaat te zien.
3.  Selecteer in het menu weglatingstekens (drie puntjes) de optie **apparaat verwijderen** en voltooi de verwijdering door het dialoogvenster te bevestigen.
4.  U dient nu af te melden bij de bedrijfs portal-app. Selecteer **Aanmelden** om het apparaat opnieuw te registreren.

Zie de informatie over Azure Active Directory in [aanvullende algemene informatie over de migratie van Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory)voor meer informatie over de acties die moeten worden uitgevoerd tijdens de migratie fase van deze werkbelasting of van invloed zijn op beheer of gebruik.

## <a name="ios"></a>Apparaten

Op iOS-apparaten moet een gebruiker alle in de cache opgeslagen accounts handmatig verwijderen van de Microsoft Authenticator, de registratie van het apparaat opheffen en u afmelden bij een willekeurige app op het apparaat.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Stap 1: indien aanwezig, verwijdert u het account uit de Microsoft Authenticator-app.

1. Tik op het account in de Microsoft Authenticator-app.
2. Tik in de rechterbovenhoek op het pictogram **instellingen** . Als u het pictogram **instellingen** niet ziet, gebruikt u mogelijk niet de meest recente versie van Microsoft Authenticator.
3. Tik op de knop **account verwijderen** .
4. Tik **op alle apps op dit apparaat**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Stap 2: het apparaat uit de Microsoft Authenticator-app verwijderen

1. Tik op het menupictogram in de rechterbovenhoek.
2. Tik op **instellingen** en vervolgens op **apparaatregistratie**.
4. Als uw account wordt weergegeven, tikt u op **apparaat registreren** en **gaat u door** in het dialoogvenster. U ziet geen account meer.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Stap 3: zo nodig afmelden bij afzonderlijke apps

Gebruikers kunnen naar afzonderlijke apps, zoals Outlook, teams en OneDrive, gaan en accounts van die apps verwijderen.

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden](ms-cloud-germany-transition.md)
- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](ms-cloud-germany-migration-opt-in.md)
- [Gebruikerservaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang navigeren:

- [Acties en effecten bij migratie fasen](ms-cloud-germany-transition-phases.md)
- [Extra vooraf werken](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie over [Services](ms-cloud-germany-transition-add-general.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
