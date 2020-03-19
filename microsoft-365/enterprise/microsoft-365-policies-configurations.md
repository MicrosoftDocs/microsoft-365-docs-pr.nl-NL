---
title: Configuraties voor identiteits- en apparaattoegang - Microsoft 365 Enterprise
description: Beschrijft aanbevelingen en kernconcepten van Microsoft voor het implementeren van beleid en configuraties voor het implementeren van beveiligde e-mail, documenten en apps.
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
ms.openlocfilehash: 8d7adda0ded3a118676a67d0446a5744233468f3
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812018"
---
# <a name="identity-and-device-access-configurations"></a>Configuraties voor identiteits- en apparaattoegang

In deze serie artikelen wordt beschreven hoe u veilige toegang tot cloudservices configureren via Enterprise Mobility + Security (EMS)-producten door een aanbevolen omgeving en configuratie te implementeren, inclusief een voorgeschreven set beleid voor voorwaardelijke toegang en gerelateerde mogelijkheden. EMS is een kernonderdeel van Microsoft 365. U deze richtlijnen gebruiken om de toegang te beschermen tot alle services die zijn geïntegreerd met Azure Active Directory, waaronder Office 365-services, andere SaaS-services en on-premises toepassingen die zijn gepubliceerd met Azure AD-toepassingsproxy. 

