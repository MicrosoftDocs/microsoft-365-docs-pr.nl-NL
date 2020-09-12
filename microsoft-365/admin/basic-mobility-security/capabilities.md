---
title: Mogelijkheden van eenvoudige mobiliteit en beveiliging
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Met basis mobiliteit en beveiliging kunt u mobiele apparaten beschermen en beheren.
ms.openlocfilehash: aed4f4c2d252e487d24496ac00f3de24bc57ab55
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545894"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Mogelijkheden van eenvoudige mobiliteit en beveiliging

Met basis mobiliteit en beveiliging kunt u mobiele apparaten zoals iPhones, iPads, Android-telefoons en Windows Phones gebruiken die door een licentie van Microsoft 365-gebruikers in uw organisatie worden gebruikt. U kunt beleidsregels voor mobiel Apparaatbeheer maken met instellingen waarmee u de toegang kunt beheren tot het Microsoft 365-e-mailadres en documenten van uw organisatie voor ondersteunde mobiele apparaten en apps. Als een apparaat gaat verloren of gestolen, kunt u het apparaat extern wissen om gevoelige organisatiegegevens te verwijderen.

## <a name="supported-devices"></a>Ondersteunde apparaten

U kunt basis mobiliteit en beveiliging gebruiken om de volgende apparaten te beveiligen en beheren.

- iOS 11,0 of hogere versies
    
- Android 5,0 of hogere versies<sup>3</sup>
    
- Windows 8,1<sup>1</sup>
    
- Windows 8,1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 Mobile<sup>2</sup>   

<sup>1</sup> Toegangsbeheer voor Windows 8,1 RT-apparaten is beperkt tot Exchange ActiveSync.

<sup>2</sup> Toegangsbeheer voor Windows 8,1 RT-apparaten is beperkt tot Exchange ActiveSync.
Voor toegangsbeheer voor Windows 10 is een abonnement met Azure AD Premium vereist en het apparaat moet deel uitmaken van Azure Active Directory.

<sup>3</sup> Toegangsbeheer voor Windows 8,1 RT-apparaten is beperkt tot Exchange ActiveSync.
Na 2020 juni kunnen Android-versies later dan 9 de wachtwoordinstellingen niet beheren, behalve op een Samsung Knox-apparaat.

>[!NOTE]
>Apparaten die al zijn geregistreerd bij eerdere versies van het besturingssysteem, blijven werken hoewel de functies zonder voorafgaande kennisgeving kunnen wijzigen.

