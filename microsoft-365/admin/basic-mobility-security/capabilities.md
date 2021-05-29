---
title: Capaciteiten Basic Mobility en Security
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
description: Basismobiliteit en beveiliging kunnen u helpen bij het beveiligen en beheren van mobiele apparaten.
ms.openlocfilehash: 41df5bfba7362d9c2b3a47deca4e4586902bbd98
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706176"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Capaciteiten Basic Mobility en Security

Basismobiliteit en beveiliging kunnen u helpen bij het beveiligen en beheren van mobiele apparaten zoals iPhones, iPads, Androids en Windows Telefoons die worden gebruikt door gelicentieerde Microsoft 365 gebruikers in uw organisatie. U kunt beleidsregels voor beheer van mobiele apparaten maken met instellingen om de toegang tot de e-mail en documenten van uw organisatie Microsoft 365 voor ondersteunde mobiele apparaten en apps te beheren. Als een apparaat verloren of gestolen is, kunt u het apparaat op afstand wissen om gevoelige organisatiegegevens te verwijderen.

## <a name="supported-devices"></a>Ondersteunde apparaten

U kunt basismobiliteit en beveiliging gebruiken om de volgende apparaten te beveiligen en te beheren.

- iOS 11.0 of hoger

- Android 5.0 of hoger versies<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> Toegangsbeheer voor Windows 8.1 RT-apparaten is beperkt tot Exchange ActiveSync.

<sup>2</sup> Toegangsbeheer voor Windows 10 vereist een abonnement met Azure AD-Premium en het apparaat moet worden samengevoegd met Azure Active Directory.

<sup>3</sup> Na juni 2020 kunnen Android-versies later dan 9 geen wachtwoordinstellingen beheren, behalve op Samsung Knox-apparaten.

>[!NOTE]
>Apparaten die al zijn geregistreerd met eerdere OS-versies blijven werken, hoewel de mogelijkheden zonder kennisgeving kunnen veranderen.

Als personen in uw organisatie mobiele apparaten gebruiken die niet worden ondersteund door Basismobiliteit en Beveiliging, kunt u de toegang van Exchange ActiveSync-apps tot Microsoft 365-e-mail voor deze apparaten blokkeren om de gegevens van uw organisatie veiliger te maken. Zie Instellingen voor apparaattoegang beheren in Basismobiliteit en beveiliging voor Exchange ActiveSync voor stappen om de Exchange ActiveSync [te blokkeren.](manage-device-access-settings.md)

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Toegangsbeheer voor Microsoft 365 e-mail en documenten

De ondersteunde apps voor de verschillende typen mobiele apparaten in de volgende tabel vragen gebruikers zich aan te melden bij Basismobiliteit en Beveiliging, waarbij er een nieuw beleid voor mobiel apparaatbeheer is dat van toepassing is op het apparaat van een gebruiker en de gebruiker het apparaat nog niet eerder heeft geregistreerd. Als het apparaat van een gebruiker niet voldoet aan een beleid, kan een gebruiker, afhankelijk van de manier waarop u het beleid hebt ingesteld, worden geblokkeerd voor toegang tot Microsoft 365-resources in deze apps, of hebben ze mogelijk toegang, maar Microsoft 365 meldt een beleidsovertreding.

|**Product**|**iOS 10.0 of hoger**|**Android 5.0 of hoger**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync bevat ingebouwde e-mail en apps van derden, zoals TouchDown, die gebruikmaken van Exchange ActiveSync versie 14.1 of hoger. |E-mail |E-mail |
|**Office**   en  **OneDrive voor Bedrijven** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Op telefoons en tablets:**<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Alleen op telefoons:** <br/> Office Mobiel |

>[!NOTE]
- >Ondersteuning voor iOS 10.0 en nieuwere versies omvat iPhone en iPad apparaten.
- >Het beheer van BlackBerry OS-apparaten wordt niet ondersteund door Basisbeveiliging en Mobiliteit. Gebruik BlackBerry Business Cloud Services (BBCS) van BlackBerry om BlackBerry OS-apparaten te beheren. Blackberry-apparaten met Android OS worden ondersteund als standaard Android-apparaten
- >Gebruikers worden niet gevraagd zich in te schrijven en worden niet geblokkeerd of gerapporteerd voor beleidsovertreding als ze de mobiele browser gebruiken om toegang te krijgen tot Microsoft 365 SharePoint-sites, documenten in Office Online of e-mail in Outlook Web App.

