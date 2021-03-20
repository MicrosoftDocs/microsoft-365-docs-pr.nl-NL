---
title: Veelvoorkomende beleidsregels voor identiteits- en apparaattoegang - Microsoft 365 voor | Microsoft Docs
description: Beschrijft de aanbevolen algemene beleidsregels en configuraties voor identiteits- en apparaattoegang.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: ed49405aa2933c029f7e62d274119550adc379e8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910656"
---
# <a name="common-identity-and-device-access-policies"></a>Algemeen beleid voor identiteiten en apparaattoegang

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- Azure

In dit artikel worden de algemene aanbevolen beleidsregels beschreven voor het beveiligen van toegang tot Microsoft 365-cloudservices, inclusief on-premises toepassingen die zijn gepubliceerd met Azure Active Directory (Azure AD) Application Proxy.

In deze richtlijn wordt besproken hoe u het aanbevolen beleid implementeert in een nieuwe omgeving. Als u dit beleid in een afzonderlijke labomgeving instelt, kunt u de aanbevolen beleidsregels begrijpen en evalueren voordat u de implementatie naar uw preproductie- en productieomgevingen organiseert. Uw nieuwe inrichtingsomgeving kan alleen in de cloud of hybride zijn om aan uw evaluatiebehoeften te voldoen.

## <a name="policy-set"></a>Beleidsset

In het volgende diagram ziet u de aanbevolen set beleidsregels. Hier ziet u op welke beveiligingslaag elk beleid van toepassing is en of het beleid van toepassing is op pc's of telefoons en tablets, of beide categorieën apparaten. Het geeft ook aan waar u dit beleid configureert.

