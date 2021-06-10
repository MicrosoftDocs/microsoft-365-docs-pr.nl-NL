---
title: 'Case study : Contoso configureert snel een aanstootgevend taalbeleid voor Microsoft Teams, Exchange en Yammer communicatie'
description: Een case study voor Contoso en hoe ze snel een communicatie compliancebeleid configureren om te controleren op aanstootgevende taal in Microsoft Teams, Exchange Online en Yammer communicatie.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 1b9bef180fed9c3afa3b3d8d2319a1fa0260ed14
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "52161686"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Case study : Contoso configureert snel een aanstootgevend taalbeleid voor Microsoft Teams, Exchange en Yammer communicatie

Communicatie compliance in Microsoft 365 helpt communicatierisico's te minimaliseren door u te helpen ongepaste berichten in uw organisatie op te sporen, vast te leggen en te handelen. Met vooraf gedefinieerde en aangepaste beleidsregels kunt u interne en externe communicatie scannen op beleidswedstrijden, zodat deze kunnen worden onderzocht door aangewezen revisoren. Revisoren kunnen gescande e-mail, Microsoft Teams, Yammer of externe communicatie in uw organisatie onderzoeken en passende herstelacties uitvoeren om ervoor te zorgen dat ze voldoen aan de berichtstandaarden van uw organisatie.

De Contoso Corporation is een fictieve organisatie die snel een beleid moet configureren om te controleren op aanstootgevende taal. Ze gebruiken Microsoft 365 voornamelijk voor e-mail, Microsoft Teams en Yammer ondersteuning voor hun gebruikers, maar hebben nieuwe vereisten voor het afdwingen van het bedrijfsbeleid rond pesterijen op het werk. Contoso IT-beheerders en compliancespecialisten hebben een basiskennis van de basisprincipes van het werken met Microsoft 365 en zijn op zoek naar richtlijnen voor end-to-end om snel aan de slag te gaan met communicatie compliance.

In deze casestudie worden de basisbeginselen bestudeert voor het snel configureren van een communicatiebeleid voor het controleren van communicatie op aanstootgevende taal. Deze richtlijnen omvatten:

- Stap 1 - Planning voor communicatie compliance
- Stap 2 : toegang krijgen tot communicatie compliance in Microsoft 365
- Stap 3 : vereisten configureren en een communicatie-compliancebeleid maken
- Stap 4 - Waarschuwingen onderzoeken en herstellen

## <a name="step-1-planning-for-communication-compliance"></a>Stap 1: Planning voor communicatie compliance

Contoso IT-beheerders en compliancespecialisten hebben deelgenomen aan online webinars over complianceoplossingen in Microsoft 365 en besloten dat communicatie compliancebeleid hen zal helpen voldoen aan de bijgewerkte bedrijfsbeleidsvereisten voor het verminderen van pesterijen op het werk. Samen hebben ze een plan ontwikkeld voor het maken en inschakelen van een communicatie-compliancebeleid dat controleert op aanstootgevende taal voor chats die worden verzonden in Microsoft Teams, privéberichten en communitygesprekken in Yammer en in e-mailberichten die worden verzonden in Exchange Online. Hun plan omvat het identificeren van:

- De IT-beheerders die toegang nodig hebben tot communicatie-compliancefuncties.
- De compliancespecialisten die communicatiebeleid moeten maken en beheren.
- De compliancespecialisten en andere collega's op andere afdelingen (Human Resources, Legal, enz.) die waarschuwingen voor communicatie compliance moeten onderzoeken en corrigeren.
- De gebruikers die binnen het bereik van het communicatie compliance-aanstootgevende taalbeleid vallen.

### <a name="licensing"></a>Licenties

De eerste stap is om te bevestigen dat de Microsoft 365 contoso ondersteuning biedt voor de oplossing voor communicatie compliance. Als u communicatiecond compliance wilt openen en gebruiken, moeten IT-beheerders van Contoso controleren of Contoso een van de volgende opties heeft:

