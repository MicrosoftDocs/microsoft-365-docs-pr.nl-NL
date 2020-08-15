---
title: Skype voor bedrijven on-premises configureren voor gebruik van hybride moderne verificatie
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Meer informatie over hoe u Skype voor bedrijven on-premises kunt configureren voor gebruik van de Hybrid modern Authentication (HMA), met een veiligere verificatie van gebruikers en autorisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695008"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Skype voor bedrijven on-premises configureren voor gebruik van hybride moderne verificatie

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Moderne verificatie is een methode van identiteitsbeheer die veiliger en autorisatie van gebruikers biedt, is beschikbaar voor Skype voor bedrijven server on-premises en Exchange Server on-premises en gesplitste domein Skype voor bedrijven-hybriden.
  
 **Belangrijk** Wilt u meer weten over moderne verificatie (MA) en waarom u liever deze wilt gebruiken in uw bedrijf of organisatie? Bekijk [dit document](hybrid-modern-auth-overview.md) voor een overzicht. Als u wilt weten wat de topologie van Skype voor bedrijven met MA moet ondersteunen, wordt deze hier beschreven.
  
 **Voordat we beginnen**, gebruik ik deze voorwaarden:
  
- Moderne verificatie (MA)

- Hybrid modern Authentication (HMA)

- Exchange on-premises (uitwisseling)

- Exchange Online (EXO)

- Skype voor bedrijven on-premises (SFB)

- Skype voor bedrijven online (SFBO)

Ook als een afbeelding in dit artikel een object heeft dat grijs wordt weergegeven of grijs wordt weergegeven, betekent dit dat het element grijs wordt weergegeven en **niet** is opgenomen in de configuratie voor ma-specifiek.
  
## <a name="read-the-summary"></a>Lees het overzicht

In deze samenvatting wordt het proces in stappen opgesplitst en is dit geschikt voor een algemene controlelijst die u kunt bijhouden waar u zich bevindt.
  
1. Zorg er eerst voor dat u aan alle vereisten voldoet.

1. Aangezien veel voor **waarden** voor Skype voor bedrijven en Exchange voor u gelden, [raadpleegt u het artikeloverzicht voor de controlelijst voorafgaand aan de vereisten](hybrid-modern-auth-overview.md). Ga verder  *voordat*  u de stappen in dit artikel begint.

1. Verzamel de HMA-specifieke informatie die u nodig hebt in een bestand of OneNote.

1. Moderne verificatie voor EXO inschakelen (als dit nog niet is ingeschakeld).

1. Moderne verificatie voor SFBO inschakelen (als dit nog niet is ingeschakeld).

1. Hybride moderne verificatie inschakelen voor Exchange on-premises.

1. Schakel hybride moderne verificatie in voor Skype voor bedrijven on-premises.

Met deze stappen wordt de MA voor SFB, SFBO, wisselkoers, en EXO, dat wil zeggen alle producten die kunnen deelnemen aan een HMA-configuratie van SFB en SFBO (inclusief afhankelijkheden voor wissel/EXO). Met andere woorden, als uw gebruikers zijn aangemeld/postvakken hebben gemaakt in een deel van de Hybrid (EXO + SFBO, EXO + SFB, SFBO + SFB of +), ziet uw voltooide product er zo uit:
  
