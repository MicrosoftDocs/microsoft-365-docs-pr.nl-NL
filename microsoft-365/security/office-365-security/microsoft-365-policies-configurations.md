---
title: Configuraties voor identiteits- en apparaattoegang - Microsoft 365 voor ondernemingen
description: In dit artikel worden aanbevelingen en basisconcepten van Microsoft beschreven voor het implementeren van veilige e-mail, documenten en apps-beleidsregels en -configuraties.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: 0f6e3d7bef0f09dc922a7c1878e6ea7ce0aad3d7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233150"
---
# <a name="identity-and-device-access-configurations"></a>Configuratie van identiteiten en apparaattoegang

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

De moderne beveiligingsperimeter van uw organisatie breidt zich nu uit buiten uw netwerk om gebruikers toe te laten die cloud-apps openen vanaf elke locatie met een verscheidenheid aan apparaten. Uw beveiligingsinfrastructuur moet bepalen of een bepaalde toegangsaanvraag moet worden verleend en onder welke voorwaarden.

Deze beslissing dient te zijn gebaseerd op het gebruikersaccount van de aanmelding, het gebruikte apparaat, de app die de gebruiker gebruikt voor toegang, de locatie waar de toegangsaanvraag wordt ingediend en een evaluatie van het risico van de aanvraag. Op deze manier zorgt u ervoor dat alleen goedgekeurde gebruikers en apparaten toegang hebben tot uw belangrijke bronnen.

In deze reeks artikelen wordt een reeks vereiste configuraties voor identiteits- en apparaattoegang en een reeks voorwaardelijke toegang van Azure Active Directory (Azure AD), Microsoft Intune en andere beleidsregels beschreven voor het beveiligen van toegang tot Microsoft 365 voor cloud-apps en -services voor ondernemingen, andere SaaS-services en on-premises toepassingen die zijn gepubliceerd met Azure AD-toepassingsproxy.

Identiteits- en apparaattoegangsinstellingen en -beleid worden aanbevolen in drie lagen: basislijnbeveiliging, gevoelige beveiliging en beveiliging voor omgevingen met sterk reguleerde of geclassificeerde gegevens. Deze lagen en de bijbehorende configuraties bieden een consistent beveiligingsniveau van uw gegevens, identiteiten en apparaten.

Deze mogelijkheden en hun aanbevelingen:

- Deze worden ondersteund in Microsoft 365 E3 en Microsoft 365 E5.
- Deze worden afgestemd op [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) en de identiteitsscore in Azure [AD,](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)en verhogen deze scores voor uw organisatie.
- Helpt u bij het implementeren van deze [vijf stappen voor het beveiligen van uw identiteitsinfrastructuur.](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)

Als uw organisatie unieke omgevingsvereisten of -complexiteiten kent, gebruikt u deze aanbevelingen als uitgangspunt. De meeste organisaties kunnen deze aanbevelingen echter implementeren zoals voorgeschreven.

Bekijk deze video voor een kort overzicht van identiteits- en apparaattoegangsconfiguraties voor Microsoft 365 voor Ondernemingen.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft verkoopt ook ENTERPRISE Mobility + Security -licenties (EMS) voor Office 365-abonnementen. EMS E3- en EMS E5-mogelijkheden zijn gelijk aan die in Microsoft 365 E3 en Microsoft 365 E5. Zie [EMS-abonnementen](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) voor de details.

## <a name="intended-audience"></a>Beoogde doelgroep

Deze aanbevelingen zijn bedoeld voor ondernemingsarchitecten en IT-professionals die bekend zijn met cloudproductiviteits- en beveiligingsservices van Microsoft 365, waaronder Azure AD (identiteit), Microsoft Intune (apparaatbeheer) en Azure Information Protection (gegevensbescherming).

### <a name="customer-environment"></a>Klantomgeving

