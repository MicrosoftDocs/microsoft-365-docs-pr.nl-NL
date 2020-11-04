---
title: Power BI in uw organisatie
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: Meer informatie over Power BI en hoe gebruikers in uw organisatie deze Business Analytics-service kunnen gebruiken.
ms.openlocfilehash: e549ff25b7db41d6a582b4af0506d67787df7e0d
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906583"
---
# <a name="power-bi-in-your-organization"></a>Power BI in uw organisatie

Op deze pagina wordt beschreven hoe gebruikers in uw organisatie Power BI kunnen gebruiken en hoe u kunt bepalen hoe uw organisatie deze service krijgt.

## <a name="what-is-power-bi"></a>Wat is Power BI?

Met Microsoft Power BI kunnen gebruikers gegevens visualiseren, ontdekkingen delen en samenwerken op intuïtieve en nieuwe manieren. Zie de [website van Power BI](https://powerbi.microsoft.com/en-us/) voor meer informatie.
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Voldoet Power BI aan nationale, regionale en branchespecifieke nalevingsvereisten?

Als u meer wilt weten over naleving voor Power BI, raadpleegt u het [Microsoft Vertrouwenscentrum](https://go.microsoft.com/fwlink/?LinkId=785324).
  
## <a name="how-do-users-sign-up-for-power-bi"></a>Hoe kunnen gebruikers zich registreren voor Power BI?

Als beheerder kunt u zich registreren voor Power BI via de [Power BI-website](https://powerbi.microsoft.com/en-us/). U kunt zich ook registreren via de pagina voor het aanschaffen van services in het Microsoft 365-Beheercentrum. Wanneer beheerders zich registreren voor Power BI, kunnen ze licenties voor gebruikersabonnementen toewijzen aan gebruikers die toegang moeten krijgen.
  
Bovendien kunnen individuele gebruikers in uw organisatie zich registreren voor Power BI via de [Power BI-website](https://powerbi.microsoft.com/en-us/). Wanneer een gebruiker in uw organisatie zich registreert voor Power BI, krijgt deze gebruiker automatisch een Power BI-licentie toegewezen.
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>Hoe kunnen individuele gebruikers in mijn organisatie zich registreren?

Er zijn drie scenario's die van toepassing kunnen zijn op gebruikers in uw organisatie:
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-a-microsoft-365-account"></a>Scenario 1: uw organisatie beschikt al over een bestaande Microsoft 365-omgeving en de gebruiker die zich registreert voor Power BI heeft al een Microsoft 365-account.

Als een gebruiker in dit scenario al een werk- of schoolaccount in de tenant heeft (bijvoorbeeld contoso.com) maar nog niet over Power BI beschikt, activeert Microsoft het abonnement voor dat account en wordt de gebruiker automatisch geïnformeerd over het gebruik van de Power BI-service.
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-a-microsoft-365-account"></a>Scenario 2: uw organisatie heeft al een Microsoft 365-omgeving en de gebruiker die zich registreert voor Power BI heeft geen Microsoft 365-account.

In dit scenario heeft de gebruiker een e-mailadres in het domein van uw organisatie (bijvoorbeeld contoso.com), maar u hebt nog geen Microsoft 365-account. In dit geval kan de gebruiker zich registreren voor Power BI en krijgt hij of zij automatisch een account. Hiermee krijgt de gebruiker toegang tot de Power BI-service. Als een werknemer met de naam Nancy het werk-e-mailadres (bijvoorbeeld Nancy@contoso.com) gebruikt om u aan te melden, zal Microsoft automatisch Nancy toevoegen als een gebruiker in de contoso Microsoft 365-omgeving en Power BI voor dat account activeren.
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a>Scenario 3: uw organisatie beschikt niet over een Microsoft 365-omgeving die is verbonden met uw e-mail domein.

Uw organisatie hoeft geen beheerdersacties te ondernemen om gebruik te kunnen maken van Power BI.
  
> [!IMPORTANT]
> Als uw organisatie meerdere e-mail domeinen heeft en u wilt dat alle e-mailadres uitbreidingen zich in dezelfde Tenant bevinden, moet voordat gebruikers de primaire Tenant maken, alle e-mailadres domeinen toevoegen aan deze Tenant voordat gebruikers de primaire Tenant maken. Er is geen automatisch mechanisme voor het verplaatsen van gebruikers tussen tenants nadat deze zijn gemaakt. Zie voor meer informatie over dit proces, [als ik meerdere domeinen heb, kan ik de Tenant beheren waaraan gebruikers worden toegevoegd?](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to) verderop in dit artikel, en [Voeg een domein toe aan Office 365](../setup/add-domain.md) online.
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Hoe verandert dit de manier waarop ik nu identiteiten beheer voor gebruikers in mijn organisatie?

Als uw organisatie al een bestaande Microsoft 365-omgeving heeft en alle gebruikers in uw organisatie Microsoft 365-accounts hebben, blijft het identiteitsbeheer ongewijzigd.
  
Als uw organisatie al beschikt over een bestaande Microsoft 365-omgeving, maar niet alle gebruikers in uw organisatie Microsoft 365-accounts hebben, wordt er een gebruiker in de Tenant gemaakt en licenties toe te wijzen op basis van het e-mailadres van de gebruiker of school. Dit betekent dat het aantal gebruikers dat u op een willekeurig moment beheert, toeneemt naarmate er zich meer gebruikers in uw organisatie voor de service registreren.
  
Als u uw map lokaal beheert en Active Directory Federation Services (ADFS) gebruikt, worden er geen gebruikers aan uw tenant toegevoegd. Gebruikers die aan de tenant proberen deel te nemen, ontvangen een bericht om contact op te nemen met de beheerder van de organisatie.
  
Als in uw organisatie geen Microsoft 365-omgeving is verbonden met uw e-mail domein, hoeft u geen wijziging te doen in de manier waarop u de identiteit beheert. Gebruikers worden toegevoegd aan een nieuwe gebruikerslijst die alleen in de cloud wordt gebruikt en u hebt als tenantbeheerder de mogelijkheid het beheer over de studenten over te nemen.
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Wat is het proces voor het beheren van een tenant die Microsoft voor mijn gebruikers heeft gemaakt?

Als een tenant door Microsoft is gemaakt, kunt u deze tenant claimen en beheren door deze stappen uit te voeren:
  
1. Neem deel aan de tenant door u te [registreren voor Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) via een e-maildomein dat overeenkomt met het tenantdomein dat u wilt beheren. Als Microsoft bijvoorbeeld de tenant contoso.com heeft gemaakt, moet u aan de tenant deelnemen met een e-mailadres dat eindigt op @contoso.com.

1. U kunt het beheer claimen door het eigendom van het domein te verifiëren: zodra u zich in de tenant bevindt, kunt u de rol van beheerder overnemen door het domeineigendom te verifiëren. Ga hiervoor als volgt te werk:

::: moniker range="o365-worldwide"

3. Ga naar [https://admin.microsoft.com](https://admin.microsoft.com).

::: moniker-end

::: moniker range="o365-germany"

3. Ga naar [https://portal.office.de](https://portal.office.de).

::: moniker-end

::: moniker range="o365-21vianet"

3. Ga naar [https://portal.partner.microsoftonline.cn](https://portal.partner.microsoftonline.cn).

::: moniker-end

4. Selecteer het pictogram voor het startprogramma voor apps in de linkerbovenhoek en kies **Beheer**.

    ![Startprogramma voor apps met de app beheer gemarkeerd](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. Lees de instructies op de pagina **de beheerder worden** en kies vervolgens **Ja, ik wil de beheerder zijn**.

    > [!NOTE]
    >  Als deze optie niet wordt weergegeven, is er al een beheerder ter plaatste.
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a>Kan ik, als ik meerdere domeinen heb, de Tenant beheren waaraan gebruikers worden toegevoegd?

Als u niets doet, wordt er een tenant gemaakt voor het e-maildomein en subdomein van elke gebruiker.
  
Ga als volgt te werk als u alle gebruikers in dezelfde tenant wilt onderbrengen, ongeacht hun e-mailadresextensies:
  
- Maak vooraf een doeltenant of gebruik een bestaande tenant en voeg alle bestaande domeinen en subdomeinen toe die u binnen die tenant wilt vastleggen. Alle gebruikers met een e-mailadres dat eindigt op een dergelijk domein en subdomein, nemen dan bij registratie automatisch deel aan de doeltenant.

> [!IMPORTANT]
> Er is geen ondersteund automatisch mechanisme om gebruikers te verplaatsen tussen tenants nadat deze zijn gemaakt. Zie [een domein toevoegen aan Office 365](../setup/add-domain.md)voor informatie over het toevoegen van domeinen aan één microsoft 365-Tenant.

> [!IMPORTANT]
> Zie [Wat is Power bi-beheer?](https://docs.microsoft.com/power-bi/service-admin-administering-power-bi-in-your-organization)voor meer informatie en instructies voor het beheren van tenants.
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a>Hoe kan ik voorkomen dat gebruikers deelnemen aan mijn bestaande Tenant?

U kunt de volgende stappen uitvoeren als beheerder om te voorkomen dat gebruikers deelnemen aan uw bestaande Tenant. Als u wilt voorkomen dat gebruikers deelnemen aan de Tenant, mislukt het aanmelden van gebruikers en worden ze doorgestuurd naar contact opnemen met de beheerder van de organisatie. U hoeft dit proces niet te herhalen als u de distributie van licenties al eerder hebt uitgeschakeld vóór (bijvoorbeeld Office 365 Education voor leerlingen en studenten, onderwijs medewerkers en personeel).
  
Voor deze stappen is het gebruik van Windows PowerShell vereist. Raadpleeg de [handleiding Aan de slag met PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286814) als u aan de slag wilt met Windows PowerShell.
  
U kunt de volgende stappen alleen uitvoeren als u de nieuwste 64-bits versie van de [Azure Active Directory v2 PowerShell-module](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5)hebt geïnstalleerd.
  
Nadat u de koppeling hebt geselecteerd, klikt u op **uitvoeren** om het installatiepakket uit te voeren.
  
**Automatische deelname aan de tenant uitschakelen** : Gebruik deze Windows PowerShell-opdracht om te voorkomen dat nieuwe gebruikers deelnemen aan een beheerde tenant:
  
Ga als volgt te werk als u automatische deelname van nieuwe gebruikers aan de tenant wilt uitschakelen:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
Ga als volgt te werk als u automatische deelname van nieuwe gebruikers aan de tenant wilt inschakelen:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> Dit blokkeert voorkomt dat nieuwe gebruikers in uw organisatie zich registreren voor Power BI. Gebruikers die zich registreren voor Power BI voordat nieuwe aanmeld functies voor uw organisatie worden uitgeschakeld, blijven hun licenties behouden. Zie [Hoe verwijder ik Power BI voor gebruikers die zich al hebben geregistreerd?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) voor instructies over het verwijderen van de toegang tot Power BI voor gebruikers die zich eerder hebben geregistreerd voor de service.
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a>Hoe kan ik gebruikers toestaan deel te nemen aan mijn bestaande Tenant?

Als u wilt dat gebruikers kunnen deelnemen aan de tenant, voert u de tegenovergestelde opdracht uit zoals is beschreven in de bovenstaande vraag:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Hoe controleer ik of de blokkering in de tenant is ingeschakeld?

Gebruik het volgende PowerShell-script:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Hoe kan ik voorkomen dat mijn bestaande gebruikers Power BI gaan gebruiken?

**Automatische distributie van licenties uitschakelen:** Gebruik dit Windows PowerShell-script om automatische distributie van licenties voor bestaande gebruikers uit te schakelen. U hoeft dit proces niet te herhalen als u de distributie van licenties al eerder hebt uitgeschakeld vóór (bijvoorbeeld Office 365 Education voor leerlingen en studenten, onderwijs medewerkers en personeel).
  
Ga als volgt te werk om automatische distributie van licenties voor bestaande gebruikers uit te schakelen:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
Ga als volgt te werk om automatische distributie van licenties voor bestaande gebruikers in te schakelen:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> Met de *AllowAdHocSubscriptions* -vlag beheert u diverse gebruikers mogelijkheden in uw organisatie, waaronder de mogelijkheid om gebruikers te registreren voor de Azure Rights Management-service. Wijziging van deze vlag is van invloed op al deze mogelijkheden.
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Hoe kan ik mijn bestaande gebruikers toestaan zich te registreren voor Power BI?

Als u de bestaande gebruikers wilt toestaan zich te registreren voor Power BI, voert u de tegenovergestelde opdracht uit zoals is beschreven in de bovenstaande vraag:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Hoe verwijder ik Power BI voor gebruikers die zich al hebben geregistreerd?

Als een gebruiker zich heeft geregistreerd voor Power BI, maar u niet meer wilt dat de gebruiker toegang heeft tot Power BI, kunt u de Power BI-licentie voor die gebruiker verwijderen.

::: moniker range="o365-worldwide"
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Zoek de gebruiker van wie u de licentie wilt verwijderen en selecteer de naam.

3. Schakel op het tabblad **licenties en apps** het selectievakje **Microsoft Power bi** uit.

4. Selecteer **Wijzigingen opslaan**.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Zoek de gebruiker van wie u de licentie wilt verwijderen en selecteer de naam.

3. Naast **product licenties** selecteert u **bewerken**.

4. Schakel de optie **Microsoft Power bi** uit.

5. Kies **Opslaan**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Zoek de gebruiker van wie u de licentie wilt verwijderen en selecteer de naam.

3. Naast **product licenties** selecteert u **bewerken**.

4. Schakel de optie **Microsoft Power bi** uit.

5. Klik op **Opslaan**.

::: moniker-end

## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Hoe weet ik wanneer nieuwe gebruikers deelnemen aan mijn tenant?

Gebruikers die deelnemen aan de tenant als onderdeel van dit programma, krijgen een unieke licentie toegewezen waarop u kunt filteren binnen het actieve gebruikersdeelvenster in het beheerdersdashboard.
  
Als u deze nieuwe weergave wilt maken, volgt u de stappen in het Beheercentrum om [een aangepaste gebruikersweergave maken](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view)te volgen. Selecteer onder **toegewezen productlicentie** de optie **Microsoft Power bi**. Nadat de nieuwe weergave is gemaakt, kunt u alle gebruikers in de Tenant zien die zich hebben geregistreerd in dit programma.
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Is er nog meer waarop ik voorbereid moet zijn?

U kunt meer aanvragen verwachten voor het opnieuw instellen van wachtwoorden. Zie [Het wachtwoord van een gebruiker opnieuw instellen](../add-users/reset-passwords.md) voor informatie over deze procedure.
  
U kunt een gebruiker verwijderen uit uw Tenant via het standaardproces van het Beheercentrum. Als de gebruiker echter nog steeds een actief e-mailadres van uw organisatie heeft, kan die gebruiker opnieuw deelnemen tenzij u alle gebruikers hebt geblokkeerd.
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a>Waarom zijn er 1.000.000-licenties voor Microsoft Power BI in mijn Tenant weergegeven?

Uw organisatie is een in aanmerking komende organisatie en daarom kunnen gebruikers in uw organisatie de Microsoft Power BI-service gebruiken. Deze licenties geven de beschikbare capaciteit voor nieuwe Power BI-gebruikers in uw tenant aan. Als u toestaat dat gebruikers zich kunnen registreren voor Power BI zelf, wordt er een van de beschikbare gratis licenties toegewezen wanneer ze het aanmeldingsproces voltooien. U kunt er ook voor kiezen om deze licenties toe te wijzen aan gebruikers in het Beheercentrum.
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Is dit gratis? Moet ik betalen voor deze licenties?

Deze licenties zijn voor de gratis versie van Power BI. Als u geïnteresseerd bent in aanvullende voorzieningen, kunt u de Pro-versie van Power BI bekijken.
  
## <a name="why-1-million-licenses"></a>Waarom 1 miljoen licenties?

We hebben een aantal gekozen dat zo groot is dat de meeste organisaties voldoende licenties hebben om deze vergoeding zonder vertraging voor hun gebruikers te bieden.
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>Wat moet ik doen als ik meer dan 1 miljoen licenties nodig heb?

Neem contact op met uw Microsoft-vertegenwoordiger voor meer informatie als u extra licenties nodig hebt.