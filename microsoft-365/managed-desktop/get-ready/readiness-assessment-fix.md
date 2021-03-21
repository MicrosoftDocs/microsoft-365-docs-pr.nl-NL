---
title: Los problemen op die door het hulpprogramma voor gereedheidsevaluatie worden gevonden
description: Gedetailleerde acties die moeten worden ondernomen voor elk probleem dat door het hulpprogramma wordt gevonden
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75c2967037ae83abca2aaa3cd02d1f6b2ae14caa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925914"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Los problemen op die door het hulpprogramma voor gereedheidsevaluatie worden gevonden

Voor elke controle rapporteert het hulpprogramma een van de vier mogelijke resultaten:


|Resultaat  |Betekenis  |
|---------|---------|
|Gereed     | Er is geen actie vereist voordat u zich inschrijft.        |
|Advies    | Volg de stappen in het hulpprogramma of dit artikel voor de beste ervaring met registratie en voor gebruikers. U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.        |
|Nog niet klaar | *De inschrijving mislukt als u deze problemen niet op kunt lossen.* Volg de stappen in het hulpprogramma of dit artikel om deze op te lossen.        |
|Error | De Azure Active Directory-rol (AD) die u gebruikt, heeft niet voldoende machtigingen om deze controle uit te voeren. |

> [!NOTE]
> De resultaten die door dit hulpprogramma worden gerapporteerd, geven alleen de status van uw instellingen weer op het specifieke moment dat u de instellingen hebt gebruikt. Als u later wijzigingen aan het beleid aan gaat brengen in Microsoft Intune, Azure Active Directory of Microsoft 365, kunnen items die 'Gereed' waren, 'Niet klaar' worden. Als u problemen met Microsoft Managed Desktop-bewerkingen wilt voorkomen, controleert u de specifieke instellingen die in dit artikel worden beschreven voordat u beleid wijzigt.

## <a name="microsoft-intune-settings"></a>Microsoft Intune-instellingen

