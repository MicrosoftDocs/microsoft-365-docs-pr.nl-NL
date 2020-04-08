---
title: 'Stap 4: uw gebruikersaccounts toevoegen'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Voeg gebruikersaccounts en groepen rechtstreeks toe aan de Cloud of door ze te synchroniseren met uw on-premises adreslijst.
ms.openlocfilehash: 324d4662f868a4a92693b43c6bc0f75c11f20519
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812047"
---
# <a name="step-4-add-your-user-accounts"></a>Stap 4: uw gebruikersaccounts toevoegen

![Fase 2: identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a>De gebruikersaccounts maken voor de Cloud-identiteit

Voor Cloud-identiteit maakt u uw gebruikers en groepen in Azure Active Directory (Azure AD). U kunt het volgende gebruiken:

- Het Microsoft 365-beheercentrum
- De Azure-portal
- Azure PowerShell

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a>Identiteiten voor hybride identiteit synchroniseren

*Deze stap is vereist voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

In deze sectie synchroniseert u uw on-premises Active Directory Domain Services (AD DS) met de Azure AD-tenant die wordt gebruikt door Office 365, Microsoft Intune en andere Cloud-services die zijn opgenomen in Microsoft 365 Enterprise.

Azure AD Connect is het ondersteunde Microsoft-hulpprogramma dat u helpt bij het synchroniseren van alleen de identiteiten die u echt nodig hebt, van AD DS-omgevingen met één of meerdere forests tot uw Azure AD-tenant. In de volgende afbeelding ziet u het basisproces voor Azure AD Connect-synchronisatie.

![Hoe Azure AD Connect uw on-premises adreslijst synchroniseert met Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. Met Azure AD Connect dat op een server wordt uitgevoerd, wordt AD DS gecontroleerd op wijzigingen in accounts, groepen en contactpersonen.
2. Azure AD Connect stuurt die wijzigingen naar de Azure AD-tenant van uw Microsoft 365-abonnement.

De eerste beslissing in uw hybride identiteitsoplossing is uw verificatievereiste. De volgende opties zijn beschikbaar:

- Met **beheerde verificatie**wordt het verificatieproces voor gebruikersaanmelding door Azure AD afgehandeld. Beheerde verificatie bestaat uit twee methoden: 
    - **Wachtwoord-hash-synchronisatie (PHS)** [aanbevolen en vereist voor enkele Premium-functies]. Dit is de eenvoudigste manier om verificatie in te schakelen voor on-premises adreslijstobjecten in Azure Active Directory. Azure AD Connect haalt het gehashte wachtwoord uit AD DS, voert extra beveiligingsverwerking uit op de wachtwoordhash en synchroniseert het met Azure AD. Zie voor meer informatie [wachtwoord hash-synchronisatie implementeren met Azure AD Connect-synchronisatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).
    - **Pass Through-verificatie (PTA)** biedt een eenvoudige oplossing voor wachtwoordvalidatie voor Azure AD-services. PTA gebruikt een agent die op een of meer on-premises servers wordt uitgevoerd om de gebruikersverificaties rechtstreeks met uw lokale AD DS te valideren. Voor meer informatie raadpleegt u [aanmelden als gebruiker met Azure Active Directory Pass Through-verificatie.
- Met **federatieve verificatie**wordt het verificatieproces omgeleid naar een andere identiteitsprovider via een identiteitsfederatieserver, zoals Active Directory Federation Services (AD FS), voor aanmelding van een gebruiker. De identiteitsprovider kan aanvullende verificatiemethoden bieden, zoals op smartcards gebaseerde verificatie. Zie voor meer informatie [het kiezen van de juiste verificatiemethode voor uw Azure Active Directory hybride identiteitsoplossing](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Bekijk deze video voor een overzicht van identiteitsmodellen en verificatie voor Microsoft 365 Enterprise.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Nadat u de hybride-identiteitsoplossing hebt vastgesteld, downloadt en voert u het [hulpprogramma voor het oplossen van fouten met IdFix Directory-synchronisatie uit om uw AD DS te analyseren op problemen.

Wanneer u alle problemen hebt opgelost die met het hulpprogramma IdFix zijn geïdentificeerd, raadpleegt u [wachtwoord hash-synchronisatie implementeren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) voor hulp bij het installeren van de Azure AD Connect-hulpmiddelen en het configureren van adreslijstsynchronisatie tussen uw on-premises AD DS en de Azure AD-tenant voor uw Microsoft 365-abonnement. Nadat de synchronisatie is gestart, houdt u uw gebruikersaccounts en -groepen bij met uw on-premises-identiteitsprovider, zoals AD DS.

Microsoft biedt een aantal aanbevelingen voor [identiteits- en apparaattoegang](microsoft-365-policies-configurations.md) om te zorgen dat uw personeel veilig en productief blijft. 

- Zie voor meer informatie over de aanbevolen vereisten voor hybride omgevingen de kolom **Active Directory met hash-synchronisatie** onder [vereisten](identity-access-prerequisites.md#prerequisites). 

- Zie de kolom **alleen Cloud** onder [vereisten](identity-access-prerequisites.md#prerequisites)voor aanbevolen vereisten voor alleen Cloud omgevingen.

Wanneer uw on-premises gebruikers en groepen in Azure AD aanwezig zijn, kunt u beginnen met het toewijzen van licenties en het gebruik van productiviteitslasten zoals OneDrive voor Bedrijven en Exchange Online.

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md)<br> [Testlabrichtlijn: pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md) |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sync) voor deze sectie bekijken.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>Synchronisatiestatus bewaken

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*

In deze sectie installeert u een Azure AD Connect Health-agent op elk van uw on-premises AD DS-domeincontrollers om uw identiteitsinfrastructuur en de synchronisatieservices van Azure AD Connect te bewaken. De bewakingsinformatie wordt beschikbaar gesteld in een Azure AD Connect Health-portal waar u waarschuwingen, prestatiebewaking, gebruiksanalyses en andere informatie kunt bekijken.

![Onderdelen van Azure AD Connect Health](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

De belangrijkste ontwerpbeslissing over hoe u Azure AD Connect Health gaat gebruiken, is gebaseerd op hoe u Azure AD Connect gebruikt:

- Als u de optie **beheerde verificatie** gebruikt, begint u met [Azure AD Connect Health gebruiken met synchronisatie](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), om Azure AD Connect Health te begrijpen en te configureren.
- Als u alleen de namen synchroniseert van de accounts en groepen met **federatieve verificatie** met Active Directory Federation Services (AD FS), begint u met [Azure AD Connect Health gebruiken met AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) om Azure AD Connect Health te begrijpen en te configureren.

Wanneer u deze stap hebt voltooid, hebt u:

- De Azure AD Connect Health-agent die is geïnstalleerd op uw on-premises servers van de identiteitsprovider.
- De Azure AD Connect Health-portal met de huidige status van uw on-premises infrastructuur en synchronisatieactiviteiten met de Azure AD-tenant voor uw Microsoft 365- en EMS-abonnementen.

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sync-health) voor deze stap bekijken.



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>Wachtwoordupdates vereenvoudigen

*Deze stap is optioneel voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

In deze sectie staat u gebruikers toe hun wachtwoorden opnieuw in te stellen via Azure Active Directory (Azure AD), die vervolgens wordt gerepliceerd naar uw lokale Active Directory Domain Services (AD DS). Dit proces wordt het terugschrijven van wachtwoorden genoemd. Met het terugschrijven van wachtwoorden hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises AD DS waar de gebruikersaccounts en de bijbehorende kenmerken zijn opgeslagen. Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.

Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de mogelijkheden van Identity Protection-functies, zoals vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een hoog risico op inbreuk van accounts is gedetecteerd.

Zie [Azure AD SSPR met wachtwoord terugschrijven](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) voor meer informatie en configuratie-instructies.

>[!Note]
>Voer een upgrade uit naar de nieuwste versie van Azure AD Connect om te zorgen voor een optimale ervaring en nieuwe functies zodra deze beschikbaar komen. Zie [Aangepaste installatie van Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom) voor meer informatie.
>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md) |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pw-writeback) voor deze stap bekijken.

|||
|:-------|:-----|
|![Stap 5](../media/stepnumbers/Step5.png)| [Groepen gebruiken voor beheer](identity-use-group-management.md) |
