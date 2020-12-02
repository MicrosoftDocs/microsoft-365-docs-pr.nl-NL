---
title: Problemen gevonden met het hulpprogramma voor gereedheids beoordeling
description: Gedetailleerde stappen voor elk probleem dat met het hulpprogramma wordt gevonden
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f23209568fcfc2db4a22dbb034890c5a25e21bf7
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527731"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Problemen gevonden met het hulpprogramma voor gereedheids beoordeling

Voor elke controle wordt in het hulpmiddel een van de vier mogelijke resultaten weergegeven:


|Resultaat  |Betekenis  |
|---------|---------|
|Gereedgemaakt     | U hoeft geen actie te ondernemen voordat u de registratie uitvoert.        |
|Adviser    | Voer de stappen in het hulpprogramma of dit artikel uit voor de beste ervaring met inschrijving en voor gebruikers. U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.        |
|Niet gereed | *De registratie mislukt als u deze problemen niet oplost.* Voer de stappen in het hulpprogramma of dit artikel uit om ze op te lossen.        |
|Error | De rol van Azure Active Director (AD) die u gebruikt, heeft onvoldoende machtigingen om deze controle uit te voeren. |

## <a name="microsoft-intune-settings"></a>Microsoft intune-instellingen

U kunt de intune-instellingen openen via het [Beheercentrum](https://endpoint.microsoft.com)van Microsoft Endpoint Manager.

### <a name="autopilot-deployment-profile"></a>Auto Pilot-implementatie profiel

U hebt geen bestaande auto pilot-profielen die door Microsoft beheerde bureaublad worden toegewezen of dynamische groepen die door Microsoft worden beheerd. Microsoft Managed Desktop gebruikt auto pilot om nieuwe apparaten te creëren.

**Niet gereed**

U hebt een auto pilot-profiel dat is toegewezen aan alle apparaten. Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies. Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.

**Adviser**

Zorg ervoor dat uw auto pilot-profielen een toegewezen of dynamische Azure AD-groep betreffen die geen door Microsoft beheerde bureaublad apparaten bevat die worden gemaakt bij het registreren. Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies. Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.


### <a name="certificate-connectors"></a>Certificaat verbindingslijnen

Als u certificaat verbindingslijnen hebt die worden gebruikt door de apparaten die u wilt registreren op Microsoft Managed Desktop, zijn de connectors geen fouten. Slechts één van de volgende adviseurs is op uw situatie van toepassing, dus controleer ze aandachtig.

**Adviser**

Er zijn geen certificaat connectors aanwezig. Het is mogelijk dat u geen connectors nodig hebt, maar u moet eerst beoordelen of u een netwerkverbinding met Microsoft beheerde bureaublad apparaten nodig hebt. Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.

**Adviser**

Minstens één certificaatconnector bevat een fout. Als u deze connector nodig hebt voor connectiviteit met Microsoft Managed Desktop-apparaten, moet u de fout oplossen. Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.


**Adviser**

U moet minimaal één certificaatconnector en geen fouten rapporteren. U kunt echter wel een profiel maken om de connector voor Microsoft beheerde bureaublad apparaten opnieuw te gebruiken. Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.


### <a name="conditional-access-policies"></a>Beleidsregels voor voorwaardelijke toegang

Het beleid voor voorwaardelijke toegang in uw Azure AD-organisatie mag geen Microsoft-bureaubladgebruikers bedoelen.

**Niet gereed**

U hebt ten minste één beleid voor voorwaardelijke toegang voor alle gebruikers. Stel het beleid opnieuw in om een specifieke Azure AD-groep met de Azure AD-groep met Microsoft Managed Desktop service-accounts die worden gemaakt bij het registreren, niet te omvatten. Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).

**Adviser**