- Microsoft 365 E5 (betaalde of proefversie)
- Microsoft 365 E3 +de Microsoft 365 E5 Compliance-invoegvoegvoeging
- Microsoft 365 E3 abonnement + de Microsoft 365 E5 Insider Risk Management-invoegvoegvoeging
- Microsoft 365 A5-abonnement (betaalde versie of proefversie)
- Microsoft 365 A3-abonnement + de Microsoft 365 A5 Compliance-invoegvoegvoeging
- Microsoft 365 A3-abonnement + de Microsoft 365 A5 Insider Risk Management-invoegvoegvoeging
- Microsoft 365 G5-abonnement (betaalde versie of proefversie)
- Microsoft 365 G5-abonnement + de Microsoft 365 G5 Compliance-invoegvoegvoeging
- Microsoft 365 G5-abonnement + de Microsoft 365 G5 Insider Risk Management-invoegvoegvoeging
- Office 365 Enterprise E5-abonnement (betaalde of proefversie)
- Office 365 Enterprise E3-abonnement + de Office 365 Advanced Compliance-invoegabonnement (niet meer beschikbaar voor nieuwe abonnementen, zie opmerking)

Ze moeten ook bevestigen dat gebruikers die deel uit maken van communicatie-compliancebeleid, een van de bovenstaande licenties moeten krijgen.

>[!IMPORTANT]
>Office 365 Advanced Compliance wordt niet meer als zelfstandig abonnement verkocht. Wanneer huidige abonnementen verlopen, moeten klanten overstappen op een van de bovenstaande abonnementen, die dezelfde of aanvullende compliancefuncties bevatten.

It-beheerders van Contoso nemen de volgende stappen om de ondersteuning voor licenties voor Contoso te controleren:

