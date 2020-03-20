---
title: Microsoft 365 voor bedrijven-basisinfrastructuur voor middelgrote bedrijven
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Stap in de vereenvoudigde fasen van de basisinfrastructuur van Microsoft 365 voor bedrijven voor middelgrote bedrijven.
ms.openlocfilehash: 0d372578539ff05fcd2cadaa45c554921ee68f71
ms.sourcegitcommit: 9afcc63b1a7e73f6946f67207337f10b71a5d7f3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2020
ms.locfileid: "42809152"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-for-non-enterprises"></a>Microsoft 365 voor bedrijven-basisinfrastructuur voor middelgrote bedrijven

Middelgrote bedrijven kunnen ook Microsoft 365 voor bedrijven implementeren en de bedrijfswaarde van een geïntegreerde en beveiligde infrastructuur realiseren waarmee teamwork mogelijk is en creativiteit wordt ontsloten. Een middelgroot bedrijf heeft over het algemeen:

- Kleinschalige on-premises IT-infrastructuur, zoals e-mail- en bestandsservers en een Active Directory Domain Services-domein (AD DS) of helemaal geen.
- Een klein aantal IT-medewerkers, waarvan de meeste IT-generalisten en geen specialisten in een specifieke technologie of werkbelasting zoals netwerken of e-mail.

Voor kleinere bedrijven biedt Microsoft [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business). Er zijn echter redenen waarom u Microsoft 365 voor bedrijven nodig zou kunnen hebben, zoals:

- uw bedrijf heeft nu of in de toekomst meer dan 300 Microsoft 365-licenties (het maximum voor Microsoft 365 Business) nodig.
- uw bedrijf heeft behoefte aan de geavanceerde productiviteits-, voice-, beveiligings- en analytische mogelijkheden die niet beschikbaar zijn met Microsoft 365 Business.

In dit artikel wordt uitgelegd hoe u de basisinfrastructuur van Microsoft 365 voor bedrijven die geschikt is voor uw middelgrote bedrijf eenvoudig kunt implementeren.

## <a name="first-set-up-your-subscription"></a>Eerst moet u uw abonnement instellen

U moet de DNS-domeinen (Domain Name System) voor uw abonnement instellen. Als u al een Office 365-abonnement hebt, moet dit al zijn gedaan. Zo niet, volg dan de instructies in [Een domein toevoegen aan Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).

