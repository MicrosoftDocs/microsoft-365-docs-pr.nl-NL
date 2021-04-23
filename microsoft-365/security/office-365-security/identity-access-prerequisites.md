---
title: Vereiste werk voor het implementeren van beleidsregels voor identiteits- en apparaattoegang - Microsoft 365 voor | Microsoft Docs
description: In dit artikel worden de vereisten beschreven waar u aan moet voldoen om beleid en configuraties voor identiteits- en apparaattoegang te gebruiken.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: edce65314062f731673926195be791f77d1cb823
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952546"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Vereiste werk voor het implementeren van beleidsregels voor identiteits- en apparaattoegang

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- Azure

In dit artikel wordt beschreven aan welke vereisten beheerders moeten voldoen voor het gebruik van aanbevolen beleidsregels voor identiteits- en apparaattoegang en voor het gebruik van Voorwaardelijke toegang. Ook worden de aanbevolen standaardinstellingen besproken voor het configureren van clientplatforms voor de beste ervaring met eenmalige aanmelding (SSO).

## <a name="prerequisites"></a>Vereisten

Voordat u het beleid voor identiteits- en apparaattoegang gebruikt dat wordt aanbevolen, moet uw organisatie voldoen aan vereisten. De vereisten zijn verschillend voor de verschillende identiteits- en verificatiemodellen die worden vermeld:

- Alleen in de cloud
- Hybride met PHS-verificatie (Password Hash Sync)
- Hybride met pass-throughverificatie (PTA)
- Federatief

De volgende tabel bevat de vereiste functies en de configuratie die van toepassing zijn op alle identiteitsmodellen, behalve indien vermeld.

|Configuratie|Uitzonderingen|Licenties|
|---|:---:|---|
|[PHS configureren.](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)  Dit moet zijn ingeschakeld om gelekte referenties op te sporen en op te treden voor voorwaardelijke toegang op basis van risico's. **Opmerking:** Dit is vereist, ongeacht of uw organisatie federatief verificatie gebruikt.|Alleen in de cloud|Microsoft 365 E3 of E5|
|[Schakel naadloze één aanmelding in om](/azure/active-directory/connect/active-directory-aadconnect-sso) gebruikers automatisch aan te melden wanneer ze zich op hun organisatieapparaten aanmelden die zijn verbonden met uw organisatienetwerk.|Alleen-cloud en federatief|Microsoft 365 E3 of E5|
|[Benoemde locaties configureren.](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) Azure AD Identity Protection verzamelt en analyseert alle beschikbare sessiegegevens om een risicoscore te genereren. Het is raadzaam om de openbare IP-bereik van uw organisatie voor uw netwerk op te geven in de configuratie met de naam Azure AD-locaties. Verkeer dat afkomstig is uit deze reeksen krijgt een lagere risicoscore en verkeer van buiten de organisatieomgeving krijgt een hogere risicoscore.||Microsoft 365 E3 of E5|
|[Registreer alle gebruikers voor selfservice password reset (SSPR) en meervoudige verificatie (MFA).](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) We raden u aan gebruikers vooraf te registreren voor Azure AD Multi-Factor Authentication. Azure AD Identity Protection maakt gebruik van Azure AD Multi-Factor Authentication om extra beveiligingsverificatie uit te voeren. Bovendien raden we gebruikers aan om de Microsoft [Authenticator-app](/azure/active-directory/user-help/microsoft-authenticator-app-how-to) en de Microsoft Company Portal-app op hun apparaten te installeren voor de beste aanmeldingservaring. Deze kunnen worden geïnstalleerd vanuit de App Store voor elk platform.||Microsoft 365 E3 of E5|
|[Automatische apparaatregistratie van windows-computers met een domein inschakelen.](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) Voorwaardelijke toegang zorgt ervoor dat apparaten die verbinding maken met apps zijn verbonden met een domein of compatibel zijn. Als u dit wilt ondersteunen op Windows-computers, moet het apparaat zijn geregistreerd bij Azure AD.  In dit artikel wordt beschreven hoe u automatische apparaatregistratie configureert.|Alleen in de cloud|Microsoft 365 E3 of E5|
|**Bereid uw ondersteuningsteam voor.** Een abonnement hebben voor gebruikers die MFA niet kunnen voltooien. Dit kan het toevoegen van deze gegevens aan een groep met beleidsuitsluitingen of het registreren van nieuwe MFA-gegevens voor hen zijn. Voordat u een van deze beveiligingsgevoelige wijzigingen aan gaat brengen, moet u ervoor zorgen dat de werkelijke gebruiker de aanvraag doet. Het is een effectieve stap om managers van gebruikers te vragen om te helpen met de goedkeuring.||Microsoft 365 E3 of E5|
|[Wachtwoord writeback configureren naar on-premises AD](/azure/active-directory/active-directory-passwords-getting-started). Met wachtwoord writeback kan Azure AD vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een risicovolle accountcompromitteerd wordt gedetecteerd. U kunt deze functie op twee manieren inschakelen met Azure AD Connect: wachtwoord schrijven **inschakelen** in het optionele functiesscherm van de installatiewizard azure AD Connect of deze inschakelen via Windows PowerShell.|Alleen in de cloud|Microsoft 365 E3 of E5|
|[Azure AD-wachtwoordbeveiliging configureren.](/azure/active-directory/authentication/concept-password-ban-bad) Azure AD-wachtwoordbeveiliging detecteert en blokkeert bekende zwakke wachtwoorden en hun varianten, en kan ook aanvullende zwakke termen blokkeren die specifiek zijn voor uw organisatie. Standaardlijsten met verboden wachtwoorden worden automatisch toegepast op alle gebruikers in een Azure AD-tenant. U kunt aanvullende vermeldingen definiëren in een aangepaste lijst met geblokkeerde wachtwoorden. Als gebruikers hun wachtwoord wijzigen of opnieuw instellen, worden deze verboden wachtwoordlijsten ingeschakeld om het gebruik van sterke wachtwoorden af te dwingen.||Microsoft 365 E3 of E5|
|[Azure Active Directory Identity Protection inschakelen.](/azure/active-directory/identity-protection/overview-identity-protection) Met Azure AD Identity Protection kunt u mogelijke beveiligingslekken opsporen die van invloed zijn op de identiteiten van uw organisatie en een geautomatiseerd herstelbeleid configureren op laag, gemiddeld en hoog aanmeldings- en gebruikersrisico.||Microsoft 365 E5 of Microsoft 365 E3 met de E5-beveiligings add-on|
|**Moderne verificatie inschakelen** [voor Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) en voor Skype voor Bedrijven [Online.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) Moderne verificatie is een vereiste voor het gebruik van MFA. Moderne verificatie is standaard ingeschakeld voor Office 2016- en 2019-clients, SharePoint en OneDrive voor Bedrijven.||Microsoft 365 E3 of E5|
|

