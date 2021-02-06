---
title: Los problemen op die door het hulpprogramma voor gereedheidsevaluatie worden gevonden
description: Gedetailleerde acties die u moet uitvoeren voor elk probleem dat met het hulpprogramma wordt gevonden
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ff2ef15f93cef5255e8c8113facf51b833eff77d
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122358"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Los problemen op die door het hulpprogramma voor gereedheidsevaluatie worden gevonden

Bij elke controle wordt een van de vier mogelijke resultaten door het hulpmiddel rapporteren:


|Resultaat  |Betekenis  |
|---------|---------|
|Klaar     | U hoeft niets te doen voordat u de inschrijving voltooit.        |
|Advies    | Volg de stappen in het hulpprogramma of dit artikel voor een optimaal gebruik van de inschrijving en voor gebruikers. U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.        |
|Nog niet gereed | *De registratie mislukt als u deze problemen niet op kunt lossen.* Volg de stappen in het hulpprogramma of in dit artikel om ze op te lossen.        |
|Error | De Ad-rol (Azure Active Directory) die u gebruikt, heeft onvoldoende machtigingen om deze controle uit te voeren. |

> [!NOTE]
> De resultaten die door dit hulpprogramma zijn gerapporteerd, geven alleen de status van uw instellingen weer op het specifieke tijdstip dat u het hulpprogramma hebt gemaakt. Als u later wijzigingen aan het beleid aan brengen in Microsoft Intune, Azure Active Directory of Microsoft 365, kunnen items die 'Gereed' waren, 'Niet gereed' worden. Als u problemen met bewerkingen met beheerd bureaublad van Microsoft wilt voorkomen, controleert u de specifieke instellingen die in dit artikel worden beschreven voordat u beleid wijzigt.

## <a name="microsoft-intune-settings"></a>Microsoft Intune-instellingen

U kunt intune-instellingen openen in het beheercentrum van Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Autopilot-implementatieprofiel

U mag geen Bestaande Autopilot-profielen hebben die zijn gericht op toegewezen of dynamische groepen met Microsoft Managed Desktop-apparaten. Microsoft Managed Desktop gebruikt Autopilot om nieuwe apparaten in terichten.

**Nog niet gereed**

U hebt een Autopilot-profiel dat is toegewezen aan alle apparaten. Zie Windows-apparaten [registreren in Intune door Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)te gebruiken voor stappen. Stel na de registratie van het beheerde bureaublad van Microsoft uw Autopilot-beleid in om de **groep Modern Workplace Devices -All** Azure AD uit te sluiten.

**Advies**

Zorg ervoor dat uw Autopilot-profielen zijn gericht op een toegewezen of dynamische Azure AD-groep die geen Microsoft Managed Desktop-apparaten bevat. Zie Windows-apparaten [registreren in Intune door Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)te gebruiken voor stappen. Stel na de registratie van Het beheerde bureaublad van Microsoft uw Autopilot-profielen zo in dat de **groep Modern Workplace Devices -All** Azure AD wordt uitgesloten.


### <a name="certificate-connectors"></a>Connectors voor certificaten

Als u certificaatconnectors hebt die worden gebruikt door de apparaten die u wilt registreren in Het beheerde bureaublad van Microsoft, mogen de connectors geen fouten bevatten. Slechts één van de volgende adviezen is van toepassing op uw situatie, dus controleer deze zorgvuldig.

**Advies**

Er zijn geen connectors voor certificaten aanwezig. Het is mogelijk dat u geen connectors nodig hebt, maar u moet evalueren of u mogelijk enkele connectors nodig hebt voor de netwerkconnectiviteit op uw beheerde desktopapparaten van Microsoft. Zie Certificaten en netwerkprofielen voorbereiden voor [het beheerde bureaublad van Microsoft voor meer informatie.](certs-wifi-lan.md)

**Advies**