Zorg ervoor dat u een beleidsregels voor voorwaardelijke toegang hebt uitgesloten met de Azure AD-groep voor de **moderne service accounts** . Zie [voorwaardelijke toegang aanpassen](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)voor de stappen. De **modern Workplace service accounts** Azure Ad Group is een dynamische groep die we voor de service maken wanneer u zich registreert. U dient na de inschrijving weer de groep uit te sluiten. Zie voor meer informatie over deze serviceaccounts [standaardprocedures](../service-description/operations-and-monitoring.md#standard-operating-procedures)voor het werk.

**Fout**

De rol intune-beheerder heeft onvoldoende machtigingen voor deze controle. U hebt ook een van de volgende Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:

- Beveiligings lezer
- Beveiligingsbeheerder
- Beheerder van voorwaardelijke toegang
- Algemene lezer
- Apparaten beheerder


### <a name="device-compliance-policies"></a>Nalevingsbeleid voor apparaten

Het beleid voor naleving van intune-apparaten in de Azure AD-organisatie mag geen door Microsoft beheerde bureaubladgebruikers afstemmen.

**Niet gereed**

U hebt ten minste één nalevingsbeleid voor alle gebruikers. Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen Microsoft-beheerde bureaubladgebruikers omvat. Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.

**Adviser**

Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaubladgebruikers niet omvat. Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.



### <a name="device-configuration-policies"></a>Beleidsregels voor apparaatconfiguratie

Het beleid voor het configureren van intune-apparaten in de Azure AD-organisatie mag geen Microsoft-bureaublad apparaten of-gebruikers beheren.

**Niet gereed**

U hebt minimaal één configuratiebeleid voor alle gebruikers, alle apparaten of beide. Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen door Microsoft beheerde bureaublad apparaten bevat. Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.

**Adviser**

Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaublad apparaten of gebruikers niet omvat. Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.



### <a name="device-type-restrictions"></a>Beperkingen voor apparaattype

Door Microsoft beheerde bureaublad apparaten moet u zich kunnen registreren bij intune.

**Niet gereed**

Voer de stappen uit in de optie voor het [instellen van inschrijving](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) om de **instelling toe te passen.**


### <a name="enrollment-status-page"></a>Pagina met inschrijvings status

U hebt momenteel de pagina met de inschrijvings status (ESP) ingeschakeld. Als u deelneemt aan de openbare preview van deze functie, kunt u dit item negeren. Zie [First Run-ervaring met auto pilot en de pagina inschrijvings status](../get-started/esp-first-run.md)voor meer informatie.

**Niet gereed**

Voor het weergeven van de voortgang van de **apps en profielen** moet u de standaard-ESP-profielset opgeven. Schakel deze instelling uit of zorg ervoor dat toewijzingen aan een Azure AD-groep geen door Microsoft beheerde bureaublad apparaten bevatten door de stappen te volgen in [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

**Adviser**

Zorg ervoor dat profielen met de instelling **voortgang van app en profielconfiguratie weergeven** niet zijn toegewezen aan een Azure AD-groep die Microsoft beheerde bureaublad apparaten bevat. Zie [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)voor meer informatie.

### <a name="intune-enrollment"></a>InTune-registratie

Windows 10-apparaten in uw Azure AD-organisatie moeten automatisch worden geregistreerd in intune.

**Adviser**

Zorg ervoor dat het bereik van MDM-gebruikers is **ingesteld op** **Alles of alles**, niet **none**. Als u **een aantal** kiest, meldt u zich weer na de inschrijving en selecteert u de groep **modern Workplace-all** Azure AD voor **groepen**.


### <a name="microsoft-store-for-business"></a>Microsoft Store voor Bedrijven

We gebruiken Microsoft Store voor bedrijven, zodat u de bedrijfs portal kunt downloaden om bepaalde apps te implementeren, zoals Microsoft Project en Microsoft Visio.

**Niet gereed**

Microsoft Store voor bedrijven is niet ingeschakeld of wordt niet gesynchroniseerd met intune. Zie voor meer informatie het artikel [apps gekochte apps in Microsoft Store voor bedrijven beheren met Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) en de [intune-bedrijfs portal installeren op een apparaat](../get-started/company-portal.md).

### <a name="multifactor-authentication"></a>Meervoudige verificatie

Meervoudige verificatie mag niet per ongeluk worden toegepast op accounts van Microsoft Managed Desktop service.


**Niet gereed**

U hebt een MFA-beleid (multi-factor Authentication) ingesteld als vereist voor regels voor voorwaardelijke toegang die zijn toegewezen aan alle gebruikers. Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat. Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).

**Adviser**

Zorg ervoor dat voor beleidsregels voor voorwaardelijke toegang de optie MFA moet **zijn opgenomen:** de groep alle Azure AD. Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). De **modern Workplace-all** Azure AD-groep is een dynamische groep die we maken wanneer u zich registreert bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.

**Fout**

De rol intune-beheerder heeft onvoldoende machtigingen voor deze controle. U hebt ook een van de volgende Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:

