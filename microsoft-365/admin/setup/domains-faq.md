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
description: Meer informatie over domeinen vindt u in antwoorden op uw veelgestelde vragen.
ms.openlocfilehash: bb949dbd4e32bb62f10dfd0323df70697fdc5404
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804194"
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
- [Hoe kan ik het standaarddomein instellen of wijzigen in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Hoe kan ik een domein van Microsoft 365 overbrengen naar een andere host?]
- [Waarom heb ik een domein met de naam onmicrosoft.com?](#why-do-i-have-an-onmicrosoftcom-domain)
- [Waarom heb ik een onmicrosoft.de-domein?](#why-do-i-have-an-onmicrosoftde-domain)
- [Hoe controleer ik de status van een non-profit of onderwijs?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>Wat is MX-prioriteit?

E-mail wordt bezorgd bij de Mail Exchange-server met het laagste voorkeursgetal (hoogste prioriteit), dus de MX-record die u gebruikt om e-mail te routeren, moet het laagste voorkeursgetal hebben, gewoonlijk 0 of met prioriteit  *Hoog*  . 
  
- Voor de meeste DNS-hostingproviders geldt dat u bij het maken van een MX-record het voorkeursgetal moet instellen.
    
- Sommigen geven het vak het label  *voorkeur*  , anderen het label  *prioriteit*  . 
    
- Sommigen vereisen een getal, anderen vragen u  *Laag*  ,  *Gemiddeld*  of  *Hoog*  te selecteren. 
    
- Als u slechts één MX-record hebt, kunt u een willekeurige waarde voor prioriteit of voorkeur gebruiken.
    
- Als u er meerdere hebt, dan moet u ervoor zorgen dat de MX-record voor e-mailroutering een hogere prioriteit heeft dan de record die wordt gebruikt om te valideren dat het domein van u is.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Hoe kan ik SPF-records voor mijn domein valideren?

Het is belangrijk dat u  **maar één TXT-record voor SPF**hebt gemaakt. Als u al een SPF-record hebt, moet u de nieuwe Microsoft 365-waarden toevoegen aan de record, en niet een nieuwe maken. Wanneer u de SPF-record voor Microsoft-e-mail hebt toegevoegd of bijgewerkt, controleert u of de syntaxis in een van de volgende hulpprogramma's correct is: 
  
- [Hulpprogramma's voor het testen van SPF-records](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig webinterface](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>Wat is een domeinnaam?

Een domein is een unieke naam die na het **@** -teken wordt weergegeven in een e-mailadres en na **www.** in een webadres. Meestal bestaat deze uit de naam van uw organisatie en een standaard-internetachtervoegsel, zoals  *uwbedrijf.com*  of  *universiteit.edu*  . 
  
Met behulp van een aangepast domein zoals '**rob \@ contoso.com**' met Microsoft 365 kunt u geloofwaardigheid en herkenning voor uw merk opbouwen. 
  
U kunt [een domein kopen in Microsoft 365 en we stellen dit automatisch in](../get-help-with-domains/buy-a-domain-name.md)of u kunt een domein kopen of ophalen dat u al hebt gekocht bij een domeinregistratie.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?

Als u uw eigen DNS-records beheert en uw DNS-host geen ondersteuning biedt voor alle DNS-records die in Microsoft 365 zijn vereist, werken sommige functies van Microsoft 365 niet. U wordt aangeraden uw domein over te zetten naar een registrar die ondersteuning biedt voor alle vereiste DNS-records.
  
Providers die ondersteuning bieden voor alle vereiste DNS-records:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Hoe kan ik het standaarddomein instellen of wijzigen in Microsoft 365?

U moet minimaal één aangepast domein aan Microsoft 365 hebben toegevoegd voordat u een standaarddomein kunt kiezen.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
2. Selecteer op de pagina **Domains** het domein dat u als standaard wilt instellen voor nieuwe e-mailadressen. 
    
3. Selecteer **Als standaard instellen**.
    
::: moniker range="o365-worldwide"

U kunt de naam van uw initiële  *.onmicrosoft.com*  -domein niet wijzigen. 

::: moniker-end

::: moniker range="o365-germany"

U kunt de naam van uw initiële  *. ononmicrosoft.de*  -domein niet wijzigen. 

::: moniker-end

::: moniker range="o365-21vianet"

U kunt de naam van uw initiële  *. onpartner.onmschina.cn*  -domein niet wijzigen. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Microsoft 365?

::: moniker range="o365-worldwide"

Ja. Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van de registratieserver. Als u Microsoft uw DNS-instellingen met NS-records wilt laten beheren, of als u het domein van Microsoft hebt gekocht, kunt u geen subdomeinen toevoegen.

::: moniker-end

::: moniker range="o365-germany"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van de registratieserver. Als u Microsoft uw DNS-instellingen met NS-records wilt laten beheren, of als u het domein van Microsoft hebt gekocht, kunt u geen subdomeinen toevoegen.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van de registratieserver. Als u 21Vianet uw DNS-instellingen met NS-records beheert, kunt u geen subdomeinen toevoegen.

::: moniker-end

Meestal kunt u maximaal 900 domeinen toevoegen aan uw Microsoft 365-abonnement.
  
U kunt bijvoorbeeld de domeinen contoso.com en contosomarketing.com toevoegen, en vervolgens de subdomeinen www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com enzovoort.
  
Wanneer u een subdomein toevoegt, wordt dit automatisch gecontroleerd op basis van het bovenliggende domein dat wordt geverifieerd.
  
Als u meerdere domeinen toevoegt aan Microsoft 365, kunt u alle services (zoals e-mail) hosten in elk van de domeinen die u hebt toegevoegd.  *Wanneer u uw e-mailadres wijzigt in Microsoft 365, worden alle e-mailberichten die naar het domein worden verzonden, doorgestuurd naar Microsoft 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Als u een contoso.com-domein hebt toegevoegd aan een Microsoft 365-abonnement, kunt u ook de subdomein-xyz.contoso.com toevoegen aan een andere Microsoft 365-organisatie. Wanneer u het subdomein toevoegt, wordt u gevraagd een TXT-record toe te voegen aan de DNS-hosting provider.

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>Hoe kan ik een domein van Microsoft 365 overbrengen naar een andere host?

Zie [een domein van Microsoft overbrengen naar een andere host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)voor de procedure voor het overdragen van een domein.

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>Testfase van Microsoft 365 uitvoeren vanaf mijn aangepaste domein

Voor de procedure voor het testen van de Microsoft 365-e-mail functionaliteit van een aangepast domein naar een Microsoft 365-postvak, raadpleegt u [Microsoft 365 van mijn aangepaste domein testen](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Waarom heb ik een domein met de naam onmicrosoft.com?

Microsoft 365 maakt een domein voor u, zoals *contoso.onmicrosoft.com*, wanneer u zich aanmeldt bij de service. De gebruikers-ID die u maakt wanneer u zich registreert, omvat het domein, bijvoorbeeld *Alan@contoso.onmicrosoft.com*. 
  
 **Als u uw e-mail wilt weergeven als *Alan \@ contoso.com*:** [Koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg de stappen in [uw gebruikers en domein toevoegen aan Microsoft 365](add-domain.md) als u het al bent. 
  
- **U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.** Als u tijdens het registreren bijvoorbeeld in eerste instantie fourthcoffee.onmicrosoft.com hebt gekozen, kunt u deze naam niet meer wijzigen in fabrikam.onmicrosoft.com. Als u een ander onmicrosoft.com-domein wilt gebruiken, moet u een nieuw abonnement beginnen met Microsoft 365. 
    
- **U kunt de URL van uw team site niet wijzigen.** De URL van uw team site is gebaseerd op de onmicrosoft.com-domeinnaam. Helaas kunt u de naam van de team site niet wijzigen vanwege de manier waarop SharePoint Online Architecture werkt. 
    
- **U kunt uw onmicrosoft-domein niet verwijderen.** Microsoft 365 moet aan de slag gaan, omdat dit wordt gebruikt achter de scènes voor uw abonnement. U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd. 
    
U kunt het onmicrosoft.com-domein blijven gebruiken, ook nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Waarom heb ik een onmicrosoft.de-domein?

Microsoft 365 maakt een domein voor u, zoals *contoso.onmicrosoft.de*, wanneer u zich aanmeldt bij de service. De gebruikers-ID die u maakt wanneer u zich registreert, omvat het domein, bijvoorbeeld *Alan@contoso.onmicrosoft.de*. 
  
 **Ga als volgt te werk als u uw e-mail wilt weergeven als *Alan@contoso.de*:** [het domein kopen](../get-help-with-domains/buy-a-domain-name.md) of voer de stappen uit in [uw gebruikers en domein toevoegen aan Microsoft 365](add-domain.md) als u de e-mail al hebt gekocht. 
  
- **U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.** Als het eerste domein dat u hebt gekozen bijvoorbeeld fourthcoffee.onmicrosoft.de, kunt u dit niet wijzigen in fabrikam.onmicrosoft.de. Als u een ander onmicrosoft.de-domein wilt gebruiken, moet u een nieuw abonnement beginnen met Microsoft 365. 
    
- **U kunt de URL van uw team site niet wijzigen.** De URL van uw team site is gebaseerd op de onmicrosoft.de-domeinnaam. Helaas kunt u de naam van de team site niet wijzigen vanwege de manier waarop SharePoint Online Architecture werkt. 
    
- **U kunt uw onmicrosoft-domein niet verwijderen.** Microsoft 365 moet aan de slag gaan, omdat dit wordt gebruikt achter de scènes voor uw abonnement. U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd. 
    
U kunt het initiële ononmicrosoft.de-domein blijven gebruiken, zelfs nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Hoe controleer ik de status van een non-profit of onderwijs?

1. Selecteer **Setup** in het [Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-home) om de wizard te starten. (Zorg ervoor dat u zich eerst aanmeldt bij Microsoft 365.) 
    
2. Als u de beheerder van uw school wilt worden, selecteert u de optie  **een beheerder worden** in microsoft 365. 
    
3. U wordt gevraagd om een TXT DNS-record toe te voegen op de website van de DNS-host voor uw domein. Waarom? Door u aan te melden bij de DNS-host en een record voor uw domein toe te voegen, meldt u Microsoft 365 dat u de eigenaar van de domeinnaam bent.
    
4. Nadat u de record hebt toegevoegd, gaat u terug naar de Microsoft 365-Portal en bevestigt u dat u deze hebt toegevoegd, zodat micro 365 Soft kan controleren.
    
Hebt u een non-profit organisatie en wilt u Microsoft 365 aanschaffen? [Zorg ervoor dat uw organisatie in aanmerking komt](https://www.microsoft.com/en-us/nonprofits/eligibility) en registreert voor de service. 
  
Wilt u meer weten over de beheerder voor uw school? [Meer informatie hierover](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).