In het volgende diagram ziet u wat er gebeurt wanneer een gebruiker met een nieuw apparaat zich meldt bij een app die toegangsbeheer ondersteunt met Basismobiliteit en Beveiliging. De gebruiker wordt geblokkeerd voor toegang tot Microsoft 365 resources in de app totdat hij of zij zijn of haar apparaat inschrijft.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Toegangsbeheer voor basismobiliteit en beveiliging":::

> [!NOTE]
> Beleidsregels en toegangsregels die zijn gemaakt in Basismobiliteit en beveiliging voor Microsoft 365 Business Standard, worden Exchange ActiveSync beleidsregels voor postvak op mobiele apparaten en regels voor apparaattoegang die zijn gemaakt in het Exchange beheercentrum. Nadat een apparaat is geregistreerd voor Basismobiliteit en beveiliging voor Microsoft 365 Business Standard, wordt elke Exchange ActiveSync beleid voor postvak voor mobiele apparaten of regel voor apparaattoegang die is toegepast op het apparaat, genegeerd. Zie Exchange ActiveSync in Exchange Online voor [meer Exchange ActiveSync informatie](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)over Exchange Online.

## <a name="policy-settings-for-mobile-devices"></a>Beleidsinstellingen voor mobiele apparaten

Als u een beleid maakt om toegang te blokkeren met bepaalde instellingen ingeschakeld, worden gebruikers geblokkeerd voor toegang tot Microsoft 365-resources wanneer ze een ondersteunde app gebruiken die wordt weergegeven in Access-besturingselement voor e-mail en documenten van [Microsoft 365.](capabilities.md) 

De instellingen die gebruikers kunnen blokkeren om toegang te krijgen tot Microsoft 365 resources, vindt u in deze secties:

- Beveiliging

- Versleuteling

- De cel is verbroken

- Beheerd e-mailprofiel  

In het volgende diagram ziet u bijvoorbeeld wat er gebeurt wanneer een gebruiker met een geregistreerd apparaat niet voldoet aan een beveiligingsinstelling in een beleid voor mobiel apparaatbeheer dat van toepassing is op het apparaat. De gebruiker meldt zich aan bij een app die toegangsbeheer ondersteunt met Basismobiliteit en Beveiliging. Ze worden geblokkeerd voor toegang tot Microsoft 365 resources in de app totdat hun apparaat voldoet aan de beveiligingsinstelling.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Bericht over naleving van basismobiliteit en beveiliging":::

In de volgende secties vindt u de beleidsinstellingen die u kunt gebruiken om mobiele apparaten te beveiligen en te beheren die verbinding maken met uw Microsoft 365 organisatiebronnen.

## <a name="security-settings"></a>Beveiligingsinstellingen

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Een wachtwoord vereisen|Ja|Ja|Ja|
|Eenvoudig wachtwoord voorkomen|Ja|Nee|Nee|
|Een alfanumeriek wachtwoord vereisen|Ja|Nee|Nee|
|Minimale wachtwoordlengte |Ja|Ja|Ja|
|Aantal aanmeldingsfouten voordat het apparaat wordt gewist |Ja|Ja|Ja|
|Minuten van inactiviteit voordat het apparaat is vergrendeld |Ja|Ja|Ja|
|Wachtwoordverloop (dagen) |Ja|Ja|Ja|
|Wachtwoordgeschiedenis onthouden en hergebruik voorkomen |Ja|Ja|Ja|

## <a name="encryption-settings"></a>Versleutelingsinstellingen

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Gegevensversleuteling vereisen op apparaten<sup>1</sup> |Nee|Ja|Ja|

<sup>1</sup> Met Samsung Knox kunt u ook versleuteling op opslagkaarten vereisen. 

## <a name="jail-broken-setting"></a>Instelling voor de cel met gebroken cel 

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Apparaat kan niet worden verbroken of geroot |Ja|Ja|Ja|

## <a name="managed-email-profile-option"></a>Optie Beheerd e-mailprofiel 

Met de volgende optie kunnen gebruikers geen toegang krijgen tot hun Microsoft 365 e-mail als ze een handmatig gemaakt e-mailprofiel gebruiken. Gebruikers op iOS-apparaten moeten hun handmatig gemaakte e-mailprofiel verwijderen voordat ze toegang hebben tot hun e-mail. Nadat ze het profiel hebben verwijderd, wordt er automatisch een nieuw profiel gemaakt op het apparaat. Zie Een bestaand [e-mailaccount is gevonden](/intune-user-help/existing-company-email-account-found)voor instructies over hoe eindgebruikers compatibel kunnen worden.

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|E-mailprofiel wordt beheerd |Ja|Nee|Nee|

