---
title: Vereiste werkzaamheden voor het implementeren van identiteits- en apparaattoegangsbeleid - Microsoft 365 voor | Microsoft Docs
description: In dit artikel wordt beschreven aan welke vereisten u moet voldoen voor het gebruik van identiteits- en apparaattoegangsbeleid en -configuraties.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
ms.date: 09/01/2020
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
ms.openlocfilehash: e411eaa7874dee710cbb21dd02a4edd383003def
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142095"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Vereiste werkzaamheden voor het implementeren van identiteits- en apparaattoegangsbeleid

In dit artikel worden de vereisten beschreven waar beheerders aan moeten voldoen om aanbevolen identiteits- en apparaattoegangsbeleid te gebruiken en om voorwaardelijke toegang te gebruiken. Daarnaast worden de aanbevolen standaardwaarden besproken voor het configureren van clientplatforms voor de beste ervaring met eenmalige aanmelding .SSO.

## <a name="prerequisites"></a>Vereisten

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- Azure

Voordat u het aanbevolen identiteits- en apparaattoegangsbeleid gebruikt, moet uw organisatie aan de vereisten voldoen. De vereisten verschillen voor de verschillende identiteits- en verificatiemodellen die worden vermeld:

- Alleen in de cloud
- Hybride met wachtwoord-hashsynchronisatie (PHS)-verificatie
- Hybride met Pass Through-verificatie (PTA)
- Federatief

De volgende tabel bevat informatie over de vereiste functies en de configuratie die van toepassing zijn op alle identiteitsmodellen, behalve waar vermeld.

|Configuratie|Uitzonderingen|
|---|:---:|
|[PHS configureren.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)  Dit moet zijn ingeschakeld voor het detecteren van gelekte referenties en om voorwaardelijke toegang op basis van risico te kunnen gebruiken. **Opmerking:** Dit is vereist, ongeacht of uw organisatie federatieverificatie gebruikt.|Alleen in de cloud|
|[Schakel naadloze eenpersoons aanmelden in om](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) gebruikers automatisch aan te melden wanneer ze zich op hun organisatieapparaten aanmelden die met het netwerk van uw organisatie zijn verbonden.|Alleen in de cloud en federatief|
|[Benoemde netwerken configureren.](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal) Azure AD Identity Protection verzamelt en analyseert alle beschikbare sessiegegevens om een risicoscore te genereren. U wordt aangeraden de openbare IP-adresbereiken van uw organisatie voor uw netwerk op te geven in de configuratie van netwerken met de naam Azure AD. Het verkeer dat vanuit deze bereiken komt, krijgt een lagere risicoscore en verkeer van buiten de organisatieomgeving krijgt een hogere risicoscore.||
|[Alle gebruikers registreren voor selfservice voor wachtwoordreset (SSPR) en meervoudige verificatie (MFA).](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) We raden u aan gebruikers van tevoren te registreren voor multi-factor authentication in Azure AD. Azure AD Identity Protection maakt gebruik van Azure AD Multi-Factor Authentication om aanvullende beveiligingsverificatie uit te voeren. Daarnaast raden we gebruikers aan om de Microsoft [Authenticator-app](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) en de Microsoft Company Portal-app op hun apparaten te installeren voor de beste aanmeldingservaring. Deze kunnen voor elk platform worden geïnstalleerd vanuit de App Store.||
|[Schakel automatische apparaatregistratie in voor Windows-computers die lid](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)zijn van een domein. Met voorwaardelijke toegang zorgt u ervoor dat apparaten die verbinding maken met apps, lid zijn van een domein of compatibel zijn. Dit apparaat kan alleen worden ondersteund op Windows-computers als het apparaat is geregistreerd bij Azure AD.  In dit artikel wordt besproken hoe u automatische apparaatregistratie configureert.|Alleen in de cloud|
|**Bereid uw ondersteuningsteam voor.** Een abonnement hebben voor gebruikers die MFA niet kunnen voltooien. Dit kan door ze toe te voegen aan een groep voor beleidsuitsluiting of nieuwe MFA-gegevens voor hen te registreren. Voordat u een van deze beveiligingsgevoelige wijzigingen aan kunt brengen, moet u ervoor zorgen dat de werkelijke gebruiker de aanvraag doet. Het is een effectieve stap om te vereisen dat de beheerders van de gebruikers helpen met de goedkeuring.||
|[Wachtwoordin writeback configureren naar on-premises AD.](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) Met wachtwoordin writeback kan Azure AD vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer een risicovolle accountcompromitteerd wordt gedetecteerd. U kunt deze functie op twee manieren inschakelen met behulp van Azure AD Connect: schakel Wachtwoordopschrijven **in** het scherm met optionele functies van de installatiewizard van Azure AD Connect in of schakel deze in via Windows PowerShell.|Alleen in de cloud|
|[Configureer wachtwoordbeveiliging voor Azure AD.](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) Azure AD-wachtwoordbeveiliging detecteert en blokkeert bekende zwakke wachtwoorden en hun varianten, en kan ook aanvullende zwakke termen blokkeren die specifiek zijn voor uw organisatie. Standaardlijsten met verboden wachtwoorden worden automatisch toegepast op alle gebruikers in een Azure AD-tenant. U kunt aanvullende vermeldingen definiëren in een aangepaste lijst met geblokkeerde wachtwoorden. Als gebruikers hun wachtwoord wijzigen of opnieuw instellen, worden deze verboden wachtwoordlijsten ingeschakeld om het gebruik van sterke wachtwoorden af te dwingen.||
|[Schakel Azure Active Directory Identity Protection in.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection) Met Azure AD Identity Protection kunt u potentiële beveiligingsproblemen opsporen die de identiteiten van uw organisatie beïnvloeden en een geautomatiseerd herstelbeleid configureren voor lage, gemiddelde en hoge aanmeldings- en gebruikersrisico's.||
|**Schakel moderne verificatie in** [voor Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) en voor Skype voor [Bedrijven Online.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) Moderne verificatie is een vereiste voor het gebruik van MFA. Moderne verificatie is standaard ingeschakeld voor Office 2016- en 2019-clients, SharePoint en OneDrive voor Bedrijven.||
|