- Beveiligings lezer
- Beveiligingsbeheerder
- Beheerder van voorwaardelijke toegang
- Algemene lezer
- Apparaten beheerder


### <a name="powershell-scripts"></a>PowerShell-scripts

Windows PowerShell-scripts kunnen niet worden toegewezen in de manier waarop Microsoft beheerde bureaublad apparaten kunnen worden beheerd.  

**Adviser**

Zorg ervoor dat Windows PowerShell-scripts in uw Azure AD-organisatie geen Microsoft-bureaublad apparaten of-gebruikers beheren. Wijs geen PowerShell-script toe om alle gebruikers, alle apparaten of beide te bereiken. Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat. Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)voor meer informatie.

### <a name="region"></a>Regio

Uw regio moet worden ondersteund door Microsoft Managed Desktop.

**Niet gereed**

Uw regio van Azure AD organisatie wordt momenteel niet ondersteund door Microsoft Managed Desktop. Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.

**Adviser**

Een of meer van de landen waar uw Azure AD organisatie zich bevindt, wordt niet ondersteund door het door Microsoft beheerde bureaublad. Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.


### <a name="security-baselines"></a>Basislijnen voor beveiliging

Beleidsregels voor beveiliging van basislijn dienen niet te worden beheerd door Microsoft beheerde bureaublad apparaten.

**Niet gereed**

U hebt een profiel voor beveiligings basislijn voor alle gebruikers, alle apparaten of beide. Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat. Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.

**Adviser**

Zorg dat beleidsregels voor beveiliging op basis van Microsoft beheerde bureaublad apparaten zijn uitgesloten. Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies. De **moderne werkplekken-** de groep Azure AD is een dynamische groep die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.


### <a name="windows-apps"></a>Windows-apps

Bekijk de apps waarover u Microsoft beheerde bureaubladgebruikers wilt hebben.

**Adviser**

U moet een inventarisatie voorbereiden van de apps die u wilt laten door Microsoft beheerde bureaubladgebruikers. Aangezien deze apps moeten worden geïmplementeerd door intune, evalueert u de bestaande intune-apps opnieuw. Overweeg om bedrijfsportal te gebruiken (Zie [intune-bedrijfsportal installeren op apparaten](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) en de pagina inschrijvings status (ESP) om apps te distribueren voor uw gebruikers. Zie [apps in Microsoft Managed Desktop](apps.md) en [First-Run met auto pilot en de pagina met de inschrijvings status](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)voor meer informatie.

U kunt de vertegenwoordiger van uw Microsoft-account vragen om te bepalen welke apps gereed zijn om te worden gemigreerd naar intune of een correctie.


### <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven

Voor Microsoft Managed Desktop is Windows hello voor bedrijven ingeschakeld.

**Niet gereed**

Windows hello voor bedrijven is uitgeschakeld. Activeren door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Adviser**

Windows hello voor bedrijven is niet ingesteld. Schakel deze optie in door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).


### <a name="windows-10-update-rings"></a>Windows 10-update ringen

Het beleid Windows 10-update ring in intune mag geen Microsoft-bureaublad apparaten met Microsoft worden beheerd.

**Niet gereed**

U hebt een beleid voor het bijwerken van een update voor alle apparaten, alle gebruikers of beide. Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat. Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.

**Adviser**

Zorg ervoor dat bij een update ring beleid u de **moderne Werkplaatsings apparaten-alle** Azure AD-groep uitsluiten. Als u een Azure AD-gebruikersgroep aan deze beleidsregels hebt toegewezen, moet u ervoor zorgen dat u ook de **moderne werkplek,** exclusief de Azure AD-groep, die uw door Microsoft beheerde bureaubladgebruikers omvat. Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies. Zowel de **moderne werkplekken-** alle en de **moderne werkplek: alle** Azure ad-groepen zijn toegewezen groepen die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

