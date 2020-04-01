---
title: Gemeenschappelijk beleid voor identiteits- en apparaattoegangsbeleid - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft het beleid voor Microsoft-aanbevelingen voor het toepassen van beleid en configuratie van identiteits- en apparaattoegangs.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
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
- remotework
ms.openlocfilehash: 8b5cb7d8d8b16fea1c1bef44e477dfd43a79a3d8
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081318"
---
# <a name="common-identity-and-device-access-policies"></a>Gemeenschappelijk beleid voor identiteits- en apparaattoegangs
In dit artikel worden de algemene aanbevolen beleidsregels beschreven voor het beveiligen van toegang tot cloudservices, waaronder on-premises toepassingen die zijn gepubliceerd met Azure AD Application Proxy. 

In deze leidraad wordt besproken hoe u het aanbevolen beleid in een nieuw ingerichte omgeving implementeert. Als u dit beleid in een afzonderlijke labomgeving instelt, u het aanbevolen beleid begrijpen en evalueren voordat de implementatie naar uw preproductie- en productieomgevingen wordt georganiseerd. Uw nieuw ingerichte omgeving kan alleen in de cloud of hybride zijn.  

## <a name="policy-set"></a>Beleidsset 

In het volgende diagram wordt de aanbevolen set beleidsregels weergegeven. Hierin wordt weergegeven op welke beschermingslaag elk beleid van toepassing is en of het beleid van toepassing is op pc's of telefoons en tablets, of op beide categorieën apparaten. Het geeft ook aan waar deze beleidsregels zijn geconfigureerd.

