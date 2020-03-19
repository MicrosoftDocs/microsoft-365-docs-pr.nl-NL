---
title: Randwerk voor de implementatie van beleid voor identiteits- en apparaattoegang - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft het beleid voor Microsoft-aanbevelingen over het toepassen van beleid en configuraties voor identiteits- en apparaattoegang.
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
ms.openlocfilehash: c1af88f489072490777cc6f2c7edfc66fd038bdf
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808791"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Voorwaarde werk voor de implementatie van identiteits- en apparaattoegangsbeleid

In dit artikel worden vereisten beschreven die moeten worden geïmplementeerd voordat u het aanbevolen beleid voor identiteits- en apparaattoegang implementeren. In dit artikel worden ook de standaardclientconfiguraties van het platform besproken, raden we aan om uw gebruikers de beste SSO-ervaring te bieden, evenals de technische vereisten voor voorwaardelijke toegang.


## <a name="prerequisites"></a>Vereisten

Voordat het aanbevolen beleid voor identiteits- en apparaattoegang wordt geïmplementeerd, zijn er verschillende vereisten waar uw organisatie aan moet voldoen. In de volgende tabel worden de vereisten beschreven die van toepassing zijn op uw omgeving. 


| Configuratie | Alleen cloud | Active Directory met wachtwoordhashsynchronisatie |  Doorgegeven verificatie |  Federatie met AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Wachtwoordhashsynchronisatie configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Dit moet mogelijk zijn om gelekte referenties te detecteren en op deze gegevens te reageren voor op risico's gebaseerde voorwaardelijke toegang. **Let op:** Dit is vereist, ongeacht of uw organisatie beheerde verificatie gebruikt, zoals pass-through authentication (PTA) of federatieve verificatie. |    | Ja | Ja | Ja |
| [Schakel naadloos één aanmelding in](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) om gebruikers automatisch aan te melden wanneer ze zich op hun bedrijfsapparaten bevinden die zijn verbonden met uw bedrijfsnetwerk. |  | Ja | Ja |  |
| [Benoemde netwerken configureren](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection verzamelt en analyseert alle beschikbare sessiegegevens om een risicoscore te genereren. We raden u aan de openbare IP-bereiken van uw organisatie voor uw netwerk op te geven in de azure AD-netwerkconfiguratie. Verkeer uit deze bereiken krijgt een lagere risicoscore en verkeer van buiten de bedrijfsomgeving krijgt een hogere risicoscore. | Ja  | Ja | Ja | Ja |
|[Registreer alle gebruikers voor self-service password reset (SSPR) en multi-factor authentication (MFA).](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) We raden u aan gebruikers van tevoren te registreren voor Azure MFA. Azure AD Identity Protection maakt gebruik van Azure MFA om extra beveiligingsverificatie uit te voeren. Bovendien raden we gebruikers aan om de Microsoft [Authenticator-app](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) en de Microsoft Company Portal-app op hun apparaten te installeren voor de beste aanmeldingservaring. Deze kunnen voor elk platform vanuit de app store worden geïnstalleerd. | Ja | Ja | Ja | Ja |
| [Automatische apparaatregistratie van windows-computers met domeininschakelen.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) Voorwaardelijke toegang zorgt ervoor dat apparaten die verbinding maken met apps zijn verbonden met het domein of compatibel zijn. Om dit op Windows-computers te ondersteunen, moet het apparaat zijn geregistreerd bij Azure AD.  In dit artikel wordt besproken hoe u automatische apparaatregistratie configureren. |   | Ja |  Ja |  Ja |
| **Bereid uw ondersteuningsteam voor.** Heb een plan voor gebruikers die MFA niet kunnen voltooien. Dit kan zijn om ze toe te voegen aan een beleidsuitsluitingsgroep of nieuwe MFA-informatie voor hen te registreren. Voordat u een van deze beveiligingsgevoelige wijzigingen aanbrengt, moet u ervoor zorgen dat de werkelijke gebruiker de aanvraag indient. Het verplicht stellen van gebruikersmanagers om te helpen met de goedkeuring is een effectieve stap. | Ja | Ja | Ja | Ja |  
| [Wachtwoordterugschrijven configureren naar on-premises AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Met het schrijven van wachtwoorden kan Azure AD eisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer een accountcompromis met een hoog risico wordt gedetecteerd. U deze functie op twee manieren inschakelen via Azure AD Connect: schakel **Password Writeback in** in het optionele functiescherm van de wizard Azure AD Connect setup of schakel deze in via Windows PowerShell. |   | Ja | Ja | Ja |
| [Azure Active Directory-identiteitsbeveiliging inschakelen](https://docs.microsoft.com/azure/active-directory/identity-protection/enable). Azure AD Identity Protection stelt u in staat om potentiële kwetsbaarheden op te sporen die de identiteit van uw organisatie beïnvloeden en een geautomatiseerd herstelbeleid te configureren voor laag, gemiddeld en hoog aanmeldingsrisico en gebruikersrisico.  | Ja | Ja | Ja | Ja |
| **Moderne verificatie inschakelen** voor [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) en voor Skype voor [Bedrijven Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Moderne verificatie is een voorwaarde voor het gebruik van multi-factor authenticatie (MFA). Moderne verificatie is standaard ingeschakeld voor Office 2016-clients, SharePoint Online en OneDrive voor Bedrijven. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Aanbevolen clientconfiguraties
In deze sectie worden de standaardconfiguratievan de platformclient beschreven die we aanbevelen om uw gebruikers de beste SSO-ervaring te bieden, evenals de technische vereisten voor voorwaardelijke toegang.

### <a name="windows-devices"></a>Windows-apparaten
We raden de Windows 10 (versie 1703 of hoger) aan, omdat Azure is ontworpen om de soepelste SSO-ervaring te bieden die mogelijk is voor zowel on-premises als Azure AD. Werk- of schoolapparaten moeten worden geconfigureerd om rechtstreeks lid te worden van Azure AD of als de organisatie on-premises AD-domeinjoin gebruikt, moeten deze apparaten worden [geconfigureerd om automatisch en in stilte te registreren bij Azure AD.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

Voor BYOD Windows-apparaten kunnen gebruikers **Werk- of schoolaccount toevoegen**gebruiken. Houd er rekening mee dat Chrome-browsergebruikers op Windows 10 [een extensie](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) moeten installeren om dezelfde soepele aanmeldingservaring te krijgen als Edge/IE-gebruikers. Als uw organisatie windows 7-apparaten heeft gekoppeld, u Microsoft Workplace Join installeren voor niet-Windows 10-computers [Download het pakket om](https://www.microsoft.com/download/details.aspx?id=53554) de apparaten te registreren met Azure AD.

### <a name="ios-devices"></a>iOS-apparaten
We raden u aan de [Microsoft Authenticator-app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) op gebruikersapparaten te installeren voordat voorwaardelijke toegang of MFA-beleid wordt geïmplementeerd. De app moet minimaal worden geïnstalleerd wanneer gebruikers wordt gevraagd hun apparaat te registreren bij Azure AD door een werk- of schoolaccount toe te voegen of wanneer ze de Intune-bedrijfsportal-app installeren om hun apparaat in te schrijven voor beheer. Dit is afhankelijk van het geconfigureerde beleid voor voorwaardelijke toegang.

### <a name="android-devices"></a>Android-apparaten
We raden gebruikers aan de [Intune Company Portal-app](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) en [Microsoft Authenticator-app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) te installeren voordat een beleid voor voorwaardelijke toegang wordt geïmplementeerd of wanneer dit nodig is tijdens bepaalde verificatiepogingen. Na de installatie van de app kunnen gebruikers worden gevraagd zich te registreren bij Azure AD of hun apparaat in te schrijven bij Intune. Dit is afhankelijk van het geconfigureerde beleid voor voorwaardelijke toegang.

We raden ook aan dat apparaten die eigendom zijn van bedrijven (COD) zijn gestandaardiseerd op OEM's en versies die Android for Work of Samsung Knox ondersteunen om e-mailaccounts toe te staan, worden beheerd en beschermd door het MDM-beleid van Intune.


### <a name="recommended-email-clients"></a>Aanbevolen e-mailclients
De volgende e-mailclients ondersteunen moderne verificatie en voorwaardelijke toegang. 

|Platform|Client|Versie/notities|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Moderne verificatie inschakelen](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), Vereiste [updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**Ios**|Outlook voor iOS|[Laatste](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook voor Android|[Laatste](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Macos**|Outlook|2016|
|**Linux**|Niet ondersteund||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Aanbevolen clientplatforms bij het beveiligen van documenten
De volgende clients worden aanbevolen wanneer een beleid voor beveiligde documenten is toegepast.

|Platform|Word/Excel/PowerPoint|OneNote|OneDrive-app|SharePoint-app|OneDrive-synchronisatieclient|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows 8.1|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows 10|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows Phone 10|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|
|Android|Ondersteund|Ondersteund|Ondersteund|Ondersteund|N.v.t.|
|Ios|Ondersteund|Ondersteund|Ondersteund|Ondersteund|N.v.t.|
|Macos|Openbare voorbeeld|Openbare voorbeeld|N.v.t.|N.v.t.|Niet ondersteund|
|Linux|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|

<sup>*</sup>Meer informatie over het gebruik van voorwaardelijke toegang met de [Synchronisatieclient van OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Ondersteuning voor Office 365-client
Zie de volgende artikelen voor meer informatie over de clientondersteuning van Office 365:
- [Ondersteuning voor Office 365-client-app - Voorwaardelijke toegang](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Ondersteuning voor Office 365-clientapp - Beheer van mobiele toepassingen](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Ondersteuning voor Office 365-clientapp - moderne verificatie](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Beheerdersaccounts beveiligen
Azure AD biedt u een eenvoudige manier om beheerderstoegang te beveiligen met een vooraf geconfigureerd beleid voor voorwaardelijke toegang. Ga in Azure AD naar **Voorwaardelijke toegang** en zoek naar dit beleid : **Basislijnbeleid: MFA voor beheerders vereisen (voorbeeld).** Selecteer dit beleid en selecteer **vervolgens beleid gebruiken onmiddellijk**. 

Dit beleid vereist MFA voor de volgende rollen:
- Globale beheerders
- SharePoint-beheerders
- Exchange-beheerders
- Beheerders van voorwaardelijke toegang
- Beveiligingsbeheerders

Zie [Beveiligingsbeleid basislijn voor Azure AD-beheerdersaccounts](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)voor meer informatie.

Aanvullende aanbevelingen zijn onder andere:
- Gebruik Azure AD Privileged Identity Management om het aantal permanente beheeraccounts te verminderen. Zie [Start met PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started). 
- Gebruik beheer van [bevoegde toegang in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) om uw organisatie te beschermen tegen inbreuken die bestaande bevoorrechte beheerdersaccounts kunnen gebruiken met permanente toegang tot gevoelige gegevens of toegang tot kritieke configuratie-instellingen. 
- Gebruik beheerdersaccounts alleen voor beheer. Beheerders moeten een apart gebruikersaccount hebben voor regelmatig niet-administratief gebruik en hun beheerdersaccount alleen gebruiken wanneer dat nodig is om een taak te voltooien die is gekoppeld aan hun taakfunctie. [Office 365-beheerdersrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) hebben aanzienlijk meer bevoegdheden dan Office 365-services.
- Volg aanbevolen procedures voor het beveiligen van geprivilegieerde accounts in Azure AD zoals beschreven in dit [artikel](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Volgende stappen

[Het algemene beleid voor identiteits- en apparaattoegang configureren](identity-access-policies.md)

