---
title: On-premises Exchange Server configureren voor het gebruik van hybride moderne verificatie
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
description: Meer informatie over het configureren Exchange Server on-premises voor het gebruik van HMA (Hybrid Modern Authentication), met veiligere gebruikersverificatie en autorisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d30d1b2b14efd66d973e9bf6d45b970d7af681bc
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841628"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>On-premises Exchange Server configureren voor het gebruik van hybride moderne verificatie

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

HMA (Hybrid Modern Authentication) is een methode voor identiteitsbeheer die veiligere gebruikersverificatie en autorisatie biedt en beschikbaar is voor on-premises Exchange-server.

## <a name="fyi"></a>TER INFORMATIE

Voordat we beginnen, bel ik:

- Hybride moderne verificatie \> HMA

- Exchange on-premises \> EXCH

- \>Exchange Online EXO

Als een afbeelding in dit artikel een object bevat dat 'grijs'of 'grijs' is, betekent dit dat het element dat in grijs wordt weergegeven, niet is opgenomen *in HMA-specifieke configuratie.*

## <a name="enabling-hybrid-modern-authentication"></a>Hybride moderne verificatie inschakelen

HMA in- of uitschakelen betekent:

1. Zorg ervoor dat u aan de prereqs voldoet voordat u begint.

1. Aangezien veel **vereisten** gebruikelijk zijn voor zowel Skype voor Bedrijven als Exchange, zijn hybride moderne verificatieoverzicht en vereisten voor het gebruik ervan met [on-premises Skype voor Bedrijven](hybrid-modern-auth-overview.md)en Exchange servers. Doe dit voordat u een van de stappen in dit artikel start.

1. On-premises webservice-URL's toevoegen als **SPN's (Service Principal Names)** in Azure AD. Als EXCH hybride is met meerdere **tenants,** moeten deze on-premises webservice-URL's worden toegevoegd als SPN's in de Azure AD van alle tenants die hybride zijn met EXCH.

1. Ervoor zorgen dat alle virtuele directories zijn ingeschakeld voor HMA

1. Controleren op het object Auth Server van EvoSTS

1. HMA inschakelen in EXCH.

> [!NOTE]
> Ondersteunt uw versie van Office ma? Zie [Hoe moderne verificatie werkt voor Office 2013 en Office 2016-client-apps.](modern-auth-for-office-2013-and-2016.md)


## <a name="make-sure-you-meet-all-the-prerequisites"></a>Zorg ervoor dat u aan alle vereisten voldoet

Aangezien veel vereisten gebruikelijk zijn voor zowel Skype voor Bedrijven als Exchange, controleert u het overzicht van hybride moderne verificatie en vereisten voor het gebruik ervan met [on-premises Skype voor Bedrijven](hybrid-modern-auth-overview.md)en Exchange servers. Doe dit  *voordat*  u een van de stappen in dit artikel start.

> [!NOTE]
> Outlook Web App en Exchange configuratiescherm werkt niet met hybride moderne verificatie.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>On-premises webservice-URL's toevoegen als SPN's in Azure AD

Voer de opdrachten uit die uw on-premises webservice-URL's toewijzen als Azure AD SPN's. SPN's worden gebruikt door clientapparaten en apparaten tijdens verificatie en autorisatie. Alle URL's die kunnen worden gebruikt om verbinding te maken van on-premises naar Azure Active Directory (Azure AD) moeten zijn geregistreerd in Azure AD (dit omvat zowel interne als externe naamruimten).

Verzamel eerst alle URL's die u in AAD moet toevoegen. Voer deze opdrachten on-premises uit:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

Zorg ervoor dat de URL's waar verbinding mee kan worden gemaakt, worden weergegeven als HTTPS-service principal names in AAD. Als EXCH hybride is met meerdere **tenants,** moeten deze HTTPS-SPN's worden toegevoegd in de AAD van alle tenants in hybride versie van EXCH.

1. Maak eerst verbinding met AAD met [deze instructies.](connect-to-microsoft-365-powershell.md)

    > [!NOTE]
    > U moet de optie _Verbinding maken-MsolService_ op deze pagina gebruiken om de onderstaande opdracht te kunnen gebruiken.

2. Voor uw Exchange-gerelateerde URL's typt u de volgende opdracht:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Noteer (en schermafbeelding voor latere vergelijking) de uitvoer van deze opdracht, die een https://  *autodiscover.yourdomain.com*  en https://  *mail.yourdomain.com-URL* moet bevatten, maar meestal bestaat uit SPN's die beginnen met 00000002-0000-0ff1-ce00-0000000000/. Als er https:// url's van uw on-premises url's ontbreken, moeten we deze specifieke records toevoegen aan deze lijst.