Als in uw organisatie mobiele apparaten worden gebruikt die niet worden ondersteund door basis mobiliteit en beveiliging, is het raadzaam de gebruikers van de Exchange ActiveSync-app te gebruiken voor Microsoft 365-e-mail voor deze apparaten, zodat u de gegevens van uw organisatie veiliger kunt maken. Voor de stappen voor het blokkeren van Exchange ActiveSync raadpleegt u [instellingen voor Apparaattoegang beheren in eenvoudige mobiliteit en beveiliging](manage-device-access-settings.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Toegangsbeheer voor e-mail en documenten in Microsoft 365

Met de ondersteunde apps voor de verschillende typen mobiele apparaten in de volgende tabel kunt u gebruikers vragen zich aan te melden bij een eenvoudige mobiliteit en beveiliging waarbij een nieuw beleid voor het beheer van mobiele apparaten van toepassing is op het apparaat van een gebruiker en de gebruiker het apparaat niet eerder heeft geregistreerd. Als het apparaat van een gebruiker niet voldoet aan een beleid, is dit afhankelijk van de manier waarop u het beleid uitstelt, dat een gebruiker is geblokkeerd voor het openen van Microsoft 365-bronnen in deze apps of kan deze een beleidsschending melden, maar Microsoft 365 meldt.

|**Product**|**iOS 10,0 of later**|**Android 5,0 of hoger**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync bevat ingebouwde e-mail en apps van derden, zoals TouchDown, die gebruikmaken van Exchange ActiveSync versie 14,1 of hoger. |Adressen |E-mail |
|**Office**   en **OneDrive voor bedrijven** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Op telefoons en tablets**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Op alleen telefoons:** <br/> Office Mobile |

>[!NOTE]
- >Ondersteuning voor iOS 10,0 en hogere versies omvat iPhone-en iPad-apparaten.
- >Het beheer van BlackBerry-besturingssysteem apparaten wordt niet ondersteund door het hulpmiddel voor het beheer van mobiele apparaten voor Microsoft 365. Gebruik BlackBerry Business Cloud Services (BBCS) van BlackBerry om BlackBerry OS-apparaten te beheren. BlackBerry-apparaten met Android-besturingssysteem worden ondersteund als standaard Android-apparaten
- >Gebruikers hoeven niet te worden ingeschreven en worden niet geblokkeerd of gerapporteerd voor beleidsovertreding als ze gebruikmaken van de mobiele browser voor het openen van Microsoft 365 SharePoint-sites, documenten in Office Online of e-mail in Outlook Web app.
    
In het volgende diagram ziet u wat er gebeurt wanneer een gebruiker met een nieuw apparaat zich aanmeldt bij een app die toegangsbeheer ondersteunt voor basis mobiliteit en beveiliging. De gebruiker is geblokkeerd voor het openen van Microsoft 365-bronnen in de app totdat ze hun apparaat registreren.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Basisopties voor mobiliteit en beveiligingstoegang":::

Opmerking: beleidsregels en toegangsregels die zijn gemaakt in MDM voor Microsoft 365 Business Standard, negeren postvak beleid van het mobiele apparaat van Exchange ActiveSync en de regels voor Apparaattoegang die zijn gemaakt in het Exchange-Beheercentrum. Als een apparaat is ingeschreven in MDM voor Microsoft 365 Business Standard, wordt het postvak beleid mobiele apparaten van Exchange ActiveSync of de regel voor het openen van apparaten die op het apparaat zijn toegepast, genegeerd. Zie [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380)voor meer informatie over Exchange ActiveSync.

## <a name="policy-settings-for-mobile-devices"></a>Beleidsinstellingen voor mobiele apparaten

Als u een beleid maakt om toegang te blokkeren met bepaalde instellingen, zijn gebruikers geblokkeerd voor het openen van Microsoft 365-bronnen wanneer ze een ondersteunde app gebruiken die wordt vermeld in [het toegangsbeheer voor e-mail en documenten van Microsoft 365](capabilities.md). 

U kunt de volgende secties gebruiken om te voorkomen dat gebruikers toegang hebben tot Microsoft 365-bronnen:

- Beveiliging
    
- Versleuteling
    
- Jail verbroken
    
- Beheerd e-mail profiel  

In het volgende diagram ziet u bijvoorbeeld wat er gebeurt wanneer een gebruiker met een geregistreerd apparaat niet compatibel is met een beveiligingsinstelling in een beleid voor het beheer van mobiele apparaten dat van toepassing is op het apparaat. De gebruiker meldt zich aan bij een app die toegangsbeheer ondersteunt met basis mobiliteit en beveiliging. Het openen van Microsoft 365-bronnen in de app wordt geblokkeerd totdat het apparaat voldoet aan de beveiligingsinstelling.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Basis bericht over mobiliteit en beveiligings compliance":::

In de volgende secties vindt u een overzicht van de beleidsinstellingen die u kunt gebruiken om mobiele apparaten te beveiligen en te beheren die verbinding maken met uw Microsoft 365-organisatiebronnen.

## <a name="security-settings"></a>Beveiligingsinstellingen

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Wachtwoord vereisen|Ja|Ja|Ja|
|Eenvoudige wachtwoord voorkomen|Ja|Nee|Nee|
|Een alfanumeriek wachtwoord vereisen|Ja|Nee|Nee|
|Minimale wachtwoordlengte |Ja|Ja|Ja|
|Het aantal aanmeldingsfouten voordat het apparaat wordt gewist |Ja|Ja|Ja|
|Minuten van inactiviteit voordat het apparaat is vergrendeld |Ja|Ja|Ja|
|Wachtwoord verloopt (dagen) |Ja|Ja|Ja|
|Wachtwoordgeschiedenis onthouden en hergebruik verhinderen |Ja|Ja|Ja|

## <a name="encryption-settings"></a>Versleutelingsinstellingen 

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Gegevensversleuteling vereisen op apparaten<sup>1</sup> |Nee|Ja|Ja|

<sup>1</sup> Met Samsung Knox kunt u ook versleuteling vereisen voor opslagkaarten. 

## <a name="jail-broken-setting"></a>Jail verbroken instelling 

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Het apparaat kan niet worden jail gebroken of geroot. |Ja|Ja|Ja|

## <a name="managed-email-profile-option"></a>De optie beheerd e-mail profiel 

Met de volgende optie kunnen gebruikers verhinderen dat ze toegang hebben tot hun Microsoft 365-e-mail als ze een handmatig gemaakt e-mail profiel gebruiken. Gebruikers op iOS-apparaten moeten hun handmatig gemaakte e-mail profiel verwijderen voordat ze toegang hebben tot hun e-mail. Nadat het profiel is verwijderd, wordt er automatisch een nieuw profiel gemaakt op het apparaat. Zie [een bestaand e-mailaccount vinden](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)voor meer informatie over de manier waarop eindgebruikers compatibel kunnen zijn.

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|E-mail profiel wordt beheerd |Ja|Nee|Nee|

## <a name="cloud-settings"></a>Cloud instellingen 

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Gecodeerde back-up vereisen |Ja|Nee|Nee|
|Back-up van Cloud blokkeren |Ja|Nee|Nee|
|Documentsynchronisatie blokkeren |Ja|Nee|Nee|
|Foto synchronisatieblok keren  |Ja|Nee|Nee|
|Google back-up toestaan  |N.v.t.|Nee|Ja|
|Automatisch synchroniseren van Google-accounts toestaan  |N.v.t.|Nee|Ja|

## <a name="system-settings"></a>Systeeminstellingen 

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Schermopname blokkeren |Ja|Nee|Ja|
|De verzending van diagnostische gegevens van een apparaat blokkeren |Ja|Nee|Ja|

## <a name="application-settings"></a>Toepassingsinstellingen 

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Videovergaderingen blokkeren op apparaat |Ja|Nee|Nee|
|Toegang tot de toepassing Store blokkeren |Ja|Nee|Ja|
|Wachtwoord vereist wanneer u toegang hebt tot toepassingen archief |Nee|Ja|Ja|

## <a name="device-capabilities-settings"></a>Instellingen voor de apparaatfuncties 

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Verbinding met Verwisselbare opslag blokkeren |Ja|Ja|Nee|
|Bluetooth-verbinding blokkeren |Ja|Ja|Nee|

## <a name="additional-settings"></a>Meer instellingen

U kunt de volgende aanvullende beleidsinstellingen instellen met behulp van de PowerShell-cmdlets voor het & Beveiligingscentrum. Zie [beveiligings & PowerShell voor nalevings centrum](https://docs.microsoft.com/powershell/exchange/scc-powershell)voor meer informatie.

|**Naam instellen**|**iOS 7,1 en hoger**|**Android 5 en hoger**|
|:-----|:-----|:-----|
|CameraEnabled|Ja|Ja|
|RegionRatings|Ja|Nee|
|MoviesRatings|Ja|Nee|
|TVShowsRating |Ja|Nee|
|AppsRatings |Ja|Nee|
|AllowVoiceDialing |Ja|Nee|
|AllowVoiceAssistant |Ja|Nee|
|AllowAssistantWhileLocked  |Ja|Nee|
|AllowPassbookWhileLocked |Ja|Nee|
|MaxPasswordGracePeriod |Ja|Nee|
|PasswordQuality |Nee|Ja|
|SystemSecurityTLS  |Ja|Nee|
|WLANEnabled  |Nee|Nee|

## <a name="settings-supported-by-windows"></a>Door Windows ondersteunde instellingen 

U kunt Windows 10-apparaten beheren door deze als mobiele apparaten in te schrijven. Als een van toepassing zijnde beleid is geïmplementeerd, moeten gebruikers met Windows 10-apparaten zich voor de eerste keer registreren voor eenvoudige mobiliteit en beveiliging, zodat ze de e-mail van Microsoft 365 kunnen openen (hiervoor is een Azure AD Premium-abonnement vereist).

De volgende instellingen worden ondersteund voor Windows 10-apparaten die worden geregistreerd als mobiele apparaten. Met deze instelling worden gebruikers niet geblokkeerd voor het openen van Microsoft 365-bronnen.

### <a name="security-settings"></a>Beveiligingsinstellingen

- Een alfanumeriek wachtwoord vereisen

- Minimale wachtwoordlengte
    
- Het aantal aanmeldingsfouten voordat het apparaat wordt gewist
    
- Minuten van inactiviteit voordat het apparaat is vergrendeld
    
- Wachtwoord verloopt (dagen)
    
- Wachtwoordgeschiedenis onthouden en hergebruik verhinderen   

>[!NOTE]
>Met de volgende instellingen worden alleen wachtwoorden bestuurd voor lokale Windows-accounts. Windows-accounts die worden geleverd via lidmaatschap van een domein of Azure Active Directory, worden niet beïnvloed door deze instellingen.

### <a name="system-settings"></a>Systeeminstellingen

De verzending van diagnostische gegevens van een apparaat blokkeren.

### <a name="additional-settings"></a>Meer instellingen

U kunt deze extra beleidsinstellingen instellen met behulp van PowerShell-cmdlets:

- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus   

- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    

## <a name="remotely-wipe-a-mobile-device"></a>Extern wissen van een mobiel apparaat

Als een apparaat gaat verloren of gestolen, kunt u gevoelige organisatiegegevens verwijderen en de toegang tot uw Microsoft 365-organisatiebronnen helpen voorkomen door te wissen tegen beveiliging & compliance > **preventie van gegevensverlies**  >  **Device management**. U kunt selectief wissen om alleen bedrijfsgegevens te verwijderen of u kunt volledig wissen om alle gegevens van een apparaat te verwijderen en de fabrieksinstellingen van het apparaat te herstellen.

Zie [een mobiel apparaat wissen voor eenvoudige mobiliteit en beveiliging](wipe-mobile-device.md)voor meer informatie.

## <a name="related-topics"></a>Verwante onderwerpen

[Overzicht van basis mobiliteit en beveiliging voor Microsoft 365](overview.md)

[Beveiligingsbeleid voor apparaten maken in eenvoudige mobiliteit en beveiliging](create-device-security-policies.md)