[![Algemeen beleid voor het configureren van identiteits- en apparaattoegang](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Hier volgt een PDF-overzicht van één pagina met koppelingen naar het afzonderlijke beleid:

[![Duimafbeelding voor identiteits- en apparaatbeveiliging voor Microsoft 365-hand-out](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Weergeven als pdf-bestand](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Downloaden als PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

In de rest van dit artikel wordt beschreven hoe u dit beleid configureert.

> [!NOTE]
> Het is raadzaam om het gebruik van meervoudige verificatie (MFA) te vereisen voordat u apparaten in Intune inschrijft om ervoor te zorgen dat het apparaat in het bezit is van de beoogde gebruiker. U moet apparaten registreren in Intune voordat u het nalevingsbeleid voor apparaten kunt afdwingen.

Om u de tijd te geven om deze taken uit te voeren, raden we u aan het basislijnbeleid in de volgorde in deze tabel te implementeren. Het MFA-beleid voor gevoelige en sterk gereguleerde beveiligingsniveaus kan echter op elk moment worden geïmplementeerd.

|Beveiligingsniveau|Beleid|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico gemiddeld *of* *hoog* is](#require-mfa-based-on-sign-in-risk)||
||[Clients blokkeren die moderne verificatie niet ondersteunen](#block-clients-that-dont-support-multi-factor)|Clients die geen moderne verificatie gebruiken, kunnen beleidsregels voor voorwaardelijke toegang omzeilen, dus het is belangrijk om deze te blokkeren.|
||[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](#high-risk-users-must-change-password)|Dwingt gebruikers hun wachtwoord te wijzigen wanneer ze zich aanmelden als er activiteit met een hoog risico wordt gedetecteerd voor hun account.|
||[Beleid voor gegevensbescherming van apps toepassen](#apply-app-data-protection-policies)|Eén Intune App Protection-beleid per platform (Windows, iOS/iPadOS, Android).|
||[Goedgekeurde apps en app-beveiliging vereisen](#require-approved-apps-and-app-protection)|Dwingt mobiele app-beveiliging af voor telefoons en tablets met iOS, iPadOS of Android.|
||[Beleidsregels voor apparaat compliance definiëren](#define-device-compliance-policies)|Eén beleid voor elk platform.|
||[Eis conforme pc’s](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Intune-beheer van pc's met Windows of MacOS wordt afgedwongen.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog is*](#require-mfa-based-on-sign-in-risk)||
||[Compatibele pc's *en mobiele* apparaten vereisen](#require-compliant-pcs-and-mobile-devices)|Intune-beheer wordt afgedwongen voor zowel pc's (Windows of MacOS) als telefoons of tablets (iOS, iPadOS of Android).|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Beleid toewijzen aan groepen en gebruikers

Voordat u beleid configureert, identificeert u de Azure AD-groepen die u gebruikt voor elke beveiligingslaag. Normaal gesproken geldt basislijnbeveiliging voor iedereen in de organisatie. Een gebruiker die is opgenomen voor zowel basislijn als gevoelige beveiliging, heeft alle basislijnbeleidsregels plus het gevoelige beleid toegepast. Beveiliging is cumulatief en het meest beperkende beleid wordt afgedwongen.

Een aanbevolen oefening is het maken van een Azure AD-groep voor uitsluiting van voorwaardelijke toegang. Voeg deze groep toe aan al uw beleidsregels voor Voorwaardelijke toegang in de instelling **Uitsluit** van de instelling **Gebruikers** en groepen in **de sectie** Toewijzingen. Dit geeft u een methode om toegang te bieden tot een gebruiker terwijl u toegangsproblemen oplost. Dit wordt alleen aanbevolen als tijdelijke oplossing. Controleer deze groep op wijzigingen en zorg ervoor dat de uitsluitingsgroep alleen wordt gebruikt zoals bedoeld.

Hier volgen een voorbeeld van groepstoewijzingen en uitsluitingen voor het vereisen van MFA.

![Voorbeeld van groepstoewijzingen en uitsluitingen voor MFA-beleid](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Hier zijn de resultaten:

- Alle gebruikers moeten MFA gebruiken wanneer het aanmeldingsrisico gemiddeld of hoog is.

- Leden van de groep Leidinggevend personeel moeten MFA gebruiken wanneer het aanmeldingsrisico laag, gemiddeld of hoog is.

  In dit geval komen leden van de groep Leidinggevend personeel overeen met zowel het basislijnbeleid als het gevoelige beleid Voorwaardelijke toegang. De toegangsbesturingselementen voor beide beleidsregels worden gecombineerd, wat in dit geval overeenkomt met het gevoelige beleid Voorwaardelijke toegang.

- Leden van de groep Top Secret Project X zijn altijd verplicht om MFA te gebruiken

  In dit geval komen leden van de groep Top Secret Project X overeen met zowel het basislijnbeleid als het sterk gereguleerde beleid voor voorwaardelijke toegang. De toegangsbesturingselementen voor beide beleidsregels worden gecombineerd. Omdat het toegangsbeheer voor het sterk gereguleerde beleid voor voorwaardelijke toegang restrictiever is, wordt het gebruikt.

Wees voorzichtig bij het toepassen van hogere beveiligingsniveaus op groepen en gebruikers. Leden van de groep Top Secret Project X moeten bijvoorbeeld telkens MFA gebruiken wanneer ze zich aanmelden, zelfs als ze niet werken aan de sterk gereguleerde inhoud voor Project X.

Alle Azure AD-groepen die als onderdeel van deze aanbevelingen zijn gemaakt, moeten worden gemaakt als Microsoft 365-groepen. Dit is belangrijk voor de implementatie van gevoeligheidslabels bij het beveiligen van documenten in Microsoft Teams en SharePoint.

![Schermafbeelding voor het maken van Microsoft 365-groepen](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>MFA vereisen op basis van aanmeldingsrisico

U moet uw gebruikers laten registreren voor MFA voordat ze het moeten gebruiken. Als u Microsoft 365 E5, Microsoft 365 E3 met de invoegvoeging Identity & Threat Protection, Office 365 met EMS E5 of afzonderlijke Azure AD Premium P2-licenties hebt, kunt u het MFA-registratiebeleid met Azure AD Identity Protection gebruiken om te vereisen dat gebruikers zich registreren voor MFA. Het [vereiste werk omvat](identity-access-prerequisites.md) het registreren van alle gebruikers met MFA.

Nadat uw gebruikers zijn geregistreerd, kunt u MFA vereisen voor aanmelding met een nieuw beleid voor voorwaardelijke toegang.

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies Azure Active Directory in de lijst met **Azure-services.**
3. Kies in **de** lijst Beheren **de** optie Beveiliging en kies vervolgens **Voorwaardelijke toegang.**
4. Kies **Nieuw beleid** en typ de naam van het nieuwe beleid.

In de volgende tabellen worden de beleidsinstellingen voor Voorwaardelijke toegang beschreven die MFA vereisen op basis van aanmeldingsrisico.

In de **sectie Opdrachten:**

|Instelling|Eigenschappen|Waarden|Opmerkingen|
|---|---|---|---|
|Gebruikers en groepen|Opnemen|**Selecteer gebruikers en groepen > Gebruikers en groepen:** Selecteer specifieke groepen met gerichte gebruikersaccounts.|Begin met de groep met testgebruikersaccounts.|
||Uitsluiten|**Gebruikers en groepen:** selecteer de uitzonderingsgroep Voorwaardelijke toegang; serviceaccounts (app-identiteiten).|Lidmaatschap moet worden gewijzigd op een zo nodig, tijdelijke basis.|
|Cloud-apps of -acties|**Cloud-apps > Include**|**Apps selecteren:** selecteer de apps op wie u dit beleid wilt toepassen. Selecteer bijvoorbeeld Exchange Online.||
|Voorwaarden|||Configureer voorwaarden die specifiek zijn voor uw omgeving en behoeften.|
||Aanmeldingsrisico||Zie de richtlijnen in de volgende tabel.|
|

### <a name="sign-in-risk-condition-settings"></a>Instellingen voor aanmeldingsrisico

Pas de instellingen voor risiconiveau toe op basis van het beveiligingsniveau dat u wilt instellen.

|Niveau van beveiliging|Waarden op risiconiveau die nodig zijn|Actie|
|---|---|---|
|Basislijn|Hoog, gemiddeld|Controleer beide.|
|Gevoelig|Hoog, gemiddeld, laag|Controleer alle drie.|
|Sterk gereglementeerd||Laat alle opties uitgeschakeld om MFA altijd af te dwingen.|
|

In de **sectie Besturingselementen van Access:**

|Instelling|Eigenschappen|Waarden|Actie|
|---|---|---|---|
|Grant|**Grant access**||Selecteer|
|||**Meervoudige verificatie vereisen**|Cheque|
||**Alle geselecteerde besturingselementen vereisen**||Selecteer|
|

Kies **Selecteren om** de instellingen voor verlenen op **te** slaan.

Selecteer ten slotte **Aan** voor **beleid inschakelen** en kies vervolgens **Maken.**

U kunt ook het hulpprogramma [Wat als gebruiken](/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen.

## <a name="block-clients-that-dont-support-multi-factor"></a>Clients blokkeren die geen ondersteuning bieden voor meerdere factoren

Gebruik de instellingen in deze tabellen voor een beleid voor Voorwaardelijke toegang om clients te blokkeren die geen ondersteuning bieden voor meervoudige verificatie.

Zie [dit artikel voor](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) een lijst met clients in Microsoft 365 die meervoudige verificatie ondersteunen.

In de **sectie Opdrachten:**

|Instelling|Eigenschappen|Waarden|Opmerkingen|
|---|---|---|---|
|Gebruikers en groepen|Opnemen|**Selecteer gebruikers en groepen > Gebruikers en groepen:** Selecteer specifieke groepen met gerichte gebruikersaccounts.|Begin met de groep met testgebruikersaccounts.|
||Uitsluiten|**Gebruikers en groepen:** selecteer de uitzonderingsgroep Voorwaardelijke toegang; serviceaccounts (app-identiteiten).|Lidmaatschap moet worden gewijzigd op een zo nodig, tijdelijke basis.|
|Cloud-apps of -acties|**Cloud-apps > Include**|**Selecteer apps:** Selecteer de apps die overeenkomen met de clients die geen ondersteuning bieden voor moderne verificatie.||
|Voorwaarden|**Client-apps**|Kies **Ja** voor **configureren** <p> De vinkjes voor **browser-** en **mobiele apps en desktopcl** clients verwijderen||
|

In de **sectie Besturingselementen van Access:**

|Instelling|Eigenschappen|Waarden|Actie|
|---|---|---|---|
|Grant|**Toegang blokkeren**||Selecteer|
||**Alle geselecteerde besturingselementen vereisen**||Selecteer|
|

Kies **Selecteren om** de instellingen voor verlenen op **te** slaan.

Selecteer ten slotte **Aan** voor **beleid inschakelen** en kies vervolgens **Maken.**

U kunt het hulpprogramma [Wat als gebruiken](/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen.

Voor Exchange Online kunt u verificatiebeleid gebruiken om basisverificatie uit te [schakelen,](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)waardoor alle aanvragen voor clienttoegang moderne verificatie moeten gebruiken.

## <a name="high-risk-users-must-change-password"></a>Gebruikers met een hoog risico moeten het wachtwoord wijzigen

Als u ervoor wilt zorgen dat de gecompromitteerde accounts van alle gebruikers met een hoog risico worden gedwongen een wachtwoordwijziging uit te voeren wanneer u zich aanmeldt, moet u het volgende beleid toepassen.

Meld u aan bij de [Microsoft Azure-portal https://portal.azure.com) (](https://portal.azure.com/) met uw beheerdersreferenties en ga naar Azure AD **Identity Protection > Gebruikersrisicobeleid**.

In de **sectie Opdrachten:**

|Type|Eigenschappen|Waarden|Actie|
|---|---|---|---|
|Gebruikers|Opnemen|**Alle gebruikers**|Selecteer|
|Gebruikersrisico|**Hoog**||Selecteer|
|

In de tweede **sectie Opdrachten:**

|Type|Eigenschappen|Waarden|Actie|
|---|---|---|---|
|Toegang|**Toegang toestaan**||Selecteer|
|||**Wachtwoordwijziging vereisen**|Cheque|
|

Kies **Klaar om** de **Access-instellingen op te** slaan.

Selecteer ten slotte **Aan** voor **afdwingen beleid** en kies vervolgens **Opslaan.**

U kunt het hulpprogramma [Wat als gebruiken](/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen.

Gebruik dit beleid in combinatie met [Azure AD-wachtwoordbeveiliging](/azure/active-directory/authentication/concept-password-ban-bad)configureren, waarmee bekende zwakke wachtwoorden en hun varianten en aanvullende zwakke termen worden gedetecteerd en blokkeert die specifiek zijn voor uw organisatie. Als u Azure AD-wachtwoordbeveiliging gebruikt, zorgt u ervoor dat gewijzigde wachtwoorden sterke wachtwoorden zijn.

## <a name="apply-app-data-protection-policies"></a>APP-beleid voor gegevensbescherming toepassen

App-beveiligingsbeleid (APP) bepaalt welke apps zijn toegestaan en welke acties ze kunnen uitvoeren met de gegevens van uw organisatie. Met de beschikbare opties in APP kunnen organisaties de beveiliging aanpassen aan hun specifieke behoeften. Voor sommige is het mogelijk niet duidelijk welke beleidsinstellingen nodig zijn om een volledig scenario te implementeren. Om organisaties te helpen prioriteit te geven aan het uitharden van mobiele client-eindpunten, heeft Microsoft taxonomie geïntroduceerd voor het APP-gegevensbeveiligingskader voor het beheer van mobiele apps voor iOS en Android.

Het FRAMEWORK VOOR APP-gegevensbescherming is ingedeeld in drie verschillende configuratieniveaus, met elk niveau dat van het vorige niveau is afgebouwd:

- **Enterprise Basic Data Protection** (niveau 1) zorgt ervoor dat apps worden beveiligd met een pincode en versleuteld zijn en selectieve veegbewerkingen uitvoeren. Voor Android-apparaten valideert dit niveau de bevestiging van Android-apparaten. Dit is een configuratie op invoerniveau die vergelijkbare gegevensbescherming biedt in het postvakbeleid van Exchange Online en waarmee IT en de gebruikerspopulatie worden gebruikt voor APP.
- **Enterprise enhanced data protection** (Level 2) introduces APP data leakage prevention mechanisms and minimum OS requirements. Dit is de configuratie die van toepassing is op de meeste mobiele gebruikers die toegang hebben tot werk- of schoolgegevens.
- **Enterprise High Data Protection** (niveau 3) introduceert geavanceerde mechanismen voor gegevensbeveiliging, verbeterde pincodeconfiguratie en APP Mobile Threat Defense. Deze configuratie is wenselijk voor gebruikers die toegang hebben tot gegevens met een hoog risico.

Als u de specifieke aanbevelingen wilt zien voor elk configuratieniveau en de minimale apps die moeten worden beveiligd, bekijkt u Het kader voor gegevensbescherming met behulp van beleid voor [app-beveiliging.](/mem/intune/apps/app-protection-framework)

Met behulp van de principes die worden beschreven in configuraties voor [identiteits-](microsoft-365-policies-configurations.md)en apparaattoegang, worden de beveiligingslagen Basislijn en Gevoelige beveiliging nauw verbonden met de verbeterde instellingen voor gegevensbescherming op niveau 2. De hooggeguleerde beveiligingslaag wordt nauw verbonden met de instellingen voor hoge gegevensbescherming van het bedrijf niveau 3.

|Beveiligingsniveau|App-beveiligingsbeleid|Meer informatie|
|---|---|---|
|Basislijn|[Verbeterde gegevensbescherming op niveau 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|De beleidsinstellingen die in niveau 2 zijn afgedwongen, bevatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en worden alleen toegevoegd aan of bijgewerkt aan de onderstaande beleidsinstellingen om meer besturingselementen en een geavanceerdere configuratie dan niveau 1 te implementeren.|
|Gevoelig|[Verbeterde gegevensbescherming op niveau 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|De beleidsinstellingen die in niveau 2 zijn afgedwongen, bevatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en worden alleen toegevoegd aan of bijgewerkt aan de onderstaande beleidsinstellingen om meer besturingselementen en een geavanceerdere configuratie dan niveau 1 te implementeren.|
|Sterk gereguleerd|[Niveau 3 enterprise high data protection](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|De beleidsinstellingen die in niveau 3 zijn afgedwongen, bevatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en 2 en worden alleen toegevoegd aan of bijgewerkt aan de onderstaande beleidsinstellingen om meer besturingselementen en een geavanceerdere configuratie dan niveau 2 te implementeren.|
|

Als u een nieuw beleid voor app-beveiliging wilt maken voor elk platform (iOS en Android) in Microsoft Endpoint Manager met behulp van de instellingen voor het gegevensbeveiligingskader, kunt u het volgende doen:

1. Maak het beleid handmatig door de stappen te volgen in Het maken en implementeren van app-beveiligingsbeleid [met Microsoft Intune.](/mem/intune/apps/app-protection-policies)
2. Importeer de [voorbeeld-Intune App Protection Policy Configuration Framework JSON-sjablonen](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) [met PowerShell-scripts van Intune.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Goedgekeurde apps en APP-beveiliging vereisen

Als u het APP-beveiligingsbeleid wilt afdwingen dat u hebt toegepast in Intune, moet u een beleid voor voorwaardelijke toegang maken om goedgekeurde client-apps en de voorwaarden te vereisen die zijn ingesteld in het APP-beveiligingsbeleid.

Voor het afdwingen van app-beveiligingsbeleid is een set beleidsregels vereist die worden beschreven in App-beveiligingsbeleid vereisen voor toegang tot [cloud-apps met voorwaardelijke toegang.](/azure/active-directory/conditional-access/app-protection-based-conditional-access) Dit beleid wordt elk opgenomen in deze aanbevolen set identiteits- en toegangsconfiguratiebeleid.

Als u het beleid voor voorwaardelijke toegang wilt maken waarvoor goedgekeurde apps en APP-beveiliging vereist zijn, volgt u 'Stap 1: Configure an Azure AD Conditional Access policy for Microsoft 365' in [Scenario 1: Microsoft 365 apps](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)require approved apps with app protection policies , which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > Dit beleid zorgt ervoor dat mobiele gebruikers toegang hebben tot alle Office-eindpunten met de toepasselijke apps.

Als u mobiele toegang tot Exchange Online inschakelen, implementeert u [Block ActiveSync-clients,](secure-email-recommended-policies.md#block-activesync-clients)waardoor Exchange ActiveSync-clients die gebruikmaken van basisverificatie, geen verbinding kunnen maken met Exchange Online. Dit beleid wordt niet in de afbeelding boven aan dit artikel beschreven. Het wordt beschreven en afgebeeld in [beleidsaanbevelingen voor het beveiligen van e-mail.](secure-email-recommended-policies.md)

Als u het beleid Voorwaardelijke toegang wilt maken waarvoor Edge voor iOS en Android vereist is, volgt u 'Stap 2: Een Azure AD Conditional Access-beleid configureren voor Microsoft 365' in [scenario 2: Browser-apps](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)vereisen goedgekeurde apps met app-beveiligingsbeleid, waarmee Edge voor iOS en Android kan worden ondersteund, maar andere webbrowsers op mobiele apparaten geen verbinding kunnen maken met Microsoft 365-eindpunten.

 Deze beleidsregels maken gebruik van de [grant-besturingselementen Vereist goedgekeurde client-app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) en [Beleid voor app-beveiliging vereisen.](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Ten slotte zorgt het blokkeren van oudere verificatie voor andere client-apps op iOS- en Android-apparaten ervoor dat deze clients beleidsregels voor voorwaardelijke toegang niet kunnen omzeilen. Als u de richtlijnen in dit artikel volgt, hebt u Al [Block-clients](#block-clients-that-dont-support-multi-factor)geconfigureerd die geen ondersteuning bieden voor moderne verificatie.

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Beleidsregels voor apparaat compliance definiëren

Apparaatconforme beleidsregels definiëren de vereisten waar apparaten aan moeten voldoen om te worden bepaald als compatibel. U maakt Intune-beleid voor apparaat compliance vanuit het Microsoft Endpoint Manager-beheercentrum.

U moet een beleid maken voor elk pc-, telefoon- of tabletplatform:

- Android-apparaatbeheerder
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 en hoger
- Windows 10 en hoger

Als u beleid voor apparaat compliance wilt maken, meld u zich aan bij het [Microsoft Endpoint Manager-beheercentrum](https://endpoint.microsoft.com) met uw beheerdersreferenties en gaat u vervolgens naar **Beleidsregels** voor apparaten \>  \> **compliancebeleid.** Selecteer **Beleid maken.**

Als u beleidsregels voor apparaat compliance wilt geïmplementeerd, moeten ze worden toegewezen aan gebruikersgroepen. U wijst een beleid toe nadat u het hebt maken en opslaan. Selecteer in het beheercentrum het beleid en selecteer **vervolgens Toewijzingen.** Nadat u de groepen hebt geselecteerd die u het beleid wilt ontvangen, **selecteert** u Opslaan om die groepstoewijzing op te slaan en het beleid te implementeren.

Zie Een compliancebeleid [maken in Microsoft Intune](/mem/intune/protect/create-compliance-policy) in de Documentatie van Intune voor stapsgewijse richtlijnen voor het maken van compliancebeleid in Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Aanbevolen instellingen voor Windows 10 en hoger

De volgende instellingen worden aanbevolen voor pc's met Windows 10 en hoger, zoals geconfigureerd in stap **2: Nalevingsinstellingen**, van het proces voor het maken van beleid.

Zie deze tabel voor > evaluatieregels van **de Windows Health Attestation Service** voor apparaattoestand.

|Eigenschappen|Value|Actie|
|---|---|---|
|BitLocker vereisen|Vereisen|Selecteer|
|Secure Boot vereisen om te worden ingeschakeld op het apparaat|Vereisen|Selecteer|
|Codeintegriteit vereisen|Vereisen|Selecteer|
|

Geef **voor Apparaateigenschappen** de juiste waarden op voor besturingssysteemversies op basis van uw IT- en beveiligingsbeleid.

Selecteer Vereisen voor compliance door **Configuration Manager.**

Zie **deze tabel voor** systeembeveiliging.

|Type|Eigenschappen|Value|Actie|
|---|---|---|---|
|Wachtwoord|Een wachtwoord vereisen om mobiele apparaten te ontgrendelen|Vereisen|Selecteer|
||Eenvoudige wachtwoorden|Blokkeren|Selecteer|
||Wachtwoordtype|Apparaat standaard|Selecteer|
||Minimale wachtwoordlengte|6|Type|
||Maximumminuten van inactiviteit voordat wachtwoord is vereist|15|Type <p> Deze instelling wordt ondersteund voor Android-versies 4.0 en hoger of KNOX 4.0 en hoger. Voor iOS-apparaten wordt deze ondersteund voor iOS 8.0 en hoger.|
||Wachtwoordverloop (dagen)|41|Type|
||Aantal eerdere wachtwoorden om hergebruik te voorkomen|5|Type|
||Wachtwoord vereisen wanneer het apparaat terugkomt uit de niet-actieve status (mobiel en holografische toestand)|Vereisen|Beschikbaar voor Windows 10 en hoger|
|Versleuteling|Versleuteling van gegevensopslag op apparaat|Vereisen|Selecteer|
|Apparaatbeveiliging|Firewall|Vereisen|Selecteer|
||Antivirus|Vereisen|Selecteer|
||Antispyware|Vereisen|Selecteer <p> Voor deze instelling is een anti-spywareoplossing vereist die is geregistreerd bij het Windows-beveiligingscentrum.|
|Defender|Microsoft Defender Antimalware|Vereisen|Selecteer|
||Microsoft Defender Antimalware minimumversie||Type <p> Alleen ondersteund voor windows 10-bureaublad. Microsoft raadt versies aan die niet meer dan vijf van de meest recente versie achterblijven.|
||Microsoft Defender Antimalware-handtekening up-to-date|Vereisen|Selecteer|
||Realtime beveiliging|Vereisen|Selecteer <p> Alleen ondersteund voor Windows 10-bureaublad|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

|Type|Eigenschappen|Value|Actie|
|---|---|---|---|
|Microsoft Defender voor eindpuntregels|Vereisen dat het apparaat zich op of onder de machinerisicoscore|Gemiddeld|Selecteer|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Compatibele pc's vereisen (maar niet compatibele telefoons en tablets)

Voordat u een beleid toevoegt waarvoor compatibele pc's moeten worden vereist, moet u apparaten voor beheer registreren bij Intune. Het is raadzaam meervoudige verificatie te gebruiken voordat u apparaten inschrijft bij Intune om te garanderen dat het apparaat in het bezit is van de beoogde gebruiker.

Compatibele pc's vereisen:

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies Azure Active Directory in de lijst met **Azure-services.**
3. Kies in **de** lijst Beheren **de** optie Beveiliging en kies vervolgens **Voorwaardelijke toegang.**
4. Kies **Nieuw beleid** en typ de naam van het nieuwe beleid.

5. Kies **onder Opdrachten** de optie Gebruikers en **groepen** en vermeld op wie u het beleid wilt toepassen. Sluit ook de uitsluitingsgroep Voorwaardelijke toegang uit.

6. Kies **onder Opdrachten** de optie **Cloud-apps of -acties.**

7. Kies **voor** Opnemen de **optie Apps > Selecteren** en selecteer vervolgens de gewenste apps in de lijst met **cloud-apps.** Selecteer bijvoorbeeld Exchange Online. Kies **Selecteren** wanneer u klaar bent.

8. Als u compatibele pc's (maar niet compatibele telefoons en tablets) wilt vereisen, kiest u onder Opdrachten de optie **Voorwaarden > Apparaatplatforms.** Selecteer **Ja** voor **configureren.** Kies **Apparaatplatforms selecteren,** selecteer **Windows** en **macOS** en kies vervolgens **Klaar.**

9. Kies **onder Access-besturingselementen** de optie **Grant** .

10. Kies **Toegang verlenen en** controleer vervolgens Apparaat vereisen dat moet worden gemarkeerd als **compatibel**. Selecteer Alle geselecteerde besturingselementen vereisen voor meerdere **besturingselementen.** Als u klaar is, kiest u **Selecteren.**

11. Selecteer **Aan** voor **beleid inschakelen** en kies vervolgens **Maken.**

> [!NOTE]
> Zorg ervoor dat uw apparaat voldoet voordat u dit beleid inschakelen. Anders kunt u niet meer worden vergrendeld en kunt u dit beleid pas wijzigen als uw gebruikersaccount is toegevoegd aan de uitsluitingsgroep Voorwaardelijke toegang.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Compatibele pc's *en mobiele* apparaten vereisen

Naleving vereisen voor alle apparaten:

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies Azure Active Directory in de lijst met **Azure-services.**
3. Kies in **de** lijst Beheren **de** optie Beveiliging en kies vervolgens **Voorwaardelijke toegang.**
4. Kies **Nieuw beleid** en typ de naam van het nieuwe beleid.

5. Kies **onder Opdrachten** de optie Gebruikers en **groepen** en vermeld op wie u het beleid wilt toepassen. Sluit ook de uitsluitingsgroep Voorwaardelijke toegang uit.

6. Kies **onder Opdrachten** de optie **Cloud-apps of -acties.**

7. Kies **voor** Opnemen de **optie Apps > Selecteren** en selecteer vervolgens de gewenste apps in de lijst met **cloud-apps.** Selecteer bijvoorbeeld Exchange Online. Kies **Selecteren** wanneer u klaar bent.

8. Kies **onder Access-besturingselementen** de optie **Grant** .

9. Kies **Toegang verlenen en** controleer vervolgens Apparaat vereisen dat moet worden gemarkeerd als **compatibel**. Selecteer Alle geselecteerde besturingselementen vereisen voor meerdere **besturingselementen.** Als u klaar is, kiest u **Selecteren.**

10. Selecteer **Aan** voor **beleid inschakelen** en kies vervolgens **Maken.**

> [!NOTE]
> Zorg ervoor dat uw apparaat voldoet voordat u dit beleid inschakelen. Anders kunt u niet meer worden vergrendeld en kunt u dit beleid pas wijzigen als uw gebruikersaccount is toegevoegd aan de uitsluitingsgroep Voorwaardelijke toegang.

## <a name="next-step"></a>Volgende stap

[![Stap 3: Beleid voor gast- en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Meer informatie over beleidsaanbevelingen voor gast- en externe gebruikers](identity-access-policies-guest-access.md)