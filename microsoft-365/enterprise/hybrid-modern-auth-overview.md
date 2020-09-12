---
title: Hybride overzicht van de hybride verificatie en vereisten voor het gebruik van on-premises Skype voor bedrijven en Exchange-servers
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 04/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over hybride moderne verificatie en de vereisten voor gebruik met on-premises Skype voor bedrijven en Exchange-servers.
ms.openlocfilehash: 1e0330bd62d9098f11a12b44b46e9ace30b59420
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546442"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Hybride overzicht van de hybride verificatie en vereisten voor het gebruik van on-premises Skype voor bedrijven en Exchange-servers

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

_Moderne verificatie_ is een methode van identiteitsbeheer die een betere verificatie en autorisatie van gebruikers biedt. Deze is beschikbaar voor hybride implementaties van Office 365 voor de on-premises implementatie van Skype voor bedrijven server on-premises en Exchange Server on-premises, en ook in gesplitste domeinen voor Skype voor bedrijven-hybriden. Dit artikel bevat koppelingen naar gerelateerde documenten over vereisten, installatie/uitschakelen van moderne verificatie en tot enkele van de gerelateerde clients (ex. Informatie voor Outlook en Skype-clients.

- [Wat is moderne verificatie?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [Welke wijzigingen moet ik aanbrengen als ik moderne verificatie gebruik?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [De moderne verificatiestatus van uw on-premises omgeving controleren](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Voldoen de moderne verificatievereisten?](#do-you-meet-modern-authentication-prerequisites)
- [Wat moet ik nog meer weten voordat ik begint?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>Wat is moderne verificatie?
<a name="BKMK_WhatisModAuth"> </a>

Moderne verificatie is een overkoepelende term voor een combinatie van authenticatie-en autorisatie methoden tussen een client (bijvoorbeeld uw laptop of telefoon) en een server, evenals enkele beveiligingsmaatregelen die afhankelijk zijn van Access-beleid waarbij u mogelijk al bekend bent. Deze omvat:

- **Verificatiemethoden**: multi-factor Authentication (MFA); smartcard Authentication; verificatie op basis van clientcertificaat
- **Verificatiemethoden**: de implementatie van Microsoft Open Authorization (OAuth)
- **Beleid voor voorwaardelijke toegang**: Mobile Application Management (mam) en Azure Active Directory (Azure AD) voorwaardelijke toegang

Het beheren van gebruikersidentiteiten met moderne verificatie biedt beheerders een groot aantal hulpprogramma's voor het beveiligen van bronnen en biedt veiligere methoden van Identiteitsbeheer voor zowel on-premises (Exchange als Skype voor bedrijven), Exchange hybride en Skype voor bedrijven-scenario's voor hybride/gesplitste domeinen.

Omdat Skype voor bedrijven nauw samen met Exchange werkt, zien de gebruikers van de Skype voor bedrijven-client in de moderne verificatiestatus van Exchange rekening. Dit is ook van toepassing als u een hybride architectuur met een _gesplitst domein_ voor Skype voor bedrijven, waarbij u zowel Skype voor bedrijven online als Skype voor bedrijven on-premises hebt, met gebruikers op beide locaties.

Zie voor meer informatie over moderne verificatie in Office 365 [office 365 client-app voor ondersteuning-moderne verificatie](microsoft-365-client-support-modern-authentication.md).

> [!IMPORTANT]
> Met ingang van 2017 wordt voor alle nieuwe Office 365-tenants met Skype voor bedrijven online en Exchange Online moderne verificatie ingeschakeld. Bestaande tenants hebben geen wijziging in de standaard-MA-status, maar alle nieuwe tenants ondersteunen automatisch de uitgebreide set met identiteits functies die hierboven worden weergegeven. Zie de [status van de moderne verificatie voor uw on-premises omgeving controleren](hybrid-modern-auth-overview.md#BKMK_CheckStatus) voor informatie over het controleren van uw ma-status.

## <a name="what-changes-when-i-use-modern-authentication"></a>Welke wijzigingen moet ik aanbrengen als ik moderne verificatie gebruik?
<a name="BKMK_WhatChanges"> </a>

Wanneer u moderne verificatie gebruikt met lokale Skype voor bedrijven of Exchange Server, wordt u nog steeds aangeraden gebruikers on-premises te *verifiëren* , maar het *verhaal van de* toegang tot bronnen (zoals bestanden of e-mailberichten) wordt gewijzigd. Aangezien moderne verificatie over client-en servercommunicatie gaat, zijn de stappen voor het configureren van het MA-resultaat in evoSTS (een beveiligings token service die wordt gebruikt door Azure AD) ingesteld als auth server voor Skype voor bedrijven en Exchange Server on-premises.

Met de Change to evoSTS kunnen uw on-premises servers gebruikmaken van OAuth (tokenuitgifte) voor het machtigen van uw klanten, en uw on-premises beveiligingsmethoden die in de cloud worden gebruikt, zoals meervoudige verificatie, kunnen worden gebruikt. Daarnaast kunnen de tokens voor evoSTS-kwesties waarmee gebruikers toegang kunnen aanvragen tot bronnen, zonder dat ze hun wachtwoord moeten opgeven als onderdeel van de aanvraag. Ongeacht waar de gebruikers wonen (online of on-premises), en ongeacht welke locatie de benodigde resource host, wordt EvoSTS de kern van het verlenen van gebruikers en clients wanneer moderne verificatie is geconfigureerd.

Als een Skype voor bedrijven-client bijvoorbeeld toegang moet hebben tot de Exchange-Server om agendagegevens te verkrijgen namens een gebruiker, wordt hiervoor de Active Directory Authentication Library (ADAL) gebruikt. ADAL is een codebibliotheek waarmee de beveiligde bronnen in de adreslijst beschikbaar worden gemaakt voor clienttoepassingen via OAuth-beveiligingstokens. ADAL werkt met OAuth om claims en tokens voor Exchange (in plaats van wachtwoorden) te controleren, om een gebruiker toegang te verlenen tot een bron. In het verleden heeft de Authority in een transactie zoals deze, de server die weet hoe gebruikersclaims kunnen valideren en de benodigde tokens te verstrekken, mogelijk een beveiligingstoken service on-premises of zelfs Active Directory Federation Services. Maar moderne verificatie centraliseert de overheid via Azure AD.

Dit betekent ook dat hoewel uw Exchange-Server en de Skype voor bedrijven-omgeving volledig on-premises zijn en uw on-premises omgeving de mogelijkheid heeft om een verbinding te maken en te onderhouden met uw Office 365-abonnement in de Cloud (en het exemplaar van Azure AD dat uw abonnement als de adreslijst gebruikt).

Wat blijft er ongewijzigd? Ongeacht of u zich in een hybride domein bevindt of gebruikmaakt van Skype voor bedrijven en Exchange Server on-premises, moeten alle gebruikers *zich eerst on-premises*verifiëren. In een hybride implementatie van moderne verificatie, _Lyncdiscovery_ en _Autodiscover_ to your on-premises server.

> [!IMPORTANT]
> Als u wilt weten welke Skype voor bedrijven-topologieën worden ondersteund met MA, wordt deze [hier beschreven](https://technet.microsoft.com/library/mt803262.aspx).

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>De moderne verificatiestatus van uw on-premises omgeving controleren
<a name="BKMK_CheckStatus"> </a>

Aangezien moderne verificatie de autorisatieserver wijzigt die wordt gebruikt wanneer services gebruikmaken van OAuth/S2S, moet u weten of moderne verificatie is ingeschakeld of uitgeschakeld voor uw on-premises Skype voor bedrijven en Exchange-omgevingen. U kunt de status van uw Exchange-servers controleren door de volgende PowerShell-opdracht uit te voeren:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Als de waarde van de eigenschap _OAuth2ClientProfileEnabled_ niet **waar**is, is moderne verificatie uitgeschakeld.

Zie [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)voor meer informatie over de cmdlet Get-OrganizationConfig.

U kunt uw Skype voor bedrijven-servers controleren door de volgende PowerShell-opdracht uit te voeren:

```powershell
Get-CSOAuthConfiguration
```

Als de opdracht een lege _OAuthServers_ -eigenschap oplevert of als de waarde van de eigenschap _ClientADALAuthOverride_ niet is **toegestaan**, is moderne verificatie uitgeschakeld.

Zie [Get-CsOAuthConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csoauthconfiguration)voor meer informatie over de cmdlet Get-CsOAuthConfiguration.

## <a name="do-you-meet-modern-authentication-prerequisites"></a>Voldoen de moderne verificatievereisten?

Controleer de items uit uw lijst voordat u verder gaat:

- **Specifiek voor Skype voor bedrijven**
  - Op alle servers moet de cumulatieve update van mei 2017 (CU5 hoger vereist) voor Skype voor bedrijven server 2015 of hoger zijn geïnstalleerd.
    - **Uitzondering** : het filiaal toestel (SBA) kan zich bevinden op de huidige versie (op basis van Lync 2013)
  - Uw SIP-domein wordt toegevoegd als een federatief domein in Office 365
  - Alle SFB-front-ends moeten verbindingen hebben via het Internet, naar de Url's van Office 365-authenticatie (TCP 443) en bekende certificaat basis-Crl's (TCP 80) die worden weergegeven in rijen 56 en 125 van de sectie ' Microsoft 365 common and Office ' van [Office 365-url's en IP-](urls-and-ip-address-ranges.md)adresbereiken.

- **Skype voor bedrijven on-premises in een hybride Office 365-omgeving**
  - Een Skype voor bedrijven server 2019-implementatie waarbij Skype voor bedrijven server 2019 wordt uitgevoerd op alle servers.
  - Een Skype voor bedrijven server 2015-implementatie waarbij Skype voor bedrijven server 2015 wordt uitgevoerd op alle servers.
  - Een implementatie met een maximum van twee verschillende server versies, zoals hieronder aangegeven:
    - Skype voor bedrijven server 2015
    - Skype voor bedrijven server 2019
  - Voor alle Skype voor bedrijven-servers moet de nieuwste cumulatieve updates zijn geïnstalleerd, Zie [updates voor Skype voor bedrijven server](https://docs.microsoft.com/skypeforbusiness/sfb-server-updates) om alle beschikbare updates te zoeken en beheren.
  - Er is geen Lync Server 2010 of 2013 in de hybride omgeving.

>[!NOTE]
>Als uw front-end servers van Skype voor bedrijven een proxyserver gebruiken voor Internet toegang, moet het gebruikte IP-adres en poortnummer van de proxyserver in de sectie configuratie van het web.config-bestand voor elke front-end worden ingevoerd.

- C:\Program Files\Skype voor bedrijven server 2015 \ Web Components\Web ticket\int\web.config
- C:\Program Files\Skype voor bedrijven server 2015 \ Web Components\Web ticket\ext\web.config

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> Zorg ervoor dat u een abonnement hebt op de RSS-feed voor [Office 365-url's en IP-](urls-and-ip-address-ranges.md) adresbereiken, zodat u actuele resultaten krijgt met de meest recente vermeldingen van de vereiste url's.

- **Specifiek voor Exchange Server**
  - U gebruikt Exchange Server 2013 CU19 en up, Exchange Server 2016 CU8 en up, of Exchange Server 2019 CU1 en up.
  - Er is geen Exchange Server 2010 in de omgeving.
  - SSL-offloading is niet geconfigureerd. SSL-beëindiging en opnieuw versleutelen wordt ondersteund.
  - In het geval dat uw omgeving gebruikmaakt van een proxyserver-infrastructuur, zodat servers verbinding kunnen maken met internet, moet u ervoor zorgen dat alle Exchange-servers de proxyserver hebben gedefinieerd in de eigenschap [InternetWebProxy](https://technet.microsoft.com/library/bb123716%28v=exchg.160%29.aspx) .

- **Exchange Server on-premises in een hybride Office 365-omgeving**

  - Als u Exchange Server 2013 gebruikt, moet minimaal één server beschikken over de serverrollen postvak en client toegang. Hoewel het mogelijk is om het postvak en de functies voor client toegang op afzonderlijke servers te installeren, wordt u ten zeerste aangeraden beide rollen op dezelfde server te installeren voor meer betrouwbaarheid en betere prestaties te bieden.
  - Als u Exchange Server 2016 of een nieuwere versie gebruikt, moet ten minste één server de functie postvakserver hebben geïnstalleerd.
  - Er is geen Exchange Server 2007 of 2010 in de hybride omgeving.
  - Voor alle Exchange-servers moet de actuele cumulatieve updates zijn geïnstalleerd, Zie [Exchange bijwerken naar de meest recente cumulatieve updates](https://docs.microsoft.com/exchange/plan-and-deploy/install-cumulative-updates?view=exchserver-2019) om alle beschikbare updates te zoeken en te beheren.

- **Client-en protocol vereisten voor Exchange**

  - De volgende clients ondersteunen moderne verificatie:

  |**Emulatieclients**|**Primair protocol**|**Opmerkingen**|
  |:-----|:-----|:-----|
  |Outlook 2013 en Outlook 2016  <br/> |MAPI via HTTP  <br/> |MAPI via HTTP moet zijn ingeschakeld in Exchange om moderne verificatie met deze clients mogelijk te maken (meestal ingeschakeld of waar voor nieuwe installaties van Exchange 2013 Service Pack 1 en hoger). Zie de werking [van moderne verificatie voor office 2013-en office 2016-clienttoepassingen](modern-auth-for-office-2013-and-2016.md)voor meer informatie.  <br/> Zorg ervoor dat u de minimaal vereiste build van Outlook uitvoert. Zie [de meest recente updates voor versies van Outlook die gebruikmaken van Windows Installer (MSI)](https://docs.microsoft.com/officeupdates/outlook-updates-msi).  <br/> |
  |Outlook 2016 voor Mac  <br/> |Exchange-webservices  <br/> |  <br/> |
  |Outlook voor iOS en Android  <br/> |  <br/> |Zie [hybride moderne verificatie gebruiken met Outlook voor IOS en Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) voor meer informatie.  <br/> |
  |Exchange ActiveSync-clients (bijvoorbeeld E-mail van Ios 11)  <br/> |Exchange ActiveSync  <br/> |Voor Exchange ActiveSync-clients die moderne verificatie ondersteunen, moet u het profiel opnieuw maken om te overstappen van basisauthenticatie met moderne verificatie.  <br/> |

- **Algemene vereisten**
  - Als u AD FS gebruikt, moet u beschikken over Windows 2012 R2 AD FS 3,0 en hoger voor Federatie.
  - Uw identiteits configuraties zijn alle typen die worden ondersteund door Azure AD Connect, zoals wachtwoord hash-synchronisatie, Pass-Through-verificatie en on-premises STS, ondersteund door Office 365.
  - Azure AD Connect geconfigureerd en functioneert voor gebruikers replicatie en-synchronisatie.
  - U hebt gecontroleerd of Hybrid is geconfigureerd met Exchange Classic Hybrid topologie modus tussen uw on-premises en Office 365-omgeving. Voor de officiële ondersteunings verklaring voor Exchange Hybrid wordt aangegeven dat u huidige CU of huidige CU-1 moet hebben.
    > [!NOTE]
    > Hybride moderne verificatie wordt niet ondersteund met de [Hybrid agent](https://docs.microsoft.com/exchange/hybrid-deployment/hybrid-agent).

  - Zorg ervoor dat zowel een on-premises testgebruiker, als een gebruikers van een hybride test, in Office 365, zich kunnen aanmelden bij de Skype voor bedrijven-desktopclient (als u moderne verificatie wilt gebruiken met Skype) en Microsoft Outlook (als u moderne verificatie wilt gebruiken met Exchange).

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>Wat moet ik nog meer weten voordat ik begint?
<a name="BKMK_Whatelse"> </a>

- Voor alle scenario's voor on-premises servers moet de moderne verificatie on-premises worden ingesteld. voor Skype voor bedrijven is er een lijst met ondersteunde topologieën, zodat de server die verantwoordelijk is voor verificatie en autorisatie, zich in het Microsoft Cloud-service beveiligingstoken (evoSTS ') bevindt, en de update van Azure AD over de Url's of naamruimten die door uw on-premises installatie van Skype voor bedrijven of Exchange worden gebruikt. Daarom nemen on-premises servers een Microsoft-Cloud dependency. Het kan zijn dat u deze actie moet uitvoeren als hybride auth te configureren.
- Dit artikel bevat koppelingen naar andere personen die u kunnen helpen bij het kiezen van ondersteunde topologie topologieën (alleen voor Skype voor bedrijven) en procedures voor het maken van een overzicht van de instellingsstappen, of stappen om moderne verificatie uit te schakelen voor Exchange on-premises en Skype voor bedrijven on-premises. Favoriet deze pagina in de browser als u een basisversie nodig hebt voor het gebruik van moderne verificatie in uw server omgeving.

## <a name="related-topics"></a>Verwante onderwerpen
<a name="BKMK_URLListforMA"> </a>

- [De on-premises Exchange-server configureren voor gebruik van moderne verificatie](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Skype voor bedrijven-topologie ondersteund met moderne verificatie](https://technet.microsoft.com/library/mt803262.aspx)
- [Skype voor bedrijven on-premises configureren voor gebruik van moderne verificatie](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Hybride, moderne verificatie van Skype voor bedrijven en Exchange verwijderen of uitschakelen](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