Deze aanbevelingen zijn afgestemd op de Microsoft Secure Score en [de identiteitsscore in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)en verhogen deze scores voor uw organisatie. Deze aanbevelingen helpen u ook bij het implementeren van deze [vijf stappen om uw identiteitsinfrastructuur te beveiligen.](https://docs.microsoft.com/azure/security/azure-ad-secure-steps) 

Microsoft begrijpt dat sommige organisaties unieke omgevingsvereisten of complexiteiten hebben. Als u een van deze organisaties bent, gebruikt u deze aanbevelingen als uitgangspunt. De meeste organisaties kunnen deze aanbevelingen echter uitvoeren zoals voorgeschreven. 

## <a name="intended-audience"></a>Beoogde doelgroep

Deze aanbevelingen zijn bedoeld voor bedrijfsarchitecten en IT-professionals die bekend zijn met [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) en [Microsoft Enterprise Mobility + Security,](https://microsoft.com/ems)waaronder onder andere Azure Active Directory (identiteit), Microsoft Intune (apparaatbeheer) en Azure Information Protection (gegevensbescherming).

### <a name="customer-environment"></a>Klantomgeving

Het aanbevolen beleid is van toepassing op bedrijfsorganisaties die zowel volledig binnen de Microsoft-cloud als voor klanten met een hybride infrastructuur werken (zowel on-premises als de Microsoft-cloud geïmplementeerd).

Veel van de verstrekte aanbevelingen zijn afhankelijk van services die alleen beschikbaar zijn met Enterprise Mobility + Security (EMS) E5-licenties. Aanbevelingen gepresenteerd gaan uit van volledige EMS E5 licentie mogelijkheden.

Voor organisaties die geen Enterprise Mobility + Security E5-licenties hebben, raadt Microsoft u ten minste aan azure AD-basislijnbeveiligingsmogelijkheden te implementeren die bij alle abonnementen zijn opgenomen. Meer informatie vindt u in het artikel [Wat is basislijnbeveiliging](/azure/active-directory/active-directory-conditional-access-baseline-protection)in de Azure AD-bibliotheek.

### <a name="caveats"></a>Waarschuwingen

Uw organisatie kan onderworpen zijn aan wettelijke of andere nalevingsvereisten, waaronder specifieke aanbevelingen die u mogelijk verplichten om beleidsregels toe te passen die afwijken van deze aanbevolen configuraties. Deze configuraties raden gebruiksbesturingselementen aan die historisch niet beschikbaar zijn geweest. We raden deze controles aan, omdat we geloven dat ze een evenwicht vormen tussen veiligheid en productiviteit.  

We hebben ons best gedaan om rekening te houden met een breed scala aan organisatorische beschermingsvereisten, maar we zijn niet in staat om rekening te houden met alle mogelijke vereisten of voor alle unieke aspecten van uw organisatie.

## <a name="three-tiers-of-protection"></a>Drie beschermingsniveaus

De meeste organisaties hebben specifieke eisen met betrekking tot beveiliging en gegevensbescherming. Deze eisen verschillen per industriesegment en per functie binnen organisaties. Uw juridische afdeling en Office 365-beheerders hebben bijvoorbeeld extra beveiligings- en informatiebeveiligingsbesturingselementen nodig rond hun e-mailcorrespondentie die niet vereist zijn voor andere gebruikers van bedrijfseenheden. 

Elke industrie heeft ook zijn eigen set van gespecialiseerde regelgeving. In plaats van een lijst met alle mogelijke beveiligingsopties of een aanbeveling per industriesegment of functie, zijn aanbevelingen voorzien voor drie verschillende beveiligings- en beschermingsniveaus die kunnen worden toegepast op basis van de granulariteit van uw behoeften .

- **Basislijnbeveiliging:** We raden u aan een minimumnorm vast te stellen voor het beveiligen van gegevens, evenals de identiteiten en apparaten die toegang hebben tot uw gegevens. U deze basislijnaanbevelingen volgen om een sterke standaardbescherming te bieden die voldoet aan de behoeften van veel organisaties.
- **Gevoelige bescherming**: Sommige klanten hebben een subset van gegevens die op hogere niveaus moeten worden beschermd, of ze kunnen vereisen dat alle gegevens op een hoger niveau worden beschermd. U meer bescherming toepassen op alle of specifieke gegevenssets in uw Office 365-omgeving. We raden u aan identiteiten en apparaten te beschermen die toegang hebben tot gevoelige gegevens met vergelijkbare beveiligingsniveaus.  
- **Sterk gereguleerd**: Sommige organisaties kunnen een kleine hoeveelheid gegevens hebben die zeer geclassificeerd is, bedrijfsgeheimen verhoudt of gereguleerde gegevens zijn. Microsoft biedt mogelijkheden om organisaties te helpen aan deze vereisten te voldoen, waaronder extra bescherming voor identiteiten en apparaten.

![Beveiligingskegel - Alle klanten > Sommige klanten > specifieke klanten. Brede toepassing op specifieke toepassing](../media/M365-idquality-threetiers.png)

Deze richtlijnen laten u zien hoe u bescherming voor identiteiten en apparaten voor elk van deze beschermingsniveaus implementeren. Gebruik deze richtlijnen als uitgangspunt voor uw organisatie en pas het beleid aan om aan de specifieke vereisten van uw organisatie te voldoen.

Het is belangrijk om consistente beschermingsniveaus te gebruiken voor uw gegevens, identiteiten en apparaten. Als u deze richtlijnen bijvoorbeeld implementeert, moet u uw gegevens op vergelijkbare niveaus beschermen. Deze architectuurmodellen laten zien welke mogelijkheden vergelijkbaar zijn.

**Identiteits- en apparaatbeveiliging voor Office 365**<br/>
![Miniatuur voor poster 'Identiteit en apparaatbeveiliging voor Office 365'](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Meer talen](https://www.microsoft.com/download/details.aspx?id=55032)

**Oplossingen voor bestandsbeveiliging in Office 365**<br/>
![Miniatuur voor poster 'Oplossingen voor bestandsbeveiliging in Office 365'](../media/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Trade-offs voor veiligheid en productiviteit

Het implementeren van een beveiligingsstrategie vereist afwegingen tussen veiligheid en productiviteit. Het is handig om te evalueren hoe elke beslissing de balans van beveiliging, functionaliteit en gebruiksgemak beïnvloedt.

![Beveiliging triade balanceren veiligheid, functionaliteit en gebruiksgemak.](../media/policies-configurations/security-triad.png)

De verstrekte aanbevelingen zijn gebaseerd op de volgende beginselen:

- Ken je publiek en wees flexibel in hun beveiligings- en functionele vereisten.
- Pas een beveiligingsbeleid net op tijd toe en zorg ervoor dat het zinvol is.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Diensten en concepten voor bescherming van identiteits- en apparaattoegang

Microsoft 365 Enterprise is ontworpen voor grote organisaties en integreert Office 365 Enterprise, Windows 10 Enterprise en Enterprise Mobility + Security (EMS), om iedereen in staat te stellen creatief te zijn en veilig samen te werken.

In deze sectie vindt u een overzicht van de Microsoft 365-services en -mogelijkheden die belangrijk zijn voor de toegang tot identiteit en apparaten.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD biedt een volledige suite van mogelijkheden voor identiteitsbeheer. Voor het beveiligen van toegang raden we u aan de volgende mogelijkheden te gebruiken:

- **[Self-service password reset (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: Laat uw gebruikers hun wachtwoorden veilig en zonder tussenkomst van de helpdesk resetten, door verificatie te bieden van meerdere verificatiemethoden die de beheerder kan beheren.

- **[Multi-factor authentication (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)**: MFA vereist dat gebruikers twee vormen van verificatie opgeven, zoals een gebruikerswachtwoord plus een melding van de Microsoft Authenticator-app of een telefoongesprek. MFA vermindert het risico dat een gestolen identiteit kan worden gebruikt om toegang te krijgen tot uw Office 365-omgeving sterk.

- **[Voorwaardelijke toegang:](/azure/active-directory/conditional-access/overview)** Azure AD evalueert de voorwaarden van de aanmelding van de gebruiker en maakt gebruik van beleid voor voorwaardelijke toegang dat u maakt om toegang toe te staan. In deze richtlijnen laten we u bijvoorbeeld zien hoe u een beleid voor voorwaardelijke toegang maken om apparaatnaleving te vereisen voor toegang tot gevoelige gegevens. Dit vermindert sterk het risico dat een hacker met een gestolen identiteit toegang heeft tot uw gevoelige gegevens. Het beschermt ook gevoelige gegevens op de apparaten, omdat de apparaten voldoen aan specifieke eisen voor gezondheid en beveiliging.

- **[Azure AD-groepen](/azure/active-directory/fundamentals/active-directory-manage-groups)**: regels voor voorwaardelijke toegang, apparaatbeheer met Intune en zelfs machtigingen voor bestanden en sites in uw organisatie, vertrouwen op toewijzing aan gebruikers- en/of Azure AD-groepen. We raden u aan Azure AD-groepen te maken die overeenkomen met de beveiligingsniveaus die u implementeert. Bijvoorbeeld, uw leidinggevend personeel zijn waarschijnlijk hogere waarde doelen voor hackers. Daarom is het zinvol om deze werknemers toe te wijzen aan een Azure AD-groep en deze groep toe te wijzen aan beleid voor voorwaardelijke toegang en ander beleid dat een hoger niveau van bescherming afdwingt voor toegang.

- **[Apparaatregistratie:](/azure/active-directory/devices/overview)** U registreert een apparaat in Azure AD om een identiteit aan het apparaat te verstrekken. Deze identiteit wordt gebruikt om het apparaat te verifiëren wanneer een gebruiker zich aanmeldt en om voorwaardelijke toegangsregels toe te passen waarvoor pc's met domeinverbinding of compatibele pc's vereist zijn. Voor deze richtlijnen gebruiken we apparaatregistratie om windows-computers die zijn verbonden met een domein automatisch te registreren. Apparaatregistratie is een voorwaarde voor het beheren van apparaten met Intune. 

- **[Azure AD-identiteitsbeveiliging](/azure/active-directory/identity-protection/overview)**: Azure AD-identiteitsbeveiliging stelt u in staat om potentiële kwetsbaarheden te detecteren die van invloed zijn op de identiteit van uw organisatie en geautomatiseerd herstelbeleid te configureren op laag, gemiddeld en hoog aanmeldingsrisico en gebruikersrisico. Deze richtlijnen zijn gebaseerd op deze risicobeoordeling om beleid voor voorwaardelijke toegang toe te passen voor meervoudige verificatie. Deze richtlijnen bevatten ook een beleid voor voorwaardelijke toegang dat gebruikers verplicht hun wachtwoord te wijzigen als activiteit met een hoog risico wordt gedetecteerd voor hun account.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) is de cloudgebaseerde service voor het beheer van mobiele apparaten in de cloud. Deze richtlijnen beveelt apparaatbeheer van Windows-pc's met Intune aan en beveelt beleidsconfiguraties voor apparaatnaleving aan. Intune bepaalt of apparaten compatibel zijn en stuurt deze gegevens naar Azure AD om te gebruiken bij het toepassen van beleid voor voorwaardelijke toegang.

#### <a name="intune-app-protection"></a>App-beveiliging inafstemmen

[Intune-app-beveiligingsbeleid](https://docs.microsoft.com/intune/app-protection-policy) kan worden gebruikt om de gegevens van uw organisatie in mobiele apps te beschermen, met of zonder apparaten in te schrijven bij beheer. Intune helpt Office 365-informatie te beschermen, zodat uw medewerkers nog steeds productief kunnen zijn en gegevensverlies wordt voorkomen. Door beleid op app-niveau te implementeren, u de toegang tot bedrijfsbronnen beperken en gegevens binnen de controle van uw IT-afdeling houden.

In deze richtlijnen ziet u hoe u aanbevolen beleidsregels maken om het gebruik van goedgekeurde apps af te dwingen en te bepalen hoe deze apps kunnen worden gebruikt met uw bedrijfsgegevens.

### <a name="office-365"></a>Office 365

In deze richtlijnen ziet u hoe u een set beleidsregels implementeert om de toegang tot Office 365 te beschermen, waaronder Exchange Online, SharePoint Online en OneDrive voor Bedrijven. Naast het implementeren van dit beleid raden we u aan ook het beschermingsniveau voor uw Office 365-tenant te verhogen met behulp van deze bronnen:

- [Uw Office 365-tenant configureren voor meer beveiliging:](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)deze aanbevelingen zijn van toepassing op basislijnbeveiliging voor uw Office 365-tenant.
- [Office 365-beveiligingsroadmap: topprioriteiten voor de eerste 30 dagen, 90 dagen en verder:](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)deze aanbevelingen omvatten logboekregistratie, gegevensbeheer, beheerderstoegang en bescherming tegen bedreigingen.


### <a name="windows-10-and-office-365-proplus"></a>Windows 10 en Office 365 ProPlus

Windows 10 en Office 365 ProPlus is de aanbevolen clientomgeving voor pc's. We raden Windows 10 aan, omdat Azure is ontworpen om de soepelste ervaring te bieden die mogelijk is voor zowel on-premises als Azure AD. Windows 10 bevat ook geavanceerde beveiligingsmogelijkheden die kunnen worden beheerd via Intune. Office 365 ProPlus bevat de nieuwste versies van Office-toepassingen. Deze maken gebruik van moderne authenticatie, die veiliger is en een vereiste voor voorwaardelijke toegang. Deze apps bevatten ook verbeterde beveiligings- en nalevingstools.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Toepassing van deze mogelijkheden op de drie beschermingsniveaus

In de volgende tabel worden onze aanbevelingen voor het gebruik van deze mogelijkheden over de drie beschermingsniveaus samengevat.

|Beschermingsmechanisme|Basislijn|Gevoelige|Sterk gereguleerd|
|:-------------------|:-------|:--------|:---------------|
|**MFA afdwingen**|Op medium of boven aanmeldingsrisico|Op laag of boven aanmeldingsrisico|Op alle nieuwe sessies|
|**Wachtwoordwijziging afdwingen**|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|Voor gebruikers met een hoog risico|
|**Intune-toepassingsbeveiliging afdwingen**|Ja|Ja|Ja|
|**Intune-inschrijving (COD) afdwingen**|Vereisen een compatibele of domein-aangesloten pc, maar byod-telefoons/tablets toestaan|Een compatibel of domeincompatibel apparaat vereisen|Een compatibel of domeincompatibel apparaat vereisen|

## <a name="device-ownership"></a>Apparaateigendom

De bovenstaande tabel weerspiegelt de trend voor veel organisaties om een mix van apparaten die eigendom zijn van bedrijven te ondersteunen, evenals persoonlijke of bring-your-own apparaten (BYODs) om mobiele productiviteit in het hele personeelsbestand mogelijk te maken. Intune-app-beveiligingsbeleid zorgt ervoor dat e-mail wordt beschermd tegen exfiltreren uit de mobiele Outlook-app en andere mobiele Office-apps, op zowel zakelijke apparaten als BYO's.  

We raden apparaten die eigendom zijn van bedrijven worden beheerd door Intune of domein-joined aan om extra beveiligingen en controle toe te passen. Afhankelijk van de gevoeligheid van gegevens kan uw organisatie ervoor kiezen om by-o's niet toe te staan voor specifieke gebruikerspopulaties of specifieke apps.

## <a name="next-steps"></a>Volgende stappen

[Voorwaarde voor het implementeren van identiteits- en apparaattoegangsbeleid](identity-access-prerequisites.md)
