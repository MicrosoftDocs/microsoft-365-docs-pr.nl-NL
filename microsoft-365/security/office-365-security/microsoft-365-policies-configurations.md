---
title: Configuraties voor identiteits- en apparaattoegang - Microsoft 365 voor bedrijven
description: Beschrijft microsoft-aanbevelingen en kernconcepten voor het implementeren van veilige e-mail, documenten en apps-beleid en -configuraties.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 5d8d9893da69da9f08666f0468b8f185261c36f4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924082"
---
# <a name="identity-and-device-access-configurations"></a>Configuratie van identiteiten en apparaattoegang

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)

De moderne beveiligingsperimeter van uw organisatie gaat nu verder dan uw netwerk, zodat gebruikers toegang hebben tot cloud-apps vanaf elke locatie met verschillende apparaten. Uw beveiligingsinfrastructuur moet bepalen of een bepaald toegangsverzoek moet worden verleend en onder welke voorwaarden.

Deze bepaling moet zijn gebaseerd op het gebruikersaccount van de aanmelding, het apparaat dat wordt gebruikt, de app die de gebruiker gebruikt voor toegang, de locatie waaruit de toegangsaanvraag wordt gedaan en een beoordeling van het risico van de aanvraag. Op deze manier zorgt u ervoor dat alleen goedgekeurde gebruikers en apparaten toegang hebben tot uw belangrijke bronnen.

Deze reeks artikelen beschrijft een set vereistenconfiguraties voor identiteits- en apparaattoegang en een set Azure Active Directory (Azure AD) Voorwaardelijke toegang, Microsoft Intune en andere beleidsregels voor het beveiligen van toegang tot Microsoft 365 voor zakelijke cloud-apps en -services, andere SaaS-services en on-premises toepassingen die zijn gepubliceerd met Azure AD Application Proxy.

Identiteits- en apparaattoegangsinstellingen en -beleid worden aanbevolen in drie lagen: basislijnbeveiliging, gevoelige beveiliging en beveiliging voor omgevingen met sterk gereguleerde of geclassificeerde gegevens. Deze lagen en de bijbehorende configuraties bieden een consistent beveiligingsniveau van uw gegevens, identiteiten en apparaten.

Deze mogelijkheden en hun aanbevelingen:

- Worden ondersteund in Microsoft 365 E3 en Microsoft 365 E5.
- Worden uitgelijnd [met Microsoft Secure Score](../mtp/microsoft-secure-score.md) en [identiteitsscore in Azure AD](/azure/active-directory/fundamentals/identity-secure-score)en verhogen deze scores voor uw organisatie.
- Helpt u bij het implementeren van deze [vijf stappen voor het beveiligen van uw identiteitsinfrastructuur.](/azure/security/azure-ad-secure-steps)

Als uw organisatie unieke omgevingsvereisten of complexiteiten heeft, gebruikt u deze aanbevelingen als uitgangspunt. De meeste organisaties kunnen deze aanbevelingen echter implementeren zoals voorgeschreven.

Bekijk deze video voor een kort overzicht van identiteits- en apparaattoegangsconfiguraties voor Microsoft 365 voor bedrijven.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft verkoopt ook EMS-licenties (Enterprise Mobility+ Security) voor Office 365-abonnementen. EMS E3- en EMS E5-mogelijkheden zijn gelijk aan die in Microsoft 365 E3 en Microsoft 365 E5. Zie [EMS-abonnementen](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) voor de details.

## <a name="intended-audience"></a>Beoogde doelgroep

Deze aanbevelingen zijn bedoeld voor ondernemingsarchitecten en IT-professionals die bekend zijn met microsoft 365 cloudproductiviteits- en beveiligingsservices, waaronder Azure AD (identiteit), Microsoft Intune (apparaatbeheer) en Azure Information Protection (gegevensbescherming).

### <a name="customer-environment"></a>Klantomgeving

Het aanbevolen beleid is van toepassing op ondernemingsorganisaties die zowel volledig in de Microsoft-cloud als voor klanten met een hybride identiteitsinfrastructuur werken. Dit is een on-premises AD DS-forest (Active Directory Domain Services) dat wordt gesynchroniseerd met een Azure AD-tenant.

Veel van de geleverde aanbevelingen zijn afhankelijk van services die alleen beschikbaar zijn met Microsoft 365 E5, Microsoft 365 E3 met de invoeg-, EMS E5- of Azure Premium P2-licenties van Identity & Threat Protection.

Voor organisaties die deze licenties niet hebben, raadt Microsoft u aan op zijn minst beveiligingsinstellingen te implementeren [,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)die zijn opgenomen in alle Microsoft 365-abonnementen.

