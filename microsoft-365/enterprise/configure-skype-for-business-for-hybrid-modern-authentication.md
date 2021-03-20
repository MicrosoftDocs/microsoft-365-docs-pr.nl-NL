---
title: Skype voor Bedrijven on-premises configureren voor het gebruik van hybride moderne verificatie
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
description: Lees hoe u Skype voor Bedrijven on-premises configureert voor het gebruik van HMA (Hybrid Modern Authentication), met veiligere gebruikersverificatie en autorisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3177bafb6eff27053dca61ec576666cae4a97bb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911148"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Skype voor Bedrijven on-premises configureren voor het gebruik van hybride moderne verificatie

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Moderne verificatie is een methode voor identiteitsbeheer die veiligere gebruikersverificatie en -autorisatie biedt, beschikbaar is voor de on-premises server van Skype voor Bedrijven- en Exchange-server on-premises en hybride skype voor Bedrijven-gesplitste domeinen.
  
 **Belangrijk** Wilt u meer weten over moderne verificatie (MA) en waarom u deze misschien liever gebruikt in uw bedrijf of organisatie? Controleer [dit document](hybrid-modern-auth-overview.md) voor een overzicht. Als u wilt weten wat Skype voor Bedrijven-toologieën worden ondersteund met MA, wordt dat hier beschreven.
  
 **Voordat we beginnen,** gebruik ik de volgende termen:
  
- Moderne verificatie (MA)

- Hybride moderne verificatie (HMA)

- Exchange on-premises (EXCH)

- Exchange Online (EXO)

- Skype voor Bedrijven on-premises (SFB)

- Skype voor Bedrijven Online (SFBO)

Als een afbeelding in dit artikel een object bevat dat grijs of grijs is,  betekent dit dat het element dat in grijs wordt weergegeven, niet is opgenomen in ma-specifieke configuratie.
  
## <a name="read-the-summary"></a>De samenvatting lezen

In deze samenvatting wordt het proces in stappen op een gegeven moment in de loop van de uitvoering samengevat en is het goed voor een algemene controlelijst om bij te houden waar u zich in het proces kunt vinden.
  
1. Zorg er eerst voor dat u aan alle vereisten voldoet.

1. Aangezien veel vereisten gebruikelijk zijn voor zowel Skype voor Bedrijven als Exchange, bekijkt u het **overzichtsartikel** [voor uw controlelijst vooraf.](hybrid-modern-auth-overview.md) Doe dit  *voordat*  u een van de stappen in dit artikel start.

1. Verzamel de HMA-specifieke gegevens die u nodig hebt in een bestand of OneNote.

1. Moderne verificatie voor EXO inschakelen (als deze nog niet is ingeschakeld).

1. Moderne verificatie voor SFBO inschakelen (als deze nog niet is ingeschakeld).

1. Schakel on-premises hybride moderne verificatie voor Exchange in.

1. Schakel on-premises hybride moderne verificatie voor Skype voor Bedrijven in.

Met deze stappen worden MA voor SFB, SFBO, EXCH en EXO in gebruik genomen, dat wil zeggen alle producten die kunnen deelnemen aan een HMA-configuratie van SFB en SFBO (inclusief afhankelijkheden van EXCH/EXO). Met andere woorden: als uw gebruikers zijn thuisgekomen in of postvakken hebben gemaakt in een deel van de Hybride (EXO + SFBO, EXO + SFB, EXCH + SFBO of EXCH + SFB), ziet uw eindproduct er als volgende uit:
  
