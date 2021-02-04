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
ms.openlocfilehash: b9b48f591f74bd508b20a851ec48a0d7132d6a84
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097102"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Overzicht van hybride moderne verificatie en vereisten voor het gebruik ervan met on-premises Skype voor Bedrijven- en Exchange-servers

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

_Moderne verificatie_ is een methode voor identiteitsbeheer die veiligere gebruikersverificatie en autorisatie biedt. Het is beschikbaar voor hybride Office 365-implementaties van de on-premises Skype voor Bedrijven-server en de Exchange-server on-premises, en voor hybride Skype voor Bedrijven-hybride domeinen. Dit artikel bevat koppelingen naar gerelateerde documenten over vereisten, het instellen/uitschakelen van moderne verificatie en een deel van de gerelateerde client (bijvoorbeeld. Informatie over Outlook- en Skype-clients.

- [Wat is moderne verificatie?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [Welke wijzigingen worden aangebracht wanneer ik moderne verificatie gebruik?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [De moderne verificatiestatus van uw on-premises omgeving controleren](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Voldoet u aan de vereisten voor moderne verificatie?](#do-you-meet-modern-authentication-prerequisites)
- [Wat moet ik nog meer weten voordat ik begin?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>Wat is moderne verificatie?
<a name="BKMK_WhatisModAuth"> </a>

Moderne verificatie is een overkoepelende term voor een combinatie van verificatie- en autorisatiemethoden tussen een client (bijvoorbeeld uw laptop of uw telefoon) en een server, evenals enkele beveiligingsmaatregelen die afhankelijk zijn van toegangsbeleid dat u mogelijk al kent. Deze omvat:

- **Verificatiemethoden:** Meervoudige verificatie (MFA); smartcardverificatie; verificatie op basis van clientcertificaat
- **Autorisatiemethoden:** Microsoft's implementatie van Open Authorization (OAuth)
- **Beleid voor voorwaardelijke** toegang: mobile application management (MAM) en voorwaardelijke toegang van Azure Active Directory (Azure AD)

Het beheren van gebruikersidentiteiten met moderne verificatie biedt beheerders vele verschillende hulpprogramma's die ze kunnen gebruiken voor het beveiligen van resources en biedt veiligere methoden voor identiteitsbeheer voor zowel on-premises (Exchange en Skype voor Bedrijven), Exchange Hybrid en scenario's voor hybride/gesplitst domein voor Skype voor Bedrijven.

Skype voor Bedrijven werkt nauw samen met Exchange, dus het aanmeldingsgedrag van Skype voor Bedrijven-clientgebruikers wordt beïnvloed door de moderne verificatiestatus van Exchange. Dit is ook van toepassing als  u een hybride architectuur voor skype voor Bedrijven gesplitst domein hebt, waarin u zowel Skype voor Bedrijven Online als Skype voor Bedrijven on-premises hebt, waarbij gebruikers op beide locaties zijn geplaatst.

Zie de ondersteuning van de [Office 365-client-app - Meervoudige](microsoft-365-client-support-multi-factor-authentication.md)verificatie voor meer informatie over moderne verificatie in Office 365.

> [!IMPORTANT]
> Vanaf augustus 2017 is moderne verificatie standaard ingeschakeld voor alle nieuwe Office 365-tenants die Skype voor Bedrijven Online en Exchange Online bevatten. De standaard ma-status van bestaande tenants verandert niet, maar alle nieuwe tenants ondersteunen automatisch de uitgebreide set identiteitsfuncties die u hierboven ziet. Zie de sectie De moderne verificatiestatus van uw [on-premises](hybrid-modern-auth-overview.md#BKMK_CheckStatus) omgeving controleren als u de status van de gegevenscontrole wilt controleren.

## <a name="what-changes-when-i-use-modern-authentication"></a>Welke wijzigingen worden aangebracht wanneer ik moderne verificatie gebruik?
<a name="BKMK_WhatChanges"> </a>

Bij het gebruik van moderne verificatie met on-premises Skype  voor Bedrijven *of* Exchange Server, bent u nog steeds on-premises gebruikers aan het authenticeren, maar het verhaal over het authoriseren van hun toegang tot bronnen (zoals bestanden of e-mailberichten) verandert. Daarom, hoewel moderne verificatie gaat over client- en servercommunicatie, resulteren de stappen die zijn ondernomen tijdens het configureren van MA in een on-premises beveiligings tokenservice (een beveiligings tokenservice die door Azure AD wordt gebruikt) als auth-server voor Skype voor Bedrijven en Exchange-server on-premises.

Met de wijziging van uw on-premises servers kunnen uw on-premises servers gebruikmaken van OAuth (token uitgifte) voor het autoriseren van uw clients, en kunnen uw on-premises beveiligingsmethoden gebruiken die veel worden gebruikt in de cloud (zoals Meervoudige verificatie). De tokens geven bovendien uit waarmee gebruikers toegang tot resources kunnen aanvragen zonder hun wachtwoord op te geven als onderdeel van de aanvraag. Ongeacht waar uw gebruikers zijn geplaatst (online of on-premises) en ongeacht de locatie waarop de benodigde bron wordt host, wordt DezeSTS de kern van het beheer van gebruikers en clients nadat moderne verificatie is geconfigureerd.

Als een Skype voor Bedrijven-client bijvoorbeeld toegang moet hebben tot een Exchange-server om agendagegevens namens een gebruiker op te halen, wordt hiervoor de Active Directory Authentication Library (ADAL) gebruikt. ADAL is een codebibliotheek die is ontworpen om beveiligde resources in uw adreslijst beschikbaar te maken voor clienttoepassingen met behulp van OAuth-beveiligingstokens. ADAL werkt samen met OAuth om claims te verifiëren en tokens om te wisselen (in plaats van wachtwoorden) om een gebruiker toegang tot een bron te verlenen. In het verleden was de autoriteit in een transactie zoals deze , de server die weet hoe gebruikersclaims kunnen worden gevalideerd en de benodigde tokens moet geven, mogelijk een on-premises beveiligingstokenservice of zelfs Active Directory Federation Services. Moderne verificatie centraliseert deze autoriteit echter met behulp van Azure AD.

Dit betekent ook dat hoewel uw Exchange-server en Skype voor Bedrijven-omgevingen zich volledig on-premises kunnen houden, de bevoegde server online is en uw on-premises omgeving de mogelijkheid moet hebben om een verbinding te maken met uw Office 365-abonnement in de cloud (en het Azure AD-exemplaar dat in uw abonnement als adreslijst wordt gebruikt).

Wat verandert er niet? Of u nu een hybride gesplitst domein gebruikt of de on-premises Skype voor Bedrijven- en Exchange-server gebruikt, alle gebruikers moeten eerst *on-premises verifiëren.* In een hybride implementatie van moderne verificatie wijzen _Lyncdiscovery_ en _Automatisch_ zoeken beide naar de on-premises server.

> [!IMPORTANT]
> Als u de specifieke toologieën van Skype voor Bedrijven wilt kennen die worden ondersteund met MA, vindt u hier [een document.](https://technet.microsoft.com/library/mt803262.aspx)

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>De moderne verificatiestatus van uw on-premises omgeving controleren
<a name="BKMK_CheckStatus"> </a>

Omdat moderne verificatie verandert de autorisatieserver die wordt gebruikt bij services die gebruikmaken van OAuth/S2S, moet u weten of moderne verificatie is in- of uitgeschakeld voor uw on-premises Skype voor Bedrijven- en Exchange-omgevingen. U kunt de status op uw Exchange-servers controleren met de volgende PowerShell-opdracht:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Als de waarde van de _eigenschap OAuth2ClientProfileEnabled_ **Onwaar** is, wordt moderne verificatie uitgeschakeld.

Zie [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)Get-OrganizationConfig meer informatie over de nieuwe cmdlet.

U kunt uw Skype voor Bedrijven-servers controleren door de volgende PowerShell-opdracht uit te voeren:

```powershell
Get-CSOAuthConfiguration
```

Als de opdracht een lege _OAuthServers-eigenschap_ retourneert of als de waarde van de eigenschap _ClientADALAuthOverride_ niet is toegestaan, wordt moderne verificatie uitgeschakeld.

Zie [Get-CsOAuthConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csoauthconfiguration)Get-CsOAuthConfiguration meer informatie over de nieuwe cmdlet.

## <a name="do-you-meet-modern-authentication-prerequisites"></a>Voldoet u aan de vereisten voor moderne verificatie?

Controleer en vink deze items af in uw lijst voordat u doorgaat:

- **Skype voor Bedrijven specifiek**
  - Alle servers moeten een cumulatieve update (CU5) van mei 2017 voor Skype voor Bedrijven Server 2015 of hoger hebben
    - **Exception** : Het Apparaat van de Afdeling Van Baarheid (SBA) kan worden gebruikt in de huidige versie (op basis van Lync 2013)
  - Uw SIP-domein wordt toegevoegd als een federatief domein in Office 365
  - Alle front-ends voor SFB moeten verbindingen hebben die uitgaand zijn naar internet, naar URL's voor Office 365-verificatie (TCP 443) en crLs voor bekende certificaatwortels (TCP 80) in rijen 56 en 125 van de sectie 'Microsoft 365 Common en Office' van [OFFICE 365-URL's](urls-and-ip-address-ranges.md)en IP-adresbereiken.

- **Skype voor Bedrijven on-premises in een hybride Office 365-omgeving**
  - Een skype voor Bedrijven Server 2019-implementatie met alle servers waarop Skype voor Bedrijven Server 2019 wordt uitgevoerd.
  - Een skype voor Bedrijven Server 2015-implementatie met alle servers waarop Skype voor Bedrijven Server 2015 wordt uitgevoerd.
  - Een implementatie met maximaal twee verschillende serverversies, zoals hieronder vermeld:
    - Skype for Business Server 2015
    - Skype for Business Server 2019
  - Alle Skype voor Bedrijven-servers moeten de nieuwste cumulatieve updates hebben geïnstalleerd. Zie Skype voor Bedrijven [Server-updates](https://docs.microsoft.com/skypeforbusiness/sfb-server-updates) om alle beschikbare updates te zoeken en te beheren.
  - Lync Server 2010 of 2013 maakt geen gebruik van de hybride omgeving.

>[!NOTE]
>Als uw front-endservers van Skype voor Bedrijven een proxyserver voor internettoegang gebruiken, moeten voor elke front-end het IP-adres van de proxyserver en het gebruikte poortnummer worden ingevoerd in de configuratiesectie van het web.config-bestand.

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
> Abonneer u op de RSS-feed voor [OFFICE 365-URL's](urls-and-ip-address-ranges.md) en IP-adresbereiken om op de hoogte te blijven van de meest recente vermeldingen van vereiste URL's.

- **Exchange Server-specifiek**
  - U gebruikt Exchange Server 2013 CU19 en hoger, Exchange Server 2016 CU8 en hoger of Exchange Server 2019 CU1 en hoger.
  - De omgeving heeft geen Exchange Server 2010.
  - SSL Offloaden is niet geconfigureerd. SSL-beëindiging en herversleuteling worden ondersteund.
  - Als uw omgeving gebruikmaakt van een proxyserverinfrastructuur zodat servers verbinding kunnen maken met internet, moet u ervoor zorgen dat op alle Exchange-servers de proxyserver is gedefinieerd in de eigenschap [InternetWebProxy.](https://technet.microsoft.com/library/bb123716%28v=exchg.160%29.aspx)

- **Exchange Server on-premises in een hybride Office 365-omgeving**

  - Als u Exchange Server 2013 gebruikt, moeten ten minste één server de serverrollen Postvak en Client Access hebben geïnstalleerd. Hoewel het mogelijk is om de rollen Postvak en Client Access op afzonderlijke servers te installeren, raden we u ten zeerste aan om beide rollen op dezelfde server te installeren voor extra betrouwbaarheid en verbeterde prestaties.
  - Als u Exchange Server 2016 of hoger gebruikt, moet op ten minste één server de serverrol Postvak zijn geïnstalleerd.
  - De hybride omgeving heeft geen Exchange Server 2007 of 2010.
  - Alle Exchange-servers moeten de meest recente cumulatieve updates hebben geïnstalleerd. Zie [Exchange upgraden](https://docs.microsoft.com/exchange/plan-and-deploy/install-cumulative-updates) naar de meest recente cumulatieve updates om alle beschikbare updates te zoeken en te beheren.

- **Vereisten voor Exchange-client en -protocol**

    De beschikbaarheid van moderne verificatie wordt bepaald door de combinatie van de client, het protocol en de configuratie. Als moderne verificatie niet wordt ondersteund door de client, het protocol en/of de configuratie, blijft de client gebruikmaken van verouderde verificatie.
  
    De volgende clients en protocollen ondersteunen moderne verificatie met on-premises Exchange wanneer moderne verificatie is ingeschakeld in de omgeving:

  |**Klanten**|**Primary Protocol**|**Opmerkingen**|
  |:-----|:-----|:-----|
  |Outlook 2013 en hoger  <br/> |MAPI via HTTP  <br/> |MAPI via HTTP moet zijn ingeschakeld in Exchange om gebruik te kunnen maken van moderne verificatie bij deze clients (meestal ingeschakeld of Waar voor nieuwe installaties van Exchange 2013 Service Pack 1 en hoger) zie Hoe moderne verificatie werkt [voor Office 2013- en Office 2016-clientapps](modern-auth-for-office-2013-and-2016.md)voor meer informatie.  <br/> Controleer of u de minimaal vereiste build van Outlook hebt. bekijk [de meest recente updates voor versies van Outlook die gebruikmaken van Windows Installer (MSI).](https://docs.microsoft.com/officeupdates/outlook-updates-msi)  <br/> |
  |Outlook 2016 voor Mac en hoger  <br/> |Exchange-webservices  <br/> |  <br/> |
  |Outlook voor iOS en Android  <br/> | Microsoft-synchronisatietechnologie <br/> |Zie [Hybride moderne verificatie gebruiken met Outlook voor iOS en Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) voor meer informatie.  <br/> |
  |Exchange ActiveSync-clients (bijvoorbeeld iOS11 Mail)  <br/> |Exchange ActiveSync  <br/> |Voor Exchange ActiveSync-clients die moderne verificatie ondersteunen, moet u het profiel opnieuw maken om te kunnen overschakelen van basisverificatie naar moderne verificatie.  <br/> |

    Clients en/of protocollen die niet in de lijst staan (zoals POP3), ondersteunen geen moderne verificatie met on-premises Exchange en blijven gebruikmaken van verouderde verificatiemechanismen, zelfs nadat moderne verificatie is ingeschakeld in de omgeving.

- **Algemene vereisten**
  - Resource forest scenarios will require a two-way trust with the account forest to ensure proper SID lookups are performed during hybrid modern authentication requests. 
  - Als u AD FS gebruikt, hebt u Windows 2012 R2 AD FS 3.0 en hoger nodig voor federatie.
  - Uw identiteitsconfiguraties zijn alle typen die worden ondersteund door Azure AD Connect, zoals wachtwoordhashsynchronisatie, Pass Through-verificatie en on-premises STS die worden ondersteund door Office 365.
  - Azure AD Connect is geconfigureerd en werkt voor gebruikersreplicatie en synchronisatie.
  - U hebt geverifieerd dat hybride versie is geconfigureerd met de klassieke Exchange-topologiemodus tussen uw on-premises omgeving en office 365-omgeving. Officiële ondersteuningsverklaring voor Exchange Hybrid geeft aan dat u de huidige CU of de huidige CU - 1 moet hebben.
    > [!NOTE]
    > Hybride moderne verificatie wordt niet ondersteund met de [hybride agent.](https://docs.microsoft.com/exchange/hybrid-deployment/hybrid-agent)

  - Zorg ervoor dat zowel een on-premises testgebruiker als een hybride testgebruiker in Office 365 zich kan aanmelden bij de Skype voor Bedrijven-desktopclient (als u moderne verificatie wilt gebruiken met Skype) en Microsoft Outlook (als u moderne verificatie wilt gebruiken met Exchange).

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>Wat moet ik nog meer weten voordat ik begin?
<a name="BKMK_Whatelse"> </a>

- Voor alle scenario's voor on-premises servers is het nodig moderne verificatie on-premises in te stellen (in feite voor Skype voor Bedrijven is er een lijst met ondersteunde toologieën), zodat de server die verantwoordelijk is voor verificatie en autorisatie zich in de Microsoft Cloud (de beveiligings tokenservice van Azure AD, genaamd 'gebruiktSTS') en Azure AD bijwerkt over de URL's of naamruimten die worden gebruikt door uw on-premises installatie van Skype voor Bedrijven of Exchange. Daarom nemen on-premises servers een Microsoft Cloud-afhankelijkheid over. Het nemen van deze actie kan worden beschouwd als het configureren van 'hybrid auth'.
- Dit artikel bevat koppelingen naar anderen die u helpen bij het kiezen van ondersteunde moderne verificatie toologieën (alleen nodig voor Skype voor Bedrijven) en artikelen met een overzicht van de instellingsstappen of stappen voor het uitschakelen van moderne verificatie voor On-premises Exchange en Skype voor Bedrijven on-premises. Favorieten toevoegen aan deze pagina in uw browser als u een thuisbasis nodig hebt voor het gebruik van moderne verificatie in uw serveromgeving.

## <a name="related-topics"></a>Verwante onderwerpen
<a name="BKMK_URLListforMA"> </a>

- [Exchange Server on-premises configureren voor gebruik van moderne verificatie](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Ondersteunde toologieën van Skype voor Bedrijven met moderne verificatie](https://technet.microsoft.com/library/mt803262.aspx)
- [Skype voor Bedrijven on-premises configureren voor gebruik van moderne verificatie](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Hybride moderne verificatie verwijderen uit of uitschakelen uit Skype voor Bedrijven en Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
