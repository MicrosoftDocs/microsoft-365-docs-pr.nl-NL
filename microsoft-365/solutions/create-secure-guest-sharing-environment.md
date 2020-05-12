---
title: Een beveiligde omgeving voor het delen met gasten maken
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: In dit artikel vindt u meer informatie over de beschikbare opties voor het maken van een veilige omgeving voor het delen met een gast in Microsoft 365.
ms.openlocfilehash: b567be8df8d0b9dc96400627c6607560fefd9c39
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159477"
---
# <a name="create-a-secure-guest-sharing-environment"></a>Een beveiligde omgeving voor het delen met gasten maken

In dit artikel vindt u verschillende opties voor het maken van een veilige omgeving voor het delen met gasten in Microsoft 365. Dit is een voorbeeldscenario om u een idee te geven van de beschikbare opties. U kunt deze procedures in verschillende combinaties gebruiken om te voldoen aan de beveiligings- en compliance-behoeften van uw organisatie. Aan het einde van het artikel zullen we een testcase doorlopen om te zien hoe sommige van deze opties samenwerken.

Dit scenario omvat:

- Meervoudige verificatie voor gasten instellen.
- Gebruiksvoorwaarden voor gasten instellen.
- Driemaandelijkse beoordelingen voor gasttoegang instellen om periodiek te valideren of gasten nog steeds toestemming nodig hebben voor teams en sites.
- Gasten beperken tot alleen webtoegang voor onbeheerde apparaten.
- Een time-outbeleid voor sessies configureren om ervoor te zorgen dat gasten dagelijks worden geverifieerd.
- Gevoeligheidslabels maken en publiceren om inhoud te classificeren.
- Een type voor gevoelige informatie maken voor een zeer gevoelig project.
- Automatisch een label *Zeer gevoelig* toewijzen aan documenten die het type gevoelige informatie bevatten.
- Gasttoegang automatisch verwijderen voor bestanden die als *zeer gevoelig* zijn aangemerkt.

Voor een aantal van de opties die in dit artikel worden beschreven, moeten gasten een account hebben in Azure Active Directory. Als u er zeker van wilt zijn dat gasten worden opgenomen in de adreslijst wanneer u bestanden en mappen met hen deelt, gebruikt u de [SharePoint- en OneDrive-integratie met Azure AD B2B Preview](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).

