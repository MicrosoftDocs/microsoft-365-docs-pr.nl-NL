---
title: Voorwaarde voor de implementatie van beleid voor identiteits- en apparaattoegangsbeleid - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft het beleid voor Microsoft-aanbevelingen voor het toepassen van beleid en configuratie van identiteits- en apparaattoegangs.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: bfbb0481670b2f957bf240c261fcbafab96717b9
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222587"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Voorwaarde voor het implementeren van identiteits- en apparaattoegangsbeleid

In dit artikel worden vereisten beschreven die moeten worden geïmplementeerd voordat u het aanbevolen beleid voor identiteits- en apparaattoegangsbeleid implementeren. In dit artikel worden ook de standaardclientconfiguraties van het platform besproken die we aanbevelen om uw gebruikers de beste SSO-ervaring te bieden, evenals de technische vereisten voor voorwaardelijke toegang.


## <a name="prerequisites"></a>Vereisten

Voordat u het aanbevolen beleid voor identiteits- en apparaattoegangsbeleid implementeert, zijn er verschillende vereisten waar uw organisatie aan moet voldoen. In de volgende tabel worden de vereisten beschreven die van toepassing zijn op uw omgeving. 


| Configuratie | Alleen cloud | Active Directory met wachtwoordhashsynchronisatie |  Pass-through-verificatie |  Federatie met AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Wachtwoordhashsynchronisatie configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Dit moet in staat worden gesteld om gelekte referenties te detecteren en ernaar te handelen voor op risico gebaseerde voorwaardelijke toegang. **Let op:** Dit is vereist ongeacht of uw organisatie beheerde verificatie gebruikt, zoals pass-through-verificatie (PTA) of federatieve verificatie. |    | Ja | Ja | Ja |
| [Schakel naadloos eenmalig aanmelden in](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) om gebruikers automatisch aan te melden wanneer ze zich op hun bedrijfsapparaten bevinden die zijn verbonden met uw bedrijfsnetwerk. |  | Ja | Ja |  |
| [Benoemde netwerken configureren](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection verzamelt en analyseert alle beschikbare sessiegegevens om een risicoscore te genereren. We raden u aan de openbare IP-bereiken van uw organisatie voor uw netwerk op te geven in de configuratie van Azure AD met de naam netwerk. Verkeer afkomstig van deze bereiken krijgt een lagere risicoscore en verkeer van buiten de bedrijfsomgeving krijgt een hogere risicoscore. | Ja  | Ja | Ja | Ja |
|[Registreer alle gebruikers voor self-service wachtwoordreset (SSPR) en multi-factor authenticatie (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). We raden u aan gebruikers van tevoren te registreren voor Azure MFA. Azure AD Identity Protection maakt gebruik van Azure MFA om extra beveiligingsverificatie uit te voeren. Bovendien raden we gebruikers aan om voor de beste aanmeldingservaring de [Microsoft Authenticator-app](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) en de Microsoft Company Portal-app op hun apparaten te installeren. Deze kunnen worden geïnstalleerd vanuit de app store voor elk platform. | Ja | Ja | Ja | Ja |
| [Automatische apparaatregistratie van windows-computers met een domein inschakelen.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) Voorwaardelijke toegang zorgt ervoor dat apparaten die verbinding maken met apps zijn verbonden met het domein of compatibel zijn. Om dit op Windows-computers te ondersteunen, moet het apparaat zijn geregistreerd bij Azure AD.  In dit artikel wordt besproken hoe u automatische apparaatregistratie configureert. |   | Ja |  Ja |  Ja |
| **Bereid je ondersteuningsteam voor.** Heb een plan voor gebruikers die MFA niet kunnen voltooien. Dit kan zijn ze toe te voegen aan een groep beleidsuitsluiting of het registreren van nieuwe MFA-informatie voor hen. Voordat u een van deze beveiligingsgevoelige wijzigingen aanbrengt, moet u ervoor zorgen dat de werkelijke gebruiker de aanvraag indient. Het is een effectieve stap om gebruikersmanagers te verplichten om te helpen met de goedkeuring. | Ja | Ja | Ja | Ja |  
| [Wachtwoordterugschrijven configureren naar on-premises AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Met terugschrijfinformatie met wachtwoorden kan Azure AD vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer een compromis met een hoog risico-account wordt gedetecteerd. U deze functie op twee manieren inschakelen met Azure AD Connect: schakel **Wachtwoordwriteback** in het optionele functiesscherm van de installatiewizard Azure AD Connect in of schakel deze in via Windows PowerShell. |   | Ja | Ja | Ja |
| [Azure Active Directory Identity Protection inschakelen](https://docs.microsoft.com/azure/active-directory/identity-protection/enable). Azure AD Identity Protection stelt u in staat om potentiële kwetsbaarheden te detecteren die van invloed zijn op de identiteit van uw organisatie en een geautomatiseerd herstelbeleid te configureren voor laag, gemiddeld en hoog aanmeldingsrisico en gebruikersrisico.Azure AD Identity Protection enables you to detecting potential vulnerabilities affecting your organization's identities and configure an automated remediation policy to low, medium, and high sign-in risk and user risk.  | Ja | Ja | Ja | Ja |
| **Moderne verificatie inschakelen** voor [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) en voor Skype voor [Bedrijven Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Moderne verificatie is een voorwaarde voor het gebruik van multi-factor authenticatie (MFA). Moderne verificatie is standaard ingeschakeld voor Office 2016-clients, SharePoint Online en OneDrive voor Bedrijven. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Aanbevolen clientconfiguraties
In deze sectie worden de standaardclientconfiguraties van het platform beschreven die we aanbevelen om uw gebruikers de beste SSO-ervaring te bieden, evenals de technische vereisten voor voorwaardelijke toegang.

### <a name="windows-devices"></a>Windows-apparaten
We raden de Windows 10 (versie 1703 of hoger) aan, omdat Azure is ontworpen om de soepelste SSO-ervaring te bieden die mogelijk is voor zowel on-premises als Azure AD. Apparaten die door werk of school zijn uitgegeven, moeten zijn geconfigureerd om rechtstreeks lid te worden van Azure AD of als de organisatie on-premises AD-domeinjoin gebruikt, moeten deze apparaten worden [geconfigureerd om automatisch en in stilte te registreren bij Azure AD.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

Voor BYOD Windows-apparaten kunnen gebruikers **werk of schoolaccount toevoegen**gebruiken. Gebruikers van de Chrome-browser op Windows 10 moeten [een extensie installeren](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) om dezelfde soepele aanmeldingservaring te krijgen als Edge/IE-gebruikers. Als uw organisatie windows 7-apparaten met domein heeft aangesloten, u Microsoft Workplace Join installeren voor niet-Windows 10-computers [Download het pakket om](https://www.microsoft.com/download/details.aspx?id=53554) de apparaten te registreren bij Azure AD.

### <a name="ios-devices"></a>iOS-apparaten
We raden u aan de [Microsoft Authenticator-app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) op gebruikersapparaten te installeren voordat u voorwaardelijke toegang of MFA-beleid implementeert. De app moet minimaal worden geïnstalleerd wanneer gebruikers wordt gevraagd hun apparaat te registreren bij Azure AD door een werk- of schoolaccount toe te voegen of wanneer ze de Intune-bedrijfsportal-app installeren om hun apparaat in te schrijven voor beheer. Dit is afhankelijk van het geconfigureerde beleid voor voorwaardelijke toegang.

### <a name="android-devices"></a>Android-apparaten
We raden gebruikers aan de [Intune Company Portal-app](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) en [de Microsoft Authenticator-app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) te installeren voordat het beleid voor voorwaardelijke toegang wordt geïmplementeerd of wanneer dit vereist is tijdens bepaalde verificatiepogingen. Na de installatie van de app kunnen gebruikers worden gevraagd zich te registreren bij Azure AD of hun apparaat in te schrijven bij Intune. Dit is afhankelijk van het geconfigureerde beleid voor voorwaardelijke toegang.

We raden ook aan dat apparaten in bedrijfshanden (COD) zijn gestandaardiseerd op OEM's en versies die Android for Work of Samsung Knox ondersteunen om e-mailaccounts toe te staan, te beheren en te beschermen door het Intune MDM-beleid.


### <a name="recommended-email-clients"></a>Aanbevolen e-mailclients
De volgende e-mailclients ondersteunen moderne verificatie en voorwaardelijke toegang. 

|Platform|Client|Versie/notities|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Moderne verificatie inschakelen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication), Vereiste [updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**Ios**|Outlook voor iOS|[Laatste](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook voor Android|[Laatste](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Macos**|Outlook|2016|
|**Linux**|Niet ondersteund||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Aanbevolen clientplatforms bij het beveiligen van documenten
De volgende clients worden aanbevolen wanneer een beleid voor beveiligde documenten is toegepast.

|Platform|Word/Excel/PowerPoint|OneNote|OneDrive-app|SharePoint-app|Synchronisatieclient van OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows 8.1|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows 10|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows Phone 10|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|
|Android|Ondersteund|Ondersteund|Ondersteund|Ondersteund|N.v.t.|
|Ios|Ondersteund|Ondersteund|Ondersteund|Ondersteund|N.v.t.|
|Macos|Openbare preview|Openbare preview|N.v.t.|N.v.t.|Niet ondersteund|
|Linux|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|

<sup>*</sup>Meer informatie over het gebruik van voorwaardelijke toegang met de [Synchronisatieclient van OneDrive](https://docs.microsoft.com/onedrive/enable-conditional-access).

### <a name="microsoft-365-client-support"></a>Microsoft 365-clientondersteuning
Zie de volgende artikelen voor meer informatie over clientsupport:
- [Microsoft 365 Client App Support - Voorwaardelijke toegang](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Ondersteuning voor Microsoft 365-clientapps - Mobile Application Management](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Microsoft 365 Client App Support - Moderne verificatie](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Beheerdersaccounts beveiligen
Azure AD biedt u een eenvoudige manier om beheerderstoegang te beschermen met een vooraf geconfigureerd beleid voor voorwaardelijke toegang. Ga in Azure AD naar **Voorwaardelijke toegang** en zoek naar dit beleid : **Basislijnbeleid: MFA vereisen voor beheerders (voorbeeld)**. Selecteer dit beleid en selecteer **vervolgens het beleid gebruiken onmiddellijk**. 

Voor dit beleid is MFA vereist voor de volgende rollen:
- Globale beheerders
- SharePoint-beheerders
- Exchange-beheerders
- Beheerders van voorwaardelijke toegang
- Beveiligingsbeheerders

Zie [Basislijnbeveiligingsbeleid voor Azure AD-beheerdersaccounts voor](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)meer informatie .

Aanvullende aanbevelingen zijn onder meer:
- Gebruik Azure AD Privileged Identity Management om het aantal permanente beheerdersaccounts te verminderen. Zie [Pim gebruiken.](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) 
- [Gebruik privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) om uw organisatie te beschermen tegen inbreuken die bestaande bevoegde beheerdersaccounts kunnen gebruiken met permanente toegang tot gevoelige gegevens of toegang tot kritieke configuratie-instellingen. 
- Gebruik alleen beheerdersaccounts voor beheer. Beheerders moeten een apart gebruikersaccount hebben voor regelmatig niet-administratief gebruik en gebruiken hun beheerdersaccount alleen wanneer dat nodig is om een taak te voltooien die is gekoppeld aan hun functie. [Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) hebben aanzienlijk meer bevoegdheden dan Microsoft 365-services.
- Volg aanbevolen procedures voor het beveiligen van bevoegde accounts in Azure AD zoals beschreven in dit [artikel.](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)

## <a name="next-steps"></a>Volgende stappen

[Het algemene beleid voor identiteits- en apparaattoegangsconfigureren configureren](identity-access-policies.md)