U hebt toegang tot Intune-instellingen in het Microsoft Endpoint [Manager-beheercentrum.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Autopilot-implementatieprofiel

U mag geen bestaande Autopilot-profielen hebben die zich richten op toegewezen of dynamische groepen met Microsoft Managed Desktop-apparaten. Microsoft Managed Desktop gebruikt Autopilot om nieuwe apparaten in te delen.

**Nog niet klaar**

U hebt een Autopilot-profiel dat is toegewezen aan alle apparaten. Zie Windows-apparaten [registreren in Intune met Windows Autopilot](/mem/autopilot/enrollment-autopilot)voor stappen. Nadat Microsoft Managed Desktop is ingeschreven, stelt u uw Autopilot-beleid in om de groep Moderne werkplekapparaten **-Alle** Azure AD-apparaten uit te sluiten.

**Advies**

Zorg ervoor dat uw Autopilot-profielen zijn gericht op een toegewezen of dynamische Azure AD-groep die geen Microsoft Managed Desktop-apparaten bevat. Zie Windows-apparaten [registreren in Intune met Windows Autopilot](/mem/autopilot/enrollment-autopilot)voor stappen. Nadat Microsoft Managed Desktop is ingeschreven, stelt u uw Autopilot-profielen in om de groep Moderne werkplekapparaten **-Alle** Azure AD-apparaten uit te sluiten.


### <a name="certificate-connectors"></a>Connectors voor certificaten

Als u een certificaatconnector hebt die wordt gebruikt door de apparaten die u wilt registreren in Microsoft Managed Desktop, mogen de connectors geen fouten bevatten. Slechts een van de volgende adviezen is van toepassing op uw situatie, dus controleer ze zorgvuldig.

**Advies**

Er zijn geen certificaatconnectoren aanwezig. Het is mogelijk dat u geen verbindingslijnen nodig hebt, maar u moet evalueren of u mogelijk een netwerkverbinding nodig hebt op uw Microsoft Managed Desktop-apparaten. Zie Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop voor [meer informatie.](certs-wifi-lan.md)

**Advies**

Ten minste één certificaatconnector heeft een foutmelding. Als u deze connector nodig hebt voor het verstrekken van certificaten aan Microsoft Managed Desktop-apparaten, moet u de fout oplossen. Zie Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop voor [meer informatie.](certs-wifi-lan.md)


**Advies**

U hebt ten minste één certificaatconnector en er worden geen fouten gerapporteerd. Ter voorbereiding op de implementatie moet u echter mogelijk een profiel maken om de connector opnieuw te gebruiken voor beheerde bureaubladapparaten van Microsoft. Zie Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop voor [meer informatie.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Beleid voor voorwaardelijke toegang mag niet voorkomen dat Microsoft Managed Desktop uw Azure AD-organisatie (tenant) beheert in Intune en Azure AD.

**Nog niet klaar**

U hebt ten minste één beleid voor voorwaardelijke toegang dat is gericht op alle gebruikers. Tijdens de inschrijving sluiten we Microsoft Managed Desktop-serviceaccounts uit van relevante beleidsregels voor voorwaardelijke toegang en passen we nieuw beleid voor voorwaardelijke toegang toe om de toegang tot deze accounts te beperken. Nadat u zich hebt ingeschreven, kunt u het beleid voor voorwaardelijke toegang van Microsoft Managed Desktop in Microsoft Endpoint Manager bekijken. Zie Standaardbesturingssystemen voor meer informatie over [deze serviceaccounts.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Advies**

U hebt beleid voor voorwaardelijke toegang waardoor Microsoft Managed Desktop de Microsoft Managed Desktop-service niet kan beheren. Tijdens de inschrijving sluiten we Microsoft Managed Desktop-serviceaccounts uit van relevante beleidsregels voor voorwaardelijke toegang en passen we nieuw beleid voor voorwaardelijke toegang toe om de toegang tot deze accounts te beperken. Zie Standaardbesturingssystemen voor meer informatie over [deze serviceaccounts.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fout**

De rol Intune-beheerder heeft niet voldoende machtigingen voor deze controle. U hebt ook een van deze Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:

- Beveiligingslezer
- Beveiligingsbeheerder
- Beheerder van voorwaardelijke toegang
- Algemene lezer
- Apparatenbeheerder


### <a name="device-compliance-policies"></a>Beleid voor apparaat compliance

Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.

**Nog niet klaar**

U hebt ten minste één compliancebeleid dat is gericht op alle gebruikers. Microsoft Managed Desktop bevat compliancebeleid dat is gericht op uw Microsoft Managed Desktop-apparaten.  Wijzig het beleid om een specifieke Azure AD-groep te targeten die geen Microsoft Managed Desktop-gebruikers of -apparaten bevat. Zie Een [compliancebeleid maken in Microsoft Intune](/mem/intune/protect/create-compliance-policy)voor stappen.

**Advies**

Zorg ervoor dat alle nalevingsbeleidsregels die u hebt, niet zijn gericht op gebruikers van Microsoft Managed Desktop. Zie Een [compliancebeleid maken in Microsoft Intune](/mem/intune/protect/create-compliance-policy)voor stappen.



### <a name="device-configuration-profiles"></a>Apparaatconfiguratieprofielen

Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.

**Nog niet klaar**

U hebt ten minste één configuratieprofiel dat is gericht op alle gebruikers, alle apparaten of beide. Stel het profiel opnieuw in op een specifieke Azure AD-groep die geen Microsoft Managed Desktop-apparaten bevat. Zie Een profiel maken [met aangepaste instellingen in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)voor stappen.

**Advies**

Zorg ervoor dat alle configuratiebeleidsregels die u hebt, geen Microsoft Managed Desktop-apparaten of -gebruikers bevatten. Zie Een profiel maken [met aangepaste instellingen in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)voor stappen.



### <a name="device-type-restrictions"></a>Beperkingen voor apparaattype

Microsoft Managed Desktop-apparaten moeten zijn toegestaan zich in Tetune in te schrijven.

**Nog niet klaar**

U hebt momenteel ten minste één registratiebeperkingsbeleid geconfigureerd om te voorkomen dat Windows-apparaten zich kunnen registreren in Intune. Volg de stappen in [Registratiebeperkingen instellen](/mem/intune/enrollment/enrollment-restrictions-set) voor elk registratiebeperkingsbeleid dat is gericht op gebruikers van Microsoft Managed Desktop en wijzig de **windows-instelling (MDM)** in **Toestaan.** U kunt echter alle  persoonlijke **Windows-apparaten (MDM)** instellen op **Blokkeren.** 


### <a name="enrollment-status-page"></a>Pagina Inschrijvingsstatus

Op dit moment is de pagina Inschrijvingsstatus (ESP) ingeschakeld. Als u van plan bent deel te nemen aan het openbare voorbeeld van Microsoft Managed Desktop van deze functie, kunt u dit item negeren. Zie [First-run experience with Autopilot and the Enrollment Status Page (First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md)) voor meer informatie.

**Nog niet klaar**

U hebt het standaardprofiel ESP ingesteld op **Voortgang van de app- en profielconfiguratie tonen.** Schakel deze instelling uit of zorg ervoor dat toewijzingen aan een Azure AD-groep geen Microsoft Managed Desktop-apparaten bevatten door de stappen in De pagina Registratiestatus instellen [te volgen.](/mem/intune/enrollment/windows-enrollment-status)

**Advies**

Zorg ervoor dat profielen met de instelling **App-** en profielconfiguratie weergeven niet zijn toegewezen aan een Azure AD-groep met Microsoft Managed Desktop-apparaten. Zie De pagina Registratiestatus instellen voor [meer informatie.](/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store voor Bedrijven

We gebruiken Microsoft Store voor Bedrijven en implementeren de bedrijfsportal-app op Microsoft Managed Desktop, zodat gebruikers desgewenst bepaalde apps kunnen installeren, zoals Microsoft Project en Microsoft Visio (indien toegestaan).

**Nog niet klaar**

Microsoft Store voor Bedrijven is niet ingeschakeld of wordt niet gesynchroniseerd met Intune. Zie Voor meer informatie [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and Install [Intune Company Portal on devices](../get-started/company-portal.md).

### <a name="multifactor-authentication"></a>Meervoudige verificatie

Meervoudige verificatie mag niet voorkomen dat Microsoft Managed Desktop uw Azure AD-organisatie (tenant) beheert in Intune en Azure AD.


**Nog niet klaar**

U hebt een aantal beleidsregels voor meervoudige verificatie ingesteld, zoals vereist **voor** beleid voor voorwaardelijke toegang dat aan alle gebruikers is toegewezen. Tijdens de inschrijving sluiten we Microsoft Managed Desktop-serviceaccounts uit van relevante beleidsregels voor voorwaardelijke toegang en passen we nieuw beleid voor voorwaardelijke toegang toe om de toegang tot deze accounts te beperken. Zie Standaardbesturingssystemen voor meer informatie over [deze serviceaccounts.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Advies**

U hebt meervoudige verificatie vereist voor beleidsregels voor voorwaardelijke toegang, waardoor Microsoft Managed Desktop de Microsoft Managed Desktop-service niet kan beheren. Tijdens de inschrijving sluiten we Microsoft Managed Desktop-serviceaccounts uit van relevante beleidsregels voor voorwaardelijke toegang en passen we nieuw beleid voor voorwaardelijke toegang toe om de toegang tot deze accounts te beperken. Zie Standaardbesturingssystemen voor meer informatie over [deze serviceaccounts.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fout**

De rol Intune-beheerder heeft niet voldoende machtigingen voor deze controle. U hebt ook een van deze Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:

- Beveiligingslezer
- Beveiligingsbeheerder
- Beheerder van voorwaardelijke toegang
- Algemene lezer
- Apparatenbeheerder


### <a name="powershell-scripts"></a>PowerShell-scripts

Windows PowerShell-scripts kunnen niet worden toegewezen op een manier die is gericht op Beheerde bureaubladapparaten van Microsoft.  

**Advies**

Zorg ervoor dat Windows PowerShell-scripts in uw Azure AD-organisatie niet zijn gericht op Microsoft Manage Desktop-apparaten of gebruikers. Wijs geen PowerShell-script toe om alle gebruikers, alle apparaten of beide te targeten. Wijzig het beleid voor het gebruik van een toewijzing die is gericht op een specifieke Azure AD-groep die geen Microsoft Managed Desktop-apparaten of -gebruikers bevat. Zie [PowerShell-scripts gebruiken op Windows 10-apparaten in Intune](/mem/intune/apps/intune-management-extension)voor meer informatie.

### <a name="region"></a>Regio

Uw regio moet worden ondersteund door Microsoft Managed Desktop.

**Nog niet klaar**

Uw Azure AD-organisatieregio wordt momenteel niet ondersteund door Microsoft Managed Desktop. Zie ondersteunde regio's en talen voor [Microsoft Managed Desktop voor meer informatie.](../service-description/regions-languages.md)

**Advies**

Een of meer landen waar uw Azure AD-organisatie zich bevindt, worden niet ondersteund door Microsoft Managed Desktop. Zie ondersteunde regio's en talen voor [Microsoft Managed Desktop voor meer informatie.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Beveiligingslijnlijnen

Beveiligingslijnbeleid mag niet zijn gericht op beheerde bureaubladapparaten van Microsoft.

**Nog niet klaar**

U hebt een beveiligingslijnprofiel dat is gericht op alle gebruikers, alle apparaten of beide. Wijzig het beleid voor het gebruik van een toewijzing die is gericht op een specifieke Azure AD-groep die geen Microsoft Managed Desktop-apparaten bevat. Zie Beveiligingslijnlijnen gebruiken om [Windows 10-apparaten in Intune te configureren voor stappen.](/mem/intune/protect/security-baselines) Tijdens de inschrijving passen we een nieuwe beveiligingslijn toe op alle beheerde bureaubladapparaten van Microsoft. Na de registratie kunt u het beveiligingslijnbeleid voor Microsoft Managed Desktop bekijken in **het beleidsgebied** Configuratie van Microsoft Endpoint Manager.

**Advies**

Zorg ervoor dat een beveiligingslijnbeleid dat u hebt uitgesloten van Microsoft Managed Desktop-apparaten. Zie Beveiligingslijnlijnen gebruiken om [Windows 10-apparaten in Intune te configureren voor stappen.](/mem/intune/protect/security-baselines) Tijdens de inschrijving passen we een nieuwe beveiligingslijn toe op alle beheerde bureaubladapparaten van Microsoft. De **groep Moderne werkplekapparaten -Alle** Azure AD-groep is een dynamische groep die we maken wanneer u zich inschrijft voor Microsoft Managed Desktop, dus u moet terugkomen om deze groep uit te sluiten na de inschrijving. 


### <a name="windows-apps"></a>Windows-apps

Bekijk apps die uw Microsoft Managed Desktop-gebruikers moeten hebben.

**Advies**

U moet een inventaris maken van de apps die uw Microsoft Managed Desktop-gebruikers moeten hebben. Aangezien deze apps moeten worden geïmplementeerd door Intune, evalueert u het hergebruik van bestaande Intune-apps. Overweeg bedrijfsportal te gebruiken (zie [Intune Company Portal installeren](../get-started/company-portal.md) op apparaten en registratiestatuspagina (ESP) om apps te distribueren naar uw gebruikers. Zie Apps [in Microsoft Managed Desktop](apps.md) en First-run experience with Autopilot and the Enrollment Status Page (Apps in Microsoft Managed Desktop and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md)) voor meer informatie.

U kunt uw Microsoft-accountvertegenwoordiger vragen om een query in Microsoft Endpoint Configuration Manager om te bepalen welke apps klaar zijn om te migreren naar Intune of die aanpassing nodig hebben.


### <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven

Microsoft Managed Desktop vereist dat Windows Hello voor Bedrijven is ingeschakeld.

**Nog niet klaar**

Windows Hello voor Bedrijven is uitgeschakeld. Schakel dit in door de stappen te volgen in [Een Windows Hello voor Bedrijven-beleid maken](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Advies**

Windows Hello voor Bedrijven is niet ingesteld. Schakel dit in door de stappen te volgen in [Een Windows Hello voor Bedrijven-beleid maken.](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Windows 10-updateringen

Uw 'Windows 10 Update Ring'-beleid in Intune mag niet zijn gericht op beheerde bureaubladapparaten van Microsoft.

**Nog niet klaar**

U hebt een updateringsbeleid dat is gericht op alle apparaten, alle gebruikers of beide. Wijzig het beleid voor het gebruik van een toewijzing die is gericht op een specifieke Azure AD-groep die geen Microsoft Managed Desktop-apparaten bevat. Zie Windows [10-software-updates beheren in Intune](/mem/intune/protect/windows-update-for-business-configure)voor stappen.

**Advies**

Zorg ervoor dat het updateringsbeleid dat u hebt uitgevoerd, de groep Moderne werkplekapparaten **-Alle** Azure AD-apparaten uitsluit. Als u Azure AD-gebruikersgroepen aan dit beleid hebt toegewezen, moet u ervoor zorgen dat elk updateringsbeleid dat u ook hebt uitgesloten van de **groep Modern Workplace -All** Azure AD waar u uw Microsoft Managed Desktop-gebruikers aan toevoegt (of een vergelijkbare groep). Zie Windows [10-software-updates beheren in Intune](/mem/intune/protect/windows-update-for-business-configure)voor stappen. Zowel de **moderne werkplekapparaten -All** als **Modern Workplace -** Alle Azure AD-groepen zijn groepen die we maken wanneer u zich inschrijft voor Microsoft Managed Desktop, dus u moet terugkomen om deze groep uit te sluiten na de inschrijving.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

U hebt toegang tot Azure Active Directory-instellingen op de [Azure-portal.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Inschrijving voor Intune

Windows 10-apparaten in uw Azure AD-organisatie moeten zich automatisch kunnen registreren bij Intune.

**Advies**

Zorg ervoor dat **het MDM-gebruikersbereik** is ingesteld op **Aantal** of **Alles,** niet **Op Geen.** Als u **Sommige kiest,** komt u na de inschrijving terug en  selecteert u de groep Moderne werkplek **-Alle** Azure AD voor groepen of een vergelijkbare groep die is gericht op al uw Microsoft Managed Desktop-gebruikers.  Zie [Inschrijving instellen voor Windows-apparaten met Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).


### <a name="ad-hoc-subscriptions"></a>Ad hoc-abonnementen

U wordt geadviseerd om een instelling te controleren die (indien ingesteld op 'onwaar') kan voorkomen dat Enterprise State Roaming correct werkt.

**Advies**

Controleer of **AllowAdHocSubscriptions** is ingesteld op **Waar.** Anders werkt Enterprise State Roaming mogelijk niet. Zie [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)voor meer informatie.


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming moet zijn ingeschakeld.

**Advies**

Zorg ervoor dat Enterprise State Roaming is ingeschakeld voor **Alle** of voor **Geselecteerde** groepen. Zie Enterprise [State Roaming inschakelen in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)voor meer informatie.

### <a name="licenses"></a>Licenties

Er zijn een aantal licenties vereist voor het gebruik van Microsoft Managed Desktop.

**Niet gereed**

U hebt niet alle licenties die u nodig hebt om Microsoft Managed Desktop te gebruiken. Zie Microsoft [Managed Desktop-technologieën](../intro/technologies.md) en [Meer informatie over licenties voor meer informatie.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Managed Desktop-serviceaccounts

Bepaalde accountnamen kunnen conflicteren met accountnamen die zijn gemaakt door Microsoft Managed Desktop om de Microsoft Managed Desktop-service te beheren.

**Nog niet klaar**

U hebt ten minste één accountnaam die strijdig is met accountnamen die zijn gemaakt door Microsoft Managed Desktop. Werk samen met uw Microsoft-accountvertegenwoordiger om deze accountnamen uit te sluiten. We geven de accountnamen niet openbaar weer om het beveiligingsrisico te minimaliseren. 


### <a name="security-administrator-roles"></a>Beveiligingsbeheerdersrollen

Gebruikers met bepaalde beveiligingsrollen moeten deze rollen hebben toegewezen in Microsoft Defender voor Eindpunt.

**Advies**

Als u gebruikers hebt toegewezen aan een van deze rollen in uw Azure AD-organisatie, moet u ervoor zorgen dat deze rollen ook zijn toegewezen in Microsoft Defender voor Eindpunt. Anders hebben beheerders met deze rollen geen toegang tot de beheerportal.

- Beveiligingsoperator
- Algemene lezer

Zie Rollen maken en beheren voor op rollen [gebaseerd toegangsbeheer voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Beveiligings standaard

Beveiligings defaults in Azure Active Directory voorkomen dat Microsoft Managed Desktop uw apparaten kan beheren.

**Nog niet klaar**

Beveiligingsinstellingen zijn ingeschakeld. Beveiligingsinstellingen uitschakelen en beleidsregels voor voorwaardelijke toegang instellen. Zie Gemeenschappelijk beleid voor voorwaardelijke toegang voor [meer informatie.](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Selfservice Password Reset

Selfservice Password Reset (SSPR) kan worden ingeschakeld voor alle Microsoft Managed Desktop-gebruikers, met uitzondering van Microsoft Managed Desktop-serviceaccounts. Zie Zelfstudie: Gebruikers in staat stellen hun account te ontgrendelen of wachtwoorden opnieuw in te stellen met [azure Active Directory selfservice wachtwoord opnieuw instellen](/azure/active-directory/authentication/tutorial-enable-sspr)voor meer informatie.

**Advies**

Zorg ervoor dat de instelling SSPR **Selected** Microsoft Managed Desktop-gebruikers bevat, maar microsoft Managed Desktop-serviceaccounts uitsluit. Microsoft Managed Desktop-serviceaccounts kunnen niet werken zoals verwacht wanneer SSPR is ingeschakeld.  


### <a name="standard-user-role"></a>Standaardgebruikerrol

Anders dan gebruikers aan wie Azure AD-rollen van globale beheerder en apparaatbeheerder zijn toegewezen, zijn Microsoft Managed Desktop-gebruikers standaardgebruikers zonder lokale beheerdersbevoegdheden. Aan alle andere gebruikers wordt een standaardgebruikersrol toegewezen wanneer ze hun Microsoft Managed Desktop-apparaat starten.

**Advies**

Microsoft Managed Desktop-gebruikers hebben na registratie geen lokale beheerdersbevoegdheden op hun Microsoft Managed Desktop-apparaten.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps voor ondernemingen

### <a name="onedrive"></a>OneDrive

De **instelling Alleen synchroniseren toestaan op pc's die** zijn verbonden met specifieke domeinen, conflicteert met Beheerd bureaublad van Microsoft. U hebt toegang tot OneDrive-instellingen in het [OneDrive-beheercentrum.](https://admin.onedrive.com)

**Advies**

U gebruikt de instelling **Alleen synchroniseren toestaan op pc's** die zijn aangesloten bij specifieke domeinen. Deze instelling werkt niet met Beheerd bureaublad van Microsoft. Schakel deze instelling uit en stel in plaats daarvan OneDrive in om een beleid voor voorwaardelijke toegang te gebruiken. Zie [Een implementatie van voorwaardelijke toegang plannen](/azure/active-directory/conditional-access/plan-conditional-access) voor hulp.