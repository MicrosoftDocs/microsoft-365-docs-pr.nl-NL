---
title: Veelgestelde vragen over domeinen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Meer informatie over domeinen door antwoorden te vinden op uw veelgestelde vragen.
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068101"
---
# <a name="domains-faq"></a>Veelgestelde vragen over domeinen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Dit artikel bevat antwoorden op veelgestelde vragen over domeinen in Microsoft 365.

Als u geen antwoord op uw vraag kunt vinden, kunt u dit laten weten door een opmerking achter te laten. Deze wordt dan aan de lijst toegevoegd.

In dit artikel

- [Wat is MX-prioriteit?](#what-is-mx-priority)
- [Hoe kan ik SPF-records voor mijn domein valideren?](#how-can-i-validate-spf-records-for-my-domain)
- [Wat is een domeinnaam?](#what-is-a-domain-name)
- [Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [Hoe stel ik het standaarddomein in of wijzig ik deze in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Waarom heb ik een domein met de naam onmicrosoft.com?](#why-do-i-have-an-onmicrosoftcom-domain)
- [Waarom heb ik een 'onmicrosoft.de'-domein?](#why-do-i-have-an-onmicrosoftde-domain)
- [Hoe verifieer ik mijn status zonder winstoogoogs naar een opleiding?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>Wat is MX-prioriteit?

E-mail wordt bezorgd bij de Mail Exchange-server met het laagste voorkeursgetal (hoogste prioriteit), dus de MX-record die u gebruikt om e-mail te routeren, moet het laagste voorkeursgetal hebben, gewoonlijk 0 of met prioriteit  *Hoog*  . 
  
- Voor de meeste DNS-hostingproviders geldt dat u bij het maken van een MX-record het voorkeursgetal moet instellen.
    
- Sommigen geven het vak het label  *voorkeur*  , anderen het label  *prioriteit*  . 
    
- Sommigen vereisen een getal, anderen vragen u  *Laag*  ,  *Gemiddeld*  of  *Hoog*  te selecteren. 
    
- Als u slechts één MX-record hebt, kunt u een willekeurige waarde voor prioriteit of voorkeur gebruiken.
    
- Als u er meerdere hebt, dan moet u ervoor zorgen dat de MX-record voor e-mailroutering een hogere prioriteit heeft dan de record die wordt gebruikt om te valideren dat het domein van u is.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Hoe kan ik SPF-records voor mijn domein valideren?

Het is belangrijk dat u **slechts één TXT-record voor SPF hebt**of maakt. Als u al een SPF-record hebt, moet u de nieuwe Microsoft 365-waarden eraan toederen in plaats van er een nieuwe te maken. Nadat u uw SPF-record voor Microsoft-e-mail hebt toegevoegd of bijgewerkt, moet u controleren of de syntaxis correct is met een van de volgende hulpprogramma's: 
  
- [Hulpprogramma's voor het testen van SPF-records](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig webinterface](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>Wat is een domeinnaam?

Een domein is een unieke naam die na het **@** -teken wordt weergegeven in een e-mailadres en na **www.** in een webadres. Meestal bestaat deze uit de naam van uw organisatie en een standaard-internetachtervoegsel, zoals  *uwbedrijf.com*  of  *universiteit.edu*  . 
  
Het gebruik van een aangepast domein zoals "**rob \@ contoso.com**" met Microsoft 365 kan helpen bij het opbouwen van geloofwaardigheid en erkenning voor uw merk. 
  
U [een domein kopen in Microsoft 365 en we stellen het automatisch in,](../get-help-with-domains/buy-a-domain-name.md)of u er een kopen of meenemen die u al bezit van een domeinregistrar.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?

Als u uw eigen DNS-records beheert en uw DNS-host niet alle DNS-records ondersteunt die Microsoft 365 nodig heeft, werken sommige Microsoft 365-functies niet. U wordt aangeraden uw domein over te zetten naar een registrar die ondersteuning biedt voor alle vereiste DNS-records.
  
Providers die ondersteuning bieden voor alle vereiste DNS-records:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- Godaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Hoe stel ik het standaarddomein in of wijzig ik deze in Microsoft 365?

U moet ten minste één aangepast domein hebben dat u aan Microsoft 365 hebt toegevoegd voordat u een standaarddomein kiezen.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
2. Selecteer op de pagina **Domeinen** het domein dat u wilt instellen als standaard voor nieuwe e-mailadressen. 
    
3. Selecteer **Als standaard instellen**.
    
::: moniker range="o365-worldwide"

U kunt de naam van uw initiële  *.onmicrosoft.com*  -domein niet wijzigen. 

::: moniker-end

::: moniker range="o365-germany"

U de naam van uw oorspronkelijke *.onmicrosoft.de-domein* niet wijzigen. 

::: moniker-end

::: moniker range="o365-21vianet"

U de naam van uw oorspronkelijke *.partner.onmschina.cn-domein* niet wijzigen. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Microsoft 365?

::: moniker range="o365-worldwide"

Ja. Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein bij Microsoft hebt gekocht, u geen subdomeinen toevoegen.

::: moniker-end

::: moniker range="o365-germany"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein bij Microsoft hebt gekocht, u geen subdomeinen toevoegen.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u 21Vianet uw DNS-instellingen laat beheren met NS-records, u geen subdomeinen toevoegen.

::: moniker-end

Normaal gesproken u maximaal 900 domeinen toevoegen aan uw Microsoft 365-abonnement.
  
U kunt bijvoorbeeld de domeinen contoso.com en contosomarketing.com toevoegen, en vervolgens de subdomeinen www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com enzovoort.
  
Wanneer u een subdomein toevoegt, wordt deze automatisch geverifieerd op basis van het bovenliggende domein dat wordt geverifieerd.
  
Wanneer u meerdere domeinen toevoegt aan Microsoft 365, u een van de services (zoals e-mail) hosten op een van de domeinen die u hebt toegevoegd.  *Wanneer u uw e-mail wijzigt naar Microsoft 365, door de MX-record van een domein bij te werken, begint ALLE e-mail die naar dat domein wordt verzonden, naar Microsoft 365 te komen.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Als u een contoso.com domein hebt toegevoegd aan een Microsoft 365-abonnement, u het subdomein ook toevoegen xyz.contoso.com aan een andere Microsoft 365-organisatie. Wanneer u het subdomein toevoegt, wordt u gevraagd een TXT-record toe te voegen aan de DNS-hostingprovider.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Waarom heb ik een domein met de naam onmicrosoft.com?

Microsoft 365 maakt een domein voor u, zoals *contoso.onmicrosoft.com,* wanneer u zich aanmeldt bij de service. De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.com*. 
  
 **Als u uw e-mail eruit wilt laten zien als *alan \@ contoso.com:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Microsoft [365](add-domain.md) als u het al bezit. 
  
- **U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.** Als u tijdens het registreren bijvoorbeeld in eerste instantie fourthcoffee.onmicrosoft.com hebt gekozen, kunt u deze naam niet meer wijzigen in fabrikam.onmicrosoft.com. Als u een ander onmicrosoft.com domein wilt gebruiken, moet u een nieuw abonnement starten met Microsoft 365. 
    
- **U de naam van de URL van uw teamsite niet wijzigen.** De URL van uw teamsite is gebaseerd op uw onmicrosoft.com domeinnaam. Vanwege de manier waarop de SharePoint Online-architectuur werkt, u de naam van de teamsite helaas niet wijzigen. 
    
- **U kunt uw onmicrosoft-domein niet verwijderen.** Microsoft 365 moet het rond houden omdat het achter de schermen wordt gebruikt voor uw abonnement. U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd. 
    
U kunt het onmicrosoft.com-domein blijven gebruiken, ook nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Waarom heb ik een 'onmicrosoft.de'-domein?

Microsoft 365 maakt een domein voor u, zoals *contoso.onmicrosoft.de,* wanneer u zich aanmeldt bij de service. De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.de*. 
  
 **Als u uw e-mail eruit wilt laten zien als *alan@contoso.de:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Microsoft [365](add-domain.md) als u het al bezit. 
  
- **U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.** Als het oorspronkelijke domein dat u hebt gekozen bijvoorbeeld fourthcoffee.onmicrosoft.de, u het niet wijzigen om te worden fabrikam.onmicrosoft.de. Als u een ander onmicrosoft.de domein wilt gebruiken, moet u een nieuw abonnement starten met Microsoft 365. 
    
- **U de naam van de URL van uw teamsite niet wijzigen.** De URL van uw teamsite is gebaseerd op uw onmicrosoft.de domeinnaam. Vanwege de manier waarop de SharePoint Online-architectuur werkt, u de naam van de teamsite helaas niet wijzigen. 
    
- **U kunt uw onmicrosoft-domein niet verwijderen.** Microsoft 365 moet het rond houden omdat het achter de schermen wordt gebruikt voor uw abonnement. U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd. 
    
U de initiële onmicrosoft.de domein blijven gebruiken, zelfs nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Hoe verifieer ik mijn status zonder winstoogoogs naar een opleiding?

1. Selecteer **Setup** in het [beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-home) om de wizard te starten. (Meld u eerst aan bij Microsoft 365.) 
    
2. Als u beheerder van uw school wilt worden, selecteert u de optie **Een beheerder worden** in Microsoft 365. 
    
3. U wordt gevraagd om een TXT DNS-record toe te voegen op de DNS-hostwebsite voor uw domein. Waarom? Omdat u door u aan te melden bij de DNS-host en een record voor uw domein toe te voegen, aan Microsoft 365 bewijst dat u eigenaar bent van de domeinnaam.
    
4. Nadat u de record hebt toegevoegd, gaat u terug naar de Microsoft 365-portal en bevestigt u dat u deze hebt toegevoegd, zodat Microsoft 365 deze kan controleren.
    
Heb je een non-profitorganisatie en wil je Microsoft 365? [Zorg ervoor dat uw organisatie in aanmerking komt](https://www.microsoft.com/en-us/nonprofits/eligibility) en meld u vervolgens aan voor de service. 
  
Wilt u meer weten over het worden van de admin voor uw school? [Leer er alles over.](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)