---
title: Common identity and device access policies - Microsoft 365 for enterprise | Microsoft Docs
description: Hier worden de aanbevolen algemene beleidsregels en configuraties voor identiteits- en apparaattoegang beschreven.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: a928044df2c4185cff71db4883dcc1ddf30cdf3e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932584"
---
# <a name="common-identity-and-device-access-policies"></a>Algemeen beleid voor identiteiten en apparaattoegang

In dit artikel worden de meestgebruikte aanbevolen beleidsregels beschreven voor het beveiligen van toegang tot Microsoft 365-cloudservices, inclusief on-premises toepassingen die zijn gepubliceerd met Azure Active Directory -toepassingsproxy (Azure AD).

In deze richtlijnen wordt besproken hoe u het aanbevolen beleid implementeert in een nieuwe omgeving. Als u dit beleid in een afzonderlijke testomgeving instelt, kunt u de aanbevolen beleidsregels begrijpen en evalueren voordat u de implementatie in uw preproductie- en productieomgevingen organiseert. De nieuw ingebouwde omgeving kan alleen in de cloud of hybride omgeving worden gebruikt om uw evaluatiebehoeften te weerspiegelen.

## <a name="policy-set"></a>Beleidsset

In het volgende diagram ziet u de aanbevolen set beleidsregels. Hier ziet u op welke beveiligingslaag elk beleid van toepassing is en of het beleid van toepassing is op pc's, telefoons en tablets, of beide categorieën apparaten. Ook wordt aangegeven waar u dit beleid kunt configureren.

