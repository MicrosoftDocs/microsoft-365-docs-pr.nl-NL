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
description: Meer informatie over domeinen vindt u antwoorden op uw vragen in veelgestelde vragen.
ms.openlocfilehash: c82d5d01d64ad01f68d0c1ba73860511aa1718aa
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398904"
---
# <a name="domains-faq"></a>Veelgestelde vragen over domeinen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Dit artikel bevat antwoorden op veelgestelde vragen over domeinen in Office 365.

Als u geen antwoord op uw vraag kunt vinden, kunt u dit laten weten door een opmerking achter te laten. Deze wordt dan aan de lijst toegevoegd.
    
## <a name="what-is-mx-priority"></a>Wat is MX-prioriteit?

E-mail wordt bezorgd bij de Mail Exchange-server met het laagste voorkeursgetal (hoogste prioriteit), dus de MX-record die u gebruikt om e-mail te routeren, moet het laagste voorkeursgetal hebben, gewoonlijk 0 of met prioriteit  *Hoog*  . 
  
- Voor de meeste DNS-hostingproviders geldt dat u bij het maken van een MX-record het voorkeursgetal moet instellen.
    
- Sommigen geven het vak het label  *voorkeur*  , anderen het label  *prioriteit*  . 
    
- Sommigen vereisen een getal, anderen vragen u  *Laag*  ,  *Gemiddeld*  of  *Hoog*  te selecteren. 
    
- Als u slechts één MX-record hebt, kunt u een willekeurige waarde voor prioriteit of voorkeur gebruiken.
    
- Als u er meerdere hebt, dan moet u ervoor zorgen dat de MX-record voor e-mailroutering een hogere prioriteit heeft dan de record die wordt gebruikt om te valideren dat het domein van u is.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Hoe kan ik SPF-records voor mijn domein valideren?

Het is belangrijk dat u **slechts één TXT-record voor SPF**hebt of maakt. Als u al een SPF-record hebt, moet u de nieuwe Office 365-waarden eraan toevoegen in plaats van een nieuwe te maken. Nadat u uw SPF-record voor Microsoft-e-mail hebt toegevoegd of bijgewerkt, moet u controleren of de syntaxis correct is met een van deze hulpprogramma's: 
  
