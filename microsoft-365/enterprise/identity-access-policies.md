---
title: Gangbare beleidsregels voor identiteit en Apparaattoegang-Microsoft 365 for Enterprise | Microsoft docs
description: Een beschrijving van de aanbevolen beleidsregels en configuraties voor het openen van identiteiten en apparaten.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: 9819c161cc421117730cb4c58d1db06859125476
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332095"
---
# <a name="common-identity-and-device-access-policies"></a>Algemeen beleid voor identiteiten en apparaattoegang
In dit artikel wordt het aanbevolen beleid beschreven voor de beveiliging van de toegang tot cloudservices, waaronder on-premises toepassingen die zijn gepubliceerd met de Azure AD-toepassings proxy. 

In deze richtlijnen wordt uitgelegd hoe u de aanbevolen beleidsregels implementeert in een nieuw ingerichte omgeving. Door deze beleidsregels in een afzonderlijke lab-omgeving in te stellen, kunt u de aanbevolen beleidsregels uitleggen en evalueren voordat u de implementatie uitschakelt voor de producties en productieomgevingen. Uw zojuist ingerichte omgeving mag alleen in de Cloud of hybride.  

## <a name="policy-set"></a>Beleidsinstelling 

In het volgende diagram wordt de aanbevolen set beleidsregels getoond. In dit voorbeeld wordt aangegeven welke beveiligings bescherming elk beleid van toepassing is en of het beleid van toepassing is op Pc's of telefoons en tablets, of op beide soorten apparaten. Ook wordt aangegeven waar dit beleid is geconfigureerd.

