---
title: Gemeenschappelijk beleid voor identiteits- en apparaattoegang - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft het beleid voor Microsoft-aanbevelingen over het toepassen van beleid en configuraties voor identiteits- en apparaattoegang.
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
ms.openlocfilehash: 272e8a76cdb3a1555f561bd56e63422f14394904
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809841"
---
# <a name="common-identity-and-device-access-policies"></a>Gemeenschappelijk beleid voor identiteits- en apparaattoegang
In dit artikel wordt het algemene aanbevolen beleid beschreven voor het beveiligen van toegang tot cloudservices, inclusief on-premises toepassingen die zijn gepubliceerd met Azure AD-toepassingsproxy. 

In deze richtlijnen wordt besproken hoe het aanbevolen beleid kan worden geïmplementeerd in een nieuw ingerichte omgeving. Als u dit beleid instelt in een afzonderlijke labomgeving, u het aanbevolen beleid begrijpen en evalueren voordat u de implementatie naar uw preproductie- en productieomgevingen organiseert. Uw nieuw ingerichte omgeving kan alleen in de cloud of hybride zijn.  

## <a name="policy-set"></a>Beleidsset 

Het volgende diagram illustreert de aanbevolen set beleidsregels. Het geeft aan op welke beschermingsniveaus elk beleid van toepassing is en of het beleid van toepassing is op pc's of telefoons en tablets, of op beide categorieën apparaten. Het geeft ook aan waar deze beleidsregels zijn geconfigureerd.

![Gemeenschappelijk beleid voor het configureren van identiteits- en apparaattoegang](../media/Identity_device_access_policies_byplan.png)


In de rest van dit artikel wordt beschreven hoe u dit beleid configureren. 

Het gebruik van multi-factor authenticatie wordt aanbevolen voordat u apparaten inschrijft bij Intune om te garanderen dat het apparaat in het bezit is van de beoogde gebruiker. U moet apparaten ook inschrijven voor Intune voordat u het nalevingsbeleid van apparaten afdwingt.

Om u de tijd te geven om deze taken uit te voeren, raden we u aan het basislijnbeleid in de volgorde in deze tabel te implementeren. Het MFA-beleid voor gevoelige en sterk gereguleerde bescherming kan echter op elk moment worden geïmplementeerd.