[![Algemeen beleid voor het configureren van identiteit en apparaattoegang](../media/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)
[Zie een grotere versie van deze afbeelding](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)

In de rest van dit artikel wordt beschreven hoe u dit beleid configureren. 

Het gebruik van multi-factor authenticatie wordt aanbevolen voordat u apparaten inschrijft bij Intune om te garanderen dat het apparaat in het bezit is van de beoogde gebruiker. U moet apparaten ook inschrijven bij Intune voordat u het nalevingsbeleid van apparaten afdwingt.

Als u tijd wilt geven om deze taken uit te voeren, raden we u aan het basislijnbeleid in de volgorde in deze tabel te implementeren. Het MFA-beleid voor gevoelige en sterk gereguleerde bescherming kan echter op elk moment worden uitgevoerd.


|Beschermingsniveau|Beleid|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|        |[Cliënten blokkeren die geen moderne verificatie ondersteunen](#block-clients-that-dont-support-modern-authentication)|Clients die geen moderne authenticatie gebruiken, kunnen regels voor voorwaardelijke toegang omzeilen, dus het is belangrijk om deze te blokkeren|
|        |[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](#high-risk-users-must-change-password)|Dwingt gebruikers om hun wachtwoord te wijzigen wanneer ze zich aanmelden als activiteit met een hoog risico wordt gedetecteerd voor hun account|
|        |[App-beleid voor gegevensbescherming toepassen](#apply-app-data-protection-policies)|Eén beleid per platform (iOS, Android, Windows). Intune App Protection Policies (APP) zijn vooraf gedefinieerde sets van bescherming, van niveau 1 tot niveau 3.|
|        |[Goedgekeurde apps en APP-beveiliging vereisen](#require-approved-apps-and-app-protection)|Dwingt mobiele app-beveiliging voor telefoons en tablets af|
|        |[Nalevingsbeleid voor apparaten definiëren](#define-device-compliance-policies)|Eén beleid voor elk platform|
|        |[Eis conforme pc’s](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Dwingt Intune-beheer van pc's af|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|         |[Compatibele pc's *en* mobiele apparaten vereisen](#require-compliant-pcs-and-mobile-devices)|Dwingt Intune-beheer af voor pc's en telefoon/tablets|
|**Sterk gereglementeerd**|[*Altijd* mfa nodig](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Beleid toewijzen aan gebruikers
Voordat u beleid configureert, identificeert u de Azure AD-groepen die u voor elke beveiligingslaag gebruikt. Doorgaans is basislijnbeveiliging van toepassing op iedereen in de organisatie. Een gebruiker die is opgenomen voor zowel basislijn als gevoelige bescherming, heeft alle basislijnbeleidsregels toegepast plus het gevoelige beleid. Bescherming is cumulatief en het meest restrictieve beleid wordt afgedwongen. 

Een aanbevolen praktijk is het maken van een Azure AD-groep voor uitsluiting van voorwaardelijke toegang. Voeg deze groep toe aan al uw regels voor voorwaardelijke toegang onder 'Uitsluiten'. Dit geeft u een methode om toegang te bieden aan een gebruiker terwijl u toegangsproblemen oplost. Dit wordt alleen aanbevolen als tijdelijke oplossing. Controleer deze groep op wijzigingen en zorg ervoor dat de uitsluitingsgroep alleen wordt gebruikt zoals bedoeld. 

In het volgende diagram vindt u een voorbeeld van gebruikerstoewijzing en uitsluitingen.

![Voorbeeld van gebruikerstoewijzing en uitsluitingen voor MFA-regels](../media/identity-access-policies-assignment.png)

In de illustratie krijgt het 'Top secret project X-team' een voorwaardelijk toegangsbeleid dat MFA *altijd*vereist. Wees verstandig bij het toepassen van hogere niveaus van bescherming voor gebruikers. Leden van dit projectteam moeten elke keer dat ze zich aanmelden twee vormen van verificatie verstrekken, zelfs als ze niet sterk gereguleerde inhoud bekijken.  

Alle Azure AD-groepen die als onderdeel van deze aanbevelingen zijn gemaakt, moeten worden gemaakt als Office 365-groepen. Dit is specifiek belangrijk voor de implementatie van Azure Information Protection (AIP) bij het beveiligen van documenten in SharePoint Online.

![Schermopname voor het maken van Office 365-groepen](../media/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>MFA vereisen op basis van aanmeldingsrisico
Voordat u MFA vereist, gebruikt u eerst een MFA-registratiebeleid voor identiteitsbescherming om gebruikers voor MFA te registreren. Nadat gebruikers zijn geregistreerd, u MFA afdwingen voor aanmelding. Het [vereiste werk](identity-access-prerequisites.md) omvat het registreren van alle gebruikers met MFA.

Ga als lid van het volgende over een nieuw beleid voor voorwaardelijke toegang: 

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies voorwaardelijke **toegang**onder de sectie **Beveiliging** .

4. Kies **Nieuw beleid**.

![CA-beleid basislijn](../media/secure-email/CA-EXO-policy-1.png)

 In de volgende tabellen worden de beleidsinstellingen voor voorwaardelijke toegang beschreven die voor dit beleid moeten worden geïmplementeerd.

**Toewijzingen**

|Type|Eigenschappen|Waarden|Notities|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Opnemen|Gebruikers en groepen selecteren – Selecteer specifieke beveiligingsgroep met gerichte gebruikers|Begin met beveiligingsgroep inclusief pilotgebruikers|
||Uitsluiten|Uitzonderingsbeveiligingsgroep; serviceaccounts (app-identiteiten)|Lidmaatschap gewijzigd op een indien nodig tijdelijke basis|
|Cloud-apps|Opnemen|Selecteer de apps waarop u deze regel wilt toepassen. Selecteer bijvoorbeeld Office 365 Exchange Online||
|Voorwaarden|Geconfigureerd|Ja|Configureren specifiek voor uw omgeving en behoeften|
|Aanmeldingsrisico|Risiconiveau||Zie de richtlijnen in de volgende tabel|

**Aanmeldingsrisico**

Pas de instellingen toe op basis van het beveiligingsniveau dat u target.

|Eigenschap|Beschermingsniveau|Waarden|Notities|
|:---|:---------|:-----|:----|
|Risiconiveau|Basislijn|Hoog, gemiddeld|Controleer beide|
| |Gevoelig|Hoog, gemiddeld, laag|Controleer alle drie|
| |Sterk gereglementeerd| |Laat alle opties onaangevinkt om MFA altijd af te dwingen|

**Toegangsbesturingselementen**

|Type|Eigenschappen|Waarden|Notities|
|:---|:---------|:-----|:----|
|Verlenen|Toegang verlenen|Waar|Geselecteerde|
||MFA vereisen|Waar|Cheque|
||Apparaat vereisen dat het als compatibel is gemarkeerd|Valse||
||Hybride Azure-apparaat vereisen dat is aangesloten bij AD|Valse||
||Goedgekeurde client-app vereisen|Valse||
||Alle geselecteerde besturingselementen vereisen|Waar|Geselecteerde|

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt door **Op**te kiezen . Overweeg ook het gebruik van de [Tool Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Cliënten blokkeren die geen moderne verificatie ondersteunen
1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies voorwaardelijke **toegang**onder de sectie **Beveiliging** .

4. Kies **Nieuw beleid**.

In de volgende tabellen worden de beleidsinstellingen voor voorwaardelijke toegang beschreven die voor dit beleid moeten worden geïmplementeerd.

**Toewijzingen**

|Type|Eigenschappen|Waarden|Notities|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Opnemen|Gebruikers en groepen selecteren – Selecteer specifieke beveiligingsgroep met gerichte gebruikers|Begin met beveiligingsgroep inclusief pilotgebruikers|
||Uitsluiten|Uitzonderingsbeveiligingsgroep; serviceaccounts (app-identiteiten)|Lidmaatschap gewijzigd op tijdelijke basis|
|Cloud-apps|Opnemen|Selecteer de apps waarop u deze regel wilt toepassen. Selecteer bijvoorbeeld Office 365 Exchange Online||
|Voorwaarden|Geconfigureerd|Ja|Client-apps configureren|
|Client-apps|Geconfigureerd|Ja|Mobiele apps en desktopclients, Andere clients (selecteer beide)|

**Toegangsbesturingselementen**

|Type|Eigenschappen|Waarden|Notities|
|:---|:---------|:-----|:----|
|Verlenen|Toegang blokkeren|Waar|Geselecteerde|
||MFA vereisen|Valse||
||Apparaat vereisen dat het als compatibel is gemarkeerd|Valse||
||Hybride Azure-apparaat vereisen dat is aangesloten bij AD|Valse||
||Goedgekeurde client-app vereisen|Valse||
||Alle geselecteerde besturingselementen vereisen|Waar|Geselecteerde|

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt door **Op**te kiezen . Overweeg ook het gebruik van de [Tool Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen.



## <a name="high-risk-users-must-change-password"></a>Gebruikers met een hoog risico moeten het wachtwoord wijzigen
Om ervoor te zorgen dat de gecompromitteerde accounts van gebruikers met een hoog risico worden gedwongen om een wachtwoordwijziging uit te voeren bij het aanmelden, moet u het volgende beleid toepassen.

Meld u aan bij de [Microsoft Azure-portal (methttps://portal.azure.com) ](https://portal.azure.com/) uw beheerdersreferenties) en navigeer vervolgens naar Azure **AD-identiteitsbeveiliging > gebruikersrisicobeleid**.

**Toewijzingen**

|Type|Eigenschappen|Waarden|Notities|
|:---|:---------|:-----|:----|
|Gebruikers|Opnemen|Alle gebruikers|Geselecteerde|
||Uitsluiten|Geen||
|Voorwaarden|Gebruikersrisico|High|Geselecteerde|

**Besturingselementen**

| Type | Eigenschappen | Waarden                  | Notities |
|:-----|:-----------|:------------------------|:------|
|      | Access     | Toegang toestaan            | Waar  |
|      | Access     | Wachtwoordwijziging vereisen | Waar  |

**Beoordeling:** niet van toepassing

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt door **Op**te kiezen . Overweeg ook het gebruik van de [tool Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen

## <a name="apply-app-data-protection-policies"></a>App-beleid voor gegevensbescherming toepassen
App-beveiligingsbeleid (APP) bepaalt welke apps zijn toegestaan en welke acties ze kunnen uitvoeren met de gegevens van uw organisatie. De keuzes die beschikbaar zijn in APP stellen organisaties in staat om de bescherming af te stemmen op hun specifieke behoeften. Voor sommigen is het mogelijk niet duidelijk welke beleidsinstellingen nodig zijn om een volledig scenario te implementeren. Om organisaties te helpen prioriteit te geven aan het verharden van het eindpunt van mobiele klanten, heeft Microsoft taxonomie geïntroduceerd voor het APP-beheer voor gegevensbescherming voor iOS- en Android-mobiele apps. 

Het APP-kader voor gegevensbescherming is ingedeeld in drie verschillende configuratieniveaus, waarbij elk niveau het vorige niveau afbouwt: 

- **Enterprise Basic Data Protection** (Level 1) zorgt ervoor dat apps worden beveiligd met een pincode en versleuteld en selectieve veegbewerkingen uitvoeren. Voor Android-apparaten valideert dit niveau de attest van Android-apparaten. Dit is een instapconfiguratie die vergelijkbare gegevensbeschermingscontrole biedt in het postvakbeleid van Exchange Online en IT en de gebruikerspopulatie introduceert in APP. 
- **Enterprise enhanced data protection** (Level 2) introduceert APP data lekpreventie mechanismen en minimale OS-vereisten. Dit is de configuratie die van toepassing is op de meeste mobiele gebruikers die toegang hebben tot werk- of schoolgegevens. 
- **Enterprise high data protection** (Level 3) introduceert geavanceerde mechanismen voor gegevensbescherming, verbeterde pincodeconfiguratie en APP Mobile Threat Defense. Deze configuratie is wenselijk voor gebruikers die toegang hebben tot gegevens met een hoog risico. 

Als u de specifieke aanbevelingen voor elk configuratieniveau en de minimale apps wilt bekijken die moeten worden beschermd, controleert u [het kader voor gegevensbescherming met behulp van app-beveiligingsbeleid](https://docs.microsoft.com/mem/intune/apps/app-protection-framework). 

Met behulp van de principes die worden beschreven in [de configuraties voor identiteits- en apparaattoegang,](microsoft-365-policies-configurations.md)worden de niveaus basislijn en gevoelige beveiliging nauwkeurig afgestemd op de instellingen voor gegevensbescherming van niveau 2. De sterk gereguleerde beveiligingslaag wordt nauwkeurig toegewezen aan de instellingen voor hoge gegevensbescherming van niveau 3.

|Beschermingsniveau |Beleid voor app-beveiliging  |Meer informatie  |
|---------|---------|---------|
|Basislijn     | [Niveau 2 verbeterde gegevensbescherming](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | De beleidsinstellingen die in niveau 2 worden afgedwongen, bevatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en worden alleen toegevoegd aan of worden bijgewerkt met de onderstaande beleidsinstellingen om meer besturingselementen en een meer geavanceerde configuratie dan niveau 1 te implementeren.         |
|Gevoelig     | [Niveau 2 verbeterde gegevensbescherming](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | De beleidsinstellingen die in niveau 2 worden afgedwongen, bevatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en worden alleen toegevoegd aan of worden bijgewerkt met de onderstaande beleidsinstellingen om meer besturingselementen en een meer geavanceerde configuratie dan niveau 1 te implementeren.        |
|Sterk gereguleerd     | [Niveau 3 onderneming hoge gegevensbescherming](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | De beleidsinstellingen die in niveau 3 worden afgedwongen, bevatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en 2 en worden alleen toegevoegd aan of worden bijgewerkt met de onderstaande beleidsinstellingen om meer besturingselementen en een meer geavanceerde configuratie dan niveau 2 te implementeren.        |

Als u een nieuw beleid voor app-beveiliging wilt maken voor elk platform (iOS en Android) binnen Microsoft Endpoint Manager met behulp van de instellingen voor het kader voor gegevensbescherming, kunnen beheerders:
1. Maak het beleid handmatig door de stappen te volgen in [Het beveiligingsbeleid voor apps maken en implementeren met Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies). 
2. Importeer het voorbeeld [Van het Intune App Protection Policy Configuration Framework JSON-sjablonen](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) met [de PowerShell-scripts van Intune.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Goedgekeurde apps en APP-beveiliging vereisen
Als u het app-beveiligingsbeleid wilt afdwingen dat u in Intune hebt toegepast, moet u een regel voor voorwaardelijke toegang maken om goedgekeurde client-apps en de voorwaarden in het app-beveiligingsbeleid te vereisen. 

Voor het afdwingen van app-beveiligingsbeleid is een reeks beleidsregels vereist die zijn beschreven in [Het beleid voor app-beveiliging vereisen voor toegang tot cloud-apps met voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access). Deze beleidsregels zijn elk opgenomen in deze aanbevolen set identiteits- en toegangsconfiguratiebeleid.

Als u de regel voor voorwaardelijke toegang wilt maken waarvoor goedgekeurde apps en app-beveiliging vereist zijn, volgt u 'Stap 1: Configureer een Azure AD Conditional Access-beleid voor Office 365' in [Scenario 1: Voor Office 365-apps zijn goedgekeurde apps met een app-beveiligingsbeleid vereist,](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)waarmee Outlook voor iOS en Android is toegestaan, maar blokkeert UAuth-compatibele Exchange ActiveSync-clients om verbinding te maken met Exchange Online.

   > [!NOTE]
   > Dit beleid zorgt ervoor dat mobiele gebruikers toegang hebben tot alle Office-eindpunten met behulp van de toepasselijke apps.

Als u mobiele toegang tot Exchange Online inschakelt, implementeert u [Block ActiveSync-clients](secure-email-recommended-policies.md#block-activesync-clients), waardoor Exchange ActiveSync-clients geen verbinding kunnen maken met Exchange Online. Dit beleid is niet afgebeeld in de afbeelding bovenaan dit artikel. Het wordt beschreven en afgebeeld in [beleidsaanbevelingen voor het beveiligen van e-mail.](secure-email-recommended-policies.md)

 Met dit beleid wordt gebruikgemaakt van de subsidiebesturingselementen [Vereist goedgekeurde client-app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) en [Vereist app-beveiligingsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Ten slotte zorgt het blokkeren van oudere verificatie voor andere client-apps op iOS- en Android-apparaten ervoor dat deze clients voorwaardelijke toegangsregels niet kunnen omzeilen. Als u de richtlijnen in dit artikel volgt, hebt u Blokclients die [geen moderne verificatie ondersteunen,](#block-clients-that-dont-support-modern-authentication)al geconfigureerd.

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several conditional access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Office 365" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Beleid voor naleving van apparaten definiëren

In het beleid voor naleving van apparaten worden de vereisten gedefinieerd waaraan apparaten moeten voldoen om als compatibel te worden gemarkeerd. Maak intune-beleid voor apparaatnaleving vanuit het Microsoft Endpoint Manager-beheercentrum.

Maak een beleid voor elk platform:
- Beheerder van Android-apparaten
- Android Enterprise
- iOS/iPadOS
- Macos
- Windows Phone 8.1
- Windows 8.1 en hoger
- Windows 10 en hoger

Als u beleid voor naleving van apparaten wilt maken, meldt u zich aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) met uw beheerreferenties en navigeert u vervolgens naar**het beleid****voor** > naleving **van apparaten** > . Selecteer **Beleid maken**.

Als u het nalevingsbeleid van apparaten wilt implementeren, moeten deze worden toegewezen aan gebruikersgroepen. U wijst een beleid toe nadat u het hebt gemaakt en opgeslagen. Selecteer in het beheercentrum het beleid en selecteer **Toewijzingen**. Nadat u de groepen hebt geselecteerd die u het beleid wilt ontvangen, selecteert u **Opslaan** om die groepstoewijzing op te slaan en het beleid te implementeren.

Zie [Een nalevingsbeleid maken in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) in de Intune-documentatie voor stapsgewijze richtlijnen voor het maken van nalevingsbeleid in Intune.

De volgende instellingen worden aanbevolen voor Windows 10.

**Apparaatstatus: evaluatieregels voor windows health attestation service**

|Eigenschappen|Waarden|Notities|
|:---------|:-----|:----|
|BitLocker vereisen|Vereisen||
|Secure Boot moeten worden ingeschakeld op het apparaat|Vereisen||
|Code-integriteit vereisen|Vereisen||


**Eigenschappen van het apparaat**

|Type|Eigenschappen|Waarden|Notities|
|:---|:---------|:-----|:----|
|Versie van het besturingssysteem|Alle|Niet geconfigureerd||

**Systeembeveiliging**

|Type|Eigenschappen|Waarden|Notities|
|:---|:---------|:-----|:----|
|Wachtwoord|Een wachtwoord vereisen om mobiele apparaten te ontgrendelen|Vereisen||
||Eenvoudige wachtwoorden|Blok||
||Wachtwoordtype|Standaard apparaat||
||Minimale wachtwoordlengte|6||
||Maximale minuten van inactiviteit voordat wachtwoord vereist is|15|Deze instelling wordt ondersteund voor Android-versies 4.0 en hoger of KNOX 4.0 en hoger. Voor iOS-apparaten wordt het ondersteund voor iOS 8.0 en hoger|
||Wachtwoord vervaldatum (dagen)|41||
||Aantal eerdere wachtwoorden om hergebruik te voorkomen|5||
||Wachtwoord vereisen wanneer apparaat terugkeert van niet-actieve status (mobiel en holografisch)|Vereisen|Beschikbaar voor Windows 10 en hoger|
|Codering|Versleuteling van gegevensopslag op het apparaat|Vereisen||
|Apparaatbeveiliging|Firewall|Vereisen||
||Antivirus|Vereisen||
||Antispyware|Vereisen|Deze instelling vereist een anti-spyware-oplossing die is geregistreerd bij Windows Security Center|
|Verdediger|Microsoft Defender Antimalware|Vereisen||
||Microsoft Defender Antimalware minimumversie||Alleen ondersteund voor Windows 10-bureaublad. Microsoft raadt versies niet meer dan vijf achter van de meest recente versie|
||Microsoft Defender Antimalware-handtekening up-to-date|Vereisen||
||Real-time bescherming|Vereisen|Alleen ondersteund voor Windows 10-bureaublad|

**Microsoft Defender ATP**

|Type|Eigenschappen|Waarden|Notities|
|:---|:---------|:-----|:----|
|Microsoft Defender Advanced Threat Protection-regels|Het apparaat moeten op of onder de machine-risicoscore bevinden|Medium||


## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Compatibele pc's vereisen (maar niet voldoen aan telefoons en tablets)
Voordat u een beleid toevoegt dat compatibele pc's vereist, moet u apparaten inschrijven voor beheer in Intune. Het gebruik van multi-factor authenticatie wordt aanbevolen voordat u apparaten inschrijft bij Intune om te garanderen dat het apparaat in het bezit is van de beoogde gebruiker. 

Ga als nodig:

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies voorwaardelijke **toegang**onder de sectie **Beveiliging** .

4. Kies **Nieuw beleid**.

5. Voer een beleidsnaam in en kies vervolgens de **gebruikers en groepen** waarvoor u het beleid wilt toepassen.

6. Kies **Cloud-apps**.

7. Kies **Apps selecteren**, selecteer de gewenste apps in de lijst Met **Cloud-apps.** Selecteer bijvoorbeeld Office 365 Exchange Online. Kies **Selecteren** en **gereed**.

8. Als u compatibele pc's nodig hebt, maar niet voldoen aan telefoons en tablets, kiest u **Voorwaarden** en **apparaatplatforms.** Kies **Apparaatplatforms selecteren** en selecteer **Windows** en **macOS**.

9. Kies **Verlenen** in de sectie **Toegangsbesturingselementen.**

10. Kies **Toegang verlenen**, selecteer Apparaat vereisen dat als compatibel moet zijn **gemarkeerd**. Selecteer Voor meerdere besturingselementen **Alle geselecteerde besturingselementen vereisen**en kies selecteer **Selecteren**. 

11. Kies **Create**.

Als het uw doel is om compatibele pc's *en* mobiele apparaten te vereisen, selecteert u geen platforms. Dit dwingt naleving voor alle apparaten af. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Compatibele pc's *en* mobiele apparaten vereisen

Naleving voor alle apparaten vereisen:

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies voorwaardelijke **toegang**onder de sectie **Beveiliging** .

4. Kies **Nieuw beleid**.

5. Voer een beleidsnaam in en kies vervolgens de **gebruikers en groepen** waarvoor u het beleid wilt toepassen.

6. Kies **Cloud-apps**.

7. Kies **Apps selecteren**, selecteer de gewenste apps in de lijst Met **Cloud-apps.** Selecteer bijvoorbeeld Office 365 Exchange Online. Kies **Selecteren** en **gereed**.

8. Kies **Verlenen** in de sectie **Toegangsbesturingselementen.**

9. Kies **Toegang verlenen**, selecteer Apparaat vereisen dat als compatibel moet zijn **gemarkeerd**. Selecteer Voor meerdere besturingselementen **Alle geselecteerde besturingselementen vereisen**en kies selecteer **Selecteren**. 

10. Kies **Create**.

Selecteer bij het maken van dit beleid geen platforms. Dit dwingt compatibele apparaten af.


## <a name="next-steps"></a>Volgende stappen

[Meer informatie over beleidsaanbevelingen voor het beveiligen van e-mail](secure-email-recommended-policies.md)