![Een HMA-topologie van Mixed 6 Skype voor Bedrijven heeft MA op alle vier mogelijke locaties.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
Zoals u kunt zien zijn er vier verschillende locaties om MA in te zetten! Voor de beste gebruikerservaring raden we u aan ma in te zetten op alle vier deze locaties. Als u ma niet op al deze locaties kunt in- of uitstellen, past u de stappen aan zodat u MA alleen in de locaties in kunt zetten die nodig zijn voor uw omgeving.
  
Zie het [onderwerp Ondersteuning voor Skype voor Bedrijven met MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) voor ondersteunde excuses.
  
 **Belangrijk** Controleer of u aan alle vereisten hebt voldaan voordat u begint. U vindt deze informatie in hybride [moderne verificatieoverzicht en vereisten.](hybrid-modern-auth-overview.md)
  
## <a name="collect-all-hma-specific-info-youll-need"></a>Alle HMA-specifieke gegevens verzamelen die u nodig hebt

Nadat u hebt gecontroleerd of u [](hybrid-modern-auth-overview.md) voldoet aan de vereisten voor het gebruik van moderne verificatie (zie de opmerking hierboven), moet u een bestand maken om de gegevens vast te houden die u nodig hebt voor het configureren van HMA in de volgende stappen. Voorbeelden die in dit artikel worden gebruikt:
  
- **SIP/SMTP-domein**

  - Ex. contoso.com (is federatief met Office 365)

- **Tenant-id**

  - De GUID die uw Office 365-tenant vertegenwoordigt (bij het aanmelden van contoso.onmicrosoft.com).

- **URL's voor SFB 2015 CU5-webservice**

u hebt url's voor interne en externe webservice nodig voor alle SfB 2015-pools die zijn geïmplementeerd. Voer het volgende uit vanuit Skype voor Bedrijven Management Shell om deze te verkrijgen:
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Ex. Intern: https://lyncwebint01.contoso.com

- Ex. Extern: https://lyncwebext01.contoso.com

Als u een Standard Edition-server gebruikt, is de interne URL leeg. Gebruik in dit geval de poolfqdn voor de interne URL.
  
## <a name="turn-on-modern-authentication-for-exo"></a>Moderne verificatie voor EXO inschakelen

Volg de instructies hier: [Exchange Online: Uw tenant](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx) inschakelen voor moderne verificatie.
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>Moderne verificatie voor SFBO inschakelen

Volg de instructies hier: [Skype voor Bedrijven Online: Uw tenant inschakelen voor moderne verificatie.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Hybride moderne verificatie voor Exchange on-premises inschakelen

Volg de instructies hier: [Exchange Server on-premises](configure-exchange-server-for-hybrid-modern-authentication.md)configureren voor het gebruik van hybride moderne verificatie.
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Hybride moderne verificatie voor Skype voor Bedrijven on-premises inschakelen

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>On-premises webservice-URL's toevoegen als SPN's in Azure Active Directory

Nu moet u opdrachten uitvoeren om de URL's (eerder verzameld) toe te voegen als Service principals in SFBO.
  
 **Opmerking** Service principal names (SPN's) identificeren webservices en koppelen deze aan een beveiligingsprincipaal (zoals een accountnaam of groep), zodat de service kan optreden namens een geautoriseerde gebruiker. Clients die worden authentiek gemaakt op een server, maken gebruik van informatie die is opgenomen in SPN's.
  
1. Maak eerst verbinding met Azure Active Directory (Azure AD) met [deze instructies.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2. Voer deze opdracht on-premises uit om een lijst met URL's voor SFB-webservice te krijgen.

   Houd er rekening mee dat de AppPrincipalId begint met `00000004` . Dit komt overeen met Skype voor Bedrijven Online.

   Noteer (en schermafbeelding voor latere vergelijking) de uitvoer van deze opdracht, die een SE- en WS-URL bevat, maar meestal bestaat uit SPN's die beginnen met `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Als de interne of **externe** SFB-URL's van on-premises ontbreken (bijvoorbeeld, en we moeten deze specifieke https://lyncwebint01.contoso.com records toevoegen aan deze https://lyncwebext01.contoso.com) lijst.

    Zorg ervoor dat u  *de onderstaande voorbeeld-URL's* vervangt door uw werkelijke URL's in de opdrachten Toevoegen!
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. Controleer of uw nieuwe records zijn toegevoegd door de **opdracht Get-MsolServicePrincipal** uit stap 2 opnieuw uit te voeren en door de uitvoer te kijken. Vergelijk de lijst of schermafbeelding van vóór met de nieuwe lijst met SPN's. U kunt ook schermafbeeldingen maken van de nieuwe lijst voor uw records. Als u succes hebt gehad, ziet u de twee nieuwe URL's in de lijst. Als u naar ons voorbeeld gaat, bevat de lijst met SPN's nu de specifieke URL's https://lyncwebint01.contoso.com en https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Het Object Auth Server van EvoSTS maken

Voer de volgende opdracht uit in de Skype voor Bedrijven Management Shell.
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Hybride moderne verificatie inschakelen

Dit is de stap die ma daadwerkelijk in schakelt. Alle vorige stappen kunnen van tevoren worden uitgevoerd zonder de clientverificatiestroom te wijzigen. Wanneer u klaar bent om de verificatiestroom te wijzigen, kunt u deze opdracht uitvoeren in de Skype voor Bedrijven Management Shell.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Controleren

Wanneer u HMA hebt ingeschakeld, wordt de nieuwe auth-stroom gebruikt voor de volgende aanmelding van een klant. Houd er rekening mee dat u met het in-/uitschakelen van HMA geen herauthenticatie voor een client kunt activeren. De clients reauthenticate op basis van de levensduur van de auth tokens en/of certs die ze hebben.
  
Als u wilt testen of HMA werkt nadat u deze hebt ingeschakeld, meldt u zich af bij een test-SFB Windows-client en klikt u op 'Mijn referenties verwijderen'. Meld u opnieuw aan. De client moet nu de stroom Moderne Auth gebruiken en uw aanmelding bevat nu een **Office 365-prompt** voor een 'Werk- of schoolaccount', gezien vlak voordat de client contact op neemt met de server en u aanmeldt.
  
U moet ook de 'Configuratiegegevens' voor Skype voor Bedrijven-clients controleren op een 'OAuth Authority'. Als u dit wilt doen op uw clientcomputer, houdt u Ctrl ingedrukt terwijl u met de rechtermuisknop klikt op het pictogram Skype voor Bedrijven in het Windows-systeemvak. Klik **op Configuratiegegevens** in het menu dat wordt weergegeven. Zoek in het venster Configuratiegegevens van Skype voor Bedrijven dat op het bureaublad wordt weergegeven naar het volgende:
  
![In de configuratiegegevens van een Skype voor Bedrijven-client met moderne verificatie wordt de URL van lync en EWS OAUTH Authority van https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
U moet ook de Ctrl-toets ingedrukt houden terwijl u met de rechtermuisknop op het pictogram voor de Outlook-client klikt (ook in het windows-systeemvak) en klikt u op 'Verbindingsstatus'. Zoek naar het SMTP-adres van de klant ten opzichte van een AuthN-type 'Bearer', dat het token van de token voor de toler vertegenwoordigt dat \* in OAuth wordt gebruikt.
  
## <a name="related-articles"></a>Verwante artikelen

[Terugkoppeling naar het overzicht moderne verificatie](hybrid-modern-auth-overview.md).
  
Wilt u weten hoe u moderne verificatie (ADAL) kunt gebruiken voor uw Skype voor Bedrijven-clients? We hebben stappen [hier.](./hybrid-modern-auth-overview.md)