|Beschermingsniveau|Beleid|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|        |[Clients blokkeren die geen ondersteuning bieden voor moderne verificatie](#block-clients-that-dont-support-modern-authentication)|Clients die geen gebruik maken van moderne verificatie kunnen regels voor voorwaardelijke toegang omzeilen, dus het is belangrijk om deze|
|        |[Gebruikers met een hoog risico moeten wachtwoord wijzigen](#high-risk-users-must-change-password)|Dwingt gebruikers om hun wachtwoord te wijzigen bij het aanmelden als activiteit met een hoog risico wordt gedetecteerd voor hun account|
|        |[App-beveiligingsbeleid definiëren](#define-app-protection-policies)|Eén beleid per platform (iOS, Android, Windows).|
|        |[Goedgekeurde apps vereisen](#require-approved-apps)|Dwingt mobiele app bescherming voor telefoons en tablets|
|        |[Apparaatnalevingsbeleid definiëren](#define-device-compliance-policies)|Eén beleid voor elk platform|
|        |[Compatibele pc's vereisen](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Dwingt Intune management van pc's af|
|**Gevoelige**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog* is](#require-mfa-based-on-sign-in-risk)| |
|         |[Compatibele pc's *en* mobiele apparaten vereisen](#require-compliant-pcs-and-mobile-devices)|Afdwingt Intune-beheer voor pc's en telefoon/tablets|
|**Sterk gereguleerd**|[*Altijd* mfa vereisen](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Beleid toewijzen aan gebruikers
Voordat u beleid configureert, identificeert u de Azure AD-groepen die u gebruikt voor elke beschermingslaag. Standaardbeveiliging is meestal van toepassing op iedereen in de organisatie. Een gebruiker die is opgenomen voor zowel basislijn- als gevoelige bescherming, heeft alle basislijnbeleidsregels toegepast plus het gevoelige beleid. Bescherming is cumulatief en het meest beperkende beleid wordt afgedwongen. 

Een aanbevolen praktijk is het maken van een Azure AD-groep voor uitsluiting van voorwaardelijke toegang. Voeg deze groep toe aan al uw regels voor voorwaardelijke toegang onder 'Uitsluiten'. Dit geeft u een methode om toegang te bieden aan een gebruiker terwijl u toegangsproblemen oplost. Dit wordt aanbevolen als een tijdelijke oplossing alleen. Controleer deze groep op wijzigingen en zorg ervoor dat de uitsluitingsgroep alleen wordt gebruikt zoals bedoeld. 

Het volgende diagram geeft een voorbeeld van gebruikerstoewijzing en uitsluitingen.

![Voorbeeldgebruikerstoewijzing en uitsluitingen voor MFA-regels](../media/identity-access-policies-assignment.png)

In de illustratie krijgt het 'Top secret project X-team' een beleid voor voorwaardelijke toegang toegewezen dat *ALTIJD*MFA vereist. Wees verstandig bij het toepassen van hogere niveaus van bescherming voor gebruikers. Leden van dit projectteam moeten elke keer dat ze zich aanmelden twee vormen van verificatie aanbieden, zelfs als ze niet hoog gereguleerde inhoud bekijken.  

Alle Azure AD-groepen die zijn gemaakt als onderdeel van deze aanbevelingen, moeten worden gemaakt als Office 365-groepen. Dit is specifiek belangrijk voor de implementatie van Azure Information Protection (AIP) bij het beveiligen van documenten in SharePoint Online.

![Schermopname voor het maken van Office 365-groepen](../media/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>MFA vereisen op basis van aanmeldingsrisico
Gebruik voordat u MFA vereist, eerst een MFA-registratiebeleid voor identiteitsbeveiliging om gebruikers te registreren voor MFA. Nadat gebruikers zijn geregistreerd, u MFA afdwingen voor aanmelding. Het [vereiste werk](identity-access-prerequisites.md) omvat het registreren van alle gebruikers met MFA.

Ga als nieuw beleid voor voorwaardelijke toegang maken: 

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies onder de sectie **Beveiliging** **voorwaardelijke toegang**.

4. Kies **Nieuw beleid**.

![Ca-beleid basislijn](../media/secure-email/CA-EXO-policy-1.png)

 In de volgende tabellen worden de instellingen voor beleid voor voorwaardelijke toegang beschreven die voor dit beleid moeten worden geïmplementeerd.

**Toewijzingen**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Opnemen|Gebruikers en groepen selecteren : specifieke beveiligingsgroep selecteren met gerichte gebruikers|Begin met een beveiligingsgroep inclusief proefgebruikers|
||Uitsluiten|Uitzonderingsbeveiligingsgroep; serviceaccounts (app-identiteiten)|Lidmaatschap gewijzigd op een zo nodig tijdelijke basis|
|Cloud-apps|Opnemen|Selecteer de apps waarop u deze regel wilt toepassen. Selecteer bijvoorbeeld Office 365 Exchange Online||
|Voorwaarden|Geconfigureerd|Ja|Specifiek configureren voor uw omgeving en behoeften|
|Aanmeldingsrisico|Risiconiveau||Zie de richtlijnen in de volgende tabel|

**Aanmeldingsrisico**

Pas de instellingen toe op basis van het beveiligingsniveau dat u target.

|Eigenschap|Beschermingsniveau|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Risiconiveau|Basislijn|Hoog, gemiddeld|Controleer beide|
| |Gevoelige|Hoog, gemiddeld, laag|Controleer alle drie|
| |Sterk gereguleerd| |Laat alle opties ongecontroleerd om MFA altijd af te dwingen|

**Toegangsbesturingselementen**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Verlenen|Toegang verlenen|Waar|Geselecteerde|
||MFA vereisen|Waar|Cheque|
||Apparaat moeten worden gemarkeerd als compatibel|Valse||
||Hybride Azure AD-aangesloten apparaat vereisen|Valse||
||Goedgekeurde client-app vereisen|Valse||
||Alle geselecteerde besturingselementen vereisen|Waar|Geselecteerde|

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt, door **op**te kiezen . Overweeg ook het gereedschap [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Clients blokkeren die geen ondersteuning bieden voor moderne verificatie
1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies onder de sectie **Beveiliging** **voorwaardelijke toegang**.

4. Kies **Nieuw beleid**.

In de volgende tabellen worden de instellingen voor beleid voor voorwaardelijke toegang beschreven die voor dit beleid moeten worden geïmplementeerd.

**Toewijzingen**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Gebruikers en groepen|Opnemen|Gebruikers en groepen selecteren : specifieke beveiligingsgroep selecteren met gerichte gebruikers|Begin met een beveiligingsgroep inclusief proefgebruikers|
||Uitsluiten|Uitzonderingsbeveiligingsgroep; serviceaccounts (app-identiteiten)|Lidmaatschap aangepast op een als nodig tijdelijke basis|
|Cloud-apps|Opnemen|Selecteer de apps waarop u deze regel wilt toepassen. Selecteer bijvoorbeeld Office 365 Exchange Online||
|Voorwaarden|Geconfigureerd|Ja|Client-apps configureren|
|Client-apps|Geconfigureerd|Ja|Mobiele apps en desktopclients, andere clients (selecteer beide)|

**Toegangsbesturingselementen**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Verlenen|Toegang blokkeren|Waar|Geselecteerde|
||MFA vereisen|Valse||
||Apparaat moeten worden gemarkeerd als compatibel|Valse||
||Hybride Azure AD-aangesloten apparaat vereisen|Valse||
||Goedgekeurde client-app vereisen|Valse||
||Alle geselecteerde besturingselementen vereisen|Waar|Geselecteerde|

> [!NOTE]
> Zorg ervoor dat u dit beleid inschakelt, door **op**te kiezen . Overweeg ook het gereedschap [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen.



## <a name="high-risk-users-must-change-password"></a>Gebruikers met een hoog risico moeten wachtwoord wijzigen
Om ervoor te zorgen dat alle gecompromitteerde accounts van gebruikers met een hoog risico worden gedwongen om een wachtwoordwijziging uit te voeren bij het aanmelden, moet u het volgende beleid toepassen.

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
> Zorg ervoor dat u dit beleid inschakelt, door **op**te kiezen . Overweeg ook het gereedschap [Wat als](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen

## <a name="define-app-protection-policies"></a>App-beveiligingsbeleid definiëren
App-beveiligingsbeleid bepaalt welke apps zijn toegestaan en welke acties ze kunnen uitvoeren met de gegevens van uw organisatie. Intune-app-beveiligingsbeleid maken vanuit de Azure-portal. 

Maak een beleid voor elk platform:
- Ios
- Android
- Windows 10

Als u een nieuw beleid voor app-beveiliging wilt maken, meldt u zich aan bij de Microsoft Azure-portal met uw beheerdersreferenties en navigeert u vervolgens naar**beleid voor het beveiliging van**apps voor **clientse** > apps . Kies **Beleid maken**kiezen .

Er zijn kleine verschillen in de opties voor app-beveiligingsbeleid tussen iOS en Android. Het onderstaande beleid is specifiek voor Android. Gebruik dit als leidraad voor uw andere beleid.

De aanbevolen lijst met apps bevat de volgende:
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

In de volgende tabellen worden de aanbevolen instellingen beschreven:

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Verplaatsing van gegevens|Android-back-ups voorkomen|Ja|Op iOS zal dit specifiek iTunes en iCloud roepen|
||Apps toestaan gegevens over te dragen op andere apps|Beheerde apps voor beleid||
||Apps toestaan gegevens te ontvangen van andere apps|Beheerde apps voor beleid||
||Voorkomen dat "Opslaan als"|Ja||
||Selecteren in welke opslagapparaten zakelijke gegevens kunnen worden opgeslagen|OneDrive voor Bedrijven, SharePoint||
||Knippen, kopiëren en plakken met andere apps beperken|Beheerde apps met beleid met plakken in||
||Webinhoud beperken om weer te geven in de beheerde browser|Nee||
||App-gegevens versleutelen|Ja|Selecteeroptie in iOS: Wanneer het apparaat is vergrendeld|
||App-versleuteling uitschakelen wanneer apparaat is ingeschakeld|Ja|Deze instelling uitschakelen om dubbele versleuteling te voorkomen|
||Synchronisatie van contactpersonen uitschakelen|Nee||
||Afdrukken uitschakelen|Nee||
|Access|Pincode vereisen voor toegang|Ja||
||Tekst selecteren|Numerieke||
||Eenvoudige pincode toestaan|Nee||
||Pinlengte|6||
||Vingerafdruk toestaan in plaats van pincode|Ja||
||Pincode van de app uitschakelen wanneer apparaatpincode wordt beheerd|Ja||
||Bedrijfsreferenties vereisen voor toegang|Nee||
||Controleer de toegangsvereiste na (minuten) opnieuw|30||
||Schermopname blokkeren en Android-assistent|Nee|Op iOS is dit geen optie beschikbaar|
|Beveiligingsvereisten voor aanmelding|Max PIN-pogingen|5|Pin opnieuw instellen|
||Offline respijtperiode|720|Toegang blokkeren|
||Offline-interval (dagen) voordat app-gegevens worden gewist|90|Gegevens wissen|
||Jailbroken/gewortelde apparaten| |Gegevens wissen|

Als u klaar bent, moet u 'Maken' selecteren. Herhaal de bovenstaande stappen en vervang het geselecteerde platform (vervolgkeuzelijst) door iOS. Hiermee worden twee app-beleidsregels gemaakt, dus zodra u het beleid maakt, wijst u vervolgens groepen toe aan het beleid en implementeert u het.

Zie [Beleid voor app-beveiliging maken en toewijzen](https://docs.microsoft.com/intune/app-protection-policies)als u het beleid wilt bewerken en dit beleid aan gebruikers wilt toewijzen. 

## <a name="require-approved-apps"></a>Goedgekeurde apps vereisen
Goedgekeurde apps vereisen:

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies onder de sectie **Beveiliging** **voorwaardelijke toegang**.

4. Kies **Nieuw beleid**.

5. Voer een beleidsnaam in en kies vervolgens de **gebruikers en groepen** waarvoor u het beleid wilt toepassen.

6. Kies **Cloud-apps**.

7. Kies **Apps selecteren**en selecteer de gewenste apps in de lijst **Cloud-apps.** Selecteer bijvoorbeeld Office 365 Exchange Online. Kies **Selecteren** en **klaar**.

8. Kies **Voorwaarden**, selecteer **Apparaatplatforms**en kies **Configureren**

9. Kies onder **Opnemen**de optie **Apparaatplatforms selecteren**, selecteer **Android** en **iOS**. Klik opnieuw op **Gereed** en **klaar**

10. Kies **Grant** in de sectie **Toegangsbesturingselementen.**

11. Kies **Grant-toegang**, selecteer **Goedgekeurde client-app vereisen**. Selecteer voor meerdere besturingselementen **de geselecteerde besturingselementen vereisen**en kies **Selecteren**. 

12. Kies **Create**.

## <a name="define-device-compliance-policies"></a>Beleid voor apparaatnaleving definiëren

Beleid voor apparaatnaleving definieert de vereisten waaraan apparaten moeten voldoen om als compatibel te zijn gemarkeerd. Maak intune-beleid voor het voldoen aan apparaten vanuit de Azure-portal. 

Maak een beleid voor elk platform:
- Android
- Android-onderneming
- Ios
- Macos
- Windows Phone 8.1
- Windows 8.1 en hoger
- Windows 10 en hoger

Als u beleid voor apparaatnaleving wilt maken, meldt u zich met uw beheerdersreferenties aan bij de Microsoft Azure-portal en navigeert u vervolgens naar **Intune > naleving van apparaatapparaten**. Selecteer **Beleid maken**.

De volgende instellingen worden aanbevolen voor Windows 10.

**Apparaatstatus: windows health attestation service-evaluatieregels**

|Eigenschappen|Waarden|Opmerkingen|
|:---------|:-----|:----|
|BitLocker vereisen|Vereisen||
|Secure Boot moeten worden ingeschakeld op het apparaat|Vereisen||
|Code-integriteit vereisen|Vereisen||


**Apparaateigenschappen**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Versie van het besturingssysteem|Alle|Niet geconfigureerd||

Om alle bovenstaande beleidsregels als geïmplementeerd te laten gelden, moeten ze gericht zijn op gebruikersgroepen. U dit doen door het beleid (op Opslaan) of hoger te maken door **Implementatie beheren** in de sectie **Beleid** (hetzelfde niveau als Toevoegen) te selecteren.

**Systeembeveiliging**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Wachtwoord|Een wachtwoord vereisen om mobiele apparaten te ontgrendelen|Vereisen||
||Eenvoudige wachtwoorden|Blok||
||Wachtwoordtype|Standaardapparaat||
||Minimale wachtwoordlengte|6||
||Maximale minuten inactiviteit voordat wachtwoord vereist is|15|Deze instelling wordt ondersteund voor Android-versies 4.0 en hoger of KNOX 4.0 en hoger. Voor iOS-apparaten wordt het ondersteund voor iOS 8.0 en hoger|
||Wachtwoord verlopen (dagen)|41||
||Aantal eerdere wachtwoorden om hergebruik te voorkomen|5||
||Wachtwoord vereisen wanneer apparaat terugkeert vanuit de status van niet-actieve toestand (mobiel en holografisch)|Vereisen|Beschikbaar voor Windows 10 en hoger|
|Codering|Versleuteling van gegevensopslag op apparaat|Vereisen||
|Apparaatbeveiliging|Firewall|Vereisen||
||Antivirus|Vereisen||
||Antispyware|Vereisen|Deze instelling vereist een antispywareoplossing die is geregistreerd bij Windows Security Center|
|Verdediger|Windows Defender-antimalware|Vereisen||
||Windows Defender Antimalware minimumversie||Alleen ondersteund voor Windows 10-bureaublad. Microsoft raadt versies niet meer dan vijf achter van de meest recente versie|
||Windows Defender Antimalware-handtekening up-to-date|Vereisen||
||Real-time bescherming|Vereisen|Alleen ondersteund voor Windows 10-bureaublad|

**Microsoft Defender ATP**

|Type|Eigenschappen|Waarden|Opmerkingen|
|:---|:---------|:-----|:----|
|Microsoft Defender Advanced Threat Protection regels|Het apparaat op of onder de machinerisicoscore moeten bevinden|Medium||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Vereisen compatibele pc's (maar niet compliant telefoons en tablets)
Voordat u een beleid toevoegt om compatibele pc's te vereisen, moet u apparaten inschrijven voor beheer in Intune. Het gebruik van multi-factor authenticatie wordt aanbevolen voordat u apparaten inschrijft bij Intune om te garanderen dat het apparaat in het bezit is van de beoogde gebruiker. 

Ga als nog steeds om compatibele pc's:

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies onder de sectie **Beveiliging** **voorwaardelijke toegang**.

4. Kies **Nieuw beleid**.

5. Voer een beleidsnaam in en kies vervolgens de **gebruikers en groepen** waarvoor u het beleid wilt toepassen.

6. Kies **Cloud-apps**.

7. Kies **Apps selecteren**en selecteer de gewenste apps in de lijst **Cloud-apps.** Selecteer bijvoorbeeld Office 365 Exchange Online. Kies **Selecteren** en **klaar**.

8. Als u compatibele pc's wilt vereisen, maar niet compatibele telefoons en tablets, kiest u **Voorwaarden** en **apparaatplatforms.** Kies **Apparaatplatforms selecteren** en selecteer **Windows** en **macOS**.

9. Kies **Grant** in de sectie **Toegangsbesturingselementen.**

10. Kies **Grant-toegang**, selecteer **Apparaat als gemarkeerd als compatibel .** Selecteer **alle geselecteerde besturingselementen vereisen**voor meerdere besturingselementen en kies **Selecteren**. 

11. Kies **Create**.

Als het uw doel is om compatibele pc's *en* mobiele apparaten te vereisen, selecteert u geen platforms. Dit dwingt naleving voor alle apparaten af. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Compatibele pc's *en* mobiele apparaten vereisen

Naleving voor alle apparaten vereisen:

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies onder de sectie **Beveiliging** **voorwaardelijke toegang**.

4. Kies **Nieuw beleid**.

5. Voer een beleidsnaam in en kies vervolgens de **gebruikers en groepen** waarvoor u het beleid wilt toepassen.

6. Kies **Cloud-apps**.

7. Kies **Apps selecteren**en selecteer de gewenste apps in de lijst **Cloud-apps.** Selecteer bijvoorbeeld Office 365 Exchange Online. Kies **Selecteren** en **klaar**.

8. Kies **Grant** in de sectie **Toegangsbesturingselementen.**

9. Kies **Grant-toegang**, selecteer **Apparaat als gemarkeerd als compatibel .** Selecteer **alle geselecteerde besturingselementen vereisen**voor meerdere besturingselementen en kies **Selecteren**. 

10. Kies **Create**.

Selecteer bij het maken van dit beleid geen platforms. Dit dwingt compatibele apparaten af.


## <a name="next-steps"></a>Volgende stappen

[Meer informatie over beleidsaanbevelingen voor het beveiligen van e-mail](secure-email-recommended-policies.md)
