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
ms.openlocfilehash: 8c4b136f30da0499b31102683f1a903e71813142
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547218"
---
# <a name="common-identity-and-device-access-policies"></a>Algemeen beleid voor identiteiten en apparaattoegang

In dit artikel wordt het aanbevolen beleid beschreven voor de beveiliging van de toegang tot Microsoft 365-cloudservices, waaronder on-premises toepassingen die zijn gepubliceerd met de toepassings proxy Azure Active Directory (Azure AD). 

In deze richtlijnen wordt uitgelegd hoe u de aanbevolen beleidsregels implementeert in een nieuw ingerichte omgeving. Door deze beleidsregels in een afzonderlijke lab-omgeving in te stellen, kunt u de aanbevolen beleidsregels uitleggen en evalueren voordat u de implementatie uitschakelt voor de producties en productieomgevingen. Uw zojuist ingerichte omgeving kan alleen in de Cloud of hybride worden weergegeven om de evaluatie behoeften weer te geven.  

## <a name="policy-set"></a>Beleidsinstelling 

In het volgende diagram wordt de aanbevolen set beleidsregels getoond. In dit voorbeeld wordt aangegeven welke beveiligings bescherming elk beleid van toepassing is en of het beleid van toepassing is op Pc's of telefoons en tablets, of op beide soorten apparaten. Ook wordt aangegeven waar u deze beleidsregels configureert.

