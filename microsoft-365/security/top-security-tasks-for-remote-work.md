---
title: De 12 belangrijkste taken voor beveiligingsteams ter ondersteuning van thuis werken
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: Bescherm uw zakelijke e-mail en gegevens tegen cyberaanvallen, waaronder ransomware, phishing en schadelijke bijlagen.
ms.openlocfilehash: a1850438d02042ba5931a6208b82f74766ae0be8
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097268"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>De 12 belangrijkste taken voor beveiligingsteams ter ondersteuning van thuis werken

Als u net als [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) werkt en u plotseling te maken hebt met voornamelijk thuis werkend personeel, willen we u helpen om ervoor te zorgen dat uw organisatie zo veilig mogelijk werkt. In dit artikel wordt prioriteit gegeven aan taken om beveiligingsteams te helpen de belangrijkste beveiligingsfuncties zo snel mogelijk te implementeren.

![Voer deze taken uit om thuis te werken te ondersteunen.](../media/security/security-support-remote-work.png)

Als u een kleine of middelgrote organisatie hebt met een van de bedrijfsplannen van Microsoft, bekijkt u in plaats daarvan deze bronnen:

- [De tien belangrijkste manieren om abonnementen voor Office 365 en Microsoft 365 voor Bedrijven te beveiligen](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 voor campagnes](https://docs.microsoft.com/microsoft-365/campaigns/) (inclusief een aanbevolen beveiligingsconfiguratie voor Microsoft 365 Business)

Voor klanten die onze enterprise-abonnementen gebruiken, raadt Microsoft u aan de taken uit de volgende tabel uit te voeren die van toepassing zijn op uw serviceplan. Als u abonnementen combineert in plaats van een Microsoft 365 Enterprise-abonnement, houd dan rekening met het volgende:

- Microsoft 365 E3 bevat Enterprise Mobility + Security (EMS) E3 en Azure AD P1
- Microsoft 365 E5 bevat EMS E5 en Azure AD P2

****

|Stap|Taak|Alle Office 365 Enterprise-abonnementen|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1|[Azure AD Multi-Factor Authentication (MFA) inschakelen](#1-enable-azure-ad-multi-factor-authentication-mfa)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Beveiligen tegen bedreigingen](#2-protect-against-threats)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Microsoft Defender voor Office 365 configureren](#3-configure-microsoft-defender-for-office-365)|||![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[Microsoft Defender configureren voor identiteit](#4-configure-microsoft-defender-for-identity)|||![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[Microsoft 365 Defender in te zetten](#5-turn-on-microsoft-365-defender)|||![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6|[Mobiele Intune-app-beveiliging configureren voor telefoons en tablets](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7|[MFA en voorwaardelijke toegang configureren voor gasten, met inbegrip van Intune-app-beveiliging](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8|[Pc's registreren voor apparaatbeheer en compatibele pc's vereisen](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9|[Uw netwerk optimaliseren voor cloudconnectiviteit](#9-optimize-your-network-for-cloud-connectivity)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[Gebruikers wegwijs maken](#10-train-users)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11|[Aan de slag met Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security)|||![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12|[Op bedreigingen controleren en actie ondernemen](#12-monitor-for-threats-and-take-action)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

Controleer voordat u begint uw [Microsoft 365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) in het Microsoft 365-beveiligingscentrum. Vanuit een gecentraliseerd dashboard kunt u de beveiliging van uw Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur controleren en verbeteren. U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingstaken (zoals het weergeven van rapporten) of het oplossen van aanbevelingen met een toepassing of software van derden. De aanbevolen taken in dit artikel verhogen uw score.

![Schermafbeelding van Microsoft Secure Score](../media/secure-score.png)

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1: Azure AD Multi-Factor Authentication (MFA) inschakelen

Het beste wat u kunt doen om de beveiliging voor werknemers die thuis werken te verbeteren, is MFA in te zetten. Als u nog geen processen hebt, kunt u deze als een pilot voor noodgevallen behandelen en ervoor zorgen dat er ondersteuningsmedewerkers klaar staan om werknemers te helpen die vast komen te zitten. Omdat u waarschijnlijk geen hardwarebeveiligingsapparaten kunt distribueren, gebruikt u authenticatie via Windows Hello en apps voor smartphone-verificatie, zoals Microsoft Authenticator.

Normaal gesproken raadt Microsoft aan gebruikers 14 dagen de tijd te geven hun apparaat te registreren voor meervoudige verificatie voordat ze MFA vereisen. Als het personeel echter plotseling thuis werkt, kunt u MFA vereisen als beveiligingsprioriteit en bereid zijn om gebruikers te helpen die dat nodig hebben.

Het toepassen van dit beleid duurt slechts een paar minuten, maar u bent voorbereid om uw gebruikers de komende dagen te ondersteunen.

****

|Abonnement|Aanbeveling|
|---|---|
|Microsoft 365-abonnementen (zonder Azure AD P1 of P2)|[Schakel standaardinstellingen voor beveiliging in Azure AD in](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). De standaardinstellingen voor beveiliging in Azure AD omvatten MFA voor gebruikers en beheerders.|
|Microsoft 365 E3 (met Azure AD P1)|Gebruik [algemeen beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) om het volgende beleid te configureren: <br/>- [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5 (met Azure AD P2)|Als u gebruikmaakt van Azure AD Identity Protection, begint u het implementeren van de [aanbevolen set beleidsregels voor voorwaardelijke toegang en verwante beleidsregels](./office-365-security/identity-access-policies.md) van Microsoft door de volgende twee beleidsregels te maken:<br/> - [MFA vereisen bij een normaal of hoog risico bij het aanmelden](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [Clients blokkeren die moderne verificatie niet ondersteunen](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [Gebruikers met een hoog risico moeten het wachtwoord wijzigen](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|
|

## <a name="2-protect-against-threats"></a>2: Beschermen tegen bedreigingen

Alle Microsoft 365-abonnementen bevatten diverse functies voor risicobeveiliging. Het kost maar een paar minuten om de beveiliging tegen te gaan voor deze functies.

- Beveiliging tegen malware
- Bescherming tegen schadelijke URL's en bestanden
- Bescherming tegen phishing
- Beveiliging tegen ongewenste e-mail

Zie [Beveiligen tegen bedreigingen in Office 365](office-365-security/protect-against-threats.md) voor richtlijnen die u als uitgangspunt kunt gebruiken.

## <a name="3-configure-microsoft-defender-for-office-365"></a>3: Microsoft Defender voor Office 365 configureren

Microsoft Defender voor Office 365, inbegrepen in Microsoft 365 E5 en Office 365 E5, beschermt uw organisatie tegen schadelijke bedreigingen in plaats van e-mailberichten, koppelingen (URL's) en samenwerkingshulpmiddelen. De configuratie kan enkele uren duren.

Microsoft Defender voor Office 365:

- Beschermt uw organisatie in realtime tegen onbekende e-mailrisico's door intelligente systemen te gebruiken die bijlagen en koppelingen voor schadelijke inhoud controleren. Deze geautomatiseerde systemen bevatten een krachtig detonatieplatform, heuristics en machine learning-modellen.
- Beschermt uw organisatie wanneer gebruikers samenwerken en bestanden delen door schadelijke bestanden in teamsites en documentbibliotheken te identificeren en te blokkeren.
- Hiermee worden machine learning-modellen en geavanceerde imitatie-detectiealgoritmen toegepast om phishing-aanvallen om te keren.

Zie Defender voor [Office 365](office-365-security/office-365-atp.md)voor een overzicht, inclusief een overzicht van de abonnementen.

Uw globale beheerder kan deze beveiligingen configureren:

- [Beleid voor veilige koppelingen instellen](office-365-security/set-up-atp-safe-links-policies.md)
- [Algemene instellingen voor veilige koppelingen configureren](office-365-security/configure-global-settings-for-safe-links.md)
- [Beleid voor veilige bijlagen instellen](office-365-security/set-up-atp-safe-attachments-policies.md)

U moet samenwerken met uw Exchange Online-beheerder en de SharePoint Online-beheerder om Defender voor Office 365 te configureren voor deze werkbelastingen:

- [ATP voor SharePoint, OneDrive en Microsoft Teams](office-365-security/atp-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4: Microsoft Defender configureren voor identiteit

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) is een cloudbeveiligingsoplossing die gebruikmaakt van uw on-premises Active Directory-signalen om geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadwillende acties van binnenuit die zijn gericht op uw organisatie, te identificeren, te detecteren en te onderzoeken. Focus hier vervolgens op, omdat hiermee uw on-prem en uw cloudinfrastructuur worden beschermd, geen afhankelijkheden of vereisten zijn en direct voordeel kunnen bieden.

- Zie [Snelstarts voor Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) voor identiteit om snel te installeren
- Bekijk [de video: Inleiding tot Microsoft Defender voor identiteit](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- De drie [fasen van de implementatie van Microsoft Defender voor identiteit bekijken](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5: Microsoft 365 Defender in te zetten

Nu u Microsoft Defender voor Office 365 en Microsoft Defender voor identiteit hebt geconfigureerd, kunt u de gecombineerde signalen van deze mogelijkheden in één dashboard bekijken. [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) brengt waarschuwingen, incidenten, geautomatiseerd onderzoek en reactie samen, en geavanceerd zoeken naar werkbelastingen (Microsoft Defender for Identity, Defender voor Office 365, Microsoft Defender voor Eindpunt en Microsoft Cloud App-beveiliging) in één deelvenster [security.microsoft.com.](https://security.microsoft.com)

![Afbeelding van MTP-dashboard](../media/top-ten-security-remote-work-mtp-dashboard.png)

Schakel MTP in nadat u een of meer van uw Defender voor Office 365-services hebt geconfigureerd. Nieuwe functies worden voortdurend toegevoegd aan MTP. overweeg om preview-functies te ontvangen.

- [Meer informatie over MTP](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [MTP in te zetten](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
- [Preview-functies gebruiken](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: Intune Mobile-app-beveiliging configureren voor telefoons en tablets

Met Microsoft Intune Mobile Application Management (MAM) kunt u de gegevens van uw organisatie op telefoons en tablets beheren en beschermen zonder deze apparaten te beheren. Het werkt als volgende:

- U maakt een App Protection Policy (APP) dat bepaalt welke apps op een apparaat worden beheerd en welk gedrag is toegestaan (zoals voorkomen dat gegevens uit een beheerde app worden gekopieerd naar een niet-beheerde app). U maakt één beleid voor elk platform (iOS, Android).
- Nadat u het beveiligingsbeleid voor apps hebt gemaakt, dwingt u deze af door in Azure AD een regel voor voorwaardelijke toegang te maken die goedgekeurde apps en app-gegevensbescherming vereist.

Beleid voor app-beveiliging bevat een groot aantal instellingen. Gelukkig is het niet nodig om meer te weten te komen over elke instelling en de opties bij te stellen. Microsoft maakt het gemakkelijk om een configuratie van instellingen toe te passen door beginpunten aan te bevelen. Het [Framework voor gegevensbescherming met behulp van beleidsregels voor app-beveiliging](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) bevat drie niveaus waar uit kunt kiezen.

Nog beter is het dat Microsoft dit beveiligings framework voor apps coördineren met een set voorwaardelijke toegang en verwante beleidsregels. Het is zelfs raadzaam dat alle organisaties het gebruiken als uitgangspunt. Als u MFA hebt geïmplementeerd volgens de richtlijnen in dit artikel, bent u halverwege.

Voor het configureren van mobiele app-beveiliging gebruikt u de richtlijnen in [common identity- en apparaattoegangsbeleid:](./office-365-security/identity-access-policies.md)

 1. Gebruik de [richtlijnen voor het beschermen van app-gegevens](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) om beleid te maken voor iOS en Android. Niveau 2 (verbeterde gegevensbescherming) wordt aanbevolen voor basislijnbeveiliging.
 2. Maak een regel voor voorwaardelijke toegang om [goedgekeurde apps en APP-beveiliging te vereisen.](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: MFA en voorwaardelijke toegang configureren voor gasten, waaronder intune mobiele app-beveiliging

Laten we er vervolgens voor zorgen dat u kunt blijven samenwerken en met gasten kunt werken. Als u het Microsoft 365 E3-abonnement gebruikt en u MFA voor alle gebruikers hebt geïmplementeerd, bent u klaar.

Als u het Microsoft 365 E5-abonnement gebruikt en gebruik maakt van Azure Identity Protection voor op risico's gebaseerde MFA, moet u een paar aanpassingen doen (omdat de beveiliging van Azure AD-identiteit niet wordt uitgebreid naar gasten):

- Maak een nieuwe regel voor voorwaardelijke toegang om MFA altijd te vereisen voor gasten en externe gebruikers.
- Werk de risicogebaseerde MFA-regel voor voorwaardelijke toegang bij om gasten en externe gebruikers uit te sluiten.

Gebruik de richtlijnen in [Het algemene](./office-365-security/identity-access-policies-guest-access.md) beleid bijwerken om gast- en externe toegang toe te staan en te beschermen om inzicht te krijgen in de manier waarop gasttoegang met Azure AD werkt en om het betreffende beleid bij te werken.

Het beveiligingsbeleid voor mobiele apps van Intune dat u hebt gemaakt, samen met de regel voor voorwaardelijke toegang om goedgekeurde apps en APP-beveiliging te vereisen, zijn van toepassing op gastaccounts en helpen uw organisatiegegevens te beschermen.

> [!NOTE]
> Als u al pc's hebt geregistreerd bij apparaatbeheer om compatibele pc's te vereisen, moet u ook gastaccounts uitsluiten van de regel voor voorwaardelijke toegang die apparaat compliance afdwingt.

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: Pc's inschrijven bij apparaatbeheer en compatibele pc's vereisen

Er zijn verschillende methoden om de apparaten van uw personeel in te schrijven. Elke methode is afhankelijk van de eigendomsvereisten (persoonlijk of zakelijk) van het apparaat, het apparaattype (iOS, Windows, Android) en de beheervereisten (reset, affiniteit, vergrendeling). Dit kan even duren. Meer informatie: [Apparaten registreren in Microsoft Intune.](https://docs.microsoft.com/mem/intune/enrollment/)

De snelste manier om te werken is door automatische registratie in [te stellen voor Windows 10-apparaten.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

U kunt ook profiteren van deze zelfstudies:

- [AutoPilot gebruiken om Windows-apparaten in te schrijven in Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [De functies voor het registreren van zakelijke apparaten van Apple in Apple Business Manager (ABM) gebruiken om iOS-/iPadOS-apparaten in te schrijven bij Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

Nadat apparaten zijn ingeschreven, gebruikt u de richtlijnen in [beleidsregels voor](./office-365-security/identity-access-policies.md) algemene identiteit en apparaattoegang om dit beleid te maken:

- [Beleid voor apparaat compliance definiëren:](./office-365-security/identity-access-policies.md#define-device-compliance-policies) de aanbevolen instellingen voor Windows 10 omvatten het vereisen van antivirusbescherming. Als u Microsoft 365 E5 hebt, gebruikt u Microsoft Defender voor het eindpunt om de status van werknemersapparaten te controleren. Zorg ervoor dat compliancebeleid voor andere besturingssystemen antivirusbescherming en eindpuntbeveiligingssoftware bevat.
- [Compatibele pc's vereisen:](./office-365-security/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) dit is de regel voor voorwaardelijke toegang in Azure AD die het nalevingsbeleid voor apparaten afdwingt.

Slechts één organisatie kan een apparaat beheren, dus zorg ervoor dat u gastaccounts uitsluit van de regel voor voorwaardelijke toegang in Azure AD. Als u gasten en externe gebruikers niet uitsluit van beleid waarvoor apparaat compliance is vereist, worden deze gebruikers geblokkeerd door dit beleid. Zie Het algemene beleid bijwerken om gast- en externe toegang toe te staan en [te beschermen voor meer informatie.](./office-365-security/identity-access-policies-guest-access.md)

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: Uw netwerk optimaliseren voor cloudconnectiviteit

Als u snel wilt dat de meeste werknemers vanuit huis kunnen werken, kan deze plotseling veranderende connectiviteitspatronen een grote invloed hebben op de bedrijfsnetwerkinfrastructuur. Veel netwerken zijn geschaald en ontworpen voordat cloudservices werden in gebruik genomen. In veel gevallen zijn netwerken tolerant van externe medewerkers, maar ze zijn niet ontworpen om op afstand door alle gebruikers tegelijk te worden gebruikt.

Netwerkelementen zoals VPN-factoren, centrale netwerkingressieapparatuur (zoals proxies en apparaten voor preventie van gegevensverlies), centrale internetbandbreedte, backhaul MPLS-circuits, NAT-mogelijkheden en dergelijke worden plotseling belast door de belasting van het hele bedrijf die deze gebruikt. Het resultaat is slechte prestaties en productiviteit in combinatie met slechte gebruikerservaring voor gebruikers die zich aanpassen aan het werk vanuit huis.

Sommige beveiligingen die gewoonlijk worden geboden door het routeren van verkeer via een bedrijfsnetwerk, worden geleverd door de cloud-apps die uw gebruikers gebruiken. Als u deze stap in dit artikel hebt bereikt, hebt u een reeks geavanceerde cloudbeveiligingsbesturingselementen geïmplementeerd voor Microsoft 365-services en -gegevens. Als deze besturingselementen zijn gebruikt, bent u mogelijk klaar om verkeer van externe gebruikers rechtstreeks naar Office 365 te routen. Als u nog steeds een VPN-koppeling nodig hebt voor toegang tot andere toepassingen, kunt u de prestaties en gebruikerservaring enorm verbeteren door het implementeren van gesplitste tunneling. Als u in uw organisatie tot overeenstemming bent gekomen, kan dit binnen een dag worden gedaan door een goed gecoördineerde netwerkteam.

Zie de volgende bronnen op Documenten voor meer informatie:

- [Overzicht: Connectiviteit optimaliseren voor externe gebruikers met behulp van VPN gesplitste tunneling](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Vpn-gesplitste tunneling voor Office 365 implementeren](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Recente blogartikelen over dit onderwerp:

- [Snel verkeer optimaliseren voor externe medewerkers& de belasting van uw infrastructuur verminderen](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Alternatieve manieren voor beveiligingsmedewerkers en IT om moderne beveiligingsbesturingselementen te realiseren in de huidige unieke scenario's voor werken op afstand](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10: Gebruikers trainen

Trainingsgebruikers kunnen uw gebruikers en het team met beveiligingsbewerkingen veel tijd en frustraties besparen. Slimme gebruikers openen minder snel bijlagen of klikken op koppelingen in twijfelachtige e-mailberichten en ze vermijden dan waarschijnlijk verdachte websites.

Het handboek Marketingcampagne van Harvard [School biedt](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) uitstekende richtlijnen voor het creëren van een sterke beveiligingscultuur binnen uw organisatie, waaronder training voor het identificeren van phishing-aanvallen.

Microsoft 365 biedt de volgende informatiebronnen om gebruikers in uw organisatie op de hoogte te stellen:

****

|Concept|Resources|
|---|---|
|Microsoft 365|[Aanpasbare leerroutes](https://docs.microsoft.com/office365/customlearning/) <p>Deze bronnen kunnen u helpen bij het organiseren van trainingen voor eindgebruikers in uw organisatie|
|Microsoft 365-beveiliging|[Leermodule: Uw organisatie beveiligen met ingebouwde, intelligente beveiliging van Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Met deze module kunt u beschrijven hoe Microsoft 365-beveiligingsfuncties samenwerken en de voordelen van deze beveiligingsfuncties duidelijk maken.|
|Meervoudige verificatie|[Verificatie in twee stappen: Wat is de extra verificatiepagina?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Dit artikel helpt eindgebruikers te begrijpen wat meervoudige verificatie is en waarom deze in uw organisatie wordt gebruikt.|
|

Naast deze richtlijnen raadt Microsoft uw gebruikers aan de acties uit te voeren die in dit artikel worden beschreven: Bescherm uw account en apparaten [tegen hackers en malware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Dit zijn onder andere de volgende acties:

- Sterke wachtwoorden gebruiken
- Apparaten beveiligen
- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's (voor niet-beherende apparaten)

Microsoft raadt gebruikers ook aan hun persoonlijke e-mailaccounts te beveiligen door de acties uit te voeren die worden aanbevolen in de volgende artikelen:

- [Uw e-mailaccount Outlook.com beschermen](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Uw Gmail-account beveiligen met verificatie in twee stappen](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Aan de slag met Microsoft Cloud App Security

[Microsoft Cloud App Security biedt](https://docs.microsoft.com/cloud-app-security) uitgebreide zichtbaarheid, controle over gegevensreizen en geavanceerde analyses om cyberaanvallen in al uw cloudservices te identificeren en te bestrijden. Zodra u aan de slag gaat met Cloud App Security, wordt beleidsregels voor afwijkingsdetectie automatisch ingeschakeld, maar voor Cloud App-beveiliging is een eerste leerperiode van zeven dagen nodig, waarin niet alle waarschuwingen voor het detecteren van anomaly-detectie worden verhoogd.

Ga nu aan de slag met Cloud App Security. Later kunt u geavanceerdere controle en besturingselementen instellen.

- [Snelstart: Aan de slag met Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [Direct analyse van analyse en afwijkingsdetectie](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Meer informatie over Beveiliging van Microsoft Cloud-apps](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Nieuwe functies en mogelijkheden bekijken](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Basisinstructies voor installatie bekijken](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: Op bedreigingen controleren en actie ondernemen

Microsoft 365 bevat verschillende manieren om de status te controleren en de juiste acties uit te voeren. Het beste uitgangspunt is het Microsoft 365-beveiligingscentrum, waar u de Microsoft Secure Score van uw organisatie kunt bekijken, en alle waarschuwingen of entiteiten die uw [https://security.microsoft.com](https://security.microsoft.com) aandacht vereisen. [](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

- [Aan de slag met het Microsoft 365-beveiligingscentrum](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [Rapporten controleren en bekijken](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [De beveiligingsportals in Microsoft 365 bekijken](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>Volgende stappen

Gefeliciteerd! U hebt snel enkele van de belangrijkste beveiligingsbeschermingen geïmplementeerd en uw organisatie is veel veiliger. U kunt nu nog verder gaan met mogelijkheden voor risicobeveiliging (waaronder Microsoft Defender voor Eindpunt), voorzieningen voor gegevensclassificatie en beveiliging en het beveiligen van beheeraccounts. Zie [Microsoft 365 Security for Business Decision Makers (BDM's)](Microsoft-365-security-for-bdm.md)voor een diepere, methodische reeks beveiligingsaanbevelingen voor Microsoft 365.

Ga ook naar het nieuwe beveiligingscentrum van Microsoft op [docs.microsoft.com/security.](https://docs.microsoft.com/security)