### <a name="caveats"></a>Voorbehouden

Uw organisatie kan onderhevig zijn aan wettelijke of andere nalevingsvereisten, waaronder specifieke aanbevelingen waarvoor u mogelijk beleid moet toepassen dat afwijkt van deze aanbevolen configuraties. In deze configuraties wordt aanbevolen gebruiksbesturingselementen te gebruiken die niet historisch beschikbaar zijn geweest. We raden deze besturingselementen aan omdat we denken dat deze een evenwicht vertegenwoordigen tussen beveiliging en productiviteit.

We hebben ons best gedaan om rekening te houden met een groot aantal vereisten voor organisatiebeveiliging, maar we kunnen niet alle mogelijke vereisten of voor alle unieke aspecten van uw organisatie verantwoorden.

## <a name="three-tiers-of-protection"></a>Drie beveiligingslagen

De meeste organisaties hebben specifieke vereisten met betrekking tot beveiliging en gegevensbescherming. Deze vereisten variëren per branchesegment en per functie binnen organisaties. Uw juridische afdeling en beheerders hebben bijvoorbeeld extra beveiligings- en informatiebeveiligingsbesturingselementen nodig rond hun e-mailcorrespondentie die niet vereist zijn voor andere bedrijfseenheden.

Elke branche heeft ook een eigen set gespecialiseerde voorschriften. In plaats van een lijst met alle mogelijke beveiligingsopties of een aanbeveling per bedrijfstaksegment of functie, zijn er aanbevelingen gedaan voor drie verschillende beveiligings- en beveiligingslagen die kunnen worden toegepast op basis van de granulariteit van uw behoeften.

- **Basislijnbeveiliging:** U wordt aangeraden een minimumstandaard vast te stellen voor het beveiligen van gegevens, evenals de identiteiten en apparaten die toegang hebben tot uw gegevens. U kunt deze basislijnaanbevelingen volgen om een sterke standaardbeveiliging te bieden die voldoet aan de behoeften van veel organisaties.
- **Gevoelige beveiliging:** Sommige klanten hebben een subset met gegevens die op een hoger niveau moeten worden beveiligd, of ze vereisen mogelijk dat alle gegevens op een hoger niveau worden beveiligd. U kunt meer beveiliging toepassen op alle of specifieke gegevenssets in uw Microsoft 365-omgeving. We raden u aan identiteiten en apparaten te beveiligen die toegang hebben tot gevoelige gegevens met vergelijkbare beveiligingsniveaus.
- **Sterk geregeld:** Sommige organisaties hebben mogelijk een kleine hoeveelheid gegevens die sterk is geclassificeerd, bedrijfsgeheimen vormen of die zijn geregeld. Microsoft biedt mogelijkheden om organisaties te helpen aan deze vereisten te voldoen, waaronder extra beveiliging voor identiteiten en apparaten.