Merk op dat we het in dit artikel niet hebben over het inschakelen van instellingen voor het delen met gasten. Zie [Samenwerken met personen buiten uw organisatie](https://docs.microsoft.com/Office365/Enterprise/collaborate-with-people-outside-your-organization) voor meer informatie over het inschakelen van de functie voor het delen met gasten onder verschillende scenario's.

## <a name="set-up-multi-factor-authentication-for-guests"></a>Meervoudige verificatie instellen voor gasten

Meervoudige verificatie vermindert de kans dat een account wordt aangetast aanzienlijk. Aangezien gastgebruikers mogelijk persoonlijke e-mailaccounts gebruiken die niet voldoen aan enig beleid of aanbevolen procedures, is het belangrijk dat u meervoudige verificatie van gasten vereist. Als de gebruikersnaam en het wachtwoord van een gastgebruiker worden gestolen, vermindert het vereisen van een tweede verificatiestap de kans dat onbekende partijen toegang krijgen tot uw sites en bestanden aanzienlijk.

In dit voorbeeld wordt meervoudige verificatie voor gasten ingesteld met behulp van een beleid voor voorwaardelijke toegang in Azure Active Directory.

Meervoudige verificatie instellen voor gasten
1. Zoek in Microsoft Azure naar *voorwaardelijke toegang*.
2. Klik in de blade **voorwaardelijke toegang - beleid** op **nieuw beleid**.
3. Typ in het veld **naam** *gast-MFA*.
4. Klik onder **toewijzingen**op **gebruikers en groepen**.
5. Selecteer op de blade **Gebruikers en groepen** de optie **Gebruikers en groepen selecteren**, schakel het selectievakje **Alle gasten en externe gebruikers** in en klik vervolgens op **Gereed**.
4. Klik onder **toegangsbeheer**op **toewijzen**.
5. Schakel op de blade **Toewijzen** het selectievakje **Meervoudige verificatie vereisen** in en klik vervolgens op **Selecteren**.
6. Klik op de blade **Nieuw** onder **Beleid inschakelen** op **Aan** en klik vervolgens op **Maken**.

Nu moeten gasten zich eerst inschrijven voor meervoudige verificatie voordat ze toegang krijgen tot gedeelde inhoud, sites of teams.

### <a name="more-information"></a>Meer informatie

[Een cloudgebaseerde implementatie van Azure Multi-Factor Authentication plannen](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a>Gebruiksvoorwaarden voor gasten instellen

Vaak hebben gastgebruikers mogelijk geen geheimhoudingsovereenkomsten of andere juridische overeenkomsten met uw organisatie ondertekend. U kunt instellen dat gasten een gebruiksrechtovereenkomst moeten accepteren, voordat ze toegang krijgen tot bestanden die met hen zijn gedeeld. De gebruiksvoorwaarden kunnen worden weergegeven wanneer ze de eerste keer proberen toegang te krijgen tot een gedeeld bestand of een gedeelde site.

Als u gebruiksvoorwaarden wilt maken, moet u eerst het document maken in Word of een andere tekstverwerker en het vervolgens opslaan als een PDF-bestand. Dit bestand kan vervolgens worden geüpload naar Azure AD.

Gebruiksvoorwaarden voor Azure AD maken
1. Meld u aan bij Azure als een globale beheerder, beveiligingsbeheerder of beheerder van voorwaardelijke toegang.
2. Navigeer naar [gebruiksvoorwaarden](https://aka.ms/catou).
3. Klik op **nieuwe voorwaarden**.</br>
   ![Schermafbeelding van de instellingen voor nieuwe gebruiksvoorwaarden van Azure AD](../media/azure-ad-guest-terms-of-use.png)
4. Typ in de vakken **naam** en **weergegeven naam**, *gebruiksvoorwaarden voor gasten*.
6. Voor **gebruiksrechtovereenkomst**bladert u naar het PDF-bestand dat u hebt gemaakt en selecteert u het.
7. Selecteer de taal voor uw gebruiksrechtovereenkomst.
8. Stel **Gebruikers verplichten om de gebruiksvoorwaarden uit te vouwen** in op **Aan**.
9. Kies onder **Voorwaardelijke toegang** in de lijst **Afdwingen met sjabloon voor voorwaardelijke toegang**, **Maak later een beleid voor voorwaardelijke toegang**.
10. Klik op **Maken**.

Als u de gebruiksvoorwaarden hebt gemaakt, is de volgende stap het maken van een beleid voor voorwaardelijke toegang waarin de gebruiksrechtovereenkomst voor gastgebruikers wordt weergegeven.

Een voorwaardelijk toegangsbeleid maken
1. Zoek in Microsoft Azure naar *voorwaardelijke toegang*.
2. Klik in de blade **voorwaardelijke toegang - beleid** op **nieuw beleid**.
3. Typ in het vak **naam** *gebruiksrechtovereenkomst voor gastgebruikers*.
4. Klik onder **toewijzingen**op **gebruikers en groepen**.
5. Selecteer op de blade **Gebruikers en groepen** de optie **Gebruikers en groepen selecteren**, schakel het selectievakje **Alle gasten en externe gebruikers** in en klik vervolgens op **Gereed**.
6. Klik onder **toewijzingen**op **cloud-apps of -acties**.
7. Selecteer op het tabblad **Opnemen**, **Apps selecteren** en klik vervolgens op **Selecteren**.
8. Selecteer op de blade **selecteren**, **Microsoft Teams**, **Office 365 SharePoint Online** en **Outlook Groups** en klik vervolgens op **Selecteren**.
9. Klik op de blade **Cloud-apps of -acties** op **Gereed**.
10. Klik onder **toegangsbeheer**op **toewijzen**.
11. Selecteer op de blade **Toewijzen** de optie **Gebruiksrechtovereenkomst voor gasten** en klik vervolgens op **Selecteren**.
12. Klik op de blade **Nieuw** onder **Beleid inschakelen** op **Aan** en klik vervolgens op **Maken**.

De eerste keer dat een gastgebruiker probeert toegang te krijgen tot inhoud of een team of site in uw organisatie, moeten ze de gebruiksvoorwaarden accepteren.

### <a name="more-information"></a>Meer informatie
[Gebruiksvoorwaarden voor Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a>Revisies voor gasttoegang instellen

Met toegangscontroles in Azure AD kunt u een periodieke beoordeling van gebruikerstoegang tot verschillende teams en groepen automatiseren. Door specifiek een toegangscontrole voor gasten te vereisen, kunt u ervoor zorgen dat gastgebruikers niet langer toegang houden tot gevoelige informatie van uw organisatie dan nodig is.

Toegangscontroles kunnen in programma's worden georganiseerd. Een programma is een groepering van vergelijkbare toegangscontroles die kunnen worden gebruikt om toegangscontroles te organiseren voor rapportage- en auditdoeleinden.

In dit voorbeeld maken we een programma voor de controle van gasttoegang.

Een programma maken
1. Meld u aan bij de Azure-portal en open de pagina [identiteitsbeheer](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade).
2. Klik in het linkermenu op **Programma's**
3. Klik op **nieuw programma**.
4. Typ in het vak **Naam** *programma voor het controleren van gasttoegang*.
5. Typ in het vak **beschrijving** *programma voor controle van gasttoegang*.
6. Klik op **Maken**.

Wanneer het programma is gemaakt, kunnen we toegangscontrole voor gasten maken en aan het programma koppelen.

De controle van de toegang van een gastgebruiker instellen
1. Klik op de pagina [Identiteitsbeheer](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) in het linkermenu op **Toegangscontroles**.
2. Klik op **nieuwe toegangscontrole**.</br>
   ![Schermafbeelding van de controle-instellingen van Azure AD Access](../media/azure-ad-create-access-review.png)
3. Typ in het vak **Naam** *driemaandelijkse gasttoegangscontrole*.
4. Voor **frequentie**kiest u **driemaandelijks**.
5. Kies voor **beëindigen** de optie **nooit**.
6. Kies **alleen gastgebruikers**voor **bereik**.
7. Klik op **groep**, selecteer de groepen die u wilt opnemen in de toegangscontrole en klik vervolgens op **selecteren**.
8. Klik onder **Programma's** op **koppeling naar programma**.
9. Kies op de blade **Selecteer een programma** de optie **Programma gasttoegangscontrole**
10. Klik op **Start**.

Voor elke groep die u opgeeft, wordt een afzonderlijke toegangscontrole gemaakt. Groepseigenaren van elke groep worden driemaandelijks gemaild om gasttoegang tot hun groepen goed te keuren of te weigeren.

Het is belangrijk op te merken dat gasten toegang kunnen krijgen tot teams of groepen, of tot individuele bestanden en mappen. Als u toegang tot bestanden en mappen hebt gegeven, worden gasten mogelijk niet aan een bepaalde groep toegevoegd. Als u toegangscontroles wilt uitvoeren op gastgebruikers die niet tot een team of groep behoren, kunt u een dynamische groep in Azure AD maken die alle gasten bevat en vervolgens een toegangscontrole voor die groep maken.

### <a name="more-information"></a>Meer informatie
[Gasttoegang beheren met Azure AD-toegangscontroles](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[Een toegangscontrole maken voor groepen of toepassingen in Azure AD-toegangscontroles](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a>Stel webtoegang in voor gastgebruikers

U kunt het risico op een aanval beperken en het beheer vereenvoudigen door gastgebruikers alleen toegang te verlenen tot uw teams, sites en bestanden via een webbrowser. Dit wordt gedaan met beleid voor voorwaardelijke toegang van Azure AD.

De toegang van gasten tot beperken tot alleen webtoegang
1. Zoek in Microsoft Azure naar *voorwaardelijke toegang*.
2. Klik in de blade **voorwaardelijke toegang - beleid** op **nieuw beleid**.
3. Typ in het vak **naam** *browsertoegang voor gastgebruikers*.
4. Klik onder **toewijzingen**op **gebruikers en groepen**.
5. Selecteer op de blade **Gebruikers en groepen** de optie **Gebruikers en groepen selecteren**, schakel het selectievakje **Alle gasten en externe gebruikers** in en klik vervolgens op **Gereed**.
6. Klik onder **toewijzingen**op **cloud-apps of -acties**.
7. Selecteer op het tabblad **Opnemen**, **Apps selecteren** en klik vervolgens op **Selecteren**.
8. Selecteer op de blade **selecteren**, **Microsoft Teams**, **Office 365 SharePoint Online** en **Outlook Groups** en klik vervolgens op **Selecteren**.
9. Klik op de blade **Cloud-apps of -acties** op **Gereed**.
10. Klik onder **toewijzingen**op **voorwaarden**.
11. Klik op de blade **Voorwaarden** op **Client-apps**.
12. Klik op de blade **Client-apps** op **Ja** voor** Configureren** en selecteer vervolgens de instellingen voor **Mobiele apps en bureaublad-clients** en **Moderne verificatieclients**.</br>
    ![Schermafbeelding van de instellingen van client-apps voor voorwaardelijke toegang van Azure AD](../media/azure-ad-conditional-access-client-mobile.png)
13. Klik op **gereed**en klik vervolgens op de blade **voorwaarden** en daarna nogmaals op **gereed**.
14. Klik onder **toegangsbeheer**op **toewijzen**.
15. Selecteer op de blade **toewijzen** de optie **vereisen dat apparaat moet worden gemarkeerd als compatibel** en **vereisen dat hybride Azure AD-aan het apparaat is toegevoegd**.
16. Selecteer onder **voor meerdere besturingselementen** **een van de geselecteerde besturingselementen vereisen**en klik vervolgens op **selecteren**.
17. Klik op de blade **Nieuw** onder **Beleid inschakelen** op **Aan** en klik vervolgens op **Maken**.

## <a name="configure-a-session-timeout-for-guest-users"></a>Een sessietime-out configureren voor gastgebruikers

Vereisen dat gasten regelmatig verifiëren, kan de kans verkleinen dat onbekende gebruikers toegang krijgen tot de inhoud van uw organisatie, als het apparaat van een gastgebruiker niet veilig is. U kunt een voorwaardelijk toegangsbeleid voor sessie time-outs configureren voor gastgebruikers in Azure AD.

Een beleid voor de time-out van een gastsessie configureren
1. Zoek in Microsoft Azure naar *voorwaardelijke toegang*.
2. Klik in de blade **voorwaardelijke toegang - beleid** op **nieuw beleid**.
3. Typ in het vak **naam** *time-out van gast sessie*.
4. Klik onder **toewijzingen**op **gebruikers en groepen**.
5. Selecteer op de blade **Gebruikers en groepen** de optie **Gebruikers en groepen selecteren**, schakel het selectievakje **Alle gasten en externe gebruikers** in en klik vervolgens op **Gereed**.
6. Klik onder **toewijzingen**op **cloud-apps of -acties**.
7. Selecteer op het tabblad **Opnemen**, **Apps selecteren** en klik vervolgens op **Selecteren**.
8. Selecteer op de blade **selecteren**, **Microsoft Teams**, **Office 365 SharePoint Online** en **Outlook Groups** en klik vervolgens op **Selecteren**.
9. Klik op de blade **Cloud-apps of -acties** op **Gereed**.
10. Klik onder **toegangsbeheer**op **sessie**.
11. Op de blade **sessie** selecteert u **aanmeldingsfrequentie**.
12. Selecteer **1** en **dagen** voor de tijdsperiode en klik vervolgens op **selecteren**.
13. Klik op de blade **Nieuw** onder **Beleid inschakelen** op **Aan** en klik vervolgens op **Maken**.

## <a name="create-sensitivity-labels"></a>Gevoeligheidslabels maken

Gevoeligheidslabels kunnen op verschillende manieren worden gebruikt om de gegevens van uw organisatie te classificeren en te beveiligen. In dit voorbeeld ziet u hoe labels kunnen worden gebruikt om u te helpen bij het beheren van gasttoegang tot gedeelde bestanden en mappen.

Eerst maken we drie gevoeligheidslabels in het Microsoft 365 Compliance Center:

- Algemeen
- gevoelig
- Zeer gevoelig

Gebruik de volgende procedure om de labels *Algemeen* en *Gevoelig* te maken.

Een classificatielabel maken (Algemeen en Gevoelig)
1. Vouw in het [Microsoft 365 Compliance Center](https://compliance.microsoft.com) in de linkernavigatiebalk **Classificatie** uit en klik vervolgens op **Gevoeligheidslabels**.
2. Klik op **een label maken**.
3. Typ bij **Labelnaam** *Algemeen* of *Gevoelig*.
4. In **Knopinfo** typt u *Algemene informatie die kan worden gedeeld met werknemers, gasten en partners* of *Gevoelige informatie. Deel alleen met werknemers en geautoriseerde gasten*. Klik vervolgens op **Volgende**.
5. Laat de versleuteling **uit** en klik op **volgende**.
6. Laat de markering van inhoud **uit** en klik op **volgende**.
7. Laat het verlies van gegevensverlies voorkomen **uit** en klik op **volgende**.
8. Laat automatische labeling **uit** en klik op **volgende**.
9. Klik op **Maken**.

Met het label *Zeer gevoelig* voegen we met het label automatische watermerken van documenten toe.

Een classificatielabel maken (Zeer gevoelig)
1. Klik op **een label maken**.
2. In **Labelnaam** typt u *Zeer gevoelig*.
3. In **Knopinfo** typt u *Zeer gevoelige informatie. Niet delen met gasten*. Vervolgens klikt u op **volgende**.
4. Laat de versleuteling **uit** en klik op **volgende**.
5. Schakel de markerings voor inhoud **aan**, voeg een selectievakje **koptekst toevoegen** toe en klik vervolgens op **tekst aanpassen**.
6. Typ *Zeer gevoelig* voor de koptekst en klik op **Opslaan**.
7. Schakel op de pagina **inhoudsmarkering** de inhoudsmarkering **in**.
8. Selecteer het selectievakje **een watermerk toevoegen** en klik vervolgens op **tekst aanpassen**.
9. Bij **Tekst voor het watermerk** typt u *Zeer gevoelig*.
10. Typ *24* voor **tekengrootte** en klik vervolgens op **opslaan**.
11. Klik op de pagina **inhoudsmarkering** op **volgende**.
12. Laat het verlies van gegevensverlies voorkomen **uit** en klik op **volgende**.
13. Laat automatische labeling **uit** en klik op **volgende**.
14. Klik op **Maken**.

![Schermafbeelding van gevoeligheidslabels in het Microsoft 365 Compliance Center](../media/microsoft-365-sharing-sensitivity-labels.png)

Nadat u de labels heeft gemaakt, is de volgende stap het publiceren ervan. 

Labels publiceren
1. Klik op de pagina **gevoeligheidslabels** op **labels publiceren**.
2. Klik op **labels kiezen om te publiceren**.
3. Klik op **toevoegen**, selecteer de labels die u hebt gemaakt en klik vervolgens op **toevoegen**.
4. Klik op **Gereed**.
5. Klik op **Volgende**.
6. Laat de gebruikers en groepen op **alle** staan en klik op **volgende**.
7. Kies in de lijst **dit label standaard toepassen op documenten en e-mail** de optie **algemeen** en klik vervolgens op **volgende**.
8. Typ op de pagina **Beleidsinstellingen** *Documentgevoeligheid* voor de naam en klik vervolgens op **Volgende**.
9. Klik op **Publiceren**.

De gepubliceerde labels zijn nu beschikbaar voor gebruikers van Office-bureaublad-apps. Wanneer gebruikers het label **Zeer gevoelig** toepassen, wordt er automatisch een watermerk aan het document toegevoegd.

### <a name="more-information"></a>Meer informatie
[Overzicht van gevoeligheidslabels](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a>Een type voor gevoelige informatie maken voor een zeer gevoelig project

De typen gevoelige informatie zijn vooraf gedefinieerde tekenreeksen die kunnen worden gebruikt in werkstromen om nalevingsvereisten af te dwingen. Het Microsoft 365 Compliance Center bevat meer dan honderd soorten gevoelige informatie, waaronder rijbewijsnummers, creditcardnummers, bankrekeningnummers, enz.

U kunt aangepaste typen gevoelige informatie maken om inhoud te beheren die specifiek is voor uw organisatie. In dit voorbeeld maken we een aangepast type voor gevoelige informatie voor een zeer gevoelig project. Vervolgens kunnen we dit gevoelig informatietype gebruiken om automatisch een classificatielabel toe te wijzen.

Een gevoelig informatietype maken
1. Vouw in het [Microsoft 365 Compliance Center](https://compliance.microsoft.com) in de linkernavigatiebalk **Classificatie** uit en klik vervolgens op **Gevoelige informatietypen**.
2. Klik op **Maken**.
3. Voor **naam** en **beschrijving**typt u **Project Saturnus**en klik vervolgens op **volgende**.
4. Klik op **een element toevoegen**.
5. Selecteer **Trefwoorden** in de lijst **Inhoud zoeken met** en typ *Project Saturnus* in het trefwoordvak.
6. Klik op **Volgende** en vervolgens op **Voltooien**.
7. Als u wordt gevraagd of u het gevoelige informatietype wilt testen, klikt u op **Nee**.

### <a name="more-information"></a>Meer informatie
[Aangepaste gevoelige informatietypen](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-a-policy-to-assign-a-label-based-on-a-sensitive-information-type"></a>Een beleid maken om een label toe te wijzen op basis van een gevoelig informatietype

Zodra het type gevoelige informatie is gemaakt, kunnen we een bestandsbeleid in Microsoft Cloud App Security maken dat automatisch het label *Zeer gevoelig* toepast op documenten die de *Project Saturnus*-tekenreeks bevatten.

> [!NOTE]
> Er is een replicatieproces waarmee gevoeligheidslabels beschikbaar worden in Cloud App Security. Het is mogelijk dat u het label voor een beleid niet onmiddellijk kunt zien.

Een bestandsbeleid op basis van een gevoelig informatietype maken
1. Open [Microsoft Cloud App Security](https://portal.cloudappsecurity.com).
2. Vouw in het navigatievenster aan de linkerkant **Beheer**uit en klik vervolgens op **Beleid**.
3. Klik op **Beleid maken**en kies vervolgens **Bestandsbeleid**.
4. Typ voor **Beleidsnaam** *Project Saturnus labeling*.
5. Klik onder **een filter maken voor de bestanden waarop dit beleid wordt toegepast** tweemaal op X om de standaardfilters te verwijderen.
7. Kies **App** in de lijst **Selecteer een filter** en selecteer vervolgens **Microsoft SharePoint Online** in de lijst **Apps selecteren...**.
8. Kies onder **inspectiemethode**, **dataclassificeringsservice**.
9. Kies in de lijst **Inspectietype kiezen**, **Gevoelig informatietype**.
10. Zoek en selecteer het gevoeligheidslabel *Project Saturnus* en klik vervolgens op **Gereed**.</br>
   ![Schermafbeelding van de instellingen voor de inspectiemethode van Cloud App Security](../media/mcas-sensitive-info-type-project-saturn.png)
11. Vouw onder **Beheermodel** de optie **Microsoft SharePoint Online** uit.
12. Schakel het selectievakje **Classificatielabel toepassen** in en selecteer het label **Zeer gevoelig**.
13. Klik op **Maken**.

Als het beleid van kracht is, zal Cloud App Security, wanneer een gebruiker 'Project Saturnus' in een document typt, automatisch het label *Zeer gevoelig* toepassen wanneer het bestand wordt gescand.

### <a name="more-information"></a>Meer informatie
[Bestandsbeleidsregels](https://docs.microsoft.com/cloud-app-security/data-protection-policies)

## <a name="create-a-policy-to-remove-guest-access-to-highly-sensitive-files"></a>Een beleid maken voor het verwijderen van gasttoegang tot zeer gevoelige bestanden

In het voorbeeld in dit artikel mogen bestanden met het label *Zeer gevoelig* niet worden gedeeld met gasten. We kunnen een bestandsbeleid maken in de cloud app Security waarmee gasttoegang automatisch wordt verwijderd voor bestanden met dat label.

Hiermee wordt niet voorkomen dat gebruikers deze bestanden delen of opnieuw delen. U bent nog steeds afhankelijk van uw gebruikersbeleid voor het beheer van bestanden die zijn opgeslagen op sites die het delen met gasten toestaan. Dit is echter een handig hulpmiddel om gasttoegang te verwijderen voor bestanden waaraan gevoelige informatie is toegevoegd nadat ze zijn gedeeld met gasten.

Een op labels gebaseerd bestandsbeleid maken
1. Open [Microsoft Cloud App Security](https://portal.cloudappsecurity.com).
2. Vouw in het navigatievenster aan de linkerkant **Beheer**uit en klik vervolgens op **Beleid**.
3. Klik op **Beleid maken**en kies vervolgens **Bestandsbeleid**.
4. Typ voor **Beleidsnaam** *Project Saturn - gasttoegang verwijderen*.
5. Klik onder **een filter maken voor de bestanden waarop dit beleid wordt toegepast** tweemaal op X om de standaardfilters te verwijderen.
6. Kies **App** in de lijst **Selecteer een filter** en selecteer vervolgens **Microsoft SharePoint Online** in de lijst **Apps selecteren...**.
7. Klik op **een filter toevoegen**.
8. Kies in de lijst **Selecteer een filter** de optie **Classificatielabel** en selecteer vervolgens **Azure Information Protection** in de lijst **Filter selecteren...**.
9. Selecteer in de lijst **Classificatielabel selecteren** de optie **Zeer gevoelig**.</br>
   ![Schermafbeelding van de filterinstellingen van het Cloud App Security-beleid](../media/mcas-sharepoint-confidential-label-filter.png)
10. Vouw onder **Beheermodel** de optie **Microsoft SharePoint Online** uit.
11. Schakel de selectievakjes **Beleidovereenkomst verzenden naar bestandseigenaar** en **Externe gebruikers verwijderen** in.
12. Typ voor het aangepaste meldingsbericht *Dit bestand is zeer gevoelig. Het bedrijfsbeleid verbiedt het delen met gasten*.
13. Klik op **Maken**.

Het is belangrijk op te merken dat dit beleid de toegang verwijdert voor bestanden die worden gedeeld via een koppeling voor *specifieke personen*. Het ontzegt niet de toegang tot niet-geverifieerde koppelingen (*voor iedereen*). Bovendien wordt de toegang niet ontzegd als de gast lid is van de site of het team als geheel. Als u van plan bent om zeer gevoelige documenten te gebruiken in een site of team met gastleden, kunt u overwegen [persoonlijke kanalen in Teams](https://support.office.com/article/60ef929a-4d68-418b-bf4f-5784db184ec9) te gebruiken en alleen leden van uw organisatie toe te laten tot de persoonlijke kanalen.

## <a name="test-the-solution"></a>De oplossing testen

Als u de oplossing wilt testen die in dit artikel wordt beschreven, maakt u een Word-document en slaat u het op in een documentbibliotheek. Het bestand delen met een gastgebruiker. Wanneer de gast probeert toegang te krijgen tot het document, moeten ze zich inschrijven voor meervoudige verificatie en vervolgens de gebruiksvoorwaarden accepteren.

Zodra de gasttoegang tot het document heeft, typt u *Project Saturnus* in het document en slaat u het op. Wanneer het document door Cloud App Security wordt gescand, moet het label *Zeer gevoelig* worden toegepast en moet de gastgebruiker er geen toegang meer toe kunnen krijgen.

U kunt de hulpprogramma's die in dit artikel worden beschreven, gebruiken in verschillende combinaties om een productieve, veilige omgeving voor het delen met gasten te maken voor uw organisatie.

## <a name="additional-options"></a>Aanvullende opties

Er zijn enkele extra opties beschikbaar in Microsoft 365 en Azure Active Directory waarmee u uw omgeving voor het delen met gasten kunt beveiligen.

- U kunt een lijst maken met toegestane of geweigerde domeinen om te beperken met wie gebruikers kunnen delen. Zie [Delen van SharePoint- en OneDrive-inhoud per domein beperken](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) en [Uitnodigingen voor B2B-gebruikers van specifieke organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) voor meer informatie.
- U kunt bepalen met welke andere Azure Active Directory-tenants uw gebruikers verbinding kunnen maken. Zie [Tenant beperkingen gebruiken voor het beheren van de toegang tot SaaS-cloud-toepassingen](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions) voor meer informatie.
- U kunt een beheerde omgeving maken waar partners kunnen helpen bij het beheren van gastaccounts. Zie [Een B2B-extranet maken met beheerde gasten](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet) voor meer informatie.

## <a name="see-also"></a>Zie ook

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Een B2B-extranet maken met beheerde gasten](b2b-extranet.md)
