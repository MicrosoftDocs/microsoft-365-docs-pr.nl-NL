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
description: 'Overzicht: Aanvullende apparaatinformatie over services wanneer u van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio gaat.'
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861300"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Aanvullende apparaatgegevens voor de migratie van Microsoft Cloud Deutschland

Verbonden en geregistreerde Azure AD-apparaten die zijn verbonden met Microsoft Cloud Deutschland, moeten worden gemigreerd na fase 9 en vóór fase 10. De migratie van een apparaat is afhankelijk van het type apparaten, het besturingssysteem en de AAD-relatie. 

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Hoe weet ik of mijn organisatie is beïnvloed?**

Beheerders moeten controleren of ze geregistreerde of `https://portal.microsoftazure.de` Azure AD-apparaten hebben. Als uw organisatie geregistreerde apparaten heeft, is dit van invloed op u.

**Wat zijn de gevolgen voor mijn gebruikers?**

Gebruikers van een geregistreerd apparaat kunnen zich niet meer aanmelden nadat [migratiefase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) is voltooid en de eindpunten voor Microsoft Cloud Deutschland zijn uitgeschakeld.  

Zorg ervoor dat al uw apparaten zijn geregistreerd bij het wereldwijde eindpunt voordat uw organisatie is losgekoppeld van Microsoft Cloud Deutschland.
  
**Wanneer registreren mijn gebruikers hun apparaten opnieuw?**

Het is essentieel voor uw succes dat u uw apparaten alleen uitschrijft en opnieuw registreert nadat [fase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) is voltooid. U moet de herregistratie voltooien voordat fase 10 wordt gestart, anders hebt u geen toegang meer tot uw apparaat.

**Hoe herstel ik de status van mijn apparaat na de migratie?**

Voor bedrijfsapparaten Windows die zijn geregistreerd bij Azure AD, kunnen beheerders de migratie van deze apparaten beheren via op afstand geactiveerde werkstromen die de registratie van de oude apparaatstatussen ongedaan maken.
  
Voor alle andere apparaten, waaronder persoonlijke apparaten Windows die zijn geregistreerd in Azure AD, moet de eindgebruiker deze stappen handmatig uitvoeren. Voor apparaten die zijn verbonden met Azure AD, moeten gebruikers een lokaal beheerdersaccount hebben om de registratie uit te schrijven en vervolgens hun apparaten opnieuw te registreren.

Raadpleeg hieronder gedetailleerde instructies voor het herstellen van apparaatstaten. 
 
**Hoe weet ik dat al mijn apparaten zijn geregistreerd in de openbare cloud?**