[ ![ Veelgebruikte beleidsregels voor het configureren van de identiteit en Apparaattoegang bieden](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [een grotere versie van deze afbeelding weer](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

In de rest van dit artikel wordt uitgelegd hoe u deze beleidsregels configureert. 

>[!Note]
>Als u wilt dat het gebruik van multi-factor Authentication (MFA) wordt aanbevolen voordat u intune-apparaten registreert, moet u ervoor zorgen dat het apparaat over de juiste gebruiker beschikt. U moet apparaten in intune registreren voordat u beleidsregels voor apparaatcompatibiliteit kunt afdwingen.
>

Om u tijd te bieden voor het uitvoeren van deze taken, wordt u aangeraden het basisbeleid voor basisregels te implementeren in de volgorde waarin deze tabel wordt weergegeven. De MFA-beleidsregels voor gevoelige en hoogst gereglementeerde beveiligingsniveaus kunnen op elk moment worden geïmplementeerd.

|Beveiligingsniveau|Lijnen|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|        |[Clients blokkeren die moderne verificatie niet ondersteunen](#block-clients-that-dont-support-modern-authentication)|Clients die geen moderne verificatie gebruiken, kunnen het beleid voor voorwaardelijke toegang omzeilen, dus het is belangrijk dat u dit blokkeert.|
|        |[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](#high-risk-users-must-change-password)|Hiermee zorgt u dat gebruikers hun wachtwoord kunnen wijzigen bij het aanmelden als er een High Risk-activiteit voor hun account wordt gedetecteerd.|
|        |[Beleid voor app-gegevensbeveiliging toepassen](#apply-app-data-protection-policies)|Eén beleid voor het intune-app-bescherming per platform (Windows, iOS of iPadOS, Android).|
|        |[Goedgekeurde apps en app-beveiliging vereisen](#require-approved-apps-and-app-protection)|Hiermee wordt de bescherming van de mobiele app afgedwongen voor telefoons en tablets via iOS, iPadOS of Android.|
|        |[Beleidsregels voor naleving van apparaten definiëren](#define-device-compliance-policies)|Eén beleid voor elk platform.|
|        |[Eis conforme pc’s](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Het intune-beheer van Pc's afdwingen met behulp van Windows of MacOS.|
|**Gevoelig**|[MFA vereisen wanneer het aanmelding van risico *slecht*, *gemiddeld*of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|         |[Compatibele Pc's *en* mobiele apparaten vereisen](#require-compliant-pcs-and-mobile-devices)|Dwing het intune-beheer af voor Pc's (Windows of MacOS) en telefoons of Tablets (iOS, iPadOS of Android).|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](#require-mfa-based-on-sign-in-risk)|
| | | |

## <a name="assigning-policies-to-groups-and-users"></a>Beleid toewijzen aan groepen en gebruikers

Voordat u beleidsregels configureert, identificeert u de groepen van Azure AD die u voor elke beschermingsniveau gebruikt. Normaalgesproken geldt er basislijn beveiliging voor iedereen in de organisatie. Een gebruiker die is opgenomen in de basislijn en de gevoelige beveiliging, heeft alle toegepaste basisregels plus het gevoelige beleid. Beveiliging is cumulatief en het meest beperkte beleid wordt afgedwongen. 

U wordt geadviseerd een Azure AD-groep te maken voor de uitsluiting van voorwaardelijke toegang. Voeg deze groep toe aan al uw voorwaardelijke toegangsbeleidsregels in de instelling **uitsluiten** van de instelling **gebruikers en groepen** in de sectie **opdrachten** . U onthoudt een methode voor het verlenen van toegang aan een gebruiker wanneer u problemen met Access oplost. Dit wordt alleen aanbevolen als tijdelijke oplossing. Bewaakt deze groep voor wijzigingen en zorg ervoor dat de uitsluitings groep uitsluitend wordt gebruikt zoals bedoeld. 

Hier ziet u een voorbeeld van opdrachten en uitsluitingen van groepen voor de vereiste MFA.

![Voorbeeld van toewijzingen en uitsluitingen van groepen voor MFA-beleid](../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Dit zijn de resultaten:

- Alle gebruikers moeten gebruikmaken van MFA wanneer het aantekening van het risico normaal of hoog is.

- Leden van de groep werknemers moeten zijn verplicht MFA te gebruiken als het risico voor aanmeldingen laag, normaal of hoog is.

  In dit geval komen leden van de groep werknemers overeen met de basislijn en het beleid voor voorwaardelijke toegang. De besturingselementen voor het openen van beide beleidsregels worden gecombineerd, wat niet het geval is.

- Leden van de bovenste Secret Project X-groep zijn altijd verplicht MFA te gebruiken

  In dit geval komen leden van de bovenste geheimen van Project X-groepen overeen met het beleid voor voorwaardelijke toegang met basislijn en regels met volledig gereglementeerde regels. De toegangs elementen voor beide beleidsregels worden gecombineerd. Aangezien de toegangsregeling voor het zwaarbeveiligde beleid voor voorwaardelijke toegang meer beperkingen bevat, wordt dit gebruikt.

Wees voorzichtig wanneer u een hoger beveiligingsniveau toepast voor groepen en gebruikers. Leden van de hoofdmap Project X zijn bijvoorbeeld verplicht MFA te gebruiken telkens wanneer ze zich aanmelden, ook als ze niet werken met de uiterst gereguleerde inhoud van Project X.  

Alle Azure AD-groepen die als onderdeel van deze aanbevelingen zijn gemaakt, moeten worden gemaakt als Microsoft 365-groepen. Dit is belangrijk voor de implementatie van tekstlabels bij het beveiligen van documenten in Microsoft teams en SharePoint.

![Schermafbeelding van het maken van Microsoft 365-groepen](../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>MFA vereisen op basis van aanmeldings risico

U moet uw gebruikers registreren voor MFA voordat u het gebruik ervan moet vereisen. Als u met Microsoft 365 E5, Microsoft 365 E3 met de identiteit & invoegtoepassing voor beveiliging van bedreiging, Office 365 met EMS E5 of afzonderlijke Azure AD Premium-licenties hebt, kunt u het MFA-registratiebeleid gebruiken met Azure AD Identity Protection om gebruikers registreren voor MFA in te stellen. Het [vereiste werk](identity-access-prerequisites.md) omvat het registreren van alle gebruikers met MFA.

Nadat uw gebruikers zijn geregistreerd, kunt u MFA vereisen voor aanmelding met een nieuw beleid voor voorwaardelijke toegang.

1. Ga naar de [Azure-Portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies in de lijst met Azure-Services **Azure Active Directory**.
3. Kies **beveiliging**in de lijst **beheren** en kies **voorwaardelijke toegang**.
4. Kies **nieuwe beleids** tekst en typ de naam van het nieuwe beleid.

In de volgende tabellen worden de beleidsinstellingen voor voorwaardelijke toegang beschreven waarop MFA is vereist op basis van een aanmeldings risico.

In de sectie **opdrachten** :

|Instelling|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Voorzien| **Selecteer gebruikers en groepen > gebruikers en groepen**: Selecteer specifieke groepen met gerichte gebruikersaccounts. |Begin met de groep die gebruikersaccounts voor prototype bevat.|
||Uit| **Gebruikers en groepen**: Selecteer uw groep met uitzonderingen voor voorwaardelijke toegang. serviceaccounts (app-Identities).|Het lidmaatschap moet zo nodig worden gewijzigd.|
|Cloud-apps of-acties| **> van Cloud apps zijn inbegrepen** | **Selecteer apps**: Selecteer de apps waarop u dit beleid wilt toepassen. Selecteer bijvoorbeeld Exchange Online.||
|Vastgestelde| | |Configureer voorwaarden die specifiek zijn voor uw omgeving en behoefte.|
||Aanmeld risico||Zie de instructies in de volgende tabel.|
|||||

**Instellingen voor aanmeldings risico**

De instellingen voor risiconiveau toepassen op basis van het beschermingsniveau dat u wilt instellen.

|Beschermingsniveau|Vereiste risiconiveau waarden|Actierij|
|:---------|:-----|:----|
|Basislijn|Hoog, normaal|Schakel beide selectievakjes in.|
|Gevoelig|Hoog, normaal, laag|Selecteer alledrie.|
|Sterk gereglementeerd| |Schakel alle opties uit om MFA altijd af te dwingen.|
||||

In de sectie **Access-besturingselementen** :

|Instelling|Eigenschappen|Waarden|Actierij|
|:---|:---------|:-----|:----|
|Wijs|**Grant access**| | Kiest |
|||**Verificatie via meerdere factoren vereisen**| Cheque |
||**Alle geselecteerde besturingselementen vereisen** ||Kiest|
|||||

Kies **selecteren** om de **machtigings** instellingen op te slaan.

Selecteer ten slotte het selectievakje **ingeschakeld** voor het **beleid inschakelen**en kies vervolgens **maken**.

U kunt ook het hulpprogramma [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen.

## <a name="block-clients-that-dont-support-modern-authentication"></a>Cliënten blokkeren die geen moderne verificatie ondersteunen

Gebruik de instellingen in deze tabellen voor een voorwaardelijk toegangsbeleid om clients te blokkeren die moderne verificatie niet ondersteunen.

Zie [dit artikel](microsoft-365-client-support-modern-authentication.md) voor een lijst met klanten in microsoft 365 met moderne verificatie voor Suppport.

In de sectie **opdrachten** :

|Instelling|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Voorzien| **Selecteer gebruikers en groepen > gebruikers en groepen**: Selecteer specifieke groepen met gerichte gebruikersaccounts. |Begin met de groep die gebruikersaccounts voor prototype bevat.|
||Uit| **Gebruikers en groepen**: Selecteer uw groep met uitzonderingen voor voorwaardelijke toegang. serviceaccounts (app-Identities).|Het lidmaatschap moet zo nodig worden gewijzigd.|
|Cloud-apps of-acties|**> van Cloud apps zijn inbegrepen**| **Selecteer apps**: Selecteer de apps die overeenkomen met de clients die moderne verificatie niet ondersteunen.||
|Vastgestelde| **Client toepassingen** | Kies **Ja** voor **configureren** <br> De vinkjes voor **browser** -en **mobiele apps en desktop clients** wissen | |
||||

In de sectie **Access-besturingselementen** :

|Instelling|Eigenschappen|Waarden|Actierij|
|:---|:---------|:-----|:----|
|Wijs|**Toegang blokkeren**| | Kiest |
||**Alle geselecteerde besturingselementen vereisen** ||Kiest|
|||||

Kies **selecteren** om de **machtigings** instellingen op te slaan.

Selecteer ten slotte het selectievakje **ingeschakeld** voor het **beleid inschakelen**en kies vervolgens **maken**.

U kunt ook het hulpmiddel [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen.

## <a name="high-risk-users-must-change-password"></a>Gebruikers met een hoog risico moeten het wachtwoord wijzigen

U moet het volgende beleid toepassen om ervoor te zorgen dat alle accounts met een hoog risico voor het opnieuw instellen van wachtwoorden worden geforceerd wanneer ze zich aanmelden.

Meld u aan bij de [Microsoft Azure https://portal.azure.com) -Portal (](https://portal.azure.com/) met uw beheerdersreferenties en ga vervolgens naar **Azure AD-identiteitsbeveiliging > gebruikers risico beleid**.

In de sectie **opdrachten** :

|Type|Eigenschappen|Waarden|Actierij|
|:---|:---------|:-----|:----|
|Gebruikers|Voorzien|**Alle gebruikers**|Kiest|
|Gebruikers risico| **Hoog**||Kiest|
|||||

In het tweede gedeelte **toewijzingen** :

| Type | Eigenschappen | Waarden                  | Actierij |
|:-----|:-----------|:------------------------|:------|
| Access | **Toegang toestaan** |  | Kiest  |
|      |     | **Wachtwoord wijzigen vereist** | Cheque  |
|||||

Kies **gereed** om de instellingen voor **Access** op te slaan.

Selecteer ten slotte het selectievakje **inschakelen** voor **beleid afdwingen**en kies vervolgens **Opslaan**.

U kunt ook het hulpmiddel [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen.

U kunt dit beleid gebruiken in combinatie met [Azure AD-wachtwoordbeveiliging configureren](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad), waarmee bekende zwakke wachtwoorden en hun varianten worden gedetecteerd en geblokkeerd, en extra zwakke termen die specifiek zijn voor uw organisatie. Met de wachtwoordbeveiliging van Azure Active Directory zorgt u ervoor dat gewijzigde wachtwoorden sterk zijn.

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

U kunt als volgt een nieuw beleid voor app-beveiliging maken voor elk platform (iOS en Android) in Microsoft Endpoint Manager met de instellingen voor Data Protection Framework:

1. Maak handmatig een beleid door de stappen [te volgen voor het maken en implementeren van een app-beveiligingsbeleid met Microsoft intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies). 
2. Importeer de JSON-sjablonen voor het voorbeeld van een [intune-app-beveiligings raamwerk](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) met [de PowerShell-scripts van intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Goedgekeurde apps en APP-beveiliging vereisen

Als u wilt dat het beleid voor APP-beveiliging afdwingt dat u hebt toegepast op intune, moet u een beleid voor voorwaardelijke toegang maken om goedgekeurde client-apps en de voorwaarden in het beleid voor APP-beveiliging te vereisen. 

Voor het afdwingen van een APP-beveiligingsbeleid is een set beleidsregels vereist die worden beschreven in het [beleid voor de app-beveiliging vereisen voor toegang tot de Cloud-app met voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access). Deze beleidsregels zijn allemaal opgenomen in deze aanbevolen set identiteit en toegangsbeleid.

Als u het beleid voor voorwaardelijke toegang wilt maken waarvoor goedgekeurde apps en APP-beveiliging zijn vereist, volgt u ' stap 1: een Azure AD voor Microsoft-beleid instellen voor Microsoft 365 ' in [scenario 1: voor Microsoft 365-apps zijn goedgekeurde apps vereist met een app-beveiligingsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), waaronder Outlook voor IOS en Android-clients, maar wel VPN-clients met Exchange Online.

   > [!NOTE]
   > Met deze beleidsinstelling zorgt u ervoor dat mobiele gebruikers toegang hebben tot alle Office-eindpunten met behulp van de toepasselijke apps.

Als u mobiele toegang voor Exchange Online inschakelt, kunt u [blokkerings ActiveSync-clients](secure-email-recommended-policies.md#block-activesync-clients)implementeren, zodat Exchange ActiveSync-clients niet via basisverificatie verbinding maken met Exchange Online. Dit beleid is niet afbeelding van de afbeelding boven aan dit artikel. In dit onderwerp wordt beschreven hoe u [beleids aanbevelingen voor de beveiliging van e-mail ontvangt](secure-email-recommended-policies.md).

 Voor deze beleidsregels gelden de [goedgekeurde client-app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) en het vereisen van een [app-beveiligingsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Ten slotte kunt u de oudere verificatie voor andere client-apps op iOS-en Android-apparaten blokkeren, zodat deze clients geen beleid voor voorwaardelijke toegang kunnen negeren. Als u de instructies in dit artikel volgt, hebt u al een [Blokkeer clients geconfigureerd die moderne verificatie niet ondersteunen](#block-clients-that-dont-support-modern-authentication).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Beleid voor naleving van apparaat definiëren

Beleid voor naleving van apparaat definiëren de vereisten waaraan apparatuur moet voldoen om te voldoen aan de normen. U maakt een intune-apparaatcompatibiliteitbeleid vanuit het Beheercentrum van Microsoft Endpoint Manager.

U moet een beleid maken voor elke PC, telefoon of Tablet platform:

- Android-apparaat beheerder
- Android Enterprise
- iOS-iPadOS
- macOS
- Windows 8,1 en hoger
- Windows 10 en hoger

U maakt beleidsregels voor naleving van apparaten door u aan te melden bij het [Microsoft Endpoint Manager-Beheercentrum](https://endpoint.microsoft.com) met uw **Devices**beheerdersreferenties en vervolgens naar  >  beleidsregels voor**nalevingsbeleid**van apparaten te navigeren  >  **Policies**. Selecteer **beleid maken**.

Voor het toepassen van apparaatcompatibiliteit moet de beleidsregels worden toegewezen aan gebruikersgroepen. U kunt een beleid toewijzen nadat u het hebt gemaakt en opgeslagen. Selecteer in het Beheercentrum het beleid en selecteer vervolgens **opdrachten**. Nadat u de groepen waarvoor u het beleid wilt ontvangen, hebt geselecteerd, selecteert u **Opslaan** om deze groepstoewijzing op te slaan en het beleid te implementeren.

Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) in de intune-documentatie voor stapsgewijze instructies voor het maken van compliance-beleidsregels in intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Aanbevolen instellingen voor Windows 10 en hoger

De volgende instellingen worden aanbevolen voor Pc's met Windows 10 en latere versies, zoals is geconfigureerd in **stap 2: compliance Settings**, van het proces voor het maken van beleid.

Zie de volgende tabel voor meer informatie over de statuswaarden van de apparaatstatusverklaring- **Service >**.

|Eigenschappen|Value|Actierij|
|:---------|:-----|:----|
|BitLocker vereisen|Dient| Kiest |
|Het veilig opstarten moet zijn ingeschakeld op het apparaat|Dient| Kiest |
|Code integriteit vereist|Dient| Kiest |
||||

Voor **Apparaateigenschappen**geeft u de juiste waarden op voor besturingssysteemversies op basis van uw IT-en beveiligingsbeleid.

Voor **naleving van Configuration Manager**selecteert u **vereisen**.

Zie de volgende tabel voor meer informatie over **systeembeveiliging**.

|Type|Eigenschappen|Value|Actierij|
|:---|:---------|:-----|:----|
|Wachtwoord|Een wachtwoord vereisen om mobiele apparaten te ontgrendelen|Dient| Kiest |
||Eenvoudige wachtwoorden|Blokkeren|Kiest|
||Type wachtwoord|Apparaat standaard|Kiest|
||Minimale wachtwoordlengte|zes|Type|
||Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist|15|Type <br>Deze instelling wordt ondersteund voor Android-versies 4,0 en hoger of KNOX 4,0 en hoger. Voor iOS-apparaten is de ondersteuning voor iOS 8,0 en hoger.|
||Wachtwoord verloopt (dagen)|41|Type|
||Aantal eerdere wachtwoorden om hergebruik te voorkomen|vijf|Type|
||Wachtwoord vereisen wanneer het apparaat niet-actief is (mobiele en Holographic)|Dient|Beschikbaar voor Windows 10 en nieuwere versies|
|Versleuteling|Versleuteling van gegevensopslag op apparaat|Dient|Kiest|
|Beveiliging van apparaten|Blokkeert|Dient|Kiest|
||Antivirussoftware|Dient|Kiest|
||Programma's|Dient|Kiest <br> Voor deze instelling is een anti spyware-oplossing vereist die is geregistreerd met Windows Beveiligingscentrum.|
|Beschermd|Microsoft Defender antimalware|Dient|Kiest|
||Minimale versie Microsoft Defender antimalware||Type <br> Alleen ondersteund voor de bureaubladversie van Windows 10. Microsoft adviseert geen versies van meer dan vijf erachter van de meest recente versie.|
||Microsoft Defender antimalware-handtekening up-to-date|Dient|Kiest|
||Real-time beveiliging|Dient|Kiest <br>Alleen ondersteund voor Windows 10-bureaublad|
|||||

**Microsoft Defender ATP**

|Type|Eigenschappen|Value|Actierij|
|:---|:---------|:-----|:----|
|Regels voor Geavanceerd Bedreigingsbeveiliging voor Microsoft Defender|Het apparaat moet zich op of onder de risicoscore voor de machine bevinden|Medium|Kiest|
|||||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Compatibele Pc's (maar niet compliant telefoons en tablets) vereisen

Voordat u een beleid toevoegt voor het vereisen van compatibele Pc's, moet u de apparaten voor het beheer van intune registreren. Het gebruik van multi-factor Authentication wordt aanbevolen voordat u apparaten registreert voor een intune-service om zeker te zijn dat het apparaat in bezit is van de bedoelde gebruiker. 

Compatibele Pc's vereisen:

1. Ga naar de [Azure-Portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies in de lijst met Azure-Services **Azure Active Directory**.
3. Kies **beveiliging**in de lijst **beheren** en kies **voorwaardelijke toegang**.
4. Kies **nieuwe beleids** tekst en typ de naam van het nieuwe beleid.

5. Onder **toewijzingen**kiest u **gebruikers en groepen** , en kunt u ook aangeven met wie u het beleid wilt toepassen. Sluit ook uw groep met voorwaardelijke toegang.

6. Kies onder **opdrachten**de optie **Cloud-apps of acties**.

7. Voor **opnemen**kiest **u apps selecteren > selecteren**en selecteert u vervolgens de gewenste apps in de lijst met **Cloud-apps** . Selecteer bijvoorbeeld Exchange Online. Kies **selecteren wanneer u** klaar bent.

8. Als u compatibele Pc's (maar niet de compliant telefoons en tablets) nodig hebt, kiest u onder **opdrachten**de optie **voorwaarden > apparaat-platforms**. Selecteer **Ja** voor **configureren**. Kies  **hardwareplatforms selecteren**, selecteer **Windows** en **macOS**en kies vervolgens **gereed**.

9. Kies **subsidie** onder **toegangsbeheer**.

10. Kies **toegang verlenen** en controleer vervolgens of **apparaat is gemarkeerd als compatibel**. Voor meerdere besturingselementen selecteert u **alle geselecteerde besturingselementen vereisen**. Wanneer u klaar bent, kiest **u selecteren**. 

10. Selecteer **inschakelen** voor **beleids**optie en kies vervolgens **maken**.

>[!Note]
>Zorg ervoor dat uw apparaat compatibel is voordat u dit beleid inschakelt. Anders kon u uitgaand raken en kunt u dit beleid niet wijzigen totdat uw gebruikersaccount is toegevoegd aan de groep voorwaardelijke toegang.
>

## <a name="require-compliant-pcs-and-mobile-devices"></a>Compatibele Pc's *en* mobiele apparaten vereisen

Naleving voor alle apparaten vereisen:

1. Ga naar de [Azure-Portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies in de lijst met Azure-Services **Azure Active Directory**.
3. Kies **beveiliging**in de lijst **beheren** en kies **voorwaardelijke toegang**.
4. Kies **nieuwe beleids** tekst en typ de naam van het nieuwe beleid.

5. Onder **toewijzingen**kiest u **gebruikers en groepen** , en kunt u ook aangeven met wie u het beleid wilt toepassen. Sluit ook uw groep met voorwaardelijke toegang.

6. Kies onder **opdrachten**de optie **Cloud-apps of acties**.

7. Voor **opnemen**kiest **u apps selecteren > selecteren**en selecteert u vervolgens de gewenste apps in de lijst met **Cloud-apps** . Selecteer bijvoorbeeld Exchange Online. Kies **selecteren wanneer u** klaar bent.

8. Kies **subsidie** onder **toegangsbeheer**.

9. Kies **toegang verlenen** en controleer vervolgens of **apparaat is gemarkeerd als compatibel**. Voor meerdere besturingselementen selecteert u **alle geselecteerde besturingselementen vereisen**. Wanneer u klaar bent, kiest **u selecteren**. 

10. Selecteer **inschakelen** voor **beleids**optie en kies vervolgens **maken**.

>[!Note]
>Zorg ervoor dat uw apparaat compatibel is voordat u dit beleid inschakelt. Anders kon u uitgaand raken en kunt u dit beleid niet wijzigen totdat uw gebruikersaccount is toegevoegd aan de groep voorwaardelijke toegang.
>

## <a name="next-step"></a>Volgende stap

![Stap 3: beleid voor gast en externe gebruikers](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)


[Meer informatie over beleids aanbevelingen voor gast en externe gebruikers](identity-access-policies-guest-access.md)