[ ![ Veelgebruikte beleidsregels voor het configureren van de identiteit en Apparaattoegang bieden](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [een grotere versie van deze afbeelding weer](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

In de rest van dit artikel wordt uitgelegd hoe u deze beleidsregels configureert. 

Het gebruik van multi-factor Authentication wordt aanbevolen voordat u apparaten registreert voor een intune-service om zeker te zijn dat het apparaat in bezit is van de bedoelde gebruiker. U moet apparaten ook registreren in intune voordat u beleidsregels voor naleving van apparaatcompatibiliteit afdwingt.

Om u tijd te bieden voor het uitvoeren van deze taken, wordt u aangeraden het basisbeleid voor basisregels te implementeren in de volgorde waarin deze tabel wordt weergegeven. De MFA-beleidsregels voor gevoelige en zeer gereguleerde bescherming kunnen op elk moment worden geïmplementeerd.


|Beveiligingsniveau|Lijnen|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|        |[Clients blokkeren die moderne verificatie niet ondersteunen](#block-clients-that-dont-support-modern-authentication)|Clients die geen moderne verificatie gebruiken, kunnen regels voor voorwaardelijke toegang negeren, dus het is belangrijk om deze te blokkeren|
|        |[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](#high-risk-users-must-change-password)|Zorgt ervoor dat gebruikers hun wachtwoord kunnen wijzigen bij het aanmelden als er een hoog/riskant-activiteit voor hun account is gedetecteerd|
|        |[Beleid voor APP-gegevensbeveiliging toepassen](#apply-app-data-protection-policies)|Eén beleid per platform (iOS, Android, Windows). Beveiligingsbeleid in de intune-app (APP) zijn vooraf gedefinieerde sets beveiliging, van niveau 1 tot niveau 3.|
|        |[Goedgekeurde apps en APP-beveiliging vereisen](#require-approved-apps-and-app-protection)|De bescherming van de mobiele app afdwingt voor telefoons en tablets|
|        |[Beleidsregels voor naleving van apparaten definiëren](#define-device-compliance-policies)|Eén beleid voor elk platform|
|        |[Eis conforme pc’s](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|InTune-beheer van Pc's afdwingen|
|**Gevoelig**|[MFA vereisen wanneer het aanmeld risico *slecht*, *gemiddeld* of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|         |[Compatibele Pc's *en* mobiele apparaten vereisen](#require-compliant-pcs-and-mobile-devices)|InTune-beheer afdwingen voor Pc's en telefoons/tablets|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Beleid toewijzen aan gebruikers
Voordat u beleidsregels configureert, identificeert u de groepen van Azure AD die u voor elke beschermingsniveau gebruikt. Normaalgesproken geldt er basislijn beveiliging voor iedereen in de organisatie. Een gebruiker die is opgenomen in de basislijn en de gevoelige beveiliging, heeft alle toegepaste basisregels plus het gevoelige beleid. Beveiliging is cumulatief en het meest beperkte beleid wordt afgedwongen. 

U wordt geadviseerd een Azure AD-groep te maken voor de uitsluiting van voorwaardelijke toegang. Deze groep toevoegen aan al uw voorwaardelijke toegangsregels onder "uitsluiten". U onthoudt een methode voor het verlenen van toegang aan een gebruiker wanneer u problemen met Access oplost. Dit wordt alleen aanbevolen als tijdelijke oplossing. Bewaakt deze groep voor wijzigingen en zorg ervoor dat de uitsluitings groep uitsluitend wordt gebruikt zoals bedoeld. 

Het volgende diagram bevat een voorbeeld van gebruikers opdrachten en uitsluitingen.

![Voorbeeld van gebruikerstoewijzing en uitsluitingen van MFA-regels](../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

In de afbeelding het ' belangrijkste Secret Project X team ' is een beleid voor voorwaardelijke toegang toegewezen waarvoor MFA *altijd*is vereist. Wees zorgvuldig wanneer u een hoger beveiligingsniveau toepast voor gebruikers. Leden van dit projectteam dienen twee soorten verificatie te bieden telkens wanneer ze zich aanmelden, ook als ze geen sterk gereguleerde inhoud weergeven.  

Alle Azure AD-groepen die als onderdeel van deze aanbevelingen zijn gemaakt, moeten worden gemaakt als Microsoft 365-groepen. Dit is vooral belangrijk voor de implementatie van tekstlabels bij het beveiligen van documenten in SharePoint Online.

![Schermafbeelding van het maken van Microsoft 365-groepen](../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>MFA vereisen op basis van aanmeldings risico
Voordat MFA is vereist, moet u eerst een MFA-registratiebeleid voor identiteitsbeveiliging gebruiken om gebruikers voor MFA te registreren. Nadat gebruikers zijn geregistreerd, kunt u MFA afdwingen voor aanmelding. Het [vereiste werk](identity-access-prerequisites.md) omvat het registreren van alle gebruikers met MFA.

Een nieuw beleid voor voorwaardelijke toegang maken: 

1. Ga naar de [Azure-Portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies in de sectie **beveiliging** de optie **voorwaardelijke toegang**.

4. Kies **nieuwe beleids**optie.

![Beleid voor basis van basis certificering](../media/secure-email/CA-EXO-policy-1.png)

 In de volgende tabellen worden de beleidsinstellingen voor voorwaardelijke toegang beschreven voor de implementatie van dit beleid.

**Verlenen**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Voorzien|Selecteer gebruikers en groepen – Selecteer specifieke beveiligingsgroep met gerichte gebruikers|Beginnen met beveiligingsgroep, waaronder proef gebruikers|
||Uit|Beveiligingsgroep uitzonderingen; serviceaccounts (app-Identities)|Lidmaatschap gewijzigd voor een zo nodig tijdelijke basis|
|Cloud-apps|Voorzien|Selecteer de apps waarop u deze regel wilt toepassen. Selecteer bijvoorbeeld Exchange Online||
|Vastgestelde|Configureren|Ja|Specifiek configureren voor uw omgeving en behoefte|
|Aanmeld risico|Risiconiveau||Zie de instructies in de volgende tabel|

**Aanmeld risico**

De instellingen toepassen op basis van het beveiligingsniveau dat u wilt bereiken.

|Eigenschap|Beschermingsniveau|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Risiconiveau|Basislijn|Hoog, normaal|Beide controleren|
| |Gevoelig|Hoog, normaal, laag|Alle drie controleren|
| |Sterk gereglementeerd| |Schakel alle opties uit om MFA altijd af te dwingen|

**Besturingselementen voor Access**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Wijs|Toegang verlenen|Waar|Bepaalde|
||MFA vereisen|Waar|Cheque|
||Apparaat vereisen om te worden gemarkeerd als compatibel|Vals||
||Hybride Azure AD-bijgevoegde apparaat vereisen|Vals||
||Goedgekeurde clienttoepassing vereisen|Vals||
||Alle geselecteerde besturingselementen vereisen|Waar|Bepaalde|

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt door **aan**te bieden. U kunt ook het hulpprogramma [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Cliënten blokkeren die geen moderne verificatie ondersteunen
1. Ga naar de [Azure-Portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies in de sectie **beveiliging** de optie **voorwaardelijke toegang**.

4. Kies **nieuwe beleids**optie.

In de volgende tabellen worden de beleidsinstellingen voor voorwaardelijke toegang beschreven voor de implementatie van dit beleid.

**Verlenen**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Voorzien|Selecteer gebruikers en groepen – Selecteer specifieke beveiligingsgroep met gerichte gebruikers|Beginnen met beveiligingsgroep, waaronder proef gebruikers|
||Uit|Beveiligingsgroep uitzonderingen; serviceaccounts (app-Identities)|Verlangd lidmaatschap gewijzigd met de gewenste tijdelijke basis|
|Cloud-apps|Voorzien|Selecteer de apps waarop u deze regel wilt toepassen. Selecteer bijvoorbeeld Exchange Online||
|Vastgestelde|Configureren|Ja|Client toepassingen configureren|
|Client toepassingen|Configureren|Ja|Mobiele apps en desktop-clients, andere clients (selecteren beide)|

**Besturingselementen voor Access**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Wijs|Toegang blokkeren|Waar|Bepaalde|
||MFA vereisen|Vals||
||Apparaat vereisen om te worden gemarkeerd als compatibel|Vals||
||Hybride Azure AD-bijgevoegde apparaat vereisen|Vals||
||Goedgekeurde clienttoepassing vereisen|Vals||
||Alle geselecteerde besturingselementen vereisen|Waar|Bepaalde|

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt door **aan**te bieden. U kunt ook het hulpprogramma [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen.



## <a name="high-risk-users-must-change-password"></a>Gebruikers met een hoog risico moeten het wachtwoord wijzigen
U moet het volgende beleid toepassen om ervoor te zorgen dat alle accounts met een hoog risico voor het opnieuw instellen van wachtwoorden worden geforceerd wanneer ze zich aanmelden.

Meld u aan bij de [Microsoft Azure https://portal.azure.com) -Portal (](https://portal.azure.com/) met uw beheerdersreferenties en ga vervolgens naar **Azure AD-identiteitsbeveiliging > gebruikers risico beleid**.

**Verlenen**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers|Voorzien|Alle gebruikers|Bepaalde|
||Uit|Geen||
|Vastgestelde|Gebruikers risico|Hoog|Bepaalde|

**Control**

| Type | Eigenschappen | Waarden                  | Opmerkingen |
|:-----|:-----------|:------------------------|:------|
|      | Access     | Toegang toestaan            | Waar  |
|      | Access     | Wachtwoord wijzigen vereist | Waar  |

**Revisie:** niet van toepassing

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt door **aan**te bieden. U kunt ook het hulpprogramma [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen

## <a name="apply-app-data-protection-policies"></a>Beleid voor APP-gegevensbeveiliging toepassen
App-beveiligingsbeleid (APP) Definieer welke apps zijn toegestaan en welke acties ze kunnen uitvoeren met de gegevens van uw organisatie. Met de beschikbare opties in de APP kunnen organisaties de beveiliging op hun specifieke behoeften aanpassen. Voor sommige gevallen is het mogelijk niet duidelijk welke beleidsinstellingen zijn vereist voor de implementatie van een compleet scenario. Microsoft heeft de taxonomie geïntroduceerd voor de APP Data Protection Framework voor iOS-en Android-apps voor mobiele apparaten. 

De APP Data Protection Framework is onderverdeeld in drie verschillende configuratieniveaus, waarbij elk niveau van het vorige niveau wordt opgebouwd: 

- Met **Enterprise Basic Data Protection** (niveau 1) zorgt u ervoor dat apps zijn beveiligd met een pincode en worden versleuteld en om selectief wissen te uitvoeren. Voor Android-apparaten valideert dit niveau Android-apparaatstatusverklaring. Dit is een configuratie op het niveau van het gegevensbescherming van een e-mailbericht dat vergelijkbaar is met gegevensbescherming in Postvak beleid van Exchange Online, met ininformatie over en de gebruikers bevolking op APP. 
- **Enterprise Enhanced Data Protection** (niveau 2) introduceert app data lekkage preventie en minimale besturingssysteemvereisten. Dit is de configuratie die van toepassing is op de meeste mobiele gebruikers, die werk-of school gegevens raadplegen. 
- Met **High Data Protection** (niveau 3) van de onderneming worden geavanceerde mechanismen voor gegevensbeveiliging geïntroduceerd, verbeterde configuratie van pincode en beveiliging van de mobiele bedreiging van de app. Deze configuratie is wenselijk voor gebruikers die toegang hebben tot de High Risk-gegevens. 

Als u de specifieke aanbevelingen voor elk configuratieniveau en de minimaal te beschermen Apps wilt bekijken, moet [u gegevens beschermings raamwerk raadplegen met behulp van het app-beveiligingsbeleid](https://docs.microsoft.com/mem/intune/apps/app-protection-framework). 

Met behulp van de basisprincipes van het werken met [identiteits-en Apparaattoegang-configuraties](microsoft-365-policies-configurations.md), de plattegrond van de basislijn en de gevoelige beveiliging nauwkeurig met de instellingen voor verbeterde gegevensbeveiliging van niveau 2 Enterprise. De zeer gereguleerde beveiligingslagen zijn nauwkeurig voor de instellingen voor hoog beveiligingsniveau van de onderneming van niveau 3.

|Beveiligingsniveau |Beleid voor app-beveiliging  |Meer informatie  |
|---------|---------|---------|
|Basislijn     | [Niveau 2 verbeterde gegevensbescherming](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | Met de beleidsinstellingen die worden toegepast op niveau 2, zijn alle beleidsinstellingen die worden aanbevolen voor niveau 1 opgenomen en worden de onderstaande beleidsinstellingen toegevoegd of bijgewerkt om meer besturingselementen te implementeren en een meer verfijnde configuratie dan niveau 1 te implementeren.         |
|Gevoelig     | [Niveau 2 verbeterde gegevensbescherming](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | Met de beleidsinstellingen die worden toegepast op niveau 2, zijn alle beleidsinstellingen die worden aanbevolen voor niveau 1 opgenomen en worden de onderstaande beleidsinstellingen toegevoegd of bijgewerkt om meer besturingselementen te implementeren en een meer verfijnde configuratie dan niveau 1 te implementeren.        |
|Zeer gereguleerd     | [Niveau 3 Enterprise High Data Protection](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | Met de beleidsinstellingen die worden toegepast op niveau 3, worden alle beleidsinstellingen die worden aanbevolen voor niveau 1 en 2, weergegeven en worden alleen de onderstaande beleidsinstellingen toegevoegd of bijgewerkt om meer besturingselementen en een verfijnde configuratie van niveau 2 te implementeren.        |

Beheerders kunnen de volgende opties gebruiken om een nieuw beleid voor app-beveiliging te maken voor elk platform (iOS en Android) in Microsoft Endpoint Manager met behulp van de instellingen voor Data Protection Framework:
1. Maak handmatig een beleid door de stappen [te volgen voor het maken en implementeren van een app-beveiligingsbeleid met Microsoft intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies). 
2. Importeer de JSON-sjablonen voor het voorbeeld van een [intune-app-beveiligings raamwerk](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) met [de PowerShell-scripts van intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Goedgekeurde apps en APP-beveiliging vereisen
Als u de APP-beveiligings beleidsregels die u hebt toegepast op intune wilt afdwingen, moet u een regel voor voorwaardelijke toegang maken om goedgekeurde client-apps en de voorwaarden van de beleidsregels voor APP-beveiliging te vereisen. 

Voor het afdwingen van een APP-beveiligingsbeleid is een set beleidsregels vereist die worden beschreven in het [beleid voor de app-beveiliging vereisen voor toegang tot de Cloud-app met voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access). Deze beleidsregels zijn allemaal opgenomen in deze aanbevolen set identiteit en toegangsbeleid.

Als u de regel voor voorwaardelijke toegang wilt maken waarvoor de goedgekeurde apps en APP-beveiliging zijn vereist, volgt u ' stap 1: een Azure AD-beleid voor voorwaardelijke toegang voor Microsoft 365 ' in [scenario 1: Microsoft 365-apps vereisen goedgekeurde apps met een app-beveiligingsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), waaronder Outlook voor IOS en Android

   > [!NOTE]
   > Met deze beleidsinstelling zorgt u ervoor dat mobiele gebruikers toegang hebben tot alle Office-eindpunten met behulp van de toepasselijke apps.

Als u mobiele toegang voor Exchange Online inschakelt, kunt u [blokkerings ActiveSync-clients](secure-email-recommended-policies.md#block-activesync-clients)implementeren, zodat Exchange ActiveSync-clients niet via basisverificatie verbinding maken met Exchange Online. Dit beleid is niet afbeelding van de afbeelding boven aan dit artikel. In dit onderwerp wordt beschreven hoe u [beleids aanbevelingen voor de beveiliging van e-mail ontvangt](secure-email-recommended-policies.md).

 Voor deze beleidsregels gelden de [goedgekeurde client-app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) en het vereisen van een [app-beveiligingsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Ten slotte kunt u de oudere verificatie voor andere client-apps op iOS-en Android-apparaten blokkeren, zodat deze clients geen regels voor voorwaardelijke toegang kunnen negeren. Als u de instructies in dit artikel volgt, hebt u al een [Blokkeer clients geconfigureerd die moderne verificatie niet ondersteunen](#block-clients-that-dont-support-modern-authentication).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several conditional access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Beleid voor naleving van apparaat definiëren

Beleidsregels voor naleving definiëren de vereisten waaraan apparaten moeten voldoen om te kunnen worden gemarkeerd als compatibel. Maak een intune-apparaatcompatibiliteitbeleid vanuit het Beheercentrum van Microsoft Endpoint Manager.

Maak een beleid voor elk platform:
- Android-apparaat beheerder
- Android Enterprise
- iOS-iPadOS
- macOS
- Windows Phone 8.1
- Windows 8,1 en hoger
- Windows 10 en hoger

U maakt beleidsregels voor naleving van apparaten door u aan te melden bij het [Microsoft Endpoint Manager-Beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) met uw **Devices**beheerdersreferenties en vervolgens naar  >  **Compliance policies**  >  **beleidsregels**voor naleving van apparatuur te navigeren. Selecteer **beleid maken**.

Voor het toepassen van apparaatcompatibiliteit moet de beleidsregels worden toegewezen aan gebruikersgroepen. U kunt een beleid toewijzen nadat u het hebt gemaakt en opgeslagen. Selecteer in het Beheercentrum het beleid en selecteer vervolgens **opdrachten**. Nadat u de groepen waarvoor u het beleid wilt ontvangen, hebt geselecteerd, selecteert u **Opslaan** om deze groepstoewijzing op te slaan en het beleid te implementeren.

Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) in de intune-documentatie voor stapsgewijze instructies voor het maken van compliance-beleidsregels in intune.

De volgende instellingen worden aanbevolen voor Windows 10.

**Apparaatstatusverklaring: evaluatie regels voor Windows Health Attestation-service**

|Eigenschappen|Waarden|Opmerkingen|
|:---------|:-----|:----|
|BitLocker vereisen|Dient||
|Het veilig opstarten moet zijn ingeschakeld op het apparaat|Dient||
|Code integriteit vereist|Dient||


**Eigenschappen van apparaat**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Versie van besturingssysteem|Alles|Niet geconfigureerd||

**Systeembeveiliging**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Wachtwoord|Een wachtwoord vereisen om mobiele apparaten te ontgrendelen|Dient||
||Eenvoudige wachtwoorden|Blokkeren||
||Type wachtwoord|Apparaat standaard||
||Minimale wachtwoordlengte|zes||
||Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist|15|Deze instelling wordt ondersteund voor Android-versies 4,0 en hoger of KNOX 4,0 en hoger. Voor iOS-apparaten is de ondersteuning voor iOS 8,0 en hoger.|
||Wachtwoord verloopt (dagen)|41||
||Aantal eerdere wachtwoorden om hergebruik te voorkomen|vijf||
||Wachtwoord vereisen wanneer het apparaat niet-actief is (mobiele en Holographic)|Dient|Beschikbaar voor Windows 10 en nieuwere versies|
|Versleuteling|Versleuteling van gegevensopslag op apparaat|Dient||
|Beveiliging van apparaten|Blokkeert|Dient||
||Antivirussoftware|Dient||
||Programma's|Dient|Voor deze instelling is een anti spyware-oplossing vereist die is geregistreerd met Windows Beveiligingscentrum|
|Beschermd|Microsoft Defender antimalware|Dient||
||Minimale versie Microsoft Defender antimalware||Alleen ondersteund voor de bureaubladversie van Windows 10. Microsoft adviseert geen versies van meer dan vijf erachter van de meest recente versie|
||Microsoft Defender antimalware-handtekening up-to-date|Dient||
||Real-time beveiliging|Dient|Alleen ondersteund voor Windows 10-bureaublad|

**Microsoft Defender ATP**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Regels voor Geavanceerd Bedreigingsbeveiliging voor Microsoft Defender|Het apparaat moet zich op of onder de risicoscore voor de machine bevinden|Medium||


## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Compatibele Pc's (maar niet compliant telefoons en tablets) vereisen
Voordat u een beleid toevoegt voor het vereisen van compatibele Pc's, moet u de apparaten voor het beheer van intune registreren. Het gebruik van multi-factor Authentication wordt aanbevolen voordat u apparaten registreert voor een intune-service om zeker te zijn dat het apparaat in bezit is van de bedoelde gebruiker. 

Compatibele Pc's vereisen:

1. Ga naar de [Azure-Portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies in de sectie **beveiliging** de optie **voorwaardelijke toegang**.

4. Kies **nieuwe beleids**optie.

5. Voer een Beleidsnaam in en kies vervolgens de **gebruikers en groepen** waarop u het beleid wilt toepassen.

6. Kies **Cloud-apps**.

7. Kies **apps selecteren**, selecteer de gewenste apps in de lijst met **Cloud apps** . Selecteer bijvoorbeeld Exchange Online. Kies **Select** en **done**.

8. Als u voldoet aan compatibele Pc's, maar niet compliante telefoons en tablets, kies dan **voorwaarden** en **platforms**. Kies **hardwareplatforms selecteren** en selecteer **Windows** en **macOS**.

9. Kies **verlenen** via de sectie **toegangsbeheer** .

10. Kies **toegang verlenen**, selecteer **apparaat vereisen om als compatibel te markeren**. Voor meerdere besturingselementen selecteert u **alle geselecteerde besturingselementen vereisen**en kiest **u vervolgens selecteren**. 

11. Kies **Create**.

Als u wilt dat het om compatibele Pc's *en* mobiele apparaten moet voldoen, selecteert u geen platforms. Dit dwingt naleving af op alle apparaten. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Compatibele Pc's *en* mobiele apparaten vereisen

Naleving voor alle apparaten vereisen:

1. Ga naar de [Azure-Portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies in de sectie **beveiliging** de optie **voorwaardelijke toegang**.

4. Kies **nieuwe beleids**optie.

5. Voer een Beleidsnaam in en kies vervolgens de **gebruikers en groepen** waarop u het beleid wilt toepassen.

6. Kies **Cloud-apps**.

7. Kies **apps selecteren**, selecteer de gewenste apps in de lijst met **Cloud apps** . Selecteer bijvoorbeeld Exchange Online. Kies **Select** en **done**.

8. Kies **verlenen** via de sectie **toegangsbeheer** .

9. Kies **toegang verlenen**, selecteer **apparaat vereisen om als compatibel te markeren**. Voor meerdere besturingselementen selecteert u **alle geselecteerde besturingselementen vereisen**en kiest **u vervolgens selecteren**. 

10. Kies **Create**.

Selecteer geen platforms wanneer u dit beleid maakt. Hiermee dwingt u geschikte apparaten af.


## <a name="next-steps"></a>Volgende stappen

[Meer informatie over beleids aanbevelingen voor het beveiligen van e-mail](secure-email-recommended-policies.md)
