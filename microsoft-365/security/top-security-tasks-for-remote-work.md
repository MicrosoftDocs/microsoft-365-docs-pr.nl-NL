---
title: Top 12 taken voor beveiligingsteams ter ondersteuning van thuiswerken
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: Bescherm uw zakelijke e-mail en gegevens tegen cyberbedreigingen, waaronder ransomware, phishing en schadelijke bijlagen.
ms.openlocfilehash: 04f59d4f87bda9460930b54818d2ab43933d11e5
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943541"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>Top 12 taken voor beveiligingsteams ter ondersteuning van thuiswerken

Als u net als [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) bent en plotseling merkt dat u een voornamelijk thuiswerkende werknemers ondersteunt, willen we u helpen ervoor te zorgen dat uw organisatie zo veilig mogelijk werkt. Dit artikel geeft prioriteit aan taken om beveiligingsteams te helpen de belangrijkste beveiligingsmogelijkheden zo snel mogelijk te implementeren. 

Als u een kleine of middelgrote organisatie bent die een van de bedrijfsplannen van Microsoft gebruikt, raadpleegt u deze bronnen in plaats daarvan:
- [Top 10 manieren om Office 365- en Microsoft 365-abonnementen te beveiligen](../admin/security-and-compliance/secure-your-business-data.md) 
- [Microsoft 365 voor campagnes](https://docs.microsoft.com/microsoft-365/campaigns/?view=o365-worldwide) (bevat een aanbevolen beveiligingsconfiguratie voor Microsoft 365 Business)

  
Voor klanten die onze bedrijfsplannen gebruiken, raadt Microsoft u aan de taken in de volgende tabel uit te voeren die van toepassing zijn op uw serviceplan. Als u in plaats van een Microsoft 365-ondernemingsabonnement koopt, abonnementen te combineren, houdt u het volgende op:
- Microsoft 365 E3 bevat Enterprise Mobility + Security (EMS) E3 en Azure AD P1
- Microsoft 365 E5 bevat EMS E5 en Azure AD P2
  
||**Taak**| Alle Office 365 Enterprise-abonnementen|**Microsoft 365 E3** |**Microsoft 365 E5**|
|:-----|:-----|:-----|:-----|:-----|
|1      |[Azure Multi-Factor Authentication (MFA) inschakelen](#1-enable-azure-multi-factor-authentication-mfa)   |   ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)   | ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|2     | [Beveiligen tegen bedreigingen](#2-protect-against-threats) |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png) |  ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)       | ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|3      |  [Geavanceerde bedreigingsbeveiliging van Office 365 configureren](#3-configure-office-365-advanced-threat-protection)  |   |      |  ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|4      | [Azure Advanced Threat Protection (ATP) configureren](#4-configure-azure-advanced-threat-protection)   |   |      |  ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|5     |   [Microsoft Advanced Threat Protection inschakelen](#5-turn-on-microsoft-advanced-threat-protection)  |  |      | ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|6      | [Intune-beveiliging voor mobiele apps configureren voor telefoons en tablets](#6-configure-intune-mobile-app-protection-for-phones-and-tablets) |    |  ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)       |  ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|7     | [MFA en voorwaardelijke toegang configureren voor gasten, inclusief intune-app-beveiliging](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)  |    |  ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)     | ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|8      |  [Pc's inschrijven voor apparaatbeheer en vereisen compatibele pc's](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)   |  | ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)        | ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|9      | [Optimaliseer uw netwerk voor cloudconnectiviteit](#9-optimize-your-network-for-cloud-connectivity)  |  ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|10   | [Treingebruikers](#10-train-users) |    ![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|11 |[Aan de slag met Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security) |  |  |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)   |
|12 |[Controleren op bedreigingen en actie ondernemen](#12-monitor-for-threats-and-take-action) |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Opgenomen](../media/d238e041-6854-4a78-9141-049224df0795.png)  |
| | | |


   
Controleer voordat u begint de [Microsoft 365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) in het Microsoft 365-beveiligingscentrum. Vanuit een gecentraliseerd dashboard u de beveiliging voor uw Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur bewaken en verbeteren. U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingsgerelateerde taken (zoals het bekijken van rapporten) of het aanpakken van aanbevelingen met een toepassing of software van derden. De aanbevolen taken in dit artikel verhogen uw score.
  
![Schermafbeelding van microsoft secure score](../media/secure-score.png)
  
## <a name="1-enable-azure-multi-factor-authentication-mfa"></a>1: Azure Multi-Factor Authentication (MFA) inschakelen
Het beste wat u doen om de beveiliging te verbeteren voor werknemers die vanuit huis werken, is MFA inschakelen. Als u nog geen processen op zijn plaats, behandelen als een noodpiloot en zorg ervoor dat u ondersteuning mensen klaar om werknemers die vast komen te helpen. Aangezien u waarschijnlijk geen hardwarebeveiligingsapparaten distribueren, gebruikt u Windows Hello biometrie en smartphoneauthenticatie-apps zoals Microsoft Authenticator.

Normaal gesproken raadt Microsoft gebruikers aan om hun apparaat 14 dagen te registreren voor Multi-Factor Authentication voordat u MFA nodig hebt. Als uw personeel echter plotseling vanuit huis werkt, moet u MFA als beveiligingsprioriteit nodig hebben en bereid zijn om gebruikers te helpen die het nodig hebben. 

Het toepassen van dit beleid duurt slechts enkele minuten, maar wees bereid om uw gebruikers te ondersteunen in de komende dagen.  


|Plannen  |Aanbeveling  |
|---------|---------|
|Microsoft 365-abonnementen (zonder Azure AD P1 of P2)     |[Beveiligingsstandaardinstellingen inschakelen in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Beveiligingsstandaarden in Azure AD bevatten MFA voor gebruikers en beheerders.   |
|Microsoft 365 E3 (met Azure AD P1)     | Gebruik [algemene beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) om het volgende beleid te configureren: <br>- [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (met Azure AD P2)     | Als u gebruikmaakt van Azure AD-identiteitsbeveiliging, begint u met het implementeren van de [aanbevolen set voorwaardelijke toegang en bijbehorende beleidsregels van](../enterprise/identity-access-policies.md) Microsoft door deze twee beleidsregels te maken:<br> - [MFA vereisen wanneer het aanmeldingsrisico gemiddeld of hoog is](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Clients blokkeren die geen moderne verificatie ondersteunen](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Gebruikers met een hoog risico moeten het wachtwoord wijzigen](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |


  
## <a name="2-protect-against-threats"></a>2: Beschermen tegen bedreigingen

Alle Microsoft 365-abonnementen bevatten verschillende functies voor bedreigingsbescherming. Bumping up bescherming voor deze functies duurt slechts een paar minuten.
- Beveiliging tegen malware
- Bescherming tegen schadelijke URL's en bestanden
- Bescherming tegen phishing
- Beveiliging tegen ongewenste e-mail

Zie [Beschermen tegen bedreigingen in Office 365](office-365-security/protect-against-threats.md) voor richtlijnen die u als uitgangspunt gebruiken.
    

## <a name="3-configure-office-365-advanced-threat-protection"></a>3: Geavanceerde bedreigingsbeveiliging van Office 365 configureren

Office 365 Advanced Threat Protection (ATP), opgenomen in Microsoft 365 E5 en Office 365 E5, beschermt uw organisatie tegen schadelijke bedreigingen van e-mailberichten, koppelingen (URL's) en samenwerkingstools. Dit kan enkele uren duren om te configureren.

Office 365 ATP:
- Beschermt uw organisatie in realtime tegen onbekende e-mailbedreigingen door intelligente systemen te gebruiken die bijlagen en koppelingen inspecteren op schadelijke inhoud. Deze geautomatiseerde systemen omvatten een robuust detonatieplatform, heuristiek en machine learning-modellen. 
- Beschermt uw organisatie wanneer gebruikers samenwerken en bestanden delen, door schadelijke bestanden in teamsites en documentbibliotheken te identificeren en te blokkeren. 
- Past machine learning-modellen en geavanceerde imitatie-detectie-algoritmen toe om phishing-aanvallen af te wenden. 

Zie [Office 365 Advanced Threat Protection](office-365-security/office-365-atp.md)voor een overzicht, inclusief een overzicht van de abonnementen.

Uw globale beheerder kan deze beveiligingen configureren:
- [ATP Safe Links instellen](office-365-security/set-up-atp-safe-links-policies.md)
- [Beleid voor veilige bijlagen in ATP instellen](office-365-security/set-up-atp-safe-attachments-policies.md)
- [Een aangepaste lijst instellen met URL's die niet opnieuw mogen worden geschreven](office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
- [Een aangepaste lijst met geblokkeerde URL's instellen](office-365-security/set-up-a-custom-blocked-urls-list-wtih-atp.md)

U moet samenwerken met uw Exchange Online-beheerder en SharePoint Online-beheerder om ATP voor deze workloads te configureren:
- [ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen](office-365-security/turn-on-atp-for-spo-odb-and-teams.md)

## <a name="4-configure-azure-advanced-threat-protection"></a>4: Azure Advanced Threat Protection configureren

[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) is een cloudgebaseerde beveiligingsoplossing die uw on-premises Active Directory-signalen gebruikt om geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke insideracties gericht op uw organisatie te identificeren, detecteren en onderzoeken. Focus op dit volgende omdat het uw on-prem en uw cloudinfrastructuur beschermt, geen afhankelijkheden of vereisten heeft en onmiddellijk voordeel kan bieden.


- Bekijk [Azure ATP Quickstarts](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) om snel te worden ingesteld 
- [Bekijk video: Inleiding tot Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Bekijk de [drie fasen van Azure ATP-implementatie](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-advanced-threat-protection"></a>5: Microsoft Advanced Threat Protection inschakelen

Nu u Office 365 ATP en Azure ATP hebt geconfigureerd, u de gecombineerde signalen van deze mogelijkheden in één dashboard bekijken. [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) (MTP) brengt waarschuwingen, incidenten, geautomatiseerd onderzoek en respons en geavanceerde jacht over workloads (Azure ATP, Office 365 ATP, Microsoft Defender ATP en Microsoft Cloud App Security) samen in één deelvenster op [security.microsoft.com.](https://security.microsoft.com) 
<br>

![Afbeelding van het MTP-dashboard](../media/top-ten-security-remote-work-mtp-dashboard.png)
<br><br>
Nadat u een of meer van uw geavanceerde services voor bedreigingsbescherming hebt geconfigureerd, schakelt u MTP in. Nieuwe functies worden voortdurend toegevoegd aan MTP; overweeg u zich aan te melden voor preview-functies.

- [Meer informatie over MTP](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [MTP inschakelen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide)
- [Aanmelden voor previewfuncties](https://docs.microsoft.com/microsoft-365/security/mtp/preview?view=o365-worldwide)


## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: Intune-beveiliging voor mobiele apps configureren voor telefoons en tablets

Met Microsoft Intune Mobile Application Management (MAM) u de gegevens van uw organisatie op telefoons en tablets beheren en beveiligen zonder deze apparaten te beheren. Zo werkt het:
- U maakt een app (App) voor app-beveiliging dat bepaalt welke apps op een apparaat worden beheerd en welk gedrag is toegestaan (zoals voorkomen dat gegevens uit een beheerde app worden gekopieerd naar een niet-beheerde app). U maakt één beleid voor elke platorm (iOS, Android).
- Nadat u het beleid voor app-beveiliging hebt gemaakt, u deze afdwingen door een regel voor voorwaardelijke toegang in Azure AD te maken om goedgekeurde apps en app-gegevensbescherming te vereisen.

App-beveiligingsbeleid bevat veel instellingen. Gelukkig hoef je niet elke instelling te leren en de opties af te wegen. Microsoft maakt het eenvoudig om een configuratie van instellingen toe te passen door startpunten aan te bevelen. Het [kader voor gegevensbescherming met app-beveiligingsbeleid](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) bevat drie niveaus waaruit u kiezen. 

Nog beter, Microsoft coördineert dit app-beveiligingsframework met een reeks voorwaardelijke toegang en bijbehorend beleid dat we alle organisaties als uitgangspunt aanbevelen. Als je MFA hebt geïmplementeerd met behulp van de richtlijnen in dit artikel, ben je halverwege!

Als u de beveiliging van mobiele apps wilt configureren, gebruikt u de richtlijnen in [beleid voor algemene identiteits- en apparaattoegangs:](../enterprise/identity-access-policies.md)
 1. Gebruik de richtlijnen [voor het beleid voor gegevensbescherming van APP toepassen](../enterprise/identity-access-policies.md#apply-app-data-protection-policies) om beleid voor iOS en Android te maken. Niveau 2 (verbeterde gegevensbescherming) wordt aanbevolen voor basisbescherming. 
 2. Maak een regel voor voorwaardelijke toegang voor [Goedgekeurde apps en APP-beveiliging vereisen](../enterprise/identity-access-policies.md#require-approved-apps-and-app-protection). 

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: MFA en voorwaardelijke toegang configureren voor gasten, inclusief intune-beveiliging van mobiele apps

Laten we er vervolgens voor zorgen dat u blijven samenwerken en met gasten samenwerken. Als u het Microsoft 365 E3-abonnement gebruikt en MFA voor alle gebruikers hebt geïmplementeerd, bent u ingesteld. 

Als u het Microsoft 365 E5-abonnement gebruikt en u maakt gebruik van Azure Identity Protection voor op risico's gebaseerde MFA, moet u een paar aanpassingen doorvoeren (omdat azure AD-identiteitsbescherming niet geldt voor gasten):
- Maak een nieuwe regel voor voorwaardelijke toegang om MFA altijd voor gasten en externe gebruikers te vereisen.
- Werk de op risico's gebaseerde MFA-regel voor voorwaardelijke toegang bij om gasten en externe gebruikers uit te sluiten.

Gebruik de richtlijnen bij [Het bijwerken van het algemene beleid om gast- en externe toegang toe](../enterprise/identity-access-policies-guest-access.md) te staan en te beschermen om te begrijpen hoe gasttoegang werkt met Azure AD en om het getroffen beleid bij te werken. 

Het intune-beleid voor mobiele apps dat u hebt gemaakt, samen met de regel voor voorwaardelijke toegang om goedgekeurde apps en APP-beveiliging te vereisen, is van toepassing op gastenaccounts en helpt uw organisatiegegevens te beschermen. 

**Opmerking:** als u pc's al hebt ingeschreven voor apparaatbeheer om compatibele pc's te vereisen, moet u ook gastaccounts uitsluiten van de regel voor voorwaardelijke toegang die de naleving van het apparaat afdwingt. 


## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: Pc's inschrijven voor apparaatbeheer en compatibele pc's vereisen

Er zijn verschillende methoden om de apparaten van uw personeel in te schrijven. Elke methode is afhankelijk van het eigendom van het apparaat (persoonlijk of zakelijk), apparaattype (iOS, Windows, Android) en beheervereisten (resets, affiniteit, vergrendeling). Dit kan een beetje tijd in beslag nemen om uit te zoeken. Zie: [Apparaten inschrijven in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/). 

De snelste manier om aan de slag te gaan is het [instellen van automatische inschrijving voor Windows 10-apparaten.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) 

U ook profiteren van deze tutorials:
- [Autopilot gebruiken om Windows-apparaten in te schrijven in Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Gebruik de functies Corporate Device Enrollment van Apple in Apple Business Manager (ABM) om iOS/iPadOS-apparaten in te schrijven in Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

Nadat u apparaten hebt ingeschreven, gebruikt u de richtlijnen in [beleid voor algemene identiteit en toegang tot apparaten](../enterprise/identity-access-policies.md) om dit beleid te maken:
- [Beleid](../enterprise/identity-access-policies.md#define-device-compliance-policies) voor naleving van apparaten definiëren : de aanbevolen instellingen voor Windows 10 vereisen onder meer antivirusbescherming. Als u Microsoft 365 E5 hebt, gebruikt u Microsoft Defender Advanced Threat Protection om de status van werknemersapparaten te controleren. Zorg ervoor dat nalevingsbeleid voor andere besturingssystemen antivirusbeveiliging en end-point beveiligingssoftware omvat. 
- [Compatibele pc's vereisen:](../enterprise/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) dit is de regel voor voorwaardelijke toegang in Azure AD die het nalevingsbeleid voor apparaten afdwingt.

Slechts één organisatie kan een apparaat beheren, dus sluit gastaccounts uit van de regel voor voorwaardelijke toegang in Azure AD. Als u gast- en externe gebruikers niet uitsluit van beleid waarvoor apparaatnaleving vereist is, worden deze gebruikers met dit beleid geblokkeerd. Zie [Het algemene beleid bijwerken om gast- en externe toegang toe te staan en te beschermen voor](../enterprise/identity-access-policies-guest-access.md)meer informatie.

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: Optimaliseer uw netwerk voor cloudconnectiviteit

Als u het grootste deel van uw werknemers snel vanuit huis laat werken, kan deze plotselinge omschakeling van connectiviteitspatronen een aanzienlijke impact hebben op de bedrijfsnetwerkinfrastructuur. Veel netwerken werden geschaald en ontworpen voordat cloudservices werden overgenomen. In veel gevallen zijn netwerken tolerant ten opzichte van externe werknemers, maar zijn ze niet ontworpen om op afstand door alle gebruikers tegelijk te worden gebruikt.

Netwerkelementen zoals VPN-concentrators, centrale netwerkuitgangsapparatuur (zoals proxy's en apparaten voor het voorkomen van gegevensverlies), centrale internetbandbreedte, backhaul MPLS-circuits, NAT-mogelijkheden enzovoort, worden plotseling onder enorme druk gezet door de belasting van het hele bedrijf dat ze gebruikt. Het eindresultaat is slechte prestaties en productiviteit in combinatie met een slechte gebruikerservaring voor gebruikers die zich aanpassen aan het werken vanuit huis.

Sommige van de beveiligingen die traditioneel zijn geboden door het routeren van verkeer terug via een bedrijfsnetwerk worden geleverd door de cloud-apps die uw gebruikers openen. Als u deze stap in dit artikel hebt bereikt, hebt u een reeks geavanceerde cloudbeveiligingsbesturingselementen voor Microsoft 365-services en -gegevens geïmplementeerd. Met deze besturingselementen u het verkeer van externe gebruikers rechtstreeks naar Office 365 routeren. Als u nog steeds een VPN-link nodig hebt voor toegang tot andere toepassingen, u uw prestaties en gebruikerservaring sterk verbeteren door split tunneling te implementeren. Zodra u overeenstemming bereikt in uw oganization, kan dit binnen een dag worden bereikt door een goed gecoördineerd netwerkteam.


Zie deze bronnen op Documenten voor meer informatie:
- [Overzicht: Connectiviteit optimaliseren voor externe gebruikers met VPN split tunneling](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [VPN-splittunneling implementeren voor Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Recente blog artikelen over dit onderwerp:
- [Zo snel het verkeer voor externe medewerkers optimaliseren & de belasting van uw infrastructuur te verminderen](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Alternatieve manieren voor beveiligingsprofessionals en IT om moderne beveiligingscontroles te realiseren in de unieke scenario's voor werken op afstand](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)


## <a name="10-train-users"></a>10: Treingebruikers

Het trainen van gebruikers kan uw gebruikers en beveiligingsteam veel tijd en frustratie besparen. Savvy gebruikers hebben minder kans om bijlagen te openen of klik op links in twijfelachtige e-mailberichten, en ze hebben meer kans om verdachte websites te vermijden. 

Het Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) biedt uitstekende richtlijnen voor het opzetten van een sterke cultuur van beveiligingsbewustzijn binnen uw organisatie, inclusief het trainen van gebruikers om phishing-aanvallen te identificeren. 

Microsoft 365 biedt de volgende bronnen om gebruikers in uw organisatie te informeren:

|Concept  |Resources  |
|---------|---------|
|Microsoft 365     |[Aanpasbare leertrajecten](https://docs.microsoft.com/office365/customlearning/) <p>Met deze bronnen u training samenstellen voor eindgebruikers in uw organisatie        |
|Microsoft 365-beveiliging |[Leermodule: beveilig uw organisatie met ingebouwde, intelligente beveiliging van Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Met deze module u beschrijven hoe microsoft 365-beveiligingsfuncties samenwerken en de voordelen van deze beveiligingsfuncties verwoorden. |
|Meervoudige verificatie     | [Verificatie in twee stappen: wat is de extra verificatiepagina?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Dit artikel helpt eindgebruikers te begrijpen wat multi-factor authenticatie is en waarom het wordt gebruikt in uw organisatie.    |
| | |

Naast deze richtlijnen raadt Microsoft uw gebruikers aan de in dit artikel beschreven acties te ondernemen: [Bescherm uw account en apparaten tegen hackers en malware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Deze acties omvatten:
  
- Sterke wachtwoorden gebruiken
    
- Apparaten beveiligen 
    
- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's (voor niet-beheerde apparaten)
    
Microsoft raadt gebruikers ook aan hun persoonlijke e-mailaccounts te beschermen door de in de volgende artikelen aanbevolen acties uit te voeren:
  
- [Uw Outlook.com e-mailaccount beschermen](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba.aspx)
    
- [Bescherm je Gmail-account met verificatie in twee stappen](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)


## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Aan de slag met Microsoft Cloud App Security

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) biedt uitgebreide zichtbaarheid, controle over gegevensreizen en geavanceerde analyses om cyberbedreigingen in al uw cloudservices te identificeren en te bestrijden. Zodra u aan de slag gaat met Cloud App Security, worden het beleid voor anomaliedetectie automatisch ingeschakeld, maar Cloud App Security heeft een eerste leerperiode van zeven dagen waarin niet alle waarschuwingen voor anomaliedetectie worden verhoogd.

Ga nu aan de slag met Cloud App Security. Later u meer geavanceerde controle en controles instellen.

- [Snel aan de slag met Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [Krijg onmiddellijk gedragsanalyse en anomaliedetectie](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Meer informatie over Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Bekijk nieuwe functies en mogelijkheden](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Zie basisinstructies voor het instellen](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: Monitor op bedreigingen en actie ondernemen

Microsoft 365 bevat verschillende manieren om de status te controleren en passende acties uit te voeren. Uw beste uitgangspunt is het Microsoft 365-beveiligingscentrum ( ),[https://security.microsoft.com](https://security.microsoft.com)waar u de Microsoft Secure [Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score?view=o365-worldwide)van uw organisatie bekijken en alle waarschuwingen of entiteiten die uw aandacht vereisen.

- [Aan de slag met het Microsoft 365-beveiligingscentrum](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center?view=o365-worldwide)
- [Rapporten controleren en bekijken](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting?view=o365-worldwide)
- [Bekijk de beveiligingsportalen in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>Volgende stappen

Gefeliciteerd! U hebt snel enkele van de belangrijkste beveiligingsbeveiligingen geïmplementeerd en uw organisatie is veel veiliger. Nu bent u klaar om nog verder te gaan met mogelijkheden voor bedreigingsbescherming (waaronder Geavanceerde bedreigingsbescherming van Microsoft Defender), mogelijkheden voor gegevensclassificatie en -bescherming en het beveiligen van administratieve accounts. Zie [Microsoft 365 Security for Business Decision Makers (BDM's) voor](Microsoft-365-security-for-bdm.md)een diepere, methodische set beveiligingsaanbevelingen voor Microsoft 365. 

Bezoek ook het nieuwe beveiligingscentrum van Microsoft op [docs.microsoft.com/security.](https://docs.microsoft.com/security) 
