---
title: Configuraties voor identiteits-en Apparaattoegang-Microsoft 365 for Enterprise
description: Beschrijving van Microsoft-aanbevelingen en basisconcepten voor het implementeren van beveiligde e-mail, documenten en het configureren van beveiligde e-mail, documenten en apps.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
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
ms.openlocfilehash: e76ed8869f2e3bc3198eeff6dc4fcec777d0ce26
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898162"
---
# <a name="identity-and-device-access-configurations"></a>Configuratie van identiteiten en apparaattoegang

In deze reeks artikelen wordt uitgelegd hoe u veilige toegang kunt krijgen tot cloudservices via Enterprise Mobility + Security (EMS)-producten door een aanbevolen omgeving en configuratie te implementeren, waaronder een vooraf ingestelde verzameling beleidsregels voor voorwaardelijke toegang en gerelateerde mogelijkheden. EMS is een kernonderdeel van Microsoft 365. U kunt deze richtlijnen gebruiken om de toegang te beschermen tot alle services die zijn geïntegreerd met Azure Active Directory, waaronder Microsoft 365-Services, andere SaaS-Services en on-premises toepassingen die zijn gepubliceerd met de Azure AD-toepassings proxy. 

Deze aanbevelingen worden afgestemd op de Microsoft Secure Score en de [Score Score in azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score), en zal deze scores voor uw organisatie verhogen. Met deze aanbevelingen kunt u ook deze [vijf stappen uitvoeren om uw identiteits infrastructuur te beveiligen](https://docs.microsoft.com/azure/security/azure-ad-secure-steps). 

Microsoft begrijpt dat sommige organisaties unieke omgevings eisen of complexe factoren hebben. Als u een van deze organisaties bent, gebruik dan deze aanbevelingen als uitgangspunt. De meeste organisaties kunnen deze aanbevelingen evenwel implementeren. 

## <a name="intended-audience"></a>Doelgroep

Deze aanbevelingen zijn bedoeld voor Enterprise Architects en IT-professionals die bekend zijn met [Office 365](https://docs.microsoft.com/microsoft-365/admin) en [Microsoft Enterprise Mobility + Security](https://microsoft.com/ems), waaronder, onder andere, Azure Active Directory (identiteit), Microsoft intune (Apparaatbeheer) en Azure Information Protection (gegevensbescherming).

### <a name="customer-environment"></a>Klant omgeving

De aanbevolen beleidsregels gelden voor Enterprise-organisaties die zowel in de Microsoft-Cloud werken en voor klanten met een hybride infrastructuur (zowel on-premises als de Microsoft-Cloud geïmplementeerd).

Veel van de geboden aanbevelingen zijn afhankelijk van de services die alleen beschikbaar zijn met een licentie voor Enterprise Mobility + Security (EMS) E5. De gepresenteerde aanbevelingen zijn de volledige vereisten voor EMS E5-licentie.

Voor organisaties die geen Enterprise Mobility + beveiligings-E5-licenties hebben, adviseert Microsoft u ten minste de functies van Azure AD basisbescherming voor basistaken uit te voeren die deel uitmaken van alle abonnementen. Meer informatie vindt u in het artikel over de [basislijn beveiliging](/azure/active-directory/active-directory-conditional-access-baseline-protection)in de Azure AD-bibliotheek.

### <a name="caveats"></a>Voorbehoud

Uw organisatie kan onderworpen zijn aan wettelijke of andere nalevingsvereisten, waaronder specifieke aanbevelingen waarbij u beleidsregels moet toepassen die afwijken van deze aanbevolen configuraties. Deze configuraties bevelen gebruiks besturingselementen voor voor gebruik die niet historisch beschikbaar waren. We raden u aan deze besturingselementen te onderscheiden omdat ze een evenwicht tussen beveiliging en productiviteit aangeven.  

We hebben ons de beste account voor een grote verscheidenheid aan de beschermings vereisten voor de organisatie, maar we kunnen niet op de hoogte worden gesteld van alle mogelijke eisen of voor alle unieke aspecten van uw organisatie.

## <a name="three-tiers-of-protection"></a>Drie niveaus van bescherming

De meeste organisaties hebben specifieke vereisten inzake beveiliging en gegevensbescherming. Deze vereisten hangen af van het sector segment en van functie functies binnen organisaties. Voor uw wettelijke afdeling en beheerders zijn mogelijk extra beveiligings-en informatie beschermingsfuncties nodig voor de e-mail correspondentie die niet is vereist voor andere gebruikers van de Business Unit. 

Elke bedrijfstak heeft ook een eigen set gespecialiseerde voorschriften. In plaats van een lijst te maken met alle mogelijke beveiligingsopties of een aanbevelingen per sector segment of functie, zijn er aanbevelingen voor drie verschillende niveaus van beveiliging en bescherming die kunnen worden toegepast op basis van de granulatie van uw behoeften.

- **Basislijn beveiliging**: u wordt aangeraden een minimum standaard te creëren voor het beschermen van gegevens, evenals de identiteiten en apparaten die toegang hebben tot uw gegevens. U kunt deze aanbevelingen volgen om krachtige standaardbeveiliging te bieden die voldoet aan de behoeften van vele organisaties.
- **Gevoelige beveiliging**: sommige klanten hebben een subset van gegevens die op een hoger niveau moeten worden beveiligd, of alle gegevens moeten worden beveiligd op een hoger niveau. U kunt betere beveiliging toepassen op alle of specifieke gegevenssets in uw Microsoft 365-omgeving. U wordt aangeraden identiteiten en apparaten te beschermen die toegang hebben tot gevoelige gegevens met vergelijkbare beveiligingsniveaus.  
- **Zeer gereguleerd**: sommige organisaties hebben mogelijk een kleine hoeveelheid gegevens die in hoge mate is geclassificeerd, dat wil zeggen handelsgeheimen of een gereguleerde gegevens. Microsoft biedt mogelijkheden om organisaties te helpen aan deze vereisten te voldoen, waaronder extra bescherming voor identiteiten en apparaten.

![Beveiligings kegel: alle klanten > sommige klanten > specifieke klanten. Uitgebreide toepassing voor een specifieke toepassing](../media/M365-idquality-threetiers.png)

In deze richtlijnen wordt uitgelegd hoe u beveiliging voor identiteiten en apparaten kunt implementeren voor elk van deze beveiligingsniveaus. U kunt deze richtlijnen gebruiken als uitgangspunt voor uw organisatie en de beleidsregels aanpassen zodat ze voldoen aan de specifieke vereisten van uw organisatie.

Het is belangrijk dat u een consistent beveiligingsniveau gebruikt voor uw gegevens, identiteiten en apparaten. Als u bijvoorbeeld deze richtlijnen implementeert, moet u ervoor zorgen dat u uw gegevens beveiligt tegen vergelijkbare niveaus. 

De **identiteit en beveiliging van Office 365** Architecture-model laat u zien welke mogelijkheden vergelijkbaar zijn.

![Miniatuur van poster en beveiliging van identiteit en apparaat voor Office 365](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF-bestand](https://go.microsoft.com/fwlink/p/?linkid=841656)  |  [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657)  |  [Meer talen](https://www.microsoft.com/download/details.aspx?id=55032)

Zie ook de oplossing [gegevensbescherming implementeren voor data privacy Regulation](../solutions/information-protection-deploy.md) voor informatie over de bescherming van informatie die is opgeslagen in microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Beveiliging en productiviteits commerciële commerciële afschrijving

Voor de implementatie van een beveiligingsstrategie zijn commerciële zaken tussen beveiliging en productiviteit vereist. Het is handig om te bepalen hoe elke beslissing van invloed is op het saldo van beveiliging, functionaliteit en gebruiksgemak.

![Beveiligings Triad Balancing beveiliging, functionaliteit en gebruiksgemak.](../media/policies-configurations/security-triad.png)

De verstrekte aanbevelingen zijn gebaseerd op de volgende beginselen:

- Ken uw doelgroep en Wees flexibel aan de vereisten voor beveiliging en functionele.
- Pas een beveiligingsbeleid toe op tijd en zorg ervoor dat het zinvol is.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Services en concepten voor de bescherming van identiteit en beveiliging van apparaten

Microsoft 365 voor Enterprise is ontworpen voor grote organisaties en bevat Office 365 Enterprise, Windows 10 Enterprise en Enterprise Mobility + Security (EMS), zodat iedereen veilig kan samenwerken.

In deze sectie wordt een overzicht gegeven van de services en functies van Microsoft 365 die belangrijk zijn voor identiteits-en Apparaattoegang.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD biedt een volledige suite met mogelijkheden voor identiteitsbeheer. Voor de toegang tot Access is het raadzaam de volgende mogelijkheden te gebruiken:

- **[Selfservice voor wachtwoordherstel (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: laat uw gebruikers hun wachtwoord veilig opnieuw instellen en zonder dat de beheerder van de beheerder een verificatie biedt van meerdere verificatiemethoden die door de beheerder kunnen worden beheerd.

- **[Multi-factor Authentication (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)**: voor MFA moeten gebruikers twee soorten verificatie bieden, zoals een gebruikerswachtwoord plus een melding van de Microsoft Authenticator-app of een telefoongesprek. MFA reduceert sterk het risico dat een gestolen identiteit kan worden gebruikt voor toegang tot uw omgeving.

- **[Voorwaardelijke toegang](/azure/active-directory/conditional-access/overview)**: Azure AD evalueert de voorwaarden van de gebruikersaanmelding en gebruikt regels voor voorwaardelijke toegang die u hebt gemaakt om toegang te geven. In deze richtlijnen wordt uitgelegd hoe u een voorwaardelijk toegangsbeleid moet maken om de naleving van een apparaat te vereisen voor toegang tot gevoelige gegevens. Hierdoor wordt het risico dat een hacker met een gestolen identiteit toegang heeft tot uw gevoelige gegevens, sterk beperkt. De bescherming beschermt ook gevoelige informatie op de apparaten, omdat de apparaten voldoen aan specifieke vereisten voor de gezondheid en beveiliging.

- **[Azure ad-groepen](/azure/active-directory/fundamentals/active-directory-manage-groups)**: regels voor voorwaardelijke toegang, Apparaatbeheer met intune en zelfs machtigingen voor bestanden en sites in uw organisatie, zijn afhankelijk van toewijzingen aan gebruikers-en/of Azure ad-groepen. We raden u aan om Azure AD-groepen te maken die overeenkomen met het niveau van bescherming dat u implementeert. Uw personeelsleden hebben bijvoorbeeld waarschijnlijk een hogere waarde voor de doelwit van hackers. Daarom is het handig om deze werknemers toe te wijzen aan een Azure AD-groep en deze groep toe te wijzen aan regels voor voorwaardelijke toegang en andere beleidsregels die een hoger beschermingsniveau voor Access afdwingen.

- **[Apparaatregistratie](/azure/active-directory/devices/overview)**: u registreert een apparaat in azure AD om een identiteit aan het apparaat te geven. Deze identiteit wordt gebruikt om het apparaat te verifiëren wanneer een gebruiker zich aanmeldt en voorwaardelijke toegangsregels toe te passen die met een domein of compatibele Pc's zijn vereist. Voor deze richtlijnen gebruiken we apparaatregistratie om automatisch aan het domein gekoppelde Windows-computers te registreren. Apparaatregistratie is een vereiste voor het beheren van apparaten met intune. 

- **[Azure AD-identiteitsbeveiliging](/azure/active-directory/identity-protection/overview)**: Azure AD-identiteitsbeveiliging biedt u de mogelijkheid om mogelijke problemen op te sporen die van invloed zijn op de identiteiten van uw organisatie en het geautomatiseerde herstelbeleid te configureren voor slecht, gemiddeld en hoog aanmeldingen en gebruikers risico. Deze richtlijnen zijn van toepassing op het toepassen van regels voor voorwaardelijke toegang voor verificatie met meerdere factoren. Deze richtlijnen bestaan ook uit een beleid voor voorwaardelijke toegang waarvoor gebruikers hun wachtwoord moeten wijzigen als er High Risk-activiteiten worden gedetecteerd voor hun account.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) is de service voor het beheer van mobiele apparaten met de cloud van Microsoft. Met deze richtlijnen wordt het Apparaatbeheer voor Windows-Pc's met intune aanbevolen en worden de configuraties voor nalevingsbeleid aanbevolen. InTune Hiermee bepaalt u of de apparaten compatibel zijn en worden deze gegevens naar Azure AD verzonden voor gebruik wanneer u voorwaardelijke toegangsbeleid toepast.

#### <a name="intune-app-protection"></a>InTune-app-beveiliging

Met behulp van [intune-app-beveiligings](https://docs.microsoft.com/intune/app-protection-policy) beleid kunt u de gegevens van uw organisatie beschermen in mobiele apps, met of zonder dat u apparaten registreert bij beheer. InTune helpt de informatie te beschermen en te zorgen dat uw werknemers nog steeds productief zijn en gegevensverlies kunnen voorkomen. Als u beleidsregels op het niveau van de app implementeert, kunt u de toegang tot bedrijfsbronnen beperken en de gegevens in het beheer van uw IT-afdeling bewaren.

In deze richtlijnen wordt uitgelegd hoe u aanbevolen beleidsregels maakt om het gebruik van goedgekeurde apps af te dwingen en om te bepalen hoe deze apps kunnen worden gebruikt met uw zakelijke gegevens.

### <a name="microsoft-365"></a>Microsoft 365

In deze richtlijnen wordt uitgelegd hoe u een set beleidsregels implementeert voor de toegang tot Office 365, waaronder Exchange Online, SharePoint Online en OneDrive voor bedrijven. U wordt ook aangeraden om dit beleid te implementeren, maar u kunt ook het beschermingsniveau voor uw Tenant verhogen met behulp van de volgende bronnen:

- [Uw Tenant configureren voor een betere beveiliging](https://docs.microsoft.com/microsoft-365/security/office-365-security/tenant-wide-setup-for-increased-security): deze aanbevelingen gelden voor de basislijn beveiliging voor uw Tenant.
- [Microsoft 365-beveiligingsschema: de belangrijkste punten voor de eerste 30 dagen, 90 dagen en](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)meer: deze aanbevelingen omvatten logboekregistratie, Data Governance, beheerderstoegang en beveiliging van bedreigingen.


### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10- en Microsoft 365-apps voor ondernemingen

Windows 10 en Microsoft 365-apps voor Enterprise is de aanbevolen clientomgeving voor Pc's. U wordt aangeraden Windows 10 te maken als Azure, zodat de soepelste ervaring van zowel on-premises als Azure AD kan worden geconstrueerd. Windows 10 omvat ook geavanceerde beveiligingsfuncties die kunnen worden beheerd via intune. Microsoft 365-apps voor Enterprise omvat de nieuwste versies van Office-toepassingen. Dit maakt gebruik van moderne verificatie, wat veiliger is en een vereiste voor voorwaardelijke toegang. Deze apps zijn ook uitgebreid met uitgebreide beveiligings-en compliance-tools.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>De mogelijkheden van deze functies op de drie niveaus van bescherming toepassen

De volgende tabel bevat een overzicht van de aanbevelingen voor het gebruik van deze mogelijkheden over de drie niveaus van bescherming.

|Beveiligingsmechanisme|Basislijn|Gevoelig|Sterk gereglementeerd|
|:-------------------|:-------|:--------|:---------------|
|**MFA afdwingen**|Bij normaal of hoger risico voor aanmelding|Met een laag of hoger aanmeldings risico|Voor alle nieuwe sessies|
|**Wachtwoordwijziging afdwingen**|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|
|**InTune-toepassingsbeveiliging afdwingen**|Ja|Ja|Ja|
|**InTune-inschrijving afdwingen (COD)**|U moet een compatibele of domeincomputer installeren, maar BYOD-telefoons en-tablets toestaan|Een compatibel of domein bijgevoegd apparaat vereisen|Een compatibel of domein bijgevoegd apparaat vereisen|

## <a name="device-ownership"></a>Eigendom van het apparaat

De bovenstaande tabel weerspiegelt de trend voor veel organisaties voor de ondersteuning van een combinatie van bedrijfseigendoms apparaten, alsook persoonlijke of persoonlijke apparaten (BYODs), zodat de mobiele productiviteit voor de personeelsleden wordt ingeschakeld. Beleidsregels voor het intune-app-beveiliging zorgen ervoor dat e-mailberichten in exfiltrating worden beveiligd vanuit de mobiele Outlook-app en andere Office Mobile-apps, zowel op bedrijfsapparaten als in BYODs.  

U wordt aangeraden om de bedrijfseigen apparatuur te beheren via intune of domein, zodat u extra bescherming en controle kunt toepassen. Afhankelijk van de beschikbaarheid van gegevens kan uw organisatie er ook voor kiezen om BYODs niet toe te staan voor specifieke gebruikersnamen of bepaalde apps.

## <a name="next-steps"></a>Volgende stappen

[Vereisten voor het implementeren van identiteits-en Apparaattoegang](identity-access-prerequisites.md)