## <a name="recommended-client-configurations"></a>Aanbevolen clientconfiguraties

In deze sectie worden de standaardconfiguraties voor platformclients beschreven die we aanbevelen om de beste SSO-ervaring te bieden aan uw gebruikers, evenals de technische vereisten voor Voorwaardelijke toegang.

### <a name="windows-devices"></a>Windows-apparaten

We raden windows 10 (versie 2004 of hoger) aan, omdat Azure is ontworpen om de soepelste SSSO-ervaring te bieden die mogelijk is voor zowel on-premises als Azure AD. Werk- of schoolapparaten moeten worden geconfigureerd om rechtstreeks deel te nemen aan Azure AD of als de organisatie on-premises AD-domein join gebruikt, moeten deze apparaten worden geconfigureerd om zich automatisch en stil te registreren bij [Azure AD.](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

Voor BYOD Windows-apparaten kunnen gebruikers Werk- of **schoolaccount toevoegen gebruiken.** Gebruikers van de Google Chrome-browser op Windows [](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 10-apparaten moeten een extensie installeren om dezelfde soepele aanmeldingservaring te krijgen als Microsoft Edge-gebruikers. Als uw organisatie domeingevoegde apparaten Windows 8 of 8.1-apparaten heeft, kunt u Microsoft Workplace Join installeren voor niet-Windows 10-computers. [Download het pakket om de apparaten te](https://www.microsoft.com/download/details.aspx?id=53554) registreren bij Azure AD.

### <a name="ios-devices"></a>iOS-apparaten

Het is raadzaam de [Microsoft Authenticator-app](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) op gebruikersapparaten te installeren voordat u beleidsregels voor voorwaardelijke toegang of MFA implementeert. De app moet minimaal worden geïnstalleerd wanneer gebruikers worden gevraagd hun apparaat te registreren bij Azure AD door een werk- of schoolaccount toe te voegen of wanneer ze de intune-bedrijfsportal-app installeren om hun apparaat in te schrijven voor beheer. Dit is afhankelijk van het geconfigureerde beleid voor Voorwaardelijke toegang.

### <a name="android-devices"></a>Android-apparaten

Het is raadzaam dat gebruikers de [Intune Company Portal-app](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) en [de Microsoft Authenticator-app](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) installeren voordat beleid voor voorwaardelijke toegang wordt geïmplementeerd of wanneer dit vereist is tijdens bepaalde verificatiepogingen. Na de installatie van de app kunnen gebruikers worden gevraagd zich te registreren bij Azure AD of hun apparaat te registreren bij Intune. Dit is afhankelijk van het geconfigureerde beleid voor Voorwaardelijke toegang.

We raden ook aan dat apparaten die eigendom zijn van de organisatie gestandaardiseerd zijn op OEM's en versies die Android voor Werk of Samsung Knox ondersteunen om e-mailaccounts toe te staan, te beheren en te beschermen met het MDM-beleid van Intune.

### <a name="recommended-email-clients"></a>Aanbevolen e-mail clients

De volgende e-mail clients ondersteunen moderne verificatie en Voorwaardelijke toegang.

|Platform|Client|Versie/notities|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Moderne verificatie inschakelen](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [Vereiste updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook voor iOS|[Meest recent](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook voor Android|[Meest recent](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 en 2016|
|**Linux**|Niet ondersteund||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Aanbevolen clientplatforms bij het beveiligen van documenten

De volgende clients worden aanbevolen wanneer een beleid voor veilige documenten is toegepast.

|Platform|Word/Excel/PowerPoint|OneNote|OneDrive-app|SharePoint App|[OneDrive-synchronisatieclient](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Ondersteund|
|Windows 10|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Ondersteund|
|Android|Ondersteund|Ondersteund|Ondersteund|Ondersteund|N.v.t.|
|iOS|Ondersteund|Ondersteund|Ondersteund|Ondersteund|N.v.t.|
|macOS|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Niet ondersteund|
|Linux|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365-clientondersteuning

Zie de volgende artikelen voor meer informatie over clientondersteuning in Microsoft 365:

- [Ondersteuning voor Microsoft 365 Client App - Voorwaardelijke toegang](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Ondersteuning voor Microsoft 365 Client App - Meervoudige verificatie](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Beheerdersaccounts beveiligen

Voor Microsoft 365 E3 of E5 of met afzonderlijke Azure AD Premium P1- of P2-licenties kunt u MFA voor beheerdersaccounts vereisen met een handmatig gemaakt beleid voor Voorwaardelijke toegang. Zie [Voorwaardelijke toegang: MFA vereisen voor beheerders](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) voor de details.

Voor edities van Microsoft 365 of Office 365 die [](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) geen ondersteuning bieden voor Voorwaardelijke toegang, kunt u beveiligingsinstellingen inschakelen voor het vereisen van MFA voor alle accounts.

Hier volgen enkele extra aanbevelingen:

- Gebruik [Azure AD Privileged Identity Management om](/azure/active-directory/privileged-identity-management/pim-getting-started) het aantal permanente beheerdersaccounts te verminderen.
- [Gebruik bevoorrecht](../../compliance/privileged-access-management-overview.md) toegangsbeheer om uw organisatie te beschermen tegen inbreuken die bestaande bevoorrechte beheerdersaccounts kunnen gebruiken met permanente toegang tot gevoelige gegevens of toegang tot kritieke configuratie-instellingen.
- Maak en gebruik afzonderlijke accounts die alleen voor beheer [aan Microsoft 365-beheerdersrollen](../../admin/add-users/about-admin-roles.md) *zijn toegewezen.* Beheerders moeten een eigen gebruikersaccount hebben voor regelmatig niet-administratief gebruik en alleen een beheeraccount gebruiken wanneer dat nodig is om een taak te voltooien die is gekoppeld aan hun rol of functie.
- Volg [best practices voor](/azure/active-directory/admin-roles-best-practices) het beveiligen van bevoorrechte accounts in Azure AD.

## <a name="next-step"></a>Volgende stap

[![Stap 2: Het algemene beleid voor identiteit en toegang tot voorwaardelijke toegang configureren](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Het algemene beleid voor identiteits- en apparaattoegang configureren](identity-access-policies.md)