Vervolgens moet u aanvullende beveiliging configureren voor Microsoft 365. Volg de instructies in [Verbeterde beveiliging configureren](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

## <a name="phase-1-networking"></a>Fase 1: Netwerk

Middelgrote bedrijven hebben meestal lokale internetverbindingen in elk kantoor en gebruiken geen proxyservers, firewalls of pakketcontroleapparaten. De internetprovider (ISP) voor elk kantoor heeft een regionaal lokale DNS-server, zodat het verkeer wordt geleid naar de Microsoft 365-netwerklocatie het dichtst bij uw kantoren en hun on-premises gebruikers. Zie [Lokale internetverbindingen configureren voor elk kantoor](networking-dns-resolution-same-location.md).

U hoeft dus alleen bij uw ISP te verifiëren dat de verbinding van elk van uw kantoorlocaties:

- gebruikmaakt van een regionaal lokale DNS-server.
- geschikt is voor de huidige en toekomstige behoeften van uw gebruikers naarmate ze meer Microsoft 365-cloudservices gaan gebruiken.

Zie [Verkeersomleidingen configureren](networking-configure-proxies-firewalls.md) voor informatie over hoe u de prestaties in Microsoft 365-services kunt optimaliseren als u proxyservers, firewalls of pakketcontroleapparaten gebruikt.

### <a name="your-configuration-so-far"></a>Uw configuratie tot nu toe

Hier ziet u een visueel overzicht met het Fase 1-element gemarkeerd. **Uw bedrijf** kan bestaan uit meerdere kantoren, elk met een lokale internetverbinding met een ISP die een regionaal lokale DNS-server gebruikt. Gebruikers in elk kantoor kunnen via de ISP de dichtstbijzijnde Microsoft 365-netwerklocatie en de resources van uw Microsoft 365-abonnement benaderen.

![Uw bedrijf na de netwerkfase](../media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a>Fase 2 : Identiteit

Elke medewerker van uw bedrijf moet in staat zijn zich aan te melden. Hiervoor is een gebruikersaccount nodig in de Azure AD-tenant (Azure Active Directory) van uw Microsoft 365 voor bedrijven-abonnement. Vervolgens worden groepen gebruikt om gebruikersaccounts en andere groepen te herbergen voor communicatie of om toegang te krijgen tot gemachtigde informatiebronnen, zoals een SharePoint Online-site of een team. 

### <a name="administrator-accounts"></a>Beheerdersaccounts

Bescherm uw globale beheerdersaccounts door sterke wachtwoorden en meervoudige verificatie (MFA) te eisen. Zie [Globale beheeerdersaccounts beveiligen](identity-create-protect-global-admins.md#protect-global-administrator-accounts) voor meer informatie.

Gebruik Azure AD Privileged Identiteitsbeheer om beheerders per keer toegang te verlenen als uw bedrijf een hoge beveiliging vereist en u Microsoft 365 E5 hebt. Zie [Globale beheerders op verzoek instellen](identity-create-protect-global-admins.md#identity-pim) voor meer informatie.

### <a name="recommendations-for-groups"></a>Aanbevelingen voor groepen

Als u een on-premises AD DS-domein hebt, gebruik die groepen dan in Microsoft 365 voor bedrijven als groepen in Azure AD.

Als u geen on-premises AD DS-domein hebt, maak dan beveiligingsgroepen in Azure AD met deze beveiligingsniveaus.

| Beveiligingsniveau | Beschrijving | Voorbeelden |
|:-------|:-----|:-----|
| Basislijn | Dit is een minimale en standaardnorm voor de bescherming van gegevens en de identiteiten en apparaten die toegang hebben tot uw gegevens. <BR><BR> Dit is meestal het grootste deel van de gegevens van uw bedrijf dat wordt beheerd door de meeste gebruikers. | Groepen voor operationele medewerkers, zoals verkopers, marketing-, ondersteunings-, administratieve en productiemedewerkers. |
| Gevoelig | Dit is aanvullende bescherming voor een subverzameling van uw gegevens die beter moeten worden beschermd dan de basisbescherming. Deze groepen bevatten gebruikers die gevoelige gegevens gebruiken en maken en die specifiek zijn voor afdelingen en projecten die niet beschikbaar moeten zijn voor iedereen. | Product- of marketingteams die toekomstige producten ontwikkelen |
| Sterk gereglementeerd | Dit is het hoogste beveiligingsniveau voor een geringe hoeveelheid gegevens die zeer vertrouwelijk is, zoals intellectueel eigendom of handelsgeheimen of gegevens die moeten voldoen aan veiligheidsvoorschriften. |  Ontwikkel-, juridische en financiële teams of teams die klant- of partnergegevens opslaan of gebruiken. |
||||

### <a name="hybrid-identity"></a>Hybride identiteit

Als u een on-premises AD DS-domein hebt, moet u de gebruikersaccounts, groepen en contactpersonen van uw domein synchroniseren met de Azure AD-tenant van uw abonnement van Microsoft 365 voor bedrijven. Voor uw middelgroot bedrijf configureert u Azure AD Connect op een server met PHS (wachtwoord-hash-synchronisatie). Zie [Identiteiten synchroniseren](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity) voor meer informatie.

### <a name="more-secure-user-access-with-conditional-access-policies"></a>Beter beveiligde gebruikerstoegang met beleidsregels voor voorwaardelijke toegang.

In Azure Ad worden de voorwaarden van gebruikersaanmeldingen beoordeeld en kan beleid voor voorwaardelijke toegang worden gebruikt om toegang te verlenen of te weigeren en verdere acties op te leggen die moeten worden uitgevoerd om de aanmelding af te ronden. Als in Azure AD bijvoorbeeld wordt vastgesteld dat de aanmelding plaatsvindt onder omstandigheden met gemiddelde of hoge risico’s, kan de gebruiker MFA uit moeten voeren om de aanmelding af te ronden.

Beleidsregels voor voorwaardelijke toegang worden toegepast op gebruikersaccounts of groepen. Maak deze Azure AD-beveiligingsgroepen in uw bedrijf om eenvoudigere toewijzing van beleidsregels voor voorwaardelijke toegang mogelijk te maken:

- BASISLIJN

  Bevat de groepen of gebruikersaccounts voor gebruikers die toegang hebben tot basislijngegevens.

- GEVOELIG

  Bevat de groepen of gebruikersaccounts voor gebruikers die toegang hebben tot gevoelige gegevens.

- STERK GEREGLEMENTEERD

  Bevat de groepen of gebruikersaccounts voor gebruikers die toegang hebben tot sterk gereglementeerde gegevens.

- COND-ACCESS-EXCLUDE

  Een lege groep die u kunt gebruiken om tijdelijk een gebruiker uit te sluiten van beleidsregels voor voorwaardelijke toegang.

Dit is de lijst van beleidsregels voor voorwaardelijke toegang van Azure AD die u kunt inschakelen of maken.

| Azure AD-beleid voor voorwaardelijke toegang | Groepen waarop het van toepassing is |
|:------|:-----|
| Basislijnbeleid: vereist MFA voor beheerders | Dit beleid wordt toegepast op beheerdersrollen, er hoeven dus geen groepen te worden opgegeven. Dit beleid hoeft alleen te worden ingeschakeld. Alle volgende beleidsregels moet worden gemaakt en ingeschakeld. |
| Cliënten blokkeren die geen moderne verificatie ondersteunen | Selecteer ‘Alle gebruikers’ in de beleidsinstellingen. |
| Eis MFA als het aanmeldrisico gemiddeld of hoog is (vereist Microsoft 365 E5) | BASISLIJN |
| Eis MFA als het aanmeldrisico laag, gemiddeld of hoog is (vereist Microsoft 365 E5) | GEVOELIG |
| Eis altijd MFA | STERK GEREGLEMENTEERD |
| Eis goedgekeurde apps op iOS- en Android-apparaten | BASISLIJN, GEVOELIG, STERK GEREGLEMENTEERD |
| Eis conforme pc’s | BASISLIJN |
| Eis conforme pc’s en iOS- en Android-apparaten | GEVOELIG, STERK GEREGLEMENTEERD |
|||

Hier is het beleid van Azure AD Identiteitsbeveiliging (vereist Microsoft 365 E5) voor gebruikersrisico’s dat moet worden gemaakt en ingeschakeld.

| Beleid van Azure AD Identiteitsbeveiliging voor gebruikersrisico’s | Groepen waarop het van toepassing is |
|:------|:-----|
| Gebruikers met een hoog risico moeten wachtwoorden wijzigen | Selecteer ‘Alle gebruikers’ in de beleidsinstellingen. |
|||

Zie [Algemene beleidsregels voor identiteit en apparaattoegang](identity-access-policies.md) voor de instructies.

### <a name="groups-for-easier-management"></a>Groepen voor eenvoudiger beheer

Hier vindt u een aantal functies die groeps- en licentiebeheer eenvoudiger kunnen maken.

| Functie | Gebruik |
|:------|:-----|
| Selfservice voor groepsbeheer | Sta beheer toe van Azure AD-groepen door groepseigenaren in plaats van IT-medewerkers. Zie [Selfservice voor groepsbeheer](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups) voor meer informatie. |
| Dynamisch groepslidmaatschap | Configureer het automatisch toevoegen en verwijderen van gebruikersaccounts in Azure AD-groepen op basis van kenmerken van gebruikersaccounts, zoals afdeling of land. Zie [Dynamisch groepslidmaatschap](identity-use-group-management.md#set-up-dynamic-group-membership) voor meer informatie. |
| Licenties op groepsbasis | Gebruik het groepslidmaatschap om automatisch licenties toe te wijzen aan of te verwijderen van gebruikersaccounts. Zie [Licenties op groepsbasis](identity-use-group-management.md#set-up-automatic-licensing) voor meer informatie. |
|  |  |

Als u licenties op groepsbasis gebruikt, maak dan een groep met de naam GELICENTIEERD die gebruikersaccountnamen bevat aan wie een Microsoft 365 voor bedrijven-licentie is toegewezen.

### <a name="monitor-user-access"></a>Gebruikerstoegang controleren

Als u Microsoft 365 E5 hebt, kunt u Azure AD-identiteitsbeveiliging gebruiken om aanmeldingen van gebruikers te controleren en te analyseren voor inbreuk op referenties. Zie [Bescherming tegen inbreuk op referenties](identity-secure-user-sign-ins.md#protect-against-credential-compromise) voor meer informatie.

### <a name="your-configuration-so-far"></a>Uw configuratie tot nu toe

Hier ziet u een visueel overzicht van de Identiteitsfase voor hybride identiteiten, waarin de bestaande en nieuwe elementen zijn gemarkeerd.

![Uw bedrijf na de identiteitsfase voor hybride identiteiten](../media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
De nieuwe en gemarkeerde elementen van hybride identiteiten zijn onder meer:
 
|||
|:------:|:-----|
| ![Een on-premises AD DS-domein met gebruikersaccounts en groepen ](../media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | Een on-premises AD DS-domein met gebruikersaccounts en groepen. |
| ![Een Windows-server met Azure AD Connect](../media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | Een Windows-server met Azure AD Connect. |
| ![De gesynchroniseerde verzameling van AD DS-gebruikersaccounts en -groepen in Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | De gesynchroniseerde verzameling van AD DS-gebruikersaccounts en -groepen in Azure AD. |
| ![Azure AD-instellingen voor verificatie, beveiliging van globale accounts en vereenvoudiging van groeps- en licentiebeheer](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | Azure AD-instellingen voor verificatie, beveiliging van globale accounts en vereenvoudiging van groeps- en licentiebeheer. |
| ![Azure AD-beleid voor voorwaardelijke toegang](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | Azure AD-beleid voor voorwaardelijke toegang. |
|||

Hier ziet u een visueel overzicht van de Identiteitsfase voor cloudidentiteiten, waarin de nieuwe elementen zijn gemarkeerd.

![Uw bedrijf na de identiteitsfase voor cloudidentiteiten](../media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
De nieuwe en gemarkeerde elementen van cloudidentiteiten zijn onder meer:
 
|||
|:------:|:-----|
| ![De gebruikersaccounts en groepen in Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts-cloud-only.png) | De gebruikersaccounts en groepen in Azure AD. |
| ![Azure AD-instellingen voor verificatie, beveiliging van globale accounts en vereenvoudiging van groeps- en licentiebeheer](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | Azure AD-instellingen voor verificatie, beveiliging van globale accounts en vereenvoudiging van groeps- en licentiebeheer. |
| ![Azure AD-beleid voor voorwaardelijke toegang](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | Azure AD-beleid voor voorwaardelijke toegang. |
|||

## <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

Hier zijn uw opties om er zeker van te zijn dat uw Windows 10 Enterprise-apparaten zijn geïntegreerd in de identiteits- en beveiligingsinfrastructuur van Microsoft 365 voor bedrijven:

- Hybride (u hebt een on-premises AD DS-domein)

  Koppel elk bestaand Windows 10 Enterprise-apparaat dat al is gekoppeld aan uw AD DS-domein aan de Azure AD-tenant. Bekijk [Hybride apparaten die zijn gekoppeld aan Azure Active Directory configureren](https://go.microsoft.com/fwlink/p/?linkid=872870) voor de instructies.

  Koppel elk nieuw Windows 10 Enterprise-apparaat aan uw AD DS-domein en vervolgens aan de Azure AD-tenant.

  Registreer elk Windows 10 Enterprise-apparaat voor beheer van mobiele apparaten. Zie [Windows 10-apparaat registreren met Intune met groepsbeleid](https://go.microsoft.com/fwlink/p/?linkid=872871) voor de instructies.

- Cloud (u hebt geen on-premises AD DS-domein)

  Koppel elk Windows 10 Enterprise-apparaat aan de Azure AD-tenant van uw abonnement.

  Zie [Uw zakelijk apparaat koppelen aan uw bedrijfsnetwerk](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) voor meer informatie.


Zodra de installatie en koppeling zijn voltooid, installeert elk Windows 10 Enterprise-apparaat automatisch updates van de cloudservice Windows Update voor Bedrijven. Het is over het algemeen in een middelgroot bedrijf niet nodig een infrastructuur in te stellen om Windows 10-updates te distribueren en te installeren.

### <a name="your-configuration-so-far"></a>Uw configuratie tot nu toe

Hier ziet u een visueel overzicht van de Windows 10 Enterprise-fase waarin de nieuwe elementen zijn gemarkeerd.

![Uw bedrijf na de Windows 10 Enterprise-fase](../media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
De nieuwe en gemarkeerde Windows 10 Enterprise-elementen zijn onder meer:

|||
|:------:|:-----|
| ![Windows 10 Enterprise geïnstalleerd op Windows-apparaten](../media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | Windows 10 Enterprise geïnstalleerd op Windows-apparaten met een on-premises-laptop als voorbeeld. |
| ![Het servicecentrum voor volumelicenties](../media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | Het servicecentrum voor volumelicenties dat images biedt voor nieuwe installaties van Windows 10 Enterprise en de service Windows Update voor Bedrijven die de nieuwste updates biedt. |
|||

## <a name="phase-4-office-365-proplus"></a>Fase 4: Office 365 ProPlus

Microsoft 365 voor bedrijven omvat Office 365 ProPlus, de abonnementsversie van Microsoft Office. Office 365 ProPlus wordt net als Office 2016 of Office 2019 rechtstreeks geïnstalleerd op uw clientapparaten. Office 365 ProPlus ontvangt echter regelmatig updates met nieuwe functies. Zie [Informatie over Office 365 ProPlus in de onderneming](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) voor meer informatie.

Voor uw middelgroot bedrijf installeert u Office 365 ProPlus handmatig op apparaten, waaronder Windows-, iOS en Android-apparaten. Dit kan worden gedaan als onderdeel van het voorbereiden van een nieuw apparaat of door de gebruiker als onderdeel van het onboardingproces.

De beheerder of de gebruiker meldt zich in elk geval aan bij de Office 365-portal op https://portal.office.com. Klik in het tabblad **Microsoft Office voor thuisgebruik** op **Office installeren** en volg het installatieproces.

Functie-updates voor Office 365 ProPlus worden maandelijks gedownload door elke computer waarop het is geïnstalleerd. Het is over het algemeen in een middelgroot bedrijf niet nodig een infrastructuur in te stellen om Office 365 ProPlus-updates te distribueren en te installeren. 

### <a name="your-configuration-so-far"></a>Uw configuratie tot nu toe

Hier ziet u een visueel overzicht van de Office 365 ProPlus-fase waarin de nieuwe elementen zijn gemarkeerd.

![Uw bedrijf na de Office 365 ProPlus-fase](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
De nieuwe en gemarkeerde elementen van Office 365 ProPlus zijn onder meer:
 
|||
|:------:|:-----|
| ![Office 365 ProPlus geïnstalleerd op apparaten](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | Office 365 ProPlus geïnstalleerd op apparaten met een on-premises-laptop als voorbeeld. |
| ![Het Office-CDN (netwerk voor contentlevering) voor Office 365 ProPlus](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | Het Office-CDN (netwerk voor contentlevering) voor Office 365 ProPlus met apparaattoegang voor Office 365 ProPlus-updates. |
|||

## <a name="phase-5-mobile-device-management"></a>Fase 5: Mobile Device Management

Microsoft 365 voor bedrijven omvat Microsoft Intune voor beheer van mobiele apparaten. Met Intune kunt u Windows-, iOS-, Android- en macOS-apparaten beheren om toegang tot de resources van uw bedrijf, inclusief uw gegevens, te beschermen. Intune gebruikt de gebruikers-, groeps- en computeraccounts van Azure AD.

Intune biedt twee typen beheer voor mobiele apparaten:

- MDM (beheer voor mobiele apparaten) wordt gebruikt wanneer apparaten worden geregistreerd in Intune. Na de registratie zijn het beheerde apparaten en kunnen ze het beleid, de regels en instellingen ontvangen die door uw bedrijf worden gebruikt. Deze typen apparaten zijn over het algemeen eigendom van het bedrijf en worden uitgereikt aan uw medewerkers.

- Gebruikers met hun eigen persoonlijke apparaten willen mogelijk niet dat hun apparaat wordt geregistreerd of beheerd door Intune met uw beleid en instellingen. U moet de resources en gegevens van uw bedrijf echter nog steeds beveiligen. Voor dit scenario kunt u uw apps beveiligen met MDM (beheer voor mobiele apparaten).  

Intune-beleid kan apparaatcompatibiliteit en app-beveiliging afdwingen. Hier ziet u de lijst met Intune-beleidsregels die u kunt maken.

| Intune-beleid | Groepen waarop het van toepassing is |
|:------|:-----|
| Nalevingsbeleid voor Windows-apparaten | BASISLIJN, GEVOELIG, STERK GEREGLEMENTEERD |
| Nalevingsbeleid voor iOS-apparaten | GEVOELIG, STERK GEREGLEMENTEERD |
| Nalevingsbeleid voor macOS-apparaten | GEVOELIG, STERK GEREGLEMENTEERD |
| Nalevingsbeleid voor Android- en Android voor bedrijven-apparaten | GEVOELIG, STERK GEREGLEMENTEERD |
| App-beveiliging voor iOS | BASISLIJN, GEVOELIG, STERK GEREGLEMENTEERD |
| App-beveiliging voor macOS | BASISLIJN, GEVOELIG, STERK GEREGLEMENTEERD |
| App-beveiliging voor Android en Android voor bedrijven | BASISLIJN, GEVOELIG, STERK GEREGLEMENTEERD |
|||
    
Zie [Algemene beleidsregels voor identiteit en apparaattoegang](identity-access-policies.md) voor de instructies.

### <a name="your-configuration-so-far"></a>Uw configuratie tot nu toe

Hier ziet u een visueel overzicht van de MDM-fase waarin de nieuwe elementen zijn gemarkeerd.

![Uw bedrijf na de MDM-fase](../media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
De nieuwe en gemarkeerde MDM-elementen zijn onder meer:

|||
|:------:|:-----|
| ![Apparaten die zijn geregistreerd in Intune](../media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | Apparaten die zijn geregistreerd in Intune, met een on-premises laptop met Windows 10 Enterprise als voorbeeld. |
| ![Intune-beleid voor apparaatcompatibiliteit en app-beveiliging](../media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | Intune-beleid voor apparaatcompatibiliteit en app-beveiliging. |
|||

## <a name="phase-6-information-protection"></a>Fase 6: Gegevensbeveiliging

Microsoft 365 voor bedrijven heeft een overvloed aan functies voor gegevensbescherming waarmee u verschillende typen gegevens op verschillende manieren kunt behandelen door verschillende niveaus van beheer, beveiliging en bescherming toe te passen. 

Zo hebben bijvoorbeeld normale correspondentie tussen de meeste medewerkers en de documenten waaraan ze werken een zekere mate van bescherming nodig. Financiële documenten, klantgegevens en uw intellectuele eigendom heeft een hoger beveiligingsniveau nodig.

De eerste stap naar een gegevensbeveiligingsstrategie is het bepalen van de beveiligingsniveaus. Veel bedrijven gebruiken de volgende niveaus die al worden gebruikt voor beleid voor voorwaardelijke toegang:

- Basislijn

  Voorbeelden hiervan zijn normale bedrijfscommunicatie (e-mail) en bestanden voor administratieve, verkoop- en ondersteuningsmedewerkers.

- Gevoelig

  Voorbeelden hiervan zijn financiële en juridische gegevens en gegevens van onderzoek en ontwikkeling voor nieuwe producten of diensten.

- Sterk gereglementeerd

  Voorbeelden hiervan zijn persoonsgegevens van klanten en partners en de strategische plannen of het intellectuele eigendom van uw bedrijf.

Op basis van deze gegevensbeveiligingsniveaus is de volgende stap het identificeren en implementeren:

- Aangepaste typen van gevoelige gegevens

  Microsoft 365 biedt een grote selectie van typen gevoelige gegevens, zoals zorgverzekerings- en creditcardnummers. Als u niet in de lijst kunt vinden wat u nodig hebt, kunt u zelf typen maken.

- Bewaarlabels

  Om te voldoen aan bedrijfsbeleid en regionale regelgeving moet u mogelijk aangeven hoe lang bepaalde typen documenten of documenten met specifieke inhoud moeten worden bewaard. U kunt dit implementeren voor e-mail en documenten met bewaarlabels. Bewaarlabels kunnen ook worden gebruikt in combinatie met DLP-beleid (preventie van gegevensverlies) waarmee het delen van bestanden of e-mailberichten buiten uw bedrijf kan worden beperkt.

- Gevoeligheidslabels

  U kunt e-mailberichten of documenten labelen met een gevoeligheidslabel zodat aanvullende beveiligingsniveaus kunnen worden toegepast. Voorbeelden hiervan zijn watermerken, versleuteling en machtigingen waarin wordt opgegeven wie toegang heeft tot het e-mailbericht of document en wat ze kunnen doen.

Zie [Classificatietypen voor Microsoft 365](infoprotect-configure-classification.md#microsoft-365-classification-types) voor meer informatie.

Als u gevoeligheidslabels met machtigingen gebruikt, moet u mogelijk aanvullende Office 365-beveiligingsgroepen maken om te bepalen wie wat mag doen met e-mailberichten en documenten waarop het gevoeligheidslabel is toegepast. 

U moet bijvoorbeeld een gevoeligheidslabel ONDERZOEK maken om de e-mailberichten en documenten van uw onderzoeksteam te beveiligen. U bepaalt dat:

- Onderzoekers de mogelijkheid moeten hebben om documenten te wijzigen met het gevoeligheidslabel ONDERZOEK.
- Andere medewerkers alleen de mogelijkheid moeten hebben om documenten te bekijken met het gevoeligheidslabel ONDERZOEK. 

Dit betekent dat u twee extra Office 365-groepen moet maken en beheren:

- ONDERZOEK-ALLES
- ONDERZOEK-BEKIJKEN

Deze groepen en hun machtigingen worden onderdeel van de configuratie van het gevoeligheidslabel ONDERZOEK.

Voor gevoeligheidslabels die zijn geconfigureerd met groepsmachtigingen moet u het lidmaatschap van deze groepen beheren.

### <a name="your-configuration-so-far"></a>Uw configuratie tot nu toe

Hier ziet u een visueel overzicht van de Gegevensbeschermingsfase waarin de nieuwe elementen zijn gemarkeerd.

![Uw bedrijf na de gegevensbeschermingsfase](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
De nieuwe en gemarkeerde gegevensbeveiligingselementen zijn onder meer:
 
|||
|:------:|:-----|
| ![Gevoeligheidslabels voor de drie beveiligingsniveaus](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | Gevoeligheidslabels voor de drie beveiligingsniveaus die gebruikers kunnen toepassen op documenten en e-mailberichten. |
|||

Aangepaste gegevenstypen en bewaarlabels worden niet getoond.

## <a name="onboarding"></a>Onboarding

Met de Microsoft 365 voor bedrijven-infrastructuur kunt u uw medewerkers eenvoudig faciliteren.

### <a name="a-new-windows-10-enterprise-device"></a>Een nieuw Windows 10 Enterprise-apparaat

Voordat u een medewerker een nieuw Windows 10 Enterprise-apparaat geeft:

- Voor hybride identiteit

  Koppel het apparaat aan uw AD DS-domein en uw Azure AD-tenant en registreer het apparaat vervolgens in Intune.

- Voor cloudidentiteit

  Koppel het apparaat aan uw Azure AD-tenant.

### <a name="existing-employee-with-an-ad-ds-user-account"></a>Bestaande medewerker met een AD DS-account

Voeg het AD DS-gebruikersaccount toe aan de volgende Azure AD-groepen als onderdeel van de initiële introductie in uw bedrijf wanneer u een hybride identiteit gebruikt:

- GELICENTIEERD
- De juiste AD DS- of Azure AD-beveiligingsgroepen die lid zijn van de Azure AD-groepen BASISLIJN, GEVOELIG en STERK GEREGLEMENTEERD
- Gevoeligheidslabelgroepen (indien nodig)

De bestaande medewerker zou al aan de juiste werk-, afdelings- en regionale AD DS-groepen moeten zijn toegevoegd.

U kunt een gebruikersaccount toevoegen aan meerdere Azure AD-groepen in het Microsoft 365-beheercentrum. Klik in de eigenschappen van het gebruikersaccount op **Groepen beheren > Lidmaatschappen toevoegen**.

Bekijk deze [downloadbare Excel-werkmap](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-foundation-infrastructure-non-enterprises/Group-License-Mgmt-PowerShell.xlsx) als u PowerShell wilt gebruiken, waarmee de PowerShell-opdrachten worden gegenereerd op basis van een specifiek gebruikersaccount en geselecteerde groepsnamen.

### <a name="new-employee-with-a-cloud-only-user-account"></a>Nieuwe medewerker met cloudgebruikersaccount 

Voeg het nieuwe gebruikersaccount toe aan de volgende groepen als onderdeel van de initiële introductie in uw bedrijf wanneer u een cloudidentiteit gebruikt:

- GELICENTIEERD
- De juiste Azure AD-beveiligingsgroepen die lid zijn van de Azure AD-groepen BASISLIJN, GEVOELIG en STERK GEREGLEMENTEERD.
- Werk-, afdelings- en regionale groepen
- Gevoeligheidslabelgroepen (indien nodig)

### <a name="initial-sign-in-to-microsoft-365"></a>Initiële aanmelding bij Microsoft 365

Instrueer de nieuwe medewerkers dat wanneer ze zich voor het eerst aanmelden in Microsoft 365:

1. Ze zich aanmelden bij hun apparaten met de aanmeldingsgegevens van hun gebruikersaccount.
2. Een browser gebruiken om zich op https://portal.office.com aan te melden bij de Office 365-portal.
3. Vanaf het tabblad **Office 365 voor thuisgebruik** klikken op **Office installeren** om Office 365 ProPlus op hun apparaat te installeren.

## <a name="end-results"></a>Eindresultaten

Hieronder ziet u de eindresultaten van de configuratie van de Microsoft 365 voor bedrijven-basisinfrastructuur voor uw middelgroot bedrijf.

### <a name="infrastructure-results"></a>Infrastructuurresultaten

Na de opbouw en configuratie van uw Microsoft 365 voor bedrijven-infrastructuur hebt u als het goed is:

- Een lokale internetverbinding voor elk van uw kantoren met voldoende bandbreedte, geleverd door een ISP die gebruikmaakt van een regionaal lokale DNS-server.
- Azure AD Connect dat wordt uitgevoerd op een server die uw on-premises AD DS-domein synchroniseert met uw Azure AD-tenant voor hybride identiteiten.
- Deze groepen:
  - GELICENTIEERD
  - COND-ACCESS-EXCLUDE
  - De juiste AD DS- of Azure AD-beveiligingsgroepen die ook lid zijn van de Azure AD-groepen BASISLIJN, GEVOELIG en STERK GEREGLEMENTEERD. 
  - Werk-, afdelings- en regionale groepen
  - Office 365-gevoeligheidslabelgroepen (indien nodig)
- Azure AD-aanmeldbeleid voor voorwaardelijke toegang die de Azure AD-groepen BASISLIJN, GEVOELIG, STERK GEREGLEMENTEERD en COND-ACCESS-EXCLUDE gebruiken.
- Intune-toepassings- en nalevingsbeleid voor apparaten.
- Aangepaste typen gevoelige gegevens (indien nodig).
- Bewaarlabels (indien nodig).
- Gevoeligheidslabels (indien nodig).

Hieronder ziet u een visueel overzicht van de infrastructuur wanneer uw bedrijf een hybride identiteit gebruikt met uw AD DS-domein, een Azure AD Connect-server en gesynchroniseerde AD DS-gebruikers en -groepen.

![Overzicht van de infrastructuur wanneer uw bedrijf een hybride identiteit gebruikt](../media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
Hieronder ziet u een visueel overzicht van de infrastructuur wanneer uw bedrijf een cloudindentiteit gebruikt.
 
![Overzicht van de infrastructuur wanneer uw bedrijf een cloudindentiteit gebruikt](../media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a>Werknemersresultaten

Na de onboarding moet elke medewerker het volgende hebben:

- Een goed presterend, on-premises netwerkpad van zijn apparaat naar de Microsoft 365-cloudservices in zijn regio.
- Een gebruikersaccount met deze groepslidmaatschappen:
   - GELICENTIEERD
   - De juiste AD DS- of Azure AD-beveiligingsgroepen die ook lid zijn van de Azure AD-groepen BASISLIJN, GEVOELIG en STERK GEREGLEMENTEERD voor beleid voor voorwaardelijke toegang 
   - De juiste werk-, afdelings- en regionale groepen
   - Office 365-gevoeligheidslabelgroepen (indien nodig)
- Een Windows 10 Enterprise-apparaat:
   - dat is gekoppeld aan de Azure AD-tenant (cloud) of aan zowel de Azure AD-tenant als uw AD DS-domein (hybride).
   - dat zichzelf automatisch bijwerkt met de nieuwste verbeteringen voor Windows 10 Enterprise-producten en -beveiliging. 
   - waarop Office 365 ProPlus is geïnstalleerd, dat zichzelf automatisch bijgewerkt met de nieuwste verbeteringen voor Office-producten en -beveiliging
   - dat is geregistreerd in Intune en valt onder nalevings- en app-beveiligingsbeleid van Intune.

## <a name="next-step"></a>Volgende stap

Implementeer uw [werkbelastingen en scenario’s](deploy-workloads.md) om te profiteren van de functies en configuratie van uw Microsoft 365 voor bedrijven-basisinfrastructuur.
