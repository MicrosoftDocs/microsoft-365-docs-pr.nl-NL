---
title: Vereisten voor het implementeren van identiteits-en Apparaattoegang-beleid-Microsoft 365 for Enterprise | Microsoft docs
description: Een beschrijving van de beleidsregels voor Microsoft aanbevelingen voor het toepassen van beleidsregels en configuraties voor identiteiten en apparaten.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: a81e17cad1722c58f5bf13b2a36c16fc2ff5cba4
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898038"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Vereisten voor het implementeren van identiteits-en Apparaattoegang

In dit artikel worden de vereisten beschreven die moeten worden geïmplementeerd voordat u de aanbevolen identiteit en het toegangsbeleid voor apparaten kunt implementeren. In dit artikel wordt ook ingegaan op de standaardplatform-clientconfiguraties, en de voorwaarden voor de beste eenmalige aanmelding voor uw gebruikers en de technische vereisten voor voorwaardelijke toegang.


## <a name="prerequisites"></a>Vereisten

Voordat u de aanbevolen beleidsregels implementeert en een beleid voor het openen van een apparaat implementeert, moet u aan de volgende vereisten voldoen. In de volgende tabel vindt u meer informatie over de vereisten die van toepassing zijn op uw omgeving. 


| Configuratie | Alleen cloud | Active Directory met wachtwoord hash-synchronisatie |  Pass-through-verificatie |  Federatie met AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Configureer wachtwoord hash-synchronisatie](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Dit moet worden ingeschakeld voor het detecteren van gelekte referenties en om hierop te reageren voor voorwaardelijke toegang op basis van risico. **Opmerking:** Dit is vereist, ongeacht of uw organisatie gebruikmaakt van beheerde verificatie, zoals Pass-Through-verificatie (PTA), of federatieve verificatie. |    | Ja | Ja | Ja |
| [Naadloze eenmalige aanmelding inschakelen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) om gebruikers automatisch aan te melden wanneer ze zich bevinden op de bedrijfsapparaten die verbinding hebben met uw bedrijfsnetwerk. |  | Ja | Ja |  |
| [Netwerken met een naam configureren](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD-identiteitsbeveiliging verzamelt en veranalyseert alle beschikbare sessiegegevens voor het genereren van een risicoscore. U wordt aangeraden de openbare IP-bereiken van uw organisatie voor uw netwerk op te geven in de configuratie van Azure AD named Network. Verkeer van deze bereiken krijgt een beperkte risicoscore, en verkeer van buiten de bedrijfsomgeving krijgt een hogere risicoscore. | Ja  | Ja | Ja | Ja |
|[Registreer alle gebruikers voor selfservice voor wachtwoordherstel (SSPR) en multi-factor Authentication (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). U wordt aangeraden gebruikers voor de periode van Azure MFA tevoren te registreren. Azure AD-identiteitsbeveiliging biedt gebruik van Azure MFA voor het uitvoeren van extra beveiligingsverificatie. Voor de beste aanmeld ervaring raden wij u aan gebruikers de [Microsoft Authenticator-app](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) en de Microsoft Company Portal-app op hun apparaten te installeren. Deze kunnen worden geïnstalleerd vanuit de App Store voor elk platform. | Ja | Ja | Ja | Ja |
| [Automatische apparaatregistratie inschakelen voor Windows-computers die lid zijn van een domein](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Met voorwaardelijke toegang zorgt u ervoor dat apparaten die verbinding maken met apps, aan een domein zijn toegevoegd of compatibel zijn. Als u dit op Windows-computers wilt ondersteunen, moet het apparaat zijn geregistreerd bij Azure AD.  In dit artikel wordt beschreven hoe u automatische apparaatregistratie configureert. |   | Ja |  Ja |  Ja |
| **Uw ondersteuningsteam voorbereiden**. Een plan hebben voor gebruikers die MFA niet kunnen voltooien. U kunt deze toevoegen aan een groep beleidsuitsluiting of nieuwe MFA-gegevens voor de groep registreren. Voordat u een van deze beveiligingsgevoelige wijzigingen aanbrengt, moet u ervoor zorgen dat de daadwerkelijke gebruikers de aanvraag doen. Wanneer de managers van de gebruikers u kunnen helpen bij de goedkeuring, vormt dit een effectieve stap. | Ja | Ja | Ja | Ja |  
| [Configureer het terugschrijven van wachtwoorden naar on-premises advertenties](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Voor wachtwoord terugschrijfing is Azure AD vereist dat gebruikers hun on-premises wachtwoorden kunnen wijzigen wanneer er een account voor hoog risico wordt gedetecteerd. U kunt deze functie inschakelen met behulp van Azure AD Connect via een van de volgende twee manieren: Schakel het selectievakje **wachtwoord terugschrijven** in het scherm optionele functies van de wizard Azure AD Connect installeren in of schakel het in via Windows PowerShell. |   | Ja | Ja | Ja |
| [Azure Active Directory-identiteits bescherming inschakelen](https://docs.microsoft.com/azure/active-directory/identity-protection/enable). Met Azure AD-identiteitsbeveiliging kunt u potentiële beveiligingsproblemen detecteren die van invloed zijn op de identiteiten van uw organisatie en een automatisch herstelbeleid configureren voor slecht, gemiddeld en sterk aanmelding Risico's en gebruikers risico.  | Ja | Ja | Ja | Ja |
| **Schakel moderne verificatie in** voor [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) en voor [Skype voor bedrijven online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Moderne verificatie is een vereiste voor het gebruik van multi-factor Authentication (MFA). Moderne verificatie is standaard ingeschakeld voor Office 2016-clients, SharePoint Online en OneDrive voor bedrijven. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Aanbevolen clientconfiguraties
In deze sectie vindt u een beschrijving van de standaardplatform-clientconfiguraties die u kunt gebruiken om de beste SSO-ervaring te bieden aan uw gebruikers en de technische vereisten voor voorwaardelijke toegang.

### <a name="windows-devices"></a>Windows-apparaten
U wordt aangeraden Windows 10 (versie 1703 of hoger) te installeren, omdat Azure is ontworpen om de soepele SSO-ervaring te bieden voor zowel on-premises als Azure AD. Apparaten op basis van werk of school moeten worden geconfigureerd om rechtstreeks lid te worden van Azure AD of als de organisatie on-premises AD-Domeindeelname gebruikt, worden deze apparaten [zodanig geconfigureerd dat ze automatisch en zonder meldingen worden geregistreerd met Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Voor BYOD Windows-apparaten kunnen gebruikers **werk-of schoolaccount toevoegen**gebruiken. Houd er rekening mee dat gebruikers met een Chrome-browser op Windows 10 [een uitbreiding moeten installeren om een](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) goede aanmeld ervaring te krijgen als Edge/IE-gebruikers. Daarnaast kunt u Microsoft Workplace join voor computers zonder Windows 10 installeren via Microsoft Workplace-servers, zodat uw organisatie [het pakket kan downloaden](https://www.microsoft.com/download/details.aspx?id=53554) voor de registratie van de apparaten met Azure AD.

### <a name="ios-devices"></a>iOS-apparaten
U wordt aangeraden om de [Microsoft Authenticator-app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) te installeren op gebruikers apparaten voordat u beleidsregels voor voorwaardelijke toegang of MFA implementeert. De app moet minimaal worden geïnstalleerd wanneer gebruikers wordt gevraagd hun apparaat te registreren met Azure AD door een werk-of schoolaccount toe te voegen of wanneer ze de app intune Company Portal installeren om hun apparaat in te delen in Management. Dit is afhankelijk van het geconfigureerde voorwaardelijke toegangsbeleid.

### <a name="android-devices"></a>Android-apparaten
U wordt aangeraden gebruikers de [app intune Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) en [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) te installeren voordat beleidsregels voor voorwaardelijke toegang worden geïmplementeerd of wanneer u tijdens een bepaalde verificatie wordt gevraagd. Na de installatie van de app wordt u mogelijk gevraagd om u aan te melden bij Azure AD of hun apparaat te registreren met intune. Dit is afhankelijk van het geconfigureerde voorwaardelijke toegangsbeleid.

We raden u ook aan dat de bedrijfseigen apparatuur (COD) wordt gebruikt voor Oem's en versies die Android voor werk of Samsung Knox ondersteunen om e-mailaccounts toe te staan, te beheren en te beveiligen via intune MDM-beleid.


### <a name="recommended-email-clients"></a>Aanbevolen e-mailclients
De volgende e-mailclients ondersteunen moderne verificatie en voorwaardelijke toegang. 

|Platform|Client|Versie/notities|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [moderne verificatie inschakelen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication), [vereiste updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**Apparaten**|Outlook voor iOS|[Snufje](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook voor Android|[Snufje](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Spreek**|Niet ondersteund||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Aanbevolen clientplatforms bij het beveiligen van documenten
U wordt aangeraden de volgende clients te bezorgen wanneer een beleid voor beveiligd document is toegepast.

|Platform|Word/Excel/PowerPoint|OneNote|OneDrive-app|SharePoint-app|OneDrive-Synchronisatieclient|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows 8,1|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows 10|Ondersteund|Ondersteund|N.v.t.|N.v.t.|Voorbeeld<sup>*</sup>|
|Windows Phone 10|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|
|Android|Ondersteund|Ondersteund|Ondersteund|Ondersteund|N.v.t.|
|Apparaten|Ondersteund|Ondersteund|Ondersteund|Ondersteund|N.v.t.|
|macOS|Openbare preview|Openbare preview|N.v.t.|N.v.t.|Niet ondersteund|
|Spreek|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|Niet ondersteund|

<sup>*</sup> Meer informatie over het gebruik van voorwaardelijke toegang met de [synchronisatieclient van OneDrive](https://docs.microsoft.com/onedrive/enable-conditional-access).

### <a name="microsoft-365-client-support"></a>Ondersteuning voor Microsoft 365-clients
Zie de volgende artikelen voor meer informatie over clientondersteuning:
- [Ondersteuning voor Microsoft 365 client app-voorwaardelijke toegang](microsoft-365-client-support-conditional-access.md)
- [Ondersteuning voor Microsoft 365 client app-moderne verificatie](microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>Beheerdersaccounts beveiligen
Azure AD biedt een eenvoudige manier om te beginnen met het beveiligen van beheerderstoegang met een vooraf geconfigureerd beleid voor voorwaardelijke toegang. Ga in azure AD naar **voorwaardelijke toegang** en kijk naar dit beleid ( **Basislijnbeleid: MFA vereisen voor beheerders (preview)**. Selecteer dit beleid en selecteer vervolgens **beleid gebruiken direct**. 

Voor deze beleidsinstelling is MFA vereist voor de volgende rollen:
- Globale beheerders
- SharePoint-beheerders
- Exchange-beheerders
- Beheerders van voorwaardelijke toegang
- Beveiligingsbeheerders

Zie [basislijn beveiligingsbeleid voor Azure AD-beheerdersaccounts](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)voor meer informatie.

Aanvullende aanbevelingen zijn onder meer:
- U kunt het aantal permanente beheeraccounts beperken met behulp van Azure AD geprivilegieerde Identity Management. Zie aan de [slag met Pim](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Gebruik geprivilegieerd toegangsbeheer](../compliance/privileged-access-management-overview.md) om uw organisatie te beschermen tegenstrijdige beheerdersaccounts die bestaande beheerdersaccounts met toegang hebben tot gevoelige gegevens of toegang tot belangrijke configuratie-instellingen. 
- Gebruik alleen beheerdersaccounts voor beheer. Beheerders moeten beschikken over een afzonderlijke gebruikersaccount voor het regelmatig gebruik van niet-beheerdersaccounts en daarom indien nodig alleen hun beheerdersaccount gebruiken om een taak te voltooien die is gekoppeld aan hun functie functie. [Beheerdersrollen van Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) hebben belangrijke bevoegdheden dan microsoft 365-Services.
- Volg de aanbevolen procedures voor het beveiligen van geprivilegieerde accounts in azure AD zoals wordt beschreven in dit [artikel](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Volgende stappen

[De veelgebruikte beleidsregels voor identiteit en toegang tot apparaten configureren](identity-access-policies.md)

