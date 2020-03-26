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
ms.openlocfilehash: 772c4c5785115995593a4946bfbac49312ad15f3
ms.sourcegitcommit: 8e8230ceab480a5f1506e31de828f04f5590a350
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2020
ms.locfileid: "42959226"
---
# <a name="common-identity-and-device-access-policies"></a>Gemeenschappelijk beleid voor identiteits- en apparaattoegangs
In dit artikel worden de algemene aanbevolen beleidsregels beschreven voor het beveiligen van toegang tot cloudservices, waaronder on-premises toepassingen die zijn gepubliceerd met Azure AD Application Proxy. 

In deze leidraad wordt besproken hoe u het aanbevolen beleid in een nieuw ingerichte omgeving implementeert. Als u dit beleid in een afzonderlijke labomgeving instelt, u het aanbevolen beleid begrijpen en evalueren voordat de implementatie naar uw preproductie- en productieomgevingen wordt georganiseerd. Uw nieuw ingerichte omgeving kan alleen in de cloud of hybride zijn.  

## <a name="policy-set"></a>Beleidsset 

In het volgende diagram wordt de aanbevolen set beleidsregels weergegeven. Hierin wordt weergegeven op welke beschermingslaag elk beleid van toepassing is en of het beleid van toepassing is op pc's of telefoons en tablets, of op beide categorieën apparaten. Het geeft ook aan waar deze beleidsregels zijn geconfigureerd.

![Algemeen beleid voor het configureren van identiteit en apparaattoegang](../media/Identity_device_access_policies_byplan.png)


In de rest van dit artikel wordt beschreven hoe u dit beleid configureren. 

Het gebruik van multi-factor authenticatie wordt aanbevolen voordat u apparaten inschrijft bij Intune om te garanderen dat het apparaat in het bezit is van de beoogde gebruiker. U moet apparaten ook inschrijven bij Intune voordat u het nalevingsbeleid van apparaten afdwingt.

Als u tijd wilt geven om deze taken uit te voeren, raden we u aan het basislijnbeleid in de volgorde in deze tabel te implementeren. Het MFA-beleid voor gevoelige en sterk gereguleerde bescherming kan echter op elk moment worden uitgevoerd.


