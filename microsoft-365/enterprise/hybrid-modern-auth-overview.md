---
title: Overzicht van hybride moderne verificatie en vereisten voor gebruik met on-premises Skype voor Bedrijven- en Exchange-servers
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 10/15/2020
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
description: In dit artikel vindt u meer informatie over hybride moderne verificatie en de vereisten voor gebruik met on-premises Skype voor Bedrijven- en Exchange-servers.
ms.openlocfilehash: 33bcf9bde2cda0388160337d3ffe6b81ab94eb12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907526"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Overzicht van hybride moderne verificatie en vereisten voor het gebruik ervan met on-premises Skype voor Bedrijven- en Exchange-servers

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

_Moderne verificatie_ is een methode voor identiteitsbeheer die veiligere gebruikersverificatie en autorisatie biedt. Het is beschikbaar voor hybride implementaties van hybride implementaties voor Office 365 van skype voor Bedrijven-server on-premises en Exchange-server on-premises, evenals hybride versies van splitsdomein Skype voor Bedrijven. Dit artikel bevat koppelingen naar gerelateerde documenten over vereisten, het instellen/uitschakelen van moderne verificatie en een deel van de gerelateerde client (bijvoorbeeld. Outlook- en Skype-clients) informatie.

- [Wat is moderne verificatie?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [Wat verandert er wanneer ik moderne verificatie gebruik?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [De moderne verificatiestatus van uw on-premises omgeving controleren](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Voldoet u aan de vereisten voor moderne verificatie?](#do-you-meet-modern-authentication-prerequisites)
- [Wat moet ik nog meer weten voordat ik begin?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>Wat is moderne verificatie?
<a name="BKMK_WhatisModAuth"> </a>

Moderne verificatie is een overkoepelende term voor een combinatie van verificatie- en autorisatiemethoden tussen een client (bijvoorbeeld uw laptop of uw telefoon) en een server, evenals enkele beveiligingsmaatregelen die afhankelijk zijn van toegangsbeleid dat u mogelijk al kent. Deze omvat:

- **Verificatiemethoden:** meervoudige verificatie (MFA); smartcardverificatie; clientcertificaatverificatie
- **Autorisatiemethoden**: Microsoft's implementatie van Open Authorization (OAuth)
- **Beleid voor voorwaardelijke toegang:** Mam (Mobile Application Management) en Azure Active Directory (Azure AD) Voorwaardelijke toegang

Het beheren van gebruikersidentiteiten met moderne verificatie biedt beheerders veel verschillende hulpprogramma's voor het beveiligen van resources en biedt veiligere methoden voor identiteitsbeheer voor zowel on-premises (Exchange en Skype voor Bedrijven), hybride Exchange-scenario's als hybride Skype voor Bedrijven-scenario's voor hybride/gesplitste domeinen.

Aangezien Skype voor Bedrijven nauw samenwerkt met Exchange, wordt het aanmeldingsgedrag van gebruikers van Skype voor Bedrijven-client beïnvloed door de moderne verificatiestatus van Exchange. Dit is ook van toepassing als u een hybride architectuur voor skype voor Bedrijven _splitsdomein_ hebt, waarin u zowel Skype voor Bedrijven Online als Skype voor Bedrijven on-premises hebt, met gebruikers die zich op beide locaties bevinden.

Zie Ondersteuning voor [Office 365 Client App - Meervoudige verificatie voor](microsoft-365-client-support-multi-factor-authentication.md)meer informatie over moderne verificatie in Office 365.

> [!IMPORTANT]
> Vanaf augustus 2017 is moderne verificatie standaard ingeschakeld voor alle nieuwe Office 365-tenants die Skype voor Bedrijven online en Exchange Online bevatten. Bestaande tenants hebben geen wijziging in de standaard ma-status, maar alle nieuwe tenants ondersteunen automatisch de uitgebreide set identiteitsfuncties die u hierboven ziet. Zie de sectie De moderne verificatiestatus van uw [on-premises](hybrid-modern-auth-overview.md#BKMK_CheckStatus) omgeving controleren als u de status van uw ma wilt controleren.

## <a name="what-changes-when-i-use-modern-authentication"></a>Wat verandert er wanneer ik moderne verificatie gebruik?
<a name="BKMK_WhatChanges"> </a>

Wanneer u moderne verificatie gebruikt met on-premises Skype voor  Bedrijven *of* Exchange-server, bent u nog steeds gebruikers on-premises aan het authenticeren, maar het verhaal van het verlenen van toegang tot resources (zoals bestanden of e-mailberichten) verandert. Dit is de reden waarom, hoewel moderne verificatie over client- en servercommunicatie gaat, de stappen die zijn ondernomen tijdens het configureren van MA ertoe leiden dat de functie A0 (een beveiligings-tokenservice die wordt gebruikt door Azure AD) wordt ingesteld als Auth Server voor Skype voor Bedrijven en Exchange-server on-premises.

Met de wijziging in evoSTS kunnen uw on-premises servers profiteren van OAuth (tokenuitgifte) voor het autoriseren van uw clients en kunt u ook on-premises beveiligingsmethoden gebruiken die gebruikelijk zijn in de cloud (zoals Meervoudige verificatie). Daarnaast geeft de evoSTS tokens af waarmee gebruikers toegang tot resources kunnen aanvragen zonder hun wachtwoord op te geven als onderdeel van de aanvraag. Ongeacht waar uw gebruikers zich bevinden (van online of on-premises) en ongeacht welke locatie de benodigde resource host, Zal EvoSTS de kern worden van het autoriseren van gebruikers en clients zodra moderne verificatie is geconfigureerd.

Als een Skype voor Bedrijven-client bijvoorbeeld toegang moet hebben tot Exchange-server om namens een gebruiker agendagegevens op te halen, wordt hiervoor de Active Directory Authentication Library (ADAL) gebruikt. ADAL is een codebibliotheek die is ontworpen om beveiligde bronnen in uw adreslijst beschikbaar te maken voor clienttoepassingen met OAuth-beveiligingstokens. ADAL werkt samen met OAuth om claims te verifiëren en tokens uit te wisselen (in plaats van wachtwoorden), om een gebruiker toegang te verlenen tot een resource. In het verleden was de autoriteit in een transactie als deze , de server die weet hoe gebruikersclaims moeten worden gevalideerd en de benodigde tokens moet worden uitgeven, mogelijk een on-premises beveiligingstokenservice of zelfs Active Directory Federation Services. Moderne verificatie centraliseert deze autoriteit echter door Azure AD te gebruiken.

Dit betekent ook dat hoewel uw Exchange-server en Skype voor Bedrijven-omgevingen volledig on-premises zijn, de bevoegde server online is en uw on-premises omgeving de mogelijkheid moet hebben om een verbinding te maken en te onderhouden met uw Office 365-abonnement in de cloud (en het Azure AD-exemplaar dat uw abonnement gebruikt als adreslijst).

Wat verandert er niet? Of u nu een hybride splitsdomein gebruikt of on-premises Skype voor Bedrijven- en Exchange-server gebruikt, alle gebruikers moeten eerst *on-premises verifiëren.* In een hybride implementatie van moderne verificatie wijzen _Lyncdiscovery_ en _Autodiscovery_ beide naar uw on-premises server.

> [!IMPORTANT]
> Als u de specifieke Skype voor Bedrijven-toologieën wilt kennen die worden ondersteund met MA, wordt dat [hier beschreven.](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>De moderne verificatiestatus van uw on-premises omgeving controleren
<a name="BKMK_CheckStatus"> </a>

Omdat moderne verificatie de autorisatieserver wijzigt die wordt gebruikt wanneer services OAuth/S2S gebruiken, moet u weten of moderne verificatie is ingeschakeld of uitgeschakeld voor uw on-premises Skype voor Bedrijven- en Exchange-omgevingen. U kunt de status op uw Exchange-servers controleren door de volgende PowerShell-opdracht uit te voeren:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Als de waarde van de _eigenschap OAuth2ClientProfileEnabled_ **Onwaar** is, is moderne verificatie uitgeschakeld.

Zie [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)voor meer informatie over Get-OrganizationConfig cmdlet.

U kunt uw Skype voor Bedrijven-servers controleren door de volgende PowerShell-opdracht uit te voeren:

```powershell
Get-CSOAuthConfiguration
```

Als de opdracht een lege _eigenschap OAuthServers_ retourneert of als de waarde van de eigenschap _ClientADALAuthOverride_ niet is toegestaan, is moderne verificatie uitgeschakeld.

Zie [Get-CsOAuthConfiguration](/powershell/module/skype/get-csoauthconfiguration)voor meer informatie over Get-CsOAuthConfiguration cmdlet.

## <a name="do-you-meet-modern-authentication-prerequisites"></a>Voldoet u aan de vereisten voor moderne verificatie?

Controleer en controleer deze items uit uw lijst voordat u doorgaat:

- **Specifiek voor Skype voor Bedrijven**
  - Alle servers moeten een cumulatieve update van mei 2017 (CU5) voor Skype voor Bedrijven Server 2015 of hoger hebben
    - **Uitzondering** : De huidige versie (op basis van Lync 2013) kan worden gebruikt in de huidige versie .
  - Uw SIP-domein wordt toegevoegd als federatief domein in Office 365
  - Alle SFB-front ends moeten verbindingen hebben die uitgaand zijn van internet, met Office 365 Authentication URL's (TCP 443) en bekende certificaatwortel-CRLs (TCP 80) die worden vermeld in rijen 56 en 125 van de sectie 'Microsoft 365 Common and Office' van [Office 365-URL's](urls-and-ip-address-ranges.md)en IP-adresbereiken.

- **Skype voor Bedrijven on-premises in een hybride Office 365-omgeving**
  - Een implementatie van Skype voor Bedrijven Server 2019 met alle servers waarop Skype voor Bedrijven Server 2019 wordt uitgevoerd.
  - Een implementatie van Skype voor Bedrijven Server 2015 met alle servers waarop Skype voor Bedrijven Server 2015 wordt uitgevoerd.
  - Een implementatie met maximaal twee verschillende serverversies zoals hieronder wordt vermeld:
    - Skype for Business Server 2015
    - Skype for Business Server 2019
  - Alle Skype voor Bedrijven-servers moeten de meest recente cumulatieve updates hebben geïnstalleerd, zie [Skype voor Bedrijven Server-updates](/skypeforbusiness/sfb-server-updates) om alle beschikbare updates te vinden en te beheren.
  - Er is geen Lync Server 2010 of 2013 in de hybride omgeving.

>[!NOTE]
>Als uw front-endservers van Skype voor Bedrijven een proxyserver voor internettoegang gebruiken, moeten het gebruikte IP- en poortnummer van de proxyserver worden ingevoerd in de configuratiesectie van het web.config-bestand voor elke front-end.

- C:\Program Files\Skype voor Bedrijven Server 2015\Web Components\Web ticket\int\web.config
- C:\Program Files\Skype voor Bedrijven Server 2015\Web Components\Web ticket\ext\web.config

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
> Abonneer u op de RSS-feed voor URL's en IP-adresbereiken van [Office 365](urls-and-ip-address-ranges.md) om op de hoogte te blijven van de meest recente vermeldingen met vereiste URL's.

- **Exchange Server-specifiek**
  - U gebruikt Exchange Server 2013 CU19 en hoger, Exchange Server 2016 CU8 en hoger of Exchange Server 2019 CU1 en hoger.
  - Er is geen Exchange Server 2010 in de omgeving.
  - SSL Offloading is niet geconfigureerd. SSL-beëindiging en herversleuteling wordt ondersteund.
  - Als uw omgeving een proxyserverinfrastructuur gebruikt om servers verbinding te laten maken met internet, moet u ervoor zorgen dat op alle Exchange-servers de proxyserver is gedefinieerd in de eigenschap [InternetWebProxy.](/powershell/module/exchange/set-exchangeserver)

- **Exchange Server on-premises in een hybride Office 365-omgeving**

  - Als u Exchange Server 2013 gebruikt, moet ten minste één server de serverrollen Postvak en Client Access hebben geïnstalleerd. Hoewel het mogelijk is om de rollen Postvak en ClientToegang op afzonderlijke servers te installeren, raden we u ten zeerste aan beide rollen op dezelfde server te installeren om extra betrouwbaarheid en verbeterde prestaties te bieden.
  - Als u exchange server 2016 of een nieuwere versie gebruikt, moet ten minste één server de postvakserverrol hebben geïnstalleerd.
  - Er is geen Exchange Server 2007 of 2010 in de hybride omgeving.
  - Op alle Exchange-servers moeten de meest recente cumulatieve updates zijn geïnstalleerd, zie [Exchange upgraden](/exchange/plan-and-deploy/install-cumulative-updates) naar de meest recente cumulatieve updates om alle beschikbare updates te zoeken en te beheren.

- **Vereisten voor Exchange-client en protocol**

    De beschikbaarheid van moderne verificatie wordt bepaald door de combinatie van de client, het protocol en de configuratie. Als moderne verificatie niet wordt ondersteund door de client, het protocol en/of de configuratie, blijft de client gebruikmaken van oudere verificatie.
  
    De volgende clients en protocollen ondersteunen moderne verificatie met on-premises Exchange wanneer moderne verificatie is ingeschakeld in de omgeving:

  |**Clients**|**Primair protocol**|**Opmerkingen**|
  |:-----|:-----|:-----|
  |Outlook 2013 en hoger  <br/> |MAPI via HTTP  <br/> |MAPI via HTTP moet binnen Exchange zijn ingeschakeld om gebruik te kunnen maken van moderne verificatie met deze clients (meestal ingeschakeld of Waar voor nieuwe installaties van Exchange 2013 Service Pack 1 en hoger); Zie Hoe moderne verificatie werkt voor [office 2013- en Office 2016-client-apps](modern-auth-for-office-2013-and-2016.md)voor meer informatie.  <br/> Controleer of u de minimaal vereiste build van Outlook hebt uitgevoerd. zie [Nieuwste updates voor versies van Outlook die Windows Installer (MSI) gebruiken.](/officeupdates/outlook-updates-msi)  <br/> |
  |Outlook 2016 voor Mac en hoger  <br/> |Exchange-webservices  <br/> |  <br/> |
  |Outlook voor iOS en Android  <br/> | Synchronisatietechnologie van Microsoft <br/> |Zie [Hybride moderne verificatie gebruiken met Outlook voor iOS en Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) voor meer informatie.  <br/> |
  |Exchange ActiveSync-clients (bijvoorbeeld iOS11 Mail)  <br/> |Exchange ActiveSync  <br/> |Voor Exchange ActiveSync-clients die moderne verificatie ondersteunen, moet u het profiel opnieuw maken om over te schakelen van basisverificatie naar moderne verificatie.  <br/> |

    Clients en/of protocollen die niet worden vermeld (bijvoorbeeld POP3) ondersteunen geen moderne verificatie met on-premises Exchange en blijven gebruikmaken van oudere verificatiemechanismen, zelfs nadat moderne verificatie is ingeschakeld in de omgeving.

- **Algemene vereisten**
  - Scenario's voor resource forest vereisen een vertrouwen in twee-weg met het account forest om ervoor te zorgen dat de juiste SID-opzoekingen worden uitgevoerd tijdens hybride moderne verificatieaanvragen. 
  - Als u AD FS gebruikt, hebt u windows 2012 R2 AD FS 3.0 en hoger voor federatie.
  - Uw identiteitsconfiguraties zijn een van de typen die worden ondersteund door Azure AD Connect, zoals wachtwoordhashsynchronisatie, wachtwoordverificatie en on-premises STS die worden ondersteund door Office 365.
  - Azure AD Connect is geconfigureerd en werkt voor gebruikersreplicatie en -synchronisatie.
  - U hebt geverifieerd dat hybride is geconfigureerd met de exchange classic hybrid topology-modus tussen uw on-premises en Office 365-omgeving. Officiële ondersteuningsverklaring voor Exchange hybrid zegt dat u de huidige CU of de huidige CU - 1 moet hebben.
    > [!NOTE]
    > Hybride moderne verificatie wordt niet ondersteund met de [hybride agent.](/exchange/hybrid-deployment/hybrid-agent)

  - Zorg ervoor dat zowel een on-premises testgebruiker als een hybride testgebruiker die is thuis in Office 365, zich kan aanmelden bij de skype voor Bedrijven-bureaubladclient (als u moderne verificatie met Skype wilt gebruiken) en Microsoft Outlook (als u moderne verificatie met Exchange wilt gebruiken).

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>Wat moet ik nog meer weten voordat ik begin?
<a name="BKMK_Whatelse"> </a>

- Alle scenario's voor on-premises servers omvatten het instellen van moderne verificatie on-premises (in feite is er voor Skype voor Bedrijven een lijst met ondersteunde excuses) zodat de server die verantwoordelijk is voor verificatie en autorisatie zich in de Microsoft Cloud (de beveiligings-tokenservice van Azure AD, genaamd 'evoSTS') en Azure AD bijwerkt over de URL's of naamruimten die worden gebruikt door uw on-premises installatie van Skype voor Bedrijven of Exchange. On-premises servers nemen daarom een Microsoft Cloud-afhankelijkheid aan. Het nemen van deze actie kan worden beschouwd als het configureren van 'hybride auth'.
- Dit artikel bevat koppelingen naar anderen die u helpen bij het kiezen van ondersteunde moderne verificatie-toologieën (alleen nodig voor Skype voor Bedrijven) en artikelen met een overzicht van de installatiestappen of stappen voor het uitschakelen van moderne verificatie, voor on-premises Exchange-on-premises en Skype voor Bedrijven on-premises. Favoriete deze pagina in uw browser als u een thuisbasis nodig hebt voor het gebruik van moderne verificatie in uw serveromgeving.

## <a name="related-topics"></a>Verwante onderwerpen
<a name="BKMK_URLListforMA"> </a>

- [Exchange Server on-premises configureren voor moderne verificatie](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Skype voor Bedrijven-excuses ondersteund met moderne verificatie](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
- [Skype voor Bedrijven on-premises configureren voor het gebruik van moderne verificatie](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Hybride moderne verificatie verwijderen of uitschakelen uit Skype voor Bedrijven en Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)