Het aanbevolen beleid is van toepassing op ondernemingen die zowel volledig in de Microsoft-cloud als voor klanten met een hybride identiteitsinfrastructuur werken. Dit is een on-premises AD DS-forest (Active Directory Domain Services) die wordt gesynchroniseerd met een Azure AD-tenant.

Veel van de verstrekte aanbevelingen zijn afhankelijk van services die alleen beschikbaar zijn in Microsoft 365 E5, Microsoft 365 E3 met de Identity & Threat Protection-invoeglicenties, EMS E5 of Azure Premium P2.

Voor organisaties die deze licenties niet hebben, raadt Microsoft u aan om in ieder geval beveiligingsinstellingen te [implementeren,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)die zijn opgenomen in alle Microsoft 365-abonnementen.

### <a name="caveats"></a>Waarschuwingen

Uw organisatie kan onderhevig zijn aan wettelijke of andere nalevingsvereisten, waaronder specifieke aanbevelingen waarvoor u mogelijk beleid moet toepassen dat afwijkt van deze aanbevolen configuraties. Bij deze configuraties worden gebruiksbesturingselementen aanbevolen die historisch niet beschikbaar zijn geweest. Wij raden deze besturingselementen aan omdat wij van mening zijn dat deze een balans vertegenwoordigen tussen beveiliging en productiviteit.

We hebben ons best gedaan om rekening te houden met een groot aantal vereisten voor organisatiebescherming, maar we kunnen niet rekening houden met alle mogelijke vereisten of voor alle unieke aspecten van uw organisatie.

## <a name="three-tiers-of-protection"></a>Drie beschermingsniveaus

De meeste organisaties hebben specifieke vereisten met betrekking tot beveiliging en gegevensbescherming. Deze vereisten verschillen per branchesegment en per functie binnen organisaties. Het is bijvoorbeeld mogelijk dat uw juridische afdeling en beheerders aanvullende besturingselementen voor beveiliging en gegevensbescherming vereisen voor hun e-mail-correspondentie die niet vereist zijn voor andere bedrijfseenheden.

Elke branche heeft ook een eigen set gespecialiseerde regelgeving. In plaats van een lijst te verstrekken met alle mogelijke beveiligingsopties of een aanbeveling per branchesegment of functie, zijn er aanbevelingen gedaan voor drie verschillende beveiligings- en beschermingsniveaus die kunnen worden toegepast op basis van de granulatie van uw behoeften.

- **Basislijnbeveiliging:** het is raadzaam een minimale standaard op te geven voor het beschermen van gegevens, evenals de identiteiten en apparaten die toegang hebben tot uw gegevens. U kunt deze basislijnaanbevelingen volgen om een krachtige standaardbeveiliging te bieden die voldoet aan de behoeften van veel organisaties.
- **Gevoelige beveiliging:** sommige klanten hebben een subset van gegevens die op hogere niveaus moeten worden beschermd, of mogelijk moeten alle gegevens op een hoger niveau worden beschermd. U kunt extra beveiliging toepassen op alle of specifieke gegevenssets in uw Microsoft 365-omgeving. U wordt aangeraden identiteiten en apparaten te beveiligen die toegang hebben tot gevoelige gegevens met vergelijkbare beveiligingsniveaus.
- **Sterk reguleerd:** sommige organisaties hebben mogelijk een kleine hoeveelheid gegevens die sterk is geclassificeerd, die bedrijfsgeheimen vormen of die is reguleerd. Microsoft biedt mogelijkheden om organisaties te helpen aan deze vereisten te voldoen, waaronder extra beveiliging voor identiteiten en apparaten.