|Beschermingsniveau|Beleid|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|        |[Cliënten blokkeren die geen moderne verificatie ondersteunen](#block-clients-that-dont-support-modern-authentication)|Clients die geen moderne authenticatie gebruiken, kunnen regels voor voorwaardelijke toegang omzeilen, dus het is belangrijk om deze te blokkeren|
|        |[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](#high-risk-users-must-change-password)|Dwingt gebruikers om hun wachtwoord te wijzigen wanneer ze zich aanmelden als activiteit met een hoog risico wordt gedetecteerd voor hun account|
|        |[Beleid voor app-beveiliging definiëren](#define-app-protection-policies)|Eén beleid per platform (iOS, Android, Windows).|
|        |[Apps vereisen die het beleid voor app-beveiliging van Intune ondersteunen](#require-apps-that-support-intune-app-protection-policies)|Dwingt mobiele app-beveiliging voor telefoons en tablets af|
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

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Opnemen|Gebruikers en groepen selecteren – Selecteer specifieke beveiligingsgroep met gerichte gebruikers|Begin met beveiligingsgroep inclusief pilotgebruikers|
||Uitsluiten|Uitzonderingsbeveiligingsgroep; serviceaccounts (app-identiteiten)|Lidmaatschap gewijzigd op een indien nodig tijdelijke basis|
|Cloud-apps|Opnemen|Selecteer de apps waarop u deze regel wilt toepassen. Selecteer bijvoorbeeld Office 365 Exchange Online||
|Voorwaarden|Geconfigureerd|Ja|Configureren specifiek voor uw omgeving en behoeften|
|Aanmeldingsrisico|Risiconiveau||Zie de richtlijnen in de volgende tabel|

**Aanmeldingsrisico**

Pas de instellingen toe op basis van het beveiligingsniveau dat u target.

|Eigenschap|Beschermingsniveau|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Risiconiveau|Basislijn|Hoog, gemiddeld|Controleer beide|
| |Gevoelig|Hoog, gemiddeld, laag|Controleer alle drie|
| |Sterk gereglementeerd| |Laat alle opties onaangevinkt om MFA altijd af te dwingen|

**Toegangsbesturingselementen**

|Type|Eigenschappen|Waarden|Opmerkingen|
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

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Opnemen|Gebruikers en groepen selecteren – Selecteer specifieke beveiligingsgroep met gerichte gebruikers|Begin met beveiligingsgroep inclusief pilotgebruikers|
||Uitsluiten|Uitzonderingsbeveiligingsgroep; serviceaccounts (app-identiteiten)|Lidmaatschap gewijzigd op tijdelijke basis|
|Cloud-apps|Opnemen|Selecteer de apps waarop u deze regel wilt toepassen. Selecteer bijvoorbeeld Office 365 Exchange Online||
|Voorwaarden|Geconfigureerd|Ja|Client-apps configureren|
|Client-apps|Geconfigureerd|Ja|Mobiele apps en desktopclients, Andere clients (selecteer beide)|

**Toegangsbesturingselementen**

|Type|Eigenschappen|Waarden|Opmerkingen|
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

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers|Opnemen|Alle gebruikers|Geselecteerde|
||Uitsluiten|Geen||
|Voorwaarden|Gebruikersrisico|High|Geselecteerde|

**Besturingselementen**

| Type | Eigenschappen | Waarden                  | Opmerkingen |
|:-----|:-----------|:------------------------|:------|
|      | Access     | Toegang toestaan            | Waar  |
|      | Access     | Wachtwoordwijziging vereisen | Waar  |

**Beoordeling:** niet van toepassing

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt door **Op**te kiezen . Overweeg ook het gebruik van de [tool Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen

## <a name="define-app-protection-policies"></a>Beleid voor app-beveiliging definiëren
App-beveiligingsbeleid (APP) bepaalt welke apps zijn toegestaan en welke acties ze kunnen uitvoeren met de gegevens van uw organisatie. De keuzes die beschikbaar zijn in APP stellen organisaties in staat om de bescherming af te stemmen op hun specifieke behoeften. Voor sommigen is het mogelijk niet duidelijk welke beleidsinstellingen nodig zijn om een volledig scenario te implementeren. Om organisaties te helpen prioriteit te geven aan het verharden van het eindpunt van mobiele klanten, heeft Microsoft taxonomie geïntroduceerd voor het APP-beheer voor gegevensbescherming voor iOS- en Android-mobiele apps. 

Het APP-kader voor gegevensbescherming is ingedeeld in drie verschillende configuratieniveaus, waarbij elk niveau het vorige niveau afbouwt: 

- Enterprise basic data protection zorgt ervoor dat apps worden beveiligd met een pincode en versleuteld en voert selectieve veegbewerkingen uit. Voor Android-apparaten valideert dit niveau de attest van Android-apparaten. Dit is een instapconfiguratie die vergelijkbare gegevensbeschermingscontrole biedt in het postvakbeleid van Exchange Online en IT en de gebruikerspopulatie introduceert in APP. 
- Enterprise enhanced data protection introduceert APP data lek preventie mechanismen en minimale OS-vereisten. Dit is de configuratie die van toepassing is op de meeste mobiele gebruikers die toegang hebben tot werk- of schoolgegevens. 
- Enterprise hoge gegevensbescherming introduceert geavanceerde mechanismen voor gegevensbescherming, verbeterde PIN-configuratie en APP Mobile Threat Defense. Deze configuratie is wenselijk voor gebruikers die toegang hebben tot gegevens met een hoog risico. 

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

## <a name="require-apps-that-support-intune-app-protection-policies"></a>Apps vereisen die het beleid voor app-beveiliging van Intune ondersteunen
Met Voorwaardelijke toegang kunnen organisaties de toegang tot goedgekeurde (moderne verificatiegeschikte) iOS- en Android-client-apps beperken met intune-app-beveiligingsbeleid dat op hen wordt toegepast. Er zijn verschillende beleid voor voorwaardelijke toegang vereist, waarbij elk beleid zich richt op alle potentiële gebruikers. Details over het maken van dit beleid vindt u in [Het beveiligingsbeleid voor apps vereisen voor toegang tot de cloud-app met voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Volg 'Stap 1: Configureer een Azure AD Conditional Access-beleid voor Office 365' in [scenario 1: Voor Office 365-apps zijn goedgekeurde apps met een beleid voor app-beveiliging vereist,](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)waarmee Outlook voor iOS en Android is ingesteld, maar kan UAuth-compatibele Exchange ActiveSync-clients worden verwijderd van een verbinding met Exchange Online.

   > [!NOTE]
   > Dit beleid zorgt ervoor dat mobiele gebruikers toegang hebben tot alle Office-eindpunten met behulp van de toepasselijke apps.

2. Als u mobiele toegang tot Exchange Online inschakelt, implementeert u [ActiveSync-clients blokkeren] (secure-email-recommended-policies.md#block-activesync-clients), waardoor Exchange ActiveSync-clients geen verbinding kunnen maken met Exchange Online.

   Het bovenstaande beleid maakt gebruik van de subsidiebesturingselementen [Vereist goedgekeurde client-app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) en [Vereist app-beveiligingsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Schakel verouderde verificatie voor andere client-apps op iOS- en Android-apparaten uit. Zie [Clients blokkeren die geen moderne verificatie ondersteunen](#block-clients-that-dont-support-modern-authentication)voor meer informatie.

## <a name="define-device-compliance-policies"></a>Beleid voor naleving van apparaten definiëren

In het beleid voor naleving van apparaten worden de vereisten gedefinieerd waaraan apparaten moeten voldoen om als compatibel te worden gemarkeerd. Maak intune-beleid voor apparaatnaleving vanuit de Azure-portal. 

Maak een beleid voor elk platform:
- Android
- Android-onderneming
- Ios
- Macos
- Windows Phone 8.1
- Windows 8.1 en hoger
- Windows 10 en hoger

Als u beleid voor naleving van apparaten wilt maken, meldt u zich aan bij de Microsoft Azure-portal met uw beheerreferenties en navigeert u vervolgens naar **Intune >-apparaatnaleving.** Selecteer **Beleid maken**.

De volgende instellingen worden aanbevolen voor Windows 10.

**Apparaatstatus: evaluatieregels voor windows health attestation service**

|Eigenschappen|Waarden|Opmerkingen|
|:---------|:-----|:----|
|BitLocker vereisen|Vereisen||
|Secure Boot moeten worden ingeschakeld op het apparaat|Vereisen||
|Code-integriteit vereisen|Vereisen||


**Eigenschappen van het apparaat**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Versie van het besturingssysteem|Alle|Niet geconfigureerd||

Voor al het bovenstaande beleid dat als geïmplementeerd moet worden beschouwd, moeten ze zijn gericht op gebruikersgroepen. U dit doen door het beleid (op Opslaan) of hoger te maken door **Implementatie beheren** te selecteren in de sectie **Beleid** (hetzelfde niveau als Toevoegen).

**Systeembeveiliging**

|Type|Eigenschappen|Waarden|Opmerkingen|
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
|Verdediger|Windows Defender Antimalware|Vereisen||
||Windows Defender Antimalware minimumversie||Alleen ondersteund voor Windows 10-bureaublad. Microsoft raadt versies niet meer dan vijf achter van de meest recente versie|
||Windows Defender Antimalware-handtekening up-to-date|Vereisen||
||Real-time bescherming|Vereisen|Alleen ondersteund voor Windows 10-bureaublad|

**Microsoft Defender ATP**

|Type|Eigenschappen|Waarden|Opmerkingen|
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