U kunt toegang krijgen tot Azure Active Directory-instellingen op de [Azure-Portal](https://portal.azure.com).

### <a name="ad-hoc-subscriptions"></a>Ad hoc-abonnementen

Adviseert het controleren van een instelling die (indien ingesteld op ' onwaar ') kan voorkomen dat roaming via Enterprise niet goed werkt.

**Adviser**

Zorg ervoor dat **AllowAdHocSubscriptions** is ingesteld op **waar**. Anders werkt Enterprise State roaming mogelijk niet. Zie [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)voor meer informatie.


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State roaming moet zijn ingeschakeld.

**Adviser**

Zorg ervoor dat roaming voor bedrijven is ingeschakeld voor **alle** of voor **geselecteerde** groepen. Zie [Enterprise State roaming inschakelen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)voor meer informatie.

### <a name="licenses"></a>Licenties

U moet een aantal licenties gebruiken om Microsoft Managed Desktop te gebruiken.

**Niet gereed**

U hebt niet alle licenties die u nodig hebt om Microsoft Managed Desktop te gebruiken. Zie [Microsoft Managed Desktop Technologies](../intro/technologies.md) en meer informatie [over licenties](prerequisites.md#more-about-licenses)voor meer informatie.


### <a name="security-account-names"></a>Namen van beveiligingsaccounts

Het is mogelijk dat de namen van bepaalde beveiligingsaccounts conflicteren met die van Microsoft Managed Desktop.

**Niet gereed**

U hebt minimaal één accountnaam waarvan de naam afwijkt van de naam die wordt gemaakt door Microsoft Managed Desktop. Met de vertegenwoordiger van uw Microsoft-account kunt u deze accountnamen uitsluiten.


### <a name="security-administrator-roles"></a>Rollen van beveiligingsbeheerders

Gebruikers met bepaalde beveiligingsrollen moeten de toewijzingen in Microsoft Defender voor eindpunten hebben.

**Adviser**

Als u gebruikers hebt toegewezen aan een van deze rollen in uw Azure AD-organisatie, moet u ervoor zorgen dat deze rollen ook zijn toegewezen in Microsoft Defender voor eindpunt. Anders hebben beheerders met deze rollen geen toegang tot de beheerportal.

- Beveiligings operator
- Algemene lezer

Zie [rollen voor toegangsbeheer op basis van rollen maken en beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)voor meer informatie.


### <a name="security-default"></a>Beveiligingsstandaard

Met behulp van de beveiligingsinstellingen in azure Active Directory wordt voorkomen dat Microsoft beheerd bureaublad uw apparaten beheert.

**Niet gereed**

U hebt beveiligingsstandaarden ingeschakeld. Schakel beveiligingsstandaarden uit en stel beleidsregels voor voorwaardelijke toegang in. Zie voor meer informatie [veelgebruikte beleidsregels voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Selfservice voor wachtwoordherstel

U moet selfservice voor wachtwoordherstel (SSPR) inschakelen voor alle Microsoft beheerde bureaubladgebruikers, met uitzondering van Microsoft beheerde bureaublad serviceaccounts. Zie [Zelfstudie: gebruikers toestaan hun account te ontgrendelen of wachtwoorden opnieuw in te stellen met behulp van Azure Active Directory-wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).

**Adviser**

Zorg ervoor dat de **geselecteerde** instelling voor SSPR Microsoft beheerde bureaublad apparaten bevat, maar dat Microsoft beheerde bureaublad-serviceaccounts niet is opgenomen. Accounts van Microsoft beheerde bureaubladservices werken niet zoals verwacht wanneer SSPR is ingeschakeld.  


### <a name="standard-user-role"></a>Standaard gebruikersrol

Behalve de gebruikers die een Azure AD-rol van globale beheerder en een andere netwerkbeheerder toegewezen, zijn Microsoft-beheerde bureaubladgebruikers standaardgebruikers zonder lokale beheerdersbevoegdheden. Voor alle andere gebruikers wordt een standaard gebruikersrol toegewezen wanneer ze hun Microsoft-beheerde bureaublad apparaat starten.

**Adviser**

Microsoft beheerde bureaubladgebruikers hebben geen lokale beheerdersbevoegdheden op hun Microsoft beheerde bureaublad apparaten na registratie.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365-apps voor ondernemingen

### <a name="onedrive"></a>OneDrive

De instelling voor **synchronisatie alleen toestaan op pc's die lid zijn van een specifieke domein** instelling, conflicteert met Microsoft Managed Desktop. U kunt toegang krijgen tot OneDrive-instellingen in het OneDrive- [Beheercentrum](https://admin.onedrive.com).

**Adviser**

U gebruikt de instelling **synchronisatie alleen toestaan op pc's die lid zijn van bepaalde domeinen** . Deze instelling werkt niet met beheerde Microsoft-bureaublad. Schakel deze instelling uit en zet OneDrive zodanig in dat deze gebruikmaakt van een voorwaardelijk toegangsbeleid. Zie [voorwaardelijke toegang plannen](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) voor hulp.