3. Als u uw interne en externe MAPI/HTTP-, EWS-, ActiveSync-, OAB- en Autodiscover-records niet ziet in deze lijst, moet u deze toevoegen met de onderstaande opdracht (het voorbeeld-URL's zijn ' ' en ' ', maar u vervangt de voorbeeld-URL's door uw `mail.corp.contoso.com` `owa.contoso.com` **eigen** URL's):

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Controleer of de nieuwe records zijn toegevoegd door de opdracht Get-MsolServicePrincipal stap 2 opnieuw uit te voeren en door de uitvoer te kijken. Vergelijk de lijst /schermafbeelding van vóór met de nieuwe lijst met SPN's. Mogelijk maakt u ook een schermafbeelding van de nieuwe lijst voor uw records. Als u succes hebt gehad, ziet u de twee nieuwe URL's in de lijst. Als u naar ons voorbeeld gaat, bevat de lijst met SPN's nu de specifieke URL's  `https://mail.corp.contoso.com`  en  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Controleren of virtuele adresgegevens correct zijn geconfigureerd

Controleer nu of OAuth correct is ingeschakeld in Exchange op alle virtuele Outlook door de volgende opdrachten uit te voeren:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Controleer de uitvoer om te controleren of **OAuth** is ingeschakeld op elk van deze VDirs, het ziet er zo uit (en het belangrijkste wat u moet bekijken is 'OAuth'):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Als OAuth ontbreekt op een server en een van de vier virtuele directories, moet u deze toevoegen met behulp van de relevante opdrachten voordat u verdergaat ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)en [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Bevestig dat het Object Auth Server van EvoSTS aanwezig is

Ga terug naar de on-premises Exchange Management Shell voor deze laatste opdracht. U kunt nu valideren dat uw on-premises vermelding een vermelding heeft voor de provider van de verificatieprovider van evoSTS:

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

De uitvoer moet een AuthServer van de naam EvoSts laten zien en de status 'Ingeschakeld' moet Waar zijn. Als u dit niet ziet, moet u de meest recente versie van de wizard Hybride configuratie downloaden en uitvoeren.

> [!NOTE]
> Als EXCH hybride is met meerdere **tenants,** moet in de uitvoer één AuthServer van de naam EvoSts worden getoond : {GUID} voor elke tenant in hybride versie met EXCH en moet de status 'Ingeschakeld' Waar zijn voor al deze AuthServer-objecten.

 **Belangrijk** Als u een Exchange 2010 in uw omgeving gebruikt, wordt de Provider voor Verificatie van EvoSTS niet gemaakt.

## <a name="enable-hma"></a>HMA inschakelen

Voer de volgende opdracht uit in de Exchange Management Shell, on-premises:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

Als de EXCH-versie Exchange 2016 (CU18 of hoger) of Exchange 2019 (CU7 of hoger) is en hybride is geconfigureerd met HCW die is gedownload na september 2020, voer dan de volgende opdracht uit in de Exchange Management Shell, on-premises:

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> Als EXCH hybride is met meerdere **tenants,** zijn er meerdere AuthServer-objecten aanwezig in EXCH met domeinen die overeenkomen met elke tenant.  De **vlag IsDefaultAuthorizationEndpoint** moet zijn ingesteld op waar (met de **cmdlet IsDefaultAuthorizationEndpoint)** voor een van deze AuthServer-objecten. Deze vlag kan niet worden ingesteld op waar voor alle Authserver-objecten en HMA is zelfs ingeschakeld als een van de **isDefaultAuthorizationEndpoint-vlag** van een van deze AuthServer-objecten is ingesteld op waar.

## <a name="verify"></a>Controleren

Wanneer u HMA hebt ingeschakeld, wordt de nieuwe auth-stroom gebruikt voor de volgende aanmelding van een klant. Houd er rekening mee dat u met het in-/uitschakelen van HMA geen herauthenticatie voor een client kunt activeren. De clients reauthenticate op basis van de levensduur van de auth tokens en/of certs die ze hebben.

U moet ook de Ctrl-toets ingedrukt houden terwijl u met de rechtermuisknop op het pictogram voor de Outlook-client (ook in het Windows-systeemvak) klikt en klikt u op 'Verbindingsstatus'. Zoek naar het SMTP-adres van de klant tegen het type 'Authn' van 'Bearer', dat het token voor de toler vertegenwoordigt dat \* in OAuth wordt gebruikt.

> [!NOTE]
> Wilt u Skype voor Bedrijven met HMA configureren? U hebt twee artikelen nodig: een met ondersteunde [toologieën](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)en een waarin u kunt zien hoe u [de configuratie kunt doen.](configure-skype-for-business-for-hybrid-modern-authentication.md)


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Hybride moderne verificatie gebruiken met Outlook voor iOS en Android

Als u een on-premises klant bent met Exchange server op TCP 443, kunt u de verwerking van verkeer voor de volgende IP-adresbereiken omzeilen:

```text
52.125.128.0/20
52.127.96.0/23
```

De Outlook-app voor iOS en Android is ontworpen als de beste manier om Microsoft 365 of Office 365 op uw mobiele apparaat te ervaren met behulp van Microsoft-services om uw dagelijkse leven en werk te vinden, plannen en prioriteit te geven. Zie Hybride moderne verificatie gebruiken met Outlook [voor iOS en Android voor meer informatie.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

## <a name="related-topics"></a>Verwante onderwerpen

[Moderne verificatieconfiguratievereisten voor de overgang van Office 365 dedicated/ITAR naar vNext](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