1. IT-beheerders melden zich aan bij **het Microsoft 365-beheercentrum** [( https://admin.microsoft.com)](https://admin.microsoft.com) en navigeren naar Microsoft 365 **beheercentrum**  >    >  **Factureringslicenties**.

2. Hier bevestigen ze dat ze een van de licentieopties [hebben](communication-compliance-configure.md#subscriptions-and-licensing) die ondersteuning voor communicatie compliance bevat.

![Compliancelicenties voor communicatie](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Machtigingen voor communicatie compliance

Er zijn vijf rollengroepen die worden gebruikt om machtigingen te configureren voor het beheren van communicatie compliancefuncties. Als u **communicatie compliance beschikbaar** wilt maken als menuoptie in Microsoft 365 compliancecentrum en deze configuratiestappen wilt voortzetten, krijgen Contoso-beheerders de rol Communicatie *compliancebeheerder* toegewezen.

Contoso besluit de  rolgroep Communicatie compliance te gebruiken om alle communicatie compliancebeheerders, analisten, onderzoeker en kijkers toe te wijzen aan de groep. Dit maakt het voor Contoso gemakkelijker om snel aan de slag te gaan en het beste aan hun compliancebeheervereisten te voldoen.

|**Rol**|**Rolmachtigingen**|
|:-----|:-----|
| **Naleving van communicatie** | Gebruik deze rollengroep om communicatie compliance voor uw organisatie in één groep te beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten, onderzoeker en kijkers, kunt u communicatie compliancemachtigingen configureren in één groep. Deze rollengroep bevat alle machtigingsrollen voor communicatie compliance. Deze configuratie is de eenvoudigste manier om snel aan de slag te gaan met communicatie-compliance en is geschikt voor organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers. |
| **Communicatie compliancebeheerder** | Gebruik deze rollengroep om communicatie compliance in eerste instantie te configureren en later om beheerders van communicatie compliance te scheiden in een gedefinieerde groep. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen communicatie compliancebeleid, globale instellingen en toewijzingen voor rollengroepen maken, lezen, bijwerken en verwijderen. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen geen berichtwaarschuwingen weergeven. |
| **Communicatie compliance-analist** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als communicatie-complianceanalisten. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen beleid weergeven waarin ze zijn toegewezen als revisoren, metagegevens van berichten weergeven (geen berichtinhoud), escaleren naar extra revisoren of meldingen verzenden naar gebruikers. Analisten kunnen waarschuwingen in behandeling niet oplossen. |
| **Communicatie compliance-onderzoeker** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als communicatie compliance-onderzoeker. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen metagegevens en inhoud van berichten bekijken, escaleren naar extra revisoren, escaleren naar een Advanced eDiscovery-geval, meldingen naar gebruikers verzenden en de waarschuwing oplossen. |
| **Viewer voor communicatie compliance** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die communicatierapporten beheren. Gebruikers die aan deze rollengroep zijn toegewezen, hebben toegang tot alle rapportagewidgets op de startpagina communicatie compliance en kunnen alle communicatie compliancerapporten bekijken. |

1. It-beheerders van Contoso melden zich aan bij de machtigingenpagina **Office 365 beveiligings- & compliancecentrum** [( https://protection.office.com/permissions)](https://protection.office.com/permissions) gebruik referenties voor een globale beheerdersaccount en selecteer de koppeling voor het weergeven en beheren van rollen in Microsoft 365.
2. In het **Beveiligings- & Compliancecentrum**  gaan ze naar Machtigingen en selecteren ze de koppeling om rollen in Office 365.
3. De beheerders selecteren de *rollengroep Communicatie compliance* en selecteren **vervolgens Rollengroep bewerken.**
4. De beheerders selecteren **Leden kiezen** in het linkernavigatiedeelvenster en selecteer vervolgens **Bewerken.**
5. Ze selecteren **Toevoegen** en selecteren vervolgens het selectievakje voor alle Contoso-gebruikers die communicatie compliance beheren, onderzoeken en waarschuwingen controleren.
6. De beheerders selecteren **Toevoegen** en selecteer vervolgens **Klaar.**
7. Ze selecteren **Opslaan om** Contoso-gebruikers toe te voegen aan de rollengroep. Ze selecteren **Sluiten om** de stappen uit te voeren.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Stap 2: Toegang krijgen tot communicatie compliance in Microsoft 365

Na het configureren van de machtigingen voor communicatie compliance, hebben Contoso IT-beheerders en compliancespecialisten die zijn toegewezen aan de rolgroep Communicatie compliance toegang tot de communicatie compliance-oplossing in Microsoft 365. It-beheerders en compliancespecialisten van Contoso hebben verschillende manieren om toegang te krijgen tot communicatie compliance en aan de slag te gaan met het maken van een nieuw beleid:

- Rechtstreeks vanuit de oplossing voor communicatie compliance
- Vanaf het Microsoft 365 compliancecentrum
- Vanaf de catalogus met Microsoft 365-oplossing
- Vanaf het Microsoft 365 beheercentrum

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Rechtstreeks vanuit de oplossing voor communicatie compliance

De snelste manier om toegang te krijgen tot de oplossing is door u rechtstreeks aan te melden bij de **oplossing Communicatie compliance** <https://compliance.microsoft.com/supervisoryreview> (). Via deze koppeling worden IT-beheerders en compliancespecialisten van Contoso doorgestuurd naar het dashboard Overzicht van communicatie compliance, waar u snel de status van waarschuwingen kunt bekijken en nieuwe beleidsregels kunt maken op basis van de vooraf gedefinieerde sjablonen.

![Overzicht van communicatie compliance](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Vanaf het Microsoft 365 compliancecentrum

Een andere eenvoudige manier voor It-beheerders en compliancespecialisten van Contoso om toegang te krijgen tot de oplossing voor communicatie compliance, is door u rechtstreeks aan te melden bij **het Microsoft 365 compliancecentrum** [( https://compliance.microsoft.com)](https://compliance.microsoft.com). Na het aanmelden hoeven gebruikers  alleen het besturingselement Alle weergeven te selecteren om alle complianceoplossingen weer te geven en vervolgens de **communicatie-complianceoplossing** te selecteren om aan de slag te gaan.

![Compliancecentrum](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>Vanaf de catalogus met Microsoft 365-oplossing

It-beheerders en compliancespecialisten van Contoso kunnen er ook voor kiezen om toegang te krijgen tot de communicatie-complianceoplossing door de catalogus met Microsoft 365 selecteren. Door **catalogus** in de sectie **Oplossingen** van de linkernavigatie te selecteren in het **Microsoft 365 compliancecentrum,** kunnen ze de oplossingscatalogus openen met alle Microsoft 365 complianceoplossingen. Als u omlaag schuift naar de **sectie Insider-risicobeheer,** kunnen It-beheerders van Contoso Communicatie compliance selecteren om aan de slag te gaan. Contoso IT-beheerders besluiten ook om het navigatiebesturingselement Weergeven in te gebruiken om de oplossing voor communicatie compliance vast te maken aan het linkernavigatiedeelvenster voor snellere toegang wanneer ze zich aanmelden.

![Oplossingscatalogus](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>Vanaf het Microsoft 365 beheercentrum

Als u toegang wilt tot communicatie compliance wanneer u begint vanuit het Microsoft 365-beheercentrum, melden CONTOSO-IT-beheerders en compliancespecialisten zich aan bij het Microsoft 365-beheercentrum [( https://admin.microsoft.com)](https://admin.microsoft.com) en navigeert u naar **Microsoft 365-beheercentrum**  >  **Compliance**.

![Koppeling communicatie compliance](../media/communication-compliance-case-compliance-link.png)

Met deze actie wordt **Office 365** beveiligings- en compliancecentrum geopend en moet de koppeling naar het **Microsoft 365 compliancecentrum** in de banner boven aan de pagina worden geselecteerd.

![Office 365 beveiligings- en compliancecentrum](../media/communication-compliance-case-scc.png)

Eenmaal in het **Microsoft 365 compliancecentrum,** selecteren IT-beheerders van Contoso **Alles** weergeven om de volledige lijst met complianceoplossingen weer te geven.

![Menu Communicatie compliance](../media/communication-compliance-case-show-all.png)

Nadat u **Alles tonen hebt geselecteerd,** hebben de IT-beheerders van Contoso toegang tot de oplossing voor communicatie compliance.

![Overzicht van communicatie compliance](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Stap 3: Vereisten configureren en een communicatie-compliancebeleid maken

Om aan de slag te gaan met een communicatie compliancebeleid, zijn er verschillende vereisten die It-beheerders van Contoso moeten configureren voordat ze het nieuwe beleid instellen om te controleren op aanstootgevende taal. Nadat deze vereisten zijn voltooid, kunnen IT-beheerders en compliancespecialisten van Contoso de nieuwe beleids- en compliancespecialisten configureren en eventuele gegenereerde waarschuwingen onderzoeken en herstellen.

### <a name="enabling-auditing-in-microsoft-365"></a>Controle inschakelen in Microsoft 365

Communicatie compliance vereist auditlogboeken om waarschuwingen weer te geven en herstelacties van revisoren bij te houden. De auditlogboeken zijn een overzicht van alle activiteiten die zijn gekoppeld aan een gedefinieerd organisatiebeleid of wanneer er een wijziging is in een communicatie-compliancebeleid.

It-beheerders van Contoso controleren en voltooien de [stapsgewijs](turn-audit-log-search-on-or-off.md) instructies om auditing in te zetten. Nadat ze de controle hebben in- of uitgevoerd, wordt een bericht weergegeven met de melding dat het auditlogboek wordt voorbereid en dat ze een zoekopdracht kunnen uitvoeren binnen een paar uur nadat de voorbereiding is voltooid. De IT-beheerders van Contoso moeten deze actie maar één keer uitvoeren.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Het configureren Yammer tenant voor de autochtone modus

Communicatie compliance vereist dat de Yammer tenant voor een organisatie zich in de autochtone modus heeft om te controleren op aanstootgevende taal in privéberichten en openbare communitygesprekken.

It-beheerders van Contoso controleren de gegevens in het artikel Overzicht van Yammer Native [Mode in Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode) en volgen de stappen voor het uitvoeren van het migratiehulpmiddel in het artikel Uw [Yammer-netwerk](/yammer/configure-your-yammer-network/native-mode) configureren voor native mode voor Microsoft 365.

### <a name="setting-up-a-group-for-in-scope-users"></a>Een groep instellen voor gebruikers binnen het bereik

Contoso-compliancespecialisten willen alle gebruikers toevoegen aan het communicatiebeleid dat wordt gecontroleerd op aanstootgevende taal. Ze kunnen besluiten om elk gebruikersaccount afzonderlijk aan het beleid toe te voegen, maar  ze hebben besloten dat het veel gemakkelijker is en besparen tijd om een distributiegroep Alle gebruikers voor de gebruikers voor dit beleid te gebruiken.

Ze moeten een nieuwe groep maken om alle Contoso-gebruikers op te nemen, zodat ze de volgende stappen ondernemen:

1. IT-beheerders van Contoso melden zich aan bij het **Microsoft 365 -beheercentrum** [ https://admin.microsoft.com) (](https://admin.microsoft.com) en navigeer naar Microsoft 365 **beheercentrum**  >  **Groepen** groepen  >  .
2. Ze selecteren **Een groep toevoegen en** voltooien  de wizard om een nieuwe groep Microsoft 365 of *distributiegroep te maken.*

    ![Groepen](../media/communication-compliance-case-all-employees.png)

3. Nadat de nieuwe groep is gemaakt, moeten ze alle Contoso-gebruikers toevoegen aan de nieuwe groep. Ze openen het **Exchange beheercentrum** [(en https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) navigeren naar Exchange **groepen** geadresseerden van  >  **het**  >  **beheercentrum.** De IT-beheerders van Contoso selecteren  het gebied Lidmaatschap en  de nieuwe groep Alle werknemers die ze hebben gemaakt en selecteer het besturingselement Bewerken om alle Contoso-gebruikers toe te voegen aan de nieuwe groep in de wizard.

    ![Exchange-beheercentrum](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Het beleid maken om te controleren op aanstootgevende taal

Als alle vereisten zijn voltooid, zijn de IT-beheerders en de compliancespecialisten voor Contoso klaar om het communicatie compliancebeleid te configureren om te controleren op aanstootgevende taal. Met de nieuwe sjabloon voor aanstootgevend taalbeleid kunt u dit beleid eenvoudig en snel configureren.

1. De IT-beheerders en compliancespecialisten van Contoso melden zich aan bij het Microsoft 365 **compliancecentrum** en **selecteren** Communicatie compliance in het linkernavigatiedeelvenster. Met deze actie wordt het dashboard **Overzicht** geopend met snelle koppelingen voor beleidssjablonen voor communicatie compliance. Ze kiezen de **sjabloon Monitor voor aanstootgevende taal** door Aan de slag te **selecteren** voor de sjabloon.

    ![Taalsjabloon communicatie compliance](../media/communication-compliance-case-template.png)

2. In de wizard Beleidssjabloon werken de IT-beheerders en compliancespecialisten van Contoso samen om de drie vereiste velden te voltooien: **Beleidsnaam,** **Gebruikers** of groepen om toezicht op te houden en **Revisoren.**
3. Aangezien de beleidswizard al een naam voor het beleid heeft voorgesteld, besluiten de IT-beheerders en compliancespecialisten de voorgestelde naam te behouden en zich te concentreren op de resterende velden. Ze selecteren de groep  *Alle gebruikers* voor de gebruikers of groepen om toezicht te houden op het veld en selecteren de compliancespecialisten die beleidswaarschuwingen voor het veld **Revisoren moeten** onderzoeken en corrigeren. De laatste stap voor het configureren van het beleid en het verzamelen van waarschuwingsgegevens is het selecteren **van Beleid maken.**

    ![Wizard Taal met aanstootgevende communicatie compliance](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Stap 4: Waarschuwingen onderzoeken en corrigeren

Nu het communicatie compliancebeleid voor het controleren op aanstootgevende taal is geconfigureerd, is de volgende stap voor de contoso-compliancespecialisten het onderzoeken en corrigeren van waarschuwingen die door het beleid worden gegenereerd. Het duurt maximaal 24 uur voordat het beleid de communicatie in alle communicatiebronkanalen volledig verwerkt en dat waarschuwingen worden weergeven in het **dashboard Waarschuwing.**

Nadat waarschuwingen zijn gegenereerd, volgen contoso-compliancespecialisten de werkstroominstructies om aanstootgevende taalproblemen te onderzoeken en te verhelpen. [](communication-compliance-investigate-remediate.md)