![Een gemengde 6 Skype voor bedrijven HMA-topologie biedt op alle vier mogelijke locaties op de i](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
Zoals u ziet, zijn er vier verschillende locaties waarmee u MA kunt inschakelen. Voor de beste ervaring raden we u aan om MA in te schakelen op alle vier deze locaties. Als u op al deze locaties de optie MA niet kunt inschakelen, moet u de stappen aanpassen, zodat u MA alleen kunt inschakelen op de locaties die nodig zijn voor uw omgeving.
  
Zie het [onderwerp voor ondersteuning voor Skype voor bedrijven met ma](https://technet.microsoft.com/library/mt803262.aspx) voor ondersteunde topologieën.
  
 **Belangrijk** Controleer nog eens of u aan de vereisten voldoet voordat u begint. U vindt deze informatie in de [hybride overzicht van de hybride verificatie en de vereisten](hybrid-modern-auth-overview.md).
  
## <a name="collect-all-hma-specific-info-youll-need"></a>Verzamel alle HMA-specifieke informatie die u nodig hebt

Nadat u hebt gecontroleerd of u beschikt over de [vereisten](hybrid-modern-auth-overview.md) voor moderne verificatie (Zie de opmerking hierboven), moet u een bestand maken voor de informatie die u nodig hebt voor het configureren van HMA in de stappen voor het eerst. Voorbeelden in dit artikel:
  
- **SIP/SMTP-domein**

  - ". contoso.com (is federatief met Office 365)

- **Tenant-ID**

  - De GUID waarmee uw Office 365-Tenant wordt aangeduid (bij aanmelding van contoso.onmicrosoft.com).

- **SFB 2015 CU5 hoger vereist webservice-Url's**

voor alle SfB 2015 groepen is een interne en externe webservice-URL nodig. Voer de volgende stappen uit in de beheer shell van Skype voor bedrijven om deze te verkrijgen:
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- ". Binnenlandse https://lyncwebint01.contoso.com

- ". External https://lyncwebext01.contoso.com

Als u een Standard Edition-server gebruikt, is de interne URL leeg. Gebruik in dit geval de FQDN-naam van de groep voor de interne URL.
  
## <a name="turn-on-modern-authentication-for-exo"></a>Moderne verificatie voor EXO inschakelen

Volg de instructies hier: [Exchange Online: de Tenant inschakelen voor moderne verificatie.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>Moderne verificatie voor SFBO inschakelen

Volg de instructies hier: [Skype voor bedrijven online: uw Tenant inschakelen voor moderne verificatie](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Hybride moderne verificatie inschakelen voor Exchange on-premises

Volg de instructies hier: [informatie over het configureren van Exchange Server on-premises voor hybride moderne verificatie](configure-exchange-server-for-hybrid-modern-authentication.md).
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Hybride moderne verificatie inschakelen voor Skype voor bedrijven on-premises

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>On-premises webservice-Url's toevoegen als Spn's in azure Active Directory

U moet nu opdrachten uitvoeren om de Url's (eerder verzameld) toe te voegen als service-principals in SFBO.
  
 **Opmerking** Met Spn's (Service Principal Names) identificeert u webservices en koppelt u deze aan een beveiligingsprincipal (zoals een accountnaam of groep), zodat de service namens een gemachtigde gebruiker kan handelen. Clientverificatie op een server gebruikt informatie die zich bevindt in Spn's.
  
1. Maak eerst verbinding met Azure Active Directory (Azure AD) met [de volgende instructies](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Voer deze opdracht, on-premises, uit om een lijst te zien met SFB-Url's voor de web-service.

   Houd er rekening mee dat het Appprincipalid die begint met `00000004` . Dit komt overeen met Skype voor bedrijven online.

   Notitie maken van (en schermafbeelding voor later vergelijken) de uitvoer van deze opdracht, die een SE en een WS-URL omvat, maar meestal bestaan uit Spn's die beginnen met `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Als de interne **of** externe SFB-url's van on-premises ontbreken (bijvoorbeeld https://lyncwebint01.contoso.com en https://lyncwebext01.contoso.com) we moeten deze specifieke records toevoegen aan deze lijst.

    Vervang  *de onderstaande voorbeeld url's* door uw werkelijke url's in de opdrachten toevoegen.
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. Controleer of de nieuwe records zijn toegevoegd door de opdracht **Get-MsolServicePrincipal** uit stap 2 opnieuw uit te voeren en de uitvoer te bekijken. Vergelijk de lijst of schermafbeelding van vóór de nieuwe lijst met Spn's. U kunt ook een schermafbeelding van de nieuwe lijst voor uw records weergeven. Als u gelukte, ziet u de twee nieuwe Url's in de lijst. In ons voorbeeld, de lijst met Spn's bevat nu de specifieke Url's https://lyncwebint01.contoso.com en https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Maak het EvoSTS auth Server-object

Voer de volgende opdracht uit in de Skype voor bedrijven-beheer shell.
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Hybride moderne verificatie inschakelen

Dit is de stap waarmee u in het MA MA schakelt. U kunt alle vorige stappen vóór de tijd uitvoeren zonder de clientverificatie stroom te wijzigen. Wanneer u klaar bent om de verificatie stroom te wijzigen, voert u deze opdracht uit in de Skype voor bedrijven-beheer shell.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Verifiëren

Wanneer u HMA hebt ingeschakeld, wordt de nieuwe verificatie stroom gebruikt door de volgende aanmelding van een client. Wanneer u een HMA inschakelt, wordt de herauthenticatie voor geen enkele client geactiveerd. De client verifieert op basis van de levensduur van de auth-tokens en/of certificeringen.
  
Als u wilt testen of het HMA werkt nadat u dit hebt ingeschakeld, meldt u zich af bij een Windows-client voor test SFB en klikt u op ' mijn referenties verwijderen '. Meld u opnieuw aan. De client dient nu de moderne verificatie stroom te gebruiken, en de aanmelding bevat nu een **Office 365** -prompt voor een werk-of schoolaccount, weergegeven, rechts voordat de client contact maakt met de server en u zich aanmeldt.
  
U dient ook de ' configuratiegegevens ' voor Skype voor bedrijven-clients te controleren voor een ' OAuth-autoriteit '. Houd de CTRL-toets ingedrukt en klik met de rechtermuisknop op het pictogram van Skype voor bedrijven in het systeemvak van Windows om dit te doen op de clientcomputer. In het menu dat wordt weergegeven, klikt u op **configuratiegegevens** . In het venster ' Skype voor bedrijven Configuration Information ', dat wordt weergegeven op het bureaublad, raadpleegt u het volgende:
  
![De configuratiegegevens van een Skype voor bedrijven-client die gebruikmaken van moderne verificatie tonen een URL van Lync en EWS OAUTH-autoriteit https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
Houd de CTRL-toets ook ingedrukt terwijl u met de rechtermuisknop op het pictogram van de Outlook-client klikt (ook in het systeemvak van Windows) en klik op verbindings status. Zoek het SMTP-adres van de client tegen een authentication type van ' Bearer \* ', dat staat voor het dragertoken dat wordt gebruikt in OAuth.
  
## <a name="related-articles"></a>Verwante artikelen

[Koppeling terug naar het moderne verificatie overzicht](hybrid-modern-auth-overview.md).
  
Wilt u meer weten over het gebruik van moderne verificatie (ADAL) voor uw Skype voor bedrijven-clients? We hebben [hier](https://technet.microsoft.com/library/mt710548.aspx)stappen.
