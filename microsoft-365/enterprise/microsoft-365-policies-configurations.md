---
title: Configuraties voor identiteits- en apparaattoegang - Microsoft 365 Enterprise
description: Beschrijft Microsoft-aanbevelingen en kernconcepten voor het implementeren van veilige e-mail- en documenten- en appsbeleid en -configuraties.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
ms.openlocfilehash: 1a16fa9a26ab20065d213857614b06fdde6c0af1
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530269"
---
# <a name="identity-and-device-access-configurations"></a>Configuratie van identiteiten en apparaattoegang

In deze reeks artikelen wordt beschreven hoe u veilige toegang tot cloudservices configureren via Ems-producten (Enterprise Mobility + Security) door een aanbevolen omgeving en configuratie te implementeren, inclusief een voorgeschreven set beleid voor voorwaardelijke toegang en gerelateerde mogelijkheden. EMS is een kernonderdeel van Microsoft 365. U deze richtlijnen gebruiken om de toegang te beschermen tot alle services die zijn geïntegreerd met Azure Active Directory, waaronder Microsoft 365-services, andere SaaS-services en on-premises toepassingen die zijn gepubliceerd met Azure AD Application Proxy. 

Deze aanbevelingen zijn afgestemd op microsoft secure score en [identiteitsscore in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)en verhogen deze scores voor uw organisatie. Deze aanbevelingen helpen u ook bij de implementatie van deze [vijf stappen om uw identiteitsinfrastructuur te beveiligen.](https://docs.microsoft.com/azure/security/azure-ad-secure-steps) 

Microsoft begrijpt dat sommige organisaties unieke omgevingsvereisten of complexiteiten hebben. Als u een van deze organisaties bent, gebruikt u deze aanbevelingen als uitgangspunt. De meeste organisaties kunnen deze aanbevelingen echter uitvoeren zoals voorgeschreven. 

## <a name="intended-audience"></a>Beoogd publiek

Deze aanbevelingen zijn bedoeld voor bedrijfsarchitecten en IT-professionals die bekend zijn met [Office 365](https://docs.microsoft.com/microsoft-365/admin) en [Microsoft Enterprise Mobility + Security](https://microsoft.com/ems), waaronder onder andere Azure Active Directory (identiteit), Microsoft Intune (apparaatbeheer) en Azure Information Protection (gegevensbescherming).

### <a name="customer-environment"></a>Klantomgeving

Het aanbevolen beleid is van toepassing op bedrijfsorganisaties die zowel binnen de Microsoft-cloud als voor klanten met een hybride infrastructuur actief zijn (zowel on-premises als de Microsoft-cloud geïmplementeerd).

Veel van de verstrekte aanbevelingen zijn afhankelijk van services die alleen beschikbaar zijn met Enterprise Mobility + Security (EMS) E5-licenties. Gepresenteerde aanbevelingen nemen volledige EMS E5 licentiemogelijkheden.

Voor organisaties die geen Enterprise Mobility + Security E5-licenties hebben, raadt Microsoft u aan op zijn minst Azure AD-basislijnbeveiligingsmogelijkheden te implementeren die bij alle abonnementen zijn inbegrepen. Meer informatie is te vinden in het artikel [Wat is basislijnbeveiliging](/azure/active-directory/active-directory-conditional-access-baseline-protection)in de Azure AD-bibliotheek.

### <a name="caveats"></a>Waarschuwingen

Uw organisatie kan onderhevig zijn aan wettelijke of andere nalevingsvereisten, waaronder specifieke aanbevelingen die vereisen dat u beleid toepast dat afwijkt van deze aanbevolen configuraties. In deze configuraties worden gebruiksbesturingselementen aanbevolen die in het verleden niet beschikbaar zijn. We raden deze controles aan omdat we geloven dat ze een evenwicht vormen tussen beveiliging en productiviteit.  

We hebben ons best gedaan om rekening te houden met een breed scala aan vereisten voor organisatiebescherming, maar we kunnen niet alle mogelijke vereisten of alle unieke aspecten van uw organisatie verantwoorden.

## <a name="three-tiers-of-protection"></a>Drie beschermingsniveaus

De meeste organisaties hebben specifieke eisen op het gebied van beveiliging en gegevensbescherming. Deze eisen verschillen per bedrijfstak en per functie binnen organisaties. Uw juridische afdeling en beheerders kunnen bijvoorbeeld extra besturingselementen voor beveiliging en informatiebeveiliging rond hun e-mailcorrespondentie vereisen die niet vereist zijn voor andere gebruikers van de bedrijfseenheid. 

Elke industrie heeft ook zijn eigen set van gespecialiseerde regelgeving. In plaats van een lijst te geven van alle mogelijke beveiligingsopties of een aanbeveling per bedrijfstaksegment of functie, zijn aanbevelingen verstrekt voor drie verschillende beveiligings- en beveiligingsniveaus die kunnen worden toegepast op basis van de granulariteit van uw behoeften.

- **Basislijnbescherming**: We raden u aan een minimumstandaard vast te stellen voor de bescherming van gegevens, evenals de identiteiten en apparaten die toegang hebben tot uw gegevens. U deze basislijnaanbevelingen volgen om een sterke standaardbescherming te bieden die voldoet aan de behoeften van veel organisaties.
- **Gevoelige bescherming**: Sommige klanten hebben een subset van gegevens die op hogere niveaus moeten worden beschermd, of ze kunnen eisen dat alle gegevens op een hoger niveau worden beschermd. U meer bescherming toepassen op alle of specifieke gegevenssets in uw Microsoft 365-omgeving. We raden u aan identiteiten en apparaten te beschermen die toegang hebben tot gevoelige gegevens met vergelijkbare beveiligingsniveaus.  
- **Sterk gereguleerd**: Sommige organisaties kunnen een kleine hoeveelheid gegevens hebben die sterk is geclassificeerd, bedrijfsgeheimen vormt of gereguleerde gegevens zijn. Microsoft biedt mogelijkheden om organisaties te helpen aan deze vereisten te voldoen, waaronder extra bescherming voor identiteiten en apparaten.

![Beveiligingskegel - Alle klanten > Sommige klanten > specifieke klanten. Brede toepassing op specifieke toepassing](../media/M365-idquality-threetiers.png)

Deze richtlijnen laten u zien hoe u bescherming voor identiteiten en apparaten implementeren voor elk van deze beveiligingsniveaus. Gebruik deze richtlijnen als uitgangspunt voor uw organisatie en pas het beleid aan om aan de specifieke vereisten van uw organisatie te voldoen.

Het is belangrijk dat u een consistent beveiligingsniveau gebruikt voor uw gegevens, identiteiten en apparaten. Als u deze richtlijnen bijvoorbeeld implementeert, moet u uw gegevens op vergelijkbare niveaus beschermen. Deze architectuurmodellen laten zien welke mogelijkheden vergelijkbaar zijn.

**Identiteits- en apparaatbeveiliging voor Office 365**<br/>
![Miniatuur voor poster 'Identiteits- en apparaatbeveiliging voor Office 365'](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656)  |  [Visio Visio](https://go.microsoft.com/fwlink/p/?linkid=841657)  |  [Meer talen](https://www.microsoft.com/download/details.aspx?id=55032)

**File Protection Solutions in Office 365** (Oplossingen voor bestandsbeveiliging in Office 365)<br/>
![Miniatuur voor poster "Oplossingen voor bestandsbeveiliging in Office 365"](../media/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Compromissen op het gebied van beveiliging en productiviteit

Het implementeren van een beveiligingsstrategie vereist compromissen tussen beveiliging en productiviteit. Het is handig om te evalueren hoe elke beslissing de balans van beveiliging, functionaliteit en gebruiksgemak beïnvloedt.

![Beveiliging triade balanceren beveiliging, functionaliteit, en gebruiksgemak.](../media/policies-configurations/security-triad.png)

De aanbevelingen zijn gebaseerd op de volgende beginselen:

- Ken je doelgroep en wees flexibel in hun beveiligings- en functionele vereisten.
- Pas een beveiligingsbeleid net op tijd toe en zorg ervoor dat het zinvol is.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Services en concepten voor bescherming tegen toegang tot identiteit en apparaten

Microsoft 365 Enterprise is ontworpen voor grote organisaties en integreert Office 365 Enterprise, Windows 10 Enterprise en Enterprise Mobility + Security (EMS), om iedereen in staat te stellen creatief te zijn en veilig samen te werken.

In deze sectie vindt u een overzicht van de Microsoft 365-services en -mogelijkheden die belangrijk zijn voor de toegang tot identiteit en apparaten.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD biedt een volledige suite van mogelijkheden voor identiteitsbeheer. Voor het beveiligen van de toegang raden we u aan de volgende mogelijkheden te gebruiken:

- **[Self-service password reset (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: Sta uw gebruikers toe hun wachtwoorden veilig en zonder tussenkomst van de helpdesk te resetten, door verificatie te bieden van meerdere verificatiemethoden die de beheerder kan beheren.

- **[Multi-factor authenticatie (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)**: MFA vereist dat gebruikers twee vormen van verificatie opgeven, zoals een gebruikerswachtwoord plus een melding van de Microsoft Authenticator-app of een telefoongesprek. MFA vermindert het risico dat een gestolen identiteit kan worden gebruikt om toegang te krijgen tot uw omgeving.

- **[Voorwaardelijke toegang](/azure/active-directory/conditional-access/overview)**: Azure AD evalueert de voorwaarden van de aanmelding van de gebruiker en gebruikt beleid voor voorwaardelijke toegang dat u maakt om toegang toe te staan. In deze richtlijnen laten we u bijvoorbeeld zien hoe u een beleid voor voorwaardelijke toegang maken om naleving van apparaten te vereisen voor toegang tot gevoelige gegevens. Dit vermindert sterk het risico dat een hacker met een gestolen identiteit toegang heeft tot uw gevoelige gegevens. Het beschermt ook gevoelige gegevens op de apparaten, omdat de apparaten voldoen aan specifieke eisen voor gezondheid en beveiliging.

- **[Azure AD-groepen](/azure/active-directory/fundamentals/active-directory-manage-groups)**: Regels voor voorwaardelijke toegang, apparaatbeheer met Intune en zelfs machtigingen voor bestanden en sites in uw organisatie, vertrouwen op toewijzing aan gebruikers- en/of Azure AD-groepen. We raden u aan Azure AD-groepen te maken die overeenkomen met de beveiligingsniveaus die u implementeert. Bijvoorbeeld, uw executive personeel zijn waarschijnlijk hogere waarde doelen voor hackers. Daarom is het zinvol om deze werknemers toe te wijzen aan een Azure AD-groep en deze groep toe te wijzen aan beleid voor voorwaardelijke toegang en andere beleidsregels die een hoger beschermingsniveau voor toegang afdwingen.

- **[Apparaatregistratie](/azure/active-directory/devices/overview)**: U registreert een apparaat in Azure AD om een identiteit aan het apparaat te geven. Deze identiteit wordt gebruikt om het apparaat te verifiëren wanneer een gebruiker zich aanmeldt en om voorwaardelijke toegangsregels toe te passen waarvoor domein-joined of compatibele pc's vereist zijn. Voor deze richtlijnen gebruiken we apparaatregistratie om windows-computers die lid zijn van het domein automatisch te registreren. Apparaatregistratie is een voorwaarde voor het beheren van apparaten met Intune. 

- **[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)**: Azure AD Identity Protection stelt u in staat om potentiële kwetsbaarheden die van invloed zijn op de identiteit van uw organisatie te detecteren en geautomatiseerd herstelbeleid te configureren naar een laag, gemiddeld en hoog aanmeldingsrisico en gebruikersrisico. Deze richtlijnen zijn afhankelijk van deze risicobeoordeling om beleid voor voorwaardelijke toegang toe te passen voor meervoudige verificatie. Deze richtlijnen bevatten ook een beleid voor voorwaardelijke toegang waarbij gebruikers hun wachtwoord moeten wijzigen als activiteit met een hoog risico wordt gedetecteerd voor hun account.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) is de cloudgebaseerde service voor het beheer van mobiele apparaten van Microsoft. Deze richtlijnen raden apparaatbeheer van Windows-pc's met Intune aan en beveelt beleidsconfiguraties voor apparaatnaleving aan. Intune bepaalt of apparaten compatibel zijn en stuurt deze gegevens naar Azure AD om te gebruiken bij het toepassen van beleid voor voorwaardelijke toegang.

#### <a name="intune-app-protection"></a>Intune-app-beveiliging

[Het beveiligingsbeleid voor intune-apps](https://docs.microsoft.com/intune/app-protection-policy) kan worden gebruikt om de gegevens van uw organisatie in mobiele apps te beschermen, met of zonder apparaten in te schrijven voor beheer. Intune helpt informatie te beschermen, ervoor te zorgen dat uw medewerkers nog steeds productief kunnen zijn en gegevensverlies te voorkomen. Door beleid op app-niveau te implementeren, u de toegang tot bedrijfsbronnen beperken en gegevens binnen de controle van uw IT-afdeling houden.

In deze richtlijnen ziet u hoe u aanbevolen beleidsregels maakt om het gebruik van goedgekeurde apps af te dwingen en te bepalen hoe deze apps kunnen worden gebruikt met uw bedrijfsgegevens.

### <a name="microsoft-365"></a>Microsoft 365

In deze richtlijnen ziet u hoe u een reeks beleidsregels implementeert om de toegang tot Office 365 te beschermen, waaronder Exchange Online, SharePoint Online en OneDrive voor Bedrijven. Naast het implementeren van dit beleid raden we u ook aan het beschermingsniveau voor uw tenant te verhogen met behulp van deze bronnen:

- [Uw tenant configureren voor meer beveiliging:](https://docs.microsoft.com/microsoft-365/security/office-365-security/tenant-wide-setup-for-increased-security)deze aanbevelingen zijn van toepassing op basislijnbeveiliging voor uw tenant.
- [Microsoft 365-beveiligingsroadmap: de hoogste prioriteiten voor de eerste 30 dagen, 90 dagen en daarna:](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)deze aanbevelingen omvatten logboekregistratie, gegevensbeheer, beheerderstoegang en bedreigingsbeveiliging.


### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10- en Microsoft 365-apps voor ondernemingen

Windows 10 en Microsoft 365 Apps for enterprise is de aanbevolen clientomgeving voor pc's. We raden Windows 10 aan, omdat Azure is ontworpen om de best mogelijke ervaring te bieden voor zowel on-premises als Azure AD. Windows 10 bevat ook geavanceerde beveiligingsmogelijkheden die via Intune kunnen worden beheerd. Microsoft 365 Apps for enterprise bevat de nieuwste versies van Office-toepassingen. Deze maken gebruik van moderne verificatie, die veiliger is en een vereiste voor voorwaardelijke toegang. Deze apps bevatten ook verbeterde beveiligings- en nalevingstools.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Het toepassen van deze mogelijkheden op de drie beschermingsniveaus

In de volgende tabel worden onze aanbevelingen voor het gebruik van deze mogelijkheden in de drie beschermingsniveaus samengevat.

|Beschermingsmechanisme|Basislijn|Gevoelig|Sterk gereglementeerd|
|:-------------------|:-------|:--------|:---------------|
|**MFA afdwingen**|Op gemiddeld of hoger aanmeldingsrisico|Op laag of boven aanmeldingsrisico|Op alle nieuwe sessies|
|**Wachtwoordwijziging afdwingen**|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|
|**Bescherming van Intune-toepassingen afdwingen**|Ja|Ja|Ja|
|**Intune-inschrijving (COD) afdwingen**|Een compatibele of domein-aangesloten pc vereisen, maar byod-telefoons/tablets toestaan|Een compatibel of domeinapparaat vereisen|Een compatibel of domeinapparaat vereisen|

## <a name="device-ownership"></a>Apparaateigendom

De bovenstaande tabel weerspiegelt de trend voor veel organisaties om een mix van apparaten in bedrijf te ondersteunen, evenals persoonlijke of bring-your-own devices (BYODs) om mobiele productiviteit in het hele personeelsbestand mogelijk te maken. Het beveiligingsbeleid voor intune-apps zorgt ervoor dat e-mail wordt beschermd tegen exfiltreting uit de mobiele Outlook-app en andere mobiele Office-apps, op zowel apparaten die eigendom zijn van bedrijven als BYODs.  

We raden zakelijke apparaten aan om te worden beheerd door Intune of die zijn aangesloten om extra beveiligingen en controle toe te passen. Afhankelijk van de gegevensgevoeligheid kan uw organisatie ervoor kiezen om geen BYOD's toe te staan voor specifieke gebruikerspopulaties of specifieke apps.

## <a name="next-steps"></a>Volgende stappen

[Voorwaarde werk voor de implementatie van identiteits- en apparaattoegangsbeleid](identity-access-prerequisites.md)
