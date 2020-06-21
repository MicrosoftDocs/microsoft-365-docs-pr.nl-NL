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
description: Meer informatie over domeinen door antwoorden op uw vragen te vinden in VEELgestelde vragen.
ms.openlocfilehash: a52513130f9bbbf7c4cd25d4c4827e833700d992
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739152"
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

Het is belangrijk dat u **slechts één TXT-record voor SPF hebt**of maakt. Als u al een SPF-record hebt, moet u de nieuwe Office 365-waarden eraan toederen in plaats van er een nieuwe te maken. Nadat u uw SPF-record voor Microsoft-e-mail hebt toegevoegd of bijgewerkt, moet u controleren of de syntaxis correct is met een van de volgende hulpprogramma's: 
  
- [Hulpprogramma's voor het testen van SPF-records](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig webinterface](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Hoe worden mijn DNS-records door Office 365 beheerd?

Er zijn twee opties voor DNS-beheer met Office 365:
  
1. U wijzigt uw NS-records (nameserver) en vervolgens zorgt Microsoft voor alle servicespecifieke records, zoals het instellen van uw MX-record voor e-mail. **(Aanbevolen)**
    
2. U voegt DNS-records voor e-mail en andere Office 365-services bij uw DNS-host zelf toe. **(Alleen voor experts)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 maakt en host de DNS-records 
**Voordelen** 
- U hoeft niet bang te zijn om fouten te maken bij de waarden die u invoert voor de DNS-records voor Office 365-services.  
- U hebt meer flexibiliteit bij het kiezen van een domeinregistrar en DNS-host. 
- U kunt elke provider gebruiken waarbij u uw naamserverrecords kunt wijzigen, zelfs als de provider niet alle vereiste recordtypen ondersteunt.   
- Wanneer Office 365 nieuwe DNS-records toevoegt, hoeft u geen updates uit te voeren.  

#### <a name="disadvantages"></a>Nadelen 
- U kunt uw DNS-records niet wijzigen om e-mail buiten Office 365 te hosten. 
- Als u al een openbare website met uw domein gebruikt voor het adres, zoals www.fourthcoffee.com, moet u mensen vanaf Office 365 doorverwijzen naar dat adres. 
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


A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.* 
  
Het gebruik van een aangepast domein zoals "**rob \@ contoso.com**" met Office 365 kan helpen bij het opbouwen van geloofwaardigheid en erkenning voor uw merk. 
  
U kunt [een domein kopen in Office 365, waarna het automatisch wordt ingesteld](../get-help-with-domains/buy-a-domain-name.md). U kunt ook een domein kopen bij een domeinregistrar of een domein gebruiken dat u al hebt.
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>Kan ik een domein dat ik van Microsoft heb gekocht, overzetten naar een andere provider?

Ja, maar u een Office 365-domein pas 60 dagen nadat u het hebt gekocht met Office 365, overzetten naar een andere registrar.

Houd er rekening mee dat in een *Whois-query* een door Office 365 gekochte domeinregistrar wordt weergegeven als Wild West Domains LLC. Er moet echter alleen contact worden opgenomen met Office 365 met betrekking tot uw door Office 365 gekochte domein.
  
Volg de stappen hieronder om de code op te halen op Office 365. Ga vervolgens naar de website van de andere domeinregistrar om het overzetten van uw domeinnaam naar die registrar in te stellen.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Licenties voor instellingen.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a>

::: moniker-end
    
2. Selecteer op de pagina **Domeinen** het Office 365-domein dat u naar een andere domeinregistrar wilt overbrengen en selecteer **vervolgens**  >  **Domeinoverdracht Inschakelen domeinoverdracht**.
       
4. Volg de stappen om het overzetten van uw domein voor te bereiden.
    
5. Als u de code hebt opgehaald, gaat u naar de website van de domeinregistrar waar u voortaan de domeinnaam wilt beheren en volgt u de aanwijzingen voor het overzetten van een domein (zoek op de website voor hulp).
    
6. Als u de code opnieuw moet zien, selecteert u op de pagina **Domeininstellingen** in Office 365 **de machtigingscode weergeven voor domeinoverdracht**.
    
7. Nadat de overdracht is voltooid, verlengt u uw domein bij de nieuwe domeinregistrar.
    
8. Als u het proces wilt voltooien, gaat u terug naar de pagina **Domeinen** van het beheercentrum en selecteert u **Domeinoverdracht voltooien**. 

*Opmerking: u houdt er rekening mee dat door Office 365 gekochte domeinen niet in aanmerking komen voor wijzigingen in de naamserver of het domein tussen Office 365-tenants.  Als een van deze vereist is, moet de domeinregistratie worden overgedragen aan een andere registrar.*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>Hoe kan ik wijzigen hoe mijn DNS-records in Office 365 worden beheerd?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>DNS-beheer overdragen aan een DNS-host buiten Office 365
   
1. Meld u aan bij de domeinregistrar voor uw domein.
    
2. Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host. (The DNS host is often the domain registrar.)
    
3. Volg een koppeling om naar de wizard Domeininstellingen te gaan:

::: moniker range="o365-worldwide"

4. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

4. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

4. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
5. Selecteer op de pagina **Domeinen** het domein dat u overstapt en selecteer **DNS-beheer.**
    
6. Selecteer in de wizard Domeininstellingen instellen op de pagina **Uw online services instellen** de optie Ik beheer mijn eigen **DNS-records**en selecteer **vervolgens Volgende**.
    
7. Voeg de DOOR de wizard voorgestelde DNS-records toe aan de pagina **DNS-instellingen bijwerken** aan de website van uw registrar. 
    
8. Nadat u de records hebt toegevoegd, gaat u terug naar Office 365 en selecteert **u Verifiëren**.
    

### <a name="change-dns-management-to-office-365"></a>DNS-beheer overdragen aan Office 365

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum **Settings** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a> instellingen..

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.

::: moniker-end
    
2. Selecteer op de pagina **Domeinen** het domein dat u overstapt en selecteer **DNS-beheer**.
    
3. Selecteer in de wizard Domeininstellingen instellen op de pagina **Uw online services instellen** de optie Mijn online services voor mij **instellen. (Aanbevolen)** en selecteer **Volgende**.
    
4. Als u het domein nog niet hebt gecontroleerd, volg dan de stappen om dat eerst te doen.
    
5. On the **Update DNS settings** page, we list the nameservers for Office 365. Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers. 
    
4. Als u de naamservers hebt bijgewerkt, **wacht u minstens een uur**. Selecteer vervolgens terug in de wizard in Office 365 de optie **Verifiëren**.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?

If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work. We recommend that you transfer your domain to a registrar that supports all required DNS records.
  
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
    
 **Als SRV-records niet worden ondersteund**, zijn de volgende functies van Office 365 niet beschikbaar: 
  
- Integratie van de chatfunctie van Skype voor Bedrijven Online en aanwezigheidsgegevens met Outlook Web App
    
- Externe communicatie (federatie) met gebruikers van Skype voor Bedrijven Online in andere organisaties.
    
- Openbare internetverbinding (Public Internet Connectivity (PIC)) met gebruikers van Skype voor Bedrijven Online die zijn aangemeld met een Microsoft-account (voorheen Windows Live ID).
    
 **Als meerdere CNAME-records niet worden ondersteund,** moet u kiezen tussen de volgende functies voor Skype voor Bedrijven Online: 
  
- E-maildesktopclients en mobiele clients kunnen Automatisch opsporen gebruiken om automatisch de Exchange Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.
    
- Desktopclients van Skype voor Bedrijven Online kunnen Automatisch opsporen gebruiken om automatisch de Skype voor Bedrijven Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.
    
- Mobiele clients van Skype voor Bedrijven Online kunnen Automatisch opsporen gebruiken om automatisch de Skype voor Bedrijven Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.

- Microsoft Teams-federatie met Skype voor Bedrijven, on-premises of online. Zie [Het netwerk van uw organisatie voorbereiden voor Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)voor meer informatie.
    
 **If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email. SPF records work by identifying the servers that are authorized to send email from your domain. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>Hoe stel ik het standaarddomein in Of wijzig ik het in Office 365?

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

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Office 365?

::: moniker range="o365-worldwide"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein bij Microsoft hebt gekocht, u geen subdomeinen toevoegen.

::: moniker-end

::: moniker range="o365-germany"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein bij Microsoft hebt gekocht, u geen subdomeinen toevoegen.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar. Als u 21Vianet uw DNS-instellingen laat beheren met NS-records, u geen subdomeinen toevoegen.

::: moniker-end

U doorgaans maximaal 900 domeinen toevoegen aan uw Office 365-abonnement.
  
U kunt bijvoorbeeld de domeinen contoso.com en contosomarketing.com toevoegen, en vervolgens de subdomeinen www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com enzovoort.
  
Wanneer u een subdomein toevoegt, wordt deze automatisch geverifieerd op basis van het bovenliggende domein dat wordt geverifieerd.
  
When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.  *When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Als u al een contoso.com domein hebt toegevoegd aan een Office 365-tenant, u het subdomein xyz.contoso.com ook toevoegen aan een andere Office 365-tenant. Wanneer u het subdomein toevoegt, wordt u gevraagd om een TXT-record toe te voegen aan de DNS-hostingprovider.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Waarom heb ik een domein met de naam onmicrosoft.com?

Office 365 maakt een domein voor u, zoals *contoso.onmicrosoft.com,* wanneer u zich aanmeldt bij de service. De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.com*. 
  
 **Als u uw e-mail eruit wilt laten zien als *alan \@ contoso.com:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Office [365](add-domain.md) als u het al bezit. 
  
- **You can't rename the onmicrosoft domain after sign-up.** For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com. To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365. 
    
- **U de naam van de URL van uw teamsite niet wijzigen.** De URL van uw teamsite is gebaseerd op uw onmicrosoft.com domeinnaam. Vanwege de manier waarop de SharePoint Online-architectuur werkt, u de naam van de teamsite helaas niet wijzigen. 
    
- **You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain. 
    
You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Waarom heb ik een 'onmicrosoft.de'-domein?

Office 365 maakt een domein voor u, zoals *contoso.onmicrosoft.de,* wanneer u zich aanmeldt bij de service. De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.de*. 
  
 **Als u uw e-mail eruit wilt laten zien als *alan@contoso.de:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Office [365](add-domain.md) als u het al bezit. 
  
- **U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.** Als het oorspronkelijke domein dat u hebt gekozen bijvoorbeeld fourthcoffee.onmicrosoft.de, u het niet wijzigen om te worden fabrikam.onmicrosoft.de. Als u een ander onmicrosoft.de domein wilt gebruiken, moet u een nieuw abonnement starten met Office 365. 
    
- **U de naam van de URL van uw teamsite niet wijzigen.** De URL van uw teamsite is gebaseerd op uw onmicrosoft.de domeinnaam. Vanwege de manier waarop de SharePoint Online-architectuur werkt, u de naam van de teamsite helaas niet wijzigen. 
    
- **You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain. 
    
U de initiële onmicrosoft.de domein blijven gebruiken, zelfs nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Hoe verifieer ik mijn status zonder winstoogoogs naar een opleiding?

1. Selecteer **Setup** in het [beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-home) om de wizard te starten. (Moet je eerst aanmelden bij Office 365.) 
    
2. Als u beheerder van uw school wilt worden, selecteert u de optie **Een beheerder in** Office 365. 
    
3. U wordt gevraagd om een TXT DNS-record toe te voegen op de DNS-hostwebsite voor uw domein. Waarom? Omdat u door u aan te melden bij de DNS-host en een record voor uw domein toe te voegen, aan Office 365 bewijst dat u eigenaar bent van de domeinnaam.
    
4. Nadat u de record hebt toegevoegd, gaat u terug naar de Office 365-portal en bevestigt u dat u deze hebt toegevoegd, zodat Office 365 deze kan controleren.
    
Hebt u een non-profitorganisatie en wilt u Office 365 ophalen? [Zorg ervoor dat uw organisatie in aanmerking komt](https://www.microsoft.com/en-us/nonprofits/eligibility) en meld u vervolgens aan voor de service. 
  
Wilt u meer weten over het worden van de admin voor uw school? [Leer er alles over.](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>Kan ik Office 365 besturen met slechts een paar e-mailadressen uit mijn aangepaste domein?

Dat kan, maar er zijn beperkingen:
  
- Uw huidige e-mailprovider moet e-mail doorsturen.
    
- U moet uw DNS-records met Office 365 beheren bij uw DNS-hostingprovider, in plaats van dat Office 365 deze records voor u beheert. Zie Uw domein toevoegen aan Office 365 wanneer u uw eigen DNS-records wilt beheren voor meer informatie over dit inhoudt.
    
- Sommige Office 365-functies zijn niet beschikbaar:
- Gebruikers kunnen geen gratis/drukke informatie zien voor de gebruikers die zich op de andere e-mailprovider bevinden.
- Beheerders kunnen de accounts van niet vanaf één plek beheren.
- Gebruikers kunnen mogelijk geen Office 365-spamfilter gebruiken

### <a name="how-to-set-up-an-office-365-pilot"></a>Een Office 365-pilot instellen
    
1. Aanmelden bij het Microsoft 365-beheercentrum
    
    1. Meld u aan bij Office 365 met uw werk- of schoolaccount.
        
    2. Ga **Settings** naar \> **Instellingendomeinen**. 
    
2. Controleren of u eigenaar bent van het domein dat u wilt gebruiken
    
    1. Selecteer **domein toevoegen**op de pagina **Domeinen** . 
        
    2. Typ in het deelvenster het domein in dit voorbeeld cohowinery.com en selecteer **Volgende**. 
        
    3. Volg **op** de pagina Domein verifiëren de stapsgewijze instructies. 
        
    4. Selecteer in de vervolgkeuzelijst uw DNS-hostingprovider en volg de instructies om aan te geven dat u eigenaar bent van het domein.
        
    5. Selecteer **Verifiëren**. Het duurt tussen een paar minuten en 72 uur voordat DNS-wijzigingen van kracht worden. 
        
    6. Wanneer de verificatie is geslaagd, wordt u gevraagd uw DNS-records te wijzigen.
    
3. Het domein markeren als gedeeld in Exchange Online
    
    1. Ga naar het **Exchange-beheercentrum** (EAC). 
        
    2. Selecteer **geaccepteerde domeinen**in de sectie **E-mailstroom** . 
        
    3. Dubbelklik op het domein dat u wilt wijzigen.
        
    4. Selecteer **Intern relais**in het venster dat wordt geopend. 
        
    5. Kies **Opslaan**. Deze instelling kan enkele minuten nodig hebben om van kracht te worden. 
    
4. De blokkering van de bestaande e-mailserver des te deblokkeren
    
    1. Office 365 gebruikt Exchange Online Protection (EOP) voor spambescherming. Als EOP detecteert dat een groot aantal spam wordt doorgestuurd door uw huidige e-mailserver, kan deze worden geblokkeerd, waardoor doorsturen niet werkt. Als u vertrouwen hebt in de spambescherming die uw andere e-mailprovider gebruikt, u hun server toevoegen aan een lijst met toegestaneen in Office 365. Hierdoor kan echter ook spam via uw oorspronkelijke server worden geleverd via de Office 365-postvakken en u niet beoordelen hoe goed Office 365 spam voorkomt.
    
    2. Ga naar Exchange admin center (EAC).
        
    3. Selecteer in EAC **Beveiliging**en selecteer **Vervolgens Verbindingsfilter**. 
        
    4. Selecteer in de **lijst IP Toestaan**het IP-adres van de **+** e-mailserver dat u van uw huidige e-mailprovider krijgen. 
    
5. Gebruikersaccounts maken en het primaire (reply-to) adres instellen
    
    1. Ga naar het Microsoft 365-beheercentrum.
        
    2. Selecteer op de linkernavigatiebalk **De** optie \> **Actieve gebruikers van**gebruikers . 
        
    3. Maak de gebruikersaccounts.
        
    4. Selecteer voor elk account **+ (Nieuw)** en vul de vereiste informatie in. 
        
    5. Om de e-mail van de gebruiker hetzelfde te houden als nu, moet het veld **Gebruikersnaam** exact hetzelfde zijn als het bestaande e-mailadres van de gebruiker. 
        
    6. Selecteer naast gebruikersnaam uw aangepaste domeinnaam in de vervolgkeuzelijst.
        
    7. Selecteer **Sluiten** \> **maken**. 
        
6. DNS-records bijwerken bij uw DNS-hostingprovider
    
    1. Meld u aan bij de website van uw DNS-hostingprovider en volg de [DNS-records maken bij elke DNS-hostingprovider voor Office 365-stappen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). **Maak de volgende uitzonderingen:**
    
        1. Maak geen nieuwe MX-record en wijzig uw bestaande MX-record niet.
            
        2. Als u al een SPF-record (Sender Policy Framework) hebt voor uw vorige e-mailprovider, voegt u in plaats van een nieuwe SPF-record (TXT) voor Exchange Online op te maken, gewoon 'include:spf.protection.outlook.com' toe aan de huidige TXT-record. Bijvoorbeeld, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".
            
        3. Als u nog geen SPF-record hebt, wijzigt u de door Office 365 aanbevolen record om het domein voor uw huidige e-mailprovider op te nemen, plus spf.protection.outlook.com. Dit machtigt uitgaande berichten van beide e-mailsystemen.
            
7. E-mail doorsturen instellen bij uw huidige provider
    
    1. Stel bij uw huidige e-mailprovider doorsturen in voor uw gebruikers-e-mailaccounts naar uw onmicrosoft.com domein:
        
    2. Het postvak van gebruiker A moet doorsturen naar usera@yourcompany.onmicrosoft.com
        
    3. Het postvak van gebruiker B moet doorsturen naar userb@yourcompany.onmicrosoft.com
        
    4. Wanneer u deze stap voltooit:
        
    5. Alle e-mails die naar usera@yourcompany.com en userb@yourcompany.com worden verzonden, zijn beschikbaar in Office 365.
    
    6. Opmerkingen:
        
        - Neem contact op met uw huidige e-mailprovider voor de exacte stappen voor het instellen van doorsturen.
            
        - U hoeft geen kopie van berichten bij de huidige e-mailprovider te bewaren.
            
        - De meeste providers sturen e-mail door en laten het antwoordadres van de afzender intact, zodat de antwoorden naar de oorspronkelijke afzender gaan.
    
8. E-mailstroom testen
    
    1. Meld u aan bij Outlook Web App met de referenties van gebruiker A.
        
    2. Voer de volgende tests uit:
        
    3. Test lokale Microsoft-e-mail. Stuur bijvoorbeeld een e-mail naar gebruiker B. Deze e-mail moet onmiddellijk worden bezorgd. In dit scenario wordt het bericht niet doorgestuurd naar het postvak van gebruiker B op uw oorspronkelijke server, omdat het postvak in Office 365 lokaal is.
        
    4. Test e-mail naar iemand die op het andere e-mailsysteem staat. Stuur bijvoorbeeld een e-mail naar gebruiker C. Deze e-mail moet worden bezorgd in het postvak van gebruiker C op uw oorspronkelijke e-mailserver.
        
    5. Controleer vanaf een extern account of van het e-mailaccount van een werknemer op het andere e-mailsysteem of doorsturen correct is ingesteld op het andere e-mailsysteem. Stuur gebruiker A bijvoorbeeld vanuit het oorspronkelijke serveraccount van gebruiker C of een Hotmail-account een e-mail en controleer of deze binnenkomt in het Office 365-postvak van gebruiker A.
        
9. Inhoud van postvakken verplaatsen
    
    1. Aangezien er slechts twee gebruikers te verplaatsen, en aangezien gebruiker A en gebruiker B zijn beide met behulp van Outlook al, de e-mail kan worden verplaatst door het openen van de oude . PST-bestand in het nieuwe Outlook-profiel en het kopiëren van de berichten, agenda-items, contactpersonen, enz. Eenmaal georganiseerd op de juiste locaties in het Office 365-postvak, zijn de items allemaal toegankelijk vanaf elk apparaat, overal.
        
    2. Wanneer er meer postvakken bij betrokken zijn of als de werknemers Outlook nog niet gebruiken, u de migratiehulpprogramma's gebruiken die beschikbaar zijn in het Exchange-beheercentrum. Ga naar Exchange-beheercentrum en volg de aanwijzingen in E-mail migreren van een IMAP-server naar Exchange Online-postvakken om aan de slag te gaan.
    
