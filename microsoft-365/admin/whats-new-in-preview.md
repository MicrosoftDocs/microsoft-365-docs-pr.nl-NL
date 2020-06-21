---
title: Wat is er nieuw in het Microsoft 365-beheercentrum?
f1.keywords:
- CSH
ms.author: anfowler
author: adefowler
manager: shohara
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- FRP150
description: Het Microsoft 365-beheercentrum - meer informatie over de functies die deze maand zijn toegevoegd.
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
ms.openlocfilehash: d0c32c7f7ac3b2824cd48c0e10085e3d59a16c69
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780705"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Nieuwe in het Microsoft 365-beheercentrum

::: moniker range="o365-21vianet"

> [!NOTE]
> Sommige van de gegevens in dit artikel zijn mogelijk niet van toepassing op Office 365 dat wordt beheerd door 21Vianet.

::: moniker-end

We voegen voortdurend nieuwe functies toe aan [het Microsoft 365-beheercentrum,](microsoft-365-admin-center-preview.md)lossen problemen op waarover we meer te weten komen en wijzigingen aan te brengen op basis van uw feedback. Bekijk hieronder wat er vandaag voor u beschikbaar is. Sommige functies worden met verschillende snelheden uitgerold naar onze klanten. Als u nog geen functie ziet, [probeert u uzelf toe te voegen aan gerichte release.](manage/release-options-in-office-365.md)

> [!IMPORTANT]
> **"Klassieke" admin center pensionering vanaf maart**<br><br>
Wanneer u zich aanmeldt bij het Microsoft 365-beheercentrum, gaat u nu elke keer naar het nieuwe beheercentrum. En in maart zijn we begonnen met het uitschakelen van de mogelijkheid om terug te schakelen naar het klassieke admin center. Voor nu u nog steeds terugschakelen, maar als het nieuwe beheercentrum op gelijke voet komt (en deze overschrijdt) schakelen we de schakelaar voor alle organisaties uit. <br><br> *Laatst bijgewerkt: 11 mei 2020*

En als u wilt weten wat er nieuw is met andere Microsoft-cloudservices:

