---
title: De on-premises implementatie van Exchange server configureren voor gebruik van hybride moderne verificatie
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lees meer over het configureren van een on-premises Exchange-Server voor hybride implementatie van gebruikers, met een uitgebreide verificatie van gebruikers en autorisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 291c7c220fb4ee56db2a42409d5b81724de5da32
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688913"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>De on-premises implementatie van Exchange server configureren voor gebruik van hybride moderne verificatie

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Hybrid modern Authentication (HMA) is een methode van identiteitsbeheer die veiliger en autorisatie van gebruikers biedt en beschikbaar is voor Exchange Server on-premises hybride implementaties.
  
## <a name="fyi"></a>TER informatie

Voordat we beginnen, bel ik het volgende:
  
- Hybrid modern Authentication \> HMA

- Exchange on \> -premises uitwisseling

- Exchange Online \> Exo

Ook *als een afbeelding in dit artikel een object heeft dat niet beschikbaar is (grijs) of lichter gekleurd, betekent dit dat het element dat grijs wordt weergegeven, niet is opgenomen in de HMA-specifieke configuratie* .
  
## <a name="enabling-hybrid-modern-authentication"></a>Hybride authenticatie inschakelen

Als u het HMA wilt uitschakelen, doet u dit:
  
1. Zorg ervoor dat u voldoet aan de prereqs voordat u begint.

1. Aangezien veel voor **waarden** van toepassing zijn op Skype voor bedrijven en Exchange, de [hybride verificatie-overzicht van de hybride versie en vereisten voor het gebruik van on-premises Skype voor bedrijven en Exchange-servers](hybrid-modern-auth-overview.md). Ga verder voordat u de stappen in dit artikel begint.

1. On-premises Url's voor webservice toevoegen als **spn's (Service Principal Names)** in azure AD.

1. Ervoor zorgen dat alle virtuele mappen worden ingeschakeld voor HMA

1. Controleren op het EvoSTS auth Server-object

1. Enable HMA in wisselkoers.

 **Opmerking** Biedt uw versie van Office ondersteuning voor MA? Zie [hoe moderne verificatie werkt voor office 2013-en office 2016-clienttoepassingen](modern-auth-for-office-2013-and-2016.md).
  
## <a name="make-sure-you-meet-all-the-prerequisites"></a>Zorg dat u aan alle vereisten voldoet.

Aangezien veel voorwaarden voor Skype voor bedrijven en Exchange voor u gelden, moet [u het overzicht van hybride verificatie en vereisten voor het gebruik van on-premises Skype voor bedrijven en Exchange-servers](hybrid-modern-auth-overview.md)raadplegen. Ga verder  *voordat*  u de stappen in dit artikel begint.
  
## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>On-premises webservice-Url's toevoegen als Spn's in azure AD

Voer de opdrachten uit waarop u de on-premises Url's voor de web-service aanwijst als Azure AD-Spn's. Spn's worden door clients en apparaten van de client gebruikt tijdens verificatie en autorisatie. Alle Url's die kunnen worden gebruikt voor het maken van verbinding tussen locaties en Azure Active Directory (Azure AD), moeten worden geregistreerd in azure AD (dit geldt ook voor interne en externe naamruimten).
  
Verzamel eerst alle Url's die u wilt toevoegen in AAD. Voer deze opdrachten on-premises uit:
  
```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```
    
Zorg ervoor dat de Url's clients kunnen verbinding maken met behulp van HTTPS-service-principal-namen in AAD.
  
1. Maak eerst verbinding met AAD met [deze instructies](connect-to-microsoft-365-powershell.md).

 **Opmerking** U moet de optie _verbinding-MsolService_ van deze pagina gebruiken om de onderstaande opdracht te kunnen gebruiken.