## <a name="recommended-client-configurations"></a>Aanbevolen clientconfiguraties

In dit gedeelte worden de standaardconfiguraties van platformclients beschreven die u wordt aangeraden uw gebruikers de beste SSO-ervaring te bieden, evenals de technische vereisten voor voorwaardelijke toegang.

### <a name="windows-devices"></a>Windows-apparaten

We raden Windows 10 (versie 2004 of hoger) aan, omdat Azure zo is ontworpen dat het gebruik van eenmalige aanmelding soepel verloopt voor zowel on-premises als Azure AD. Door de school uitgegeven apparaten moeten worden geconfigureerd om rechtstreeks deel te nemen aan Azure AD. Als de organisatie on-premises AD-domein joins gebruikt, moeten deze apparaten zo worden geconfigureerd dat ze automatisch en op de silent worden geregistreerd bij [Azure AD.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

Voor BYOD Windows-apparaten kunnen gebruikers werk- of **schoolaccount toevoegen.** Gebruikers van de browser Google Chrome op Windows [](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 10-apparaten moeten een uitbreiding installeren om dezelfde probleemloos aanmelden als gebruikers van Microsoft Edge te krijgen. Als uw organisatie meerdere domeinen aan een Windows 8 of 8.1-apparaten heeft, kunt u Microsoft Workplace Join installeren voor niet-Windows 10-computers. [Download het pakket om de apparaten te](https://www.microsoft.com/download/details.aspx?id=53554) registreren bij Azure AD.

### <a name="ios-devices"></a>iOS-apparaten

Het is raadzaam de [Microsoft Authenticator-app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) te installeren op gebruikersapparaten voordat u beleidsregels voor voorwaardelijke toegang of MFA implementeert. De app moet ten minste worden geïnstalleerd wanneer gebruikers wordt gevraagd hun apparaat te registreren bij Azure AD door een werk- of schoolaccount toe te voegen, of wanneer ze de Intune-bedrijfsportal-app installeren om hun apparaat in te schrijven voor beheer. Dit is afhankelijk van het geconfigureerde beleid voor voorwaardelijke toegang.

### <a name="android-devices"></a>Android-apparaten

Het is raadzaam dat gebruikers de [Intune-bedrijfsportal-app](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) en de [Microsoft Authenticator-app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) installeren voordat beleid voor voorwaardelijke toegang wordt geïmplementeerd of wanneer dit nodig is tijdens bepaalde verificatiepogingen. Na de installatie van de app kunnen gebruikers worden gevraagd zich te registreren bij Azure AD of hun apparaat te registreren bij Intune. Dit is afhankelijk van het geconfigureerde beleid voor voorwaardelijke toegang.

Het is ook raadzaam dat apparaten die eigendom zijn van organisaties, gestandaardiseerd zijn voor OEM's en versies die Android voor Werk of Samsung Knox ondersteunen om e-mailaccounts toe te staan, te beheren en te beschermen door het Intune MDM-beleid.

### <a name="recommended-email-clients"></a>Aanbevolen e-mail clients

De volgende e-mail clients ondersteunen moderne verificatie en voorwaardelijke toegang.

|Platform|Client|Versie/notities|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Moderne verificatie inschakelen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) <p> [Vereiste updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook voor iOS|[Nieuwste](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook voor Android|[Nieuwste](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 en 2016|
|**Linux**|Niet ondersteund||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Aanbevolen clientplatforms bij het beveiligen van documenten

De volgende clients worden aanbevolen wanneer een beleid voor veilige documenten is toegepast.

|Platform|Word/Excel/PowerPoint|OneNote|OneDrive-app|SharePoint-app|[OneDrive-synchronisatieclient](https://docs.microsoft.com/onedrive/enable-conditional-access)|
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

- [Ondersteuning voor Microsoft 365-client-apps - Voorwaardelijke toegang](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Ondersteuning voor Microsoft 365 Client-app - Meervoudige verificatie](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Beheerdersaccounts beveiligen

Voor Microsoft 365 E3 of E5 of met afzonderlijke Azure AD Premium P1- of P2-licenties kunt u MFA vereisen voor beheerdersaccounts met een handmatig gemaakt beleid voor voorwaardelijke toegang. Zie [Voorwaardelijke toegang: MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) voor meer informatie.

Voor edities van Microsoft 365 of Office 365 die [](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) geen ondersteuning bieden voor voorwaardelijke toegang, kunt u voor alle accounts MFA vereisen voor beveiligingsinstellingen.

Hier volgen enkele aanvullende aanbevelingen:

- Gebruik [Azure AD Privileged Identity Management om](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) het aantal permanente beheeraccounts te verminderen.
- [Gebruik bevoorrechte toegangsbeheer](../../compliance/privileged-access-management-overview.md) om uw organisatie te beschermen tegen inbreuken die mogelijk gebruikmaken van bestaande bevoegde beheerdersaccounts met staande toegang tot gevoelige gegevens of toegang tot essentiële configuratie-instellingen.
- Maak en gebruik afzonderlijke accounts aan en toegewezen [Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) *alleen voor beheer.* Beheerders moeten een eigen gebruikersaccount hebben voor normaal, niet-administratief gebruik en gebruiken zo nodig alleen een beheeraccount om een taak te voltooien die is gekoppeld aan hun functie of functie.
- Volg [de beste procedures voor](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) het beveiligen van accounts met bevoegdheden in Azure AD.

## <a name="next-step"></a>Volgende stap

[![Stap 2: Het algemene beleid voor identiteit en toegang tot voorwaardelijke toegang configureren](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Het algemene beleid voor identiteits- en apparaattoegang configureren](identity-access-policies.md)