- [Nieuwe gegevens in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/whats-new)
- [Nieuwe in het Exchange-beheercentrum](https://docs.microsoft.com/Exchange/whats-new)
- [Nieuwe mogelijkheden in Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/whats-new)
- [Nieuw in het Microsoft 365 compliance center](https://docs.microsoft.com/Office365/SecurityCompliance/whats-new)
- [Wat is er nieuw in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)
- [Nieuwe informatie in het SharePoint-beheercentrum](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)
- [Office-updates](https://docs.microsoft.com/OfficeUpdates/)

## <a name="may-2020"></a>Mei 2020

### <a name="new-update-channel-for-office"></a>Nieuw updatekanaal voor Office

Op 12 mei kondigden we de beschikbaarheid aan van een nieuw updatekanaal voor Office: Monthly Enterprise Channel. Dit updatekanaal biedt uw gebruikers één keer per maand nieuwe Office-functies, op de tweede dinsdag van de maand.

Als u uw gebruikers toestaat Office zelf te installeren vanuit de portal, u maandelijks Enterprise Channel voor hen selecteren. Meld u hiervoor aan bij het Microsoft 365-beheercentrum en ga naar De instellingen **van de**  > Instellingen organisatieinstellingen voor**Settings**  >  **Org settings**  >  **Services**  >  **Office-software downloaden weergeven.** Als u **Eenmaal per maand (Maandelijks Enterprise Channel)** selecteert, worden nieuwe zelfinstallaties van Office geconfigureerd om maandelijks Enterprise Channel te gebruiken.

In combinatie met de release van Monthly Enterprise Channel herzien we ook de namen van de bestaande updatekanalen. Het maandkanaal wordt bijvoorbeeld hernoemd naar Huidige kanaal. De nieuwe namen gaan in op 9 juni 2020.

Zie [Wijzigingen in updatekanalen voor Microsoft 365-apps voor](https://docs.microsoft.com/DeployOffice/update-channels-changes)meer informatie.

### <a name="new-admin-roles"></a>Nieuwe beheerdersrollen

We hebben een aantal nieuwe Azure Active Directory-beheerdersrollen toegevoegd aan het Microsoft 365-beheercentrum.

- De rol van hybride identiteitsbeheerder geeft gebruikers toestemming om cloudinrichtings- en verificatieservices te beheren.
- Met de functie Netwerkbeheerder kunnen gebruikers netwerklocaties beheren en netwerkinzichten voor Microsoft 365 Software as a Service-apps bekijken.
- Printerbeheerdersrol verleent toestemming voor het beheren van alle aspecten van printers en printerverbindingen.
- Printertechnicus is een subset van de printerbeheerdersrol waarbij deze gebruikers printers kunnen registreren en uitschrijven en de printerstatus kunnen bijwerken.
[Zie Over beheerdersrollen voor](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)meer informatie over deze rollen.

### <a name="export-groups-list"></a>Lijst met exportgroepen

We hebben van veel beheerders gehoord dat ze informatie over groepen en het gebruik ervan moeten delen met mensen die geen toegang hebben tot de beheercentra. U de lijst Groepen nu exporteren naar een CSV-bestand voor controledoeleinden, wat betekent dat u dat oude PowerShell-script weggooien. Als u het wilt **Groups**uitproberen, gaat u naar  >  **Groepengroepen**en selecteert u **Groepen exporteren** op de opdrachtbalk.

### <a name="microsoft-365-solution-and-architecture-center"></a>Microsoft 365-oplossings- en architectuurcentrum

Nog deze maand hebben we een nieuwe site uitgebracht op [https://docs.microsoft.com](https://docs.microsoft.com) de [Microsoft 365-oplossing en het architectuurcentrum,](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center)die de technische richtlijnen samenbrengt die u nodig hebt om geïntegreerde Microsoft 365-oplossingen te begrijpen, te plannen en te implementeren voor veilige en compatibele samenwerking. In dit centrum vindt u:

- Richtlijnen voor basisoplossing
- Werkbelastingoplossingen en scenariobegeleiding
- Illustraties voor oplossingen en architectuur (De posters!!!)
- Branchespecifieke richtlijnen
- Enterprise architecture design principals

### <a name="docs-training-and-videos"></a>Documenten, training en video's

- **Nieuw in de Microsoft 365-videoserie**: Deze maand behandelen we de nieuwe ondersteuningservaring in de Teams-beheer- en beveiligings- en compliancecentra, planner-integratie met het Berichtencentrum en de nieuwe 3x3-video-indeling in Microsoft Teams. [Nieuwe in Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)
- De [helphubpagina van het Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/) is bijgewerkt om u te helpen sneller te vinden wat u nodig hebt. En als je nu naar die pagina gaat kijken, hebben we een kaart toegevoegd om je op de hoogte te stellen van belangrijke updates en wijzigingen.

## <a name="april-2020"></a>April 2020

### <a name="intune-roles-management"></a>Intune roles management

[April 2020](#april-2020)

Nou, het is ons gelukt! We hebben de tweede stap gezet naar een uniforme rolervaring en u nu Intune-rollen beheren in het Microsoft 365-beheercentrum. U ook gebruikmaken van functies, zoals de mogelijkheid om te zoeken naar rollen en rolmachtigingen weer te geven. Dit betekent dat u geen twee afzonderlijke hulpprogramma's nodig hebt om rollen voor Microsoft 365 en Intune te beheren. Wanneer u zich aanmeldt bij het Microsoft 365-beheercentrum, ziet u dat er twee draaipunten zijn op de pagina Rollen, een voor Azure AD en een voor Intune.

:::image type="content" source="../media/MAC-WN-IntuneRoles.png" alt-text="Rollenpagina met de intune-draaipunt geselecteerd":::

### <a name="sync-message-center-posts-to-planner"></a>Berichten van Berichtencentrum synchroniseren met Planner

Vanaf mei zien beheerders die zich in Gerichte release bevinden de knop 'Planner synchroniseren' in het berichtencentrum. U nu berichten bijhouden die actie nodig hebben, het type berichten selecteren dat u wilt bijhouden, berichten toewijzen om bij te houden als taken en berichten taggen voor latere aandacht.

[Word lid van Targeted Release](manage/release-options-in-office-365.md) om aan de slag te gaan!

### <a name="need-help-launched-in-teams-admin-center--security-and-compliance-centers"></a>"Hulp nodig?" gelanceerd in Teams admin center & Security and Compliance centers

Het Teams-beheercentrum, het beveiligingscentrum en het Compliance Center gebruiken nu hetzelfde 'Hulp nodig?' functie die het Microsoft 365-beheercentrum gebruikt voor het vinden van hulp en het contact opnemen met ondersteuning. We hebben veel feedback ontvangen van beheerders dat je hetzelfde niveau van hulp en ondersteuning wilde en we zijn blij om dat aan u te brengen. Probeer het uit en geef ons uw feedback!

#### <a name="need-chat"></a>Chat nodig?

Onze ondersteuningsmedewerkers hebben vanuit huis gewerkt terwijl we nog steeds klantaanvragen en beperkingen op de internetbandbreedte nemen terwijl thuiswerken van invloed kan zijn op de kwaliteit van het gesprek van klanten. Om u te blijven ondersteunen, hebben we een live chat-ondersteuningsoptie gelanceerd voor commerciële klanten in het Microsoft 365-beheercentrum.

Tijdens het maken van een serviceaanvraag ziet u nu ook chat als een optie, naast telefoon en e-mail. Selecteer chat als voorkeurskanaal voor communicatie en maak het verzoek. Zodra u het verzoek hebt gemaakt, u de chat starten wanneer u klaar bent om te chatten met Microsoft-agents.

### <a name="teams-updates"></a>Teams updates

Met het toegenomen gebruik van Teams hebben we een aantal functies toegevoegd om u te helpen deze te beheren.

- Een nieuwe aanbevelingskaart op de startpagina van het beheercentrum laat zien welke gebruikers Teams gedurende 30 dagen niet actief hebben gebruikt. U deze gebruikers een trainingse-mail sturen om ze aan de slag te krijgen met Teams.
- **Mensen samenbrengen met teams:** Ga naar **Setup** om een nieuwe pagina te bekijken om teams in te schakelen voor gelicentieerde gebruikers en gasttoegang te verlenen, zodat u werken met externe klanten in Teams.
- Een Microsoft Teams-kaart is nu standaard vastgemaakt aan uw startpagina. Hieruit wordt weergegeven of Teams is ingeschakeld en of gasttoegang is toegestaan. U ook de installatiestatus voor nieuw gelicentieerde Teams-gebruikers controleren en controleren of netwerkproblemen van invloed kunnen zijn op Teams-gebruikers.
- Ten slotte is Teams nu een stap in de oorspronkelijke set-up flow als u een licentie hebt gekocht die Teams bevat.

### <a name="productivity-score"></a>Productiviteitsscore

Productivity Score geeft inzicht in hoe mensen Microsoft-cloudservices gebruiken en de technologische ervaringen die hen ondersteunen. De score weerspiegelt de prestaties van uw organisatie ten opzichte van metingen van werknemers- en technologie-ervaring en vergelijkt uw score met organisaties als de uwe. Deze maand introduceren we de volgende nieuwe concepten in de preview-ervaring:

- Trendweergave van primaire inzichten op startpagina- en categoriedetailspagina's -Endpoint Analytics- en Netwerkconnectiviteitscategorieën toegevoegd aan Technologie-ervaring
- Relevant Technology Experience inzicht getoond in Employee Experience categorieën
- Nieuwe communicatiecategorie als onderdeel van Employee Experience
- Gebruikersgegevens met metagegevens van organisaties in de categorieën Employee Experience

Als u meer wilt weten, bekijk dan de blog: [Meet en verbeter de Microsoft 365-ervaring met Microsoft Productivity Score](https://techcommunity.microsoft.com/t5/microsoft-365-blog/measure-and-improve-the-microsoft-365-experience-with-microsoft/ba-p/1348618). De productiviteitsscore bevindt zich momenteel in een privévoorbeeld. [Neem deel aan de privévoorbeeld van de productiviteitsscore](https://aka.ms/productivityscorepreview) om aan de slag te gaan.

### <a name="groups-updates"></a>Groepen updates

We hebben deze maand twee updates voor groepen:

- U nu e-mailadressen bewerken voor Office 365-groepen (ook bekend als Groepen in Outlook en binnenkort Microsoft 365-groepen worden genoemd).
- We hebben uw feedback gehoord en we hebben duidelijkere foutberichten toegevoegd waarom u een groep niet converteren naar een Microsoft Team.

### <a name="docs-videos-and-training-april"></a>Documenten, video's en training (april)

**Nieuw in de Video-serie van Microsoft 365:** Deze maand behandelen we tips en bronnen om kleine bedrijven te helpen bij de overgang naar extern werk, waaronder hoe u Microsoft Teams uitrollen, externe werktrainingsbronnen om in contact te blijven met klanten en partners en het nieuwe Microsoft 365 Business Voice-abonnement. [Nieuwe in Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

#### <a name="for-your-users"></a>Voor uw gebruikers

- [Een vergadering plannen](https://support.microsoft.com/office/c61b4f61-ee62-4a06-8bf7-0a1cd302700a)
- [Deelnemen aan een Teams-vergadering](https://support.microsoft.com/office/078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [Een organisatiebreed team maken](https://support.microsoft.com/office/037bb27a-bcc9-48fe-8d72-44d9482420a3)
- [Een team met gasten maken](https://support.microsoft.com/office/11fbb083-52ee-434d-8c6e-63711fdafac7)
- [Word lid van een team als gast](https://support.microsoft.com/office/928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Een groepse-mailadres maken](https://support.microsoft.com/office/ded875f9-a9de-437f-b559-2ae4f235bb2b)

#### <a name="for-admins-and-business-owners"></a>Voor beheerders en ondernemers

- [Geef uw kleine bedrijf werk op afstand kracht bij het werk op afstand](https://support.microsoft.com/office/9b91a85a-39b4-40a6-a590-0f9bea0ba8e6)
- [Het runnen van een klein bedrijf op afstand](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Aanmelden voor Microsoft Business Basic](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Aanmelding met twee factoren instellen](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)

## <a name="march-2020"></a>Maart 2020

### <a name="featured-feedback-fix-improve-add-user-reliability-for-licensing"></a>Aanbevolen feedback fix: Verbeteren "toevoegen gebruiker" betrouwbaarheid voor licenties

We hebben veel feedback ontvangen van beheerders over hoe moeilijk het is om licenties toe te wijzen bij het toevoegen van gebruikers. We hebben de eerste update van deze oplossing gemaakt en we zijn gemigreerd naar een betrouwbaardere service achter de schermen om die aanvragen te verwerken. En als er iets misgaat, krijg je nu een foutmelding waarmee je het opnieuw proberen.

:::image type="content" source="../media/MAC-WN-ImprovedLicensing.png" alt-text="Voeg de bevestigingspagina van de gebruiker toe met de foutmelding.":::

### <a name="microsoft-teams-home-page-card"></a>Microsoft Teams-startpaginakaart

Met de toename in het gebruik van Teams krijgen sommige organisaties een vastgepinde dashboardkaart die het inschakelen van Teams beter vindbaar maakt. De kaart heeft ook links naar training en documenten om uw organisatie te helpen over te stappen op afstand werken. Ga gewoon naar de **startpagina** om de nieuwe kaart te zien.

:::image type="content" source="../media/MAC-WN-TeamsCard.PNG" alt-text="Microsoft Teams-startpaginakaart":::

### <a name="customize-your-organizations-sharepoint-mobile-app-theme"></a>Het sharepoint-app-thema van uw organisatie aanpassen

Met het Microsoft 365-beheercentrum u nu het thema van uw organisatie aanpassen in de mobiele SharePoint-app voor de mobiele iOS- en SharePoint-app voor Android. Deze functie biedt gemakkelijk een mobiele intranet-app-ervaring die uw SharePoint Online kan afstemmen voor werknemers onderweg. Thema-aanpassing omvat uw logoafbeelding, navigatiebalkkleuren, tekst- en pictogramkleuren en accentkleuren, waardoor u gemakkelijk herkennen.

:::image type="content" source="../media/MAC-WN-CustThemeSP.png" alt-text="Diagram brengt de instellingen van het beheercentrum in kaart aan de mobiele app.":::

### <a name="improvements-to-the-add-a-group-wizard"></a>Verbeteringen aan de wizard Een groep toevoegen

Wanneer beheerders een nieuwe groep hebben gemaakt en er tegelijkertijd een team van maakten, kunnen ze eigenaren toewijzen die geen licentie hebben die Teams bevat. En dat zorgde voor wat hoofdpijn. We hebben de wizardstroom bijgewerkt om te controleren of eigenaren een Teams-licentie hebben en of ze niet de optie hebben om de groep om te zetten in een team, is uitgeschakeld.

### <a name="microsoft-365-offerings-for-small-and-medium-businesses"></a>Microsoft 365-aanbiedingen voor kleine en middelgrote bedrijven

We weten dat dit een aankondiging is voor volgende maand, maar we willen er zeker van zijn dat je voorbereid bent.

Vanaf 21 april voeren we wijzigingen aan met betrekking tot onze Office 365-abonnementen voor kleine en middelgrote bedrijven en office 365 ProPlus. Deze producten zullen nu gebruik maken van het microsoft 365 merk.

De nieuwe productnamen gaan in op 21 april 2020. Dit is alleen een wijziging in de productnaam en er zijn op dit moment geen prijs- of functiewijzigingen.

|Huidige naam |Nieuwe naam  |
|---------|---------|
|Office 365 Business Essentials     |   Microsoft 365 Business Basic      |
|Office 365 Business Premium     |    Microsoft 365 Business Standard     |
|Microsoft 365 Business     |    Microsoft 365 Business Premium     |
|Office 365 Business     |    Microsoft 365-apps voor bedrijven       |
|Office 365 ProPlus    |   Microsoft 365-apps voor bedrijven      |

### <a name="videos-training-and-docs"></a>Video's, training en documenten

[Nieuwe functies in microsoft 365-webseries:](https://go.microsoft.com/fwlink/p/?linkid=2118096)In de aflevering van deze maand belichten we het 3-jarig bestaan van Microsoft Teams en bespreken we nieuwe functies, waaronder verbeterde audiokwaliteit in online vergaderingen, gerichte communicatie voor firstline-managers met de Shifts-app, Teams en Skype-interoperabiliteit van consumenten en meer.

## <a name="february-2020"></a>Februari 2020

### <a name="featured-feedback-fix-multi-organization-switcher"></a>Aanbevolen feedback fix: multi-organisatie switcher

We kregen veel feedback van partners en beheerders over de uitdagingen van het beheren van meerdere Microsoft cloud-organisaties. Een van onze eerste multi-org management functies is de **Organisatie switcher**, waarmee u veranderen tussen de orgs die u beheert in slechts 2 klikken.
> [!TIP]
> U hoeft niets te doen om de organisatieswitch te laten verschijnen zolang u de partner van record bent voor ten minste één organisatie.

1. Selecteer in het Microsoft 365-beheercentrum de naam van de organisatie.
![Schermopname: bovenaan de startpagina met de naam van het organisatieprofiel met het pictogram switcher.](../media/MAC-Organization-switcher.png)

2. Selecteer in de organisatieswitcher de organisatie die u wilt beheren.
![Schermopname: bovenaan de startpagina met de naam van het organisatieprofiel met het pictogram switcher.](../media/MAC-OrgSwitcherSelected.png)

Dat is het letterlijk!!!

### <a name="groups"></a>Groepen

Een paar veranderingen in de groepen gebied deze maand:

- **Sorteren op groepsnaam**: U de lijst met groepen alfabetisch sorteren door de kolom **Groepsnaam te** selecteren.
- **Verwijderde Microsoft 365-groepen herstellen**: u hoeft niet meer naar het Exchange-beheercentrum te gaan om verwijderde Microsoft 365-groepen te herstellen. Ga naar de groep Groepen verwijderde groepen **van Microsoft 365-beheercentrum** \> **Groups** \> **Deleted groups** \> (selecteer een groep in de lijst) \> **Groep Herstellen**. Hiermee wordt de groep teruggehersteld naar de lijst **Groepen** en worden de e-mail, gesprekken, notitieblok, bestanden en agenda van de groep hersteld.

### <a name="videos-training-and-docs-february"></a>Video's, training en documenten (februari)

- **Nieuw in de Microsoft 365-videoserie:** Deze maand richten we ons op aangepaste zoekmogelijkheden voor SharePoint Online, de beheerfunctie 'Wat is er nieuw', waarmee u specifieke functies van eindgebruikers weergeven of verbergen via het helpvenster in de app, de nieuwste beveiligings- en nalevingsupdates in Yammer en meer. Hier is de nieuwste aflevering: [What's New in Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

- **Documenten verplaatsen**: We hebben de webartikelen van Office 365-beheerders gecombineerd met de Microsoft 365-inhoud en u hebt de nieuwe URL misschien opgemerkt. Dit artikel werd bijvoorbeeld gehost op: **docs.microsoft.com/Office365/Admin/whats-new-in-preview**, maar de URL is nu: **docs.microsoft.com/microsoft-365/admin/whats-new-in-preview**. Als je pagina's hebt bladwijzers, moet je je links bijwerken. echter, inhoud links zullen worden doorgestuurd naar de nieuwe inhoud repo.

## <a name="january-2020---happy-new-year"></a>Januari 2020 - Gelukkig Nieuwjaar

> [!NOTE]
> Wist u dat er een [What's New in Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096) video-serie op YouTube? Het belicht de nieuwste functies die we hebben uitgerold naar gebruikers. Elke maand gaan we linken naar de nieuwste aflevering in de sectie [Video's, training en documenten.](#videos-training-and-docs) <br> <br> Hier is de nieuwste aflevering: [What's New in Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

### <a name="dark-mode"></a>Donkere modus

Toen we voor het eerst de donkere modus uitrolden, was deze alleen beschikbaar op de startpagina. De donkere modus is nu uit preview en is in Gerichte release op de meeste pagina's in het beheercentrum.

1. Eerst moet je Gerichte release inschakelen: Ga **Settings** naar voorkeuren voor \> **Settings** \> **het organisatieprofiel** release van \> **Release preferences**instellingen.
1. En ga vervolgens naar de **startpagina** om de donkere modus in te schakelen en selecteer vervolgens de knop **Donkere modus.** (Het is naast het veld **Zoeken** en dit artikel **is wat is de nieuwe** link.)
1. Voor elke pagina met een donkere modus beschikbaar is, staat de knop bovenaan de pagina, naast de nieuwe schakelknop van **het beheercentrum.**

### <a name="office-whats-new-management"></a>Office Wat is nieuw beheer

Beheerders willen controle over hoe Microsoft 'Wat is er nieuw' communiceert met hun gebruikers in de Office-apps - en u hebt nu die controle. Ga naar **Instellingen** \> **Office Wat is er nieuw beheervoorbeeld**. Selecteer een functie om de details weer te geven en vervolgens u de knop **Verbergen voor gebruikers** selecteren als u niet wilt dat uw gebruikers een bepaald bericht 'nieuw' zien. Uw organisatie wacht bijvoorbeeld om gebruikers op de hoogte te stellen van een functie totdat iedereen in uw organisatie erop is getraind.

![Schermopname van Office What's New preview met het detailvenster van een functie geopend.](../media/whatsnew-officemgmt-preview.png)

Deze functie werd voor het eerst uitgebracht om een preview in november, maar er zijn een paar functie-updates die u moet weten over: [Office What's New management preview updates nu beschikbaar](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-preview/ba-p/1020438)

### <a name="partners"></a>Partners

Howdy, Partners! (Kon het niet helpen mezelf.) We hebben deze maand ook een update voor je. Er is een nieuwe functie waarmee partners CSP-klanten de mogelijkheid kunnen geven om hun Microsoft Customer Agreement (MCA) te accepteren in het gedeelte **Factureringsaccounts** van het beheercentrum. In deze nieuwe ervaring:

1. De klant ontvangt een uitnodigingsmail met een link om de partnerrelatie en de MCA te accepteren.
2. Nadat de klant zich heeft aanmelden, kunnen ze de MCA- en partnermachtigingen bekijken en accepteren - rechtstreeks vanuit het beheercentrum.

### <a name="resource-mailboxes"></a>Resourcepostvakken

De lijst Met resourcepostvakken is bijgewerkt naar de nieuwe stijl. Ga in het Microsoft 365-beheercentrum naar **Resources** \> **Rooms &-apparatuur**.

### <a name="videos-training-and-docs-january"></a>Video's, training en documenten (januari)

Bekijk de training voor beheerders voor kleine bedrijven die we in januari hebben uitgebracht:

- [Uw bedrijfswebsite maken](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)
- [Antwoorden en hulp vinden](https://support.microsoft.com/office/7f681212-c649-4a3e-a43b-32b1d1e58988)
- [Hulp of ondersteuning krijgen](https://support.microsoft.com/office/18948a4c-3eb1-4b30-b1bc-a4cc29eb7655)
- [Een gebruiker verwijderen](https://support.microsoft.com/office/6bcdad7b-732a-4260-997a-8c176bc3d9d6)
- [Een Microsoft-abonnement kiezen](https://support.microsoft.com/office/b9f7c78e-430f-4117-89ec-2eeb1dced2ca)
- [Overzicht van Microsoft 365 voor bedrijfsbeveiliging](https://support.microsoft.com/office/3274b159-a825-46d7-9421-7d6e209389d1)

## <a name="november-and-december-2019"></a>November en december 2019

We combineren het nieuws van november en december, want na Ignite hadden we weinig aankondigingen te doen. Tot ziens in het nieuwe jaar!

### <a name="change-from-credit-card-to-invoice-payment"></a>Overstappen van creditcard naar factuurbetaling

We beginnen de mogelijkheid uit te rollen om uw betalingsmethode te wijzigen van creditcard naar factuur. Ga naar **Facturering** \> **Uw producten,** selecteer een abonnement en selecteer vervolgens de koppeling **Bewerken** naast de creditcardbetaling.

![Schermopname: factureringssectie van abonnementskaart met een creditcard als betalingsmethode.](../media/MAC-BillingEditCreditCard.png)

Wilt u er meer over lezen? [Wijzigen van creditcard of bankrekening naar factuur](../commerce/billing-and-payments/change-payment-method.md)

### <a name="global-reader"></a>Algemene lezer

We noemden de Global reader rol in de [oktober 2019 - Ignite Edition](#october-2019---ignite-edition), maar aangezien het breder uitrolt, laten we enkele details bespreken:

- De rol Global reader is de alleen-lezen tegenhanger van de globale beheerdersrol. De globale lezer kan alles zien waartoe de Global-beheerder toestemming heeft.
- Op een paar uitzonderingen na, zoals sommige compliance- en beveiligingsfuncties, hebben globale lezers toegang tot alle Microsoft-cloudbeheercentra die uw organisatie mag gebruiken, kunnen bekijken.
- Wijs de rol Global-lezer toe aan gebruikers die deze nodig hebben voor planning, audits en onderzoeken.
- U de globale lezersrol ook combineren met een andere rol met minder machtigingen. Een eigenaar van een klein bedrijf kan bijvoorbeeld de globale lezersrollen **voor factureringsbeheerders**toegewezen krijgen,  +  **Global reader** zodat deze de facturen kan betalen en op de hoogte kan blijven van wijzigingen in hun cloudorganisatie.
- Wereldwijde lezers kunnen naar elke pagina in het Microsoft 365-beheercentrum gaan. Wanneer ze een bewerkbare pagina openen, wordt bovenaan een waarschuwing weergegeven waarin staat dat ze geen toestemming hebben om wijzigingen op te slaan en wordt de knop Opslaan uitgeschakeld.

We krijgen graag uw feedback over de wereldwijde lezersrol en een van de op rollen gebaseerde machtigingen die u in de toekomst wilt zien. [Feedback geven voor machtigingen op basis van rollen](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/10115430-have-a-consistent-experience-when-assigning-admin)

### <a name="new-settings-page"></a>Pagina Nieuwe instellingen

Het **organisatieprofiel,** **beveiligings- & privacy**en services & **invoegpagina's** zijn allemaal gecombineerd tot één pagina met 3 verticale tabbladen. En het beste deel -- vanaf één locatie kun je nu zoeken naar alle instellingen.
![Schermopname: pagina Instellingen met het veld Alle instellingen zoeken dat boven aan de pagina is gemarkeerd.](../media/MAC-SettingsMultiPivotSearch.png)

### <a name="training--docs"></a>Training & documenten

Deze sectie is een nieuw kenmerk van dit artikel, waar we beginnen te koppelen aan nieuwe training en documentatie die we denken dat je interessant zult vinden.

In november hebben we een flink aantal leerpaden naar [de Website van Microsoft Learn](https://docs.microsoft.com/learn/) vrijgegeven om IT-professionals te helpen meer te weten te komen over en getraind te worden in Microsoft 365. Bekijk ze:

- [Microsoft 365 basisprincipes](https://docs.microsoft.com/learn/paths/m365-fundamentals/)
- [Office-fundamentals uitbreiden](https://docs.microsoft.com/learn/paths/extend-office-fundamentals/)
- [Microsoft 365 - Uw bedrijfsimplementatie moderniseren met Windows 10 en Microsoft 365 Apps voor bedrijven](https://docs.microsoft.com/learn/paths/m365-getmodern/)
- [Uw bedrijfsimplementatie beheren met Microsoft 365](https://docs.microsoft.com/learn/paths/manage-enterprise-deployment-m365/)
- [Microsoft Office voor IT op schaal upgraden](https://docs.microsoft.com/learn/paths/m365-office-for-it/)
- [Externe bureaubladen en apps vanuit Azure leveren met Windows Virtual Desktop](https://docs.microsoft.com/learn/paths/m365-wvd/)
- [Moderniseer uw werkplek met Microsoft 365 en Surface for Business](https://docs.microsoft.com/learn/paths/modernize-workplace-with-m365-and-surface/)
- [Identiteit en toegang beveiligen met Microsoft 365](https://docs.microsoft.com/learn/paths/m365-identity/)
- [Bedrijfsgegevens beveiligen met Microsoft 365](https://docs.microsoft.com/learn/paths/m365-information-protection/)
- [Beveiliging beheren met Microsoft 365](https://docs.microsoft.com/learn/paths/m365-security-management/)
- [Verdedigen tegen bedreigingen met Microsoft 365 en Microsoft threat protection](https://docs.microsoft.com/learn/paths/m365-security-threat-protection/)
- [Teamsamenwerking beheren met Microsoft Teams](https://docs.microsoft.com/learn/paths/m365-manage-team-collaboration/)
- [Samenwerken met SharePoint in Microsoft 365](https://docs.microsoft.com/learn/paths/m365-teams-sharepoint/)

## <a name="october-2019---ignite-edition"></a>Oktober 2019 - Ignite Edition

Welkom bij de Ignite Edition van de What's new in het Microsoft 365 admin center! Natuurlijk, dit is niet een volledige lijst van aankondigingen, maar hier zijn een paar hoogtepunten. Bekijk ook de Ignite blogs voor meer geweldige info over releases:

- [ADMIN - Beveiligings-, productiviteits- en netwerkverbeteringen voor Microsoft 365](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/ADMIN-Security-Productivity-and-Network-Enhancements-for/ba-p/964019).
- [Nieuwe apps in Microsoft Teams - Ignite 2020](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-New-in-Microsoft-Teams-Ignite-2019/ba-p/937025).

### <a name="role-based-access-control"></a>Toegangsbeheer op basis van rollen

Er zijn veel veranderingen voor Rollen in het beheercentrum sinds we in juni zijn begonnen met de uitrol:

- **Rollen vergelijken** - Selecteer maximaal 3 rollen om de machtigingen voor elke rol te vergelijken. Dit zal u helpen bij het vinden van de minst tolerante rol toe te wijzen aan gebruikers. Ga naar **Rollen**, gebruik het selectievakje met meerdere opties in de eerste kolom om maximaal 3 rollen te kiezen en selecteer **Vervolgens Rollen vergelijken**.

    ![De exchange-beheerders-, helpdeskbeheerder- en gebruikersbeheerdersrollen vergelijken.](../media/RBAC-CompareRoles.png)

- **Favorieten** - U een ster toevoegen aan uw favoriete of meest gebruikte rollen, zodat u ze gemakkelijk vinden door de kolom te sorteren of een filter te maken.
- **Actieve gebruikers**  >  **Rollen beheren** - Dit is bijgewerkt om af te stemmen op de wijzigingen in Rollen. Net als bij de lijst Rollen hebben we de standaardlijst met rollen naar de meest nuttige scopes beperkt, maar u alle rollen zien door **Weergeven alles per categorie**uit te breiden.
- **Global reader rol** - Je vroeg erom! Je hebt het! De [wereldwijde lezersrol!](add-users/about-admin-roles.md#azure-ad-roles-available-in-the-microsoft-365-admin-center)

### <a name="report-an-issue"></a>Een probleem melden

De servicestatus is bijgewerkt naar de nieuwe stijl en als u wordt beïnvloed door een probleem dat niet wordt weergegeven op uw servicestatusdashboard, u **een probleem melden** om microsoft dit te laten weten. Ga naar **health**  >  **service gezondheid**.

### <a name="viral-subscriptions"></a>"Virale" abonnementen

Zoals u weet, kunnen gebruikers gratis abonnementen inschakelen op een groot aantal producten zoals Power BI en App Connect. U nu de virale abonnementen zien die uw gebruikers hebben geprobeerd. Ga naar **Facturering**  >  **uw producten**. Selecteer het filter **Accounttype** op het tabblad Abonnementen om de door de gebruiker gekochte abonnementen te bekijken. Indien nodig u deze abonnementen nu uit uw account verwijderen.

### <a name="user-templates"></a>Gebruikerssjablonen

Met sjablonen u eenvoudig veel gebruikers toevoegen door de gedeelde instellingen voor deze gebruikers op te slaan en opnieuw te gebruiken. U waarden opslaan voor rollen, toegewezen licenties, contactgegevens, locatie en meer. Wanneer u de sjabloon gebruikt om een nieuwe gebruiker te maken, krijgt deze automatisch de opgeslagen waarde voor deze instellingen. Ga **Users**naar  >  **Gebruikers Actieve gebruikers**en selecteer **Gebruikerssjablonen** om het uit te proberen.

### <a name="office-whats-new-management-preview"></a>Beheer Office 'Nieuw' (Voorbeeld)

Wanneer een belangrijke Office-functie wordt vrijgegeven voor een Office-app, krijgen gebruikers een 'Nieuwe' kaart voor meer informatie over de nieuwe functie. Als u niet wilt dat gebruikers de kaart zien, u deze verbergen. U ook kiezen wanneer u wilt dat gebruikers de kaart zien door deze te laten zien. Ga naar **Instellingen**  >  **Office Wat is nieuw beheer** om het te controleren.

### <a name="sharepoint-url-change"></a>Url-wijziging van SharePoint

Technisch gezien is dit niet het nieuws van het Microsoft 365-beheercentrum om te vertellen, maar we zijn zo opgewonden dat we ervoor wilden zorgen dat je dit nieuws ziet:
> [!IMPORTANT]
> U nu naar uw SharePoint-beheercentrum gaan met een gewone URL:[https://admin.microsoft.com/SharePoint](https://admin.microsoft.com/SharePoint)

Zie [Nieuw in het SharePoint-beheercentrum](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)voor meer informatie.

## <a name="september-2019"></a>September 2019

We zijn op zoek naar een aantal spannende feature releases op Ignite 2019, dus we kondigen alleen een paar nieuwe functies aan die in september zijn uitgebracht. Maar stay tuned voor het artikel van volgende maand, zal het worden gepubliceerd op de eerste dag van Ignite!

### <a name="featured-feedback-fix--the-option-to-convert-the-deleted-users-mailbox-to-a-shared-mailbox-is-back"></a>Aanbevolen feedback oplossing - De optie om het postvak van de verwijderde gebruiker om te zetten naar een gedeeld postvak is terug

We hoorden uw feedback luid en duidelijk en we brachten de mogelijkheid om iemand anders toegang tot het postvak van een verwijderde gebruiker te geven door het om te zetten in een **gedeelde mailbox.** Als u deze weer toevoegt aan de wizard Gebruiker verwijderen, u beslissen wat u met de gegevens moet doen:

- E-mail: geef iemand anders toegang tot het postvak van de verwijderde gebruiker door het te converteren naar een gedeeld postvak.
- Bestanden: Sla hun OneDrive-bestanden op en geef iemand anders toegang.
- Machtigingen: machtigingen verwijderen als anderen toegang hadden tot dit postvak.
- Aliassen: Verwijder e-mailaliassen, zodat ze direct voor een andere gebruiker kunnen worden gebruikt.
![Schermopname: wizard gebruiker verwijderen met e-mailaliassen, machtigingen, OneDrive en e-mailopties weergegeven](../media/WhatsNew-DeleteUserWiz.png)

### <a name="initial-setup"></a>Eerste installatie

Er is een update voor een andere van onze eerste setup wizards: Microsoft 365 voor bedrijven. De stappen zijn gestroomlijnd en we hebben twee van de ingestelde taken verplaatst naar de pagina Setup:

- **Beveilig Windows 10-computers** - stel beleid in om uw Windows 10-apparaten beter te beschermen tegen virussen, malware en aanvallen door hackers.
- **Office automatisch installeren** - Wanneer u dit inschakelt en gebruikers hun pc's hebben verbonden met Microsoft 365 Business, worden hun computers automatisch bijgewerkt naar de nieuwste Office-apps en blijft ze up-to-date.

## <a name="august-2019"></a>Augustus 2019

### <a name="billing"></a>Facturering

We hebben een aantal updates voor facturering en abonnementen deze maand:

- Abonnementen op basis van apparaten: u **Microsoft 365 Apps for Education (device)** licenties toewijzen of ontwijgen aan apparaten in het Microsoft 365-beheercentrum. **Microsoft 365 Apps for Education (apparaat)** is een invoeglicentie waarmee u een licentie aan een apparaat toewijzen. Ga naar **Facturering**  >  **Uw producten** om de licentie te vinden en te kopen.
- Gebruikerslicentiebeheer: we hebben bijgewerkt hoe u licenties in **Gebruikers**actieve gebruikers aan  >  **Active users** de nieuwe stijl toewijst. Zie voor meer informatie:
  - [Licenties toewijzen aan gebruikers](manage/assign-licenses-to-users.md)
  - [Licenties van gebruikers verwijderen](manage/remove-licenses-from-users.md)

### <a name="setup-page-updates"></a>Pagina-updates instellen

Setup heeft nu categorieën en secties, waaronder een **sectie Aanbevolen voor u** waarin we op intelligente wijze uw volgende stap voorstellen om functies in te schakelen en uw organisatie in te stellen. We hebben ook een nieuwe functie toegevoegd om in te stellen:

- **Office Advanced Threat Protection** - Als uw organisatie een licentie heeft om Office ATP te gebruiken en u deze nog niet hebt geconfigureerd of ingeschakeld, ziet u deze pagina. Ga naar **Setup** om het uit te proberen.

### <a name="report-an-issue-august"></a>Een probleem melden (augustus)

Als u wordt beïnvloed door een probleem dat niet wordt weergegeven op uw servicestatusdashboard, biedt de functie **Een probleem melden** u een snelle en eenvoudige manier om ons dit te laten weten. Ga naar **health**  >  **service gezondheid**.

## <a name="july-2019"></a>Juli 2019

### <a name="message-center"></a>Berichtencentrum

Het Message center is bijgewerkt naar het nieuwe ontwerp en het ziet er geweldig uit!

![Schermopname: Bijgewerkt berichtcentrum met het tabblad 'Alle actieve berichten' geselecteerd en het menu Filter geopend.](../media/MAC-MessageCenterUpdated.png)

- U **berichten**nu bekijken op status. Selecteer een van de tabbladen: **Alle actieve berichten**, Hoog **belang,** **Ongelezen berichten**en **verwijderde berichten**.
- U ook filteren op categorie **Gegevensprivacy,** **Plannen voor wijziging,** **Problemen voorkomen of oplossen**en **rubrieken van berichten blijven.**
- Selecteer een bericht in de lijst en je hebt een paar opties op de opdrachtbalk: **Afkeuren,** **Markeren als gelezen** of Markeren **als ongelezen**of **Delen**.
- En wanneer u een bericht opent, hebt u nog meer opties:
  - Kopieer een koppeling van het bericht naar uw klembord om het voor later op te slaan of om het te delen met collega's.
  - Berichten markeren als **Gelezen** of **Ongelezen**.
  - Geef feedback over een bericht door **Vind ik leuk** of niet **leuk**te selecteren, er wordt een feedbackvenster geopend waarin u wordt gevraagd specifieke feedback te geven over wat u wel of niet leuk vond aan dit bericht.

### <a name="navigation-pane-intelligence"></a>Intelligentie van navigatiedeelvenster

 Het navigatiedeelvenster onthoudt nu uw laatste acties en toont u het deelvenster in de laatste status waarin u het hebt achtergelaten. Het zal ook veelgebruikte items standaard zichtbaar maken.

### <a name="initial-setup--the-setup-page"></a>Eerste installatie & de pagina Setup

We hebben een aantal spannende wijzigingen om u te helpen uw organisatie op te zetten. Laten we eerst het verschil bespreken tussen **de installatie** en de **pagina Setup.** **Setup** verwijst naar de initiële installatiewizard die u hebt gebruikt om aan boord te gaan van de online services van Microsoft. Dit omvat meestal drie specifieke stappen: **Een domein verbinden,** **gebruikers toevoegen**en **De Office-apps downloaden**. De **pagina Setup** is de pagina in het beheercentrum die heeft aanbevolen taken in te stellen om ervoor te zorgen dat u het meeste uit uw abonnementen haalt, zoals het inschakelen van functies waarvoor u licenties hebt gekocht.

- **Setup** - De eerste wizard Setup is bijgewerkt voor **Microsoft 365 voor zakelijke** abonnementen. Dit nieuwe ontwerp zal nieuwe organisaties helpen om sneller en met meer succes door de wizard te komen.
- **Instellingspagina** - **Op de** pagina Setup u de services die bij uw abonnementen worden geleverd, voltooien en beveiligen. U ook afgewezen aanbevelingen zien op de pagina **Setup.** Als u wilt zien of deze nog beschikbaar is voor uw abonnementen, gaat u naar het **Microsoft 365-beheercentrum**  >  **Setup**.

### <a name="billing--subscriptions"></a>Facturering & abonnementen

- **Softwareproducttype** - U nu softwareproducten bekijken die zijn gekocht via een Cloud Service Provider (CSP). Ga naar het tabblad **Software factureren**om uw downloads en sleutels te  >  **Your products**  >  **Software** bekijken.
- U moderne Azure-producten en -services bekijken vanuit het Microsoft 365-beheercentrum, of u ze nu hebt gekocht bij Microsoft of een externe provider. Voorbeelden van moderne Azure-producten waren:
  - Azure gereserveerde virtuele exemplaren
  - Azure-ondersteuningsplannen
  - Azure Hybrid Use Benefits (AHUB)
  - Toepassingen beheren
  - Apparaatservices
  - Azure-abonnementen

### <a name="simplify-multi-factor-authentication"></a>Multi-factor authenticatie vereenvoudigen

Beheerders hebben toegang tot gevoelige informatie in uw organisatie. Alle beheerders moeten meervoudige verificatie gebruiken wanneer ze zich aanmelden. De nieuwe wizard helpt je om het gedaan te krijgen met slechts één stap. Ga naar **Installatie**  >  **Versterken van aanmeldingsbeveiliging**om het uit te proberen.

### <a name="users"></a>Gebruikers

De **pagina's Verwijderde gebruikers** en **gastgebruikers** zijn bijgewerkt naar de nieuwe stijl.

- **Gastgebruikers**: u voegt gastgebruikers toe door hen uit te nodigen om bestanden vanuit SharePoint of OneDrive te bekijken of te delen. U gastgebruikers bekijken van **gebruikers**  >  **van gebruikers.**
- **Verwijderde gebruikers**: Op de bijgewerkte pagina **Verwijderde gebruikers** u alle acties uitvoeren die u in het oudere beheercentrum zou kunnen uitvoeren, maar nu voegt u kolommen toe en verwijdert u deze. En we hebben veel kolomopties om uit te kiezen. In feite zijn het dezelfde kolommen die u kiezen op de pagina **Actieve gebruikers.**

## <a name="june-2019"></a>Juni 2019

### <a name="featured-feedback-request---dark-mode"></a>Aanbevolen feedbackverzoek - Donkere modus

Het bekijken van het admin center in donkere modus is in preview! Je het nu alleen op de **startpagina** testen. Op de **startpagina** bevindt de knop **Donkere modus** zich in de opdrachtbalk naast de **nieuwe koppeling.**

### <a name="roles-management"></a>Rolbeheer

Eind juni zijn we begonnen met het uitrollen van nieuwe manieren om admin rollen te beheren. Wanneer het voor u beschikbaar **Roles**is, gaat u naar  >  **Rollenrollen**. Tot dan, neem een kijkje - het is geweldig!
<br> ![Schermopname: lijst met beheerdersrollen met het deelvenster Details van de gebruikersbeheerderrol gemarkeerd.](../media/MAC-AdminRoles-Featured.png) <br>

Deze nieuwe ervaring maakt het gemakkelijker om te zien wie beheerdersmachtigingen heeft en om rollen toe te wijzen die het juiste niveau van toegang aan uw beheerders verlenen. En we hebben ook meer rollen van Azure AD toegevoegd, zodat u geen tijd verspilt aan het gaan naar meerdere beheercentra.
Wat kun je hier nog meer doen?

- Exporteer een lijst met alle beheerders in uw organisatie die Azure Active Directory-rollen toegewezen hebben gekregen in Microsoft 365.  
- Bekijk alle beheerders die aan een specifieke rol zijn toegewezen, voeg of verwijder beheerders uit een specifieke rol, zoek naar rollen op naam en trefwoord en leer meer over wat elke rol een gebruiker toestaat te doen.
- Zoek snel naar een specifieke rol en maak filters.

### <a name="payment-method"></a>Betalingsmethode

We hebben de manier waarop u voor uw abonnementen betaalt, bijgewerkt. Ga **Billing**naar  >  **Factureringsrekeningen &**  >  **betalingsmethoden betalingen**. U uw betalingsmethoden zien in een lijstweergave. Selecteer een item in de lijst om het te verwijderen, te bewerken en eenvoudig te zien aan welk abonnement die betalingsmethode is gekoppeld.

## <a name="may-2019"></a>Mei 2019

### <a name="mays-featured-fix---case-sensitivity"></a>May's aanbevolen fix - Case gevoeligheid

Wanneer u nu zoekt naar gedeelde postvakken, contactpersonen, bronnen en postvakmachtigingen, hoeven uw zoektermen niet voor de zaak gevoelig te zijn.

**Gebruikers- en groepsbeheer** Deze maand hebben we **de pagina's Blokkeren,** **Wachtwoord opnieuw instellen**, **lijstweergave contactpersonen,** lijstweergave **Groepen** en de **pagina's Voor** de details van groepen bijgewerkt naar de nieuwe stijl van het beheercentrum.

- Met de nieuwe lijstweergave **Groepen** krijgt u rijkere gegevens over uw groepen en u de manier waarop u uw gegevens ziet aanpassen en de lijst met groepen onthoudt hoe u uw gegevens wilt zien. U nu bijvoorbeeld **filteren** op Groepen met Teams om te zien of uw groepen deel uitmaken van een team en u de **statuskolom Teams** toevoegen.
- De lijst met groepen brengt ook alle verbeteringen met zich mee die we hebben aangebracht in de lijstervaring in gebruikersbeheer, inclusief snelle acties en de contextuele opdrachtbalk.

**Aanbevelingen**<br>
Misschien ziet u een nieuwe aanbeveling pop-up in uw admin center - we hebben net 4 nieuwe toegevoegd. Natuurlijk ziet u alleen aanbevelingen als we denken dat dit uw organisatie ten goede komt. Maar wacht niet tot we u de aanbeveling laten zien - u het toevoegen vanuit de kaartbibliotheek.

- **Wachtwoord verloopt** - We raden aan dat wachtwoorden worden ingesteld op **Nooit verlopen.** En als uw organisatie een andere instelling heeft, ziet u deze aanbeveling misschien wel.
- **Te veel globale beheerders** - Omdat het hebben van te veel globale beheerders een bedreiging voor de beveiliging is, zie je deze aanbeveling als je meer dan 4 globale beheerders hebt. We raden gebruikers aan om alleen de toegang te geven die ze nodig hebben om hun werk gedaan te krijgen.
- **Intune-apparaatbeveiliging** - Als uw licenties Intune bevatten en we ontdekken dat u nog niet klaar bent met het instellen van Intune of uw apparaten hebt ingeschreven, raden we u aan een Intune-beleid te maken om de bestanden van uw organisatie te beschermen wanneer gebruikers ze openen vanaf hun mobiele apparaten.
- **Ontvang maandelijkse Updates van Office-functies** - We hebben feedback gekregen van onze zeer kleine klanten dat wanneer ze maandelijkse Updates van Office-functies ontvangen, hun gebruikers gelukkiger zijn. Dus als u een zeer klein bedrijf bent en u ontvangt momenteel om de zes maanden updates van uw Office-functie, ziet u deze aanbeveling.

**Instellingen** <br>
Wat betreft de instellingen, zijn er nogal wat veranderingen. Meestal, gewoon het bijwerken van de bestaande instellingen naar de nieuwe admin center stijl. Als we verder gaan en nieuwe instellingen toevoegen die je nog nooit eerder hebt gezien, zullen we ze hier beginnen te vermelden. En we hebben een hele instelling aan te kondigen: **Moderne authenticatie**. Ja, er is een nieuwe instelling om **moderne verificatie**in te schakelen! Ga naar **Settings**  >  **Instellingenservices & invoegtoepassingen**Moderne verificatie om het te  >  **Modern authentication**controleren.

## <a name="april-2019"></a>April 2019

Dingen zijn op zoek geweldig voor de admin center. We hebben het lezen van uw feedback en suggesties, het beantwoorden van de meeste van hen, en echt nemen alles wat je te zeggen hebt ter harte. Natuurlijk doen we nog steeds het werk om ervoor te zorgen dat alles op gelijke voet staat met het oude admin center. En vergeet niet - als we nieuwe functies uitrollen, krijg je het misschien niet meteen.

### <a name="featured-feature---add-users"></a>Aanbevolen functie - Gebruikers toevoegen

Voor april hebben we de wizard **Gebruiker toevoegen** die je door... wachten tot het ... het toevoegen van gebruikers. Het is stap voor stap om de basisgegevens van de gebruiker toe te voegen, zoals e-mail en weergavenaam, het toewijzen van een licentie en een rol, het toevoegen van hun contactgegevens en vervolgens het account van de gebruiker te controleren voordat u zich verbindt. **Waarom hebben we deze verandering gemaakt?** We hoorden uw feedback dat u niet graag de bijna oneindige scroll om gebruikers toe te voegen in de vorige ervaring.
<br> ![Schermopname van de wizard Gebruiker toevoegen.](../media/MAC-AddUserWizard.png) <br>

Er zijn twee manieren waarop u het controleren: <br>

1. Selecteer op **de** startpagina de optie Gebruiker **toevoegen** op de **gebruikersbeheerkaart.** De wizard wordt daar geopend, zodat u niet hoeft te navigeren vanaf het werk dat u op de **startpagina** doet.
2. Ga **Users**naar  >  **Gebruikers Actieve gebruikers**en selecteer Gebruiker **toevoegen** op de opdrachtbalk.
<br><br>

We hebben nog een paar wijzigingen aangebracht in **gebruikersbeheer,** hier is een snelle lijst:

- **Het deelvenster Rollen beheren** is bijgewerkt naar de nieuwe stijl en is toegankelijk. We hebben ook de **gebruikersvensters Blokkeren** en **Gebruikersvensters verwijderen** naar de nieuwe stijl bijgewerkt.
- **Productlicenties beheren** veranderde van positie op de opdrachtbalk.
- Het wijzigen van de foto van een gebruiker is nu eenvoudiger. In **Actieve gebruikers** selecteert u een gebruiker en **wijzigt u de foto** onder hun afbeelding.

### <a name="but-wait-theres-more"></a>Maar wacht! Er is meer

- Er is een nieuwe installatiebanner op de **startpagina** die u ziet als u de ingestelde stappen nog niet hebt voltooid, zoals het toevoegen van een domein, het toevoegen van gebruikers en het downloaden van de Office-apps.
- De **lijst met groepen** en het detailvenster zijn bijgewerkt naar de nieuwe stijl. Ga **Groups**naar  >  **Groepengroepen** om de wijzigingen weer te geven.
  - Over groepen gesproken, we hebben ook een tabblad **Microsoft Teams** toegevoegd aan het detailvenster voor groepen, waar u elke Microsoft 365-groep in een team veranderen. Als u een groep wilt 'samenwerken' selecteert u een Microsoft 365-groep in de lijst, selecteert u het tabblad **Microsoft Teams** en maakt **u Team**. Als de groep al een team is, krijg je een koppeling om deze te beheren vanuit het **beheercentrum teams.**
  - Ten slotte u de **status Teams** toevoegen aan de **groepenlijst.** Selecteer in de kolomkop de optie **Kolommen**  >  **kiezen Teams status**  >  **Opslaan**.
- **Nieuwe beperkte beheerdersrollen** - We hebben een aantal nieuwe beheerdersrollen vrijgegeven, zodat u gebruikers alleen de toegang geven die ze nodig hebben.
  - **Kaizala-beheerder**: Gebruikers in deze rol hebben toestemming om alle beheertaken binnen Microsoft Kaizala uit te voeren, waaronder het maken en beheren van gebruikers in de Kaizala-directory, het beheren van Kaizala-groepen, het beheren van actiekaarten en connectoren en het maken van serviceverzoeken.
  - **Zoekbeheerder**: Gebruikers in deze rol hebben volledige toegang tot alle Microsoft Search-beheerfuncties in het Microsoft 365-beheercentrum. Zoekbeheerders kunnen de rollen Zoeken en Editor zoeken delegeren aan gebruikers en inhoud maken en beheren, zoals bladwijzers, Q&A-items en locaties. Bovendien kunnen deze gebruikers het Berichtencentrum bekijken, de status van de service controleren en serviceaanvragen maken.
  - **Zoekeditor**: gebruikers in deze rol kunnen inhoud voor Microsoft Search maken, beheren en verwijderen in het Microsoft 365-beheercentrum, inclusief bladwijzers, Q&A-items en locaties.
- Er is een bonanza van **facturering** veranderingen deze maand ...
  - U de CVV nu bijwerken voor bestaande creditcards zonder deze te hoeven verwijderen en opnieuw toe te voegen. U de CVV **Bills**bijwerken door naar  >  **betaalmethoden te**gaan.
    - We hebben het gemakkelijker gemaakt om uw facturen te vinden en inzicht te krijgen in eventuele **factureringsproblemen** die uw account mogelijk heeft. En nu u uw rekeningen in de webbrowser zien in plaats van de PDF te hoeven downloaden. Ga **Bills**naar  >  **Facturen facturen**.
    - Op de pagina **Uw producten** voegen we nu uw abonnementsgegevens samen als u meerdere abonnementen van hetzelfde type hebt.

## <a name="march-2019---weve-officially-released-the-admin-center"></a>Maart 2019 - We hebben het admin center officieel uitgebracht

Nou, als je het spannende nieuws gemist, hebben we officieel de release van de nieuwe en verbeterde Microsoft 365 admin center! Hier is de blogpost waar we het aangekondigd: [De nieuwe Microsoft 365 admin center vandaag beschikbaar](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870). Voor maart, zullen we vertrouwen op de blogpost voor u om te controleren of de functies vrijgegeven - plus, u ook lezen de post voor de functies die worden vrijgegeven in de nabije toekomst, die we niet mogen doen in de kern inhoud.
<br> ![Schermopname van de startpagina van het Microsoft 365-beheercentrum.](../media/M365AC-HomePage.png) <br>
We hebben wel een wijziging in **het gebied facturering & abonnementen** dat we willen vermelden. Jullie dachten toch niet dat we klaar waren met het verbeteren? Omdat dat niet zo is! In feite hebben we deze maand de mogelijkheid toegevoegd **Billing**om uw partnerrelaties te beheren voor factureringsfactureringsaccounts.  >  **Billing accounts** Vanaf hier u uw partnerrelaties bekijken tussen adviseurs, CSP en Indirecte resellers. U ook nieuwe partnerrelatieaanvragen accepteren, inclusief gedelegeerde beheerdersmachtigingen.

Zoals altijd, uw feedback is belangrijk voor ons, dus houd het komen! Op elke pagina in het beheercentrum u feedback geven door **feedback geven** in de rechterbenedenknop te selecteren, naast **Hulp nodig?**

## <a name="february-2019---billing--subscriptions-edition"></a>Februari 2019 - Facturering & Subscriptions Edition

Deze maand gaan we ons richten op alle verbeteringen die we hebben aangebracht op de gebieden die liefkozend "Facturering en abonnementen" worden genoemd. In het verleden heb je waarschijnlijk niet verwijzen naar die dingen liefdevol, maar we denken dat je nu ...

- **Betalingsmethoden** - We hoorden uw feedback dat het bijwerken van uw betalingsmethode moeilijk was en we hebben er veel wijzigingen omheen aangebracht. Ga **Billing**naar  >  **Betaalmethoden factureren**. U eenvoudig uw betalingsmethoden zien, zoals uw Visa-kaart, en aan welk abonnement het is gekoppeld. Selecteer in uw lijst met betalingsmethoden het menu **Meer** (3 puntjes naast de vervaldatum) en selecteer **Vervolgens Abonnementen weergeven.** U uw betalingsmethoden ook bewerken en verwijderen via het menu **Meer.**
- **Factureringsaccount** - Klanten met een gerichte release zien eerst de nieuwe pagina met factureringsaccounts en vervolgens zullen we deze wereldwijd uitrollen. Wanneer het voor u beschikbaar **Billing**is, gaat u naar factureringsfactureringsaccount  >  **Billing account**. Wat u doen op de nieuwe pagina met factureringsaccounts? Ik ben blij dat je vroeg:
  - Werk het adres en andere contactgegevens in uw organisatieprofiel rechtstreeks vanaf deze pagina bij. U hoeft niet naar **het**profiel Instellingen organisatie te  >  **Organization profile**gaan, tenzij u dat wilt.
  - En we maken het leven voor direct- of volumelicentieklanten gemakkelijker, u klantovereenkomsten accepteren en controleren via **factureringsaccounts.** U ook verbinding maken met andere organisaties, zodat u de orgs koppelen om licenties en bronnen te delen.
- We hebben ook een paar kleinere verbeteringen en bugfixes gedaan:
  - Een abonnement opnieuw activeren met een factuurbetaling
  - Het servicegebruiksadres voor uw abonnementen bewerken
  - En op de pagina Voorraaddetails hebben we enkele meldingen toegevoegd, koppelen we je aan de werkelijke pagina waar je het werk doen en zijn er meer acties op de kaart voor voorraadgegevens. Ga naar Gegevens **van**  >  **factureringsfacturen**  >  **bekijken** op een factuur.

## <a name="january-2019---happy-new-year"></a>Januari 2019 - Gelukkig nieuwjaar

- Nog steeds toevoegen in **Services & invoegtoepassingen** - We hebben meer van de **instellingen > Services bijgewerkt & invoegtoepassingspagina's.** Probeer geïntegreerde apps of rapporten om het laatste nieuws te zien.
- **Op zoek naar verbeteringen?** Zoek niet verder dan het vak **Zoeken** in de opdrachtbalk. Het is bijgewerkt om u te laten zoeken naar taken. Probeer bijvoorbeeld 'wachtwoordreset' of 'een gebruiker toevoegen'.

### <a name="featured-feedback-fix---licenses-and-apps"></a>Aanbevolen feedback fix - Licenties en apps

We combineren **licenties en apps** opnieuw in het deelvenster Gebruikersgegevens op basis van uw feedback. We hebben in eerste instantie de twee functies gescheiden om ruimte te bieden voor de details van alle licenties en alle app-mogelijkheden. We hoorden van u dat het scheiden van licenties en apps in twee ruiten verwarring heeft toegevoegd. We luisterden, en bracht licenties en apps weer bij elkaar in een tabblad. U er nu voor zorgen dat een app is uitgeschakeld in alle licenties die aan een gebruiker in één deelvenster zijn toegewezen. Melk en koekjes. Licenties en apps. We krijgen het nu.

Bekijk het: **Gebruikers > Actieve gebruikers > gebruikers bewerken** of toevoegen > **licenties en apps**