Als u wilt controleren of uw apparaten zijn geregistreerd in de openbare cloud, moet u de lijst met apparaten exporteren en downloaden van de Azure AD-portal naar een Excel spreadsheet. Filter vervolgens de apparaten die zijn geregistreerd (met behulp van de kolom _registeredTime)_ na de migratiefase Scheiden [van Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

## <a name="additional-considerations"></a>Aanvullende overwegingen
Apparaatregistratie wordt gedeactiveerd na de migratie van de tenant en kan niet worden ingeschakeld of uitgeschakeld. 

Als Intune niet wordt gebruikt, meld u dan aan bij uw abonnement en voer deze opdracht uit om de optie opnieuw te activeren:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**BELANGRIJK:** De Intune-service principal wordt ingeschakeld na de migratie van commerce, wat de activering van Azure AD Device Registration impliceert. Als u Azure AD Device Registration vóór de migratie hebt geblokkeerd, moet u de Intune-service principal met PowerShell uitschakelen om Azure AD Device Registration weer uit te schakelen met de Azure AD-portal. U kunt de Intune-service principal uitschakelen met deze opdracht in Azure Active Directory PowerShell voor Graph module.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Azure AD Join
Dit geldt voor Windows 10 apparaten. 

Als een apparaat is gekoppeld aan Azure AD, moet de verbinding met Azure AD zijn verbroken en opnieuw worden verbonden. 

[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Als de gebruiker een beheerder is op het Windows 10 apparaat, kan de gebruiker de registratie van het apparaat uit Azure AD ongedaan maken en opnieuw deelnemen. Als hij geen beheerdersbevoegdheden heeft, heeft de gebruiker referenties nodig van een lokaal beheerdersaccount op deze computer. 


Een beheerder kan een lokaal beheerdersaccount op het apparaat maken op basis van dit configuratiepad:

*Instellingen > Accounts > Andere accounts > referenties onbekend > Gebruiker toevoegen zonder Microsoft-account*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Stap 1: bepalen of het apparaat is verbonden met Azure-id
1.  Meld u aan met e-mail en wachtwoord van gebruikers.
2.  Ga naar Instellingen > accounts > Toegang tot werk of school. 
3.  Zoek een gebruiker in de lijst met **verbonden met ... 's Azure AD**. 
4.  Als er een verbonden gebruiker bestaat, gaat u verder met stap 2. Zo niet, dan is er geen verdere actie vereist.
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Stap 2: Het apparaat loskoppelen van Azure AD
1.  Tik **op Loskoppelen** op het verbonden werk- of schoolaccount. 
2.  Bevestig de verbinding tweemaal. 
3.  Voer de gebruikersnaam en het wachtwoord van de lokale beheerder in. Het apparaat is losgekoppeld.
4.  Start het apparaat opnieuw op.
### <a name="step-3-join-the-device-to-azure-ad"></a>Stap 3: Deelnemen aan het apparaat aan Azure AD
1.  de gebruiker zich aanmeld met de referenties van de lokale beheerder
2.  Ga naar **Instellingen** accounts **en** vervolgens Toegang tot werk **of school**
3.  Tik **Verbinding maken**
4.  **BELANGRIJK:** Tik op **Deelnemen aan Azure AD**
5.  Voer het e-mailadres en wachtwoord van de gebruiker in. Het apparaat is verbonden
6.  Het apparaat opnieuw starten 
7.  ondertekenen met uw e-mailadres en wachtwoord

## <a name="azure-ad-registered-company-owned"></a>Azure AD Registered (eigendom van het bedrijf)

Als u wilt bepalen of Windows 10 Azure AD-geregistreerd is, voer u de volgende opdracht uit op het apparaat:

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

Voor Android moeten gebruikers de registratie van hun apparaten ongedaan maken en opnieuw registreren. Dit kan via de Microsoft Authenticator app of de Bedrijfsportal app. 

- Vanuit de Microsoft Authenticator app kunnen gebruikers naar Instellingen > **Apparaatregistratie** gaan. Van hieruit kunnen gebruikers hun registratie ongedaan maken en hun apparaat opnieuw registreren.
 
- Vanuit de Bedrijfsportal kunnen gebruikers naar het **tabblad** Apparaten gaan en het apparaat verwijderen. Daarna kunt u het apparaat opnieuw registreren met behulp van Bedrijfsportal.
 
- Gebruikers kunnen zich ook afmelden en opnieuw registreren door het account te verwijderen van de pagina accountinstellingen en vervolgens het werkaccount opnieuw toe te voegen.

U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren met de Microsoft Authenticator app:

1.  Open de Microsoft Authenticator app en ga naar **Instellingen.**
2.  Selecteer **Apparaatregistratie.**
3.  De registratie van het apparaat ongedaan maken door **Afmelden te selecteren.**
4.  Voor **apparaatregistratie,** moet u het apparaat opnieuw registreren door uw e-mailadres te typen en vervolgens **Registreren te selecteren.**

Een Android-apparaat op de pagina Android-Instellingen opnieuw registreren:

1.  Open **Apparaat Instellingen** en ga naar **Accounts.**
2.  Selecteer het werkaccount dat u opnieuw wilt registreren en selecteer **Account verwijderen.**
3.  Nadat het account is verwijderd, selecteert u op de **pagina Accounts** de optie Account toevoegen **> werkaccount.**
4.  Voor **Workplace Join** typt u uw e-mailadres en **selecteert** u Deelnemen om de registratie van het apparaat te voltooien.

U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren Bedrijfsportal:

1.  Start Bedrijfsportal en ga naar **het tabblad** Apparaten.
2.  Selecteer het apparaat om de apparaatdetails te bekijken.
3.  Selecteer apparaat verwijderen in het menu drie puntjes (drie puntjes) en voltooi de verwijdering door dit te bevestigen in het dialoogvenster.
4.  U moet nu zijn afgemeld bij de Bedrijfsportal app. Selecteer **Aanmelden om** het apparaat opnieuw te registreren.

Bekijk de informatie over Azure Active Directory (Azure AD) in Aanvullende Azure AD-informatie voor de migratie van [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)voor meer informatie over acties die nodig zijn tijdens de migratiefase van deze werkbelasting of de gevolgen voor beheer of gebruik.

## <a name="ios"></a>iOS

Op iOS-apparaten moet een gebruiker accounts in de cache handmatig verwijderen uit de Microsoft Authenticator, het apparaat uitschrijven en zich afmelden bij native apps op het apparaat.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Stap 1: Als u aanwezig bent, verwijdert u het account uit de Microsoft Authenticator app

1. Tik op het account in de Microsoft Authenticator app.
2. Tik op **Instellingen** in de rechterbovenhoek. Als u het pictogram  Instellingen niet ziet, gebruikt u mogelijk niet de nieuwste versie van Microsoft Authenticator.
3. Tik op **de knop Account** verwijderen.
4. Tik **op Alle apps op dit apparaat.**
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Stap 2: Het apparaat uit de app Microsoft Authenticator verwijderen

1. Tik op het menupictogram in de rechterbovenhoek.
2. Tik **Instellingen** en vervolgens **op Apparaatregistratie.**
4. Als uw account wordt weergegeven, tikt u **op Apparaat afmelden** en **doorgaan** in het dialoogvenster. Daarna ziet u geen account meer.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Stap 3: Meld u indien nodig af bij afzonderlijke apps

Gebruikers kunnen naar afzonderlijke apps gaan, zoals Outlook, Teams en OneDrive en accounts uit die apps verwijderen.

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland-migratiehulp](https://aka.ms/germanymigrateassist)
- [Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Dynamics 365-migratieprogrammagegevens](/dynamics365/get-started/migrate-data-german-region)
- [Power BI migratieprogrammagegevens](/power-bi/admin/service-admin-migrate-data-germany)
- [Aan de slag met uw Microsoft Teams upgrade](/microsoftteams/upgrade-start-here)