Ten minste één certificaatconnector heeft een foutmelding. Als u deze connector nodig hebt voor het leveren van certificaten aan apparaten met Beheerd bureaublad van Microsoft, moet u de fout oplossen. Zie Certificaten en netwerkprofielen voorbereiden voor [het beheerde bureaublad van Microsoft voor meer informatie.](certs-wifi-lan.md)


**Advies**

U hebt ten minste één connector voor certificaten en er worden geen fouten gerapporteerd. Ter voorbereiding op de implementatie moet u echter mogelijk een profiel maken om de connector opnieuw te gebruiken voor apparaten met een beheerd bureaublad van Microsoft. Zie Certificaten en netwerkprofielen voorbereiden voor [het beheerde bureaublad van Microsoft voor meer informatie.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Beleidsregels voor voorwaardelijke toegang mogen niet voorkomen dat Microsoft Managed Desktop uw Azure AD-organisatie (tenant) beheert in Intune en Azure AD.

**Nog niet gereed**

U hebt ten minste één beleid voor voorwaardelijke toegang dat is gericht op alle gebruikers. Tijdens de registratie sluiten we microsoft Managed Desktop-serviceaccounts uit van relevante beleidsregels voor voorwaardelijke toegang en passen we nieuw beleid voor voorwaardelijke toegang toe om de toegang tot deze accounts te beperken. Na de registratie kunt u het beleid voor voorwaardelijke toegang van Microsoft Beheerd bureaublad bekijken in Microsoft Endpoint Manager. Zie standaardbesturingssysteemprocedures voor meer informatie over [deze serviceaccounts.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Advies**

U hebt beleidsregels voor voorwaardelijke toegang waardoor de beheerde bureaubladservice van Microsoft niet kan worden beheerd. Tijdens de registratie sluiten we microsoft Managed Desktop-serviceaccounts uit van relevante beleidsregels voor voorwaardelijke toegang en passen we nieuw beleid voor voorwaardelijke toegang toe om de toegang tot deze accounts te beperken. Zie standaardbesturingssysteemprocedures voor meer informatie over [deze serviceaccounts.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fout**

De rol Intune-beheerder heeft onvoldoende machtigingen voor deze controle. U hebt ook een van deze Azure AD-rollen nodig om deze controle uit te voeren:

- Beveiligingslezer
- Beveiligingsbeheerder
- Beheerder van voorwaardelijke toegang
- Algemene lezer
- Apparaatbeheerder


### <a name="device-compliance-policies"></a>Beleid voor apparaat compliance

Intune Device Compliance-beleid in uw Azure AD-organisatie kan van invloed zijn op beheerde Desktop-apparaten van Microsoft.

**Nog niet gereed**

U hebt ten minste één nalevingsbeleid dat is gericht op alle gebruikers. Microsoft Managed Desktop bevat nalevingsbeleidsregels die zijn gericht op uw apparaten met het beheerde bureaublad van Microsoft.  Wijzig het beleid zodat het is gericht op een specifieke Azure AD-groep die geen gebruikers of apparaten met het beheerde bureaublad van Microsoft bevat. Zie Voor de stappen een [nalevingsbeleid maken in Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)

**Advies**

Zorg ervoor dat elk compliancebeleid dat u hebt, niet is gericht op beheerde bureaubladgebruikers van Microsoft. Zie Voor de stappen een [nalevingsbeleid maken in Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Apparaatconfiguratieprofielen

Intune Device Configuration-profielen in uw Azure AD-organisatie mogen niet zijn gericht op bureaubladapparaten of gebruikers van Microsoft Beheren.

**Nog niet gereed**

U hebt ten minste één configuratieprofiel dat is gericht op alle gebruikers, alle apparaten of beide. Stel het profiel opnieuw in op een specifieke Azure AD-groep zonder beheerde bureaubladapparaten van Microsoft. Zie Een profiel maken [met aangepaste instellingen in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor stappen.

**Advies**

Zorg ervoor dat eventuele configuratiebeleidsregels geen beheerde bureaubladapparaten of gebruikers van Microsoft bevatten. Zie Een profiel maken [met aangepaste instellingen in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor stappen.



### <a name="device-type-restrictions"></a>Beperkingen voor apparaattype

Microsoft Managed Desktop-apparaten moeten zijn toegestaan zich in te schrijven bij Intune.

**Nog niet gereed**

Er is momenteel ten minste één registratiebeperkingsbeleid geconfigureerd om te voorkomen dat Windows-apparaten zich registreren bij Intune. Volg de stappen in [Registratiebeperkingen instellen](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) voor elk registratiebeperkingsbeleid dat is gericht op gebruikers van Het beheerde bureaublad van Microsoft en wijzig de **Windows-instelling (MDM)** in **Toestaan.** U kunt echter wel  persoonlijke **Windows-apparaten (MDM)-apparaten** instellen op **Blokkeren.** 


### <a name="enrollment-status-page"></a>Pagina Inschrijvingsstatus

Momenteel is de registratiestatuspagina (ESP) ingeschakeld. Als u van plan bent deel te nemen aan de openbare preview-versie van Microsoft Managed Desktop van deze functie, kunt u dit item negeren. Zie [First-run-ervaring](../get-started/esp-first-run.md)met AutoPilot en de registratiestatuspagina voor meer informatie.

**Nog niet gereed**

Het standaardprofiel van het ESP is ingesteld op De voortgang van de app- en **profielconfiguratie tonen.** Schakel deze instelling uit of zorg ervoor dat toewijzingen aan Azure AD-groepen geen beheerde Bureaublad-apparaten van Microsoft bevatten door de stappen te volgen op de pagina [Inschrijvingsstatus instellen.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

**Advies**

Zorg ervoor dat profielen met de instelling Voortgang van **de app-** en profielconfiguratie weergeven niet zijn toegewezen aan een Azure AD-groep die apparaten bevat met beheerde bureaubladapparaten van Microsoft. Zie De pagina Registratiestatus instellen voor meer [informatie.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store voor Bedrijven

We gebruiken Microsoft Store voor Bedrijven en implementeren de bedrijfsportal-app op Microsoft Managed Desktop zodat gebruikers optioneel bepaalde apps kunnen installeren, zoals Microsoft Project en Microsoft Visio (waar toegestaan).

**Nog niet gereed**

Microsoft Store voor Bedrijven is niet ingeschakeld of wordt niet gesynchroniseerd met Intune. Zie How [to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and Install [Intune Company Portal on devices](../get-started/company-portal.md).

### <a name="multifactor-authentication"></a>Meervoudige verificatie

Meervoudige verificatie mag niet voorkomen dat Microsoft Managed Desktop uw Azure AD-organisatie (tenant) beheert in Intune en Azure AD.


**Nog niet gereed**

U hebt een aantal meervoudige verificatiebeleidsregels ingesteld die zijn **vereist** voor beleidsregels voor voorwaardelijke toegang die aan alle gebruikers zijn toegewezen. Tijdens de registratie sluiten we microsoft Managed Desktop-serviceaccounts uit van relevante beleidsregels voor voorwaardelijke toegang en passen we nieuw beleid voor voorwaardelijke toegang toe om de toegang tot deze accounts te beperken. Zie standaardbesturingssysteemprocedures voor meer informatie over [deze serviceaccounts.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Advies**

Er is meervoudige verificatie vereist voor beleidsregels voor voorwaardelijke toegang waardoor microsoft Beheerd bureaublad de service Microsoft Managed Desktop niet kan beheren. Tijdens de registratie sluiten we microsoft Managed Desktop-serviceaccounts uit van relevante beleidsregels voor voorwaardelijke toegang en passen we nieuw beleid voor voorwaardelijke toegang toe om de toegang tot deze accounts te beperken. Zie standaardbesturingssysteemprocedures voor meer informatie over [deze serviceaccounts.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fout**

De rol Intune-beheerder heeft onvoldoende machtigingen voor deze controle. U hebt ook een van deze Azure AD-rollen nodig om deze controle uit te voeren:

- Beveiligingslezer
- Beveiligingsbeheerder
- Beheerder van voorwaardelijke toegang
- Algemene lezer
- Apparaatbeheerder


### <a name="powershell-scripts"></a>PowerShell-scripts

Windows PowerShell-scripts kunnen niet worden toegewezen op een manier die is gericht op door Microsoft beheerde bureaubladapparaten.  

**Advies**

Zorg ervoor dat Windows PowerShell-scripts in uw Azure AD-organisatie niet zijn gericht op bureaubladapparaten of gebruikers van Microsoft Manage. Wijs geen PowerShell-script toe aan alle gebruikers, alle apparaten of beide. Wijzig het beleid voor het gebruik van een toewijzing die is gericht op een specifieke Azure AD-groep die geen Microsoft Managed Desktop-apparaten of -gebruikers bevat. Zie [PowerShell-scripts gebruiken op Windows 10-apparaten in Intune voor meer informatie.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Regio

Uw regio moet worden ondersteund door het beheerde bureaublad van Microsoft.

**Nog niet gereed**

Uw Azure AD-organisatieregio wordt momenteel niet ondersteund door het beheerde bureaublad van Microsoft. Zie ondersteunde regio's en talen die worden ondersteund door [Microsoft Managed Desktop voor meer informatie.](../service-description/regions-languages.md)

**Advies**

Een of meer landen waarin uw Azure AD-organisatie zich bevindt, worden niet ondersteund door het beheerde bureaublad van Microsoft. Zie ondersteunde regio's en talen die worden ondersteund door [Microsoft Managed Desktop voor meer informatie.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Beveiligingsbasislijnen

Het beveiligingsbasislijnbeleid is niet gericht op beheerde bureaubladapparaten van Microsoft.

**Nog niet gereed**

U hebt een basislijnprofiel voor beveiliging dat is gericht op alle gebruikers, alle apparaten of beide. Wijzig het beleid voor het gebruik van een toewijzing die is gericht op een specifieke Azure AD-groep die geen Microsoft Managed Desktop-apparaten bevat. Zie Beveiligingsbasislijnen gebruiken [om Windows 10-apparaten te](https://docs.microsoft.com/mem/intune/protect/security-baselines)configureren in Intune voor stappen. Tijdens de registratie wordt een nieuwe basislijn voor beveiliging toegepast op alle beheerde bureaubladapparaten van Microsoft. Na de registratie kunt u het basislijnbeleid voor de beveiliging van Het beheerde bureaublad bekijken in **het** gebied Configuratiebeleid van Microsoft Endpoint Manager.

**Advies**

Zorg ervoor dat u beveiligingsbasislijnbeleidsregels uitsluit die zijn uitgesloten van beheerde bureaubladapparaten van Microsoft. Zie Beveiligingsbasislijnen gebruiken [om Windows 10-apparaten te](https://docs.microsoft.com/mem/intune/protect/security-baselines)configureren in Intune voor stappen. Tijdens de registratie wordt een nieuwe basislijn voor beveiliging toegepast op alle beheerde bureaubladapparaten van Microsoft. De **groep Modern Workplace Devices -All** Azure AD is een dynamische groep die we maken wanneer u zich inschrijft voor Microsoft Managed Desktop, dus u moet teruggaan om deze groep na de inschrijving uit te sluiten. 


### <a name="windows-apps"></a>Windows-apps

Controleer de apps die uw Microsoft Managed Desktop-gebruikers moeten hebben.

**Advies**

Maak een inventaris van de apps die uw gebruikers van Het beheerde bureaublad van Microsoft moeten hebben. Aangezien deze apps door Intune moeten worden geïmplementeerd, kunt u bestaande Intune-apps hergebruiken. Overweeg om bedrijfsportal te gebruiken (zie [Intune-bedrijfsportal](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) installeren op apparaten en registratiestatuspagina (ESP) om apps naar uw gebruikers te distribueren. Zie Apps [in Microsoft Managed Desktop](apps.md) en [First-run experience](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)met Autopilot en de statuspagina Inschrijving voor meer informatie.

U kunt uw Microsoft-accountvertegenwoordiger vragen om een query in Microsoft Endpoint Configuration Manager om te bepalen welke apps klaar zijn om te worden gemigreerd naar Intune of die moeten worden aangepast.


### <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven

Voor het beheerde bureaublad van Microsoft moet Windows Hello voor Bedrijven zijn ingeschakeld.

**Nog niet gereed**

Windows Hello voor Bedrijven is uitgeschakeld. Schakel dit in door de stappen te volgen in [Beleid voor Windows Hello voor Bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Advies**

Windows Hello voor Bedrijven is niet ingesteld. Schakel dit in door de stappen te volgen in [Beleid voor Windows Hello voor Bedrijven maken.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Updateringen voor Windows 10

Uw updateringsbeleid voor Windows 10 in Intune mag niet zijn gericht op beheerde Desktop-apparaten van Microsoft.

**Nog niet gereed**

U hebt een update-ringbeleid dat is gericht op alle apparaten, alle gebruikers of beide. Wijzig het beleid voor het gebruik van een toewijzing die is gericht op een specifieke Azure AD-groep die geen microsoft beheerde bureaubladapparaten bevat. Zie Windows [10-software-updates beheren in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor stappen.

**Advies**

Zorg ervoor dat updateringsbeleid dat u hebt uitgesloten van de **Groep Modern Workplace Devices -All** Azure AD. Als u Azure AD-gebruikersgroepen aan dit beleid hebt toegewezen, moet u ervoor zorgen dat updateringsbeleid dat u ook hebt uitgesloten van de **Modern Workplace -Alle** Azure AD-groep waar u uw Microsoft Managed Desktop-gebruikers aan toevoegt (of een equivalente groep). Zie Windows [10-software-updates beheren in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor stappen. De **Modern Workplace Devices (All)** en **Modern Workplace -all** Azure AD-groepen zijn groepen die we maken wanneer u zich inschrijft voor Microsoft Managed Desktop, dus u moet teruggaan om deze groep uit te sluiten na de registratie.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

U kunt de instellingen voor Azure Active Directory openen in [de Azure Portal.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Intune-inschrijving

Windows 10-apparaten in uw Azure AD-organisatie moeten zich automatisch kunnen registreren bij Intune.

**Advies**

Zorg ervoor dat het **bereik van de MDM-gebruiker** is ingesteld op **Sommige** of **Alle,** niet **op Geen.** Als u **Sommige** kiest, komt u terug na de inschrijving en selecteert u de Azure AD-groep Modern **Workplace -All** Azure AD **voor** groepen of een equivalente groep die is gericht op al uw microsoft Beheerd bureaublad-gebruikers.  Zie [Inschrijving voor Windows-apparaten instellen met Microsoft Intune.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Ad-hocabonnementen

U wordt geadviseerd om een instelling te controleren die (indien ingesteld op Onwaar) kan verhinderen dat Enterprise State Roaming correct werkt.

**Advies**

Zorg ervoor **dat AllowAdHocSubscriptions** is ingesteld op **Waar.** Anders werkt Enterprise State Roaming mogelijk niet. Zie [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)voor meer informatie.


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming moet zijn ingeschakeld.

**Advies**

Zorg ervoor dat Enterprise State Roaming is ingeschakeld voor **Alle** of voor **geselecteerde** groepen. Zie [Enterprise State Roaming inschakelen in Azure Active Directory voor meer informatie.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Licenties

Er zijn een aantal licenties vereist voor het gebruik van Het beheerde bureaublad van Microsoft.

**Niet gereed**

U hebt niet alle licenties die u nodig hebt om Microsoft Managed Desktop te gebruiken. Zie Microsoft [Managed Desktop Technologies](../intro/technologies.md) en Meer informatie over licenties voor meer [informatie.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Managed Desktop Service-accounts

Bepaalde accountnamen kunnen conflicteren met accountnamen die zijn gemaakt door Beheerd bureaublad van Microsoft om de service Microsoft Managed Desktop te beheren.

**Nog niet gereed**

U hebt ten minste één accountnaam die strijdig is met accountnamen die zijn gemaakt met het beheerde bureaublad van Microsoft. Werk samen met uw Microsoft-accountvertegenwoordiger om deze accountnamen uit te sluiten. De accountnamen worden niet openbaar weergegeven om het beveiligingsrisico te minimaliseren. 


### <a name="security-administrator-roles"></a>Rollen van beveiligingsbeheerders

Gebruikers met bepaalde beveiligingsrollen moeten deze rollen hebben toegewezen in Microsoft Defender voor eindpunt.

**Advies**

Als u gebruikers hebt toegewezen aan een van deze rollen in uw Azure AD-organisatie, zorg er dan voor dat er ook deze rollen zijn toegewezen in Microsoft Defender voor Eindpunt. Beheerders met deze rollen hebben anders geen toegang tot de beheerportal.

- Beveiligingsoperator
- Algemene lezer

Zie Rollen maken en beheren voor toegangsbeheer op basis van rollen [voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Standaardbeveiliging

Met beveiligingsinstellingen in Azure Active Directory wordt voorkomen dat uw apparaten worden beheerd door Microsoft Managed Desktop.

**Nog niet gereed**

Beveiligingsinstellingen zijn ingeschakeld. Schakel beveiligingsinstellingen uit en stel beleid voor voorwaardelijke toegang in. Zie Veelvoorkomende beleidsregels [voor voorwaardelijke toegang voor meer informatie.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Selfservice voor wachtwoord opnieuw instellen

Selfservice voor wachtwoord opnieuw instellen (SSPR) kan worden ingeschakeld voor alle gebruikers van het beheerde bureaublad van Microsoft, met uitzondering van accounts van de beheerde desktopservice van Microsoft. Zie Zelfstudie: Gebruikers in staat stellen hun account te ontgrendelen of wachtwoorden opnieuw in te stellen met de selfservice voor wachtwoord opnieuw instellen van [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)

**Advies**

Zorg ervoor dat de  geselecteerde SSPR-instelling gebruikers van het beheerde bureaublad van Microsoft bevat, maar dat serviceaccounts van het beheerde bureaublad van Microsoft worden uitgesloten. Microsoft Managed Desktop-serviceaccounts werken niet zoals verwacht wanneer SSPR is ingeschakeld.  


### <a name="standard-user-role"></a>Standaardgebruikersrol

Met andere woorden, dan de gebruikers aan wie de Azure AD-rol van globale beheerder en apparaatbeheerder is toegewezen, zijn Microsoft Managed Desktop-gebruikers standaardgebruikers zonder lokale beheerdersbevoegdheden. Aan alle andere gebruikers wordt een standaardgebruikersrol toegewezen wanneer ze hun apparaat met het beheerde bureaublad van Microsoft starten.

**Advies**

Gebruikers van het beheerde bureaublad van Microsoft hebben na registratie geen lokale beheerdersbevoegdheden op hun Microsoft Managed Desktop-apparaten.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365-apps voor ondernemingen

### <a name="onedrive"></a>OneDrive

Synchronisatie **toestaan alleen voor pc's die lid** zijn van een bepaalde instelling voor domeinen, conflicteert met het beheerde bureaublad van Microsoft. U kunt de OneDrive-instellingen openen in het [OneDrive-beheercentrum.](https://admin.onedrive.com)

**Advies**

U gebruikt synchronisatie alleen toestaan op pc's die lid zijn **van specifieke domeinen.** Deze instelling werkt niet met het beheerde bureaublad van Microsoft. Schakel deze instelling uit en stel in plaats daarvan OneDrive in voor het gebruik van een beleid voor voorwaardelijke toegang. Zie [Een voorwaardelijke toegang-implementatie plannen](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) voor hulp.