![Beveiligings kegel - Alle klanten > sommige klanten > specifieke klanten. Algemene toepassing voor specifieke toepassing](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

Deze richtlijnen laten zien hoe u voor elk van deze beveiligingslagen beveiliging voor identiteiten en apparaten kunt implementeren. Gebruik deze richtlijnen als uitgangspunt voor uw organisatie en pas het beleid aan om te voldoen aan de specifieke vereisten van uw organisatie.

Het is belangrijk dat u een consistent beveiligingsniveau gebruikt voor uw gegevens, identiteiten en apparaten. Als u deze richtlijnen bijvoorbeeld implementeert, moet u uw gegevens op vergelijkbare niveaus beschermen.

Het **model Identiteits- en apparaatbeveiliging voor Microsoft 365-architectuur** laat zien welke mogelijkheden vergelijkbaar zijn.

[![Thumb image for Identity and device protection for Microsoft 365 poster](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [Weergeven als PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Downloaden als PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Downloaden als Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Zie ook de [oplossing Gegevensbescherming implementeren voor](../../solutions/information-protection-deploy.md) regelgeving met de privacy van gegevens om informatie te beschermen die is opgeslagen in Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Beveiligings- en productiviteitsupdates

Het implementeren van een beveiligingsstrategie vereist een balans tussen beveiliging en productiviteit. Het is handig om te evalueren hoe elke beslissing van invloed is op de balans van beveiliging, functionaliteit en gebruiksgemak.

![Beveiliging met drie verschillende functies: beveiliging, functionaliteit en gebruiksgemak.](../../media/microsoft-365-policies-configurations/security-triad.png)

De aanbevelingen zijn gebaseerd op de volgende principes:

- Ken uw gebruikers en wees flexibel in hun beveiligings- en functionele vereisten.
- Pas een beveiligingsbeleid net op tijd toe en zorg ervoor dat het zinvol is.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Services en concepten voor identiteits- en apparaattoegangsbescherming

Microsoft 365 voor ondernemingen is ontworpen voor grote organisaties om iedereen in staat te stellen creatief te zijn en veilig samen te werken.

Deze sectie bevat een overzicht van de Microsoft 365-services en -mogelijkheden die belangrijk zijn voor identiteits- en apparaattoegang.

### <a name="azure-ad"></a>Azure AD

Azure AD biedt een volledige suite met mogelijkheden voor identiteitsbeheer. U wordt aangeraden deze mogelijkheden te gebruiken om toegang te beveiligen.

|Functie|Beschrijving|Licenties|
|---|---|---|
|[Meervoudige verificatie (Multi-Factor Authentication, MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|Voor MFA moeten gebruikers twee vormen van verificatie opgeven, zoals een gebruikerswachtwoord plus een melding van de Microsoft Authenticator-app of een telefoongesprek. Met MFA verkleint u het risico dat gestolen referenties worden gebruikt voor toegang tot uw omgeving. Microsoft 365 gebruikt de Azure AD Multi-Factor Authentication-service voor MFA-aanmeldingen.|Microsoft 365 E3 of E5|
|[Voorwaardelijke toegang](/azure/active-directory/conditional-access/overview)|Azure AD evalueert de voorwaarden voor de aanmelding van de gebruiker en gebruikt beleidsregels voor voorwaardelijke toegang om de toegestane toegang te bepalen. In deze richtlijnen laten we u bijvoorbeeld zien hoe u een beleid voor voorwaardelijke toegang kunt maken om apparaat compliance te vereisen voor toegang tot gevoelige gegevens. Hiermee verkleint u het risico dat hacker met een eigen apparaat en gestolen referenties toegang krijgt tot uw gevoelige gegevens. Ook worden gevoelige gegevens op de apparaten beschermd, omdat de apparaten aan specifieke vereisten voor status en beveiliging moeten voldoen.|Microsoft 365 E3 of E5|
|[Azure AD-groepen](/azure/active-directory/fundamentals/active-directory-manage-groups)|Voorwaardelijk toegangsbeleid, apparaatbeheer met Intune en zelfs machtigingen voor bestanden en sites in uw organisatie zijn afhankelijk van de toewijzing aan gebruikersaccounts of Azure AD-groepen. U wordt aangeraden Azure AD-groepen te maken die overeenkomen met de beschermingsniveaus die u implementeert. Uw leidinggevenden zijn bijvoorbeeld waarschijnlijk hogere waardedoelen voor hackers. Daarom is het zinvol om de gebruikersaccounts van deze werknemers toe te voegen aan een Azure AD-groep en deze groep toe te wijzen aan beleidsregels voor voorwaardelijke toegang en andere beleidsregels die een hoger beveiligingsniveau afdwingen voor toegang.|Microsoft 365 E3 of E5|
|[Apparaatinschrijving](/azure/active-directory/devices/overview)|U meldt een apparaat in bij Azure AD om een identiteit voor het apparaat te maken. Deze identiteit wordt gebruikt om het apparaat te verifiëren wanneer een gebruiker zich heeft aanmelden en voor het toepassen van beleidsregels voor voorwaardelijke toegang waarvoor een domein is aangesloten of compatibele pc's zijn. Voor deze richtlijnen gebruiken we apparaatregistratie om automatisch aan een domein verbonden Windows-computers te registreren. Apparaatinschrijving is een vereiste voor het beheren van apparaten met Intune.|Microsoft 365 E3 of E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Hiermee kunt u potentiële beveiligingsproblemen opsporen die de identiteiten van uw organisatie beïnvloeden en een geautomatiseerd herstelbeleid configureren voor lage, gemiddelde en hoge aanmeldings- en gebruikersrisico's. Deze richtlijnen zijn afhankelijk van deze risico-evaluatie om beleidsregels voor voorwaardelijke toegang toe te passen voor meervoudige verificatie. Deze richtlijnen omvatten ook een beleid voor voorwaardelijke toegang, zodat gebruikers hun wachtwoord moeten wijzigen als er activiteit met een hoog risico voor hun account wordt gedetecteerd.|Microsoft 365 E5, Microsoft 365 E3 met de identity & Threat Protection-add-on, EMS E5 of Azure Premium P2-licenties|
|[Selfservice voor wachtwoord opnieuw instellen (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Sta uw gebruikers toe hun wachtwoorden veilig en zonder tussenkomst van de helpdesk opnieuw in te stellen door verificatie te bieden van meerdere verificatiemethoden die de beheerder kan beheren.|Microsoft 365 E3 of E5|
|[Azure AD-wachtwoordbeveiliging](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)|Bekende zwakke wachtwoorden en hun varianten en aanvullende zwakke termen opsporen en blokkeren die specifiek zijn voor uw organisatie. Standaardlijsten met verboden wachtwoorden worden automatisch toegepast op alle gebruikers in een Azure AD-tenant. U kunt aanvullende vermeldingen definiëren in een aangepaste lijst met geblokkeerde wachtwoorden. Als gebruikers hun wachtwoord wijzigen of opnieuw instellen, worden deze verboden wachtwoordlijsten ingeschakeld om het gebruik van sterke wachtwoorden af te dwingen.|Microsoft 365 E3 of E5|
|

Hier volgen de onderdelen van identiteits- en apparaattoegang, waaronder Intune- en Azure AD-objecten, instellingen en subservices.

![Onderdelen van identiteits- en apparaattoegang](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) is de cloudservice voor het beheer van mobiele apparaten van Microsoft. Deze richtlijnen raden apparaatbeheer van Windows-pc's met Intune aan en raden beleidsconfiguraties voor apparaat compliance aan. Intune bepaalt of apparaten compatibel zijn en verzendt deze gegevens naar Azure AD voor gebruik bij het toepassen van beleidsregels voor voorwaardelijke toegang.

#### <a name="intune-app-protection"></a>Intune-appbeveiliging

[Beveiligingsbeleid via de Intune-app](https://docs.microsoft.com/intune/app-protection-policy) kan worden gebruikt om de gegevens van uw organisatie te beschermen in mobiele apps, met of zonder apparaten in te schrijven voor beheer. Intune beschermt informatie, zodat uw werknemers nog steeds productief kunnen zijn en gegevensverlies kunnen voorkomen. Door beleid op app-niveau te implementeren, kunt u de toegang tot bedrijfsbronnen beperken en gegevens binnen het beheer van uw IT-afdeling houden.

Deze richtlijnen laten zien hoe u aanbevolen beleid kunt maken om het gebruik van goedgekeurde apps af te dwingen en om te bepalen hoe deze apps kunnen worden gebruikt met uw zakelijke gegevens.

### <a name="microsoft-365"></a>Microsoft 365

Deze richtlijnen laten zien hoe u een set beleidsregels implementeert om de toegang tot Microsoft 365-cloudservices te beschermen, waaronder Microsoft Teams, Exchange Online, SharePoint Online en OneDrive voor Bedrijven. Naast het implementeren van dit beleid, raden we u aan ook het beschermingsniveau voor uw tenant te verhogen met behulp van de volgende bronnen:

- [Je tenant configureren voor betere beveiliging](tenant-wide-setup-for-increased-security.md)

  Aanbevelingen die van toepassing zijn op basislijnbeveiliging voor uw tenant.

- [Roadmap voor beveiliging: Topprioriteiten voor de eerste 30, 90 dagen en daarna](security-roadmap.md)

  Aanbevelingen voor logboekregistratie, gegevensbeheer, beheerderstoegang en bedreigingsbeveiliging.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10- en Microsoft 365-apps voor ondernemingen

Windows 10 met Microsoft 365 Apps voor ondernemingen is de aanbevolen clientomgeving voor pc's. We raden Windows 10 aan omdat Azure zo is ontworpen dat deze de soepelste ervaring biedt voor zowel on-premises als Azure AD. Windows 10 bevat ook geavanceerde beveiligingsmogelijkheden die kunnen worden beheerd via Intune. Microsoft 365 Apps voor ondernemingen bevat de nieuwste versies van Office-toepassingen. Deze maken gebruik van moderne verificatie, die veiliger is en een vereiste is voor voorwaardelijke toegang. Deze apps bevatten ook verbeterde hulpprogramma's voor beveiliging en naleving.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Deze mogelijkheden toepassen op de drie beveiligingslagen

De volgende tabel bevat een overzicht van onze aanbevelingen voor het gebruik van deze mogelijkheden in de drie beschermingsniveaus.

|Beveiligingsmechanisme|Basislijn|Gevoelig|Sterk gereglementeerd|
|---|---|---|---|
|**MFA afdwingen**|Bij een gemiddeld of hoger aanmeldingsrisico|Bij laag of hoger aanmeldingsrisico|Bij alle nieuwe sessies|
|**Wachtwoordwijziging afdwingen**|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|
|**Intune-toepassingsbeveiliging afdwingen**|Ja|Ja|Ja|
|**Intune-inschrijving afdwingen voor apparaat dat eigendom is van een organisatie**|Vereist een compatibele pc of pc die aan een domein is aangesloten, maar laat uw eigen apparaten (BYOD)-telefoons en -tablets toe|Een compatibel apparaat of apparaat dat aan een domein is verbonden vereisen|Een compatibel apparaat of apparaat dat aan een domein is verbonden vereisen|
|

## <a name="device-ownership"></a>Eigendom van apparaat

De bovenstaande tabel weerspiegelt de trend voor veel organisaties om ondersteuning te bieden voor een combinatie van apparaten die eigendom zijn van de organisatie en persoonlijke apparaten of BYOD's om mobiele productiviteit voor alle medewerkers mogelijk te maken. Beveiligingsbeleidsregels voor Intune-apps zorgen ervoor dat e-mail wordt beveiligd tegen het uitfilten van de mobiele Outlook-app en andere Mobiele Office-apps, op apparaten van de organisatie en BYOD's.

Het is raadzaam dat apparaten die eigendom zijn van de organisatie worden beheerd door Intune of apparaten die aan een domein zijn aangesloten, om aanvullende beveiliging en beheer toe te passen. Afhankelijk van de gevoeligheid van gegevens, kan uw organisatie ervoor kiezen om BYOD's niet toe te staan voor specifieke gebruikers bevolkingsgroepen of specifieke apps.

## <a name="deployment-and-your-apps"></a>Implementatie en uw apps

Voordat u identiteit en apparaattoegang configureert en uitrolt voor uw in Azure AD geïntegreerde apps, moet u het volgende doen:

- Bepaal welke apps worden gebruikt in uw organisatie die u wilt beveiligen.
- Analyseer deze lijst met apps om de sets met beleidsregels te bepalen die de juiste beschermingsniveaus bieden.

  U moet voor elke app geen afzonderlijke sets beleidsregels maken, omdat het beheer ervan lastig kan worden. Microsoft raadt u aan uw apps met dezelfde beveiligingsvereisten voor dezelfde gebruikers te groepeert.

  U kunt bijvoorbeeld één set beleidsregels hebben met alle Microsoft 365-apps voor al uw gebruikers voor basislijnbeveiliging en een tweede set beleidsregels voor alle gevoelige apps, zoals de beleidsregels die worden gebruikt door personeelszaken of financiële afdelingen, en deze toepassen op die groepen.

Nadat u de set beleidsregels hebt bepaald voor de apps die u wilt beveiligen, rolt u het beleid stapsgewijs uit voor uw gebruikers, met problemen die daarbij worden aangepakt.

Configureer bijvoorbeeld het beleid dat wordt gebruikt voor al uw Microsoft 365-apps voor alleen Exchange Online, met de aanvullende wijzigingen voor Exchange. Rol dit beleid uit naar uw gebruikers en werk eventuele problemen af. Voeg vervolgens Teams met de aanvullende wijzigingen toe en rol dit uit voor uw gebruikers. Voeg vervolgens SharePoint toe met de aanvullende wijzigingen. Ga verder met het toevoegen van de rest van uw apps totdat u vol vertrouwen dit basislijnbeleid kunt configureren voor alle Microsoft 365-apps.

Voor gevoelige apps kunt u ook de set beleidsregels maken en één app tegelijk toevoegen en eventuele problemen oplossen totdat ze zijn opgenomen in de beleidsset voor gevoelige apps.

Microsoft raadt u aan geen beleidssets te maken die van toepassing zijn op alle apps, omdat dit tot bepaalde onbedoelde configuraties kan leiden. Beleid dat alle apps blokkeert, kan bijvoorbeeld uw beheerders de Azure Portal blokkeren en uitsluitingen kunnen niet worden geconfigureerd voor belangrijke eindpunten, zoals Microsoft Graph.

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Stappen voor het configureren van identiteits- en apparaattoegang

![Stappen voor het configureren van identiteits- en apparaattoegang.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Vereiste identiteitsfuncties en hun instellingen configureren.
2. Configureer het algemene identiteitsbeleid en toegang tot beleidsregels voor voorwaardelijke toegang.
3. Configureer beleidsregels voor voorwaardelijke toegang voor gasten en externe gebruikers.
4. Configureer beleidsregels voor voorwaardelijke toegang voor Microsoft 365-cloud-apps zoals Microsoft Teams, Exchange Online en SharePoint.

Nadat u identiteits- en apparaattoegang hebt geconfigureerd, bekijkt u de implementatiehandleiding voor [de Azure AD-functie](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) voor een gefaseeerde controlelijst met aanvullende functies die u kunt overwegen en Azure AD-identiteitsbeheer voor het beveiligen, controleren en controleren van toegang. [](https://docs.microsoft.com/azure/active-directory/governance/)

## <a name="next-step"></a>Volgende stap

[Vereiste werkzaamheden voor het implementeren van identiteits- en apparaattoegangsbeleid](identity-access-prerequisites.md)