2. Voor de verwante Url's voor Exchange typt u de volgende opdracht:

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
```

Let op (en schermafbeelding voor een latere vergelijking) de uitvoer van deze opdracht, die een https://  *Autodiscover.yourdomain.com*  en https://  *mail.yourdomain.com* -URL moet bevatten, maar meestal bestaat uit spn's die beginnen met 00000002-0000-0ff1-CE00-000000000000/. Als er https://-Url's zijn van uw on-premises die ontbreken, moeten ze deze specifieke records toevoegen aan deze lijst.
  
3. Als u uw interne en externe MAPI-, EWS-, ActiveSync-, OAB-en Autodiscover-records niet in deze lijst ziet, moet u deze toevoegen met behulp van de volgende opdracht (de voorbeeld Url's zijn ' `mail.corp.contoso.com` ' en ' `owa.contoso.com` ', maar **vervangt u de url's met uw eigen** url's wel. <br/>
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
$x.ServicePrincipalnames.Add("https://owa.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. Controleer of de nieuwe records zijn toegevoegd door de opdracht Get-MsolServicePrincipal uit stap 2 opnieuw uit te voeren en de uitvoer te bekijken. Vergelijk de lijst/schermafbeelding van vóór de nieuwe lijst met Spn's (u kunt ook een schermafbeelding van de nieuwe lijst voor uw records weergeven). Als u slaagt, worden de twee nieuwe Url's in de lijst weergegeven. In ons voorbeeld, de lijst met Spn's bevat nu de specifieke Url's  `https://mail.corp.contoso.com`  en  `https://owa.contoso.com` . 
  
## <a name="verify-virtual-directories-are-properly-configured"></a>Controleren of virtuele mappen correct zijn geconfigureerd

Op deze manier controleert u of OAuth correct is ingeschakeld in Exchange voor alle virtuele mappen die in Outlook kunnen worden gebruikt door de volgende opdrachten uit te voeren:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth* 
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Controleer de uitvoer om er voor elk van deze VDirs in te schakelen, wat er ongeveer zo uitziet (en de naam van het bestand dat u **wilt controleren is** ' OAuth '):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```
  
Als er geen OAuth-server en een van de vier virtuele mappen ontbreken, moet u deze toevoegen aan de hand van de betreffende opdrachten voordat u verdergaat ([set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps)en [set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).
  
## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Bevestig dat het object van de EvoSTS Authentication server aanwezig is

Keer terug naar de on-premises Exchange Management Shell voor deze laatste opdracht. U kunt nu controleren of uw on-premises een vermelding heeft voor de evoSTS-verificatieprovider:
  
```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

Voor de uitvoer moet een AuthServer worden weergegeven van de naam EvoSts en moet de ' ingeschakelde ' status waar zijn. Als u dit niet ziet, dient u de meest recente versie van de wizard hybride configuratie te downloaden en uit te voeren.
  
 **Belangrijk** Als u Exchange 2010 gebruikt in uw omgeving, wordt de EvoSTS-verificatieprovider niet gemaakt. 
  
## <a name="enable-hma"></a>HMA inschakelen

Voer de volgende opdracht uit in de Exchange-beheer shell, on-premises:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true  
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Verifiëren

Wanneer u HMA hebt ingeschakeld, wordt de nieuwe verificatie stroom gebruikt door de volgende aanmelding van een client. Als u geen gebruik maakt van HMA, wordt een nieuwe verificatie niet geactiveerd voor elke client. De client verifieert opnieuw op basis van de levensduur van de auth-tokens en/of-certificaten.
  
Houd de CTRL-toets ook ingedrukt terwijl u met de rechtermuisknop op het pictogram van de Outlook-client klikt (ook in het systeemvak van Windows) en klik op verbindings status. Let op het SMTP-adres van de client tegen een ' auth '-type ' Bearer \* ', dat staat voor het dragertoken dat in OAuth wordt gebruikt.
  
 **Opmerking** Wilt u Skype voor bedrijven configureren met HMA? U hebt twee artikelen nodig: een die de [ondersteunde topologieën](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)bevat, en een ervan waarin u ziet [hoe u de configuratie kunt uitvoeren](configure-skype-for-business-for-hybrid-modern-authentication.md).
 
## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Hybride moderne verificatie gebruiken met Outlook voor iOS en Android

Als u een on-premises klant bent met Exchange Server op TCP 443, moet u de volgende IP-bereiken whitelist:  <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR>

## <a name="related-topics"></a>Verwante onderwerpen

[Configuratievereisten voor moderne verificatie voor overgang van Office 365 dedicated/ITAR naar vNext ontgrendelen](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)