- [Hulpprogramma's voor het testen van SPF-records](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig webinterface](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Hoe worden mijn DNS-records door Office 365 beheerd?

Er zijn twee opties voor DNS-beheer met Office 365:
  
1. U wijzigt uw ns-records (nameserver) en vervolgens zorgt Microsoft voor alle servicespecifieke records, zoals het instellen van uw MX-record voor e-mail. **(Aanbevolen)**
    
2. U voegt DNS-records voor e-mail en andere Office 365-services bij uw DNS-host zelf toe. **(Alleen voor experts)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 maakt en host de DNS-records 
**Voordelen** 
- U hoeft niet bang te zijn om fouten te maken bij de waarden die u invoert voor de DNS-records voor Office 365-services.  
- U hebt meer flexibiliteit bij het kiezen van een domeinregistrar en DNS-host. 
- U kunt elke provider gebruiken waarbij u uw naamserverrecords kunt wijzigen, zelfs als de provider niet alle vereiste recordtypen ondersteunt.   
- Wanneer Office 365 nieuwe DNS-records toevoegt, hoeft u geen updates uit te voeren.  

#### <a name="disadvantages"></a>Nadelen 
- U kunt uw DNS-records niet wijzigen om e-mail buiten Office 365 te hosten. 
- Als u al een openbare website met uw domein gebruikt voor het adres, zoals www.fourthcoffee.com, moet u mensen vanuit Office 365 naar dat adres doorverwijzen. 
- Het instellen van omleiding vereist een statisch IP-adres, dat niet altijd gemakkelijk beschikbaar is voor openbare websites. - Als uw huidige domeinregistrar u niet toestaat om de naamserverrecords van uw domein te wijzigen, moet u overschakelen naar een andere registrar om deze DNS-beheeroptie te gebruiken.  

 ### <a name="you-manage-the-dns-records-yourself"></a>U beheert de DNS-records zelf 
 #### <a name="advantages"></a>Voordelen
- U beheert de DNS-records voor Office 365-services.   
- Als u een openbare website hebt met uw domein als het adres, zoals www.fourthcoffee.com, hoeft u geen omleiding te gebruiken om ervoor te zorgen dat mensen uw website nog kunnen bereiken nadat u uw domein hebt ingesteld in Office 365.    
- U hebt de flexibiliteit om e-mail ergens anders te hosten, bijvoorbeeld op een lokale Exchange-server.  
 
#### <a name="disadvantages"></a>Nadelen
U moet de DNS-records voor Office 365-services zelf instellen (tenzij u een GoDaddy-domein hebt). 
-  Als uw huidige DNS-host niet alle vereiste recordtypen voor Microsoft 365 ondersteunt, zijn sommige functies niet beschikbaar en moet u mogelijk overschakelen naar een andere DNS-host. 
- Als Office 365 vereisten voor DNS-records verandert of nieuwe services toevoegt, moet u de updates zelf uitvoeren bij uw DNS-host. 
   
## <a name="what-is-a-domain-name"></a>Wat is een domeinnaam?


Een domein is een unieke naam die na het **@** -teken wordt weergegeven in een e-mailadres en na **www.** in een webadres. Meestal bestaat deze uit de naam van uw organisatie en een standaard-internetachtervoegsel, zoals  *uwbedrijf.com*  of  *universiteit.edu*  . 
  
Het gebruik van een aangepast domein zoals "**rob \@ contoso.com**" met Office 365 kan helpen bij het opbouwen van geloofwaardigheid en erkenning voor uw merk. 
  
U kunt [een domein kopen in Office 365, waarna het automatisch wordt ingesteld](../get-help-with-domains/buy-a-domain-name.md). U kunt ook een domein kopen bij een domeinregistrar of een domein gebruiken dat u al hebt.
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>Kan ik een domein dat ik van Microsoft heb gekocht, overdragen aan een andere provider?

Ja, maar u een Office 365-domein pas 60 dagen nadat u het hebt gekocht met Office 365 overdragen naar een andere registrar.

Houd er rekening mee dat een *Whois-query* een door Office 365 gekochte domeinregistrar wordt weergegeven als Wild West Domains LLC. Er moet echter alleen contact worden opgenomen met Office 365 met betrekking tot uw office 365-domein.
  
Volg de stappen hieronder om de code op te halen op Office 365. Ga vervolgens naar de website van de andere domeinregistrar om het overzetten van uw domeinnaam naar die registrar in te stellen.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum **Settings** naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Instellingenlicenties.</a>

::: moniker-end
    
2. Selecteer **op** de pagina Domeinen het Office 365-domein dat u naar een andere domeinregistrar wilt overbrengen en selecteer **vervolgens**  >  **Domeinoverdracht inschakelen.**
       
4. Volg de stappen om het overzetten van uw domein voor te bereiden.
    
5. Als u de code hebt opgehaald, gaat u naar de website van de domeinregistrar waar u voortaan de domeinnaam wilt beheren en volgt u de aanwijzingen voor het overzetten van een domein (zoek op de website voor hulp).
    
6. Als u de code opnieuw wilt zien, selecteert u op de pagina **Domeininstellingen** in Office 365 de optie **Autorisatiecode voor domeinoverdracht weergeven.**
    
7. Nadat de overdracht is voltooid, verlengt u uw domein bij de nieuwe domeinregistrar.
    
8. Als u het proces wilt voltooien, gaat u terug naar de pagina **Domeinen van** het beheercentrum en selecteert u **Volledige domeinoverdracht**. 

*Opmerking: Houd er rekening mee dat office 365-gekochte domeinen niet in aanmerking komen voor wijzigingen in naamserver of het overdragen van het domein tussen Office 365-tenants.  Als een van deze vereist is, moet de domeinregistratie worden overgedragen aan een andere registrar.*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>Hoe kan ik wijzigen hoe mijn DNS-records in Office 365 worden beheerd?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>DNS-beheer overdragen aan een DNS-host buiten Office 365
   
1. Meld u aan bij de domeinregistrar voor uw domein.
    
2. Ga naar het gedeelte op de website van uw registrar waar u naamserverrecords kunt bijwerken en werk de naamservers bij zodat ze verwijzen naar de DNS-host voor uw domein. (De DNS-host is vaak de domeinregistrar.)
    
3. Volg een koppeling om naar de wizard domeinensetup te gaan:

::: moniker range="o365-worldwide"

4. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

4. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

4. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
5. Selecteer **op** de pagina Domeinen het domein dat u overschakelt en selecteer **DNS-beheer.**
    
6. Selecteer in de wizard Domeinen instellen op de pagina **Uw onlineservices instellen** de optie **Ik beheer mijn eigen DNS-records**en selecteer **Volgende**.
    
7. Voeg de DNS-records die door de wizard worden voorgesteld toe aan de pagina **DNS-instellingen bijwerken** aan de website van uw registrar. 
    
8. Nadat u de records hebt toegevoegd, gaat u terug naar Office 365 en selecteert **u Verifiëren**.
    

### <a name="change-dns-management-to-office-365"></a>DNS-beheer overdragen aan Office 365

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum **Settings** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen..</a>

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
2. Selecteer **op** de pagina Domeinen het domein dat u overschakelt en selecteer **DNS-beheer.**
    
3. Selecteer in de wizard Domeinen instellen op de pagina **Uw onlineservices instellen** de optie **Mijn onlineservices voor mij instellen. (Aanbevolen)** en selecteer **Volgende**.
    
4. Als u het domein nog niet hebt gecontroleerd, volg dan de stappen om dat eerst te doen.
    
5. Op de pagina **DNS-instellingen bijwerken** ziet u de naamservers voor Office 365. Ga naar de domeinregistrar voor uw domein en wijzig de naamservers in de Office 365-naamservers. 
    
4. Als u de naamservers hebt bijgewerkt, **wacht u minstens een uur**. Selecteer vervolgens terug in de wizard in Office 365 de optie **Verifiëren**.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?

Als u zelf uw DNS-records beheert en uw DNS-hosting geen ondersteuning biedt voor alle DNS-records die nodig zijn voor Office 365, werken sommige functies van Office 365 niet. U wordt aangeraden uw domein over te zetten naar een registrar die ondersteuning biedt voor alle vereiste DNS-records.
  
Providers die ondersteuning bieden voor alle vereiste DNS-records:
  
- Dynadot
    
- eNomCentraal
    
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
    
 **Als SRV-records niet worden ondersteund**, zijn de volgende functies van Office 365 niet beschikbaar: 
  
- Integratie van de chatfunctie van Skype voor Bedrijven Online en aanwezigheidsgegevens met Outlook Web App
    
- Externe communicatie (federatie) met gebruikers van Skype voor Bedrijven Online in andere organisaties.
    
- Openbare internetverbinding (Public Internet Connectivity (PIC)) met gebruikers van Skype voor Bedrijven Online die zijn aangemeld met een Microsoft-account (voorheen Windows Live ID).
    
 **Als meerdere CNAME-records niet worden ondersteund,** moet u kiezen tussen de volgende functies voor Skype voor Bedrijven Online: 
  
- E-maildesktopclients en mobiele clients kunnen Automatisch opsporen gebruiken om automatisch de Exchange Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.
    
- Desktopclients van Skype voor Bedrijven Online kunnen Automatisch opsporen gebruiken om automatisch de Skype voor Bedrijven Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.
    
- Mobiele clients van Skype voor Bedrijven Online kunnen Automatisch opsporen gebruiken om automatisch de Skype voor Bedrijven Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.

- Microsoft Teams federatie met Skype voor Bedrijven, zowel on-premises als online. Zie Het [netwerk van uw organisatie voorbereiden op Microsoft Teams voor](https://docs.microsoft.com/microsoftteams/prepare-network)meer informatie.
    
 **Als SPF/TXT-records niet worden ondersteund**, kunnen andere personen mogelijk uw domein gebruiken om spam of andere schadelijke e-mail te verzenden. Door SPF-records worden de servers geïdentificeerd die zijn geautoriseerd om e-mail vanaf uw domein te verzenden. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>Hoe stel of wijzig ik het standaarddomein in Office 365?

U moet minimaal één aangepast domein aan Office 365 hebben toegevoegd voordat u een standaarddomein kunt kiezen.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
2. Selecteer **op** de pagina Domeinen het domein dat u wilt instellen als standaardvoor nieuwe e-mailadressen. 
    
3. Selecteer **Als standaard instellen**.
    
::: moniker range="o365-worldwide"

U kunt de naam van uw initiële  *.onmicrosoft.com*  -domein niet wijzigen. 

::: moniker-end

::: moniker range="o365-germany"

U de naam van uw oorspronkelijke *.onmicrosoft.de* domein niet wijzigen. 

::: moniker-end

::: moniker range="o365-21vianet"

U de naam van uw initiële *.partner.onmschina.cn* domein niet wijzigen. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Office 365?

::: moniker range="o365-worldwide"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein van Microsoft hebt gekocht, u geen subdomeinen toevoegen.

::: moniker-end

::: moniker range="o365-germany"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein van Microsoft hebt gekocht, u geen subdomeinen toevoegen.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u 21Vianet uw DNS-instellingen laat beheren met NS-records, u geen subdomeinen toevoegen.

::: moniker-end

Doorgaans u maximaal 900 domeinen toevoegen aan uw Office 365-abonnement.
  
U kunt bijvoorbeeld de domeinen contoso.com en contosomarketing.com toevoegen, en vervolgens de subdomeinen www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com enzovoort.
  
Wanneer u een subdomein toevoegt, wordt dit automatisch geverifieerd op basis van het bovenliggende domein dat wordt geverifieerd.
  
Als u meerdere domeinen aan Office 365 toevoegt, kunt u alle services (zoals e-mail) in elk van die domeinen hosten.  *Wanneer u uw e-mailadres overzet naar Office 365 door de MX-record van uw domein bij te werken, komt alle e-mail die naar dat domein wordt verzonden, binnen in Office 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Als u al een contoso.com-domein aan een Office 365-tenant hebt toegevoegd, u ook de subdomeinxyz.contoso.com toevoegen aan een andere Office 365-tenant. Bij het toevoegen van het subdomein wordt u gevraagd om een TXT-record toe te voegen aan de DNS-hostingprovider.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Waarom heb ik een domein met de naam onmicrosoft.com?

Office 365 maakt een domein voor u, zoals *contoso.onmicrosoft.com*wanneer u zich aanmeldt bij de service. De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.com.* 
  
 **Als u uw e-mail wilt laten lijken op *alan \@ contoso.com:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Office [365](add-domain.md) als u het al bezit. 
  
- **U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.** Als u tijdens het registreren bijvoorbeeld in eerste instantie fourthcoffee.onmicrosoft.com hebt gekozen, kunt u deze naam niet meer wijzigen in fabrikam.onmicrosoft.com. Als u een ander onmicrosoft.com-domein wilt gebruiken, moet u een nieuw abonnement nemen op Office 365. 
    
- **U de naam van de URL van uw teamsite niet wijzigen.** De URL van uw teamsite is gebaseerd op uw onmicrosoft.com domeinnaam. Helaas u de naam van de teamsite niet wijzigen vanwege de manier waarop de SharePoint Online-architectuur werkt. 
    
- **U kunt uw onmicrosoft-domein niet verwijderen.** Dit domein wordt achter de schermen gebruikt voor uw abonnement. U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd. 
    
U kunt het onmicrosoft.com-domein blijven gebruiken, ook nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Waarom heb ik een domein 'onmicrosoft.de'?

Office 365 maakt een domein voor u, zoals *contoso.onmicrosoft.de*wanneer u zich aanmeldt bij de service. De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.de.* 
  
 **Als u uw e-mail wilt laten lijken *op alan@contoso.de:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Office [365](add-domain.md) als u het al bezit. 
  
- **U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.** Als het oorspronkelijke domein dat u hebt gekozen bijvoorbeeld fourthcoffee.onmicrosoft.de is, u het niet wijzigen om fabrikam.onmicrosoft.de te zijn. Als u een ander onmicrosoft.de-domein wilt gebruiken, moet u een nieuw abonnement starten met Office 365. 
    
- **U de naam van de URL van uw teamsite niet wijzigen.** De URL van uw teamsite is gebaseerd op uw onmicrosoft.de domeinnaam. Helaas u de naam van de teamsite niet wijzigen vanwege de manier waarop de SharePoint Online-architectuur werkt. 
    
- **U kunt uw onmicrosoft-domein niet verwijderen.** Dit domein wordt achter de schermen gebruikt voor uw abonnement. U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd. 
    
U het oorspronkelijke onmicrosoft.de domein blijven gebruiken, zelfs nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Hoe kan ik mijn non-profit- of onderwijsstatus verifiëren?

1. Selecteer **Instellen** in het [beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-home) om de wizard te starten. (Zorg ervoor dat u zich eerst aanmeldt bij Office 365.) 
    
2. Als u de beheerder voor uw school wilt worden, selecteert u de optie **Beheerder worden** in Office 365. 
    
3. U wordt gevraagd een TXT DNS-record toe te voegen op de DNS-hostwebsite voor uw domein. Waarom? Want door u aan te melden bij de DNS-host en een record voor uw domein toe te voegen, bewijst u aan Office 365 dat u eigenaar bent van de domeinnaam.
    
4. Nadat u de record hebt toegevoegd, gaat u terug naar de Office 365-portal en bevestigt u dat u deze hebt toegevoegd, zodat Office 365 deze kan controleren.
    
Heb je een non-profitorganisatie en wil je Office 365? [Zorg ervoor dat uw organisatie in aanmerking komt](https://www.microsoft.com/en-us/nonprofits/eligibility) en meld u dan aan voor de service. 
  
Wilt u meer weten over het worden van de beheerder voor uw school? [Meer informatie over het](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>Kan ik Office 365 besturen met slechts een paar e-mailadressen uit mijn aangepaste domein?

Dat kan, maar er zijn beperkingen:
  
- Uw huidige e-mailprovider moet e-mail doorsturen.
    
- U moet uw DNS-records met Office 365 beheren bij uw DNS-hostingprovider, in plaats van dat Office 365 deze records voor u beheert. Zie Uw domein toevoegen aan Office 365 wanneer u uw eigen DNS-records wilt beheren voor meer informatie over dit:
    
- Sommige Office 365-functies zijn niet beschikbaar:
- Gebruikers kunnen geen gratis/drukke informatie zien voor de gebruikers die zich op de andere e-mailprovider bevinden.
- Beheerders kunnen de accounts van iedereen niet vanaf één plek beheren.
- Gebruikers kunnen office 365-spamfiltering mogelijk niet gebruiken

### <a name="how-to-set-up-an-office-365-pilot"></a>Een Office 365-pilot instellen
    
1. Aanmelden bij het Microsoft 365-beheercentrum
    
    1. Meld u aan bij Office 365 met uw werk- of schoolaccount.
        
    2. Ga **Settings** naar \> **Instellingendomeinen**. 
    
2. Controleren of u eigenaar bent van het domein dat u wilt gebruiken
    
    1. Selecteer **op** de pagina Domeinen de optie **Domein toevoegen**. 
        
    2. Typ in het deelvenster het domein in dit voorbeeld cohowinery.com en selecteer **Volgende**. 
        
    3. Volg op de pagina **Domein verifiëren** de stapsgewijze instructies. 
        
    4. Selecteer in de vervolgkeuzelijst uw DNS-hostingprovider en volg de instructies om aan te geven dat u eigenaar bent van het domein.
        
    5. Selecteer **Verifiëren**. Het duurt enkele minuten tot 72 uur voordat DNS-wijzigingen van kracht worden. 
        
    6. Wanneer de verificatie is geslaagd, wordt u gevraagd uw DNS-records te wijzigen.
    
3. Het domein markeren als gedeeld in Exchange Online
    
    1. Ga naar het **Exchange-beheercentrum** (EAC). 
        
    2. Selecteer **geaccepteerde domeinen**in de sectie **E-mailstroom** . 
        
    3. Dubbelklik op het domein dat u wilt wijzigen.
        
    4. Selecteer **Intern relais**in het venster dat wordt geopend . 
        
    5. Kies **Opslaan**. Deze instelling kan enkele minuten nodig hebben om van kracht te worden. 
    
4. Deblokkering van de bestaande e-mailserver optioneel deblokkeren
    
    1. Office 365 gebruikt Exchange Online Protection (EOP) voor spambescherming. Als EOP detecteert een groot volume van spam wordt doorgestuurd door uw huidige mail server, kan het blokkeren, die zou voorkomen dat doorsturen werkt. Als u zeker bent van de spambeveiliging die uw andere e-mailprovider gebruikt, u hun server op de witte lijst plaatsen in Office 365. Hierdoor kunnen echter ook spam die via uw oorspronkelijke server binnenkomen, door naar de Office 365-postvakken komen en u niet beoordelen hoe goed Office 365 spam voorkomt.
    
    2. Ga naar Exchange admin center (EAC).
        
    3. Selecteer **in**EAC Beveiliging en selecteer **vervolgens het filter Verbinding**. 
        
    4. Selecteer in de **lijst IP-toestaan** **+** het IP-adres van de e-mailserver dat u ophalen van uw huidige e-mailprovider en voeg deze toe. 
    
5. Gebruikersaccounts maken en het primaire (antwoordadres) instellen
    
    1. Ga naar het Microsoft 365-beheercentrum.
        
    2. Selecteer op de linkernavigatiebalk de optie **Users** \> **Actieve gebruikers gebruikers**. 
        
    3. Maak de gebruikersaccounts.
        
    4. Selecteer voor elk account **+ (Nieuw)** en vul de vereiste informatie in. 
        
    5. Om de e-mail van de gebruiker hetzelfde te houden als nu, moet het veld **Gebruikersnaam** exact hetzelfde zijn als het bestaande e-mailadres van de gebruiker. 
        
    6. Selecteer naast Gebruikersnaam uw aangepaste domeinnaam in de vervolgkeuzelijst.
        
    7. Selecteer **Sluiten** \> **maken**. 
        
6. DNS-records bijwerken bij uw DNS-hostingprovider
    
    1. Meld u aan bij de website van uw DNS-hostingprovider en volg de [DNS-records maken bij elke DNS-hostingprovider voor Office 365-stappen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) **Maak de volgende uitzonderingen:**
    
        1. Maak geen nieuwe MX-record of wijzig uw bestaande MX-record niet.
            
        2. Als u al een SPF-record (Sender Policy Framework) hebt voor uw vorige e-mailprovider, voegt u in plaats van een nieuwe SPF-record (TXT) voor Exchange Online te maken, voeg u 'include:spf.protection.outlook.com' toe aan de huidige TXT-record. Bijvoorbeeld, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".
            
        3. Als u nog geen SPF-record hebt, wijzigt u de record die wordt aanbevolen door Office 365 om het domein voor uw huidige e-mailprovider op te nemen, plus spf.protection.outlook.com. Hiermee worden uitgaande berichten van beide e-mailsystemen geautoriseerd.
            
7. E-mail doorsturen instellen bij uw huidige provider
    
    1. Stel bij uw huidige e-mailprovider het doorsturen voor uw gebruikers-e-mailaccounts in naar uw onmicrosoft.com-domein:
        
    2. Het postvak van gebruiker A moet worden doorgestuurd naar usera@yourcompany.onmicrosoft.com
        
    3. Het postvak van gebruiker B moet doorsturen naar userb@yourcompany.onmicrosoft.com
        
    4. Wanneer u deze stap voltooit:
        
    5. Alle e-mail die naar usera@yourcompany.com en userb@yourcompany.com wordt verzonden, is beschikbaar in Office 365.
    
    6. Opmerkingen:
        
        - Neem contact op met uw huidige e-mailprovider voor de exacte stappen voor het instellen van doorstuur.
            
        - U hoeft geen kopie van berichten bij de huidige e-mailprovider te bewaren.
            
        - De meeste providers sturen e-mail door en laten het antwoordadres van de afzender intact, zodat de antwoorden naar de oorspronkelijke afzender gaan.
    
8. E-mailstroom testen
    
    1. Meld u aan bij Outlook Web App met de referenties van gebruiker A.
        
    2. Voer de volgende tests uit:
        
    3. Lokale Microsoft-e-mail testen. Stuur bijvoorbeeld een e-mail naar gebruiker B. Deze e-mail moet onmiddellijk worden bezorgd. In dit scenario wordt het bericht niet doorgestuurd naar het postvak van gebruiker B op uw oorspronkelijke server, omdat het postvak in Office 365 als lokaal wordt weergegeven.
        
    4. Test e-mail naar iemand die zich op het andere e-mailsysteem bevindt. Stuur bijvoorbeeld een e-mail naar gebruiker C. Deze e-mail moet worden bezorgd in het postvak van gebruiker C op uw oorspronkelijke e-mailserver.
        
    5. Controleer vanaf een extern account of van het e-mailaccount van een werknemer op het andere e-mailsysteem of het doorsturen correct is ingesteld op het andere e-mailsysteem. Stuur bijvoorbeeld vanuit het oorspronkelijke serveraccount van gebruiker C of een Hotmail-account gebruiker A een e-mail en controleer of deze in het Office 365-postvak van gebruiker A wordt aangeleverd.
        
9. Postvakinhoud verplaatsen
    
    1. Aangezien er slechts twee gebruikers te verplaatsen, en aangezien gebruiker A en gebruiker B zijn beide met behulp van Outlook al, de e-mail kan worden verplaatst door het openen van de oude . PST-bestand in het nieuwe Outlook-profiel en het kopiëren van de berichten, agenda-items, contactpersonen, enz. Eenmaal georganiseerd op de juiste locaties in het Office 365-postvak, kunnen de items allemaal worden geopend vanaf elk apparaat, overal.
        
    2. Wanneer er meer postvakken bij betrokken zijn of als de werknemers Outlook nog niet gebruiken, u de migratiehulpprogramma's gebruiken die beschikbaar zijn in het Exchange-beheercentrum. Ga om aan de slag naar het Exchange-beheercentrum en volg de aanwijzingen in E-mail migreren van een IMAP-server naar Exchange Online-postvakken.
    