[![Algemene beleidsregels voor het configureren van identiteits- en apparaattoegang](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Hier volgt een PDF-overzicht van één pagina met koppelingen naar de afzonderlijke beleidsregels:

[![Thumb image for Identity and device protection for Microsoft 365 hand-out](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Weergeven als PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Downloaden als PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

In de rest van dit artikel wordt beschreven hoe u dit beleid kunt configureren.

> [!NOTE]
> Het is raadzaam om meervoudige verificatie (Multi-Factor Authentication, MFA) te vereisen voordat u apparaten inschrijft bij Intune om ervoor te zorgen dat het apparaat in het bezit is van de beoogde gebruiker. U moet apparaten registreren bij Intune voordat u beleid voor apparaat compliance kunt afdwingen.

Om u de tijd te geven om deze taken uit te voeren, wordt u aangeraden het basislijnbeleid te implementeren in de volgorde die in deze tabel wordt vermeld. Het MFA-beleid voor gevoelige en sterk reguleerde beschermingsniveaus kan echter op elk moment worden geïmplementeerd.

|Beveiligingsniveau|Beleidsregels|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* *of* hoog is](#require-mfa-based-on-sign-in-risk)||
||[Clients blokkeren die moderne verificatie niet ondersteunen](#block-clients-that-dont-support-modern-authentication)|Clients die geen moderne verificatie gebruiken, kunnen beleidsregels voor voorwaardelijke toegang omzeilen, dus het is belangrijk deze te blokkeren.|
||[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](#high-risk-users-must-change-password)|Dwingt gebruikers hun wachtwoord te wijzigen wanneer ze zich aanmelden als er activiteit met hoog risico voor hun account wordt gedetecteerd.|
||[Beleid voor gegevensbescherming van apps toepassen](#apply-app-data-protection-policies)|One Intune App Protection policy per platform (Windows, iOS/iPadOS, Android).|
||[Goedgekeurde apps en app-beveiliging vereisen](#require-approved-apps-and-app-protection)|Dwingt mobiele app-beveiliging af voor telefoons en tablets met iOS, iPadOS of Android.|
||[Beleidsregels voor apparaat compliance definiëren](#define-device-compliance-policies)|Eén beleid voor elk platform.|
||[Eis conforme pc’s](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Dwingt Intune-beheer van pc's af met Windows of MacOS.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog is*](#require-mfa-based-on-sign-in-risk)||
||[Compatibele pc's *en mobiele* apparaten vereisen](#require-compliant-pcs-and-mobile-devices)|Intune-beheer wordt afgedwongen voor pc's (Windows of MacOS) en telefoons of tablets (iOS, iPadOS of Android).|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Beleid toewijzen aan groepen en gebruikers

Voordat u beleid configureert, moet u de Azure AD-groepen identificeren die u gebruikt voor elke beveiligingslaag. Standaard is basislijnbeveiliging van toepassing op iedereen in de organisatie. Wanneer een gebruiker is opgenomen voor zowel basislijn- als gevoelige beveiliging, worden alle basislijnbeleidsregels plus het gevoelige beleid toegepast. De beveiliging is cumulatief en het meest beperkende beleid wordt afgedwongen.

Een aanbevolen gewoonte is om een Azure AD-groep te maken voor uitsluiting van voorwaardelijke toegang. Voeg deze groep toe aan al uw beleidsregels  voor voorwaardelijke toegang in **de** instelling Uitsluiten van de instelling Gebruikers en **groepen** in de sectie Toewijzingen. Op deze manier kunt u een gebruiker toegang geven terwijl u toegangsproblemen oplost. Dit wordt alleen aanbevolen als tijdelijke oplossing. Controleer deze groep op wijzigingen en zorg ervoor dat de uitsluitingsgroep alleen wordt gebruikt zoals bedoeld.

Hier volgen een voorbeeld van groepstoewijzing en uitsluitingen voor het vereisen van MFA.

![Voorbeeld van groepstoewijzing en uitsluitingen voor MFA-beleid](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Dit zijn de resultaten:

- Alle gebruikers moeten MFA gebruiken wanneer het aanmeldingsrisico gemiddeld of hoog is.

- Leden van de groep leidinggevenden moeten MFA gebruiken wanneer het aanmeldingsrisico laag, gemiddeld of hoog is.

  In dit geval komen leden van de groep Leidinggevenden overeen met zowel het basislijnbeleid als het gevoelige beleid voor voorwaardelijke toegang. De toegangsbesturingselementen voor beide beleidsregels worden gecombineerd, wat in dit geval overeenkomt met het gevoelige beleid voor voorwaardelijke toegang.

- Leden van de groep Top Secret Project X zijn altijd vereist voor het gebruik van MFA

  In dit geval komen leden van de groep Top Secret Project X overeen met het basislijnbeleid en het sterk reguleerde beleid voor voorwaardelijke toegang. De toegangsbesturingselementen voor beide beleidsregels worden gecombineerd. Omdat het toegangsbesturingselement voor het sterk reguleerde beleid voor voorwaardelijke toegang meer beperkend is, wordt het gebruikt.

Wees voorzichtig bij het toepassen van hogere beschermingsniveaus voor groepen en gebruikers. Zo moeten leden van de groep Top Secret Project X telkens MFA gebruiken wanneer ze zich aanmelden, zelfs als ze niet werken aan de sterk reguleerde inhoud voor Project X.

Alle Azure AD-groepen die zijn gemaakt als onderdeel van deze aanbevelingen, moeten worden gemaakt als Microsoft 365-groepen. Dit is belangrijk voor de implementatie van gevoeligheidslabels bij het beveiligen van documenten in Microsoft Teams en SharePoint.

![Schermopname voor het maken van Microsoft 365-groepen](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>MFA vereisen op basis van aanmeldingsrisico

Zorg dat uw gebruikers zich registreren voor MFA voordat u het gebruik ervan vereist. Als u Microsoft 365 E5, Microsoft 365 E3 met de invoeglicentie Identity & Threat Protection, Office 365 met EMS E5 of afzonderlijke Azure AD Premium P2-licenties hebt, kunt u het MFA-registratiebeleid met Azure AD Identity Protection gebruiken, zodat gebruikers zich moeten registreren voor MFA. Het [vereiste werk omvat](identity-access-prerequisites.md) het registreren van alle gebruikers met MFA.

Nadat uw gebruikers zijn geregistreerd, kunt u MFA vereisen voor aanmelding met een nieuw beleid voor voorwaardelijke toegang.

1. Ga naar de [Azure Portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies Azure Active Directory in de lijst **met Azure-services.**
3. Kies Beveiliging in **de** lijst Beheren **en** kies vervolgens **Voorwaardelijke toegang.**
4. Kies **Nieuw beleid** en typ de naam van het nieuwe beleid.

In de volgende tabellen worden de beleidsinstellingen voor voorwaardelijke toegang beschreven die nodig zijn om MFA te vereisen op basis van aanmeldingsrisico's.

In de **sectie Opdrachten:**

|Instelling|Eigenschappen|Waarden|Opmerkingen|
|---|---|---|---|
|Gebruikers en groepen|Opnemen|**Gebruikers en groepen > gebruikers en groepen:** selecteer specifieke groepen die specifieke gebruikersaccounts bevatten.|Begin met de groep met gebruikersaccounts voor de testfase.|
||Uitsluiten|**Gebruikers en groepen:** selecteer uw uitzonderingsgroep voor voorwaardelijke toegang; serviceaccounts (app-identiteiten).|Het lidmaatschap moet zo nodig en tijdelijk worden gewijzigd.|
|Cloud-apps of -acties|**Cloud-apps > Opnemen**|**Apps selecteren:** selecteer de apps die u met dit beleid wilt toepassen. Selecteer bijvoorbeeld Exchange Online.||
|Voorwaarden|||Configureer voorwaarden die specifiek zijn voor uw omgeving en behoeften.|
||Aanmeldingsrisico||Zie de richtlijnen in de volgende tabel.|
|

### <a name="sign-in-risk-condition-settings"></a>Instellingen voor aanmeldingsrisico

Pas de instellingen voor risiconiveau toe op basis van het beveiligingsniveau dat u als doel hebt.

|Beschermingsniveau|Waarden op risiconiveau vereist|Actie|
|---|---|---|
|Basislijn|Hoog, gemiddeld|Controleer beide.|
|Gevoelig|Hoog, gemiddeld, laag|Bekijk deze drie.|
|Sterk gereglementeerd||Laat alle opties uitgeschakeld als u altijd MFA wilt afdwingen.|
|

In de **sectie Besturingselementen van Access:**

|Instelling|Eigenschappen|Waarden|Actie|
|---|---|---|---|
|Grant|**Grant access**||Selecteer|
|||**Meervoudige verificatie vereisen**|Cheque|
||**Alle geselecteerde besturingselementen vereisen**||Selecteer|
|

Kies **Selecteren om** de instellingen voor verlenen op **te** slaan.

Selecteer ten slotte **Aan** voor **Beleid inschakelen** en kies vervolgens **Maken.**

Overweeg ook om het hulpprogramma [Wat als te](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) gebruiken om het beleid te testen.

## <a name="block-clients-that-dont-support-modern-authentication"></a>Cliënten blokkeren die geen moderne verificatie ondersteunen

Gebruik de instellingen in deze tabellen voor een beleid voor voorwaardelijke toegang om clients te blokkeren die geen ondersteuning bieden voor moderne verificatie.

Zie [dit artikel](../../enterprise/microsoft-365-client-support-modern-authentication.md) voor een lijst met clients in Microsoft 365 die moderne verificatie ondersteunen.

In de **sectie Opdrachten:**

|Instelling|Eigenschappen|Waarden|Opmerkingen|
|---|---|---|---|
|Gebruikers en groepen|Opnemen|**Gebruikers en groepen > gebruikers en groepen:** selecteer specifieke groepen die specifieke gebruikersaccounts bevatten.|Begin met de groep met gebruikersaccounts voor de testfase.|
||Uitsluiten|**Gebruikers en groepen:** selecteer uw uitzonderingsgroep voor voorwaardelijke toegang; serviceaccounts (app-identiteiten).|Het lidmaatschap moet zo nodig en tijdelijk worden gewijzigd.|
|Cloud-apps of -acties|**Cloud-apps > Opnemen**|**Apps selecteren:** selecteer de apps die betrekking hebben op de clients die geen ondersteuning bieden voor moderne verificatie.||
|Voorwaarden|**Client-apps**|Kies **Ja** voor **configureren** <p> De vinkjes voor **browser-** en **mobiele apps en desktopcl clients verwijderen**||
|

In de **sectie Besturingselementen van Access:**

|Instelling|Eigenschappen|Waarden|Actie|
|---|---|---|---|
|Grant|**Toegang blokkeren**||Selecteer|
||**Alle geselecteerde besturingselementen vereisen**||Selecteer|
|

Kies **Selecteren om** de instellingen voor verlenen op **te** slaan.

Selecteer ten slotte **Aan** voor **Beleid inschakelen** en kies vervolgens **Maken.**

Overweeg het hulpprogramma [Wat als te gebruiken](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen.

Voor Exchange Online kunt u verificatiebeleid gebruiken om basisverificatie uit te [schakelen,](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)waardoor alle aanvragen voor clienttoegang moeten worden gebruikt van moderne verificatie.

## <a name="high-risk-users-must-change-password"></a>Gebruikers met een hoog risico moeten het wachtwoord wijzigen

Als u er zeker van wilt zijn dat bij het aanmelden alle gekromde accounts van gebruikers met een hoog risico worden gedwongen een wachtwoordwijziging uit te voeren, moet u het volgende beleid toepassen.

Meld u aan bij [de Microsoft Azure-portal https://portal.azure.com) (met](https://portal.azure.com/) uw beheerdersreferenties en ga naar Azure AD **Identity Protection > gebruikersrisicobeleid).**

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

Selecteer ten slotte **Aan** voor **afdwingen van** beleid en kies **Opslaan.**

Overweeg het hulpprogramma [Wat als te gebruiken](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om het beleid te testen.

Gebruik dit beleid in combinatie met [Wachtwoordbeveiliging](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)voor Azure AD configureren, waarmee bekende zwakke wachtwoorden en hun varianten en aanvullende zwakke termen worden gedetecteerd en blokkeert die specifiek zijn voor uw organisatie. Met wachtwoordbeveiliging voor Azure AD zorgt u ervoor dat gewijzigde wachtwoorden sterk zijn.

## <a name="apply-app-data-protection-policies"></a>Beleid voor app-gegevensbescherming toepassen

App-beveiligingsbeleid (App) bepaalt welke apps zijn toegestaan en welke acties ze kunnen uitvoeren met de gegevens van uw organisatie. Met de beschikbare opties in APP kunnen organisaties de beveiliging aanpassen aan hun specifieke behoeften. Voor sommige gevallen is het niet duidelijk welke beleidsinstellingen vereist zijn voor het implementeren van een volledig scenario. Om organisaties te helpen prioriteit te geven aan het verbeteren van mobiele client-eindpunten, heeft Microsoft een taxonomie geïntroduceerd voor het IOS- en Android-beheer van mobiele apps.

Het framework voor app-gegevensbescherming is ingedeeld in drie verschillende configuratieniveaus, met elk niveau dat afbouwt op het vorige niveau:

- **Enterprise Basic Data Protection** (niveau 1) zorgt ervoor dat apps worden beveiligd met een pincode en versleuteld en selectieve bewerkingen uitvoeren. Op Android-apparaten wordt met dit niveau het apparaat in Android gevalideerd. Dit is een configuratie op invoerniveau die vergelijkbare controle biedt over gegevensbescherming in postvakbeleidsregels van Exchange Online, en waarmee IT en de gebruikerspopulatie worden introduceert in de APP.
- **De verbeterde gegevensbescherming van ondernemingen** (niveau 2) introduceert oplossingen voor preventie van APP-gegevenslekken en minimale os-vereisten. Dit is de configuratie die van toepassing is op de meeste mobiele gebruikers die toegang hebben tot werk- of schoolgegevens.
- **Enterprise High Data Protection** (Niveau 3) introduceert geavanceerde mechanismen voor gegevensbescherming, verbeterde configuratie van pincodes en APP Mobile Threat Defense. Deze configuratie is wenselijk voor gebruikers die toegang hebben tot gegevens met een hoog risico.

Als u specifieke aanbevelingen wilt zien voor elk configuratieniveau en de minimale apps die moeten worden beveiligd, bekijkt u het Data Protection Framework met behulp van [beleidsregels voor app-beveiliging.](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)

Met de principes die worden beschreven in [identiteits- en apparaattoegangsconfiguraties,](microsoft-365-policies-configurations.md)zijn de beveiligingslagen Basislijn en Gevoelige beveiliging nauw verbonden met de verbeterde instellingen voor gegevensbescherming op niveau 2. De hooggeguleerde beveiligingslaag is nauw verbonden met de instellingen voor hoge gegevensbeveiliging op niveau 3 voor ondernemingen.

|Beveiligingsniveau|Beveiligingsbeleid voor apps|Meer informatie|
|---|---|---|
|Basislijn|[Verbeterde gegevensbescherming op niveau 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|De beleidsinstellingen die worden afgedwongen in niveau 2 omvatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en worden alleen toegevoegd aan of bijgewerkt met de onderstaande beleidsinstellingen om meer besturingselementen en een geavanceerdere configuratie dan niveau 1 te implementeren.|
|Gevoelig|[Verbeterde gegevensbescherming op niveau 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|De beleidsinstellingen die worden afgedwongen in niveau 2 omvatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en worden alleen toegevoegd aan of bijgewerkt met de onderstaande beleidsinstellingen om meer besturingselementen en een geavanceerdere configuratie dan niveau 1 te implementeren.|
|Sterk reguleerd|[Beveiliging van hoge gegevensbeveiliging op niveau 3 van ondernemingen](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|De beleidsinstellingen die worden afgedwongen in niveau 3 omvatten alle beleidsinstellingen die worden aanbevolen voor niveau 1 en 2 en worden alleen toegevoegd aan of bijgewerkt met de onderstaande beleidsinstellingen om meer besturingselementen en een geavanceerdere configuratie dan niveau 2 te implementeren.|
|

Als u een nieuw beleid voor app-beveiliging wilt maken voor elk platform (iOS en Android) in Microsoft Endpoint Manager met behulp van de instellingen van het Data Protection Framework, kunt u het volgende doen:

1. Maak het beleid handmatig door de stappen te volgen in Het maken en implementeren van beveiligingsbeleid voor [apps met Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)
2. Importeer de [intune App Protection Policy Configuration Framework JSON-sjablonen](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) [met PowerShell-scripts van Intune.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Goedgekeurde apps en APP-beveiliging vereisen

Als u het app-beveiligingsbeleid wilt afdwingen dat u in Intune hebt toegepast, moet u een beleid voor voorwaardelijke toegang maken om goedgekeurde client-apps en de voorwaarden te vereisen die zijn ingesteld in het app-beveiligingsbeleid.

Voor het afdwingen van beveiligingsbeleid voor apps is een set beleidsregels vereist die worden beschreven in Het beveiligingsbeleid voor apps vereisen voor toegang tot [cloud-apps met voorwaardelijke toegang.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access) Dit beleid wordt elk opgenomen in deze aanbevolen set identiteits- en toegangsconfiguratiebeleidsregels.

Als u het beleid voor voorwaardelijke toegang wilt maken waarvoor goedgekeurde apps en APP-beveiliging zijn vereist, volgt u 'Stap 1: Een beleid voor voorwaardelijke toegang voor Azure AD configureren voor Microsoft 365' in [Scenario 1: Voor Microsoft 365-apps](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)zijn goedgekeurde apps met app-beveiligingsbeleid vereist. Hierdoor kunnen Outlook voor iOS en Android worden ingesteld, maar kunnen Exchange ActiveSync-clients met OAuth-ondersteuning geen verbinding maken met Exchange Online.

   > [!NOTE]
   > Dit beleid zorgt ervoor dat mobiele gebruikers toegang hebben tot alle Office-eindpunten met de toepasselijke apps.

Als u mobiele toegang tot Exchange Online inschakelen, implementeert u ActiveSync-clients blokkeren, waardoor Exchange [ActiveSync-clients](secure-email-recommended-policies.md#block-activesync-clients)geen verbinding kunnen maken met Exchange Online via basisverificatie. Dit beleid wordt niet in de afbeelding boven aan dit artikel afgebeeld. De beschrijving wordt beschreven in [beleidsaanbevelingen voor het beveiligen van e-mail.](secure-email-recommended-policies.md)

 Dit beleid maakt gebruik van de [grant-besturingselementen Goedgekeurde client-app vereisen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) en [App-beveiligingsbeleid vereisen.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Ten slotte zorgt het blokkeren van verouderde verificatie voor andere client-apps op iOS- en Android-apparaten ervoor dat deze clients beleidsregels voor voorwaardelijke toegang niet kunnen omzeilen. Als u de richtlijnen in dit artikel volgt, hebt u al geblokkeerde clients geconfigureerd die geen [ondersteuning bieden voor moderne verificatie.](#block-clients-that-dont-support-modern-authentication)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Beleidsregels voor apparaat compliance definiëren

Beleidsregels voor apparaat compliance definiëren de vereisten waar apparaten aan moeten voldoen om te worden vastgesteld als compatibel. U maakt intune device compliance policies from the Microsoft Endpoint Manager admin center.

U moet een beleid maken voor elk pc-, telefoon- of tabletplatform:

- Android-apparaatbeheerder
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 en hoger
- Windows 10 en hoger

Als u beleid voor apparaatna compliance wilt maken, meld u zich aan  bij het Beheercentrum van [Microsoft Endpoint Manager](https://endpoint.microsoft.com) met uw beheerdersreferenties en gaat u naar beleidsregels voor \>  \> **apparaatnavigatie.** Selecteer **Beleid maken.**

Beleidsregels voor apparaat compliance moeten worden toegewezen aan gebruikersgroepen. U wijst een beleid toe nadat u dit hebt maken en opslaan. Selecteer het beleid in het beheercentrum en selecteer **vervolgens Toewijzingen.** Nadat u de groepen hebt geselecteerd die het beleid moeten ontvangen, selecteert u Opslaan om **de** groepstoewijzing op te slaan en het beleid te implementeren.

Zie Een compliancebeleid maken [in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) in de Documentatie van Intune voor stapsgewijse instructies voor het maken van nalevingsbeleid in Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Aanbevolen instellingen voor Windows 10 en hoger

De volgende instellingen worden aanbevolen voor pc's met Windows 10 en hoger, zoals geconfigureerd in stap **2:** Compliance-instellingen, van het proces voor het maken van beleid.

Zie deze tabel voor > evaluatieregels van **Windows Health Health Health Service.**

|Eigenschappen|Value|Actie|
|---|---|---|
|BitLocker vereisen|Vereisen|Selecteer|
|Vereisen dat Secure Start is ingeschakeld op het apparaat|Vereisen|Selecteer|
|Codeintegriteit vereisen|Vereisen|Selecteer|
|

Geef **voor Apparaateigenschappen** de juiste waarden op voor versies van het besturingssysteem op basis van uw IT- en beveiligingsbeleid.

Selecteer Vereisen voor compliance **in** Configuration **Manager.**

Zie **deze tabel voor** systeembeveiliging.

|Type|Eigenschappen|Value|Actie|
|---|---|---|---|
|Wachtwoord|Een wachtwoord vereisen om mobiele apparaten te ontgrendelen|Vereisen|Selecteer|
||Eenvoudige wachtwoorden|Blokkeren|Selecteer|
||Wachtwoordtype|Apparaat als standaard|Selecteer|
||Minimale lengte van wachtwoord|6|Type|
||Maximum aantal minuten inactiviteit voordat wachtwoord vereist is|15|Type <p> Deze instelling wordt ondersteund voor Android-versies 4.0 en hoger of KNOX 4.0 en hoger. Voor iOS-apparaten wordt dit ondersteund voor iOS 8.0 en hoger.|
||Wachtwoordverloop (dagen)|41|Type|
||Aantal vorige wachtwoorden om hergebruik te voorkomen|5|Type|
||Wachtwoord vereisen wanneer het apparaat terugkomt uit de niet-actieve status (Mobiel en Holografisch)|Vereisen|Beschikbaar voor Windows 10 en hoger|
|Versleuteling|Versleuteling van gegevensopslag op apparaat|Vereisen|Selecteer|
|Apparaatbeveiliging|Firewall|Vereisen|Selecteer|
||Antivirussoftware|Vereisen|Selecteer|
||Antispyware|Vereisen|Selecteer <p> Voor deze instelling is een oplossing tegen spyware vereist die is geregistreerd bij het Windows-beveiligingscentrum.|
|Defender|Microsoft Defender Antimalware|Vereisen|Selecteer|
||Minimale versie van Microsoft Defender Antimalware||Type <p> Alleen ondersteund voor Windows 10-bureaublad. Microsoft raadt versies aan die niet meer dan vijf van de meest recente versie achterblijven.|
||Microsoft Defender Antimalware-handtekening bijgewerkt|Vereisen|Selecteer|
||Realtime-beveiliging|Vereisen|Selecteer <p> Alleen ondersteund voor Windows 10-bureaublad|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

|Type|Eigenschappen|Value|Actie|
|---|---|---|---|
|Regels voor Microsoft Defender voor eindpunt|Vereisen dat het apparaat binnen of onder de risicoscore van de computer ligt|Gemiddeld|Selecteer|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Compatibele pc's vereisen (maar geen compatibele telefoons en tablets)

Voordat u een beleid toevoegt om compatibele pc's te vereisen, moet u apparaten registreren voor beheer in Intune. Het is raadzaam om meervoudige verificatie te gebruiken voordat u apparaten inschrijft bij Intune om er zeker van te zijn dat het apparaat in bezit is van de beoogde gebruiker.

Compatibele pc's vereisen:

1. Ga naar de [Azure Portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies Azure Active Directory in de lijst **met Azure-services.**
3. Kies Beveiliging in **de** lijst Beheren **en** kies vervolgens **Voorwaardelijke toegang.**
4. Kies **Nieuw beleid** en typ de naam van het nieuwe beleid.

5. Kies **onder Toewijzingen** gebruikers **en groepen** en neem op wie u het beleid wilt toepassen. Sluit ook de uitsluitingsgroep voor voorwaardelijke toegang uit.

6. Kies **onder Toewijzingen** de **optie Cloud-apps of acties.**

7. Kies **bij** Opnemen de **optie Apps > Selecteer** en selecteer vervolgens de gewenste apps in de lijst met **Cloud-apps.** Selecteer bijvoorbeeld Exchange Online. Kies **Selecteren** wanneer u klaar bent.

8. Als u compatibele pc's (maar geen compatibele telefoons en tablets) wilt vereisen, kiest u onder Toewijzingen de **> apparaatplatforms.** Selecteer **Ja** voor **configureren.** Kies **Apparaatplatforms selecteren,** selecteer **Windows** en **macOS** en kies Vervolgens **Klaar.**

9. Kies **Verlenen onder** Access-besturingselementen. 

10. Kies **Toegang verlenen en** vink het selectievakje Apparaat vereisen aan om te worden gemarkeerd als **compatibel.** Voor meerdere besturingselementen **selecteert u Alle geselecteerde besturingselementen vereisen.** Kies Selecteren wanneer u klaar **is.**

11. Selecteer **Beleid** **inschakelen en** kies Maken. 

> [!NOTE]
> Zorg ervoor dat uw apparaat compatibel is voordat u dit beleid inschakelen. Anders wordt u mogelijk vergrendeld en kunt u dit beleid niet wijzigen totdat uw gebruikersaccount is toegevoegd aan de uitsluitingsgroep Voorwaardelijke toegang.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Compatibele pc's *en mobiele* apparaten vereisen

Naleving vereisen voor alle apparaten:

1. Ga naar de [Azure Portal](https://portal.azure.com)en meld u aan met uw referenties.
2. Kies Azure Active Directory in de lijst **met Azure-services.**
3. Kies Beveiliging in **de** lijst Beheren **en** kies vervolgens **Voorwaardelijke toegang.**
4. Kies **Nieuw beleid** en typ de naam van het nieuwe beleid.

5. Kies **onder Toewijzingen** gebruikers **en groepen** en neem op wie u het beleid wilt toepassen. Sluit ook de uitsluitingsgroep voor voorwaardelijke toegang uit.

6. Kies **onder Toewijzingen** de **optie Cloud-apps of acties.**

7. Kies **bij** Opnemen de **optie Apps > Selecteer** en selecteer vervolgens de gewenste apps in de lijst met **Cloud-apps.** Selecteer bijvoorbeeld Exchange Online. Kies **Selecteren** wanneer u klaar bent.

8. Kies **Verlenen onder** Access-besturingselementen. 

9. Kies **Toegang verlenen en** vink het selectievakje Apparaat vereisen aan om te worden gemarkeerd als **compatibel.** Voor meerdere besturingselementen **selecteert u Alle geselecteerde besturingselementen vereisen.** Kies Selecteren wanneer u klaar **is.**

10. Selecteer **Beleid** **inschakelen en** kies Maken. 

> [!NOTE]
> Zorg ervoor dat uw apparaat compatibel is voordat u dit beleid inschakelen. Anders wordt u mogelijk vergrendeld en kunt u dit beleid niet wijzigen totdat uw gebruikersaccount is toegevoegd aan de uitsluitingsgroep Voorwaardelijke toegang.

## <a name="next-step"></a>Volgende stap

[![Stap 3: Beleid voor gasten en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Meer informatie over beleidsaanbevelingen voor gasten en externe gebruikers](identity-access-policies-guest-access.md)