## <a name="cloud-settings"></a>Cloudinstellingen

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Versleutelde back-up vereisen |Ja|Nee|Nee|
|Cloudback-up blokkeren |Ja|Nee|Nee|
|Documentsynchronisatie blokkeren |Ja|Nee|Nee|
|Fotosynchronisatie blokkeren  |Ja|Nee|Nee|
|Back-up van Google toestaan  |N.v.t.|Nee|Ja|
|Automatische synchronisatie van Google-account toestaan  |N.v.t.|Nee|Ja|

## <a name="system-settings"></a>Systeeminstellingen

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Schermopname blokkeren |Ja|Nee|Ja|
|Het verzenden van diagnostische gegevens vanaf een apparaat blokkeren |Ja|Nee|Ja|

## <a name="application-settings"></a>Toepassingsinstellingen

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Videoconferenties blokkeren op apparaat |Ja|Nee|Nee|
|Toegang tot het toepassingsopslagblok blokkeren |Ja|Nee|Ja|
|Wachtwoord vereisen bij het openen van het toepassingsopslag |Nee|Ja|Ja|

## <a name="device-capabilities-settings"></a>Instellingen voor apparaatfuncties

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Verbinding met verwisselbare opslag blokkeren |Ja|Ja|Nee|
|Verbinding Bluetooth blokkeren |Ja|Ja|Nee|

## <a name="additional-settings"></a>Aanvullende instellingen

U kunt de volgende aanvullende beleidsinstellingen instellen met behulp & PowerShell-cmdlets van het Compliancecentrum. Zie Security [& Compliance Center PowerShell voor meer informatie.](/powershell/exchange/scc-powershell)

|**Naam instellen**|**iOS 7.1 en hoger**|**Android 5 en hoger**|
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

## <a name="settings-supported-by-windows"></a>Instellingen ondersteund door Windows

U kunt uw Windows 10 beheren door ze in te schrijven als mobiele apparaten. Nadat een toepasselijk beleid is geïmplementeerd, moeten gebruikers met Windows 10-apparaten zich de eerste keer registreren voor Basismobiliteit en Beveiliging wanneer ze de ingebouwde e-mailapp gebruiken om toegang te krijgen tot hun Microsoft 365-e-mail (hiervoor is een Azure AD Premium-abonnement vereist).

De volgende instellingen worden ondersteund voor Windows 10 apparaten die zijn geregistreerd als mobiele apparaten. Met deze instelling kunnen gebruikers geen toegang krijgen tot Microsoft 365 resources.

### <a name="security-settings"></a>Beveiligingsinstellingen

- Een alfanumeriek wachtwoord vereisen

- Minimale wachtwoordlengte

- Aantal aanmeldingsfouten voordat het apparaat wordt gewist

- Minuten van inactiviteit voordat het apparaat is vergrendeld

- Wachtwoordverloop (dagen)

- Wachtwoordgeschiedenis onthouden en hergebruik voorkomen

>[!NOTE]
>De volgende instellingen voor het reguleren van wachtwoorden bepalen alleen de lokale Windows accounts. Windows accounts die worden geleverd via deelnemen aan een domein of Azure Active Directory worden niet beïnvloed door deze instellingen.

### <a name="system-settings"></a>Systeeminstellingen

Het verzenden van diagnostische gegevens vanaf een apparaat blokkeren.

### <a name="additional-settings"></a>Aanvullende instellingen

U kunt deze aanvullende beleidsinstellingen instellen met behulp van PowerShell-cmdlets:

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>Een mobiel apparaat op afstand wissen

Als een apparaat verloren gaat of wordt gestolen, kunt u gevoelige organisatiegegevens verwijderen en de toegang tot uw Microsoft 365-organisatiebronnen voorkomen door het beveiligings- & compliancecentrum > **Preventie** van gegevensverlies apparaatbeheer uit te  >  wissen. U kunt een selectief wissen om alleen organisatiegegevens of een volledig wissen te verwijderen om alle gegevens van een apparaat te verwijderen en terug tezetten naar de fabrieksinstellingen.

Zie Een mobiel apparaat [wissen in Basismobiliteit en Beveiliging voor meer informatie.](wipe-mobile-device.md)

## <a name="related-content"></a>Verwante inhoud

[Overzicht van basismobiliteit en](overview.md) beveiliging voor Microsoft 365 (artikel)\
[Apparaatbeveiligingsbeleid maken in Basismobiliteit en Beveiliging](create-device-security-policies.md) (artikel)