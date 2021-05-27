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
description: Meer informatie Power BI en hoe gebruikers in uw organisatie deze service voor bedrijfsanalyse kunnen gebruiken.
ms.openlocfilehash: 6da25932e1813744aa38bab2b399d6ac30c3429a
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683365"
---
# <a name="power-bi-in-your-organization"></a>Power BI in uw organisatie

Op deze pagina wordt beschreven hoe gebruikers in uw organisatie Power BI kunnen gebruiken en hoe u kunt bepalen hoe uw organisatie deze service krijgt.

## <a name="what-is-power-bi"></a>Wat is Power BI?

Met Microsoft Power BI kunnen gebruikers gegevens visualiseren, ontdekkingen delen en samenwerken op intuïtieve en nieuwe manieren. Zie de [website van Power BI](https://powerbi.microsoft.com/en-us/) voor meer informatie.
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Voldoet Power BI aan nationale, regionale en branchespecifieke nalevingsvereisten?

Zie het [Microsoft Trust Center](https://go.microsoft.com/fwlink/?LinkId=785324)voor meer Power BI compliance.
  
## <a name="how-do-users-sign-up-for-power-bi"></a>Hoe kunnen gebruikers zich registreren voor Power BI?

Als beheerder kunt u zich registreren voor Power BI via de [Power BI-website](https://powerbi.microsoft.com/en-us/). U kunt zich ook registreren via de pagina Inkoopservices op het Microsoft 365 beheercentrum. Wanneer beheerders zich registreren voor Power BI, kunnen ze licenties voor gebruikersabonnementen toewijzen aan gebruikers die toegang moeten krijgen.
  
Bovendien kunnen individuele gebruikers in uw organisatie zich registreren voor Power BI via de [Power BI-website](https://powerbi.microsoft.com/en-us/). Wanneer een gebruiker in uw organisatie zich registreert voor Power BI, krijgt deze gebruiker automatisch een Power BI-licentie toegewezen.
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>Hoe kunnen individuele gebruikers in mijn organisatie zich registreren?

Er zijn drie scenario's die van toepassing kunnen zijn op gebruikers in uw organisatie:
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-a-microsoft-365-account"></a>Scenario 1: Uw organisatie heeft al een bestaande Microsoft 365 omgeving en de gebruiker die zich aanmeldt voor Power BI heeft al een Microsoft 365 account.

Als een gebruiker in dit scenario al een werk- of schoolaccount in de tenant heeft (bijvoorbeeld contoso.com) maar nog niet over Power BI beschikt, activeert Microsoft het abonnement voor dat account en wordt de gebruiker automatisch geïnformeerd over het gebruik van de Power BI-service.
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-a-microsoft-365-account"></a>Scenario 2: Uw organisatie heeft een bestaande Microsoft 365 omgeving en de gebruiker die zich aanmeldt voor Power BI heeft geen Microsoft 365 account.

In dit scenario heeft de gebruiker een e-mailadres in het domein van uw organisatie (bijvoorbeeld contoso.com), maar nog geen Microsoft 365 account. In dit geval kan de gebruiker zich registreren voor Power BI en krijgt hij of zij automatisch een account. Hiermee krijgt de gebruiker toegang tot de Power BI-service. Als een werknemer met de naam Nancy bijvoorbeeld haar werk-e-mailadres (bijvoorbeeld Nancy@contoso.com) gebruikt om zich aan te melden, voegt Microsoft Nancy automatisch toe als gebruiker in de contoso-Microsoft 365-omgeving en activeert u Power BI voor dat account.
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a>Scenario 3: Uw organisatie heeft geen Microsoft 365 verbonden met uw e-maildomein.

Er zijn geen beheeracties die uw organisatie nodig heeft om te profiteren van Power BI.
  
> [!IMPORTANT]
> Als uw organisatie meerdere e-maildomeinen heeft en u wilt dat alle e-mailadresextensies in dezelfde tenant zijn, voordat gebruikers uw primaire tenant maken, voegt u alle e-mailadresdomeinen toe aan die tenant voordat gebruikers uw primaire tenant maken. Er is geen geautomatiseerd mechanisme om gebruikers over tenants te verplaatsen nadat ze zijn gemaakt. Zie Als ik meerdere domeinen [heb,](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to) kan ik bepalen aan welke tenant gebruikers worden toegevoegd? verder in dit artikel en Een domein toevoegen aan Office 365 [online.](../setup/add-domain.md)
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Hoe verandert dit de manier waarop ik nu identiteiten beheer voor gebruikers in mijn organisatie?

Als uw organisatie al een bestaande Microsoft 365 en alle gebruikers in uw organisatie een Microsoft 365 hebben, wordt het identiteitsbeheer niet gewijzigd.
  
Als uw organisatie al een bestaande Microsoft 365-omgeving heeft, maar niet alle gebruikers in uw organisatie Microsoft 365-accounts hebben, maken we een gebruiker in de tenant en toewijzen we licenties op basis van het werk- of school-e-mailadres van de gebruiker. Dit betekent dat het aantal gebruikers dat u op een willekeurig moment beheert, toeneemt naarmate er zich meer gebruikers in uw organisatie voor de service registreren.
  
Als u uw map lokaal beheert en Active Directory Federation Services (ADFS) gebruikt, worden er geen gebruikers aan uw tenant toegevoegd. Gebruikers die aan de tenant proberen deel te nemen, ontvangen een bericht om contact op te nemen met de beheerder van de organisatie.
  
Als uw organisatie geen Microsoft 365 verbonden met uw e-maildomein, verandert er niets aan de manier waarop u identiteit beheert. Gebruikers worden toegevoegd aan een nieuwe gebruikerslijst die alleen in de cloud wordt gebruikt en u hebt als tenantbeheerder de mogelijkheid het beheer over de studenten over te nemen.
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Wat is het proces voor het beheren van een tenant die Microsoft voor mijn gebruikers heeft gemaakt?

Als een tenant door Microsoft is gemaakt, kunt u deze tenant claimen en beheren door deze stappen uit te voeren:
  
1. Neem deel aan de tenant door u te [registreren voor Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) via een e-maildomein dat overeenkomt met het tenantdomein dat u wilt beheren. Als Microsoft bijvoorbeeld de tenant contoso.com heeft gemaakt, moet u aan de tenant deelnemen met een e-mailadres dat eindigt op @contoso.com.

1. U kunt het beheer claimen door het eigendom van het domein te verifiëren: zodra u zich in de tenant bevindt, kunt u de rol van beheerder overnemen door het domeineigendom te verifiëren. Ga hiervoor als volgt te werk:

::: moniker range="o365-worldwide"

3. Ga naar <a href="https://admin.microsoft.com" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

3. Ga naar <a href="https://portal.office.de" target="_blank">https://portal.office.de</a>

::: moniker-end

::: moniker range="o365-21vianet"

3. Ga naar <a href="https://portal.partner.microsoftonline.cn" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end

4. Selecteer het pictogram voor het startprogramma voor apps in de linkerbovenhoek en kies **Beheer**.

    ![Start startpagina voor apps met de app Beheerder gemarkeerd](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. Lees de instructies op de **pagina Word de beheerder** en selecteer vervolgens **Ja, ik wil de beheerder zijn.**

    > [!NOTE]
    >  Als deze optie niet wordt weergegeven, is er al een beheerder beschikbaar.
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a>Als ik meerdere domeinen heb, kan ik dan bepalen aan wie gebruikers worden toegevoegd?

Als u niets doet, wordt er een tenant gemaakt voor het e-maildomein en subdomein van elke gebruiker.
  
Ga als volgt te werk als u alle gebruikers in dezelfde tenant wilt onderbrengen, ongeacht hun e-mailadresextensies:
  
- Maak vooraf een doeltenant of gebruik een bestaande tenant en voeg alle bestaande domeinen en subdomeinen toe die u binnen die tenant wilt vastleggen. Alle gebruikers met een e-mailadres dat eindigt op een dergelijk domein en subdomein, nemen dan bij registratie automatisch deel aan de doeltenant.

> [!IMPORTANT]
> Er is geen ondersteund automatisch mechanisme om gebruikers te verplaatsen tussen tenants nadat deze zijn gemaakt. Zie Een [domein](../setup/add-domain.md)toevoegen aan Office 365 voor meer informatie over het toevoegen Microsoft 365 een tenant.

> [!IMPORTANT]
> Zie Wat is Power BI beheer? voor meer informatie [en richtlijnen over het beheren van tenants.](/power-bi/service-admin-administering-power-bi-in-your-organization)
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a>Hoe kan ik voorkomen dat gebruikers deelnemen aan mijn bestaande tenant?

Er zijn stappen die u als beheerder kunt nemen om te voorkomen dat gebruikers deelnemen aan uw bestaande tenant. Als u gebruikers blokkeert om deel te nemen aan de tenant, mislukken de pogingen van gebruikers om zich aan te melden en worden ze doorgestuurd om contact op te nemen met de beheerder van hun organisatie. U hoeft dit proces niet te herhalen als u de automatische distributie van licenties al eerder hebt uitgeschakeld (bijvoorbeeld Office 365 Education voor studenten, onderwijsmedewerkers en personeel).
  
Voor deze stappen is het gebruik van Windows PowerShell vereist. Raadpleeg de [handleiding Aan de slag met PowerShell](/powershell/scripting/overview) als u aan de slag wilt met Windows PowerShell.
  
Als u de volgende stappen wilt uitvoeren, moet u de nieuwste 64-bits versie van de [V2 PowerShell-module Azure Active Directory installeren.](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5)
  
Nadat u de koppeling hebt geselecteerd, **selecteert** u Uitvoeren om het installatiepakket uit te voeren.
  
**Automatische deelname aan de tenant uitschakelen**: Gebruik deze Windows PowerShell-opdracht om te voorkomen dat nieuwe gebruikers deelnemen aan een beheerde tenant:
  
Ga als volgt te werk als u automatische deelname van nieuwe gebruikers aan de tenant wilt uitschakelen:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
Ga als volgt te werk als u automatische deelname van nieuwe gebruikers aan de tenant wilt inschakelen:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> Hiermee voorkomt u dat nieuwe gebruikers in uw organisatie zich kunnen registreren voor Power BI. Gebruikers die zich registreren voor Power BI voordat u nieuwe aanmeldingen voor uw organisatie uitkeert, behouden hun licenties nog steeds. Zie Hoe verwijder ik Power BI voor gebruikers die zich al hebben [aangemeld?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) voor instructies over hoe u de toegang tot Power BI kunt verwijderen voor gebruikers die zich eerder hadden aangemeld voor de service.
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a>Hoe kan ik toestaan dat gebruikers lid worden van mijn bestaande tenant?

Als u wilt dat gebruikers kunnen deelnemen aan de tenant, voert u de tegenovergestelde opdracht uit zoals is beschreven in de bovenstaande vraag:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Hoe controleer ik of de blokkering in de tenant is ingeschakeld?

Gebruik het volgende PowerShell-script:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Hoe kan ik voorkomen dat mijn bestaande gebruikers Power BI gaan gebruiken?

**Automatische distributie van licenties uitschakelen:** Gebruik dit Windows PowerShell-script om automatische distributie van licenties voor bestaande gebruikers uit te schakelen. U hoeft dit proces niet te herhalen als u de automatische distributie van licenties al eerder hebt uitgeschakeld (bijvoorbeeld Office 365 Education voor studenten, onderwijsmedewerkers en personeel).
  
Ga als volgt te werk om automatische distributie van licenties voor bestaande gebruikers uit te schakelen:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
Ga als volgt te werk om automatische distributie van licenties voor bestaande gebruikers in te schakelen:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> De *vlag AllowAdHocSubscriptions* wordt gebruikt om verschillende gebruikersmogelijkheden in uw organisatie te bepalen, waaronder de mogelijkheid voor gebruikers om zich aan te melden voor de Azure Rights Management Service. Wijziging van deze vlag is van invloed op al deze mogelijkheden.
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Hoe kan ik mijn bestaande gebruikers toestaan zich te registreren voor Power BI?

Als u de bestaande gebruikers wilt toestaan zich te registreren voor Power BI, voert u de tegenovergestelde opdracht uit zoals is beschreven in de bovenstaande vraag:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Hoe verwijder ik Power BI voor gebruikers die zich al hebben geregistreerd?

Als een gebruiker zich heeft aangemeld voor Power BI, maar u wilt niet meer dat hij of zij toegang heeft tot Power BI, kunt u de licentie voor Power BI voor die gebruiker verwijderen.
  
::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

::: moniker-end

2. Zoek de gebruiker voor wie u de licentie wilt verwijderen en selecteer vervolgens de naam.

3. Op het **tabblad Licenties en apps** kunt u het selectievakje Microsoft **Power BI** uit.

4. Selecteer **Wijzigingen opslaan**.

## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Hoe weet ik wanneer nieuwe gebruikers deelnemen aan mijn tenant?

Gebruikers die deelnemen aan de tenant als onderdeel van dit programma, krijgen een unieke licentie toegewezen waarop u kunt filteren binnen het actieve gebruikersdeelvenster in het beheerdersdashboard.
  
Als u deze nieuwe weergave wilt maken, volgt u in het beheercentrum de stappen in [Een aangepaste gebruikersweergave maken.](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view) Selecteer **onder Toegewezen productlicentie** de optie **Microsoft Power BI.** Nadat de nieuwe weergave is gemaakt, kunt u alle gebruikers in uw tenant zien die zich hebben geregistreerd voor dit programma.
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Is er nog meer waarop ik voorbereid moet zijn?

U kunt meer aanvragen verwachten voor het opnieuw instellen van wachtwoorden. Zie [Het wachtwoord van een gebruiker opnieuw instellen](../add-users/reset-passwords.md) voor informatie over deze procedure.
  
U kunt een gebruiker verwijderen uit uw tenant via het standaardproces in het beheercentrum. Als de gebruiker echter nog steeds een actief e-mailadres van uw organisatie heeft, kan die gebruiker opnieuw deelnemen tenzij u alle gebruikers hebt geblokkeerd.
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a>Waarom zijn er 1 miljoen licenties voor Microsoft Power BI in mijn tenant?

Uw organisatie is een in aanmerking komende organisatie en daarom kunnen gebruikers in uw organisatie de Microsoft Power BI-service gebruiken. Deze licenties geven de beschikbare capaciteit voor nieuwe Power BI-gebruikers in uw tenant aan. Als u ervoor hebt gekozen om gebruikers toe te staan zich aan te melden voor Power BI zelf, krijgen ze een van deze gratis licenties toegewezen wanneer ze het aanmeldingsproces voltooien. U kunt er ook voor kiezen om deze licenties aan gebruikers zelf toe te wijzen via het beheercentrum.
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Is dit gratis? Moet ik betalen voor deze licenties?

Deze licenties zijn voor de gratis versie van Power BI. Als u geïnteresseerd bent in aanvullende voorzieningen, kunt u de Pro-versie van Power BI bekijken.
  
## <a name="why-1-million-licenses"></a>Waarom 1 miljoen licenties?

We hebben een getal gekozen dat groot genoeg was dat de meeste organisaties over voldoende licenties zouden hebben om dit voordeel zonder vertraging aan hun gebruikers te bieden.
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>Wat moet ik doen als ik meer dan 1 miljoen licenties nodig heb?

Neem contact op met uw Microsoft-vertegenwoordiger voor meer informatie als u extra licenties nodig hebt.