![Beveiligingskegel : alle klanten > sommige klanten > specifieke klanten. Brede toepassing voor specifieke toepassing](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

In deze richtlijnen ziet u hoe u beveiliging voor identiteiten en apparaten implementeert voor elk van deze beveiligingslagen. Gebruik deze richtlijnen als uitgangspunt voor uw organisatie en pas het beleid aan de specifieke vereisten van uw organisatie aan.

Het is belangrijk dat u een consistent beveiligingsniveau gebruikt voor uw gegevens, identiteiten en apparaten. Als u deze richtlijnen bijvoorbeeld implementeert, moet u uw gegevens op vergelijkbare niveaus beveiligen.

De **identiteits- en apparaatbeveiliging voor het Architectuurmodel van Microsoft 365** laat zien welke mogelijkheden vergelijkbaar zijn.

[![Duimafbeelding voor identiteits- en apparaatbeveiliging voor Microsoft 365-poster](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [Weergeven als pdf-bestand](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Downloaden als PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Downloaden als visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Zie ook de oplossing [Voor gegevensbescherming implementeren](../../solutions/information-protection-deploy.md) voor privacyregels voor gegevens om gegevens te beveiligen die zijn opgeslagen in Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Beveiligings- en productiviteitsruilen

Voor het implementeren van een beveiligingsstrategie zijn afwegingen tussen beveiliging en productiviteit vereist. Het is handig om te evalueren hoe elke beslissing van invloed is op de balans tussen beveiliging, functionaliteit en gebruiksgemak.

![Beveiliging triad balanceren beveiliging, functionaliteit en gebruiksgemak.](../../media/microsoft-365-policies-configurations/security-triad.png)

De aanbevelingen zijn gebaseerd op de volgende principes:

- Ken uw gebruikers en wees flexibel met hun beveiligings- en functionele vereisten.
- Pas een beveiligingsbeleid net op tijd toe en zorg ervoor dat het zinvol is.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Services en concepten voor identiteits- en apparaattoegangsbeveiliging

Microsoft 365 voor bedrijven is ontworpen voor grote organisaties om iedereen in staat te stellen creatief te zijn en veilig samen te werken.

In deze sectie vindt u een overzicht van de Microsoft 365-services en -mogelijkheden die belangrijk zijn voor identiteits- en apparaattoegang.

### <a name="azure-ad"></a>Azure AD

Azure AD biedt een volledige suite met mogelijkheden voor identiteitsbeheer. We raden u aan deze mogelijkheden te gebruiken om toegang te beveiligen.

|Functie|Beschrijving|Licenties|
|---|---|---|
|[Meervoudige verificatie (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|Voor MFA moeten gebruikers twee verificatieformulieren opgeven, zoals een gebruikerswachtwoord plus een melding van de Microsoft Authenticator-app of een telefoongesprek. MFA verkleint het risico dat gestolen referenties kunnen worden gebruikt om toegang te krijgen tot uw omgeving. Microsoft 365 gebruikt de Azure AD Multi-Factor Authentication-service voor MFA-aanmeldingen.|Microsoft 365 E3 of E5|
|[Voorwaardelijke toegang](/azure/active-directory/conditional-access/overview)|Azure AD evalueert de voorwaarden van de aanmelding van de gebruiker en gebruikt beleid voor voorwaardelijke toegang om de toegestane toegang te bepalen. In deze richtlijnen ziet u bijvoorbeeld hoe u een beleid voor voorwaardelijke toegang kunt maken om apparaat compliance te vereisen voor toegang tot gevoelige gegevens. Hierdoor wordt het risico aanzienlijk verkleind dat een hacker met een eigen apparaat en gestolen referenties toegang heeft tot uw gevoelige gegevens. Het beschermt ook gevoelige gegevens op de apparaten, omdat de apparaten moeten voldoen aan specifieke vereisten voor gezondheid en beveiliging.|Microsoft 365 E3 of E5|
|[Azure AD-groepen](/azure/active-directory/fundamentals/active-directory-manage-groups)|Beleid voor voorwaardelijke toegang, apparaatbeheer met Intune en zelfs machtigingen voor bestanden en sites in uw organisatie zijn afhankelijk van de toewijzing aan gebruikersaccounts of Azure AD-groepen. U wordt aangeraden Azure AD-groepen te maken die overeenkomen met de beveiligingsniveaus die u implementeert. Uw leidinggevenden zijn bijvoorbeeld waarschijnlijk hogere doelen voor hackers. Daarom is het zinvol om de gebruikersaccounts van deze werknemers toe te voegen aan een Azure AD-groep en deze groep toe te wijzen aan beleidsregels voor voorwaardelijke toegang en andere beleidsregels die een hoger beschermingsniveau voor toegang afdwingen.|Microsoft 365 E3 of E5|
|[Apparaatinschrijving](/azure/active-directory/devices/overview)|U meldt een apparaat aan bij Azure AD om een identiteit voor het apparaat te maken. Deze identiteit wordt gebruikt om het apparaat te verifiëren wanneer een gebruiker zich aan meldt en om beleid voor voorwaardelijke toegang toe te passen waarvoor domeingevoegde of compatibele pc's zijn vereist. Voor deze richtlijnen gebruiken we apparaatinschrijving om automatisch domeingevoegde Windows-computers in te schrijven. Apparaatinschrijving is een vereiste voor het beheren van apparaten met Intune.|Microsoft 365 E3 of E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Hiermee kunt u mogelijke beveiligingslekken opsporen die van invloed zijn op de identiteiten van uw organisatie en het geautomatiseerde herstelbeleid configureren op laag, gemiddeld en hoog aanmeldingsrisico en gebruikersrisico. Deze richtlijnen zijn gebaseerd op deze risicoanalyse om beleidsregels voor voorwaardelijke toegang toe te passen voor meervoudige verificatie. Deze richtlijn bevat ook een beleid voor Voorwaardelijke toegang, dat vereist dat gebruikers hun wachtwoord wijzigen als er activiteit met een hoog risico wordt gedetecteerd voor hun account.|Microsoft 365 E5, Microsoft 365 E3 met de identity & Threat Protection-invoeg-, EMS E5- of Azure Premium P2-licenties|
|[Selfservice password reset (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Sta uw gebruikers toe hun wachtwoorden veilig en zonder tussenkomst van de helpdesk opnieuw in te stellen door verificatie te bieden van meerdere verificatiemethoden die de beheerder kan beheren.|Microsoft 365 E3 of E5|
|[Azure AD-wachtwoordbeveiliging](/azure/active-directory/authentication/concept-password-ban-bad)|Detecteer en blokkeer bekende zwakke wachtwoorden en hun varianten en aanvullende zwakke termen die specifiek zijn voor uw organisatie. Standaardlijsten met verboden wachtwoorden worden automatisch toegepast op alle gebruikers in een Azure AD-tenant. U kunt aanvullende vermeldingen definiëren in een aangepaste lijst met geblokkeerde wachtwoorden. Als gebruikers hun wachtwoord wijzigen of opnieuw instellen, worden deze verboden wachtwoordlijsten ingeschakeld om het gebruik van sterke wachtwoorden af te dwingen.|Microsoft 365 E3 of E5|
|

Hier volgen de onderdelen van identiteits- en apparaattoegang, waaronder Intune- en Azure AD-objecten, instellingen en subservices.

![Onderdelen van identiteits- en apparaattoegang](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune) is de cloudservice voor mobiel apparaatbeheer van Microsoft. Deze richtlijnen raden apparaatbeheer van Windows-pc's met Intune aan en raadt configuraties voor apparaat compliancebeleid aan. Intune bepaalt of apparaten compatibel zijn en verzendt deze gegevens naar Azure AD voor gebruik bij het toepassen van beleidsregels voor Voorwaardelijke toegang.

#### <a name="intune-app-protection"></a>Intune-appbeveiliging

[Intune app protection](/intune/app-protection-policy) policies can be used to protect your organization's data in mobile apps, with or without enrolling devices into management. Intune helpt gegevens te beveiligen, ervoor te zorgen dat uw werknemers nog steeds productief kunnen zijn en gegevensverlies voorkomen. Door beleid op app-niveau te implementeren, kunt u de toegang tot bedrijfsbronnen beperken en gegevens binnen het beheer van uw IT-afdeling houden.

In deze richtlijnen ziet u hoe u aanbevolen beleid kunt maken om het gebruik van goedgekeurde apps af te dwingen en om te bepalen hoe deze apps kunnen worden gebruikt met uw zakelijke gegevens.

### <a name="microsoft-365"></a>Microsoft 365

In deze richtlijnen ziet u hoe u een set beleidsregels implementeert om de toegang tot Microsoft 365-cloudservices te beschermen, waaronder Microsoft Teams, Exchange Online, SharePoint Online en OneDrive voor Bedrijven. Naast het implementeren van dit beleid, raden we u ook aan het beschermingsniveau voor uw tenant te verhogen met behulp van deze bronnen:

- [Je tenant configureren voor betere beveiliging](tenant-wide-setup-for-increased-security.md)

  Aanbevelingen die van toepassing zijn op basislijnbeveiliging voor uw tenant.

- [Routekaart voor beveiliging: topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna](security-roadmap.md)

  Aanbevelingen die logboekregistratie, gegevensbeheer, beheerderstoegang en bedreigingsbeveiliging omvatten.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10- en Microsoft 365-apps voor ondernemingen

Windows 10 met Microsoft 365 Apps voor bedrijven is de aanbevolen clientomgeving voor pc's. We raden Windows 10 aan omdat Azure is ontworpen om de soepelste ervaring te bieden die mogelijk is voor zowel on-premises als Azure AD. Windows 10 bevat ook geavanceerde beveiligingsmogelijkheden die kunnen worden beheerd via Intune. Microsoft 365 Apps voor bedrijven bevat de nieuwste versies van Office-toepassingen. Deze maken gebruik van moderne verificatie, die veiliger is en een vereiste is voor Voorwaardelijke toegang. Deze apps bevatten ook verbeterde beveiligings- en compliancehulpmiddelen.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Deze mogelijkheden toepassen op de drie beveiligingslagen

In de volgende tabel worden onze aanbevelingen voor het gebruik van deze mogelijkheden in de drie beveiligingslagen samengevat.

|Beveiligingsmechanisme|Basislijn|Gevoelig|Sterk gereglementeerd|
|---|---|---|---|
|**MFA afdwingen**|Bij middelgroot of hoger aanmeldingsrisico|Bij laag of hoger aanmeldingsrisico|Op alle nieuwe sessies|
|**Wachtwoordwijziging afdwingen**|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|
|**Intune-toepassingsbeveiliging afdwingen**|Ja|Ja|Ja|
|**Intune-inschrijving afdwingen voor apparaat dat eigendom is van een organisatie**|Een compatibele of domeingevoegde pc vereisen, maar bring-your-own apparaten (BYOD) telefoons en tablets toestaan|Een compatibel of domeingevoegd apparaat vereisen|Een compatibel of domeingevoegd apparaat vereisen|
|

## <a name="device-ownership"></a>Eigendom van apparaat

De bovenstaande tabel weerspiegelt de trend voor veel organisaties om een combinatie van apparaten die eigendom zijn van de organisatie te ondersteunen, evenals persoonlijke of BYOD's om mobiele productiviteit voor het hele personeel mogelijk te maken. Intune-beleid voor app-beveiliging zorgt ervoor dat e-mail wordt beveiligd tegen exfiltrating vanuit de mobiele Outlook-app en andere mobiele Office-apps, op zowel apparaten die eigendom zijn van de organisatie als BYOD's.

Het is raadzaam apparaten die eigendom zijn van de organisatie te beheren door Intune of domeingevoegd om extra beveiliging en controle toe te passen. Afhankelijk van de gegevensgevoeligheid kan uw organisatie ervoor kiezen om GEEN BYOD's toe te staan voor specifieke gebruikerspopulaties of specifieke apps.

## <a name="deployment-and-your-apps"></a>Implementatie en uw apps

Voordat u de configuratie voor identiteits- en apparaattoegang configureert en uitrolt voor uw in Azure AD geïntegreerde apps, moet u het volgende doen:

- Bepaal welke apps worden gebruikt in uw organisatie die u wilt beveiligen.
- Analyseer deze lijst met apps om de sets beleidsregels te bepalen die de juiste beveiligingsniveaus bieden.

  U moet geen afzonderlijke sets beleid maken voor elk van de apps, omdat het beheer ervan lastig kan worden. Microsoft raadt u aan uw apps te groepeert met dezelfde beveiligingsvereisten voor dezelfde gebruikers.

  U kunt bijvoorbeeld één set beleidsregels hebben met alle Microsoft 365-apps voor al uw gebruikers voor basislijnbeveiliging en een tweede set beleidsregels voor alle gevoelige apps, zoals die die worden gebruikt door personeelszaken of financiële afdelingen, en deze toepassen op die groepen.

Nadat u de set beleidsregels hebt bepaald voor de apps die u wilt beveiligen, rolt u het beleid stapsgewijs uit naar uw gebruikers, zodat u problemen onderweg kunt oplossen.

Configureer bijvoorbeeld het beleid dat wordt gebruikt voor al uw Microsoft 365-apps voor alleen Exchange Online met de extra wijzigingen voor Exchange. Rol dit beleid uit naar uw gebruikers en werk eventuele problemen af. Voeg vervolgens Teams toe met de extra wijzigingen en rol deze uit naar uw gebruikers. Voeg vervolgens SharePoint toe met de aanvullende wijzigingen. Blijf de rest van uw apps toevoegen totdat u deze basislijnbeleid kunt configureren met alle Microsoft 365-apps.

Op dezelfde manier maakt u voor uw gevoelige apps de set beleidsregels en voegt u één app tegelijk toe en kunt u eventuele problemen oplossen totdat ze allemaal zijn opgenomen in de beleidsset voor gevoelige apps.

Microsoft raadt u aan geen beleidssets te maken die van toepassing zijn op alle apps, omdat dit kan leiden tot bepaalde onbedoelde configuraties. Beleidsregels die bijvoorbeeld alle apps blokkeren, kunnen uw beheerders uitsluiten van de Azure-portal en uitsluitingen kunnen niet worden geconfigureerd voor belangrijke eindpunten, zoals Microsoft Graph.

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Stappen in het proces voor het configureren van identiteits- en apparaattoegang

![Stappen voor het configureren van identiteits- en apparaattoegang.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Vereiste identiteitsfuncties en hun instellingen configureren.
2. Configureer het algemene beleid voor identiteit en toegang tot voorwaardelijke toegang.
3. Beleid voor voorwaardelijke toegang configureren voor gast- en externe gebruikers.
4. Beleid voor voorwaardelijke toegang configureren voor Cloud-apps van Microsoft 365, zoals Microsoft Teams, Exchange Online en SharePoint.

Nadat u identiteits- en apparaattoegang hebt geconfigureerd, bekijkt u de azure AD-functieimplementatiehandleiding voor een gefaseerd controlelijst met aanvullende functies die u moet overwegen en [Azure AD Identity Governance](/azure/active-directory/governance/) om toegang te beveiligen, te controleren en te controleren. [](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2)

## <a name="next-step"></a>Volgende stap

[Vereiste werk voor het implementeren van beleidsregels voor identiteits- en apparaattoegang](identity-access-prerequisites.md)